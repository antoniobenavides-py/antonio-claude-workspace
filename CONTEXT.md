# CONTEXTO — Antonio Benavides
**Idioma de trabajo: español · Nombre preferido: Benavides · Actualizado: 02-jul-2026**

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
- **Gap crítico para el primer cierre: Stripe sin configurar.** Catálogo y mecánica ya especificados (ver §STACK), falta ejecución manual en el panel (~10 min).

---

## PROYECTOS ACTIVOS

### Prioridad 1 — antoniobenavides.com (hub premium de consultoría IA)
- Flujo de captación de leads funcionando (Supabase Project B + Resend). **Verificado en producción 02-jul: descargas de recursos + leads OK.**
- **Rediseño look&feel Cyprus/Sand: COMPLETADO Y DESPLEGADO (02-jul)** — ver §MARCA.
- **Bloqueadores P0** (antes de lanzar LinkedIn Serie Recursos — arranca 14 jul):
  1. ~~Copy "próximamente" obsoleto~~ → **RESUELTO**
  2. **Falta CTA post-descarga en `/recursos`** → **PENDIENTE — único bloqueador real restante**
  3. ~~Inconsistencia de estilo en botones CTA~~ → **RESUELTO**
- Destino final: asistente comercial que diagnostique, proponga y filtre clientes.
- **Tech:** Lovable (source of truth de producción), Vite/React/TS, Supabase (Project A = Lovable · Project B = controlado), Vercel, Stripe (pendiente config), Resend.

### Prioridad 2 — vibecodinges.com
- Captación / educación práctica / herramientas IA. NO prioritaria ahora.
- Pendiente: rebuild web + fix home CTA/nav. Idea: recomendador de LLMs con login Google.

