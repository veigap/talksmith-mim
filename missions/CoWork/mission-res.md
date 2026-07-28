# 🛰️ Solución paso a paso — "Faro, la mesa de inteligencia de mercado de Atlas"

> Guía de resolución de la misión descrita en `mission.md` (versión de 2 partes y 6 milestones). Pensada para que el facilitador la conduzca en vivo y para que cualquier participante **no técnico** la replique. Incluye los **prompts exactos** para copiar y pegar (en *cursiva con comillas*) y lo que hay que **clickear**.
>
> 💡 Convención: donde veas `[EMPRESAS]`, va la lista de **las 3 acciones que el jefe pidió seguir**: `YPF, VIST, TS`. Donde veas `[TICKER]`, va una sola (ej. `YPF`). Podés cambiarlas si adaptás la misión a tu propio contexto laboral.
>
> 🎭 El encuadre: trabajás en **Atlas**, una empresa de insumos de perforación para Vaca Muerta. Tu jefe quiere un **pulso semanal de mercado** sobre YPF, Vista y Tenaris, en dos entregas: un **email cada lunes** y un **tablero** siempre al día. En el workshop el email te lo enviás a vos mismo (`superboss@gmail.com` como destinatario simbólico del jefe).

---

## 🧰 Antes de empezar (setup detallado)

**Para la Parte 1 (el chat):**

1. Entrá a **claude.ai** en el navegador con tu cuenta (plan pago).
2. Verificá la **búsqueda web**: Configuración → Capacidades. Tiene que estar activa.
3. Tené a mano una cuenta de **Gmail**.

**Para la Parte 2 (Cowork):**

1. Abrí la **app de escritorio de Claude** y verificá que esté en la última versión (si aparece "Setting up Claude's workspace", es normal: se está actualizando).
2. Clickeá la pestaña **"Cowork"** (junto a "Chat" y "Code").
3. Confirmá **Code execution** activo (Configuración → Capacidades): lo piden las Skills del Milestone 6.
4. Creá (si no existe) una carpeta, por ejemplo `Documentos/Faro-Mercado`, y copiá adentro la carpeta `reportes/` de los materiales.

> 📁 **Material de ejemplo:** en `reportes/` hay una subcarpeta por semana; adentro, `fuentes/` (las notas del pasante, un archivo por portal) lado a lado con el reporte final (`.md`), que funciona de "respuesta correcta".
>
> 🧹 **Misión 0:** si es tu primer contacto con Cowork, antes del Milestone 3 hacé la **Misión 0** (`intro-escritorio-pasante.md`): 20-30 minutos guiados sobre la carpeta `escritorio-del-pasante/`, regenerable con `python3 gen_escritorio_pasante.py`.
>
> 🧩 **Para el facilitador:** si tenés las tres Skills de referencia armadas (`reporte-semanal`, `buscar-accion`, `publicar-tablero`), dejalas a mano para el Milestone 6 por si alguien se traba. El ideal del workshop es que cada participante las construya.

---

# 🧩 PARTE 1 — Faro en el chat

# 🔎 Milestone 1 — Faro se conecta
### *(Conectores: búsqueda web · noticias · Gmail)*

## Paso 1.1 — El pulso con búsqueda web

En claude.ai, con la búsqueda activada, escribí:

> *"Armame el pulso de mercado de esta semana para `[EMPRESAS]`: qué se movió, qué noticias salieron y qué hay que vigilar. Citá las fuentes de cada dato."*

Mirá dos cosas: el indicador de **"buscando..."** mientras trabaja, y las **fuentes citadas** en la respuesta. Ese es tu punto de control de que no respondió de memoria.

## Paso 1.2 — Conectar MT Newswires

La web abierta no alcanza: queremos una fuente confiable de noticias de mercado. Usamos **MT Newswires**, el proveedor al que tenemos suscripción (`https://www.mtnewswires.com`).

1. Andá a la **biblioteca de conectores** (Configuración → Conectores, o el "+" del campo de chat).
2. **Buscá "MT Newswires"** y clickeá **"Connect"**.
3. Completá la autorización con la suscripción y verificá que figure **conectado**.

**Probalo:**

