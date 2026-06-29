---
name: arquitectura-agentes
description: Diseña y revisa sistemas agénticos con la filosofía de Benavides — agentes que enrutan a un objetivo con loop auto-verificable, no automatizaciones deterministas. Úsalo SIEMPRE que diseñe, audite o proponga un agente, copiloto o sistema inteligente, ya sea para un cliente o para sus propios productos (el agente de diagnóstico comercial de la web, copilotos internos). Codifica el patrón de loop auto-mejorante con verificador objetivo, el chequeo de Goodhart, la distinción agente vs automatización, el criterio de dónde usar determinismo, y la honestidad sobre el estado real de despliegue. Consúltalo antes de proponer cualquier arquitectura de agente.
---

# Arquitectura de agentes

La especialidad de Benavides son **sistemas agénticos**: agentes que enrutan hacia un objetivo, no cadenas deterministas rígidas. Es también el núcleo de su producto (el agente de diagnóstico comercial). Este skill aplica su filosofía al diseño y la auditoría.

## Principio rector: agente vs automatización

- **Agente**: tiene un objetivo, decide cómo alcanzarlo, y se corrige contra un criterio. El determinismo es una **herramienta bajo su control**, no el esqueleto.
- **Automatización**: cadena fija de pasos deterministas sin criterio ni corrección. Es lo que Benavides NO construye; aparece solo como contraste.

Si lo que estás diseñando no toma decisiones ni se verifica, no es un agente: replantéalo o nómbralo por lo que es.

## El loop auto-verificable

El patrón de mayor valor: cerrar el feedback loop con **criterios de salida verificables**.

```
1. OBJETIVO    → qué tiene que conseguir el agente, en términos medibles
2. VERIFICADOR → criterio objetivo que dice si la salida cumple (diséñalo PRIMERO)
3. EJECUCIÓN   → el agente produce una salida
4. VERIFICACIÓN→ la salida se contrasta contra el verificador
5. ITERACIÓN   → si no cumple, el agente corrige y reintenta; si cumple, cierra
```

**Diseña el verificador antes que el agente.** Un loop sin verificador objetivo no se auto-mejora: solo repite. La pregunta de diseño no es "¿qué hace el agente?" sino "¿cómo sabremos, de forma objetiva, que lo hizo bien?".

## Chequeo de Goodhart (obligatorio)

Cuando una métrica se convierte en objetivo, deja de ser buena métrica. El agente optimizará exactamente lo que mides, incluido el proxy gameable.

- ¿El verificador se puede cumplir sin lograr el objetivo real? Si sí, es gameable → rediséñalo.
- Prefiere verificadores estructurales (¿la salida tiene la forma/propiedad correcta?) y de resultado (¿produjo el efecto buscado?) sobre proxies blandos (longitud, presencia de palabras clave).
- Caso de referencia: el agente de diagnóstico comercial con loop de verificación estructural — el verificador comprueba que el diagnóstico cumple la estructura y cubre los puntos exigidos, no que "suene bien".

## Criterio de despliegue del determinismo

Usa pasos deterministas SOLO donde aporten fiabilidad bajo control del agente: validaciones, llamadas a herramientas con contrato fijo, formateo de salida. El agente decide *cuándo* invocarlos; ellos no deciden por él. Nunca conviertas el sistema en una tubería rígida disfrazada de agente.

## Honestidad sobre el estado real

Distingue siempre, sin excepción:
- **En producción con usuarios reales** (p. ej., los 7 agentes de microbiología).
- **Configurado pero no desplegado con usuarios reales** (p. ej., el agente de onboarding). Esto NO cuenta como producción y se dice tal cual.

Marcar como "en producción" algo que solo está configurado destruye credibilidad en una auditoría o una venta. Conservador siempre.

## Stack

Real: OpenAI, Claude, Gemini, open-source, workflows de ChatGPT business. Copilot Studio = keyword ATS/empresarial, no la herramienta preferida. Elige el modelo por tarea, sin exclusividad de proveedor.

## Checklist de revisión de arquitectura

Ante cualquier diseño de agente, verifica:

1. ¿Hay un objetivo medible, o es una tarea difusa?
2. ¿Existe un verificador objetivo y está definido antes que la ejecución?
3. ¿El verificador es gameable? (chequeo de Goodhart)
4. ¿El loop cierra de verdad — la salida se contrasta y se itera — o solo ejecuta una vez?
5. ¿El determinismo está bajo control del agente o es el esqueleto rígido?
6. ¿Es un agente real o una automatización mal nombrada?
7. ¿El estado de despliegue se reporta con honestidad (producción vs configurado)?
