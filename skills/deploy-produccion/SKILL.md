---
name: deploy-produccion
description: Runbook para desplegar, publicar o commitear cambios en el stack web de Benavides (Lovable + Vite/React/TypeScript + Supabase + GitHub + Vercel). Úsalo SIEMPRE que la tarea implique deploy, publicar, "subir a producción", commit, push, editar un Edge Function, tocar Supabase, mover algo en Lovable, o cualquier cambio en antoniobenavides.com, vibecodinges.com o vibesplab.com. Codifica la arquitectura de dos proyectos Supabase, qué tool despliega qué, las trampas de SHA/binarios/silent-failures y el protocolo de verificación end-to-end. Consúltalo antes de declarar nada "desplegado".
---

# Deploy a producción — Lovable + Supabase + GitHub

Runbook operativo del stack web de Benavides. El objetivo es evitar los fallos silenciosos que ya costaron sprints enteros de debugging. Lee la sección relevante antes de actuar y **nunca declares "desplegado" sin pasar el checklist de verificación**.

## Arquitectura crítica: dos proyectos Supabase

Hay DOS proyectos Supabase y confundirlos es la causa raíz de los fallos históricos:

- **Project A — gestionado por Lovable.** Ref interno `36b0aa48-f4a0-477a-a2df-51dd31764de7`. Benavides NO puede desplegar aquí. Aloja el embudo comercial principal: WizardModal, tabla `leads`, Edge Function `submit-commercial-lead`.
- **Project B — propiedad de Benavides.** Ref `saxagolemwmfroxelscd`. Control total. Aloja el flujo de recursos (`/recursos`): tabla `resource_subscribers`, Edge Function de descarga, configuración Resend embebida en el código de la función.

**Regla de oro:** antes de desplegar un Edge Function o ejecutar SQL, decide explícitamente a qué proyecto va. Históricamente todos los deploys iban a Project B mientras la web llamaba a Project A → cada fix fallaba en silencio. Si no sabes a cuál pertenece el flujo, deténte y resuélvelo antes de tocar nada.

`Lovable:query_database` se conecta a **Project A**, no a Project B. Para actuar sobre Project B usa Supabase MCP o la extensión `http` desde la propia base de datos.

## Fuente de verdad y qué despliega cada cosa

- **Lovable es la fuente de verdad de producción, NO GitHub.** Un commit a GitHub sincroniza solo al *preview* de Lovable. Producción requiere el botón **Publish** de Lovable o `Lovable:deploy_project`.
- **`Lovable:deploy_project` publica SOLO el build de frontend** (Vite/React). NO despliega ni redespliega Edge Functions de Supabase bajo ninguna circunstancia.
- **Edge Functions se despliegan aparte**, al proyecto Supabase correcto, vía Supabase MCP / CLI. Un cambio en una función no llega a producción por hacer `deploy_project`.

### Árbol de decisión de deploy

| Tipo de cambio | Cómo llega a producción |
|---|---|
| Frontend (componente, copy, estilo, ruta) | `GitHub:create_or_update_file` → sincroniza a preview Lovable → `Lovable:deploy_project` o Publish |
| Edge Function (lógica backend) | Deploy directo al proyecto Supabase correcto (A o B). `deploy_project` NO lo hace |
| Schema / datos (tabla, policy, migración) | SQL contra el proyecto correcto. Project B vía Supabase MCP / `http`; Project A vía `Lovable:query_database` |
| Binario (PDF, imagen) | GitHub web UI o file manager de Lovable. NUNCA por API |

## Trampas de GitHub (verificadas por error)

- **Usa `GitHub:create_or_update_file` (un fichero)** con un **SHA recién obtenido**. Haz `get_file_contents` inmediatamente antes de escribir. Un SHA de antes en la misma sesión está obsoleto y el commit falla.
- **`push_files` (batch) es poco fiable** — devuelve "No approval received" de forma intermitente. No lo uses; commitea fichero a fichero.
- **Los binarios (PDF, imágenes) NO se pueden escribir por API** — llegan corruptos. Súbelos por la web UI de GitHub (arrastrar al directorio `public/`) o por el file manager de Lovable.
- **`GitHub:search_code` busca en el CONTENIDO de los ficheros, no en las rutas.** Buscar un nombre de función como `get-resource-download-url` devuelve cero resultados si ningún cuerpo de fichero contiene ese string, aunque el directorio exista con ese nombre.

## Trampa de Supabase: el cliente NO lanza excepciones

El cliente de Supabase **no hace throw** ante errores: devuelve `{ error }`. En Edge Functions y en frontend, escribe `if (error) throw error` **antes** de marcar estado de éxito. Si no, tienes el patrón de fallo silencioso que perdió todos los leads de `/recursos`: la UI muestra éxito mientras el lead nunca se guarda.

`Lovable:query_database` y el MCP de Lovable sufren **caídas de conexión intermitentes** que cortan secuencias DDL multi-statement. Ejecuta DDL statement a statement. Si un `DROP POLICY` corre pero el `CREATE POLICY` siguiente se corta, la policy queda eliminada sin recrear → re-ejecuta.

## Secretos de producción (embudo Project A)

Cinco secretos confirmados en Lovable: `SUPABASE_URL`, `SUPABASE_SERVICE_ROLE_KEY`, `RESEND_API_KEY`, `LEAD_ALERT_TO_EMAIL`, `LEAD_ALERT_FROM_EMAIL`. Para flujos en Project B, la config Resend va embebida server-side en el código del Edge Function.

## Checklist de verificación — obligatorio antes de declarar "hecho"

No cierres una tarea como desplegada sin esto. "Desplegado pero sin verificar" no cuenta.

1. **¿El cambio fue al proyecto Supabase correcto?** (A vs B) — confírmalo, no lo asumas.
2. **Frontend:** ¿se hizo `deploy_project` / Publish después del commit? El preview no es producción.
3. **Edge Function:** ¿se redesplegó la función al proyecto correcto? `deploy_project` no la toca.
4. **Flujos de lead/email/descarga — test real end-to-end:**
   - ¿La tabla destino existe? (una tabla ausente reproduce el bug de pérdida silenciosa de leads)
   - ¿El dominio/`SITE_URL` apunta bien? (afecta a la corrección de los enlaces de PDF en los emails)
   - Inserta un lead real → confirma fila en la tabla + email entregado en bandeja + descarga del PDF funcional.
   - Para Project B, el test se puede invocar directamente desde la base de datos con la extensión `http`; busca `emailStatus: sent`.
5. **Reporta el resultado del test, no la intención.** Si no se ha probado, dilo explícitamente.

## Flujo credit-efficient

El loop sin coste: autorar código vía `GitHub:create_or_update_file` → sincroniza a Lovable automáticamente → publicar con `Lovable:deploy_project` (gratis). Solo `Lovable:send_message` (el prompt al agente de Lovable) consume créditos — úsalo solo cuando un cambio esté hardcodeado en el árbol de Lovable y no se pueda tocar desde el repo. Un prompt por iteración, concreto.
