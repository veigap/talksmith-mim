# 🛰️ Solución paso a paso (versión Codex) — "Faro, la mesa de inteligencia de mercado de Atlas"

> Equivalente en **OpenAI Codex** de la solución descrita en `mission-claud- res.md` (hecha en Claude Cowork). Misma misión, mismos cuatro Milestones, mismo resultado final: un **pulso semanal de mercado** que se arma, se distribuye y se publica **solo**. Lo que cambia es la herramienta: en lugar de la app Cowork, usamos Codex.
>
> 💡 Convención (igual que en el original): donde veas `[EMPRESAS]`, va la lista de las 3 acciones que el jefe pidió seguir: `YPF, VIST, TS`. Donde veas `[TICKER]`, va una sola (ej. `YPF`).
>
> 🎭 El encuadre es idéntico: trabajás en **Atlas**, una empresa de insumos de perforación para Vaca Muerta, y tu jefe te pidió un pulso semanal sobre YPF, Vista y Tenaris — la ola de inversión en IA empuja la demanda de energía y, con ella, la perforación. Un pasante juntaba las noticias a mano, un archivo por portal. El objetivo es que Faro lo haga solo.

---

## ⚠️ Lee esto primero: Cowork vs. Codex

No son la misma clase de producto, y conviene tenerlo claro antes de empezar:

- **Claude Cowork** es una app de escritorio pensada para **gente no técnica**: todo se hace con botones, paneles y prompts. "Projects", "Skills", "Connectors", "Schedule" y "Artifacts" son piezas con interfaz propia.
- **OpenAI Codex** es un **agente de programación** que vive en tres superficies: la **app de escritorio de Codex**, la **extensión de IDE** (VS Code/Cursor) y la **CLI** (terminal). Tiene **las mismas seis piezas conceptuales**, pero algunas se expresan como **archivos y configuración** (`AGENTS.md`, `config.toml`) en lugar de botones.

**Recomendación para replicar esta misión:** usá la **app de escritorio de Codex**. Es la superficie más parecida a Cowork — tiene **Projects**, **Skills**, **MCP/Connectors**, **navegador integrado** y **Automations** con interfaz visual. Donde algo solo se hace por archivo o terminal, lo aclaro.

> 🧠 La buena noticia: el mapeo es casi 1 a 1. Codex adoptó el **mismo estándar de Skills** (`SKILL.md`) que usa Cowork, así que las Skills que escribís son prácticamente idénticas.

---

## 🗺️ Tabla maestra de equivalencias

| Pieza en Cowork (Claude) | Equivalente en Codex (OpenAI) | Cómo se materializa |
|---|---|---|
| **Project** (carpeta + memoria + lugar fijo) | **Project** en la app de Codex (+ carpeta/repo en disco) | La app de Codex arranca por "projects": un espacio de larga duración ligado a una carpeta. |
| **Instructions** del proyecto | **`AGENTS.md`** | Archivo de texto en la raíz de la carpeta (o `~/.codex/AGENTS.md` global). Es el "contrato de trabajo" de Codex. |
| **Skills** (`SKILL.md`, sin código) | **Skills** (`SKILL.md`, mismo estándar) | Carpeta con `SKILL.md` en `.agents/skills/` (repo) o `~/.agents/skills/` (usuario, sirve para cualquier carpeta). |
| **`/skill-creator`** | **`$skill-creator`** (built-in) | Asistente integrado de Codex para crear Skills sin escribir código. |
| **Connectors** (MT Newswires, Gmail) | **MCP servers** | Se configuran en `~/.codex/config.toml` bajo `[mcp_servers.<nombre>]`, o se agregan desde la app con el comando `codex mcp`. |
| **Búsqueda web** | **Web search tool** | Activada por defecto en modo "cached"; para datos frescos: `--search` o `web_search = "live"` en `config.toml`. |
| **Claude in Chrome** (navegador) | **In-app browser** / **Chrome extension** / Computer Use | Panel de navegador integrado en la app de Codex para previsualizar e inspeccionar páginas. |
| **Schedule** (tareas recurrentes) | **Automations** | Tareas programadas (cron, diaria, semanal) que corren en segundo plano y reportan en "Triage" (la bandeja de Codex). |
| **Live Artifacts** (tablero auto-actualizable) | **No hay equivalente directo** → tablero HTML regenerado por una Skill + **navegador integrado** (y opcionalmente **Codex Sites** para publicarlo) | Codex genera el HTML real en disco; la Skill lo regenera y la Automation lo vuelve a correr. |
| **Memoria del proyecto** | **Memories** (+ Chronicle) y el propio `AGENTS.md` | Codex tiene memoria propia además de las instrucciones del repo. |

