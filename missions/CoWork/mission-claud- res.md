# 🛰️ Solución paso a paso — "Faro, la mesa de inteligencia de mercado de Atlas"

> Guía de resolución de la misión descrita en `mission.md`. Pensada para que el facilitador la conduzca en vivo y para que cualquier participante **no técnico** la replique. Incluye los **prompts exactos** para copiar y pegar (en *cursiva con comillas*) y lo que hay que **clickear**.
>
> 💡 Convención: donde veas `[EMPRESAS]`, va la lista de **las 3 acciones que el jefe pidió seguir**: `YPF, VIST, TS`. Donde veas `[TICKER]`, va una sola (ej. `YPF`). (Podés cambiarlas si adaptás la misión a tu propio contexto laboral.)
>
> 🎭 El encuadre: trabajás en **Atlas**, una empresa de insumos de perforación para Vaca Muerta. Tu jefe quiere un **pulso semanal de mercado** sobre **3 empresas del sector** (YPF, Vista y Tenaris), porque la ola de inversión en IA dispara la demanda de energía y, con ella, la actividad de perforación. Hasta ahora un **pasante** juntaba las noticias a mano, un archivo por portal. En el workshop el email te lo enviás a vos mismo, como si fueras el destinatario del equipo.

---

## 🧰 Antes de empezar (setup detallado)

1. Abrí la **app de escritorio de Claude** y verificá que esté en la última versión (si aparece "Setting up Claude's workspace", es normal: se está actualizando).
2. Clickeá la pestaña **"Cowork"** (junto a "Chat" y "Code").
3. Confirmá que la **búsqueda web** esté activa: Configuración (Settings) → Capacidades (Capabilities). Faro la usa en el Milestone 2 para leer precios y noticias.
4. Creá (si no existe) una carpeta vacía, por ejemplo `Documentos/Faro-Mercado`.

> ✅ **Verificación de setup:** ves la pestaña Cowork, tenés plan pago y una carpeta lista. A despegar.

> 📁 **Material de ejemplo:** en `reportes/` hay una subcarpeta por semana. Dentro de cada una está la carpeta `fuentes/` (las notas en crudo del **pasante**, **un archivo por portal**) **lado a lado** con el reporte final (`.md`). Úsalas como insumo y como modelo del resultado:
>
> ```
> reportes/
> ├── semana-2026-05-18/
> │   ├── fuentes/   → yahoo-finance.txt, bloomberg.txt (Vista), reuters.txt (YPF), stocktitan.txt (Tenaris)
> │   └── reporte-semana-2026-05-18.md
> ├── semana-2026-05-25/   (varios archivos en fuentes/  +  reporte)
> └── semana-2026-06-01/   (varios archivos en fuentes/  +  reporte)
> ```
>
> *Noticias y enlaces reales (mayo 2026); precios aproximados con fines ilustrativos.*

> 🧩 **Skills listas (para el facilitador):** la misión incluye tres Skills ya armadas en la carpeta `skills/` (`reporte-semanal/`, `buscar-accion/` y `publicar-tablero/`). Sirven como referencia o "respuesta correcta". En el workshop, lo ideal es que los participantes las construyan con `/skill-creator` (Pasos 1.2, 2.2 y 4.1), pero podés tenerlas a mano por si alguien se traba.

---

# 🛠️ Milestone 1 — Faro toma forma
### *(Projects · Instructions · Skills)*

## Paso 1.1 — Levantar la base: el Proyecto

1. En el panel izquierdo, buscá **"Projects"** (Proyectos) y clickeá el botón **"+"**.
2. Elegí **"Start from scratch"** (Empezar de cero).
3. Completá:
   - **Nombre:** `Inteligencia de Mercado Semanal`
   - **Ubicación:** elegí tu carpeta `Documentos/Faro-Mercado`.
4. En el campo de **Instrucciones** del proyecto, pegá esto (ajustá tus empresas):

