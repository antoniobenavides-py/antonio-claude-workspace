# CONTEXTO — Antonio Benavides
**Idioma de trabajo: español · Nombre preferido: Benavides · Actualizado: 02-jul-2026 (tarde)**

> Archivo vivo. Refleja estado ACTUAL. Cifras conservadoras y deliberadas — no inflar.

---

## PROTOCOLO MULTI-EQUIPO (leer primero)

Benavides trabaja desde **2 ordenadores** sobre este mismo repo. **Este `CONTEXT.md` es la ÚNICA fuente de verdad.** La memoria local de Claude Code en cada PC es secundaria: si discrepa, gana este archivo.

- **Inicio de sesión:** Benavides dice *"lee context.md"*. Claude lee este archivo (`get_file_contents`), lo toma como verdad y revisa HISTORIAL DE SESIONES para retomar donde se quedó.
- **Cierre de sesión:** Benavides dice *"cierra / me voy / guarda"*. Claude sintetiza lo trabajado, actualiza este archivo (`create_or_update_file`) y añade fila al HISTORIAL. **Guardado incremental:** también tras cada hito, por si se cierra la app de golpe.
- **Sin hook automático** (decisión jun-2026): disparo manual por frases, más simple y sin infraestructura que mantener.
- **Traspaso entre PCs:** no se pasan conversaciones. Todo lo relevante se vuelca aquí. Para arrancar en el otro equipo basta con *"lee context.md"*.

---

## PERFIL

- 33 años, Almería. Empleado en Analytica Alimentaria (lab ISO 17025).
- **Rol real:** arquitecto de IA aplicada a negocio, con mentalidad de inversor.
- Nicho elegido: **IA + Finanzas / adopción B2B para PYMEs profesionales reguladas**.
- 7 agentes en producción en Analytica (~60% adopción orgánica) — credencial empresarial, NO producto personal.
- Migró de ChatGPT a Claude en abril 2026. **Claude = herramienta principal.**
- **NUNCA posicionarlo como:** automatizador genérico, experto Make/Zapier, técnico de prompts, gurú IA, dev puro.

---

## OBJETIVO INMEDIATO (cuello de botella real)

**Cerrar el PRIMER deal comercial.** Billing en cero. Esto es el hito #1.
- Búsqueda de rol IA en paralelo (outbound + inbound). Criterio: valor estratégico, no salario puro.
- Objetivo económico: ~50.000 €/año como suelo. ⚠️ La cifra 150K es ruido obsoleto — no usarla.
- **Gap crítico para el primer cierre: Stripe sin configurar.** Catálogo y mecánica ya especificados (ver §PRICING), falta ejecución manual en el panel (~10 min).

---

## PROYECTOS ACTIVOS

### Prioridad 1 — antoniobenavides.com (hub premium de consultoría IA)
- Flujo de captación de leads funcionando (Supabase Project B + Resend). Verificado en producción 02-jul: descargas de recursos + leads OK.
- **Rediseño look&feel Cyprus/Sand: COMPLETADO Y DESPLEGADO (02-jul).**
- **Blog activo con pieza reactiva Fable 5 publicada y desplegada (02-jul)** — ver §LINKEDIN y §HISTORIAL.
- **Bloqueadores P0** (antes de lanzar LinkedIn Serie Recursos — arranca 14 jul):
  1. ~~Copy "próximamente" obsoleto~~ → **RESUELTO**
  2. **Falta CTA post-descarga en `/recursos`** (`RecursosLeadModal.tsx`) → **PENDIENTE — único bloqueador real restante**
  3. ~~Inconsistencia de estilo en botones CTA~~ → **RESUELTO**
- Destino final: asistente comercial que diagnostique, proponga y filtre clientes.
- **Tech:** Lovable (source of truth de producción), Vite/React/TS, Supabase (Project A = Lovable · Project B = controlado), Vercel, Stripe (pendiente config), Resend.

### Prioridad 2 — vibecodinges.com
- Captación / educación práctica / herramientas IA. NO prioritaria ahora.