---

## 🧰 Antes de empezar (setup)

1. Instalá Codex. Para esta misión usá la **app de escritorio de Codex** (también existen la extensión de IDE y la CLI con `npm i -g @openai/codex`).
2. Iniciá sesión con tu cuenta de ChatGPT/OpenAI (plan que incluya Codex) o con una API key.
3. Creá (si no existe) una carpeta vacía de trabajo, por ejemplo `Documentos/Faro-Mercado`. **Tip:** inicializala como repo de Git (`git init`) — habilita worktrees y deja las Automations más prolijas.
4. Activá la **búsqueda web en vivo** (Faro la necesita en el Milestone 2). En `~/.codex/config.toml`:

```toml
web_search = "live"
```

> En la CLI también podés usar el flag `--search` en una corrida puntual. Por defecto la búsqueda es "cached" (índice de OpenAI, sin abrir páginas en vivo); "live" trae datos frescos.

> 📁 **Material de ejemplo (idéntico al original):** en `reportes/` hay una subcarpeta por semana. Dentro de cada una está `fuentes/` (las notas en crudo del pasante, un archivo por portal) **lado a lado** con el reporte final (`.md`). Sirven de insumo y de "respuesta correcta".
>
> ```
> reportes/
> ├── semana-2026-05-18/
> │   ├── fuentes/   → yahoo-finance.txt, bloomberg.txt (Vista), reuters.txt (YPF), stocktitan.txt (Tenaris)
> │   └── reporte-semana-2026-05-18.md
> ├── semana-2026-05-25/   (varios archivos en fuentes/  +  reporte)
> └── semana-2026-06-01/   (varios archivos en fuentes/  +  reporte)
> ```

> ✅ **Verificación de setup:** abrís la app de Codex, ves tus proyectos, tenés la carpeta lista y la búsqueda web en "live". A despegar.

---

# 🛠️ Milestone 1 — Faro toma forma
### *(Project · AGENTS.md · Skills)*

## Paso 1.1 — Levantar la base: el Project + las instrucciones

**En Cowork** creabas un "Project" con un campo de "Instructions". **En Codex**, el Project apunta a una carpeta y las instrucciones viven en un archivo **`AGENTS.md`** en la raíz de esa carpeta.

1. En la app de Codex, creá un **nuevo Project** y apuntalo a tu carpeta `Documentos/Faro-Mercado`.
2. Creá el archivo `AGENTS.md` en la raíz de esa carpeta (podés pedírselo a Codex: *"creá un AGENTS.md con este contenido"*) y pegá:

```markdown
# Faro — analista de mercado del equipo de Atlas

Sos **Faro**, el analista de mercado del equipo de Atlas, una empresa de insumos de perforación para Vaca Muerta. Preparás un pulso
semanal para colegas no técnicos (incluido el jefe del área), que se lee en 2
minutos antes de la reunión de los lunes.

- Seguís estas empresas que el equipo vigila: YPF, VIST, TS.
- Escribís en español, claro y breve, sin jerga financiera complicada. Si usás
  un término técnico, lo explicás en una línea.
- Tus reportes son informativos y para uso interno: NO son recomendaciones de
  inversión ni asesoramiento financiero. Siempre incluís esa aclaración al final.
- Para armar cada reporte partís de las notas en crudo de la carpeta `fuentes/`
  de la semana (y, más adelante, de lo que vos mismo busques). Si un dato no
  está, lo decís en lugar de inventarlo.
- Guardás cada reporte como Markdown con el nombre `reporte-semana-AAAA-MM-DD.md`,
  junto a la carpeta `fuentes/` de esa semana.
```