> *"Sos **Faro**, el analista de mercado del equipo de Atlas, una empresa de insumos de perforación para Vaca Muerta. Preparás un pulso semanal para colegas no técnicos (incluido el jefe del área), que se lee en 2 minutos antes de la reunión de los lunes.*
> *Seguís estas empresas que el equipo vigila: `[EMPRESAS]`.*
> *Escribís en español, claro y breve, sin jerga financiera complicada. Si usás un término técnico, lo explicás en una línea.*
> *Tus reportes son informativos y para uso interno: NO son recomendaciones de inversión ni asesoramiento financiero. Siempre incluís esa aclaración al final.*
> *Para armar cada reporte partís de las notas en crudo de la carpeta `fuentes/` de la semana (y, más adelante, de lo que vos mismo busques). Si un dato no está, lo decís en lugar de inventarlo.*
> *Guardás cada reporte como Markdown con el nombre `reporte-semana-AAAA-MM-DD.md`, junto a la carpeta `fuentes/` de esa semana."*

5. Clickeá **"Create"**.

> 📌 **Por qué importa:** el Proyecto le da a Faro una **carpeta propia**, **memoria** dentro del proyecto y un **lugar fijo** para sus tareas. Las **Instrucciones** son su "contrato de trabajo": valen para todo lo que hagas dentro del proyecto, sin repetirlas una y otra vez.

---

## Paso 1.2 — Crear la Skill `reporte-semanal` (raw → reporte)

Esta Skill toma **los varios archivos de `fuentes/`** (uno por portal) y los **consolida** en un reporte prolijo, siempre con el mismo formato.

1. Dentro del proyecto, abrí una nueva tarea (**"+ New task"**).
2. Escribí `/skill-creator` y enviá. Esto abre el asistente para crear Skills (sin código).
3. Cuando te pida describir la habilidad, pegá:

> *"Quiero crear una Skill llamada `reporte-semanal`. Su entrada es la carpeta `fuentes/` de una semana, que tiene **varios archivos en crudo, uno por portal** (la info de una misma empresa puede estar repartida entre varios). Debe leerlos TODOS, consolidar por empresa y generar un archivo Markdown con esta estructura exacta:*
> *1. **Título:** «Pulso semanal de mercado — [fecha]».*
> *2. **Resumen ejecutivo:** 3 a 4 líneas en lenguaje simple sobre la semana (lo que diría en la reunión de los lunes).*
> *3. **Una sección por empresa**: nombre y ticker; precio aprox. de cierre y variación de la semana; 2-3 noticias con una línea de contexto; «Ánimo» (Positivo/Neutral/Negativo) con media línea; «A vigilar» (1 cosa).*
> *4. **Tabla resumen:** una fila por empresa con ticker, variación % y ánimo.*
> *5. **Fuentes principales:** 3-4 de los links que venían en los archivos de `fuentes/`.*
> *6. **Aclaración legal:** «Reporte interno e informativo; no constituye asesoramiento financiero».*
> *La empresa más relevante de la semana va primera (marcada con ⭐). No inventes datos: si falta algo, decílo. Precios = aproximados; conservá los links reales. **Guardá el resultado con el sufijo `-new`** en el nombre del archivo para no pisar el reporte original (ej. `reporte-semana-2026-05-25-new.md`)."*

4. Faro te muestra el borrador (`SKILL.md`). Revisalo y confirmá. ¿Cambios? Pedíselos en lenguaje natural.

> 📎 **Modelo a seguir:** en `reportes/` tenés tres ejemplos. En cada subcarpeta está la carpeta `fuentes/` (varios `.txt`) **lado a lado** con el reporte final (`.md`) ya armado — la "respuesta correcta". Fijate cómo, en la semana del 25/05, los datos de YPF están en `industrial-info.txt`, los de Vista en `stocktitan.txt`, y las cotizaciones en `yahoo-finance.txt`.

> 📌 **Por qué importa:** una **Skill** es una carpeta con un `SKILL.md` (texto común, sin código) que le enseña a Claude a hacer **una** tarea siempre igual. La escribís una vez y Faro "ya sabe" cómo armar el reporte.

---

## Paso 1.3 — Generar el primer reporte (desde las notas del pasante)

Alimentá a Faro con las **fuentes en crudo** de una semana de ejemplo. En una tarea del proyecto, escribí:

> *"Faro, en `reportes/semana-2026-05-25/fuentes/` están las notas en crudo que dejó el pasante (varios archivos, uno por portal). Leélas TODAS, consolidá la info por empresa y generá el reporte con la Skill `reporte-semanal`. Guardalo como `reporte-semana-2026-05-25.md` en esa misma carpeta de la semana. No inventes datos que no estén en las fuentes."*

