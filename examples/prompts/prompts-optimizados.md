# 📝 Prompts Optimizados por Feature

Colección de prompts probados y optimizados para cada capacidad de Claude. Copia, adapta y usa.

---

## Búsqueda Web — Benchmark de Modelos

```
Busca los benchmarks más recientes (2025-2026) que comparen los principales LLMs 
(Claude, GPT, Gemini, Llama) en las siguientes tareas: coding (HumanEval, SWE-bench), 
razonamiento matemático (MATH, GSM8K), y comprensión de lenguaje (MMLU). 
Presenta los resultados en una tabla comparativa con las fuentes.
```

## Pensamiento Extendido — Diseño de Arquitectura ML

```
Necesito diseñar la arquitectura de un sistema de recomendación para un e-commerce 
con 10M de usuarios y 500K productos. Requisitos: latencia <100ms en serving, 
actualización diaria del modelo, capacidad de A/B testing. Stack actual: Python, 
PostgreSQL, AWS. Piensa paso a paso sobre los componentes necesarios, trade-offs 
de cada decisión, y dame una arquitectura detallada con justificaciones.
```

## Deep Research — Estado del Arte

```
Investiga el estado actual de las técnicas de Retrieval-Augmented Generation (RAG) 
en 2025-2026. Quiero conocer: (1) evolución desde RAG básico hasta las técnicas 
más recientes, (2) comparativa de frameworks (LangChain, LlamaIndex, Haystack), 
(3) técnicas de chunking y embedding más efectivas según benchmarks recientes, 
(4) casos de uso en producción documentados, (5) limitaciones conocidas y 
direcciones de investigación activa.
```

## Análisis de Documentos — Extracción de Paper

```
[Adjuntar PDF del paper]

De este paper necesito:
1. Resumen ejecutivo en 3 oraciones
2. Arquitectura del modelo propuesto con sus componentes
3. Tabla de resultados principales vs baselines
4. Datasets utilizados con sus características (tamaño, dominio)
5. Limitaciones que reconocen los autores
6. 3 ideas que podría aplicar a mi propio trabajo
```

## Excel + K-means — Segmentación de Clientes

```
[Adjuntar dataset.xlsx]

Realiza una segmentación de clientes con K-means:
1. EDA: distribuciones, correlaciones, valores faltantes
2. Preprocesamiento: imputa nulos con la mediana, normaliza con StandardScaler
3. Determina K óptimo con elbow method y silhouette score (rango 2-8)
4. Ejecuta K-means con el K óptimo
5. Visualiza clusters en 2D con PCA
6. Genera tabla de centroides con interpretación de cada segmento
7. Exporta el dataset original con columna 'cluster' asignada
```

## Artefactos — Dashboard Interactivo

```
Crea un dashboard interactivo en React con Recharts que muestre:
- Selector de período (últimos 7, 30, 90 días)
- Gráfico de línea de revenue diario
- Gráfico de barras de revenue por categoría
- KPI cards (revenue total, ticket promedio, transacciones, crecimiento %)
- Tabla con top 10 productos
Usa datos ficticios pero realistas para un e-commerce.
Colores: slate/blue profesional. Responsive.
```

## Proyectos — System Prompt para Asistente de ML

```
Instrucciones del proyecto:

Eres un asistente experto en Machine Learning para nuestro equipo.

Contexto técnico:
- Stack: Python 3.11, scikit-learn, XGBoost, PyTorch, pandas, polars
- Infraestructura: GCP (BigQuery, Vertex AI, Cloud Storage)
- MLOps: MLflow para tracking, DVC para datos, GitHub Actions para CI/CD

Reglas de respuesta:
- Siempre incluir type hints en código Python
- Usar logging con loguru, no print()
- Preferir polars sobre pandas cuando el dataset > 1GB
- Documentar funciones con docstrings estilo NumPy
- Sugerir tests para cada función nueva
- Formato: contexto breve → código → explicación de decisiones → tests sugeridos
```

## MCP + Claude Code — Workflow Combinado

```
# En Claude Code con MCP de GitHub conectado

Revisa todos los issues abiertos con label "bug" en nuestro repo.
Para cada bug:
1. Lee la descripción y los logs adjuntos
2. Busca en el codebase el archivo más probablemente responsable
3. Propón una corrección
4. Crea un branch fix/<issue-number> con la corrección
5. Corre los tests para verificar que no rompe nada
6. Genera un resumen de todos los bugs y sus correcciones propuestas
```

## Skills — Template de Skill Personalizada

```markdown
---
name: ml-model-card
description: Usa esta skill cuando el usuario pida crear una model card, 
documentación de modelo, o ficha técnica de un modelo de ML. Genera un 
documento completo siguiendo el template de Google Model Cards.
---

## Instrucciones

1. Solicitar al usuario: nombre del modelo, tipo, dataset, métricas
2. Generar documento Markdown con secciones:
   - Model Details (nombre, versión, tipo, fecha, autores)
   - Intended Use (uso previsto, usuarios, limitaciones de uso)
   - Training Data (fuente, tamaño, preprocesamiento)
   - Evaluation Data (fuente, métricas, resultados)
   - Ethical Considerations (bias conocidos, mitigaciones)
   - Caveats and Recommendations
3. Incluir tablas de métricas formateadas
4. Agregar sección de reproducibilidad (seeds, hiperparámetros)
5. Exportar como Markdown y opcionalmente como PDF
```