> 📌 **Por qué importa:** `AGENTS.md` es el "contrato de trabajo" de Faro. Codex lo lee en cada sesión que abrís dentro de esa carpeta, sin que tengas que repetir el contexto. Es el equivalente exacto a las "Instructions" del Project de Cowork. Podés commitearlo al repo para que el equipo lo comparta.

---

## Paso 1.2 — Crear la Skill `reporte-semanal` (raw → reporte)

Igual que en Cowork: una **Skill** toma los varios archivos de `fuentes/` (uno por portal) y los consolida en un reporte prolijo, siempre con el mismo formato. Codex usa **el mismo estándar `SKILL.md`**.

1. En un thread del Project, escribí el creador de Skills integrado:

```
$skill-creator
```

2. Cuando te pregunte qué hace la Skill, pegá:

> *"Quiero crear una Skill llamada `reporte-semanal`. Su entrada es la carpeta `fuentes/` de una semana, que tiene **varios archivos en crudo, uno por portal** (la info de una misma empresa puede estar repartida entre varios). Debe leerlos TODOS, consolidar por empresa y generar un archivo Markdown con esta estructura exacta:*
> *1. **Título:** «Pulso semanal de mercado — [fecha]».*
> *2. **Resumen ejecutivo:** 3 a 4 líneas en lenguaje simple sobre la semana.*
> *3. **Una sección por empresa**: nombre y ticker; precio aprox. de cierre y variación de la semana; 2-3 noticias con una línea de contexto; «Ánimo» (Positivo/Neutral/Negativo) con media línea; «A vigilar» (1 cosa).*
> *4. **Tabla resumen:** una fila por empresa con ticker, variación % y ánimo.*
> *5. **Fuentes principales:** 3-4 de los links que venían en los archivos de `fuentes/`.*
> *6. **Aclaración legal:** «Reporte interno e informativo; no constituye asesoramiento financiero».*
> *La empresa más relevante de la semana va primera. No inventes datos: si falta algo, decílo. Precios = aproximados; conservá los links reales. Que sea una Skill solo de instrucciones (sin scripts)."*

3. Codex te muestra el borrador del `SKILL.md`. Revisalo y confirmá. ¿Cambios? Pedíselos en lenguaje natural.

> 📍 **Dónde queda la Skill:** Codex la guarda en `.agents/skills/reporte-semanal/SKILL.md`. Si la querés disponible desde cualquier carpeta (no solo este proyecto), guardala en `~/.agents/skills/`. Codex detecta los cambios solo; si no aparece, reiniciá Codex.

> 🧩 **Estructura de una Skill (igual que Cowork):** una carpeta con un `SKILL.md` (frontmatter `name` + `description`, y cuerpo en Markdown con los pasos). Opcionalmente puede tener `scripts/`, `references/` y `assets/`. La escribís una vez y Faro "ya sabe" armar el reporte.

> 🔌 **Cómo se invoca:** explícita (`$reporte-semanal` en el prompt, o `/skills` para elegirla del menú) o **implícita** (Codex la elige solo cuando tu pedido encaja con la `description` — por eso conviene una descripción clara).

---

## Paso 1.3 — Generar el primer reporte (desde las notas del pasante)

En un thread del Project, escribí:

> *"Faro, en `reportes/semana-2026-05-25/fuentes/` están las notas en crudo que dejó el pasante (varios archivos, uno por portal). Leélas TODAS, consolidá la info por empresa y generá el reporte con `$reporte-semanal`. Guardalo como `reporte-semana-2026-05-25.md` en esa misma carpeta de la semana. No inventes datos que no estén en las fuentes."*