> *"Conectándote a MT Newswires, traeme las últimas noticias de `YPF`. Mostrame qué devuelve."*

## Paso 1.3 — Conectar Gmail y probar una lectura

1. En la misma biblioteca, buscá **Gmail** → **"Connect"** → autorizá con tu cuenta de Google.
2. Probá una lectura:

> *"¿Qué mails de esta semana quedaron sin responder en mi bandeja?"*

## Paso 1.4 — El pulso, ahora con todo conectado

Repetí el pedido del Paso 1.1. Compará la respuesta: ahora combina búsqueda web + MT Newswires, con citas.

> ✅ **🏁 Criterio de éxito (Milestone 1):** el chat arma el pulso de la semana con precios y noticias **citadas de fuentes reales**, sin que pegues una sola noticia a mano.

> 🛠️ **Si algo sale mal:**
>
> - *No aparece "buscando..."* → la búsqueda web está apagada; activala en Configuración → Capacidades.
> - *El conector no responde* → revisá en la biblioteca que figure conectado y autorizado.

---

# ⚙️ Milestone 2 — Faro trabaja solo
### *(Tareas programadas · conectores que actúan)*

## Paso 2.1 — Prueba de fuego: el borrador en Gmail

> *"Tomá el pulso de esta semana y dejalo como **borrador en Gmail** dirigido a `superboss@gmail.com`, con el asunto «Pulso semanal de mercado — [fecha]». Poné el resumen y los datos clave en el cuerpo, en un formato prolijo. No lo envíes: dejalo como borrador."*

La primera vez puede pedirte permiso para usar Gmail: clickeá **"Allow"**.

> 📌 **Por qué borrador y no envío directo:** un mail enviado automáticamente sin revisión humana puede generar muchos problemas. El borrador te da el control: revisás y enviás vos.

**Verificá:** en la carpeta **Borradores** de tu Gmail tiene que estar el email.

## Paso 2.2 — Programar la tarea del lunes

En claude.ai, pedí:

> *"Programá una tarea que corra **cada lunes a las 8:00**: armar el pulso de mercado de `[EMPRESAS]` con búsqueda web y MT Newswires, y dejarlo como borrador en Gmail dirigido a `superboss@gmail.com` con el asunto «Pulso semanal de mercado — [fecha]». Listo antes de la reunión de las 9:00."*

Confirmá frecuencia (**semanal**), día (**lunes**) y horario (**8:00**) si te los pregunta, y verificá que la tarea aparezca en tu **lista de tareas programadas**.

## Paso 2.3 — Correrla ahora

No esperes al lunes: ejecutala **a demanda** desde la lista de tareas para verla funcionar en vivo.

> ⚠️ **¿Dónde corre?** Si tu cuenta ya tiene la beta de ejecución en la nube (despliegue gradual, primero Max), la tarea corre sin tu computadora. Si no, corre **local**: computadora prendida y sesión activa, o la corrida se saltea y se recupera al volver.

> ✅ **🏁 Criterio de éxito (Milestone 2):** el borrador apareció en Gmail **y** la tarea figura programada para los lunes. **El jefe ya tiene la primera de sus dos entregas: el email semanal.** Fin de la Parte 1.

---

# 🧩 PARTE 2 — Faro en Cowork

*Arranca de la herencia del pasante en `reportes/`; no hace falta haber resuelto la Parte 1. Si venís de ella, MT Newswires y Gmail ya están autorizados.*

# 🛠️ Milestone 3 — Faro toma forma
### *(Projects · Instrucciones · archivos .md)*

## Paso 3.1 — Levantar la base: el Project

1. En el panel izquierdo de Cowork, buscá **"Projects"** y clickeá **"+"**.
2. Elegí **"Start from scratch"**.
3. Completá:
   - **Nombre:** `Inteligencia de Mercado Semanal`
   - **Ubicación:** tu carpeta `Documentos/Faro-Mercado` (elegida con el explorador de archivos).
4. En el campo de **Instrucciones** del proyecto, pegá esto:

