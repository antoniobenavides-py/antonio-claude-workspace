---
name: traspaso-sesion
description: Genera un documento de TRASPASO para continuar un trabajo en un chat nuevo sin pérdida de contexto. Úsalo cuando Benavides pida un "traspaso", un documento de continuación, "seguimos en otro chat", cuando una sesión larga se acerque al límite de tokens, o al cerrar una sesión de ejecución para retomarla después. Codifica su protocolo de sesiones largas (fases numeradas con checkpoints, compresión de contexto, Opus para arquitectura y Sonnet para ejecución) y la plantilla exacta del traspaso, incluido el prompt de continuación listo para pegar.
---

# Traspaso de sesión

Cuando una sesión larga se acerca al límite de tokens o se cierra una fase de ejecución, produce un documento autocontenido que permita a un chat nuevo retomar con cero pérdida de contexto. El traspaso es el activo que evita reexplicar infraestructura, decisiones y trampas en cada migración.

## Protocolo de sesiones largas

- **Fases numeradas con checkpoints**: marca cada hito con `✅ FASE N COMPLETADA`. Una fase por turno cuando la tarea sea de ejecución, con commit quirúrgico.
- **Compresión de contexto**: resúmenes de máximo ~300 palabras por checkpoint. No arrastres historial innecesario.
- **Modelo por tarea**: Opus para arquitectura y decisiones críticas; Sonnet para ejecución mecánica.
- **Disparador de traspaso**: cuando el contexto se hincha, la sesión se alarga, o se completa un bloque de trabajo que continuará después.

## Plantilla exacta del traspaso

Usa SIEMPRE esta estructura. Versiona el documento (TRASPASO v1, v2, v3…).

```
# TRASPASO v[N] — [proyecto / sprint]

## 1. Estado actual
- Qué se ha completado (con ✅ FASE N COMPLETADA por hito)
- Qué está verificado vs. desplegado-pero-sin-verificar

## 2. Infraestructura y datos clave
- Refs de proyecto, tablas, endpoints, secretos relevantes
- Identificadores concretos que el chat nuevo necesitará (no genéricos)

## 3. Decisiones arquitectónicas
- Decisiones tomadas y por qué
- Alternativas descartadas y motivo

## 4. Trampas conocidas (gotchas)
- Comportamientos no obvios de tools, fallos silenciosos, secuencias frágiles
- Lo que ya falló y cómo se evita

## 5. Tarea siguiente
- Brief concreto y acotado para la próxima sesión
- Prioridad nº1 antes de cualquier otra cosa

## 6. Prompt de continuación
[Mensaje de apertura listo para pegar en el chat nuevo, que cargue
contexto y dé la primera instrucción acotada]
```

## Reglas del traspaso

- **Identificadores concretos, no genéricos.** "Project B, ref `saxagolemwmfroxelscd`, tabla `resource_subscribers`" — no "la base de datos del flujo de recursos".
- **Sé explícito sobre verificación.** Distingue lo que está probado end-to-end de lo que solo está desplegado. Marcar algo como hecho sin verificar reproduce bugs.
- **El prompt de continuación es lo más importante.** Debe permitir abrir un chat nuevo y arrancar sin que Benavides reexplique nada. Inclúyelo siempre, listo para copiar.
- **Convención de nombres**: doble barra para entidades de marca cuando aplique (ANTONIO//BENAVIDES, VIBECODING//ES).

## Formato de entrega

Entrega el traspaso como **un único bloque copiable** (para pegar directamente en el chat nuevo) o como fichero `.md` si lo pide. La sección 6 (prompt de continuación) puede entregarse además como bloque propio para copiar por separado.
