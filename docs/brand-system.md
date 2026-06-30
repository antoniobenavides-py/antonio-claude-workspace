# SISTEMA DE MARCA — Antonio Benavides

**Fuente ÚNICA de marca** para web (antoniobenavides.com), LinkedIn y recursos `/recursos`.
Estado: **v1.1 · 30-jun-2026** — logo corregido con descripción real, paleta y formatos de carrusel consolidados.

---

## 1. Logo y marca corporativa

### Símbolo y wordmark

**Símbolo:** Monograma AB geométrico moderno. Las letras A y B se entrelazan compartiendo un eje vertical central. La A adopta una forma triangular angular con vértice superior y corte interior diagonal. La B usa aristas cortadas en ángulo (sin curvas), integrándose con la A en una sola forma compacta. Diseño bold, sin serif, sin círculo, sin barras laterales.

**Wordmark:** "Antonio Benavides" en sans-serif ligero, tracking amplio, con guión corto centrado debajo.

**Variante principal (primaria): DARK** — fondo Cyprus, símbolo y wordmark en Sand. Es la variante de referencia.

### Variantes de color

| Variante | Fondo | Símbolo / texto | Uso principal |
|---|---|---|---|
| **Principal (dark)** ⭐ | Cyprus `#004741` | Sand `#F0EDE4` | Perfil LinkedIn, web, presentaciones dark, uso general |
| **Secundaria (light)** | Sand `#F0EDE4` | Cyprus `#004741` | Documentos, propuestas, emails, fondos claros |

### Archivos fuente

- **PNG (fuente de verdad):** `assets/logo/logo-ab.png` en este repo ⚠️ *pendiente de subida manual — arrastrar desde local `look and feel/ChatGPT Image 29 jun 2026, 18_17_29.png`*
- **SVG:** pendiente para el rediseño web. La geometría es limpia y reproducible.

### Aplicaciones

| Superficie | Variante | Notas |
|---|---|---|
| Foto de perfil LinkedIn | Dark (Cyprus) | Recortada cuadrada |
| Favicon web | Dark, solo símbolo | Sin wordmark |
| Documentos / propuestas | Light o dark según fondo | |
| Marca de agua en carruseles | Light, opacidad reducida | Esquina inferior derecha |
| Cabecera de emails | Light sobre fondo claro | |

### Usos incorrectos

- No cambiar los colores fuera del sistema Cyprus / Sand.
- No añadir círculo, barras, marcos ni ornamentos al símbolo.
- No usar versión serif ni redondear las aristas angulares del monograma.
- No distorsionar proporciones.
- No añadir sombras, brillos ni efectos.

---

## 2. Paleta de color

### Sistema multi-proyecto (decidido 29-jun-2026)

Hilo verde estratégico en tres saturaciones = ecosistema reconocible. Catálogo completo de 10 combos en `docs/paletas-combos-colores.md`.

| Proyecto | Token | Hex | Rol |
|---|---|---|---|
| **antoniobenavides.com** | Cyprus | `#004741` | Base / profundo · fondo principal dark |
| | Sand | `#F0EDE4` | Neutro cálido · fondo light y texto sobre dark |
| **vibecodinges.com** | Tiffany | `#21F1A8` | Principal / luminoso · CTAs y acentos |
| | Dark Gray | `#171717` | Base dark |
| | Milky | `#FFFDF1` | Fondo light (zona recursos / educación) |
| | Mantis | `#59C749` | Acento en modo claro |
| **vibesplab.com** | Luminous Moss | `#2BEE34` | Principal / neón · lab y experimentación |
| | Silver | `#141414` | Base near-black |

```css
/* antoniobenavides.com */
:root {
  --brand:  #004741;  /* Cyprus */
  --bg:     #F0EDE4;  /* Sand */
  --ink:    #171717;
}

/* vibecodinges.com */
:root {
  --brand:        #21F1A8;  /* Tiffany */
  --bg-dark:      #171717;
  --bg-light:     #FFFDF1;  /* Milky */
  --accent-light: #59C749;  /* Mantis */
}

/* vibesplab.com */
:root {
  --brand: #2BEE34;  /* Luminous Moss */
  --bg:    #141414;  /* Silver */
}
```

### Estado actual de antoniobenavides.com (en transición)

La web desplegada usa la paleta anterior hasta el rediseño. **No tocar antes del primer cierre comercial.**

```css
/* Paleta desplegada — mantener hasta rediseño Cyprus/Sand */
--ink:          #0F1620;
--copper-start: #E0A05E;
--copper-end:   #C8824E;
--teal:         #14B8A6;
```