Faro va a: leer todos los archivos de `fuentes/` → consolidar por empresa → escribir el `.md`.

> ✅ **🏁 Criterio de éxito (Milestone 1):** se generó el reporte con sufijo `-new` (ej. `reporte-semana-2026-05-25-new.md`), con todas las empresas, la tabla, las fuentes y la aclaración legal, **partiendo de varios archivos desordenados**. Si está, **Faro ya tomó forma.** *(Tip: compará tu resultado con el reporte de ejemplo de esa misma semana — el que no tiene el `-new`.)*

> 🛠️ **Si algo sale mal:**
>
> - *Ignoró alguna fuente* → recordale: *"leé TODOS los archivos de la carpeta `fuentes/`, no solo uno"*.
> - *No respeta la plantilla* → decile *"seguí exactamente la estructura de la Skill reporte-semanal"*.

---

# 🔎 Milestone 2 — Faro aprende a investigar
### *(Tools — búsqueda web · Connectors)*

**La idea:** hasta acá Faro dependía de las notas del pasante. Ahora va a **conseguir la info solo**: dado un ticker y un día, busca en una web y en un **servicio de datos al que te conectás**, y deja las fuentes en disco — reemplazando el copy-paste manual.

## Paso 2.1 — Conectarte a MT Newswires

La web abierta no alcanza: queremos una fuente confiable. En Cowork eso se resuelve **conectándote a un servicio** desde el directorio de Connectors, igual que conectás Gmail. Usamos **MT Newswires**, el proveedor de noticias de mercado al que **tenemos suscripción** (`https://www.mtnewswires.com`).

> ⭐ **Lo mejor:** **MT Newswires ya tiene un connector listo en Cowork** — aparece en el directorio de Connectors. No hay que crear ni configurar nada raro: lo buscás y lo conectás, como cualquier otra app.

**Cómo conectarte:**

1. Clickeá el botón **"+"** del campo de chat → **"Connectors"** (o andá a **Settings → Connectors**).
2. En el directorio, **buscá "MT Newswires"** y clickeá **"Connect"**.
3. Seguí el inicio de sesión / autorización con la suscripción.
4. Cuando figure **conectado**, dejalo **habilitado para Cowork**.

📄 Cómo funcionan los connectors: [documentación oficial](https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities).

**Probalo:** en una tarea, escribí:

> *"Conectándote a MT Newswires, traeme las últimas noticias de `YPF`. Mostrame qué devuelve."*

Si responde con noticias, ya está.

> 📌 **Por qué importa:** **no estás programando ni creando nada.** Te **conectás** a un servicio que ya existe —como cuando conectás Gmail— y Faro pasa a usar sus datos. Así se enchufan a Cowork muchos servicios: de datos, noticias, CRMs, etc.

> 🌐 **La otra fuente — la web:** el **precio** lo saca Faro de la página del ticker en Yahoo Finance con la búsqueda web ya incorporada; las **noticias**, de la sección de noticias de Yahoo Finance: `https://finance.yahoo.com/news/`. Para páginas que no cargan bien, sumá **Claude in Chrome** (el navegador) y pedile que "lea la página con el navegador".

---

## Paso 2.2 — Crear la Skill `buscar-accion` (ticker + semana → guarda fuentes)

1. En una tarea del proyecto, escribí `/skill-creator` y enviá.
2. Pegá la descripción:

> *"Quiero crear una Skill llamada `buscar-accion`. Recibe un **ticker** (ej. YPF) y una **semana** (fecha del lunes, ej. 2026-06-01). Busca info en DOS fuentes: (1) **Yahoo Finance** —precio de cierre aprox. del viernes y variación semanal— accediendo directamente con `web_fetch` a `https://finance.yahoo.com/quote/<TICKER>/`; y (2) **MT Newswires** para noticias, vía el connector conectado. Guarda en disco, dentro de `reportes/semana-AAAA-MM-DD/fuentes/`, **dos archivos acumulativos** (uno por fuente): `yahoo-finance.txt` con un bloque `-- TICKER --` por empresa, y `mt-newswires.txt` con una sección `=== TICKER ===` por empresa. Si el archivo ya existe (tiene datos de otro ticker), agrega el bloque al final sin pisar lo anterior. De MT Newswires solo guarda artículos donde el ticker es el foco principal. No inventa datos: si algo no está disponible, escribe 'n/d'. Conserva los links reales y marca los precios como aproximados."*

