# 07 — Artefactos de Claude: Crea Apps Web con IA

## ¿Qué es?

Los artefactos (Artifacts) son piezas de contenido interactivo que Claude genera y renderiza directamente en la conversación. Pueden ser aplicaciones web funcionales en React, visualizaciones de datos, dashboards, juegos, calculadoras, componentes UI, diagramas SVG, y más — todo ejecutable en el navegador sin necesidad de un servidor.

## ¿Cómo se activa?

1. En Claude.ai, los artefactos se generan automáticamente cuando pides algo que se beneficia de una interfaz visual o interactiva.
2. Claude detecta la necesidad y crea un componente React (.jsx), HTML, SVG o Mermaid que se renderiza en un panel lateral.
3. Puedes iterar sobre el artefacto pidiendo cambios, y Claude lo actualiza en tiempo real.

## ¿Cómo funciona?

- Claude escribe código frontend completo (React con hooks, HTML/CSS/JS, SVG).
- El código se ejecuta en un sandbox seguro dentro de la interfaz de Claude.
- Tiene acceso a librerías como Recharts, D3, Three.js, TensorFlow.js, Lodash, Papa Parse, SheetJS, entre otras.
- Los artefactos pueden usar Tailwind CSS para estilos y componentes de shadcn/ui.
- Se pueden crear aplicaciones con estado usando useState/useReducer.

## ¿Para qué se utiliza?

- Dashboards interactivos para explorar datos.
- Calculadoras y herramientas especializadas.
- Prototipos de UI/UX funcionales.
- Visualizaciones de datos con gráficos interactivos.
- Juegos y simulaciones educativas.
- Formularios y flujos de trabajo.
- Componentes React reutilizables.

## Ventaja competitiva para Data Scientists / Devs IA

- **Visualización instantánea**: pide un dashboard interactivo de tus métricas de modelo y obtenlo funcional en segundos, sin configurar un entorno de desarrollo.
- **Prototipado frontend**: genera interfaces completas para demos de ML (input → predicción → resultado) sin escribir frontend manualmente.
- **Herramientas a medida**: crea calculadoras de tamaño de muestra, simuladores de distribuciones, o exploradores de hiperparámetros como artefactos interactivos.
- **Componentes reutilizables**: genera componentes React que puedes copiar directamente a tu proyecto.

## Ejemplo rápido

```
Prompt: "Crea un dashboard interactivo en React que muestre: un selector de dataset 
(iris, wine, breast cancer), un scatter plot 2D con los datos coloreados por clase, 
sliders para seleccionar qué features usar en los ejes X e Y, y una tabla con las 
estadísticas descriptivas del dataset seleccionado."
```

Claude generará un artefacto React funcional con gráficos Recharts, controles interactivos y datos precargados, todo ejecutable directamente en el chat.

---

[← PowerPoint](06-powerpoint.md) | [Siguiente: Proyectos →](08-projects.md)
