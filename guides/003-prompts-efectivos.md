# 03 — Cómo Armar Prompts Efectivos en Claude

## ¿Qué es un Prompt?

Un prompt es la instrucción o mensaje que le envías a Claude para obtener una respuesta. Es tu forma de comunicarte con la IA — y la calidad de lo que recibes depende directamente de la calidad de lo que envías. Un prompt puede ser tan simple como una pregunta de una línea o tan complejo como un documento estructurado con contexto, ejemplos, restricciones y formato esperado.

Pensar en prompts es pensar en comunicación efectiva: mientras más claro, específico y contextualizado sea tu mensaje, más precisa y útil será la respuesta.

## Anatomía de un Prompt Efectivo

Un buen prompt tiene hasta 6 componentes. No todos son necesarios siempre, pero conocerlos te permite construir instrucciones precisas cuando la tarea lo requiere:

```
┌─────────────────────────────────────────────────┐
│  1. ROL         → Quién quieres que sea Claude  │
│  2. CONTEXTO    → Información de fondo          │
│  3. TAREA       → Qué quieres que haga          │
│  4. FORMATO     → Cómo quieres la respuesta     │
│  5. EJEMPLOS    → Muestras de input/output       │
│  6. RESTRICCIONES → Qué debe evitar o respetar  │
└─────────────────────────────────────────────────┘
```

### 1. Rol (opcional pero poderoso)

Define la perspectiva desde la cual Claude debe responder. Esto ajusta el nivel técnico, el vocabulario y el enfoque.

```
"Eres un ingeniero de datos senior con 10 años de experiencia en pipelines de 
datos a gran escala con Apache Spark y Airflow."
```

### 2. Contexto (cuanto más, mejor)

Proporciona la información de fondo que Claude necesita para entender tu situación. No asumas que Claude conoce tu proyecto, tu stack o tus restricciones.

```
"Trabajo en una fintech en Colombia. Nuestro pipeline actual procesa 2M de 
transacciones diarias desde PostgreSQL hacia un data warehouse en BigQuery. 
El proceso actual tarda 4 horas y necesitamos reducirlo a menos de 1 hora."
```

### 3. Tarea (ser específico y directo)

Define exactamente qué quieres que haga Claude. Las instrucciones vagas producen respuestas vagas.

```
❌ Vago: "Ayúdame con mi pipeline de datos"
✅ Específico: "Propón 3 estrategias para reducir el tiempo de procesamiento 
de mi pipeline de 4 horas a menos de 1 hora, considerando que no podemos 
cambiar la base de datos de origen."
```

### 4. Formato (define la estructura de salida)

Especifica cómo quieres recibir la información: prosa, lista, tabla, código, JSON, Markdown, etc.

```
"Responde con una tabla comparativa con columnas: Estrategia, Complejidad de 
implementación (alta/media/baja), Tiempo estimado de reducción, y Trade-offs. 
Después de la tabla, incluye el código Python para la estrategia que recomiendes."
```

### 5. Ejemplos (few-shot prompting)

Proporciona ejemplos de input y output esperado. Esto es especialmente útil para tareas de clasificación, extracción o transformación donde el formato exacto importa.

```
"Clasifica estos tickets de soporte. Ejemplo:

Input: 'No puedo iniciar sesión desde ayer, ya cambié la contraseña'
Output: { categoria: 'autenticacion', prioridad: 'alta', producto: 'login' }

Input: 'Me gustaría poder exportar reportes a PDF'
Output: { categoria: 'feature_request', prioridad: 'baja', producto: 'reportes' }

Ahora clasifica estos:
[tus tickets aquí]"
```

### 6. Restricciones (límites y reglas)

Define lo que Claude debe evitar, respetar o priorizar.

```
"No uses librerías de pago. El código debe ser compatible con Python 3.9+. 
No incluyas soluciones que requieran cambiar la infraestructura de base de datos. 
Prioriza soluciones que podamos implementar esta semana."
```

## Técnicas Avanzadas de Prompting

### Chain of Thought (Cadena de Pensamiento)

Pide a Claude que razone paso a paso antes de dar la respuesta final. Mejora significativamente la precisión en problemas de lógica, matemáticas y análisis.

```
"Analiza este dataset y determina si hay data leakage. Piensa paso a paso: 
primero examina las features, luego verifica las correlaciones con el target, 
después revisa la temporalidad de los datos, y finalmente da tu conclusión."
```

