# 14 — Conectores MCP: Integra Claude con tus Aplicaciones

## ¿Qué es?

MCP (Model Context Protocol) es un protocolo abierto que permite a Claude conectarse directamente con aplicaciones y servicios externos: GitHub, Slack, Google Drive, Jira, bases de datos, APIs internas, y más. Los conectores MCP actúan como puentes que le dan a Claude acceso a tus herramientas reales de trabajo.

## ¿Cómo se activa?

1. En Claude.ai, ve al menú de herramientas (ícono de enchufe/integrations) en la conversación.
2. Explora los conectores disponibles o busca por nombre.
3. Haz clic en "Connect" y autoriza el acceso a tu cuenta del servicio.
4. Una vez conectado, Claude puede usar las herramientas del conector directamente en la conversación.

## ¿Cómo funciona?

- MCP define un protocolo estándar para que los servicios expongan "herramientas" a Claude (lectura, escritura, búsqueda, acciones).
- Cuando conectas un servicio, Claude puede invocar sus herramientas como parte de su razonamiento.
- La autenticación se gestiona con OAuth — tú autorizas una vez y Claude opera dentro de esos permisos.
- Claude decide cuándo y cómo usar cada herramienta según tu solicitud.
- Puedes tener múltiples conectores activos simultáneamente.

## ¿Para qué se utiliza?

- Buscar y leer archivos de Google Drive sin salir de Claude.
- Crear issues, revisar PRs o buscar código en GitHub/GitLab.
- Enviar mensajes o buscar conversaciones en Slack.
- Gestionar tareas en Jira, Asana o Linear.
- Consultar datos de bases de datos conectadas.
- Automatizar flujos que involucren múltiples herramientas.

## Ventaja competitiva para Data Scientists / Devs IA

- **Flujo de trabajo unificado**: consulta tu documentación en Notion, revisa un PR en GitHub y actualiza un ticket en Jira — todo desde la misma conversación con Claude.
- **Acceso a datos reales**: conecta tus repositorios para que Claude analice tu código real, no código genérico. Puede buscar en tu codebase, entender tu arquitectura y sugerir mejoras contextualizadas.
- **Automatización cross-tool**: pide a Claude que lea un reporte de Google Drive, identifique action items, y cree tickets en Jira automáticamente.
- **MCP personalizado**: al ser un protocolo abierto, puedes crear tus propios servidores MCP para exponer APIs internas, bases de datos de features o pipelines de ML directamente a Claude.

## Ejemplo rápido

```
[Con conectores de GitHub y Slack activos]

Prompt: "Revisa los últimos 5 PRs abiertos en el repo 'ml-pipeline'. 
Para cada uno, dime el autor, cuántos archivos cambia, y si modifica 
algún archivo en la carpeta /models/. Luego envía un resumen al canal 
#ml-team en Slack."
```

Claude consultará la API de GitHub, analizará los PRs, y enviará el resumen formateado directamente a Slack.

---

[← Memoria](10-memory.md) | [Siguiente: Skills Personalizadas →](12-custom-skills.md)
