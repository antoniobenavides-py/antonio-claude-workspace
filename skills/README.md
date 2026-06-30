# Skills

Skills de trabajo de Benavides, portadas desde Claude.ai. Cada una vive en `<nombre>/SKILL.md` con frontmatter `name` + `description`. Funcionan tanto en Claude.ai (formato `.skill`) como en Claude Code (instaladas en `.claude/skills/`).

| Skill | Para qué | Dependencias |
|-------|----------|--------------|
| [deploy-produccion](deploy-produccion/SKILL.md) | Runbook del stack web (Lovable/Supabase/GitHub/Vercel). Trampas y checklist de verificación. | — |
| [arquitectura-agentes](arquitectura-agentes/SKILL.md) | Diseño/auditoría de sistemas agénticos con loop auto-verificable. | — |
| [post-linkedin](post-linkedin/SKILL.md) | Posts de LinkedIn en la voz de Benavides, casos reales, links en primer comentario. | — |
| [propuesta-comercial](propuesta-comercial/SKILL.md) | Conversación comercial → propuesta cerrable. Pricing y framing ROI. | docs para entrega formal |
| [log-construccion](log-construccion/SKILL.md) | Parte de avance formato Opción B (Estado · triada · siguiente fase). | — |
| [traspaso-sesion](traspaso-sesion/SKILL.md) | Documento de traspaso para continuar en sesión nueva sin pérdida de contexto. | — |
| [cv-portfolio](cv-portfolio/SKILL.md) | CVs/portfolios ATS-safe, dos variantes (IA generalista · finanzas+IA). | generación .docx |
| [lead-magnet-pdf](lead-magnet-pdf/SKILL.md) | Lead magnets PDF con brand system para `/recursos`. | generación PDF/.docx |
| [look-and-feel](look-and-feel/SKILL.md) | Sistema de marca: logo, paleta, tipografía, carruseles y checklist por superficie. Fuente de verdad: `docs/brand-system.md`. | — |

## Nota sobre dependencias

`cv-portfolio` y `lead-magnet-pdf` (y la entrega formal de `propuesta-comercial`) invocan generación de documentos `.docx`/PDF. En Claude.ai es nativo; en **Claude Code requiere instalar una herramienta** (`python-docx`, `pandoc`, `weasyprint`). El contenido y las reglas aplican igual; solo la generación del binario necesita el setup.