> ✅ **🏁 Criterio de éxito (Milestone 1):** se generó el reporte, con todas las empresas, la tabla, las fuentes y la aclaración legal, **partiendo de varios archivos desordenados**. Si está, **Faro ya tomó forma.** *(Compará con el reporte de ejemplo de esa semana.)*

> 🛠️ **Si algo sale mal:**
>
> - *Ignoró alguna fuente* → recordale: *"leé TODOS los archivos de `fuentes/`, no solo uno"*.
> - *No respeta la plantilla* → *"seguí exactamente la estructura de la Skill reporte-semanal"*.
> - *No encuentra la Skill* → reiniciá Codex; confirmá que `reporte-semanal/SKILL.md` esté en `.agents/skills/`.

---

# 🔎 Milestone 2 — Faro aprende a investigar
### *(Web search · MCP / Connectors · Navegador)*

**La idea (idéntica):** que Faro consiga la info solo. Dado un ticker y un día, busca en la web y en un servicio de datos al que te conectás, y deja las fuentes en disco — reemplazando el copy-paste del pasante.

## Paso 2.1 — Conectarte a un proveedor de datos (MCP server)

**En Cowork** conectabas "MT Newswires" desde el directorio de Connectors. **En Codex**, los servicios externos se conectan por **MCP (Model Context Protocol)**: el mismo estándar, configurado como un "MCP server".

**Opción A — desde la terminal/CLI:**

```bash
codex mcp        # asistente para agregar y administrar servers MCP
```

**Opción B — editando `~/.codex/config.toml`** (server por HTTP, con token):

```toml
[mcp_servers.mt_newswires]
url = "https://<endpoint-del-proveedor>/mcp"
bearer_token_env_var = "MT_NEWSWIRES_TOKEN"
```

…o un server local por stdio (típico de muchos conectores de la comunidad):

```toml
[mcp_servers.market_news]
command = "npx"
args = ["-y", "<paquete-del-mcp-de-noticias>"]
```

Después, dentro de una sesión, verificá con:

```
/mcp
```

…que el server figure **conectado** y muestre sus tools.

> ⚠️ **Diferencia honesta:** Cowork trae el connector de MT Newswires **listo en su directorio**. En Codex **no hay un directorio de connectors con un botón "Connect"** equivalente: conectás cualquier servicio que exponga un **MCP server**. Si tu proveedor (MT Newswires u otro) ofrece un endpoint MCP, lo pegás como arriba. Si no, usás un MCP genérico de noticias/datos financieros, o te quedás solo con la búsqueda web. El concepto —"enchufo un servicio externo sin programarlo yo"— es el mismo.

**Probalo:** en un thread, escribí:

> *"Usando el MCP de noticias de mercado, traeme las últimas noticias de `YPF`. Mostrame qué devuelve."*

> 🌐 **La otra fuente — la web:** el **precio** lo saca Faro de la página del ticker en Yahoo Finance con la **búsqueda web** (`web_search = "live"`); las **noticias**, de `https://finance.yahoo.com/news/`. Para páginas que no cargan bien, abrí el **navegador integrado** de Codex (ver 2.2 bis).

## Paso 2.1 bis — El navegador (equivalente a Claude in Chrome)

Para páginas que dependen de JavaScript o no cargan bien con la búsqueda, Codex tiene un **navegador integrado** en la app (panel derecho), una **extensión de Chrome** y **Computer Use**. Pedile: *"abrí la página en el navegador integrado e inspeccioná el precio de `YPF`"*.

## Paso 2.2 — Crear la Skill `buscar-accion` (ticker + día → guarda fuentes)

1. En un thread del Project, escribí `$skill-creator`.
2. Pegá la descripción:

