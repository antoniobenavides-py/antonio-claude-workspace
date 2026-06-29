---
name: lead-magnet-pdf
description: Crea lead magnets en PDF alineados con el brand system de Benavides para captación vía /recursos (Track B). Úsalo SIEMPRE que pida un recurso descargable, un lead magnet, una guía, un PDF de captación, una plantilla descargable o material para /recursos. Codifica los tokens de marca (paleta INK/cobre/teal, tipografías, convención doble-barra), la estructura de un lead magnet que capta (gancho, valor usable, anclaje de autoridad, puente a diagnóstico), el tratamiento print-friendly y las reglas de voz. Genera el PDF con el skill de documentos correspondiente.
---

# Lead magnet PDF

Los lead magnets alimentan el Track B (captación vía `/recursos`). Deben ser premium, inmediatamente útiles y coherentes con la marca. Un recurso descargable es un activo de captación, no un folleto: entrega valor real y construye el puente hacia el diagnóstico.

## Tokens de marca

| Elemento | Valor |
|---|---|
| INK (navy profundo) | `#0F1620` |
| Cobre (gradiente) | `#E0A05E → #C8824E` |
| Teal (acento) | `#14B8A6` |
| Tipografías | Space Grotesk (titulares) · Inter (texto) · JetBrains Mono (código/datos) |
| Nomenclatura | doble barra para entidades de marca (ARCHIVO//MAESTRO, VIBECODING//ES, TRIAJE//IA) |

**Tratamiento print-friendly:** la web es oscura (clinical-nocturnal), pero el PDF descargable va sobre **fondo claro** para lectura e impresión, usando INK para texto, cobre para acentos/titulares y teal para destacados puntuales. Premium y limpio, no recargado.

## Estructura de un lead magnet que capta

```
1. GANCHO        → el problema concreto que resuelve, en una línea fuerte
2. VALOR USABLE  → contenido práctico que el lector puede aplicar HOY
                   (plantilla rellenable, checklist, framework, pasos)
3. ANCLAJE DE    → por qué fiarse: caso real anonimizado + cifra verificable
   AUTORIDAD       (7 agentes en producción, ~60% adopción, etc.)
4. PUENTE / CTA  → siguiente paso hacia el diagnóstico
                   ("20 minutos bastan para ver qué casos aplican a tu empresa")
```

El recurso tiene que valer por sí solo aunque el lector nunca convierta. Si no aporta valor real, no capta: quema la marca.

## Reglas de voz (heredadas del posicionamiento)

- Practitioner en primera persona. Casos reales, nunca inventados ni framing de observador de mercado.
- Sistemas agénticos, no automatizaciones (automatización solo como contraste).
- Taxonomía de cifras estricta: 7 agentes (cifra de producción precisa) vs. 25+ casos (volumen). Nunca inflar.
- Credibilidad anonimizada y conservadora: entorno regulado ISO 17025, sin nombrar al empleador, sin atribuir lo que no se pueda defender.
- Premium, directo, sin lenguaje defensivo.

## Generación

- Formato de salida: **PDF** vía el skill de PDF, o **.docx rellenable** si el recurso es una plantilla que el usuario completa (modelo ARCHIVO//MAESTRO: documento Word rellenable para configurar un copiloto de IA).
- Nombra el fichero con la convención de marca cuando aplique.
- Despliegue: el binario va a `/recursos` por la web UI de GitHub o el file manager de Lovable — **nunca por API** (los binarios se corrompen). Ver el skill de deploy.

> Nota Claude Code: la generación de PDF/.docx no es nativa aquí. Requiere instalar una herramienta (p. ej. `pandoc`, `weasyprint` o `python-docx`) antes de producir el binario. La estructura, tokens de marca y reglas de voz aplican igual.
