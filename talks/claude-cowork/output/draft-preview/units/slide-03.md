## Las tres superficies de Claude

- Mismos modelos, distinta superficie: las tres caras — **Web/Chat**, **Claude Code** y **Cowork** — corren sobre **los mismos modelos Claude**. El matiz importa: **Cowork está construido sobre las mismas bases que Claude Code** (el **Claude Agent SDK**), así que Code y Cowork comparten el mismo *engine de agente* — los mismos archivos, las mismas Skills, el mismo MCP y el mismo loop de plan → aprobar → redirigir. **Web/Chat** es ese mismo modelo en una **superficie de chat**, no el loop agéntico completo.
- **Web/Chat** — navegador o app, sin instalar; chat, preguntas y tareas puntuales; público: todos.
- **Claude Code** — app de escritorio (pestaña Code + terminal); escribir, editar y publicar código; público: perfiles técnicos / developers.
- **Cowork** — app de escritorio (pestaña Cowork), GUI sin terminal; trabajo de varios pasos sobre archivos reales; público: knowledge workers sin terminal. **Esta charla vive acá.**

```ascii
+----------------+   +----------------+   +----------------+
|   Web / Chat   |   |  Claude Code   |   |     Cowork     |
| superficie de  |   | terminal+Code  |   |  GUI, escritorio|
|   chat         |   | escribir codigo|   | trabajo multipaso|
+----------------+   +----------------+   +----------------+
        |              \________  ________/
        |                  Agent SDK (engine de agente)
        |                  archivos / Skills / MCP / loop
        \________________   |   ________________/
                         \  |  /
                  +--------------------+
                  | MISMOS MODELOS     |
                  |     CLAUDE         |
                  +--------------------+
```

### Notes

Abrir ubicando el terreno: no son tres productos distintos, es el mismo agente con tres caras. Lo único que cambia es la superficie y para quién está pensada. Dejar claro desde el minuto cero que hoy trabajamos en Cowork — la cara pensada para quien no vive en una terminal. Claude Code aparece solo como contraste; no vamos a entrar en sus internals. Tiempo objetivo: ~5 min.
