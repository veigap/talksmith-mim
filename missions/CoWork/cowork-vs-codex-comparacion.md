# Claude Cowork vs OpenAI Codex — comparación por concepto

> Comparación de los conceptos del deck (`final.md`), dejando **explícitamente fuera Claude Code** aunque aparezca en el material. Datos de Codex verificados contra la documentación oficial de OpenAI (junio 2026).

## Diferencia de fondo (arquitectura)

- **Claude Cowork:** corre **solo local**, sobre los archivos reales de la carpeta que le concediste en tu computadora. GUI, sin terminal.
- **OpenAI Codex:** es **híbrido**, unificado por tu cuenta de ChatGPT — corre **local** (CLI/IDE/app de escritorio, con sandbox en tu máquina) **o en la nube** (contenedores aislados gestionados por OpenAI para tareas asíncronas), y movés el trabajo entre ambos sin perder contexto. Nació como herramienta de devs y está pivoteando hacia knowledge workers (≈5M usuarios semanales; ~20% no-devs).

## Tabla comparativa

| Concepto (definición) | Claude Cowork | OpenAI Codex |
|---|---|---|
| **Instrucciones persistentes** — archivo/contexto que fija el comportamiento del agente en cada sesión | Panel de contexto del proyecto (GUI), sin archivo `.md` editable | `AGENTS.md` (texto en el repo); jerarquía root→subdirectorio + `AGENTS.override.md`; aplican antes de empezar; las reglas de equipo van acá |
| **Memoria automática** — notas que el agente guarda solo entre sesiones | Auto memory por proyecto, editable, vía `/memory` | "Memories" (opt-in) en `~/.codex/memories/`; recall local que se actualiza en background y redacta secretos; las reglas obligatorias van en `AGENTS.md` |
| **Working directory + permisos** — a qué archivos accede y bajo qué límites | Selector de carpetas del **SO**; trabajo local; lee uploads / escribe outputs | **Local:** sandbox a nivel SO (Seatbelt / bubblewrap / Landlock); modo default `workspace-write` (sin red, write limitado al workspace); *permission profiles* (filesystem + red). **Cloud:** contenedor aislado, sin internet salvo lo que habilites |
| **Loop agéntico + aprobación** — cómo planifica/actúa y cuándo pausa a consultarte | Interruptor de dos posiciones (Ask before acting / Act without asking); siempre pregunta antes de borrar o usar app nueva | Presets de aprobación (Read-Only / Auto / Full Access) en el selector bajo el composer; en Auto pide aprobación para editar fuera del workspace o usar red; acciones destructivas siempre requieren aprobación |
| **Skills** — flujo reutilizable empaquetado | User-level + dentro de plugins; no escanea skills de proyecto; se gestionan en Settings | Agent Skills con el **mismo formato** (`SKILL.md` + progressive disclosure); personales en `$HOME/.agents/skills`, de equipo en `.agents/skills` del repo; catálogo público `openai/skills` |
| **Subagentes** — especialistas aislados a los que se delega en paralelo | Coordinados por debajo, sin configuración expuesta en la GUI | Custom agents en **TOML** (`~/.codex/agents/` global, `.codex/agents/` proyecto); delegación **explícita** (no auto-spawn); anidamiento `max_depth=1`; corren en paralelo y juntan resultados |
| **Conectores (MCP)** — conexión estándar a sistemas externos | Conectores vía Settings (GUI) | MCP configurado en `~/.codex/config.toml` o con `codex mcp` (CLI e IDE comparten config); en ChatGPT los "connectors" se renombraron **"apps"** (dic 2025) |
| **Plugins** — empaquetar un flujo entero (skills + agents + hooks + MCP) en una instalación | Marketplace GUI; instala a tu cuenta | **Sin "plugin bundle" unificado**; se compone por separado (skills + MCP + `AGENTS.md` + agents TOML); el catálogo `openai/skills` cumple el rol de repositorio compartido |
| **Artifacts** — outputs renderizados / compartibles | **Standard + Live Artifacts:** apps web interactivas, AI-powered, con `window.storage` y conexiones MCP; dashboards que se refrescan al abrir | **Artifact Viewer** (desde abr 2026): previsualiza outputs **no-código** (PDF, planillas, docs, slides) sin salir de la app + task sidebar con plan/fuentes/artefactos. Es **preview de archivos generados**, no apps web vivas/interactivas |
| **Tareas programadas** — trabajo recurrente que corre solo | Pestaña Scheduled / `/schedule`; cada corrida abre sesión fresca; **caveat: solo con la compu despierta y la app abierta** | Automations: elegís proyecto, prompt, **cadencia (cron)** y entorno; thread vs standalone; corre en checkout local o worktree de fondo; resultados en **review queue / Triage**; triggers cloud anunciados (correr sin la app abierta) |
| **Orquestación a escala / workflows** — coordinar muchos agentes en una tarea grande | **No disponible** en Cowork (es capacidad de Claude Code) | La Codex app orquesta **múltiples agentes en paralelo** (worktrees + entornos cloud); cloud tasks asíncronas que abren PRs; subagents para paralelismo |
| **Gobernanza y verificación** — controles para uso laboral (datos, auditoría, revisión) | Sin audit trail; cada output es un borrador; guardrails apilables; **todo local** | Review queue / Triage de diffs y artefactos; sandbox + permission profiles; cloud en contenedores aislados — **el código/datos pueden subir a infraestructura de OpenAI** (a sopesar con material sensible/regulado) |

## Caveats

- Los features de Codex se mueven rápido. Hitos verificados: app de escritorio en macOS (feb 2026) y Windows (mar 2026); Artifact Viewer + task sidebar (Platform 26.415, abr 2026); CLI v0.136.0 (jun 2026). Conviene re-verificar contra la doc oficial antes de presentar.
- "Artifacts" significa cosas distintas en cada producto: en Claude son apps web vivas e interactivas; en Codex es un visor de previsualización de archivos generados.

## Fuentes

- Custom instructions with AGENTS.md — https://developers.openai.com/codex/guides/agents-md
- Memories — https://developers.openai.com/codex/memories
- Sandbox — https://developers.openai.com/codex/concepts/sandboxing
- Agent approvals & security — https://developers.openai.com/codex/agent-approvals-security
- Permissions — https://developers.openai.com/codex/permissions
- Agent Skills — https://developers.openai.com/codex/skills
- Subagents — https://developers.openai.com/codex/subagents
- Model Context Protocol — https://developers.openai.com/codex/mcp
- Automations (Codex app) — https://developers.openai.com/codex/app/automations
- Features (Codex app) — https://developers.openai.com/codex/app/features
- Web (cloud) — https://developers.openai.com/codex/cloud
- CLI — https://developers.openai.com/codex/cli
- Introducing upgrades to Codex — https://openai.com/index/introducing-upgrades-to-codex/
- Codex App Workspace: PR Review, Task Sidebar, Artifact Viewer — https://codex.danielvaughan.com/2026/04/17/codex-app-workspace-pr-review-task-sidebar-artifact-viewer/
- OpenAI's Codex is the new office productivity booster (Axios) — https://www.axios.com/2026/06/02/openai-codex-knowledge-workers