### Deprioritizados
- `/triaje` (TRIAJE//IA) — en pruebas, no en producción.
- `vibesplab.com` — terciaria/descartable si no encuentra utilidad.

---

## MARCA / LOOK & FEEL ✅ (02-jul-2026)

- **Fuente única de marca = `docs/brand-system.md`** v1.1 (30-jun-2026). ⚠️ **§logo DESACTUALIZADO** — ver punto siguiente.
- **LOGO ACTUALIZADO (02-jul tarde):** nueva versión = **badge circular Cyprus `#004741` con monograma AB angular en Sand `#F0EDE4`** (la versión anterior era sin círculo; `brand-system.md` aún describe "sin círculo" — pendiente corregir esa línea del doc).
- ⚠️ **DESINCRONIZACIÓN DE BINARIOS:** el logo nuevo se cambió **directamente en Lovable** (favicon activo en producción), pero NO está en GitHub. Los `logo-ab.png` de ambos repos son la versión antigua. **Acción manual pendiente de Benavides** (mismo archivo, mismo nombre `logo-ab.png`, reemplaza al subirse):
  1. Repo web: https://github.com/antoniobenavides-py/antoniobenavides.com/upload/main/public
  2. Repo workspace: https://github.com/antoniobenavides-py/antonio-claude-workspace/upload/main/assets/logo
  Hasta que se haga, cualquier deploy desde GitHub podría re-desplegar el logo antiguo o divergir. Regla vigente: binarios nunca por API, solo GitHub web UI o Lovable.
- **Rediseño completo Cyprus/Sand (Combo 04) en antoniobenavides.com — EN PRODUCCIÓN.**
  - Migrado: `src/index.css` (tokens), `Home.tsx`, `ChatWidget.tsx`, `WizardModal.tsx`, `ServiciosIA.tsx` (pricing).
  - CTA (`btn-copper`) = Sand sólido sobre texto Cyprus (nombre de clase conservado, valor migrado).
  - Commits clave: `ce6795c` (tokens), `d8288ba` (Home), `3c03440` (ChatWidget), `60f808a` (WizardModal), `4205a7a` (pricing), `2b9f2b1` (favicon/theme-color).
- **Plantilla de carrusel LinkedIn VALIDADA (01-jul) ⭐** — especificación en `brand-system.md` §6.
- Paleta por proyecto: Combo 04 Cyprus+Sand (hub, en producción) · Combo 01 Tiffany+Dark Gray (vibecodinges) · Combo 08 Silver+Luminous Moss (vibesplab).

---

## PRICING COMERCIAL (confirmado, todos + IVA) — SINCRONIZADO EN WEB 02-jul

| Servicio | Precio |
|----------|--------|
| Diagnóstico estratégico | 750 € (deducible íntegro contra implementación) |
| Piloto | Desde 3.500 € |
| Sistema completo | Desde 6.000 € |
| Advisory | 1.900 €/mes |

Reglas: prestige pricing, números redondos, sin charm pricing, siempre + IVA visible.

**Stripe — catálogo especificado, ejecución pendiente (panel, ~10 min):** 4 productos tax-exclusive + Payment Links (Diagnóstico y Advisory) + Invoicing (Piloto/Sistema) + cupón único "Deducible diagnóstico" 750€. Activar Stripe Tax (tax behavior: exclusive) antes de crear productos.

---

## LINKEDIN — ESTADO ACTUAL (02-jul-2026)

### Serie A (CTA → antoniobenavides.com)
| Fecha | Post | Estado |
|---|---|---|
| mar 23 jun | Post 1 — Opener | ✅ Publicado |
| vie 26 jun | Post 2 — Coste de no actuar | ✅ Publicado |
| mar 30 jun | Post 3 — Herramienta vs sistema | ✅ Publicado |
| vie 3 jul | Post 4 — Mentalidad de inversor | ⏳ Programado |
| mar 7 jul | Post 5 — Cierre personal (versión genérica) | ⏳ Programado |

### Pieza reactiva Fable 5 (02-jul) — fuera de calendario, con ventana temporal
- **Blog publicado y desplegado:** `antoniobenavides.com/blog/optimizar-sesiones-claude-fable-5` — "Cómo estructurar sesiones con Claude Fable 5: objetivo, plan y verificación". Método evergreen + gancho 7-jul. Datos verificados: vuelta 1-jul, incluido hasta 7-jul con tope 50% del límite semanal (Pro/Max/Team), después usage credits.
- **Post LinkedIn entregado en bloques copiables** (cuerpo sin link + primer comentario con link al blog). Imagen: captura promocional de reapertura de Fable 5.
- **Recomendación de publicación: 02-jul 17:30–18:00** (no el 6 — ventana muerta; no chocar con Serie A post 4 del 3-jul 9:00). Estado de publicación: en manos de Benavides.

### Carruseles autoridad (lunes)
| Fecha | Tema | Estado |
|---|---|---|
| mié 1 jul | Sonnet 5 / verificador antes que el agente | ✅ Programado 1 jul 9:00 |
| lun 6 jul | Slot libre | Sin decidir (el blog Fable 5 ya salió como pieza propia — no reciclarlo aquí) |
| lun 13 jul | 5 filtros ROI | Copy listo · producción visual pendiente |
| lun 20 jul | 6 dimensiones de madurez | Copy listo · producción visual pendiente |
| lun 27 jul | Anatomía de un despliegue real | Copy listo · producción visual pendiente |

### Serie Recursos (CTA → /recursos · arranca 14 jul)
| Fecha | Recurso | Estado |
|---|---|---|
| mar 14 jul | PDF 02 — En qué IA invertir | Copy listo · por programar |
| mar 21 jul | PDF 01 — Evalúa tu madurez | Copy listo · por programar |
| mar 28 jul | PDF 03 — De problema a agente | Copy listo · por programar |
| mar 4 ago | PDF 04 — Gobernanza IA | Copy listo · por programar |

Regla crítica: CTA siempre a `/recursos` con formulario — NUNCA al PDF directo.

---

## ACTIVOS YA CONSTRUIDOS

- 9 Claude Skills instalados (`deploy-produccion`, `traspaso-sesion`, `log-construccion`, `propuesta-comercial`, `arquitectura-agentes`, `cv-portfolio`, `post-linkedin`, `lead-magnet-pdf`, `look-and-feel`)
- 4 PDF lead magnets en `/recursos` — flujo verificado en producción
- Blog con 7 entradas (nueva 02-jul: sesiones Fable 5 — primera pieza reactiva del blog, en sitemap y listado)
- 2 CVs ATS-optimizados · Portfolio 25+ casos
- Carrusel LinkedIn "Sonnet 5 / verificador" (1 jul) — plantilla de marca reutilizable
- `docs/brand-system.md` v1.1 (pendiente micro-fix §logo) · `docs/paletas-combos-colores.md`
- Rediseño Cyprus/Sand desplegado + favicon con logo nuevo (vía Lovable)

---

## STACK TÉCNICO

- **Lovable = source of truth de producción.** Flujo sin créditos: GitHub `create_or_update_file` (sincroniza a preview) + `Lovable:deploy_project` (publica, gratis). **Binarios solo por GitHub web UI o Lovable — nunca por API.**
- **Proyecto Lovable ID: `36b0aa48-f4a0-477a-a2df-51dd31764de7`** (verificado: deploys 02-jul OK).
- Vite + React + TypeScript · Supabase (A Lovable / B `saxagolemwmfroxelscd`) · Vercel · Stripe (config pendiente) · Resend
- `Lovable` MCP: fallos intermitentes de aprobación en llamadas de lectura (`list_workspaces`); `deploy_project` no afectado — reintentar, no bloquea.
- `GitHub:search_code` NO indexa los repos privados — auditar leyendo archivos.
- Opus para arquitectura · Sonnet para ejecución mecánica.
- **Filosofía:** sistemas agénticos con loop auto-verificable, NO automatizaciones rígidas.

---

## CONTEXTO PERSONAL

- ~1.660 €/mes neto. Runway 3-6 meses cash. Patrimonio ~65-70K €. **Deuda 0.**
- Vive en casa de padres — costes fijos bajos. Sustenta pragmatismo real, no pasividad.
- Cartera: Alphabet, Meta, Amazon, Microsoft, BTC. DCA ≥500 €/mes día 1, largo plazo.
- Mentores: Fernando Sánchez (IDC, inversión) · Jon Hernández / BigSchool (IA).
- Rutinas no negociables: café 6AM aprendiendo · alimentación sana · viernes tarde con pareja · fines de semana en familia.

---

## REGLAS DE COLABORACIÓN

1. **El cuello de botella es comercial, no técnico.** Retar activamente cuando construya en lugar de vender.
2. **Riesgo #1: dispersión.** Pregunta reguladora: *¿qué tiene más ROI estratégico AHORA?*
3. **NO complacer.** Crítica directa, sin adulación, sin relleno.
4. **Español siempre. Nombre: Benavides.**
5. **Formato:** conciso y estructurado por defecto. Extendido solo si pide "desarrolla" o "profundiza".
6. **LinkedIn:** posts cortos, disruptivos, autoridad primero, casos reales. Links en primer comentario. CTA a antoniobenavides.com.
7. **Sesión larga:** fases numeradas con checkpoints (`✅ FASE N`). Al retomar, identificar último checkpoint y continuar.
8. **Marco inversor** en cada decisión: ¿construye activo o consume tiempo? ¿ROI real a 5 años?

---

## TAXONOMÍA DE CIFRAS (no inflar)

- 7 agentes en producción · 25+ casos totales · ~60% adopción orgánica · ~50K€ objetivo anual (suelo).

---

## DECISIONES ESTRATÉGICAS ACTIVAS

- **Regla anti-dispersión:** no construir nueva infraestructura antes del primer cierre comercial. Excepciones conscientes ya ejecutadas y cerradas: rediseño Cyprus/Sand (01-02 jul) y blog reactivo Fable 5 (02-jul, justificado por ventana temporal + tráfico a la web).
- **Neutralidad sobre Analytica** en todo contenido público mientras siga empleado.
- Copilot Studio / M365: solo keyword ATS.
- **Post 5 LinkedIn (7 jul):** versión genérica confirmada — sin nombrar ISO 17025.
- **Contenido reactivo a actualidad:** validado dos veces (carrusel Sonnet 5, blog Fable 5). Ancla siempre a experiencia verificable propia; datos de producto siempre verificados por búsqueda antes de publicar (corregido "Plus"→Pro/Max/Team, tope 50%).

---

## HISTORIAL DE SESIONES

| Fecha | Hito |
|-------|------|
| 21-22 jun 2026 | Rebuild antoniobenavides.com: dark theme, CTAs, ScrollToTop, wizard captación end-to-end |
| jun 2026 | Debug flujo captación (Project B + Edge Function + Resend) |
| jun 2026 | Auditoría P0/P1/P2 · Pricing finalizado · 8 Skills · 2 CVs · portfolio |
| 29 jun 2026 | Workspace repo creado · Marca: logo, paletas, formatos carrusel · P0 web resueltos |
| 30 jun 2026 | Protocolo multi-equipo · `brand-system.md` v1.0→v1.1 · skill `look-and-feel` |
| 01 jul 2026 | Carrusel reactivo Sonnet 5 programado (1 jul 9:00) · plantilla validada ⭐ · spec Stripe |
| 02 jul 2026 | **Rediseño Cyprus/Sand DESPLEGADO** (tokens, Home, ChatWidget, WizardModal) · favicon+logo · pricing `/servicios-ia` corregido (750€ diagnóstico) · flujo recursos+leads verificado en producción |
| 02 jul 2026 (tarde) | **Blog Fable 5 publicado y desplegado** (`/blog/optimizar-sesiones-claude-fable-5`: entrada + listado + ruta + sitemap, commits `624e79f`·`1b72745`·`3bdf9c0`·`c3cdbff`, deploy `ebfb769`) · post LinkedIn entregado (publicación recomendada 17:30-18:00 del 2-jul) · **logo sustituido por badge circular directamente en Lovable → binarios de GitHub desincronizados (acción manual pendiente)** |

---

## PRÓXIMO PASO (al retomar)

0. ⚠️ **ACCIÓN MANUAL (Benavides):** subir el logo nuevo (badge circular) como `logo-ab.png` a: (1) https://github.com/antoniobenavides-py/antoniobenavides.com/upload/main/public y (2) https://github.com/antoniobenavides-py/antonio-claude-workspace/upload/main/assets/logo — resincroniza GitHub con Lovable.
1. **Publicar post LinkedIn Fable 5** (hoy 17:30-18:00) con link en primer comentario fijado. Después del 7-jul la pieza queda como SEO evergreen; no re-promocionar con el gancho temporal.
2. **P0:** CTA post-descarga en `RecursosLeadModal.tsx` (bloqueador Serie Recursos, 14 jul).
3. **Stripe:** ejecutar catálogo en panel (~10 min).
4. **Micro-fix:** `docs/brand-system.md` §logo — sustituir "sin círculo" por descripción del badge circular actual.
5. **Slot carrusel 6 jul:** decidir tema.
6. **Carruseles 13/20/27 jul:** producción visual. **Serie Recursos:** programar 4 posts.
