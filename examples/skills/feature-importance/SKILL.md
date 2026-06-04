---
name: feature-importance-analysis
description: Usa esta skill cuando el usuario pida analizar la importancia de features, ranking de variables, o selección de features para un modelo de ML. Ejecuta múltiples métodos de importancia y genera un análisis comparativo con visualizaciones y recomendaciones.
---

# Skill: Análisis de Feature Importance Multi-Método

## Instrucciones

### 1. Preparación

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.ensemble import RandomForestClassifier, RandomForestRegressor
from sklearn.inspection import permutation_importance
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder, StandardScaler

# Instalar SHAP si no está disponible
try:
    import shap
except ImportError:
    import subprocess
    subprocess.run(['pip', 'install', 'shap', '--break-system-packages', '-q'])
    import shap
```

### 2. Proceso

1. **Cargar y preparar datos**
   - Leer el dataset del usuario
   - Identificar automáticamente la variable target
   - Separar features numéricas y categóricas
   - Encoding de variables categóricas con LabelEncoder
   - Split train/test (80/20, stratify si es clasificación)

2. **Método 1: Built-in Feature Importance (MDI)**
   - Entrenar RandomForest (100 árboles, random_state=42)
   - Extraer `.feature_importances_`
   - Ordenar de mayor a menor

3. **Método 2: Permutation Importance**
   - Usar `permutation_importance` de sklearn sobre test set
   - `n_repeats=10`, `random_state=42`
   - Extraer media e intervalo de confianza

4. **Método 3: SHAP Values**
   - Crear `shap.TreeExplainer` con el modelo entrenado
   - Calcular SHAP values sobre muestra de test (max 500 registros)
   - Extraer importancia media absoluta por feature

5. **Comparativa**
   - Generar tabla con ranking por cada método
   - Calcular ranking promedio (Borda count)
   - Identificar features consistentemente top-10 en los 3 métodos
   - Identificar discrepancias significativas entre métodos

### 3. Visualizaciones

```python
# Gráfico 1: Barras horizontales comparativas (3 subplots lado a lado)
fig, axes = plt.subplots(1, 3, figsize=(18, 8))
# ... MDI, Permutation, SHAP en cada subplot

# Gráfico 2: SHAP beeswarm plot (si SHAP disponible)
shap.summary_plot(shap_values, X_test, show=False)

# Gráfico 3: Heatmap de rankings comparativos
# Filas = features, Columnas = métodos, Color = ranking
```

### 4. Output

Generar:
- **Tabla resumen** con 4 columnas: Feature, Rank_MDI, Rank_Permutation, Rank_SHAP, Rank_Promedio
- **Recomendación** de features a conservar (top N donde los 3 métodos coinciden)
- **Features candidatas a eliminar** (bottom 20% en los 3 métodos)
- **Alertas** sobre features con rankings muy dispares entre métodos
- **Exportar** tabla a Excel con formato condicional

### 5. Interpretación

Para cada feature del top 5, proporcionar:
- Qué mide la feature
- Por qué es importante para el modelo
- Cómo interpretar su SHAP value (dirección del efecto)
- Recomendaciones de feature engineering relacionadas
