# 🛰️ Solución paso a paso (versión OpenAI) — "Faro, la mesa de inteligencia de mercado de Atlas"

> Equivalente en el ecosistema de **OpenAI** de la solución descrita en `mission-res.md` (hecha con claude.ai + Claude Cowork). Misma misión de `mission.md`, mismas **2 partes y 6 milestones**, mismo resultado: el email del lunes y el tablero. Lo que cambia es la herramienta: la **Parte 1** se resuelve en **ChatGPT** (el chat que el ecosistema OpenAI ofrece, con búsqueda, conectores y Tasks) y la **Parte 2** en **Codex** (su agente de escritorio).
>
> 💡 Convención: donde veas `[EMPRESAS]`, va `YPF, VIST, TS`; donde veas `[TICKER]`, una sola (ej. `YPF`).
>
> 🎭 El encuadre es idéntico: trabajás en **Atlas** y tu jefe quiere el pulso semanal de YPF, Vista y Tenaris en dos entregas (email + tablero). En el workshop el email va a `superboss@gmail.com`.

---

## ⚠️ Lee esto primero: el mapeo de herramientas

- **Parte 1 (el chat):** claude.ai ↔ **ChatGPT**. Búsqueda web con citas, conectores para leer tus apps, y **Tasks** (las tareas programadas de ChatGPT) para que el pulso llegue solo.
- **Parte 2 (el agente de escritorio):** Claude Cowork ↔ **app de escritorio de Codex**. Tiene las mismas piezas conceptuales, pero algunas se expresan como **archivos y configuración** (`AGENTS.md`, `config.toml`) en lugar de botones.

> 🧠 La buena noticia: Codex adoptó el **mismo estándar de Skills** (`SKILL.md`) que Cowork, así que las Skills del Milestone 6 son prácticamente idénticas.

## 🗺️ Tabla maestra de equivalencias

| Pieza (Claude) | Equivalente (OpenAI) | Cómo se materializa |
|---|---|---|
| claude.ai (chat) | **ChatGPT** | El chat con búsqueda web integrada y citas. |
| Biblioteca de conectores | **Connectors / apps de ChatGPT** | Se conectan Gmail, Calendar, Drive y otros desde la configuración de ChatGPT. |
| Tareas programadas de claude.ai | **Tasks de ChatGPT** | Recurrentes; notifican el resultado (push/email). |
| **Project** de Cowork | **Project** en la app de Codex | Espacio de larga duración ligado a una carpeta en disco. |
| **Instrucciones** del Project | **`AGENTS.md`** | Archivo en la raíz de la carpeta; el "contrato de trabajo" de Codex. |
| **Skills** (`SKILL.md`) | **Skills** (mismo estándar) | Carpeta con `SKILL.md` en `.agents/skills/` (repo) o `~/.agents/skills/` (usuario). |
| `/skill-creator` | **`$skill-creator`** (built-in) | Asistente integrado para crear Skills sin código. |
| Conectores en Cowork | **MCP servers** | `~/.codex/config.toml` bajo `[mcp_servers.<nombre>]`, o `codex mcp`. |
| Búsqueda web | **Web search tool** | `web_search = "live"` en `config.toml` (o `--search`). |
| Claude in Chrome | **Navegador integrado** / extensión de Chrome | Panel de navegador en la app de Codex. |
| **Schedule** de Cowork | **Automations** | Tareas recurrentes (semanal o cron) con bandeja "Triage". |
| **Live Artifacts** | Sin equivalente directo → **HTML regenerado por Skill** + navegador + **Codex Sites** | El tablero es un `tablero.html` real; la "vida" la da la Skill que lo regenera. Sites le da URL. |

---

## 🧰 Antes de empezar (setup)

**Parte 1:** cuenta de **ChatGPT** (plan pago) con búsqueda web; el conector de **Gmail** disponible en tu plan; una cuenta de Gmail.

**Parte 2:**

