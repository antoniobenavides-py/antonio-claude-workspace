# CONTEXTO — Antonio Benavides
**Idioma de trabajo: español · Nombre preferido: Benavides · Actualizado: 30-jun-2026**

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

---

## PROYECTOS ACTIVOS

### Prioridad 1 — antoniobenavides.com (hub premium de consultoría IA)
- Flujo de captación de leads funcionando (Supabase Project B + Resend).
- **Bloqueadores P0** (antes de lanzar LinkedIn Serie Recursos — arranca 14 jul):
  1. ~~Copy "próximamente" obsoleto~~ → **RESUELTO** (RecursosGratuitos.tsx → btn-copper "Ver recursos gratuitos →", 29-jun)
  2. Falta CTA post-descarga → **PENDIENTE**
  3. ~~Inconsistencia de estilo en botones CTA~~ → **RESUELTO** (Recursos.tsx → btn-copper, 29-jun)
- Destino final: asistente comercial que diagnostique, proponga y filtre clientes.
- **Tech:** Lovable (source of truth de producción), Vite/React/TS, Supabase (Project A = Lovable · Project B = controlado), Vercel, Stripe, Resend.

### Prioridad 2 — vibecodinges.com
- Captación / educación práctica / herramientas IA. NO prioritaria ahora.
- Pendiente: rebuild web + fix home CTA/nav. Idea: recomendador de LLMs con login Google.

