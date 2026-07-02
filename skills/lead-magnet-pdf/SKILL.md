---
name: lead-magnet-pdf
description: Crea lead magnets en PDF alineados con el brand system de Benavides para captación vía /recursos (Track B). Úsalo SIEMPRE que pida un recurso descargable, un lead magnet, una guía, un PDF de captación, una plantilla descargable o material para /recursos. Codifica los tokens de marca (Cyprus/Sand Combo 04, tipografías del carrusel, lockup AB), la estructura de un lead magnet que capta (gancho, valor usable, anclaje de autoridad, puente a diagnóstico), el tratamiento portada-oscura/interior-claro y las reglas de voz. Genera el PDF con el motor recursos_engine (tools/) o el skill de PDF.
---

# Lead magnet PDF

Los lead magnets alimentan el Track B (captación vía `/recursos`). Deben ser premium, inmediatamente útiles y coherentes con la marca. Un recurso descargable es un activo de captación, no un folleto: entrega valor real y construye el puente hacia el diagnóstico.

## Tokens de marca (Combo 04 — Cyprus/Sand, vigente desde 02-jul-2026)

| Elemento | Valor |
|---|---|
| Cyprus (base oscura) | `#004741` · profundo `#00332F` · hairline sobre Cyprus `#2E6B62` |
| Sand (base clara) | `#F0EDE4` · brillante `#F7F5EF` · panel sobre Sand `#E9E5D8` |
| Texto sobre Sand | cuerpo `#123F3A` · muted `#56776F` · hairline `#C4CFC7` |
| Texto sobre Cyprus | principal Sand · muted `#9FB6B0` |
| Tipografías | **Lora Bold/SemiBold** (titulares) · **Poppins** Regular/Medium/Light (cuerpo) · **DejaVu Sans Mono** (overlines con tracking) — mismo stack que el carrusel LinkedIn validado |
| Logo | lockup AB (monograma + wordmark) en `assets/logo/`: `logo-lockup-sand.png` (para fondos Cyprus) y `logo-lockup-cyprus.png` (para fondos Sand), PNG transparentes |
| Sistema | **bicolor estricto**: sin cobre, sin teal, sin tercer color. Acentos = bloques Cyprus con texto Sand sobre páginas Sand |
| Nomenclatura | doble barra para entidades de marca (VIBECODING//ES, TRIAJE//IA) |

**Tratamiento de páginas:** portada y página final CTA = **Cyprus oscuro** (identidad del carrusel: overline mono con tracking + regla corta + titular Lora + lockup). Páginas interiores = **Sand claro** (print-friendly), marco fino interior, header con overline de sección, footer mono `ANTONIO BENAVIDES · IA APLICADA A NEGOCIO — antoniobenavides.com · N`.

**Motor:** `tools/recursos_engine.py` + `tools/recursos_build.py` en este repo generan los 4 recursos actuales con ReportLab y son la base para nuevos recursos (portada, interiores, callouts, checklists, tablas, bloques numerados, matriz 2x2 y página CTA ya resueltos). Las Lora estáticas se instancian desde la variable con fontTools (`wght=600/700`).

## Estructura de un lead magnet que capta

```
1. GANCHO        → el problema concreto que resuelve, en una línea fuerte
2. VALOR USABLE  → contenido práctico que el lector puede aplicar HOY
                   (plantilla rellenable, checklist, framework, pasos)
3. ANCLAJE DE    → por qué fiarse: caso real anonimizado + cifra verificable
   AUTORIDAD       (7 agentes en producción, ~60% adopción, etc.)
4. PUENTE / CTA  → página final común: "No necesitas más IA. Necesitas la
                   decisión correcta." + 3 tarjetas (Diagnóstico 750 € + IVA
                   deducible íntegro · Implementación · Advisory) + reserva
```

El recurso tiene que valer por sí solo aunque el lector nunca convierta. Si no aporta valor real, no capta: quema la marca.

## Reglas de voz (heredadas del posicionamiento)

- Practitioner en primera persona. Casos reales, nunca inventados ni framing de observador de mercado.
- Sistemas agénticos, no automatizaciones (automatización solo como contraste).
- Taxonomía de cifras estricta: 7 agentes (cifra de producción precisa) vs. 25+ casos (volumen). Nunca inflar.
- Credibilidad anonimizada y conservadora: entorno regulado, sin nombrar al empleador, sin atribuir lo que no se pueda defender.
- Disclaimers obligatorios donde aplique (inversión → no es asesoramiento financiero; gobernanza → no es asesoramiento legal).
- Premium, directo, sin lenguaje defensivo.

## Generación y despliegue

- Formato de salida: **PDF nativo** vía `recursos_engine` (ReportLab), o **.docx rellenable** si el recurso es una plantilla que el usuario completa.
- Nombres de fichero = los que espera la web: `NN-slug.pdf` (p. ej. `01-diagnostico-madurez-ia.pdf`). Mantener el nombre exacto permite reemplazar sin tocar código.
- Despliegue: el binario va a `public/` del repo de la web por la web UI de GitHub o el file manager de Lovable — **nunca por API** (los binarios se corrompen). Después, `Lovable:deploy_project` esperando 2-3 min tras el último commit/subida.
- Verificación: descargar desde `/recursos` en producción y abrir el PDF antes de dar por cerrado.

> Nota Claude Code: la generación de PDF no es nativa aquí. Requiere `reportlab` + `fonttools` (instancia de Lora) antes de producir el binario. La estructura, tokens de marca y reglas de voz aplican igual.
