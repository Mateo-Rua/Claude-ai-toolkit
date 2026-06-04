# 10 — Memoria de Claude: Cómo Funciona y Cuándo Activarla

## ¿Qué es?

La Memoria de Claude es un sistema que permite retener información entre conversaciones separadas. Claude recuerda datos relevantes que has compartido previamente — tu nombre, rol, preferencias, proyectos en curso, stack tecnológico — y los usa como contexto en futuras interacciones sin que tengas que repetirlos.

## ¿Cómo se activa?

1. En Claude.ai, ve a Configuración (Settings) → Memoria.
2. Activa la opción de memoria.
3. Claude comenzará a crear memorias automáticamente a partir de información relevante que compartas.
4. Puedes ver, editar y eliminar memorias almacenadas en cualquier momento.
5. También puedes decirle explícitamente "Recuerda que..." para crear una memoria.

## ¿Cómo funciona?

- Cuando la memoria está activada, Claude identifica información que vale la pena retener (preferencias, datos personales, contexto de proyectos).
- Esta información se almacena como fragmentos de texto ("memorias") asociados a tu cuenta.
- En cada nueva conversación, Claude accede a estas memorias para contextualizar sus respuestas.
- Las memorias se pueden gestionar manualmente: puedes indicar qué recordar, qué olvidar, o revisar todas las memorias almacenadas.
- Claude no recuerda nada hasta que actives esta función explícitamente.

## ¿Para qué se utiliza?

- Evitar repetir tu contexto profesional en cada conversación nueva.
- Mantener continuidad en proyectos de largo plazo.
- Almacenar preferencias de formato, estilo y herramientas.
- Crear un perfil progresivo de tus necesidades y contexto.
- Tener un asistente que "te conoce" y se adapta con el tiempo.

## Ventaja competitiva para Data Scientists / Devs IA

- **Contexto persistente**: Claude recuerda que trabajas con PyTorch, que tu empresa usa Snowflake, que prefieres polars sobre pandas, y adapta todas sus respuestas futuras a tu stack.
- **Continuidad de proyectos**: si estás trabajando en un modelo de NLP durante semanas, Claude recuerda el estado del proyecto, las decisiones tomadas y los próximos pasos sin que tengas que resumir cada vez.
- **Preferencias técnicas**: recuerda tus convenciones de código, formato de documentación preferido, y estilo de visualización para generar output consistente.
- **Reducción de fricción**: cada conversación nueva arranca con tu contexto completo, eliminando los primeros 5 minutos de "setup" habituales.

## Ejemplo rápido

```
Conversación 1:
"Soy científico de datos en una fintech en Colombia. Trabajo con Python, 
scikit-learn y XGBoost. Nuestros datos están en BigQuery y deployamos 
modelos con Vertex AI. Recuerda esto para futuras conversaciones."

Conversación 2 (días después):
"Necesito implementar monitoring para mi modelo en producción."

→ Claude ya sabe que usas Vertex AI y BigQuery, y te sugiere soluciones 
específicas para ese stack (Model Monitoring de Vertex AI, alertas de 
data drift integradas con BigQuery).
```

---

[← Estilos de Escritura](09-writing-styles.md) | [Siguiente: Conectores MCP →](11-mcp-connectors.md)
