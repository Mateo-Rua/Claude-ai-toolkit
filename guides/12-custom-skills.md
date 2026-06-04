# 15 — Cómo Crear Skills Personalizadas en Claude

## ¿Qué es?

Las Skills (habilidades) personalizadas son instrucciones empaquetadas que enseñan a Claude un flujo de trabajo específico y reutilizable. Una skill define paso a paso cómo Claude debe abordar un tipo de tarea — qué librerías usar, qué formato seguir, qué errores evitar — y se activa automáticamente cuando la tarea lo requiere.

## ¿Cómo se activa?

1. Las skills se definen como archivos SKILL.md dentro de una estructura de carpetas específica.
2. En Claude.ai con ejecución de código, las skills se cargan desde el directorio `/mnt/skills/`.
3. Hay skills públicas (preinstaladas) para tareas comunes (crear DOCX, PPTX, XLSX, PDFs) y puedes crear skills propias.
4. Claude lee automáticamente la skill relevante antes de ejecutar una tarea que la requiera.

## ¿Cómo funciona?

- Cada skill es un archivo Markdown (SKILL.md) que contiene: nombre, descripción (trigger), y las instrucciones detalladas paso a paso.
- La descripción actúa como "trigger" — cuando tu solicitud coincide con la descripción, Claude lee y sigue las instrucciones de la skill.
- Las instrucciones pueden incluir: qué librerías importar, cómo estructurar el código, qué patrones seguir, qué errores comunes evitar, y cómo formatear la salida.
- Puedes crear skills para cualquier flujo repetitivo en tu trabajo.

## ¿Para qué se utiliza?

- Estandarizar cómo Claude genera ciertos tipos de archivos o análisis.
- Encapsular mejores prácticas de tu equipo en instrucciones reutilizables.
- Crear flujos de trabajo reproducibles para tareas recurrentes.
- Garantizar calidad y consistencia en outputs repetitivos.
- Compartir conocimiento procedimental entre miembros del equipo.

## Ventaja competitiva para Data Scientists / Devs IA

- **Pipelines como código**: encapsula tu pipeline de EDA, entrenamiento o evaluación como una skill, y cada vez que necesites ejecutarlo Claude sigue exactamente los mismos pasos con la calidad que definiste.
- **Onboarding de prácticas**: las mejores prácticas de tu equipo (cómo hacer feature engineering, cómo documentar modelos, cómo estructurar experimentos) se codifican como skills que cualquier miembro puede usar.
- **Calidad reproducible**: evita que Claude use enfoques inconsistentes — la skill garantiza que siempre use la versión correcta de una librería, el formato esperado y las validaciones necesarias.
- **Evolución continua**: las skills se versionan y mejoran con el tiempo, capturando lecciones aprendidas de iteraciones anteriores.

## Ejemplo rápido

```markdown
# SKILL.md - Análisis de Feature Importance

name: feature-importance-analysis
description: Usa esta skill cuando el usuario pida analizar la importancia 
de features en un modelo de ML. Incluye múltiples métodos de importancia 
y visualización comparativa.

## Instrucciones

1. Cargar el dataset con pandas
2. Entrenar el modelo indicado (default: RandomForest)
3. Calcular importancia con 3 métodos:
   - Feature importance del modelo (built-in)
   - Permutation importance (sklearn)
   - SHAP values (shap library)
4. Generar gráfico comparativo con los 3 métodos lado a lado
5. Crear tabla resumen con ranking de features por cada método
6. Identificar features consistentemente importantes vs. discrepancias
7. Exportar resultados como Excel con una pestaña por método
```

---

[← Conectores MCP](11-mcp-connectors.md) | [Siguiente: Claude Code →](13-claude-code.md)
