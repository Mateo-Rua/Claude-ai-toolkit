---
name: model-card-generator
description: Usa esta skill cuando el usuario pida crear una model card, documentación de modelo, ficha técnica de un modelo de ML, o documentación para MLOps. Genera un documento completo siguiendo estándares de la industria (Google Model Cards, Hugging Face Model Card).
---

# Skill: Generador de Model Cards

## Instrucciones

Cuando el usuario pida documentar un modelo de ML, sigue estos pasos:

### 1. Recopilar información

Solicita o infiere del contexto:
- Nombre y versión del modelo
- Tipo de modelo (clasificación, regresión, NLP, visión, etc.)
- Framework utilizado (scikit-learn, PyTorch, TensorFlow)
- Dataset de entrenamiento
- Métricas de evaluación
- Autor(es) y fecha

### 2. Generar la Model Card

Crea un documento Markdown con las siguientes secciones:

```markdown
# Model Card: [Nombre del Modelo]

## Detalles del Modelo
- **Nombre**: 
- **Versión**: 
- **Tipo**: 
- **Framework**: 
- **Fecha de entrenamiento**: 
- **Autor(es)**: 

## Uso Previsto
- **Caso de uso principal**: 
- **Usuarios objetivo**: 
- **Usos fuera del alcance** (NO usar para): 

## Datos de Entrenamiento
- **Fuente**: 
- **Tamaño**: registros / GB
- **Período temporal**: 
- **Preprocesamiento aplicado**: 
- **Distribución de clases** (si aplica):

## Datos de Evaluación
- **Fuente**: 
- **Tamaño**: 
- **Estrategia de split**: 

## Métricas de Rendimiento

| Métrica | Train | Validation | Test |
|---------|-------|------------|------|
| Accuracy | | | |
| Precision | | | |
| Recall | | | |
| F1 Score | | | |
| AUC-ROC | | | |

### Rendimiento por Subgrupo (si aplica)
[Tabla de métricas desglosada por categorías demográficas o segmentos relevantes]

## Hiperparámetros

| Parámetro | Valor |
|-----------|-------|
| learning_rate | |
| n_estimators | |
| max_depth | |
| batch_size | |
| epochs | |

## Consideraciones Éticas
- **Sesgos conocidos**: 
- **Mitigaciones aplicadas**: 
- **Limitaciones de fairness**: 

## Limitaciones y Riesgos
- **Limitaciones técnicas**: 
- **Escenarios de fallo conocidos**: 
- **Datos fuera de distribución**: 

## Reproducibilidad
- **Random seed**: 
- **Entorno**: Python X.X, librería vX.X
- **Hardware**: 
- **Tiempo de entrenamiento**: 

## Mantenimiento
- **Frecuencia de reentrenamiento**: 
- **Propietario**: 
- **Monitoreo**: 
```

### 3. Exportar

- Generar como archivo Markdown (.md)
- Opcionalmente, generar versión PDF si el usuario lo pide
- Incluir badges de metadata al inicio del documento

### 4. Validación

Verificar que la model card incluye:
- [ ] Todas las secciones obligatorias
- [ ] Métricas con valores concretos (no placeholders)
- [ ] Al menos una limitación o riesgo documentado
- [ ] Información de reproducibilidad