3. Revisá el borrador y confirmá.

> 📎 **Modelo a seguir:** la carpeta `reportes/semana-2026-06-01/fuentes/` muestra el tipo de material que esta Skill debe dejar en disco. Los dos archivos clave son `yahoo-finance.txt` (cotizaciones de los tres tickers en un solo archivo) y `mt-newswires.txt` (noticias de los tres tickers en un solo archivo).

> 📌 **Un detalle técnico importante:** para Yahoo Finance, la Skill usa **`web_fetch` directo** a `finance.yahoo.com` (no búsqueda web general). Esto da resultados más limpios y predecibles. Para MT Newswires, usa el **connector** configurado — es el mismo que conectaste en el Paso 2.1.

---

## Paso 2.3 — Que Faro arme las fuentes solo

En una tarea del proyecto, escribí:

> *"Faro, usando la Skill `buscar-accion`, buscá la info de la semana actual para `[EMPRESAS]` (una por una) y guardá las fuentes en una carpeta `fuentes/` nueva. Cuando termines, armá el reporte con la Skill `reporte-semanal` a partir de esas fuentes."*

Faro va a: por cada ticker (YPF, VIST, TS), buscar en Yahoo Finance + MT Newswires → acumular los datos en `fuentes/yahoo-finance.txt` y `fuentes/mt-newswires.txt` → y después generar el reporte con `reporte-semanal`.

> ✅ **🏁 Criterio de éxito (Milestone 2):** Faro llenó una carpeta `fuentes/` **partiendo de cero** (con datos que él mismo buscó) y con eso `reporte-semanal` armó el reporte — **sin que pegaras una sola noticia.** Faro dejó de depender del pasante: ahora su mesa de research investiga sola.

> 🛠️ **Si algo sale mal:**
>
> - *El connector no responde* → revisá en Settings → Connectors que MT Newswires esté conectado y habilitado para Cowork.
> - *Una página no carga* → pedile que "lea la página con el navegador (Claude in Chrome)".

---

# ⚙️ Milestone 3 — Faro trabaja solo
### *(Connectors — Gmail · Schedule)*

## Paso 3.1 — Conectar Gmail (Connector)

1. Andá a **Configuración (Settings) → Connectors**, o clickeá **"+"** → **"Connectors"**.
2. Buscá **Gmail** en el directorio y clickeá **"Connect"**.
3. Iniciá sesión con tu cuenta de Google y **autorizá** los permisos. Volvés a Cowork con Gmail conectado.

> 📌 **Por qué importa:** con Gmail conectado, Faro **distribuye** el reporte solo. Los connectors son la diferencia entre un asistente que *escribe* y uno que *actúa*.

---

## Paso 3.2 — Prueba de fuego: que Faro deje el reporte como borrador en Gmail

> *"Faro, tomá el último reporte semanal de la carpeta y dejalo como **borrador en Gmail** dirigido a `superboss@gmail.com`, con el asunto «Pulso semanal de mercado — [fecha]». Poné el resumen ejecutivo y la tabla en el cuerpo del correo, en un formato prolijo, listo para que el equipo lo lea con un clic."*

La primera vez, Claude puede pedirte permiso para usar Gmail: clickeá **"Allow"** (Permitir).

> ✅ **Mini-verificación:** revisá la carpeta **Borradores** de tu Gmail. Tiene que aparecer el email dirigido a `superboss@gmail.com`, listo para enviar. En el workshop, vos lo enviás: Faro dejó todo preparado.

> 📌 **Por qué borrador y no envío directo:** guardar como borrador (en lugar de enviar de una) te da control de revisión. Antes de que el correo llegue a tu jefe, pasás un ojo rápido. En producción podés cambiar esto y pedir que lo envíe directamente — pero el borrador es la práctica más segura para empezar.

---

## Paso 3.3 — Poner a Faro en piloto automático (Schedule)

Que cada lunes Faro **busque la info, arme el reporte, lo guarde y lo distribuya** — antes de la reunión de las 9:00.

1. En una tarea del proyecto, escribí `/schedule` y enviá. Se abre la Skill de programación.
2. Pegá la descripción de la tarea:

