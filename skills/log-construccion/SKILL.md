---
name: log-construccion
description: Reporta avances de construcción y actualizaciones de web en el formato Opción B de Benavides. Úsalo cuando cierre una fase de build, una actualización de web, un hito de un proyecto, o pida un parte de avance o un resumen de estado de construcción. Codifica el esqueleto exacto (declaración de estado, triada Ejecución·Gobernanza·ROI, siguiente fase) y el registro corto, confiado y orientado a estado. No es para documentos largos ni propuestas; es para partes de progreso compactos.
---

# Log de construcción — formato Opción B

Parte de avance compacto, confiado y orientado a estado. No narra el proceso: declara dónde está el sistema y qué viene después. Úsalo para cerrar fases de build y actualizaciones de web, no para informes largos.

## Esqueleto exacto

```
[ESTADO]
Una declaración corta del estado actual. Estados progresivos típicos:
· Marco listo.
· Estructura lista.
· Sistema en marcha.

[TRIADA]
Ejecución · [qué se construyó / qué corre ya]
Gobernanza · [cómo se controla, mantiene o asegura]
ROI · [retorno o impacto, en términos concretos]

[SIGUIENTE FASE]
La próxima acción acotada. Una, no varias.
```

## Reglas

- **Declarativo, no narrativo.** "Sistema en marcha", no "he estado trabajando en montar el sistema y casi está".
- **La triada es el núcleo.** Cada eje en una línea, concreto. Si un eje no aplica en esta fase, dilo en una línea ("ROI · se mide en la siguiente fase") en vez de inventarlo.
- **Una sola siguiente fase.** Cierra el parte apuntando al siguiente hito, no a un abanico de opciones.
- **Corto y confiado.** Sin relleno, sin disculpas, sin lenguaje defensivo. El formato transmite control.
- **Entrega copiable** si va a salir del chat (parte para registro, actualización para terceros).

## Ejemplo

```
Estructura lista.

Ejecución · Flujo /recursos desplegado en Project B, descarga de PDF y alta de lead funcionando end-to-end.
Gobernanza · Verificado con test real: lead en tabla + email entregado + PDF accesible.
ROI · Track B desbloqueado para captación; cada descarga es un lead cualificado.

Siguiente fase · confirmar fecha del último post de Serie A para programar el arranque sin solape.
```