1. Instalá la **app de escritorio de Codex** (también existen extensión de IDE y CLI: `npm i -g @openai/codex`) e iniciá sesión.
2. Creá la carpeta `Documentos/Faro-Mercado` con una copia de `reportes/` adentro. Tip: `git init` la deja lista para worktrees y Automations prolijas.
3. Activá búsqueda web en vivo en `~/.codex/config.toml`:

```toml
web_search = "live"
```

> 📁 Material de ejemplo: el mismo `reportes/` de la misión (subcarpeta por semana; `fuentes/` + reporte final como "respuesta correcta").
>
> 🧹 **Misión 0:** la carpeta `escritorio-del-pasante/` sirve igual con Codex: concedésela a un Project y recorré los mismos 5 ejercicios de `intro-escritorio-pasante.md` (el ciclo de aprobaciones existe igual; el modo de sandbox de Codex cumple el rol del modo Ask).

---

# 🧩 PARTE 1 — Faro en ChatGPT

# 🔎 Milestone 1 — Faro se conecta

## Paso 1.1 — El pulso con búsqueda web

En ChatGPT (la búsqueda se activa sola cuando hace falta; podés forzarla con el ícono de búsqueda):

> *"Armame el pulso de mercado de esta semana para `[EMPRESAS]`: qué se movió, qué noticias salieron y qué hay que vigilar. Citá las fuentes de cada dato."*

Verificá las **citas inline**: ese es el control de que no respondió de memoria.

## Paso 1.2 — Conectar Gmail

1. Configuración de ChatGPT → **Connectors** → buscá **Gmail** → conectá y autorizá con Google.
2. Probá una lectura: *"¿Qué mails de esta semana quedaron sin responder en mi bandeja?"*

> ⚠️ **Diferencia honesta:** claude.ai tiene a MT Newswires listo en su biblioteca; en ChatGPT el catálogo de conectores es otro. Si tu proveedor de noticias no está, el pulso se arma con búsqueda web sola (alcanza para el ejercicio) o con un conector de datos financieros del catálogo.

> ✅ **🏁 Criterio de éxito (Milestone 1):** el pulso sale con fuentes citadas y el chat puede leer tu Gmail.

# ⚙️ Milestone 2 — Faro trabaja solo

## Paso 2.1 — Programar la Task del lunes

> *"Programá una tarea que corra **cada lunes a las 8:00**: armá el pulso de mercado de `[EMPRESAS]` con búsqueda web y avisame con el resumen completo."*

ChatGPT crea la **Task**; confirmá frecuencia y horario, y verificá que figure en tu lista de Tasks. Activá las **notificaciones por email** para que el resultado llegue al inbox.

> ⚠️ **Diferencia honesta:** la tarea programada de claude.ai puede usar el conector de Gmail para **dejar el borrador dirigido al jefe**. Las Tasks de ChatGPT entregan su resultado como **notificación** (push o email a tu propia casilla); el reenvío al jefe queda como paso manual de un clic. Las Tasks de ChatGPT corren en la nube (no piden computadora prendida), que es la contracara favorable.

> ✅ **🏁 Criterio de éxito (Milestone 2):** la Task figura programada y su corrida de prueba te dejó el pulso en la notificación/email. **Primera entrega del jefe resuelta (con un reenvío).** Fin de la Parte 1.

---

# 🧩 PARTE 2 — Faro en Codex

*Arranca de `reportes/`; no exige la Parte 1.*

# 🛠️ Milestone 3 — Faro toma forma
### *(Project · AGENTS.md · archivos .md)*

## Paso 3.1 — Project + AGENTS.md

1. En la app de Codex, creá un **Project** apuntado a `Documentos/Faro-Mercado`.
2. Pedile: *"creá un `AGENTS.md` en la raíz con este contenido"* y pegá el contrato de Faro (el mismo texto de las Instrucciones de `mission-res.md`, Paso 3.1: quién es Faro, `[EMPRESAS]`, tono, regla de oro del disclaimer, trabajar en Markdown, `reporte-semana-AAAA-MM-DD.md`).

> 📌 `AGENTS.md` es el equivalente exacto de las Instrucciones del Project: Codex lo lee en cada sesión dentro de esa carpeta. Se commitea al repo y el equipo lo comparte.

