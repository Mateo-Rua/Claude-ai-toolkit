# 04 — Búsqueda Web en Claude

## ¿Qué es?

La búsqueda web permite a Claude acceder a información actualizada de internet en tiempo real durante una conversación. Claude consulta múltiples fuentes, sintetiza resultados y responde con datos vigentes, citando las fuentes originales.

## ¿Cómo se activa?

1. En la interfaz de Claude.ai, busca el ícono de búsqueda web (globo terráqueo) en la barra de herramientas del chat.
2. Actívalo antes de enviar tu mensaje, o simplemente formula preguntas que requieran datos actuales — Claude puede decidir buscar automáticamente.
3. Vía API, se habilita pasando la herramienta `web_search_20250305` en el parámetro `tools`.

## ¿Cómo funciona?

- Claude analiza tu pregunta y determina si necesita datos actualizados.
- Ejecuta una o más búsquedas en la web con queries optimizados.
- Lee y sintetiza los resultados más relevantes.
- Responde con información citada, indicando las fuentes.

## ¿Para qué se utiliza?

- Consultar noticias recientes, precios, estadísticas actuales.
- Verificar información que pudo haber cambiado desde el entrenamiento del modelo.
- Investigar sobre productos, empresas o eventos recientes.
- Comparar opciones actuales de herramientas, frameworks o servicios.

## Ventaja competitiva para Data Scientists / Devs IA

- **Análisis de mercado actualizado**: puedes pedir benchmarks recientes de modelos, comparativas de frameworks o tendencias de la industria sin salir de Claude.
- **Investigación bibliográfica rápida**: buscar papers recientes, datasets nuevos o cambios en APIs de terceros.
- **Monitoreo de ecosistema**: mantenerte al día con actualizaciones de librerías (PyTorch, TensorFlow, LangChain) directamente en tu flujo de trabajo.

## Ejemplo rápido

```
Prompt: "¿Cuáles son los benchmarks más recientes de Claude Opus 4 vs GPT-4o 
en tareas de código y razonamiento matemático?"
```

Claude buscará comparativas actualizadas, citará fuentes como papers de benchmarks o artículos técnicos, y te dará un resumen estructurado.

---

[← Volver al índice](../README.md) | [Siguiente: Pensamiento Extendido →](02-extended-thinking.md)