> *"Quiero crear una Skill llamada `buscar-accion`. Recibe un **ticker** (ej. YPF) y un **día**. Busca info de esa acción en DOS fuentes: (1) la web **Yahoo Finance** —precio y variación en `finance.yahoo.com/quote/<TICKER>/`, y noticias en `https://finance.yahoo.com/news/`— usando la búsqueda web; y (2) el **MCP de noticias que conectaste** (MT Newswires u otro). Después **guarda en disco** lo que encontró, dentro de `reportes/semana-AAAA-MM-DD/fuentes/` (usando el lunes de esa semana), agregando un bloque por ticker en un archivo por fuente: `yahoo-finance.md` y `mt-newswires.md`. No inventa datos: si una fuente no devuelve algo, escribe 'dato no disponible'. Conserva los links reales y marca los precios como aproximados. Si el MCP no está disponible, avisa y sigue solo con Yahoo Finance."*

3. Revisá el borrador y confirmá.

> 📎 **Modelo a seguir:** la carpeta `reportes/semana-2026-06-01/fuentes/` muestra el tipo de material (archivos por fuente, con precios, titulares y links) que esta Skill debe dejar en disco.

## Paso 2.3 — Que Faro arme las fuentes solo

> *"Faro, usando `$buscar-accion`, buscá la info de la semana actual para `YPF, VIST, TS` (una por una) y guardá las fuentes en una carpeta `fuentes/` nueva. Cuando termines, armá el reporte con `$reporte-semanal` a partir de esas fuentes."*

> ✅ **🏁 Criterio de éxito (Milestone 2):** Faro llenó una carpeta `fuentes/` **partiendo de cero** (con datos que él mismo buscó) y con eso `reporte-semanal` armó el reporte — **sin que pegaras una sola noticia.**

> 🛠️ **Si algo sale mal:**
>
> - *El MCP no responde* → corré `/mcp` para ver el estado; revisá el `command`/`url` y el token en `config.toml`.
> - *Una página no carga* → pedile que la abra con el **navegador integrado**.
> - *No trae precios/noticias frescas* → confirmá `web_search = "live"` (o pasá `--search`).

---

# ⚙️ Milestone 3 — Faro trabaja solo
### *(MCP — Gmail · Automations)*

## Paso 3.1 — Conectar Gmail (MCP server)

**En Cowork** conectabas Gmail desde el directorio. **En Codex**, Gmail también se conecta como **MCP server**. Agregá uno de Gmail (CLI `codex mcp`, o en `config.toml`):

```toml
[mcp_servers.gmail]
command = "npx"
args = ["-y", "<paquete-del-mcp-de-gmail>"]
# o, si es un server remoto OAuth:
# url = "https://<endpoint-gmail-mcp>/mcp"
# bearer_token_env_var = "GMAIL_OAUTH_TOKEN"
```

Seguí el inicio de sesión/autorización de Google que pida el server. Verificá con `/mcp`.

> 📌 **Por qué importa:** con Gmail conectado, Faro **distribuye** el reporte solo. Los MCP son la diferencia entre un agente que *escribe* y uno que *actúa* en tus apps.

> ⚠️ **Diferencia honesta:** en Cowork Gmail es un connector "oficial" de un clic. En Codex usás un **MCP server de Gmail** (oficial del proveedor o de la comunidad). Más flexible, pero requiere elegir/instalar el server y autorizarlo una vez.

## Paso 3.2 — Prueba de fuego: que Faro distribuya el reporte por email

> *"Faro, tomá el último reporte semanal de la carpeta y enviámelo por email a `pveiga@gmail.com` con el asunto «Pulso semanal de mercado — [fecha]» usando el MCP de Gmail. Poné el resumen ejecutivo y la tabla en el cuerpo del correo, en un formato prolijo, listo para que lo lea el equipo."*

La primera vez, Codex puede pedirte aprobación para usar la tool del MCP: aprobá.

