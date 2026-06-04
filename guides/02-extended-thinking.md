# 05 — Pensamiento Extendido de Claude

## ¿Qué es?

El pensamiento extendido (Extended Thinking) es una capacidad que permite a Claude "pensar en voz alta" internamente antes de responder. Claude descompone problemas complejos en pasos lógicos, evalúa múltiples enfoques y construye una respuesta más precisa y fundamentada.

## ¿Cómo se activa?

1. En Claude.ai, el pensamiento extendido se activa automáticamente en modelos avanzados cuando la complejidad de la pregunta lo requiere.
2. Vía API, se habilita con el parámetro `thinking` en la configuración del modelo, especificando un budget de tokens para el razonamiento interno.

## ¿Cómo funciona?

- Claude recibe tu pregunta y antes de generar la respuesta visible, genera un bloque de "pensamiento" interno.
- En este bloque, desglosa el problema, considera alternativas, identifica errores potenciales y estructura su razonamiento.
- La respuesta final refleja este proceso, siendo más precisa y menos propensa a errores.
- Puedes ver el proceso de pensamiento desplegando el bloque "Thinking" en la interfaz.

## ¿Para qué se utiliza?

- Problemas matemáticos o de lógica complejos.
- Depuración de código con múltiples posibles causas.
- Análisis que requieren considerar múltiples variables simultáneamente.
- Planificación estratégica o diseño de arquitecturas de software.
- Tareas donde un error de razonamiento tiene alto costo.

## Ventaja competitiva para Data Scientists / Devs IA

- **Depuración avanzada**: Claude razona paso a paso sobre tu pipeline de ML, identificando dónde puede estar el bug en lugar de dar una respuesta genérica.
- **Diseño de experimentos**: al pensar explícitamente, Claude puede evaluar pros y contras de diferentes configuraciones de hiperparámetros o arquitecturas de modelos.
- **Reducción de alucinaciones**: el razonamiento interno actúa como auto-verificación, reduciendo respuestas incorrectas en tareas técnicas.
- **Resolución de edge cases**: en problemas con múltiples condiciones (queries SQL complejos, transformaciones de datos), el pensamiento extendido evita omitir casos borde.

## Ejemplo rápido

```
Prompt: "Tengo un modelo de clasificación con 95% de accuracy pero 30% de recall 
en la clase minoritaria. El dataset tiene un desbalance de 95/5. ¿Qué estrategias 
debería considerar y en qué orden implementarlas?"
```

Claude pensará internamente sobre: métricas apropiadas para datos desbalanceados, técnicas de resampling (SMOTE, undersampling), ajuste de umbrales, cost-sensitive learning, y te dará un plan priorizado con trade-offs claros.

---

[← Búsqueda Web](01-web-search.md) | [Siguiente: Deep Research →](03-deep-research.md)