> *"Sos **Faro**, el analista de mercado del equipo de Atlas, una empresa de insumos de perforación para Vaca Muerta. Preparás un pulso semanal para colegas no técnicos (incluido el jefe del área), que se lee en 2 minutos antes de la reunión de los lunes.*
> *Seguís estas empresas: `[EMPRESAS]`.*
> *Escribís en español, claro y breve, sin jerga financiera complicada. Si usás un término técnico, lo explicás en una línea.*
> *Tus reportes son informativos y para uso interno: NO son recomendaciones de inversión ni asesoramiento financiero. Siempre incluís esa aclaración al final.*
> *Para armar cada reporte partís de las notas en crudo de la carpeta `fuentes/` de la semana (y, más adelante, de lo que vos mismo busques). Si un dato no está, lo decís en lugar de inventarlo.*
> *La información de trabajo va siempre en archivos Markdown: guardás cada reporte como `reporte-semana-AAAA-MM-DD.md`, junto a la carpeta `fuentes/` de esa semana."*

5. Clickeá **"Create"**.

## Paso 3.2 — La herencia del pasante, a `.md`

> *"Faro, en `reportes/semana-2026-05-25/fuentes/` están las notas en crudo que dejó el pasante, un archivo por portal. Convertilas a archivos `.md` prolijos, uno por fuente, sin perder información ni links. Trabajamos siempre en Markdown; el formato final se genera al último."*

## Paso 3.3 — El primer reporte, pedido en conversación

Todavía sin automatizar nada (las Skills llegan en el Milestone 6):

> *"Faro, leé TODAS las fuentes de `reportes/semana-2026-05-25/` (la info de una misma empresa puede estar repartida entre varios archivos), consolidá por empresa y generá el reporte de esa semana siguiendo EXACTAMENTE la estructura del reporte de ejemplo (`reporte-semana-2026-05-25.md`): título, resumen ejecutivo, una sección por empresa (precio aproximado, variación, 2-3 noticias con contexto, ánimo, a vigilar), tabla resumen, fuentes principales y la aclaración legal. La empresa más relevante va primera (⭐). No inventes datos: si falta algo, decílo. **Guardalo con sufijo `-new`** para no pisar el original."*

> ✅ **🏁 Criterio de éxito (Milestone 3):** el Project existe con sus Instrucciones, y el `reporte-semana-2026-05-25-new.md` es equivalente al de ejemplo: mismo formato, todas las empresas, la tabla, las fuentes y la aclaración legal. Compará los dos archivos lado a lado.

> 🛠️ **Si algo sale mal:**
>
> - *Ignoró alguna fuente* → *"leé TODOS los archivos de la carpeta `fuentes/`, no solo uno"*.
> - *No respeta el formato* → *"seguí exactamente la estructura del reporte de ejemplo de esa misma semana"*.

---

# ⏰ Milestone 4 — El lunes se arma solo
### *(Schedule en Cowork · conectores dentro del Project)*

## Paso 4.1 — Los conectores, ahora en Cowork

Verificá en la biblioteca de conectores que **MT Newswires** y **Gmail** estén conectados y habilitados para Cowork (si venís de la Parte 1 ya están; si no, es buscar + Connect + autorizar). Búsqueda web activa.

