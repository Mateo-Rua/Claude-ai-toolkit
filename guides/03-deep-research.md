# 06 — Deep Research en Claude

## ¿Qué es?

Deep Research es una capacidad que permite a Claude realizar investigaciones profundas y autónomas sobre un tema. A diferencia de una búsqueda web simple, Claude ejecuta docenas de búsquedas encadenadas, lee múltiples fuentes, cruza información y genera un informe completo y estructurado con citas.

## ¿Cómo se activa?

1. En Claude.ai, selecciona el modo "Deep Research" antes de enviar tu consulta (disponible en planes Pro, Team y Enterprise).
2. Claude te muestra un plan de investigación antes de ejecutarlo, permitiéndote ajustar el enfoque.

## ¿Cómo funciona?

- Recibes tu pregunta y Claude genera un plan de investigación con las áreas que va a explorar.
- Ejecuta múltiples búsquedas web secuenciales y en paralelo (puede realizar 50+ búsquedas por investigación).
- Lee, analiza y cruza información de las fuentes encontradas.
- Genera un informe largo y detallado con secciones, hallazgos clave y todas las fuentes citadas.
- El proceso puede tomar varios minutos dependiendo de la complejidad.

## ¿Para qué se utiliza?

- Revisiones de literatura técnica o estado del arte.
- Análisis comparativo de tecnologías, herramientas o proveedores.
- Investigación de mercado o industria.
- Due diligence técnica sobre una librería, API o plataforma.
- Preparación de informes con múltiples fuentes verificadas.

## Ventaja competitiva para Data Scientists / Devs IA

- **State of the art en minutos**: pide una revisión del estado actual de técnicas de RAG, fine-tuning eficiente o MLOps, y obtén un informe con papers, herramientas y comparativas recientes.
- **Evaluación de herramientas**: antes de integrar una nueva librería o servicio, Deep Research te da un análisis completo de documentación, issues conocidos, comunidad y alternativas.
- **Preparación de propuestas**: genera informes fundamentados para justificar decisiones técnicas ante stakeholders, con datos y fuentes verificables.
- **Ahorro de horas**: lo que normalmente tomaría medio día de investigación manual, Claude lo hace en 5-10 minutos.

## Ejemplo rápido

```
Prompt: "Investiga las técnicas más recientes de fine-tuning eficiente para LLMs 
(LoRA, QLoRA, DoRA, etc.). Quiero saber: qué hace cada una, benchmarks comparativos, 
requisitos de hardware, y cuál es la mejor opción para fine-tunear un modelo de 7B 
parámetros con una GPU A100 de 40GB."
```

Claude generará un informe multi-sección con comparativas técnicas, tablas de benchmarks, requerimientos de VRAM, y una recomendación fundamentada.

---

[← Pensamiento Extendido](02-extended-thinking.md) | [Siguiente: Análisis de Documentos →](04-document-analysis.md)
