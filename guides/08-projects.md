# 11 — Proyectos en Claude: Automatiza Tareas Repetitivas

## ¿Qué es?

Los Proyectos (Projects) en Claude son espacios de trabajo persistentes donde puedes cargar archivos de contexto, definir instrucciones personalizadas (system prompts), y crear un entorno especializado para un dominio o tarea específica. Todo chat creado dentro de un proyecto hereda automáticamente ese contexto.

## ¿Cómo se activa?

1. En Claude.ai, ve al panel lateral y selecciona "Projects" (disponible en planes Pro, Team y Enterprise).
2. Crea un nuevo proyecto, dale un nombre y descripción.
3. Agrega archivos de contexto (documentación, datos, código) y escribe instrucciones personalizadas.
4. Cada nueva conversación dentro del proyecto arranca con todo ese contexto precargado.

## ¿Cómo funciona?

- El proyecto actúa como un "workspace" persistente con contexto compartido.
- Los archivos subidos al proyecto están disponibles en todas las conversaciones del mismo.
- Las instrucciones personalizadas definen cómo debe comportarse Claude dentro de ese contexto (rol, formato de respuesta, restricciones, conocimiento de dominio).
- Puedes tener múltiples proyectos para diferentes tareas o dominios.

## ¿Para qué se utiliza?

- Crear un asistente especializado en tu codebase o documentación técnica.
- Mantener contexto persistente para análisis iterativos sobre el mismo dataset.
- Estandarizar respuestas para un equipo (mismo contexto y reglas).
- Automatizar tareas repetitivas definiendo el formato y proceso esperado.
- Centralizar documentación de referencia para consultas recurrentes.

## Ventaja competitiva para Data Scientists / Devs IA

- **Asistente de codebase**: sube la documentación de tu proyecto de ML, los schemas de datos y las convenciones de código, y cada conversación nueva ya "conoce" tu proyecto.
- **Análisis recurrentes**: define un proyecto para reporting mensual con las instrucciones de formato, KPIs relevantes y estructura esperada, luego solo sube los datos nuevos cada mes.
- **Onboarding acelerado**: crea un proyecto con toda la documentación de tu pipeline de datos y úsalo como asistente interactivo para nuevos miembros del equipo.
- **Estandarización**: garantiza que las respuestas sobre tu dominio sigan las mismas convenciones y usen la terminología correcta.

## Ejemplo rápido

```
Nombre del proyecto: "Pipeline de ML - Predicción de Churn"

Archivos de contexto:
- schema_base_datos.sql
- diccionario_datos.md
- pipeline_actual.py
- metricas_baseline.csv

Instrucciones personalizadas:
"Eres un asistente especializado en nuestro pipeline de predicción de churn. 
Conoces el schema de la base de datos, las features actuales y las métricas 
baseline. Cuando sugiera cambios, siempre compara contra el baseline actual.
Usa Python con pandas y scikit-learn. Formato de respuesta: problema → 
propuesta → código → impacto esperado."
```

Ahora cualquier conversación en este proyecto arranca con todo ese contexto sin necesidad de re-explicar nada.

---

[← Artefactos](07-artifacts.md) | [Siguiente: Estilos de Escritura →](09-writing-styles.md)
