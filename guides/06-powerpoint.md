# 06 — Crea Presentaciones PowerPoint con Claude

## ¿Qué es?

Claude puede generar presentaciones PowerPoint (.pptx) profesionales desde cero o a partir de contenido que le proporciones. Produce archivos reales y descargables con slides formateados, layouts variados, paletas de colores coherentes, y estructura narrativa.

## ¿Cómo se activa?

1. Simplemente pide a Claude que cree una presentación o un "deck de slides".
2. Claude usa python-pptx para construir el archivo programáticamente.
3. El archivo .pptx resultante se ofrece para descarga directa.

## ¿Cómo funciona?

- Claude interpreta tu solicitud y diseña la estructura narrativa del deck.
- Escribe código Python que genera cada slide con su layout, contenido, formato y estilo.
- Aplica principios de diseño: consistencia tipográfica, uso de espacio, jerarquía visual.
- Ejecuta el código y genera el archivo .pptx descargable.
- Puedes pedir revisiones, cambios de estilo o adición de slides iterativamente.

## ¿Para qué se utiliza?

- Presentaciones de resultados de análisis o modelos de ML.
- Decks para propuestas técnicas o de proyecto.
- Presentaciones ejecutivas con resúmenes de datos.
- Material educativo o de capacitación.
- Convertir informes o documentos en formato presentación.

## Ventaja competitiva para Data Scientists / Devs IA

- **Del notebook al deck**: transforma tus hallazgos de análisis en una presentación lista para stakeholders sin tocar PowerPoint manualmente.
- **Narrativa automática**: Claude no solo coloca datos en slides, estructura una narrativa lógica (contexto → problema → análisis → hallazgos → recomendaciones).
- **Iteración rápida**: ajusta estilos, agrega slides o reformula contenido conversacionalmente.
- **Consistencia visual**: genera decks con paleta de colores, tipografía y layouts coherentes automáticamente.

## Ejemplo rápido

```
Prompt: "Crea una presentación de 10 slides sobre los resultados de mi modelo 
de predicción de churn. Incluye: slide de título, contexto del problema, 
descripción del dataset, metodología (Random Forest + XGBoost), métricas de 
rendimiento (accuracy 92%, precision 87%, recall 85%), feature importance 
(top 5 features), conclusiones y próximos pasos. Estilo corporativo, colores 
azul oscuro y blanco."
```

---

[← Excel + K-means](05-excel-kmeans.md) | [Siguiente: Artefactos →](07-artifacts.md)