> *"Cada lunes a las 8:00: con la Skill `buscar-accion` buscá la info de la semana de `[EMPRESAS]` y guardá las fuentes; después con la Skill `reporte-semanal` armá el reporte, guardalo en la carpeta del proyecto; y por último dejá el reporte como **borrador en Gmail** dirigido a `superboss@gmail.com` con el asunto «Pulso semanal de mercado — [fecha]»."*

3. Claude puede hacerte preguntas de opción múltiple (frecuencia, horario). Confirmá: **Semanal (Weekly)**, **lunes**, **8:00**.
4. Cuando muestre el nombre, la frecuencia y qué hace, clickeá **"Schedule"** para confirmar.

**Alternativa por menú:** **"Scheduled"** en la barra izquierda → **"+ New task"** → completá Nombre, Descripción, el Prompt de arriba, Frecuencia *Weekly* y la carpeta del proyecto → **"Save"**.

> ⚠️ **Recordá:** las tareas programadas solo corren **con la computadora encendida y la app de Claude abierta**. Si estaba apagada, Cowork corre la tarea apenas la encendés y te avisa.

> ✅ **🏁 Criterio de éxito (Milestone 3):** (a) apareció el borrador en tu Gmail (Borradores), dirigido a `superboss@gmail.com`, y (b) en **"Scheduled"** aparece tu tarea «Pulso semanal», programada para los lunes. **Faro ya trabaja solo.**

> 🧪 **Tip para el workshop:** no esperes al lunes. En "Scheduled", entrá a la tarea y usá **"Run on demand"** (correr ahora) para demostrarla en vivo.

---

# 📣 Milestone 4 — Faro llega al equipo
### *(Artifacts — Live Artifacts · ShareDuo · Skills)*

**La idea:** el tablero no queda encerrado dentro de Cowork. La Skill **`publicar-tablero`** genera el HTML, crea un **Live Artifact nuevo por semana** (con ID `pulso-semanal-FECHA`) y lo comparte en modo **ShareDuo** — el sistema de sharing integrado en Cowork que genera una URL pública accesible para todo el equipo, sin que nadie necesite tener Cowork. La Skill también se engancha a la tarea del lunes para que el tablero se actualice solo.

## Paso 4.1 — ShareDuo: el sharing ya está en Cowork

> 💡 **Buena noticia: no hay nada que instalar ni registrar.** ShareDuo **no es un conector MCP externo**: es el sistema de sharing **integrado en Cowork** que se activa con una llamada a `update_artifact_settings` con `share="duo"`. La Skill lo hace sola. Vos no tocás nada de Settings para esto.

Lo que sí necesitás tener antes de seguir:
- Que exista al menos un **reporte semanal** en `reportes/` (del Milestone 1 o 2).
- Gmail conectado (del Milestone 3) — para el schedule.

## Paso 4.2 — Crear la Skill `publicar-tablero`

> 📦 **Ya existe una Skill de referencia** en la carpeta `skills/publicar-tablero/` — la podés usar directamente o como base para construirla con `/skill-creator`. En el workshop lo ideal es construirla, pero tenerla a mano evita trabas.

**¿Qué hace esta Skill?** Cuatro pasos en secuencia:

| Paso | Qué hace | Herramienta |
|------|----------|-------------|
| 1 | Lee el último `reporte-semana-*.md` y determina la `FECHA` de la semana | Carpeta del proyecto |
| 2 | Genera el HTML del tablero (tarjetas + tabla + resumen) y lo guarda como `tablero-FECHA.html` | Archivo local en outputs |
| 3 | Crea el Live Artifact `pulso-semanal-FECHA` en Cowork (o lo actualiza si ya existe para esa semana) | `mcp__cowork__create_artifact` / `update_artifact` |
| 4 | Activa el ShareDuo y confirma el link público | `mcp__cowork__update_artifact_settings` con `share="duo"` |

> 📌 **Un artifact por semana:** a diferencia de lo que podría esperarse, la Skill crea un **artifact nuevo por semana** (ej. `pulso-semanal-2026-06-01`, `pulso-semanal-2026-06-08`), no actualiza siempre el mismo. Así queda un **historial de tableros** accesible en Cowork — podés ver cualquier semana pasada desde la barra lateral.

**Para construirla con `/skill-creator`:**

1. En una tarea del proyecto, escribí `/skill-creator` y enviá.
2. Pegá esta descripción:

> *"Quiero crear una Skill llamada `publicar-tablero`. Lee los archivos `reporte-semana-*.md` de la carpeta del proyecto y tomá el MÁS RECIENTE. Extraé la fecha de la semana del nombre del archivo (`AAAA-MM-DD`). Con esa info hacé cuatro pasos en orden: **primero**, generá el HTML del tablero con un encabezado (fecha + resumen ejecutivo), una tarjeta por empresa (ticker, precio, variación en verde/rojo, ánimo, 2-3 noticias con link, a vigilar) y tabla resumen — diseño limpio tipo panel financiero, mismo diseño entre semanas; **segundo**, guardalo como archivo `tablero-FECHA.html`; **tercero**, verificá si ya existe el Live Artifact `pulso-semanal-FECHA` en Cowork: si existe, actualizalo; si no, crealo con ese ID; **cuarto**, activá el ShareDuo del artifact (share='duo') y devolvé el link público. No inventés nada: solo lo que está en el reporte. Footer obligatorio: 'Reporte interno e informativo; no constituye asesoramiento financiero.'"*

3. Revisá el borrador y confirmá.

> 📌 **Por qué una Skill y no a mano:** el tablero se mantiene al día porque Faro lo **regenera y republica** cada vez que corre esta Skill — por eso la enganchamos a la tarea del lunes.

## Paso 4.3 — Publicar el tablero por primera vez

En una tarea del proyecto, escribí:

> *"Faro, usá la Skill `publicar-tablero` con el último reporte. Generá el tablero, creá el artifact `pulso-semanal-FECHA` en Cowork, activá el ShareDuo y devolveme el link público."*

Guardá el link que te devuelve — esa es la URL del equipo para esa semana.

## Paso 4.4 — Engancharlo a la tarea del lunes

Para que se actualice solo, sumá `publicar-tablero` al final de la tarea programada del Milestone 3. Entrá a la tarea en **"Scheduled"** y editá su prompt para que **termine así**:

> *"…y por último, publicá el tablero de la semana con la Skill `publicar-tablero` y avisame si el artifact fue creado o actualizado y cuál es el link público."*

Ahora cada lunes, después de buscar la info, armar el reporte y dejar el borrador en Gmail, Faro **genera el HTML, crea el artifact de la semana en Cowork y activa el ShareDuo** — sin que vos toques nada.

> ✅ **🏁 Criterio de éxito (Milestone 4):** tenés un **link público** con el tablero de la semana (accesible para el equipo sin Cowork), el artifact `pulso-semanal-FECHA` aparece en la barra lateral de Cowork, y la tarea programada lo **regenera cada lunes** (probalo con "Run on demand"). **Faro ya vuela — y todo el equipo ve el tablero.**

> 🛠️ **Si algo sale mal:**
>
> - *El tablero está vacío* → confirmá que exista al menos un `reporte-semana-*.md` en la carpeta.
> - *El artifact no aparece en Cowork* → verificá que el paso de `create_artifact` haya corrido sin error; si la carpeta de sesión no tiene permisos de escritura, la Skill falla al guardar el HTML.
> - *No se actualizó tras correr el schedule* → revisá que el prompt de la tarea incluya el paso de `publicar-tablero`.
> - *Querés mantener una URL fija entre semanas* → cambiá la Skill para que siempre use el mismo ID (ej. `pulso-semanal`) en lugar de `pulso-semanal-FECHA`; perdés el historial pero la URL no cambia.

---

## 🔄 El círculo completo

Con los cuatro milestones listos, el desafío laboral queda resuelto — y funcionando solo:

`Lunes 8:00` → **Schedule** dispara la tarea → la Skill **`buscar-accion`** hace `web_fetch` a **Yahoo Finance** y consulta **MT Newswires** vía connector, guardando `yahoo-finance.txt` y `mt-newswires.txt` en `fuentes/` → la Skill **`reporte-semanal`** consolida todo en el **reporte `.md`** dentro del **Project** → **Gmail** lo deja como **borrador** listo para el equipo → la Skill **`publicar-tablero`** genera el HTML, crea el **Live Artifact** `pulso-semanal-FECHA` en Cowork y activa el **ShareDuo** integrado, publicando el tablero en una URL pública.

Seis piezas de Cowork — **Projects, Instructions, Skills, Connectors, Schedule y Artifacts** — más **`web_fetch` a Yahoo Finance, MT Newswires vía connector, Gmail y ShareDuo integrado**. Y vos, con la mañana del lunes libre.