## Paso 3.2 — La herencia del pasante, a `.md`

> *"Faro, en `reportes/semana-2026-05-25/fuentes/` están las notas en crudo del pasante, un archivo por portal. Convertilas a archivos `.md` prolijos, uno por fuente, sin perder información ni links."*

## Paso 3.3 — El primer reporte, en conversación

El mismo prompt del Paso 3.3 de `mission-res.md`: leer TODAS las fuentes, consolidar por empresa, seguir la estructura del reporte de ejemplo, **sufijo `-new`**.

> ✅ **🏁 Criterio de éxito (Milestone 3):** Project + `AGENTS.md` en pie, y el `reporte-…-new.md` equivalente al de ejemplo.

# ⏰ Milestone 4 — El lunes se arma solo
### *(Web search · MCP · Automations)*

## Paso 4.1 — Las fuentes: web en vivo + MCP

- Confirmá `web_search = "live"`.
- Si tu proveedor de noticias expone MCP, agregalo (`codex mcp`, o en `config.toml`):

```toml
[mcp_servers.mt_newswires]
url = "https://<endpoint-del-proveedor>/mcp"
bearer_token_env_var = "MT_NEWSWIRES_TOKEN"
```

- Para el email: un **MCP server de Gmail** (oficial del proveedor o de la comunidad), autorizado una vez. Verificá todo con `/mcp`.
- Para páginas con JavaScript (Yahoo Finance): el **navegador integrado** de la app.

## Paso 4.2 — Que Faro investigue solo

El mismo prompt del Paso 4.2 de `mission-res.md` (ticker + semana → `fuentes/` con `yahoo-finance.txt` y `mt-newswires.txt` acumulativos, 'n/d' si falta, links reales). Verificá que `fuentes/` se reconstruye desde cero.

## Paso 4.3 — La Automation del lunes

En un thread del Project:

> *"Creá una **automation** que corra **cada lunes a las 8:00**: buscá la info de la semana de `[EMPRESAS]` (Yahoo Finance + el MCP de noticias) y guardá las fuentes; consolidá el reporte de la semana en Markdown con el formato del reporte de ejemplo y guardalo en la carpeta; y dejá el reporte como **borrador en Gmail** dirigido a `superboss@gmail.com` vía el MCP de Gmail, asunto «Pulso semanal de mercado — [fecha]». Automation standalone, semanal."*

Confirmá el schedule (o cron `0 8 * * 1`) y probala **a demanda**; las corridas reportan en **Triage**.

> ⚠️ **Recordá:** las automations con scope de proyecto necesitan **la app de Codex corriendo y la carpeta en disco**, y el sandbox en **workspace-write** (read-only no puede escribir archivos ni usar red).

> ✅ **🏁 Criterio de éxito (Milestone 4):** una corrida completa deja fuentes + reporte + borrador en Gmail.

# 📊 Milestone 5 — El tablero del jefe
### *(HTML + navegador · Codex Sites)*

> 💡 **La diferencia más grande del mapeo, y acá juega a favor de OpenAI:** Cowork tiene Live Artifacts (locales y todavía sin URL compartible); Codex genera un **`tablero.html` real en disco**, lo previsualizás en el navegador integrado y lo **publicás con Codex Sites** (o cualquier hosting estático) con **URL para todo el equipo**. La "vida" la da la regeneración en cada corrida.

## Paso 5.1 — Generar el tablero

> *"Faro, generá un **`tablero.html` autocontenido** (CSS embebido, sin dependencias) con el último reporte, siguiendo el boceto del jefe (`mockup-tablero.png`): encabezado con fecha y resumen, una tarjeta por empresa (ticker, variación en verde/rojo, ánimo, 2-3 noticias con link, a vigilar) y la tabla resumen. Footer: «Reporte interno e informativo; no constituye asesoramiento financiero». Abrilo en el navegador integrado."*

## Paso 5.2 — Publicarlo (opcional pero potente)