### Prompts Negativos

Indicar explícitamente lo que NO quieres es tan importante como indicar lo que sí quieres.

```
"Explica cómo funciona un transformer. No uses analogías simplificadas ni 
metáforas — quiero la explicación técnica con la notación matemática real. 
No omitas la parte de multi-head attention."
```

### Iteración y Refinamiento

Un prompt no tiene que ser perfecto a la primera. Usa la conversación para refinar:

```
Turno 1: "Genera un script de EDA para un dataset de ventas"
Turno 2: "Ahora agrega detección de outliers con IQR"
Turno 3: "Cambia los gráficos a un estilo oscuro profesional"
Turno 4: "Exporta todo como un notebook de Jupyter"
```

### XML Tags para Estructura

Claude responde especialmente bien a prompts organizados con etiquetas XML cuando la instrucción tiene múltiples partes:

```
<contexto>
Soy data scientist en una empresa de retail con 500 tiendas.
Nuestro modelo de forecasting actual usa Prophet.
</contexto>

<tarea>
Propón una migración de Prophet a un modelo de deep learning 
para forecasting de demanda.
</tarea>

<restricciones>
- Presupuesto de GPU limitado (1x A100 por 4 horas/día)
- El modelo debe actualizar predicciones diariamente
- Necesitamos predicciones a nivel SKU-tienda
</restricciones>

<formato>
Responde con: análisis del problema, modelo propuesto con justificación, 
arquitectura técnica, plan de implementación en 3 fases, y riesgos a mitigar.
</formato>
```

## Errores Comunes en Prompting

| Error | Problema | Solución |
|-------|----------|----------|
| Demasiado vago | "Ayúdame con ML" | Especifica la tarea, los datos y el objetivo |
| Sin contexto | Claude asume tu entorno | Incluye stack, restricciones, tamaño de datos |
| Pedir todo a la vez | Respuesta superficial en todo | Divide en pasos o conversaciones |
| No especificar formato | Output en formato inesperado | Define estructura, longitud y estilo |
| No iterar | Quedarse con la primera respuesta | Refina, pide cambios, profundiza |
| Asumir conocimiento previo | Claude no conoce tu proyecto | Proporciona contexto cada vez (o usa Memoria/Proyectos) |

## Ventaja competitiva para Data Scientists / Devs IA

- **Prompts como código**: trata tus prompts como artefactos de ingeniería — versiónalos, documéntalos y reutilízalos. Un prompt bien diseñado para EDA o model evaluation es un activo reutilizable que ahorra horas en cada proyecto.
- **Few-shot para pipelines**: con 2-3 ejemplos de input/output puedes hacer que Claude procese, clasifique o transforme datos de forma consistente sin escribir código, ideal para prototipado rápido.
- **System prompts en producción**: en la API, el system prompt define el comportamiento base de Claude para tu aplicación. Un system prompt bien diseñado es la diferencia entre un chatbot genérico y un asistente especializado en tu dominio.
- **Prompting > Fine-tuning**: para muchos casos de uso, un prompt bien estructurado con contexto y ejemplos produce resultados comparables a un modelo fine-tuneado, sin el costo ni la complejidad de entrenamiento.

## Ejemplo Completo

```
Eres un científico de datos senior especializado en NLP y análisis de sentimiento.

CONTEXTO:
Tengo un dataset de 50K reseñas de productos de un e-commerce colombiano. 
Las reseñas están en español, con jerga local y errores ortográficos frecuentes. 
El dataset tiene columnas: review_id, text, rating (1-5), date, product_category.

TAREA:
1. Propón un pipeline completo de análisis de sentimiento para este dataset.
2. Incluye preprocesamiento específico para español colombiano.
3. Compara al menos 3 enfoques (rule-based, ML tradicional, transformer).
4. Recomienda el mejor enfoque considerando que no tengo GPU.

FORMATO:
- Tabla comparativa de los 3 enfoques (accuracy esperada, pros, contras, costo)
- Código Python del enfoque recomendado, listo para ejecutar
- Lista de librerías necesarias con versiones

RESTRICCIONES:
- Sin GPU (solo CPU, 16GB RAM)
- Presupuesto $0 para APIs externas
- El pipeline debe procesar las 50K reseñas en menos de 30 minutos
```

---

[← Haiku, Sonnet y Opus](16-haiku-sonnet-opus.md) | [Volver al índice →](../README.md)