> ✅ **Mini-verificación:** revisá tu bandeja de entrada. Tiene que haber llegado el correo.

## Paso 3.3 — Poner a Faro en piloto automático (Automations)

**En Cowork** usabas "Schedule". **En Codex** se llama **Automations**: tareas recurrentes que corren en segundo plano y reportan en **Triage** (la bandeja de Codex). Pueden disparar Skills con `$nombre-skill`.

**Cómo crearla (la forma más simple): pedírselo a Codex en un thread.**

> *"Creá una **automation** que corra **cada lunes a las 8:00**. En cada corrida: con `$buscar-accion` buscá la info de la semana de `YPF, VIST, TS` y guardá las fuentes; después con `$reporte-semanal` armá el reporte, guardalo en la carpeta del proyecto y enviámelo por email a `pveiga@gmail.com` con el asunto «Pulso semanal de mercado — [fecha]» usando el MCP de Gmail. Hacela una automation **standalone** (corrida independiente cada semana). Si no hay nada para reportar, archivá la corrida."*

Codex redacta el prompt durable, elige el tipo de automation y la programa. Confirmá: **semanal, lunes, 8:00** (o elegí "custom" e ingresá cron, ej. `0 8 * * 1`).

**Alternativa por menú:** abrí el panel **Automations** en la barra lateral → nueva automation → completá nombre, schedule (Weekly / lunes / 8:00 o cron), el prompt de arriba, y el modo (local o worktree).

> ⚠️ **Recordá (igual que en Cowork):** las automations **con scope de proyecto** necesitan **la app de Codex corriendo y la carpeta disponible en disco**. OpenAI está extendiendo esto a ejecución en la nube, pero hoy, para este caso (que toca archivos locales y manda mail), conviene tener la app abierta. Sandbox: para que pueda escribir archivos y usar red, dejá el modo en **workspace-write** (no read-only).

> ✅ **🏁 Criterio de éxito (Milestone 3):** (a) recibiste el email de prueba, y (b) en **Automations** aparece tu tarea «Pulso semanal», programada para los lunes. **Faro ya trabaja solo.**

> 🧪 **Tip:** no esperes al lunes. Probá el **prompt en un thread normal primero** (OpenAI lo recomienda antes de programar), y corré la automation a demanda para demostrarla en vivo. Revisá las primeras corridas en Triage y ajustá.

---

# 🦅 Milestone 4 — Faro vuela
### *(Tablero — HTML + navegador integrado / Codex Sites · Skills)*

**La idea (igual):** el tablero no se arma a mano una sola vez. Una **Skill** lo publica y lo actualiza, y la enganchamos a la automation del lunes.

> ⚠️ **La diferencia más grande de todo el mapeo está acá.** Cowork tiene **Live Artifacts**: un objeto gestionado que se "refresca" en su panel. **Codex no tiene un equivalente directo.** Lo que Codex hace —y muy bien— es **generar el HTML real del tablero en disco**. Ese archivo lo **previsualizás en el navegador integrado** y, si querés una URL para el equipo, lo **publicás** (con **Codex Sites** o cualquier hosting estático). "Se mantiene al día" porque **la Skill regenera el HTML** cada vez que corre la automation — la misma lógica que en Cowork, donde el artifact también lo regenera la Skill.

## Paso 4.1 — Crear la Skill `publicar-tablero`

1. En un thread del Project, escribí `$skill-creator`.
2. Pegá la descripción:

> *"Quiero crear una Skill llamada `publicar-tablero`. Lee los archivos `reporte-semana-*.md` de la carpeta del proyecto, toma el MÁS RECIENTE y con él genera (o regenera) un archivo **`tablero.html` autocontenido** (todo el CSS/JS embebido, sin dependencias externas): un tablero con un encabezado (fecha + resumen ejecutivo), una **tarjeta por empresa** (ticker y nombre, variación de la semana en verde/rojo, «ánimo» y 2-3 noticias con su link) y la **tabla resumen**. Diseño limpio tipo panel financiero, para alguien no técnico. Mantené el mismo diseño entre semanas; solo cambian los datos. No inventes: mostrá solo lo que está en el reporte. Dejá el HTML listo para abrir en el navegador integrado."*