Los P0 de botones ya usan `btn-copper` (`#E0A05E → #C8824E`) — se mantienen hasta el rediseño.

---

## 3. Tipografía

### Web (antoniobenavides.com — estado actual)

- **Space Grotesk** — titulares, headings
- **Inter** — texto corrido, body
- **JetBrains Mono** — código, datos, fragmentos monospace

### Carruseles LinkedIn (producción en herramientas externas)

- **Titular:** Playfair Display Bold o Cormorant Garamond Bold — peso y autoridad
- **Cuerpo:** DM Sans Regular o Inter Light — legible, clean
- **Tracking:** amplio (+2/+3) en subtítulos y wordmark

---

## 4. Nomenclatura de marca

Doble barra para entidades de marca: `ARCHIVO//MAESTRO`, `VIBECODING//ES`, `TRIAJE//IA`.

---

## 5. Tratamiento por superficie

- **Web:** oscura, "clinical-nocturnal". Fondo INK actual → Cyprus `#004741` en rediseño.
- **PDF / recursos:** fondo **claro** para lectura e impresión. Premium y limpio.
- **LinkedIn (carruseles):** ver sección 6.

---

## 6. Formatos de carrusel LinkedIn

### Especificaciones técnicas

- **Formato de entrega:** PDF (carrusel nativo LinkedIn) o secuencia de imágenes
- **Dimensiones:** 1080 × 1080 px (cuadrado 1:1)
- **Cadencia:** todos los lunes, 9:00 — mínimo 4 carruseles/mes

### División de trabajo

| Qué | Quién / Dónde |
|---|---|
| Estrategia, calendario, copy slide a slide, brief visual | Claude (en workspace) |
| Producción visual | Herramienta externa: ChatGPT Image, Gamma, Canva AI o Gemini |

Los scripts de contenido (copy por slide) se guardan en `scripts/carruseles/*.json` del workspace.

### Paleta aplicada al carrusel

Alineada con la dirección de marca Cyprus + Sand:

| Elemento | Valor |
|---|---|
| Fondo dark | Cyprus `#004741` |
| Texto sobre dark | Sand `#F0EDE4` |
| Fondo light (slides de respiro) | Sand `#F0EDE4` |
| Texto sobre light | Cyprus `#004741` |

Slides alternando dark / light para ritmo visual.

### Estructura de slides

```
PORTADA     → fondo Cyprus · título grande en Sand · wordmark AB pequeño (esquina, opacidad reducida)
SLIDES 2–N  → alternando Cyprus/Sand · máx. 4-5 líneas · una idea por slide
              slides con sección: label en uppercase + línea divisoria + cuerpo
CIERRE      → fondo Cyprus · pregunta o reflexión · "Antonio Benavides" + URL si procede
```

### Brief visual para herramienta externa

⚠️ **Pendiente de finalizar:** Benavides aportará ejemplos de carruseles anteriores (ChatGPT, Gamma, Canva) para analizar el estilo y consolidar el brief estandarizado de producción.
Hasta entonces: Combo 04 Cyprus/Sand + Playfair Display Bold (titular) + DM Sans (cuerpo).

### Carruseles julio 2026 — copy listo para producir

| Fecha | Tema | Archivo JSON (workspace) |
|---|---|---|
| lun 6 jul | Agente vs automatización | `scripts/carruseles/2026-07-06-agente-vs-automatizacion.json` |
| lun 13 jul | 5 filtros para decidir en qué IA invertir | `scripts/carruseles/2026-07-13-cinco-filtros-roi.json` |
| lun 20 jul | Las 6 dimensiones de madurez en IA | `scripts/carruseles/2026-07-20-seis-dimensiones-madurez.json` |
| lun 27 jul | Anatomía de un despliegue real | `scripts/carruseles/2026-07-27-anatomia-despliegue.json` |

---

## 7. Voz y tono (resumen)

Practitioner en primera persona · autoridad por casos reales verificables · premium y directo · taxonomía de cifras estricta (7 agentes en producción / 25+ casos) · sin clichés de IA · sin framing de observador de mercado.
Detalle completo en las skills `post-linkedin` y `lead-magnet-pdf`.

---

## 8. Checklist de coherencia

- [ ] ¿Colores dentro de la paleta del proyecto?
- [ ] ¿Tipografías correctas por jerarquía y superficie?
- [ ] ¿Nomenclatura doble-barra donde aplica?
- [ ] ¿Tratamiento correcto según superficie (oscuro web / claro PDF)?
- [ ] ¿Logo en variante correcta (dark o light) con área de respeto?
- [ ] ¿Voz practitioner, cifras sin inflar?
- [ ] ¿Logo PNG disponible en `assets/logo/logo-ab.png`?
