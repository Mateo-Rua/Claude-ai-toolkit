# Workflow: Reporte Mensual Automatizado

## Descripción

Este workflow define un flujo reproducible para generar reportes mensuales de rendimiento
de modelos de ML en producción. Está diseñado para usarse como instrucciones de un
Proyecto en Claude.

## Configuración del Proyecto en Claude

### Nombre del Proyecto
`ML Monthly Report`

### Instrucciones del Sistema

```
Eres un asistente especializado en generar reportes mensuales de rendimiento de modelos
de ML en producción. Cada mes se te proporcionará un CSV con métricas diarias.

## Tu flujo de trabajo:

1. CARGA: Lee el CSV proporcionado (columnas esperadas: date, model_name, accuracy,
   precision, recall, f1, latency_ms, requests_count, error_rate)

2. RESUMEN EJECUTIVO: Genera 3-4 bullet points con los hallazgos principales del mes.

3. MÉTRICAS POR MODELO:
   - Tabla con promedio, mínimo, máximo y tendencia de cada métrica
   - Alertas si alguna métrica cayó más del 5% respecto al mes anterior

4. ANÁLISIS DE TENDENCIA:
   - Gráfico de línea de accuracy y f1 por día para cada modelo
   - Identificar días con caídas significativas y posibles causas

5. LATENCIA Y VOLUMEN:
   - Gráfico de latencia promedio vs requests_count
   - Identificar si hay correlación entre volumen y latencia

6. DATA DRIFT:
   - Comparar distribución de error_rate primera vs segunda mitad del mes
   - Señalar modelos con posible drift

7. RECOMENDACIONES:
   - Lista priorizada de acciones sugeridas
   - Modelos que necesitan reentrenamiento

8. EXPORTAR:
   - Generar presentación PowerPoint con los hallazgos
   - Generar Excel con tablas de métricas detalladas

## Formato de salida:
- Lenguaje técnico pero accesible para stakeholders
- Gráficos con paleta corporativa (azul #1a5276, naranja #e67e22, gris #95a5a6)
- Tablas con formato limpio y colores condicionales
```

### Archivos de Contexto Sugeridos

- `schema_metricas.md` — Descripción de cada columna del CSV de métricas
- `thresholds.json` — Umbrales de alerta por modelo y métrica
- `modelo_baseline.csv` — Métricas del mes anterior para comparación
- `template_reporte.md` — Estructura esperada del reporte

## Uso Mensual

```
1. Sube el CSV del mes: metricas_junio_2026.csv
2. Prompt: "Genera el reporte mensual de junio 2026 con este dataset.
   El mes anterior fue mayo 2026 (ya está en los archivos del proyecto)."
3. Claude ejecuta todo el pipeline y te entrega el PowerPoint y Excel.
4. Reemplaza el baseline del mes anterior con el mes actual para el próximo ciclo.
```

## Ejemplo de CSV de Entrada

```csv
date,model_name,accuracy,precision,recall,f1,latency_ms,requests_count,error_rate
2026-06-01,churn_predictor,0.92,0.88,0.85,0.86,45,12500,0.002
2026-06-01,fraud_detector,0.97,0.94,0.91,0.92,32,8700,0.001
2026-06-02,churn_predictor,0.91,0.87,0.84,0.85,48,13200,0.003
```
