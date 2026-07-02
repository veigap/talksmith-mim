# Cómo se resolvería la misión "Atlas" en OpenAI Codex

> Mapeo concepto por concepto de **la misión** (los Milestones 1–4 de `mission.md`, resueltos en Claude Cowork) a su **equivalente en OpenAI Codex**. No es una comparación genérica de productos: recorre solo las piezas que la misión realmente usa. Datos de Codex verificados contra la documentación oficial de OpenAI (junio 2026).

## Tabla comparativa (concepto de la misión → Codex)

| # | Concepto usado en la misión | En Cowork (como se hace en la misión) | Equivalente en Codex | ¿Mapeo? |
|---|---|---|---|---|
| 1 | **Project** (cuartel de Atlas) | "Projects" en la GUI, apuntado a `Documentos/Atlas-Mercado` | Project en la app de Codex, ligado a una carpeta/repo en disco | ✅ Directo |
| 2 | **Instructions** (contrato de Atlas: empresas, tono, regla de oro "no es asesoramiento") | Campo "Instrucciones" del proyecto (GUI, sin archivo) | Archivo **`AGENTS.md`** en la raíz de la carpeta (texto, commiteable) | ✅ Directo (vía archivo) |
| 3 | **Skill `reporte-semanal`** (raw → reporte) | `/skill-creator` → `SKILL.md` | `$skill-creator` → `SKILL.md` (**mismo estándar**) en `.agents/skills/` | ✅ Casi 1:1 |
| 4 | **Búsqueda web** (precios/noticias de Yahoo Finance) | Activada en Settings → Capacidades; `web_fetch` directo | Web search tool; `web_search = "live"` en `config.toml` o flag `--search` | ✅ Directo (vía config) |
| 5 | **Navegador** (páginas con JS) | Claude in Chrome | Navegador integrado / extensión Chrome / Computer Use | ✅ Directo |
| 6 | **Connector MT Newswires** (datos de mercado) | Directorio de Connectors → botón "Connect", listo de fábrica | **MCP server** en `config.toml` / `codex mcp` | ⚠️ Mismo concepto, sin directorio de un clic |
| 7 | **Skill `buscar-accion`** (ticker+semana → guarda `fuentes/`) | `/skill-creator` → `SKILL.md` | `$skill-creator` → `SKILL.md` | ✅ Casi 1:1 |
| 8 | **Connector Gmail** (distribuir el reporte) | Connector oficial de un clic; deja **borrador** | **MCP server de Gmail** (oficial o comunidad), autorizado una vez | ⚠️ Mismo concepto, más setup |
| 9 | **Schedule** (lunes 8:00, recurrente) | Pestaña "Scheduled" / `/schedule` | **Automations** (cron, local/worktree, bandeja "Triage") | ✅ Equivalente fuerte |
| 10 | **Skill `publicar-tablero`** (genera el HTML del tablero) | `/skill-creator` → `SKILL.md` | `$skill-creator` → `SKILL.md` | ✅ Casi 1:1 |
| 11 | **Live Artifact `pulso-semanal`** (tablero auto-actualizable) | `create_artifact` / `update_artifact` — objeto vivo en Cowork | **Sin equivalente directo:** HTML real en disco, regenerado por la Skill | ❌ La mayor brecha |
| 12 | **ShareDuo** (URL pública del tablero) | `update_artifact_settings(share="duo")` — sharing integrado, nada que instalar | **Codex Sites** o cualquier hosting estático (Pages, Vercel) | ⚠️ Hay que publicar/hostear aparte |
| 13 | **Memoria del proyecto** | Auto memory por proyecto (`/memory`) | Memories (`~/.codex/memories/`) + el propio `AGENTS.md` | ✅ Directo |

**Leyenda:** ✅ mapeo limpio · ⚠️ mismo concepto, distinta plomería (más setup) · ❌ sin equivalente directo.

---

## Análisis por milestone

**Milestone 1 — Atlas nace (Project · Instructions · Skill).** Es el milestone que mejor traslada. El Project existe en ambos; las Instructions de Cowork pasan a ser un archivo `AGENTS.md` de texto que Codex lee en cada sesión dentro de la carpeta (con la ventaja de que se puede commitear y compartir con el equipo). La Skill `reporte-semanal` es prácticamente idéntica: Codex adoptó el **mismo estándar `SKILL.md`** y tiene su propio creador asistido (`$skill-creator`). Única fricción: en Cowork todo es GUI; en Codex tocás un archivo.