### Deprioritizados
- `/triaje` (TRIAJE//IA) — en pruebas, no en producción.
- `vibesplab.com` — terciaria/descartable si no encuentra utilidad.

---

## MARCA / LOOK & FEEL

- **Fuente única de marca = `docs/brand-system.md`** (en este repo). NO dispersar la marca en skills locales.
- **Estado: v1.0 completo (30-jun-2026).** Logo, paleta multi-proyecto, tipografía y formatos de carrusel LinkedIn consolidados.
- Paleta decidida: sistema verde multi-proyecto (Cyprus+Sand para hub · Tiffany+Dark Gray para vibecodinges · Luminous Moss+Silver para vibesplab).
- Logo: monograma AB en círculo, Cyprus+Sand, PNG en workspace. SVG pendiente para rediseño web.
- Rediseño web Cyprus/Sand: **no antes del primer cierre comercial.**
- Siguiente: crear skill local `look-and-feel` apuntando a `docs/brand-system.md`.

---

## LINKEDIN — ESTADO ACTUAL (30-jun-2026)

### Serie A (CTA → antoniobenavides.com)
| Fecha | Post | Estado |
|---|---|---|
| mar 23 jun | Post 1 — Opener | ✅ Publicado |
| vie 26 jun | Post 2 — Coste de no actuar | ✅ Publicado |
| mar 30 jun | Post 3 — Herramienta vs sistema | ⏳ Programado |
| vie 3 jul | Post 4 — Mentalidad de inversor | ⏳ Programado |
| mar 7 jul | Post 5 — Cierre personal (versión genérica, sin ISO 17025) | ⏳ Programado |

### Carruseles autoridad (lunes, CTA nulo o suave)
| Fecha | Tema | Estado |
|---|---|---|
| lun 6 jul | Agente vs automatización | Copy listo · producción visual pendiente |
| lun 13 jul | 5 filtros ROI | Copy listo · producción visual pendiente |
| lun 20 jul | 6 dimensiones de madurez | Copy listo · producción visual pendiente |
| lun 27 jul | Anatomía de un despliegue real | Copy listo · producción visual pendiente |

Producción visual: herramienta externa (ChatGPT Image / Gamma / Canva AI). Brief estandarizado pendiente de ejemplos de carruseles anteriores que aportará Benavides.

### Serie Recursos (CTA → /recursos · arranca 14 jul)
| Fecha | Recurso | Estado |
|---|---|---|
| mar 14 jul | PDF 02 — En qué IA invertir | Copy listo · por programar |
| mar 21 jul | PDF 01 — Evalúa tu madurez | Copy listo · por programar |
| mar 28 jul | PDF 03 — De problema a agente | Copy listo · por programar |
| mar 4 ago | PDF 04 — Gobernanza IA | Copy listo · por programar |

Regla crítica: CTA siempre a `/recursos` con formulario — NUNCA al PDF directo.

---

## PRICING COMERCIAL (confirmado, todos + IVA)

| Servicio | Precio |
|----------|--------|
| Diagnóstico estratégico | 750 € (deducible contra implementación) |
| Piloto | 3.500 € |
| Sistema completo | 6.000 € |
| Advisory | 1.900 €/mes |

Reglas: prestige pricing, números redondos, sin charm pricing, sin lista pública.

---

## ACTIVOS YA CONSTRUIDOS

- 8 Claude Skills: `deploy-produccion`, `traspaso-sesion`, `log-construccion`, `propuesta-comercial`, `arquitectura-agentes`, `cv-portfolio`, `post-linkedin`, `lead-magnet-pdf`
- 4 PDF lead magnets en `/recursos`
- 2 CVs ATS-optimizados (variante generalista IA + variante finanzas+IA)
- Portfolio: 25+ casos con métricas concretas
- LinkedIn Serie A corriendo (→ 7 jul). Serie Recursos arranca 14 jul.
- `docs/brand-system.md` v1.0 — sistema de marca completo

---

## STACK TÉCNICO

- **Lovable = source of truth de producción.** Cambios vía `send_message` o Publish. GitHub solo actualiza preview.
- Vite + React + TypeScript · Supabase · Vercel · Stripe · Resend
- LLMs: OpenAI, Claude, Gemini, open-source. Opus para arquitectura · Sonnet para ejecución mecánica.
- **Filosofía:** sistemas agénticos con loop auto-verificable, NO automatizaciones rígidas.

### Protocolo de trabajo en web
- Leer código real de GitHub antes de proponer cambios.
- Commits quirúrgicos, un solo archivo.
- Verificar deploy tras cada fase (skill `deploy-produccion`).
- Un prompt por iteración en Lovable, concreto y credit-efficient.

---

## CONTEXTO PERSONAL

- ~1.660 €/mes neto. Runway 3-6 meses cash. Patrimonio ~65-70K €. **Deuda 0.**
- Vive en casa de padres — costes fijos bajos. Sustenta pragmatismo real, no pasividad.
- Cartera inversión: Alphabet, Meta, Amazon, Microsoft, BTC. DCA ≥500 €/mes día 1, largo plazo (5+ años).
- Mentores: Fernando Sánchez (IDC, inversión) · Jon Hernández / BigSchool (IA).
- Rutinas no negociables: café 6AM aprendiendo · alimentación sana · viernes tarde con pareja · fines de semana en familia.

---

## REGLAS DE COLABORACIÓN

1. **El cuello de botella es comercial, no técnico.** Retar activamente cuando construya en lugar de vender.
2. **Riesgo #1: dispersión.** Pregunta reguladora: *¿qué tiene más ROI estratégico AHORA?*
3. **NO complacer.** Crítica directa, sin adulación, sin relleno.
4. **Español siempre. Nombre: Benavides.**
5. **Formato:** conciso y estructurado por defecto. Extendido solo si pide "desarrolla" o "profundiza". Sin explicar conceptos básicos de IA.
6. **LinkedIn:** posts cortos, disruptivos, autoridad primero, casos reales. Links en primer comentario (nunca en el cuerpo). CTA a antoniobenavides.com.
7. **Sesión larga:** fases numeradas con checkpoints (`✅ FASE N`). Al retomar, identificar último checkpoint y continuar.
8. **Marco inversor** en cada decisión: ¿construye activo o consume tiempo? ¿ROI real a 5 años?

---

## TAXONOMÍA DE CIFRAS (no inflar)

- 7 agentes en producción
- 25+ casos totales (agentes + copilotos + flows)
- ~60% adopción orgánica
- ~50K€ objetivo anual (suelo, no techo)

---

## DECISIONES ESTRATÉGICAS ACTIVAS

- **Regla anti-dispersión:** no construir nueva infraestructura antes del primer cierre comercial.
- **Neutralidad sobre Analytica** en todo contenido público mientras siga empleado.
- Copilot Studio / M365: solo keyword ATS, no core ni especialidad principal.
- **Post 5 LinkedIn (7 jul):** versión genérica confirmada — sin nombrar ISO 17025 explícitamente.

---

## HISTORIAL DE SESIONES

| Fecha | Hito |
|-------|------|
| 21-22 jun 2026 | Rebuild antoniobenavides.com: dark theme, CTAs, ScrollToTop, wizard captación end-to-end |
| jun 2026 | Debug flujo captación (Supabase equivocado → Project B + Edge Function + Resend) |
| jun 2026 | Auditoría P0/P1/P2: Home.tsx, Recursos.tsx, ServiciosIA.tsx |
| jun 2026 | Pricing comercial finalizado + 8 Skills + 2 CVs + portfolio |
| jun 2026 | Posicionamiento final: "arquitecto de IA aplicada a negocio, con mentalidad de inversor" |
| 29 jun 2026 | Creación de antonio-claude-workspace en GitHub + integración de contexto completo |
| 29 jun 2026 | Marca: logo (monograma AB círculo Cyprus+Sand), paleta multi-proyecto (sistema verde), formatos carrusel LinkedIn. Copy de 4 carruseles julio + 4 posts Serie Recursos listos. P0 web resueltos (RecursosGratuitos.tsx + Recursos.tsx → btn-copper, desplegado en producción). |
| 30 jun 2026 | Montado PROTOCOLO MULTI-EQUIPO. Creado docs/brand-system.md v1.0 completo (logo, paleta, tipografía, carruseles). |

---

## PRÓXIMO PASO (al retomar)

1. **P0 pendiente:** CTA post-descarga en `/recursos` (único bloqueador restante antes de 14 jul).
2. **LinkedIn carruseles:** producir visualmente los 4 de julio con herramienta externa (pendiente brief estandarizado — Benavides aportará ejemplos de carruseles anteriores).
3. **Serie Recursos:** programar los 4 posts (14, 21, 28 jul · 4 ago) en LinkedIn scheduler.
4. **Skill `look-and-feel`:** crear apuntando a `docs/brand-system.md` (baja prioridad).
5. **Sesión pendiente:** definir modelo de facturación y cobro (gap comercial urgente antes del primer deal).
