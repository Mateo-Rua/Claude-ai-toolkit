# 08 — Analiza Excel con Claude y K-means

## ¿Qué es?

Claude puede recibir archivos Excel (.xlsx) o CSV, ejecutar código Python en un entorno real, y realizar análisis de datos completos incluyendo técnicas de machine learning como clustering K-means. No es una simulación — Claude ejecuta código real con pandas, scikit-learn, matplotlib y genera resultados descargables.

## ¿Cómo se activa?

1. Sube tu archivo Excel o CSV directamente al chat de Claude.
2. La funcionalidad de ejecución de código (Code Execution) se activa automáticamente cuando Claude necesita procesar datos.
3. Claude escribe, ejecuta y depura código Python en un entorno con las librerías de data science preinstaladas.

## ¿Cómo funciona?

- Subes tu dataset y describes lo que necesitas.
- Claude lee el archivo con pandas, hace exploración inicial (shape, dtypes, nulos, estadísticas descriptivas).
- Escribe y ejecuta código de análisis, limpieza o modelado.
- Genera visualizaciones (gráficos matplotlib/seaborn) que se muestran inline.
- Puede exportar resultados como nuevos archivos Excel, CSV o imágenes descargables.

## ¿Para qué se utiliza?

- Análisis exploratorio de datos (EDA) sin abrir Jupyter.
- Clustering de clientes, productos o cualquier entidad con K-means u otros algoritmos.
- Limpieza y transformación de datos (manejo de nulos, encoding, normalización).
- Generación rápida de visualizaciones y gráficos estadísticos.
- Creación de reportes con resultados exportados a Excel formateado.

## Ventaja competitiva para Data Scientists / Devs IA

- **Prototipado ultra-rápido**: en lugar de abrir un notebook, configurar el entorno y escribir boilerplate, sube el Excel y describe en lenguaje natural lo que necesitas.
- **EDA conversacional**: puedes iterar sobre el análisis pidiendo más detalle, cambiando parámetros o explorando otros ángulos sin reiniciar.
- **K-means sin fricción**: pide segmentación de clientes y Claude se encarga de normalizar features, encontrar el K óptimo (elbow method / silhouette score), y visualizar los clusters.
- **Entregables inmediatos**: genera el Excel limpio, el gráfico de clusters y la tabla de centroides, todo descargable y listo para presentar.

## Ejemplo rápido

```
[Sube customers_data.xlsx]

Prompt: "Analiza este dataset de clientes. Quiero: (1) EDA rápido con estadísticas 
descriptivas y distribuciones de las variables numéricas, (2) segmentación con K-means 
usando las columnas de gasto anual, frecuencia de compra e ingreso estimado, 
(3) determina el número óptimo de clusters, y (4) genera un Excel con una columna 
nueva indicando el cluster asignado a cada cliente."
```

Claude ejecutará todo el pipeline y te entregará: gráficos de distribución, el gráfico del codo, scatter plot de clusters coloreados, tabla de centroides con interpretación, y el archivo Excel resultante.

---

[← Análisis de Documentos](04-document-analysis.md) | [Siguiente: PowerPoint →](06-powerpoint.md)