**Milestone 2 — Atlas investiga (búsqueda web · Connector · navegador).** La búsqueda web y el navegador trasladan bien, con la salvedad de que Codex viene por defecto en modo "cached" y hay que activar `web_search = "live"` para datos frescos. El punto de fricción real es **MT Newswires**: en Cowork tiene un connector listo en el directorio con botón "Connect"; en Codex no hay directorio equivalente — se conecta como **MCP server** editando `config.toml` o con `codex mcp`. Si el proveedor expone un endpoint MCP, se pega y listo; si no, se usa un MCP genérico de noticias o solo búsqueda web. El concepto ("enchufo un servicio sin programarlo") es el mismo; la plomería pide más manos.

**Milestone 3 — Atlas trabaja solo (Gmail · Schedule).** Gmail repite el patrón de MT Newswires: en Cowork es un connector de un clic que deja un **borrador**; en Codex es un MCP server de Gmail que se autoriza una vez. El Schedule mapea fuerte a **Automations**, que incluso suma cron custom, modo local vs. worktree y la bandeja "Triage". El caveat operativo es idéntico en ambos: las tareas con scope local necesitan la app abierta y la carpeta en disco (Codex está extendiendo esto a la nube, pero hoy, para un caso que escribe archivos y manda mail, conviene tener la app corriendo). Recordá dejar el sandbox de Codex en `workspace-write`, no read-only, o la automation falla al escribir.

**Milestone 4 — Atlas llega al equipo (Live Artifact · ShareDuo).** Acá está **la mayor brecha de todo el mapeo**. La Skill `publicar-tablero` traslada sin problema (genera el HTML). Pero Cowork tiene **Live Artifacts**: un objeto gestionado, vivo, que se refresca en su panel y se publica con **ShareDuo** (`share="duo"`) sin instalar nada. Codex **no tiene equivalente directo**: genera el HTML real en disco, lo previsualizás en su navegador integrado y, si querés URL para el equipo, lo publicás aparte con **Codex Sites** o un hosting estático. La "vida" del tablero no la da un objeto vivo sino la Skill que **regenera el archivo** cada lunes desde la automation. A favor de Codex: el resultado es un artefacto portable y desplegable de verdad. A favor de Cowork: cero fricción de publicación y sharing integrado.

---

## Las cuatro diferencias que conviene nombrar

1. **Público y superficie.** Cowork es una app para no-técnicos (todo botones y prompts). Codex es un agente de **programación** que vive en app/IDE/CLI; su app de escritorio acerca mucho la experiencia, pero quedan archivos de por medio (`AGENTS.md`, `config.toml`).
2. **Skills:** el mapeo más limpio — mismo estándar `SKILL.md`, mismo creador asistido. Las tres Skills de la misión (`reporte-semanal`, `buscar-accion`, `publicar-tablero`) se escriben casi igual.
3. **Connectors → MCP:** mismo concepto, distinta plomería. Cowork tiene directorio con "Connect"; Codex usa MCP servers en `config.toml`/`codex mcp`. Más flexible, un poco más de setup (afecta a MT Newswires y a Gmail).
4. **Live Artifacts → (sin equivalente directo):** la brecha grande. Codex genera HTML real que publicás con Sites/hosting; la "vida" la da la Skill que lo regenera, no un objeto gestionado.

**Veredicto:** el mapeo es ~10/13 conceptos directos o cercanos. Codex puede resolver la misma misión de punta a punta — mismo circuito `Automation → buscar-accion → reporte-semanal → Gmail → tablero` — pero pide más setup por archivo/terminal y pierde la magia del tablero vivo de un clic. Para un perfil no técnico, Cowork es más liso; para quien quiere un artefacto desplegable y control por archivos, Codex es más potente.

---

## Fuentes

- AGENTS.md — https://developers.openai.com/codex/guides/agents-md
- Agent Skills — https://developers.openai.com/codex/skills
- MCP — https://developers.openai.com/codex/mcp
- Sandbox / permisos — https://developers.openai.com/codex/concepts/sandboxing · https://developers.openai.com/codex/permissions
- Automations — https://developers.openai.com/codex/app/automations
- Navegador in-app — https://developers.openai.com/codex/app/browser
- Sites — https://developers.openai.com/codex/sites
- Web (cloud) — https://developers.openai.com/codex/cloud
- Memories — https://developers.openai.com/codex/memories
