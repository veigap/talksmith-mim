---
source_file: https://code.claude.com/docs/en/desktop
source_type: web-capture
ingested_at: 2026-08-03
---

# Claude Code — Desktop application (docs oficiales)

## Provenance
- Original location: fetch web directo durante Step 5 (Review), sin captura en research/web/
- Format: html
- Author / source (if known): Anthropic — documentación de Claude Code
- Date of original (if known): vigente al 2026-08-03

## Key claims
- La app de escritorio tiene tres pestañas: Chat, Cowork y Code; la pestaña Code ofrece "visual diff review, app previews, PR monitoring" e "integrated terminal and file editor".
- Paneles reorganizables: "The Code tab is built around panes you can arrange in any layout: chat, diff, browser, terminal, file, plan, tasks, and subagent."
- Modos de permiso: **Manual** ("Claude asks before editing files or running commands. You see a diff and can accept or reject each change"), **Plan** ("Claude reads files and runs commands to explore, then proposes a plan without editing your source code. Good for complex tasks where you want to review the approach first"), Accept edits, Auto y Bypass.
- Diff view: "After Claude makes changes to your code, the diff view lets you review modifications file by file"; "To comment on specific lines, click any line in the diff to open a comment box"; "Claude reads your comments and makes the requested changes, which appear as a new diff you can review."
- Review code: botón que pide a Claude evaluar los cambios y dejar comentarios en el diff.
- Preview: "Claude can start a dev server and open it in the Browser pane to verify its changes"; funciona para frontends y backends.

## Definitions and terminology
- **Plan mode:** modo en que Claude explora y propone un plan sin editar código fuente.
- **Diff view:** vista de cambios archivo por archivo, con comentarios por línea.

## Evidence and examples
- Flujo recomendado: "explore first, then plan, then code" — empezar tareas complejas en Plan y ejecutar tras aprobar.

## Inconsistencies / open questions
- Ninguna detectada. Confirma los claims de interfaz usados en las notas de la sección Claude Code (paneles de plan, diff, archivos, terminal y vista previa; comentarios sobre el diff).

## Images / diagrams
- Ninguna imagen capturada.

## Raw / preserved excerpts

> "The Code tab is built around panes you can arrange in any layout: chat, diff, browser, terminal, file, plan, tasks, and subagent."

> "Plan — Claude reads files and runs commands to explore, then proposes a plan without editing your source code."

> "To comment on specific lines, click any line in the diff to open a comment box. [...] Claude reads your comments and makes the requested changes, which appear as a new diff you can review."
