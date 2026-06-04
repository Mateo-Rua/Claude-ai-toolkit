# 02 — Cómo Elegir entre Haiku, Sonnet y Opus

## ¿Qué Son?

Anthropic organiza sus modelos de Claude en **tres niveles** (tiers), cada uno optimizado para un punto diferente en el espectro velocidad-inteligencia-costo:

| Modelo | Rol | Velocidad | Inteligencia | Costo API (por 1M tokens) |
|--------|-----|-----------|-------------|---------------------------|
| **Haiku 4.5** | Rápido y económico | ⚡⚡⚡ Más rápido (~97 tok/s) | Buena | $1 input / $5 output |
| **Sonnet 4.6** | Balance producción | ⚡⚡ Rápido | Muy alta | $3 input / $15 output |
| **Opus 4.6+** | Máxima inteligencia | ⚡ Moderado | La más alta | $5 input / $25 output |

Los tres comparten la arquitectura Claude 4 y soportan: tool use, system prompts, outputs estructurados, visión multimodal y pensamiento extendido.

## ¿Cómo Funciona Cada Uno?

### Haiku 4.5 — El velocista económico

Haiku está diseñado para tareas de alto volumen donde la velocidad y el costo importan más que la profundidad de razonamiento. Procesa a ~97 tokens por segundo y cuesta 5x menos que Opus en output.

**Ideal para:**
- Clasificación de texto y routing de solicitudes
- Extracción de datos estructurados de documentos
- Respuestas rápidas en chatbots de atención al cliente
- Filtrado y preprocesamiento de datos
- Code review de cambios simples
- Tareas repetitivas a gran escala

**Contexto:** 200K tokens (el menor de los tres, pero suficiente para la mayoría de tareas de clasificación y extracción).

**Cuándo NO usarlo:** tareas que requieran razonamiento multi-paso, generación de código complejo, o análisis profundo.

---

### Sonnet 4.6 — El caballo de batalla

Sonnet es el modelo recomendado por defecto para la mayoría de usos. Con 79.6% en SWE-bench Verified, está a solo 1.2 puntos de Opus en coding, pero cuesta 40% menos y responde 17% más rápido. Para la mayoría de tareas de escritura, código y análisis, su output es indistinguible de Opus.

**Ideal para:**
- Desarrollo de software y debugging
- Análisis de datos y visualización
- Escritura profesional y técnica
- Flujos agénticos con Claude Code
- Aplicaciones de producción (SaaS, herramientas dev)
- Procesamiento de documentos largos

**Contexto:** 1M tokens (con prompt caching que reduce costos hasta 90%).

**La regla de oro:** empieza con Sonnet. Si el output no es suficiente, prueba Opus. Si es demasiado, baja a Haiku.

---

### Opus 4.6 / 4.7 — El cerebro pesado

Opus es el modelo flagship de Anthropic. Tiene los scores más altos en benchmarks de coding (80.8% SWE-bench), razonamiento científico (91.3% GPQA Diamond) y computer use (38.1% OSWorld). Es el modelo al que recurres cuando la calidad es la única métrica que importa.

**Ideal para:**
- Refactoring de arquitecturas de código complejas
- Razonamiento científico y matemático avanzado
- Decisiones de diseño de sistemas con múltiples trade-offs
- Análisis de papers de investigación en profundidad
- Tareas agénticas complejas (multi-archivo, multi-herramienta)
- Problemas donde un error de razonamiento tiene alto costo

**Contexto:** 1M tokens, hasta 128K tokens de output.

**Cuándo NO usarlo:** tareas rutinarias donde Sonnet da el mismo resultado — estarías pagando 5x más por la misma calidad.

---

## Framework de Decisión

```
¿La tarea es simple, repetitiva o de clasificación?
  → Sí → HAIKU
  → No ↓

¿Necesito máxima profundidad de razonamiento?
  → Sí → OPUS
  → No ↓

Para todo lo demás → SONNET
```

### Decisión por caso de uso específico

| Caso de uso | Modelo recomendado | Por qué |
|-------------|-------------------|---------|
| Chatbot de soporte | Haiku | Volumen alto, respuestas rápidas, costo bajo |
| Clasificar 10K emails | Haiku | Tarea repetitiva de clasificación |
| Escribir un reporte técnico | Sonnet | Balance calidad-costo, output largo |
| Generar una app React | Sonnet | Coding fuerte, iteración rápida |
| Pipeline de datos diario | Sonnet | Producción estable, costo razonable |
| Debugging de un error complejo multi-archivo | Opus | Razonamiento profundo cross-module |
| Revisar un paper de arXiv en profundidad | Opus | Comprensión científica, contexto largo |
| Diseñar arquitectura de microservicios | Opus | Múltiples trade-offs, decisiones de diseño |
| Resumir documentos cortos en batch | Haiku | Velocidad + volumen |
| Análisis EDA de un dataset | Sonnet | Código + visualización + interpretación |

### Smart Model Switching

En Claude Code y la API, existe "smart model switching" que rutea automáticamente cada request al modelo óptimo: Haiku para tareas rutinarias, Sonnet como default, y Opus cuando la complejidad lo requiere. Esta es la configuración recomendada para producción.

## Ventaja competitiva para Data Scientists / Devs IA

- **Optimización de costos**: los desarrolladores con mejor economía en IA en 2026 no son los que usan el modelo más potente — son los que usan el modelo mínimo que produce output aceptable para cada tarea específica.
- **Escalamiento inteligente**: usa Haiku para preprocesar y clasificar datos en batch ($1/M tokens), Sonnet para análisis y generación de código ($3/M tokens), y Opus solo para las decisiones de arquitectura que realmente lo necesitan ($5/M tokens).
- **Prototipo → Producción**: prototipa con Opus para garantizar calidad, luego baja a Sonnet para producción una vez que validaste que el output es equivalente — puedes reducir costos 40% sin perder calidad medible.
- **Pipeline mixto**: en un pipeline de ML, Haiku puede hacer feature extraction, Sonnet puede generar y evaluar modelos, y Opus puede revisar la arquitectura final. Cada etapa usa el modelo que maximiza valor por dólar.

---

[← Qué es Claude](15-que-es-claude.md) | [Siguiente: Prompts Efectivos →](17-prompts-efectivos.md)