### Deprioritizados
- `/triaje` (TRIAJE//IA) — en pruebas, no en producción.
- `vibesplab.com` — terciaria/descartable si no encuentra utilidad.

---

## MARCA / LOOK & FEEL — CERRADO Y DESPLEGADO ✅ (02-jul-2026)

- **Fuente única de marca = `docs/brand-system.md`** v1.1 (30-jun-2026).
- **Rediseño completo Cyprus/Sand (Combo 04) en antoniobenavides.com — EN PRODUCCIÓN.**
  - Migrado: `src/index.css` (tokens → todas las páginas interiores), `Home.tsx` (~200 hex + canvas + partículas), `ChatWidget.tsx`, `WizardModal.tsx`, `ServiciosIA.tsx` (pricing, ver abajo).
  - Auditadas y confirmadas token-driven sin residuos de paleta antigua: Header, Footer, AgentesCopilotos, IAOperaciones, resto de páginas interiores.
  - CTA (`btn-copper`) = Sand sólido `#F0EDE4` sobre texto Cyprus `#004741` (nombre de clase conservado por compatibilidad, valor migrado).
  - Commits clave: `ce6795c` (tokens), `d8288ba` (Home), `3c03440` (ChatWidget), `60f808a` (WizardModal), `4205a7a` (pricing ServiciosIA).
- **Logo:** monograma AB geométrico, variante DARK (fondo Cyprus, símbolo Sand). **PNG subido y activo:** `public/logo-ab.png` en el repo de la web (antoniobenavides.com), no solo en workspace. Favicon + `apple-touch-icon` + `theme-color` cableados en `index.html` (commit `2b9f2b1`) y desplegados.
- **Catálogo de paletas** — `docs/paletas-combos-colores.md` (10 combos con asignación por proyecto).
- Paleta por proyecto: Combo 04 Cyprus+Sand (hub, ya en producción) · Combo 01 Tiffany+Dark Gray (vibecodinges) · Combo 08 Silver+Luminous Moss (vibesplab).
- **Plantilla de carrusel LinkedIn VALIDADA (01-jul) ⭐** — especificación en `brand-system.md` §6.

---

## PRICING COMERCIAL (confirmado, todos + IVA) — SINCRONIZADO EN WEB 02-jul

| Servicio | Precio | Estado en `/servicios-ia` |
|----------|--------|---|
| Diagnóstico estratégico | 750 € (deducible íntegro contra implementación) | ✅ Corregido (antes decía "desde 1.500€", desactualizado) |
| Piloto | Desde 3.500 € | ✅ |
| Sistema completo | Desde 6.000 € | ✅ |
| Advisory | 1.900 €/mes | ✅ |

Reglas: prestige pricing, números redondos, sin charm pricing, sin lista pública, siempre + IVA visible.

**Stripe — catálogo especificado, ejecución pendiente (panel, ~10 min):**
4 productos tax-exclusive (Diagnóstico 750€ pago único, Piloto 3.500€, Sistema 6.000€, Advisory 1.900€/mes recurrente) + Payment Links para Diagnóstico y Advisory + Invoicing para Piloto/Sistema + cupón único "Deducible diagnóstico" 750€. Activar Stripe Tax (tax behavior: exclusive) antes de crear productos.

---

## LINKEDIN — ESTADO ACTUAL (02-jul-2026)

### Serie A (CTA → antoniobenavides.com)
| Fecha | Post | Estado |
|---|---|---|
| mar 23 jun | Post 1 — Opener | ✅ Publicado |
| vie 26 jun | Post 2 — Coste de no actuar | ✅ Publicado |
| mar 30 jun | Post 3 — Herramienta vs sistema | ✅ Publicado |
| vie 3 jul | Post 4 — Mentalidad de inversor | ⏳ Programado |
| mar 7 jul | Post 5 — Cierre personal (versión genérica, sin ISO 17025) | ⏳ Programado |

### Carruseles autoridad (lunes, CTA nulo o suave)
| Fecha | Tema | Estado |
|---|---|---|
| ~~mié 1 jul~~ | Sonnet 5 / verificador antes que el agente | ✅ Programado 1 jul 9:00 |
| lun 6 jul | Slot libre (cubierto conceptualmente por el del 1 jul) | ⚠️ Sin decidir — **candidato natural: blog Fable 5 (ver PENDIENTE DE DECISIÓN)** |
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

## PENDIENTE DE DECISIÓN — propuesto 02-jul, sin confirmar por Benavides

**Blog "cómo optimizar sesiones en Fable 5 antes del 7 jul"** + post LinkedIn con foto oficial de reapertura.
- Contexto verificado por búsqueda web: Fable 5 volvió el 1-jul tras 18 días de suspensión por controles de exportación (levantados 30-jun). Ventana real: hasta el 7-jul con tope del 50% del límite semanal en Pro/Max/Team (NO "Plus" — ese plan no existe en Claude); después pasa a usage credits a $10/$50 por Mtok, 2× Opus 4.8 y ~5× Sonnet 5.
- Veredicto dado: viable SOLO si sale el mismo día 2-jul por la tarde (no el 6, que mata la ventana de utilidad a 1 día). Ángulo recomendado: método evergreen (objetivo → plan → verificación, aplicado a Fable 5) en vez de "trucos de promo", para que sobreviva a la fecha.
- **No ejecutado — pendiente confirmación explícita de Benavides.** Si no se confirma en las próximas horas, la ventana de valor se cierra sola y el ítem debe darse por caducado, no arrastrarse a sesiones futuras como si siguiera vigente.

---

## ACTIVOS YA CONSTRUIDOS

- 9 Claude Skills: `deploy-produccion`, `traspaso-sesion`, `log-construccion`, `propuesta-comercial`, `arquitectura-agentes`, `cv-portfolio`, `post-linkedin`, `lead-magnet-pdf`, `look-and-feel`
- 4 PDF lead magnets en `/recursos` — descarga + captura de lead verificada funcionando en producción (02-jul)
- 2 CVs ATS-optimizados (variante generalista IA + variante finanzas+IA)
- Portfolio: 25+ casos con métricas concretas
- LinkedIn Serie A corriendo (→ 7 jul). Serie Recursos arranca 14 jul.
- Carrusel LinkedIn "Sonnet 5 / verificador" (1 jul) — plantilla de marca reutilizable
- `docs/brand-system.md` v1.1 — sistema de marca completo, **ya reflejado 1:1 en la web de producción**
- `docs/paletas-combos-colores.md` — catálogo de 10 combos de color
- Rediseño Cyprus/Sand de antoniobenavides.com — **desplegado y verificado en producción**

---

## STACK TÉCNICO

- **Lovable = source of truth de producción.** Cambios vía GitHub `create_or_update_file` (sincroniza a preview) + `Lovable:deploy_project` (publica a producción, gratis). Binarios (PDF, PNG) solo por GitHub web UI.
- Vite + React + TypeScript · Supabase · Vercel · Stripe (config pendiente) · Resend
- LLMs: OpenAI, Claude, Gemini, open-source. Opus para arquitectura · Sonnet para ejecución mecánica.
- **Filosofía:** sistemas agénticos con loop auto-verificable, NO automatizaciones rígidas.
- `Lovable` MCP sufre fallos intermitentes de aprobación ("No approval received") en llamadas de solo lectura (`list_workspaces`); `deploy_project` no se ha visto afectado — reintentar si falla, no bloquea el flujo crítico.

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

- **Regla anti-dispersión:** no construir nueva infraestructura antes del primer cierre comercial. **Excepción consciente registrada 01-jul:** Benavides decidió explícitamente priorizar el rediseño look&feel antes del P0 comercial, pese a advertencia de dispersión — decisión suya, ejecutada, ya cerrada.
- **Neutralidad sobre Analytica** en todo contenido público mientras siga empleado.
- Copilot Studio / M365: solo keyword ATS, no core ni especialidad principal.
- **Post 5 LinkedIn (7 jul):** versión genérica confirmada — sin nombrar ISO 17025 explícitamente.
- **Contenido reactivo a actualidad:** válido y de alto valor. Precedente: carrusel Sonnet 5 (1 jul). Ancla siempre a experiencia verificable propia; nunca logos de terceros en portada.

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
| 29 jun 2026 | Marca: logo, paleta multi-proyecto, formatos carrusel LinkedIn. Copy carruseles julio + posts Serie Recursos listos. P0 web resueltos. |
| 30 jun 2026 | Protocolo multi-equipo. `docs/brand-system.md` v1.0. |
| 30 jun 2026 | Marca y branding CERRADOS: skill `look-and-feel`, `docs/paletas-combos-colores.md`, `brand-system.md` v1.1. PNG logo pendiente subida manual. |
| 01 jul 2026 | Carrusel LinkedIn reactivo a Sonnet 5, programado 1 jul 9:00. Plantilla de carrusel validada como referencia de oro. Stripe: catálogo y mecánica de cobro especificados (ejecución manual pendiente). |
| 02 jul 2026 | **Rediseño Cyprus/Sand DESPLEGADO A PRODUCCIÓN.** index.css, Home.tsx, ChatWidget, WizardModal migrados. Logo PNG subido y renombrado en repo de la web; favicon + theme-color activos. Pricing `/servicios-ia` corregido (750€ diagnóstico, no 1.500€ — dato desactualizado). Verificado en producción: descargas de recursos + captura de leads funcionando. Propuesto (sin confirmar) blog + post LinkedIn sobre optimización de sesiones Fable 5 antes del 7-jul. |

---

## PRÓXIMO PASO (al retomar)

1. **P0 real y único bloqueador de Serie Recursos (14 jul):** CTA post-descarga en `RecursosLeadModal.tsx` — tras la descarga solo hay botón, falta puente hacia diagnóstico/servicios.
2. **Stripe:** ejecutar catálogo en panel (~10 min) — condición para poder cobrar el mismo día que un lead cierre.
3. **Blog Fable 5:** si Benavides no lo confirma pronto, dar la ventana por caducada — no proponerlo de nuevo pasado el 7-jul.
4. **Slot carrusel 6 jul:** decidir tema (libre, o Fable 5 si se confirma a tiempo).
5. **LinkedIn carruseles:** producir visualmente los de julio (13, 20, 27).
6. **Serie Recursos:** programar los 4 posts (14, 21, 28 jul · 4 ago) en LinkedIn scheduler.
7. **Modelo de facturación y cobro:** definir junto con la ejecución de Stripe.
