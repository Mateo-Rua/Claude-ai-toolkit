# 16 — Cómo Funciona Claude Code como Agente

## ¿Qué es?

Claude Code es una herramienta de línea de comandos (CLI) que permite delegar tareas de codificación completas a Claude directamente desde tu terminal. No es un autocompletado — es un agente que puede navegar tu codebase, entender la arquitectura, editar múltiples archivos, ejecutar comandos, correr tests y hacer commits, todo de forma autónoma.

## ¿Cómo se activa?

1. Instala Claude Code via npm: `npm install -g @anthropic-ai/claude-code`
2. Requiere Node.js 18+ instalado.
3. Autentícate con tu cuenta de Anthropic.
4. Ejecuta `claude` en la raíz de tu proyecto para iniciar una sesión interactiva.
5. También puedes usarlo como extensión en VS Code o JetBrains.

## ¿Cómo funciona?

- Claude Code tiene acceso completo a tu sistema de archivos local (con tu permiso).
- Lee y entiende tu codebase: estructura de carpetas, dependencias, configuraciones, patrones de código.
- Puede ejecutar comandos de terminal: instalar paquetes, correr tests, ejecutar scripts, hacer git operations.
- Trabaja de forma agéntica: planifica la tarea, la ejecuta paso a paso, verifica resultados, y corrige errores automáticamente.
- Soporta integración con servidores MCP para extender sus capacidades.

## ¿Para qué se utiliza?

- Implementar features completas que involucren múltiples archivos.
- Refactorizar código existente a gran escala.
- Depurar errores complejos que cruzan varios módulos.
- Crear tests unitarios y de integración.
- Migrar entre frameworks, versiones o lenguajes.
- Automatizar tareas de DevOps y configuración.
- Documentar código existente.

## Ventaja competitiva para Data Scientists / Devs IA

- **Refactoring de pipelines**: pide a Claude Code que refactorice tu pipeline monolítico de pandas en módulos reutilizables con logging, error handling y type hints — lo hace editando todos los archivos necesarios.
- **Testing automático**: genera suites completas de tests para tu código de ML (tests unitarios para transformaciones de features, tests de integración para el pipeline, tests de regresión para predicciones).
- **Migración eficiente**: migra tu proyecto de TensorFlow a PyTorch, de notebooks a scripts modulares, o de configuración manual a Hydra/YAML — Claude Code entiende ambos mundos.
- **DevOps para ML**: configura CI/CD, Dockerfiles, GitHub Actions para tu pipeline de ML — Claude Code crea y valida toda la configuración.
- **Debug profundo**: cuando un modelo falla en producción, Claude Code puede rastrear el error a través de todo el stack (preprocessing → feature engineering → model → postprocessing) y proponer la corrección.

## Ejemplo rápido

```bash
# En la terminal, dentro de tu proyecto
$ claude

> "Revisa mi pipeline de datos en src/pipeline/. Quiero que:
   1. Agregues type hints a todas las funciones
   2. Implementes logging con loguru en cada etapa
   3. Agregues manejo de errores con mensajes descriptivos
   4. Crees tests unitarios para cada módulo en tests/
   5. Actualices el README con la nueva estructura"

# Claude Code leerá tu código, editará múltiples archivos, 
# creará los tests, los ejecutará para verificar que pasan,
# y actualizará la documentación.
```

---

[← Skills Personalizadas](12-custom-skills.md) | [Siguiente: Claude Cowork →](14-cowork.md)