---

## 🎤 Guía rápida para el facilitador

| Momento | Qué mostrar en vivo | Concepto que "cae" |
|---------|---------------------|--------------------|
| M1 · Proyecto + Instrucciones | Crear el proyecto y leer las instrucciones | "Cowork recuerda el contexto sin que yo lo repita" |
| M1 · Skill `reporte-semanal` | `/skill-creator` y abrir el `SKILL.md`; juntar varias fuentes | "Una Skill convierte el caos (muchos archivos) en un entregable" |
| M2 · Conectarte a MT Newswires | Conectar MT Newswires y pedirle noticias de un ticker | "Conecto servicios externos sin programar" |
| M2 · Skill `buscar-accion` | Ver aparecer la carpeta `fuentes/` sola | "Faro reemplaza el copy-paste del pasante" |
| M3 · Gmail | El email llegando a la bandeja | "Connectors = Claude que actúa en mis apps" |
| M3 · Schedule | "Run on demand" para no esperar al lunes | "Puedo delegar trabajo recurrente de oficina" |
| M4 · ShareDuo integrado | Mostrar que no hay nada que instalar: ShareDuo es `update_artifact_settings(share="duo")` | "Cowork tiene sharing incorporado — no necesito registrar nada" |
| M4 · Skill `publicar-tablero` | Correr la Skill, ver el artifact `pulso-semanal-FECHA` crearse y el link aparecer | "La Skill genera el HTML, lo registra en Cowork Y lo publica afuera — en un solo paso" |
| M4 · Tablero en el schedule | Mostrar la barra lateral con el historial de artifacts por semana | "Cada lunes Faro crea un artifact nuevo; el equipo siempre tiene el de la semana y el historial queda guardado" |

**Errores comunes a anticipar:**

- Olvidarse de habilitar la **búsqueda web** → Faro no puede complementar con Yahoo Finance en el Milestone 2.
- **MT Newswires** sin conectar → `buscar-accion` no tiene noticias; avisará pero seguirá solo con Yahoo.
- Confundir los archivos de fuentes: `buscar-accion` genera **`.txt`**, no `.md`. `reporte-semanal` los lee desde `fuentes/*.txt`.
- Olvidar el **sufijo `-new`** del reporte: `reporte-semanal` nunca pisa el original; buscar el archivo `-new` para ver el resultado.
- Cerrar la app y esperar que la tarea programada corra igual → no corre; necesita la app abierta.
- Esperar que el tablero se refresque solo leyendo el disco → no puede; lo actualiza la Skill `publicar-tablero` (idealmente desde el schedule).
- Olvidarse de sumar `publicar-tablero` al prompt de la tarea programada → el tablero no se refresca los lunes.
- Querer hacer el Milestone 4 sin ningún reporte generado → la Skill no tiene datos para generar el HTML.
- **Buscar "ShareDuo" en Connectors** para registrarlo → no hace falta; el sharing ya está integrado en Cowork vía `update_artifact_settings`.

**Timing sugerido (~130 min):** Setup 10' · N1 25' · N2 35' · N3 20' · N4 30' · Cierre 10'.

**Gancho de cierre:** *"Acaban de automatizar un reporte que les iba a comer la mañana de cada lunes. ¿Qué otra tarea recurrente de su trabajo podrían delegarle a su propio Faro?"*

---

## 📚 Fuentes (documentación oficial de Cowork)

- [Get started with Claude Cowork](https://support.claude.com/en/articles/13345190-get-started-with-claude-cowork)
- [Organize your tasks with projects in Cowork](https://support.claude.com/en/articles/14116274-organize-your-tasks-with-projects-in-cowork)
- [Schedule recurring tasks in Claude Cowork](https://support.claude.com/en/articles/13854387-schedule-recurring-tasks-in-claude-cowork)
- [How to create custom skills](https://support.claude.com/en/articles/12512198-how-to-create-custom-skills)
- [Use connectors to extend Claude's capabilities](https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities)
- [Browse skills, connectors, and plugins in one directory](https://support.claude.com/en/articles/14328846-browse-skills-connectors-and-plugins-in-one-directory)
- [Use live artifacts in Claude Cowork](https://support.claude.com/en/articles/14729249-use-live-artifacts-in-claude-cowork)
