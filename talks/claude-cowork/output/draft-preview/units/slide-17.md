## Connectors y MCP: las "manos" del agente

- **Qué son los Connectors.** Son lo que le permite al agente tocar sistemas externos que de otro modo no podría: Drive, Gmail, Slack, bases de datos, APIs. "Las manos: lo que el agente puede tocar que de otro modo no podría."
- **Qué es MCP (Model Context Protocol).** El estándar detrás de los Connectors: una forma estandarizada de conectar Claude con sistemas externos. Cualquier app que exponga un servidor MCP se vuelve algo con lo que podés "hablar" (Figma, Vercel, Cal.com, Home Assistant…). El patrón: la plataforma abre sus internals como herramientas MCP; el agente no gana una capacidad nueva, la plataforma se vuelve conversacional.
- En la próxima slide vemos **cómo se registra un Connector** en la práctica (directorio + un clic).

```ascii
+--------+   pide datos    +-----------+   protocolo   +--------------+
| Cowork | --------------> | Connector |  -- MCP -->   | Servicio ext |
| (agente)|                |  (1 clic) |               | Gmail/MT News|
+--------+ <-------------- +-----------+ <-----------  +--------------+
            devuelve datos
```

### Notes

Desarmar el miedo: conectar un servicio externo no es programar. En Cowork es literalmente buscar el servicio en el directorio y darle Connect — como conectás Gmail. Usar el diagrama para explicar qué pasa por debajo: el agente pide datos, el Connector los trae vía el protocolo MCP. MCP es el estándar que hace que cualquier plataforma con API pueda volverse conversacional. Ejemplo de la misión: MT Newswires (noticias de mercado) y Gmail, ambos de un clic. Aclarar que en Cowork no hay archivo de config: todo por la UI. Tiempo objetivo: ~10 min.
