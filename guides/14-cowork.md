# 17 — Claude Cowork: Tu Agente de IA Personal

## ¿Qué es?

Claude Cowork es una herramienta de escritorio que actúa como un agente personal para usuarios no-técnicos (y también técnicos). Permite automatizar la gestión de archivos, organización de tareas y flujos de trabajo directamente desde tu computadora, sin necesidad de programar ni usar la terminal.

## ¿Cómo se activa?

1. Descarga Cowork desde la página de productos de Anthropic.
2. Instálalo como aplicación de escritorio.
3. Cowork tiene acceso a tus archivos locales y puede interactuar con tu sistema de archivos.
4. Interactúas con él mediante lenguaje natural para delegar tareas.

## ¿Cómo funciona?

- Cowork opera como un agente que puede leer, crear, mover, renombrar y organizar archivos en tu computadora.
- Entiende instrucciones en lenguaje natural y las traduce en acciones concretas sobre tu sistema de archivos.
- Puede procesar lotes de archivos: renombrar masivamente, reorganizar carpetas, extraer información de documentos.
- Combina las capacidades de razonamiento de Claude con acceso a tu entorno local.

## ¿Para qué se utiliza?

- Organizar carpetas de proyectos automáticamente.
- Renombrar lotes de archivos según convenciones.
- Extraer y consolidar información de múltiples documentos.
- Crear estructuras de proyecto desde cero.
- Automatizar tareas repetitivas de gestión de archivos.
- Procesar y transformar documentos en lote.

## Ventaja competitiva para Data Scientists / Devs IA

- **Organización de experimentos**: pide a Cowork que organice tus carpetas de experimentos por fecha, modelo y dataset, renombrando archivos de resultados con convenciones consistentes.
- **Gestión de datasets**: automatiza la clasificación, renombrado y movimiento de archivos de datos entre carpetas de raw, processed y features.
- **Limpieza de workspace**: después de semanas de experimentación, Cowork puede reorganizar tu directorio de trabajo, archivar experimentos antiguos y generar un índice de resultados.
- **Preparación de entregas**: consolida resultados de múltiples experimentos en una estructura limpia para compartir con el equipo o para publicación.
- **Accesibilidad**: para miembros del equipo menos técnicos (product managers, analistas de negocio), Cowork democratiza la automatización sin requerir conocimientos de programación.

## Ejemplo rápido

```
Instrucción a Cowork: "En mi carpeta /experiments/, tengo 50 subcarpetas 
de experimentos. Cada una tiene archivos de resultados (metrics.json), 
configuración (config.yaml) y logs. Quiero que:
1. Leas el accuracy de cada metrics.json
2. Crees una carpeta /best_experiments/ con los 10 mejores por accuracy
3. Generes un resumen.csv con columnas: experiment_name, accuracy, model_type, date
4. Archiva las carpetas con accuracy menor a 0.7 en /archive/"
```

---

[← Claude Code](13-claude-code.md) | [Volver al índice →](../README.md)
