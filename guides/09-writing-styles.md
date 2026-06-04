# 12 — Estilos de Escritura Personalizados en Claude

## ¿Qué es?

Los estilos de escritura personalizados permiten definir cómo Claude se comunica contigo: tono, nivel de detalle, formato, idioma técnico, y personalidad. Puedes crear perfiles de estilo reutilizables que se aplican a todas tus conversaciones o a proyectos específicos.

## ¿Cómo se activa?

1. En Claude.ai, ve a Configuración (Settings) → Estilos de escritura.
2. Puedes elegir entre estilos predefinidos (Formal, Conciso, Explicativo) o crear uno personalizado.
3. También puedes proporcionar muestras de tu propia escritura para que Claude emule tu estilo.
4. El estilo seleccionado aplica a todas las conversaciones o se puede cambiar por chat.

## ¿Cómo funciona?

- Los estilos personalizados se almacenan como preferencias en tu perfil.
- Cuando creas un estilo personalizado, defines reglas sobre: tono (formal/casual), longitud (conciso/detallado), formato (prosa/listas/código), nivel técnico, y cualquier convención específica.
- Claude adapta todas sus respuestas para cumplir con estas preferencias.
- Puedes alternar entre estilos dentro de la misma sesión.

## ¿Para qué se utiliza?

- Mantener consistencia en documentación técnica.
- Adaptar respuestas para diferentes audiencias (técnica vs. ejecutiva).
- Generar contenido que suene como tu propia voz (blog, redes sociales).
- Estandarizar el formato de salida para flujos de trabajo repetitivos.
- Reducir la necesidad de re-especificar preferencias en cada conversación.

## Ventaja competitiva para Data Scientists / Devs IA

- **Documentación consistente**: define un estilo "Documentación técnica" que siempre use docstrings de NumPy, explique complejidades algorítmicas y siga las convenciones de tu equipo.
- **Comunicación adaptativa**: cambia entre estilo "Técnico" para tus compañeros de equipo y "Ejecutivo" para presentaciones a stakeholders, sin re-explicar el contexto.
- **Productividad en escritura**: si publicas contenido técnico (blog, Medium, LinkedIn), crea un estilo con tu voz y tono, y Claude producirá borradores que suenan como tú.
- **Code review estandarizado**: define un estilo que siempre señale performance, seguridad, legibilidad y testing al revisar código.

## Ejemplo rápido

```
Estilo personalizado: "Data Science Técnico"

Reglas:
- Usa terminología precisa de ML/estadística sin simplificar excesivamente
- Incluye complejidad temporal y espacial cuando sea relevante
- Código siempre en Python con type hints
- Prioriza explicación de trade-offs sobre respuestas absolutas
- Formato: párrafo breve de contexto → código → explicación de decisiones
- Cita papers o librerías relevantes cuando aplique
```

---

[← Proyectos](08-projects.md) | [Siguiente: Memoria →](10-memory.md)