> *"Publicá `tablero.html` como un sitio y pasame el link."*

## Paso 5.3 — Engancharlo a la Automation

Editá la automation para que termine: *"…y regenerá `tablero.html` con el reporte nuevo (y republicá el sitio si está publicado)."*

> ✅ **🏁 Criterio de éxito (Milestone 5):** el tablero respeta el boceto, se regenera con la corrida del lunes y, si lo publicaste, el equipo tiene la URL.

# 🧰 Milestone 6 — Faro se vuelve reutilizable
### *(Skills con `$skill-creator`)*

Los mismos tres prompts de `mission-res.md` (Pasos 6.1 a 6.3), con dos diferencias de plomería:

1. El creador se invoca con **`$skill-creator`** (y las Skills con `$reporte-semanal`, `$buscar-accion`, `$publicar-tablero`, o implícitamente por su `description`).
2. **No hay "trampa del Save":** las Skills quedan en `.agents/skills/` del repo (o `~/.agents/skills/` para tenerlas en cualquier carpeta). El gotcha equivalente: si Codex no la encuentra, **reiniciá la app**; y `/skills` lista las disponibles.

Después, editá la Automation del lunes para que use las tres Skills (mismo prompt del Paso 6.4 de `mission-res.md`, con `$`).

> ✅ **🏁 Criterio de éxito (Milestone 6):** la Automation corre sobre las tres Skills y `/skills` las lista; el `SKILL.md` abierto muestra la misma anatomía que enseñó la clase.

> 👀 **Sobre el bonus de subagentes** (Paso 6.6 de `mission-res.md`): Codex también reparte trabajo en paralelo por debajo (threads y worktrees), pero no expone subagentes definibles por el usuario como ejercicio. Acá queda como observación durante la corrida de la Automation, sin paso propio.

---

## 🔄 El círculo completo (versión OpenAI)

`Lunes 8:00` → **Automation** → **`$buscar-accion`** (web search live + MCP de noticias) llena `fuentes/` → **`$reporte-semanal`** consolida el reporte `.md` en el Project → el **MCP de Gmail** deja el borrador → **`$publicar-tablero`** regenera `tablero.html` (y el **Site** con URL del equipo). En paralelo, la **Task de ChatGPT** de la Parte 1 sigue mandando el pulso liviano a tu inbox.

## 🧭 Diferencias clave para nombrar en el workshop

1. **Parte 1:** las Tasks de ChatGPT corren en la nube (punto a favor) pero entregan por notificación, sin borrador dirigido al jefe (punto en contra frente al conector de Gmail de claude.ai).
2. **Conectores → MCP:** mismo concepto, distinta plomería; en Codex no hay directorio con botón Connect, hay `config.toml`/`codex mcp`.
3. **Skills:** el mapeo más limpio, mismo estándar `SKILL.md`; cambia `/skill-creator` → `$skill-creator` y el Save de la lista → la carpeta `.agents/skills/`.
4. **Tablero:** Codex no tiene Live Artifacts, y a la vez es el único que hoy da **URL pública** vía Sites. Ser honesto con las dos mitades.
5. **Público:** Cowork apunta a no-técnicos (botones); Codex pide convivir con archivos (`AGENTS.md`, `config.toml`) y algo de terminal.

## 📚 Fuentes (documentación oficial)

- [Tasks in ChatGPT](https://help.openai.com/en/articles/10291617-tasks-in-chatgpt) · [ChatGPT search](https://help.openai.com/en/articles/9237897-chatgpt-search)
- [Codex — Overview](https://developers.openai.com/codex) · [Codex app](https://developers.openai.com/codex/app)
- [AGENTS.md](https://developers.openai.com/codex/guides/agents-md) · [Agent Skills](https://developers.openai.com/codex/skills) · [MCP](https://developers.openai.com/codex/mcp)
- [Automations](https://developers.openai.com/codex/app/automations) · [In-app browser](https://developers.openai.com/codex/app/browser) · [Sites](https://developers.openai.com/codex/sites)
- [Config Reference](https://developers.openai.com/codex/config-reference)