3. Revisá el borrador y confirmá.

> 🎨 **Diseño de referencia:** si tenés `mockup-tablero.png` (el boceto del jefe), pasáselo: *"que el `tablero.html` se vea como este boceto"*.

> 📌 **Por qué una Skill y no a mano:** un HTML aislado no se actualiza solo. El tablero se mantiene al día porque **Faro regenera el archivo** cada vez que corre esta Skill — por eso conviene que la dispare la automation del lunes. (Mismo razonamiento que en Cowork.)

## Paso 4.2 — Publicar el tablero por primera vez

> *"Faro, usá `$publicar-tablero` para generar el tablero del equipo con el último reporte. Después abrilo en el navegador integrado para que lo vea."*

Para una **URL compartible** (lo más cercano a "Live"), publicá el HTML con **Codex Sites** o subilo a cualquier hosting estático (Pages, Vercel, etc.): *"publicá `tablero.html` como un sitio y pasame el link"*.

## Paso 4.3 — Engancharlo a la automation del lunes

Editá la automation del Milestone 3 para que **termine** generando el tablero. En el panel Automations, abrí la tarea y agregá al final del prompt:

> *"…y por último, actualizá el tablero del equipo con `$publicar-tablero` (regenerá `tablero.html` con el reporte recién creado) y, si está publicado como sitio, volvé a publicarlo."*

Ahora cada lunes, después de buscar la info, armar el reporte y mandar el email, Faro **regenera el tablero** solo.

> ✅ **🏁 Criterio de éxito (Milestone 4):** tenés un `tablero.html` con las empresas y la tabla (visible en el navegador integrado, y opcionalmente publicado), y la automation lo **regenera cada lunes** (probalo corriéndola a demanda). **Faro ya vuela — y tu lunes quedó libre.**

> 🛠️ **Si algo sale mal:**
>
> - *El tablero está vacío* → confirmá que exista al menos un `reporte-semana-*.md`.
> - *No se actualizó tras la automation* → revisá que el prompt de la automation incluya el paso de `$publicar-tablero`.
> - *Querés que refresque datos solo, sin regenerar* → Codex no tiene "Live Artifacts"; la actualización siempre la hace la Skill al regenerar el HTML (idealmente desde la automation).

---

## 🔄 El círculo completo (en Codex)

Con los cuatro Milestones listos, el desafío queda resuelto y funcionando solo:

`Lunes 8:00` → **Automation** dispara la tarea → la Skill **`$buscar-accion`** consulta **Yahoo Finance (web search) + el MCP de noticias** y guarda las **`fuentes/`** → la Skill **`$reporte-semanal`** las consolida en el **reporte** dentro de la carpeta del **Project** → el **MCP de Gmail** lo distribuye al equipo → la Skill **`$publicar-tablero`** regenera el **`tablero.html`** (y lo republica) para el jefe.

Seis piezas de Codex — **Projects, AGENTS.md, Skills, MCP servers, Automations y el tablero HTML/navegador** — más **búsqueda web en vivo**. Y vos, con la mañana del lunes libre.

---

## 🎤 Guía rápida para el facilitador (Cowork → Codex)

