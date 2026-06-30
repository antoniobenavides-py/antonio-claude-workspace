---
name: look-and-feel
description: Aplica el sistema de marca de Benavides en cualquier entrega visual o de copy. Úsalo SIEMPRE que pida crear o revisar carruseles de LinkedIn, diseño web, PDFs/lead magnets, propuestas comerciales, emails, activos visuales, o cualquier decisión de color, tipografía o logo. La fuente de verdad es `docs/brand-system.md` en el workspace. Este skill condensa las reglas operativas para aplicar sin fricción.
---

# Look & Feel — Sistema de marca de Benavides

**Fuente de verdad:** `docs/brand-system.md` (workspace `antoniobenavides-py/antonio-claude-workspace`).
Ante cualquier duda o detalle no cubierto aquí, leer ese archivo. Este skill es el resumen operativo.

---

## Logo — reglas rápidas

| Superficie | Variante | Colores |
|---|---|---|
| LinkedIn, web dark, presentaciones | Dark | Fondo Cyprus `#004741` · símbolo Sand `#F0EDE4` |
| Documentos, propuestas, emails, fondos claros | Light | Fondo Sand `#F0EDE4` · símbolo Cyprus `#004741` |
| Carruseles LinkedIn | Light, opacidad reducida | Esquina inferior derecha |
| Favicon web | Dark, solo símbolo | Sin wordmark |

Símbolo = monograma AB serif en círculo con barras laterales. **No alterar geometría, colores ni proporciones.**

---

## Paleta — tokens por proyecto

```css
/* antoniobenavides.com */
--brand:  #004741;  /* Cyprus */
--bg:     #F0EDE4;  /* Sand */
--ink:    #171717;

/* vibecodinges.com */
--brand:        #21F1A8;  /* Tiffany */
--bg-dark:      #171717;
--bg-light:     #FFFDF1;  /* Milky */
--accent-light: #59C749;  /* Mantis */

/* vibesplab.com */
--brand: #2BEE34;  /* Luminous Moss */
--bg:    #141414;  /* Silver */
```

**Paleta desplegada en antoniobenavides.com (hasta rediseño — no tocar):**
```css
--copper-start: #E0A05E;
--copper-end:   #C8824E;
--teal:         #14B8A6;
--ink:          #0F1620;
```
Rediseño Cyprus/Sand: **después del primer cierre comercial, no antes.**

---

## Tipografía

| Superficie | Titular | Cuerpo | Mono |
|---|---|---|---|
| Web (antoniobenavides.com) | Space Grotesk | Inter | JetBrains Mono |
| Carruseles LinkedIn | Playfair Display Bold · Cormorant Garamond Bold | DM Sans Regular · Inter Light | — |
| PDFs / recursos | Playfair Display o similar con autoridad | DM Sans o Inter | — |

Tracking amplio (+2/+3) en subtítulos y wordmark.

---

## Tratamiento por superficie

| Superficie | Fondo | Lógica |
|---|---|---|
| Web | Oscuro (INK / Cyprus en rediseño) | "Clinical-nocturnal" |
| PDF / recursos / propuestas | Claro (Sand o blanco) | Legibilidad, impresión, premium |
| Carruseles LinkedIn | Alternando Cyprus dark ↔ Sand light | Ritmo visual slide a slide |
| Emails | Claro, cabecera light | Legibilidad en cliente de correo |

---

## Carruseles LinkedIn — protocolo operativo

**Specs:** PDF o secuencia imágenes · 1080×1080 px · cadencia lunes 9:00.

**División de trabajo:**
- Claude: estrategia, copy slide a slide, brief visual (JSON en `scripts/carruseles/`)
- Producción visual: herramienta externa (ChatGPT Image, Gamma, Canva AI, Gemini)

**Estructura de slides:**
```
PORTADA     → fondo Cyprus · título grande Sand · wordmark AB (esquina, opacidad reducida)
SLIDES 2–N  → alternando Cyprus/Sand · máx 4-5 líneas · una idea por slide
              con sección: label uppercase + línea divisoria + cuerpo
CIERRE      → fondo Cyprus · pregunta o reflexión · "Antonio Benavides" + URL si aplica
```

**Brief base para producción visual:**
Combo Cyprus `#004741` / Sand `#F0EDE4` · Playfair Display Bold (titular) · DM Sans Regular (cuerpo) · tracking amplio · marca de agua AB light esquina inferior derecha.

---

## Nomenclatura de marca

Doble barra para entidades propias: `ARCHIVO//MAESTRO`, `VIBECODING//ES`, `TRIAJE//IA`.

---

## Voz y tono

Practitioner en primera persona · autoridad por casos reales · premium y directo · cifras sin inflar.
Ver skill `post-linkedin` para reglas completas de copy.

**Taxonomía estricta:**
- 7 agentes en producción (cifra precisa, no superar)
- 25+ casos totales (volumen amplio)
- ~60% adopción orgánica

---

## Checklist antes de entregar

- [ ] Colores dentro de la paleta del proyecto correcto
- [ ] Tipografías correctas por jerarquía y superficie
- [ ] Nomenclatura doble-barra donde aplica
- [ ] Tratamiento correcto: oscuro en web / claro en PDF
- [ ] Logo en variante correcta (dark o light) sin distorsión
- [ ] Voz practitioner, cifras sin inflar
- [ ] Para carruseles: JSON en `scripts/carruseles/` + brief visual listo para herramienta externa
