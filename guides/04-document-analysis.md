# 04 — Análisis de Documentos e Imágenes con Claude

## ¿Qué es?

Claude puede leer, interpretar y analizar archivos subidos directamente a la conversación: PDFs, imágenes (PNG, JPG, WebP, GIF), documentos Word, CSVs, archivos de código, y más. No solo extrae texto, sino que comprende el contexto, estructura, gráficos, tablas y elementos visuales.

## ¿Cómo se activa?

1. En Claude.ai, haz clic en el ícono de clip (adjuntar) y sube tu archivo.
2. Puedes subir múltiples archivos simultáneamente en una misma conversación.
3. Vía API, envía documentos como contenido base64 en el array `messages` con el tipo `document` o `image`.

## ¿Cómo funciona?

- Los documentos de texto (PDF, DOCX, TXT, CSV) se extraen y se pasan como contexto a Claude.
- Las imágenes se procesan con visión multimodal: Claude "ve" la imagen y puede describir, analizar o extraer información de ella.
- PDFs con tablas, gráficos o layouts complejos se interpretan combinando extracción de texto y análisis visual.
- Claude mantiene el contexto del documento durante toda la conversación, permitiendo preguntas de seguimiento.

## ¿Para qué se utiliza?

- Extraer y resumir información de papers académicos o reportes técnicos.
- Analizar gráficos, dashboards o visualizaciones en capturas de pantalla.
- Procesar y limpiar datos desde CSVs o hojas de cálculo.
- Revisar código subido en archivos fuente.
- Transcribir y analizar contenido de imágenes (OCR inteligente).
- Comparar múltiples documentos lado a lado.

## Ventaja competitiva para Data Scientists / Devs IA

- **Análisis de papers**: sube un paper de arXiv en PDF y pide que extraiga la arquitectura del modelo, los resultados de los experimentos y las limitaciones, en una fracción del tiempo de lectura manual.
- **Debugging visual**: sube una captura de un error, un gráfico con resultados inesperados, o un diagrama de arquitectura, y Claude lo interpretará directamente.
- **Procesamiento de datos**: sube un CSV desordenado y pide limpieza, detección de anomalías o análisis exploratorio sin escribir una línea de código.
- **Revisión de código**: sube archivos de tu proyecto y pide auditoría de seguridad, optimización de rendimiento o documentación automática.

## Ejemplo rápido

```
[Sube un PDF de un paper de ML]

Prompt: "Extrae de este paper: (1) la arquitectura propuesta con sus componentes 
principales, (2) los datasets usados en los experimentos, (3) los resultados en 
comparación con el baseline, y (4) las limitaciones que mencionan los autores."
```

Claude leerá el PDF completo y te dará un resumen estructurado con la información solicitada, referenciando secciones y tablas específicas del paper.

---

[← Deep Research](03-deep-research.md) | [Siguiente: Excel + K-means →](05-excel-kmeans.md)