| Momento | Qué mostrar en vivo (Codex) | Concepto que "cae" |
|---|---|---|
| M1 · Project + `AGENTS.md` | Crear el Project y abrir el `AGENTS.md` | "Codex recuerda el contexto sin que yo lo repita" |
| M1 · Skill `reporte-semanal` | `$skill-creator` y abrir el `SKILL.md`; juntar varias fuentes | "Una Skill convierte el caos (muchos archivos) en un entregable" |
| M2 · MCP de datos | Conectar un MCP de noticias y pedir noticias de un ticker (`/mcp`) | "Conecto servicios externos sin programar (vía MCP)" |
| M2 · Skill `buscar-accion` | Ver aparecer la carpeta `fuentes/` sola | "Faro reemplaza el copy-paste del pasante" |
| M3 · Gmail (MCP) | El email llegando a la bandeja | "MCP = Codex que actúa en mis apps" |
| M3 · Automations | Correr la automation a demanda para no esperar al lunes | "Puedo delegar trabajo recurrente" |
| M4 · Skill `publicar-tablero` | Correr la Skill y abrir `tablero.html` en el navegador integrado | "Hasta publicar el dashboard se automatiza con una Skill" |
| M4 · Tablero en la automation | Mostrar que el lunes el tablero se regenera solo | "De archivos sueltos a un producto vivo, y automático" |

**Errores comunes a anticipar (versión Codex):**

- Olvidarse de poner `web_search = "live"` (o `--search`) → Faro no consigue precios/noticias frescas en el M2.
- MCP de noticias o de Gmail mal configurado (token/`command`) → `buscar-accion` se queda solo con Yahoo, o no manda el mail. Diagnosticá con `/mcp`.
- Dejar el sandbox en **read-only** → las automations fallan al escribir archivos o usar red. Pasá a **workspace-write**.
- Cerrar la app y esperar que la automation de proyecto corra igual → necesita la app abierta y la carpeta en disco.
- Esperar que el tablero se "refresque solo" como un Live Artifact → en Codex lo regenera la Skill `publicar-tablero` (idealmente desde la automation).
- Olvidarse de sumar `$publicar-tablero` al prompt de la automation → el tablero no se actualiza los lunes.

---

## 🧭 Diferencias clave que conviene nombrar en el workshop

1. **Público:** Cowork está pensado para no-técnicos (todo botones); Codex es un agente de **programación** (app/IDE/CLI). La app de Codex acerca mucho la experiencia, pero hay archivos (`AGENTS.md`, `config.toml`) de por medio.
2. **Skills:** prácticamente idénticas — mismo estándar `SKILL.md`, mismo creador asistido (`$skill-creator`). Es el mapeo más limpio.
3. **Connectors → MCP:** mismo concepto ("enchufo un servicio"), distinta plomería. Cowork tiene directorio con botón "Connect"; Codex usa **MCP servers** en `config.toml`/`codex mcp`. Más flexible, un poco más de setup.
4. **Schedule → Automations:** equivalente fuerte. Codex agrega cron custom, modo local vs. worktree, y la bandeja "Triage".
5. **Live Artifacts → (sin equivalente directo):** la mayor brecha. Codex genera **HTML real** que previsualizás en su navegador y publicás con **Codex Sites**/hosting; la "vida" la da la Skill que lo regenera. A favor de Codex: el resultado es un artefacto portable y desplegable de verdad.

---

## 📚 Fuentes (documentación oficial de OpenAI Codex)

- [Codex — Overview](https://developers.openai.com/codex)
- [Codex app — Overview](https://developers.openai.com/codex/app)
- [Custom instructions with AGENTS.md](https://developers.openai.com/codex/guides/agents-md)
- [Agent Skills](https://developers.openai.com/codex/skills)
- [Model Context Protocol (MCP)](https://developers.openai.com/codex/mcp)
- [Config Reference](https://developers.openai.com/codex/config-reference) · [Config basics](https://developers.openai.com/codex/config-basic)
- [Automations (Codex app)](https://developers.openai.com/codex/app/automations)
- [In-app browser](https://developers.openai.com/codex/app/browser) · [Chrome extension](https://developers.openai.com/codex/app/chrome-extension)
- [Sites](https://developers.openai.com/codex/sites)
- [Slash commands (CLI)](https://developers.openai.com/codex/cli/slash-commands)
- [openai/skills (ejemplos y skill-creator)](https://github.com/openai/skills)
