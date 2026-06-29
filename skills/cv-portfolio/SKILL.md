---
name: cv-portfolio
description: Genera CVs y portfolios ATS-safe en el formato exacto de Benavides para el Track 1 (búsqueda de rol). Úsalo SIEMPRE que pida un CV, currículum, portfolio, o adaptar su perfil a una candidatura. Codifica las reglas ATS (una columna, sin tablas ni gráficos, enlaces en texto plano), las dos variantes (consultoría IA generalista y finanzas+IA), las reglas de titular y posicionamiento, la taxonomía de cifras 7/25+, el encuadre del trabajo fundador como desarrollo de producto, y el criterio conservador de credibilidad. Genera el documento con el skill de .docx.
---

# CV y portfolio

CVs de una página, optimizados para ATS, para el Track 1 (búsqueda de rol estratégico). El objetivo es pasar el filtro automático sin sacrificar posicionamiento premium. Conservador en lo que se afirma: nada que Benavides no pueda defender en una entrevista.

## Reglas ATS (no negociables)

- **Una sola columna.** Sin tablas, sin cajas, sin multicolumna: los parsers ATS las leen mal.
- **Sin gráficos, iconos ni imágenes.** Texto seleccionable siempre.
- **Enlaces en texto plano** (el portfolio va como URL legible, no como hipervínculo incrustado que el ATS pueda perder).
- **Encabezados estándar**: Experiencia, Formación, Habilidades, Proyectos. Nada creativo que el parser no reconozca.
- **Una página.** Densidad alta, cero relleno.
- **Keywords** del puesto integradas en Habilidades y en los bullets.

## Dos variantes

1. **Consultoría IA generalista** — perfil de arquitecto/consultor de IA aplicada a negocio.
2. **Finanzas + IA** — misma base, **añade una sección de proyectos de análisis de inversión** y orienta keywords al nicho financiero.

Elige variante según la candidatura; si no está claro, pregunta cuál.

## Titular y posicionamiento

- Titular: arquitecto/consultor de IA aplicada a negocio con mentalidad de inversor. **"Automatización empresarial" NO va en el titular** — se degrada a keyword en Habilidades.
- **El trabajo fundador se enmarca como desarrollo de producto**, no como consultora competidora (no levantar banderas de conflicto ante un empleador potencial).
- **Copilot Studio** se mantiene como keyword ATS aunque no sea su herramienta preferida.
- NUNCA posicionar como: automatizador genérico, experto en Make/Zapier, técnico de prompts, low-cost, gurú de IA, desarrollador puro.

## Criterio de aceptación de rol (para orientar la candidatura)

- Salario mínimo 35K si la oferta interesa mucho (crecimiento, contactos, autoridad). Sin ese interés, 40-45K.
- Siempre negociar revisión de sueldo obligatoria.
- Tipo empresa: consultoras de IA, empresas integrando/escalando IA, proyectos con necesidad de perfil avanzado.
- Modalidad: 100% remoto innegociable. Híbrido/presencial solo si es en Almería.

## Taxonomía de cifras (estricta)

- **7 agentes en producción** — cifra precisa, nunca inflar.
- **25+ casos** — métrica de volumen (agentes + copilotos + flujos).
No mezclar ni conflar las dos. Diferenciador de credibilidad: entorno regulado ISO 17025.

## Credibilidad conservadora

No atribuir títulos, certificaciones ni experiencia que Benavides no pueda sostener cara a cara en una entrevista. Ante la duda, fuera. Un CV que promete lo que no se defiende se cae en la primera ronda.

## Generación

Genera el `.docx` con el skill de documentos, respetando estrictamente las reglas ATS de arriba (el skill de docx tiende a formatos ricos; aquí prima la legibilidad del parser sobre la estética). Una página, una columna, enlaces en texto plano.

> Nota Claude Code: la generación de `.docx` no es nativa aquí. Requiere instalar una herramienta (p. ej. `python-docx` o `pandoc`) antes de producir el fichero. El contenido y las reglas ATS aplican igual.