> 🌐 **Claude in Chrome (opcional):** para páginas que renderizan con JavaScript (como Yahoo Finance), Cowork puede usar el navegador real. Chrome + extensión habilitada: [instrucciones oficiales](https://support.anthropic.com/en/articles/12012173-getting-started-with-claude-for-chrome).

## Paso 4.2 — Que Faro investigue solo

> *"Faro, para la semana actual y para cada ticker de `[EMPRESAS]`: buscá el precio de cierre aproximado y la variación semanal en `https://finance.yahoo.com/quote/<TICKER>/`, y las noticias en MT Newswires vía el conector. Guardá todo en disco dentro de `reportes/semana-AAAA-MM-DD/fuentes/`, en dos archivos acumulativos: `yahoo-finance.txt` (un bloque por ticker) y `mt-newswires.txt` (una sección por ticker). Si el archivo ya existe, agregá al final sin pisar. No inventes: si algo no está, escribí 'n/d'. Conservá los links reales."*

**Verificá:** la carpeta `fuentes/` de la semana en curso se reconstruyó **partiendo de cero**, sin pasante.

## Paso 4.3 — Programar el lunes desde la pestaña Scheduled

1. En la barra izquierda, clickeá **"Scheduled"** → **"+ New task"**.
2. Completá nombre (`Pulso semanal`), frecuencia **Weekly**, día **lunes**, hora **8:00**, y la carpeta del proyecto.
3. En el prompt de la tarea, pegá:

> *"Cada lunes a las 8:00: buscá la info de la semana de `[EMPRESAS]` (Yahoo Finance + MT Newswires) y guardá las fuentes en `fuentes/`; después consolidá el reporte de la semana en Markdown siguiendo el formato del reporte de ejemplo y guardalo en el Project; y por último dejá el reporte como **borrador en Gmail** dirigido a `superboss@gmail.com` con el asunto «Pulso semanal de mercado — [fecha]»."*

4. **"Save"**, y probala con **"Run now"** para no esperar al lunes.

> ⚠️ **Recordá:** estas tareas usan archivos de tu disco, así que corren **local**: computadora prendida y app abierta, o la corrida se saltea y se recupera al volver. Las notebooks se suspenden solas; revisá la configuración de energía.

> ✅ **🏁 Criterio de éxito (Milestone 4):** una corrida completa, sin tocar nada, dejó las fuentes en disco, el reporte en el Project y el borrador en Gmail.

---

# 📊 Milestone 5 — El tablero del jefe
### *(Artifacts y Live Artifacts)*

> ⚠️ **Estado real de la herramienta:** hoy los Live Artifacts son **locales** (viven en tu computadora) y **todavía no son compartibles** por URL (está en el roadmap). El tablero se muestra desde tu máquina o se exporta su HTML para mandarlo. Nada de esto lo cambia una Skill ni una configuración: es el estado del producto.

## Paso 5.1 — Crear el tablero

> *"Faro, creá un **Live Artifact** llamado `pulso-semanal-[FECHA]` con el tablero de la semana, usando el último reporte como fuente. Diseño según el boceto del jefe (`mockup-tablero.png`): encabezado con la fecha y el resumen, una tarjeta por empresa (ticker, precio, variación en verde/rojo, ánimo, 2-3 noticias con link, a vigilar) y la tabla resumen. Footer obligatorio: «Reporte interno e informativo; no constituye asesoramiento financiero». No inventes: solo lo que está en el reporte."*

## Paso 5.2 — Verificar el comportamiento "live"

1. Abrí la pestaña **"Live artifacts"** y entrá al tablero: al abrirse se **refresca** con los datos actuales de tus apps conectadas.
2. Fijate que el artifact quedó con la fecha en el nombre: un artifact nuevo por semana deja **historial** navegable.

## Paso 5.3 — Engancharlo a la tarea del lunes

Entrá a la tarea en **"Scheduled"** y editá el prompt para que **termine así**:

> *"…y por último, actualizá el tablero de la semana: creá el Live Artifact `pulso-semanal-[FECHA]` con el último reporte, con el diseño del boceto del jefe."*

> ✅ **🏁 Criterio de éxito (Milestone 5):** el tablero respeta el boceto, la corrida del lunes lo regenera, y podés mostrárselo al jefe desde tu máquina (o exportar el HTML) sin armarlo a mano.

> 🛠️ **Si algo sale mal:**
>
> - *El tablero está vacío* → confirmá que exista al menos un `reporte-semana-*.md` en la carpeta.
> - *Alguien pide "la URL pública"* → no existe todavía; es la limitación documentada de Live Artifacts. Exportá el HTML si hace falta compartir.

---

# 🧰 Milestone 6 — Faro se vuelve reutilizable
### *(Skills · una mirada a Subagentes y Plugins)*

**La idea:** todo lo que le pediste más de una vez en los milestones 3 a 5, ahora lo escribís una vez. Requisito: **Code execution** activo.

## Paso 6.1 — Skill `reporte-semanal` con `/skill-creator`

1. En una tarea del proyecto, escribí **`/skill-creator`** y enviá (tipeando `/` ves los comandos disponibles).
2. Pegá la descripción:

> *"Quiero crear una Skill llamada `reporte-semanal`. Su entrada es la carpeta `fuentes/` de una semana, con varios archivos en crudo, uno por portal (la info de una misma empresa puede estar repartida). Debe leerlos TODOS, consolidar por empresa y generar un Markdown con esta estructura exacta: 1) título «Pulso semanal de mercado — [fecha]»; 2) resumen ejecutivo de 3-4 líneas; 3) una sección por empresa (nombre y ticker, precio aproximado y variación, 2-3 noticias con contexto, ánimo, a vigilar); 4) tabla resumen (ticker, variación %, ánimo); 5) fuentes principales; 6) aclaración legal «Reporte interno e informativo; no constituye asesoramiento financiero». La empresa más relevante primera (⭐). No inventa datos. **Guarda con sufijo `-new`.**"*

3. Revisá el `SKILL.md` que propone y confirmá.
4. **La trampa del Save:** andá a **Configuración → Habilidades** y verificá que la Skill quede **guardada y habilitada** en la lista. Sin eso, "no funciona".

> 💡 Los otros caminos del menú **Agregar** (Configuración → Habilidades): "Crear con Claude" (ida y vuelta de chat) y "Escribir las instrucciones" directo en la UI. "Subir una habilidad" **importa** una Skill existente desde su ZIP; sirve para traer las de un colega.

## Paso 6.2 — Skill `buscar-accion`

Repetí con `/skill-creator`:

> *"Quiero crear una Skill llamada `buscar-accion`. Recibe un ticker y una semana (fecha del lunes). Busca en DOS fuentes: Yahoo Finance (precio de cierre aproximado y variación, con `web_fetch` directo a `https://finance.yahoo.com/quote/<TICKER>/`) y MT Newswires (noticias, vía el conector). Guarda en `reportes/semana-AAAA-MM-DD/fuentes/` dos archivos acumulativos: `yahoo-finance.txt` (un bloque por ticker) y `mt-newswires.txt` (una sección por ticker); si existen, agrega al final sin pisar. Solo artículos donde el ticker es el foco. No inventa: 'n/d' si falta. Conserva links reales."*

## Paso 6.3 — Skill `publicar-tablero`

> *"Quiero crear una Skill llamada `publicar-tablero`. Lee los `reporte-semana-*.md` de la carpeta y toma el MÁS RECIENTE; extrae la fecha del nombre. Genera el tablero según el boceto del jefe (encabezado, tarjeta por empresa, tabla resumen, footer legal) y crea o actualiza el Live Artifact `pulso-semanal-FECHA`. Un artifact por semana, para conservar el historial. No inventa nada: solo lo que está en el reporte."*

## Paso 6.4 — La tarea del lunes, ahora sobre Skills

Editá el prompt de la tarea programada para que use las tres:

> *"Cada lunes a las 8:00: con la Skill `buscar-accion` buscá la info de la semana de `[EMPRESAS]` y guardá las fuentes; con la Skill `reporte-semanal` consolidá el reporte y guardalo en el Project; dejá el reporte como borrador en Gmail dirigido a `superboss@gmail.com`; y con la Skill `publicar-tablero` actualizá el tablero de la semana."*

Corrida de prueba con **"Run now"**.

## Paso 6.5 — Mirar adentro de un SKILL.md

Abrí el `SKILL.md` de `reporte-semanal` y reconocé la anatomía de la clase: **metadata** arriba (la `description` decide cuándo se activa) e **instrucciones** en Markdown abajo.

> ✅ **🏁 Criterio de éxito (Milestone 6):** la tarea del lunes corre apoyada en las tres Skills, las tres figuran habilitadas en la lista de Habilidades, y cualquier compañero con tu Project puede disparar el flujo sin que le expliques nada.

> 📦 **Y después (fuera de la misión):** si esto lo usara todo el equipo, las tres Skills viajarían dentro de un **Plugin**; si una sub-tarea fuera pesada, un **Subagente** la correría aparte.

---

## 🔄 El círculo completo

`Lunes 8:00` → **Schedule** dispara la tarea → la Skill **`buscar-accion`** consulta Yahoo Finance y MT Newswires y guarda `fuentes/` → la Skill **`reporte-semanal`** consolida el **reporte `.md`** en el **Project** → **Gmail** recibe el **borrador** para el equipo → la Skill **`publicar-tablero`** actualiza el **Live Artifact** `pulso-semanal-FECHA`.

Las piezas, en el orden en que la clase las enseñó: **Conectores y Tareas programadas** en el chat; **Projects, Instrucciones, archivos .md, Schedule, Live Artifacts y Skills** en Cowork. Y vos, con la mañana del lunes libre.

---

## 🎤 Guía rápida para el facilitador

| Momento | Qué mostrar en vivo | Concepto que "cae" |
|---------|---------------------|--------------------|
| P1·M1 búsqueda web | La misma pregunta con búsqueda apagada y prendida; señalar las citas | "El chat puede responder de memoria o con información real" |
| P1·M1 conectores | Conectar MT Newswires desde la biblioteca y pedir noticias | "Me conecto a servicios sin programar" |
| P1·M2 borrador | El borrador apareciendo en Gmail | "Los conectores también actúan; el humano revisa antes de enviar" |
| P1·M2 schedule | Correr la tarea a demanda | "Me suscribo al resultado en vez de pedirlo cada lunes" |
| Corte | La placa de fin de parte 1 + la Misión 0 al volver | "Hasta acá, todo en el chat de siempre" |
| P2·M3 Project | Crear el Project y leer las Instrucciones | "El contexto se escribe una vez" |
| P2·M3 .md | La herencia convertida y el reporte `-new` vs el de ejemplo | "Se trabaja en .md; el formato final, al último" |
| P2·M4 Schedule | "Run now" y ver aparecer fuentes + reporte + borrador | "El agente trabaja sobre mis carpetas, solo" |
| P2·M5 tablero | El Live Artifact abriéndose y refrescándose | "El resultado vivo; compartir por URL está en el roadmap, ser honesto" |
| P2·M6 Skills | `/skill-creator` en vivo + la compuerta del Save en Habilidades | "Todo lo que explico más de una vez es una Skill" |

**Errores comunes a anticipar:**

- Búsqueda web apagada → el Milestone 1 responde de memoria y sin citas.
- MT Newswires sin conectar → sigue solo con Yahoo; lo avisa.
- Esperar que la tarea local corra con la app cerrada → no corre; se recupera al volver.
- `buscar-accion` genera **`.txt`** en `fuentes/`; el reporte consolidado es el `.md`.
- Olvidar el sufijo **`-new`** → el reporte de ejemplo se pisa y se pierde la "respuesta correcta".
- Crear la Skill y no pasar por **Guardar/Habilitar** en la lista de Habilidades → "no funciona".
- Pedir "la URL pública del tablero" → no existe todavía; exportar el HTML si hace falta compartir.
- Hacer el Milestone 5 sin ningún reporte generado → el tablero no tiene datos.

**Timing sugerido (clase de 2 bloques):** Parte 1: setup 5' · M1 20' · M2 15'. Corte. Parte 2: Misión 0 25' · M3 25' · M4 20' · M5 15' · M6 25' · Cierre 10'.

**Gancho de cierre:** *"Acaban de automatizar un reporte que les iba a comer la mañana de cada lunes. ¿Qué otra tarea recurrente de su trabajo podrían delegarle a su propio Faro?"*

---

## 📚 Fuentes (documentación oficial)

- [Get started with Claude Cowork](https://support.claude.com/en/articles/13345190-get-started-with-claude-cowork)
- [Organize your tasks with projects in Cowork](https://support.claude.com/en/articles/14116274-organize-your-tasks-with-projects-in-cowork)
- [Schedule recurring tasks in Claude Cowork](https://support.claude.com/en/articles/13854387-schedule-recurring-tasks-in-claude-cowork)
- [Release notes 7-jul-2026: tareas programadas en la nube (beta)](https://support.claude.com/en/articles/12138966)
- [How to create custom skills](https://support.claude.com/en/articles/12512198-how-to-create-custom-skills)
- [Use connectors to extend Claude's capabilities](https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities)
- [Use live artifacts in Claude Cowork](https://support.claude.com/en/articles/14729249-use-live-artifacts-in-claude-cowork)
