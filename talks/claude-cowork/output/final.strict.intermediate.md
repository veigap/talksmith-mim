# Agenda

**Sections (in delivery order):**

- 1. De chat a agente: dónde encaja Cowork
- 2. Lo básico: interfaz, Instrucciones y Projects
- 3. Extender Cowork: Skills y el rol de los archivos MD / metadata
- 4. Conectar y automatizar: Connectors/MCP y Schedule
- 5. Compartir resultados: Live Artifacts
- 6. Advanced: Subagentes y Plugins
---

# De chat a agente: dónde encaja Cowork

---

## Las tres superficies de Claude

- Mismos modelos, distinta superficie: las tres caras — **Web/Chat**, **Claude Code** y **Cowork** — corren sobre **los mismos modelos Claude**. El matiz importa: **Cowork está construido sobre las mismas bases que Claude Code** (el **Claude Agent SDK**), así que Code y Cowork comparten el mismo *engine de agente* — los mismos archivos, las mismas Skills, el mismo MCP y el mismo loop de plan → aprobar → redirigir. **Web/Chat** es ese mismo modelo en una **superficie de chat**, no el loop agéntico completo.
- **Web/Chat** — navegador o app, sin instalar; chat, preguntas y tareas puntuales; público: todos.
- **Claude Code** — app de escritorio (pestaña Code + terminal); escribir, editar y publicar código; público: perfiles técnicos / developers.
- **Cowork** — app de escritorio (pestaña Cowork), GUI sin terminal; trabajo de varios pasos sobre archivos reales; público: knowledge workers sin terminal. **Esta charla vive acá.**

![Las tres superficies de Claude sobre los mismos modelos](images/s1-1-1-tres-superficies-claude.png)

### Notes

Abrir ubicando el terreno: no son tres productos distintos, es el mismo agente con tres caras. Lo único que cambia es la superficie y para quién está pensada. Dejar claro desde el minuto cero que hoy trabajamos en Cowork — la cara pensada para quien no vive en una terminal. Claude Code aparece solo como contraste; no vamos a entrar en sus internals. Tiempo objetivo: ~5 min.
---

## El superpoder de Cowork: la herramienta de propósito general del knowledge worker

- **La idea grande.** **Cowork** es la **herramienta de propósito general del knowledge worker** — de quien *no* programa. No un asistente de una tarea puntual: una herramienta horizontal para casi cualquier trabajo de conocimiento. Sin base técnica: el "lenguaje de programación" es el español.
- **La analogía que "pega" — "el nuevo Excel"** *(encuadre de analistas / industria, no un claim de Anthropic).* Así como Excel fue ~40 años la habilidad base del trabajo de oficina, las herramientas agénticas apuntan a ser **la nueva habilidad base**.
- **El encuadre oficial de Anthropic:** Cowork como **"Claude Code para el resto de tu trabajo"**.
- **Por qué te importa (bioingeniería).** La habilidad base del trabajo del conocimiento se redefine ahora; llegar temprano es ventaja concreta y portable.

![De Excel a herramientas agenticas: la nueva habilidad base](images/s1-2-1-excel-a-agentico.png)

### Notes

Este es el beat de "¿y a mí por qué me importa?", colocado justo después de ubicar las tres superficies. Hasta acá la audiencia sabe *qué* es Cowork; esta slide responde *por qué debería invertir su atención*. Tono motivacional y de alto nivel — la mecánica viene después.

El gancho que mejor funciona es la analogía del Excel, pero hay que decirla con cuidado: durante unas cuatro décadas, saber Excel fue *la* habilidad base del trabajo de oficina — no programabas, pero con Excel resolvías el 80% del trabajo de conocimiento. La tesis de varios analistas de la industria es que las herramientas agénticas (Claude Code para los que programan, Cowork para los que no) están en camino de ser esa nueva habilidad base. Atribuirlo explícitamente como encuadre de analistas/industria — "hay quien lo llama el nuevo Excel" — y NO como un claim oficial de Anthropic.

Lo que sí es de Anthropic, y conviene citarlo como su framing propio, es "Claude Code para el resto de tu trabajo": la idea de que cualquier knowledge worker sienta con Cowork lo que los ingenieros ya sienten con Claude Code. Subrayar que Cowork no salió de la nada — es la generalización de algo que ya funcionó muy bien primero con developers.

Cerrar aterrizándolo en la audiencia: ellos son ingenieros biomédicos, no necesariamente developers, y exactamente por eso esto les sirve — la habilidad base del trabajo del conocimiento se está redefiniendo ahora mismo, y llegar temprano es ventaja. Después de este beat motivacional pasamos a la mecánica: cómo se delega de verdad (slide 1.3). Tiempo objetivo: ~4-5 min.
---

## De chat a agente: el cambio de paradigma

- La frase que resume toda la sesión: **"Dejás de tipear un mensaje a la vez y empezás a entregar un resultado."** El agente lo planifica, trabaja sobre tus archivos reales, y vos lo guiás — en lugar de hacer cada paso vos mismo.
- Cómo lo describe la propia Anthropic: trabajar con Cowork *"se parece menos a una sesión de chat y más a asignarle tareas a un colega"* ("less like a chat session and more like assigning tasks to a colleague"). Esa es exactamente la mudanza de paradigma de esta slide.
- Chatear vs delegar (no son dos productos, son dos formas de trabajar):

| | Chatear | Delegar a un agente |
|---|---|---|
| Cómo trabajás | Un mensaje a la vez | Describís un resultado |
| Los pasos | Los hacés vos | El agente planifica y ejecuta |
| La salida | Texto en la ventana | Archivos en tu disco |
| Tu rol | Tipear el próximo prompt | Leer el plan, guiar a mitad de camino |

![De chat a agente: el cambio de paradigma](images/s1-3-1-chat-vs-agente.png)

### Notes

Este es el concepto-ancla de la charla. Si se llevan una sola idea, que sea esta: el valor no está en escribir mejores mensajes, está en aprender a delegar un resultado y guiar el proceso. Usar la tabla para hacerlo concreto: la salida deja de ser texto en una ventana y pasa a ser archivos reales en tu disco. Anticipar la misión: vamos a "contratar" a Atlas, un analista de mercado virtual, y entrenarlo una vez para que después trabaje solo. Como cierre del concepto, citar el framing de la propia Anthropic — "menos una sesión de chat, más asignarle tareas a un colega" — para reforzar que esto no es marketing nuestro sino la forma en que el producto está pensado. Tiempo objetivo: ~5 min.
---

# Lo básico: interfaz, Instrucciones y Projects

---

## (Demo time) Conozcamos la interfaz de Cowork

```ascii
   __________________________________________
  /                                          /|
 /            >   D E M O   T I M E          / |
/__________________________________________/  |
|                                          |   |
|     [ Pasamos a la app real de Cowork ]  |  /
|__________________________________________| /
|__________________________________________|/
```

- **SLIDE DE DEMO EN VIVO** — Tour rápido de la pestaña Cowork sobre la app real, no sobre la slide.
- Anatomía de la pestaña Cowork (referencia anotada):

![Anatomía de la pestaña Cowork — interfaz anotada](images/screenshot-cowork-tab.png)

- Elementos a señalar en vivo: el selector de modo **"Ask"** (Ask before acting / Act without asking), el selector de carpeta de trabajo, la pestaña **Scheduled**, la pestaña **Live artifacts**, el panel de un **Project**.
- Control en Cowork = el dropdown de modo + los prompts de aprobar/redirigir por acción + el selector de carpeta. **No hay slash commands**: Cowork es GUI.

### Notes

Momento de demo en vivo — bajar de los conceptos a la app real. Abrir Cowork y hacer un recorrido de 2-3 minutos señalando: dónde está el selector de modo (Ask before acting por defecto), cómo se concede una carpeta de trabajo, y dónde viven Scheduled y Live artifacts (que vamos a usar más adelante). Demo sugerida de arranque (la del deck): "Organizá esta carpeta de 8 PDFs por tema y dame un resumen de un párrafo de cada uno." Dejarlos ver a Claude planificar, tocar archivos y entregar — sin explicar la mecánica todavía. La imagen anotada queda como respaldo por si la demo en vivo falla. Tiempo objetivo: ~8 min (incluida la demo).
---

## Los bloques de Cowork: cada problema, una pieza

- **La idea.** Cowork no se aprende como una lista de features sueltas, sino como **bloques que se apilan**: cada bloque resuelve un problema concreto y recurrente, y al sumarse vuelven al agente cada vez más rico y autónomo. **Importante:** estos bloques **no** son una escalera estricta — usás solo los que tu tarea necesita; se combinan, no se exigen unos a otros.
- **Este es el mapa de toda la charla.** Vamos a **recorrer cada bloque, uno por uno**, en el resto de la sesión — en este orden. Volvé a esta slide como "estamos acá" cuando quieras ubicarte.
- **Cada bloque = un problema que ya tuviste:**
  - **Un prompt / chatear** → *hago todo a mano, un mensaje a la vez.*
  - **Instrucciones** → *no quiero repetir el contexto en cada prompt.*
  - **Projects** → *quiero guardar y organizar todo en un lugar fijo.*
  - **Skills** → *no quiero repetir la misma tarea.*
  - **Connectors / MCP** → *quiero traer datos de mis herramientas.*
  - **Schedule** → *quiero que corra solo.*
  - **Live Artifacts** → *quiero compartir el resultado vivo* — un colaborador que entrega solo.
- **Plugins, transversal.** Hay una pieza que no es un bloque más en la pila: los **Plugins** son la **capa transversal de distribución** — empaquetan y reparten Skills, agentes y connectors a todos a la vez. La vemos al final de la charla (Sección 6).

![Los bloques de Cowork apilados, con Plugins como capa transversal](images/s2-2-1-bloques-cowork.png)

### Notes

Esta slide es el mapa de toda la sesión: antes de entrar en cada pieza, dar la foto completa. El gancho es el problema, no la feature — empezar desde abajo: "hoy hacés todo a mano, un mensaje a la vez". Cada bloque nace de una frustración concreta y la resuelve: no me quiero repetir el contexto → Instrucciones; no quiero perder los archivos → Projects; no quiero repetir la misma tarea → Skills; quiero datos de mis herramientas → Connectors/MCP; quiero que corra solo → Schedule; quiero compartir el resultado vivo → Live Artifacts. Subrayar la dirección: cuanto más arriba, menos trabajo manual y más entrega autónoma.

Cuidado con la metáfora: NO es una pirámide donde cada capa depende de todas las de abajo. Son bloques que se apilan y se combinan — usás solo los que tu tarea necesita. Por eso cambiamos el dibujo de pirámide a bloques apilados.

Decir explícitamente la promesa de roadmap: "vamos a recorrer cada uno de estos bloques, uno por uno, en el resto de la charla, en este orden" — y que pueden volver a esta slide como "estamos acá" entre secciones para ubicarse. Al final, la pila entera es Atlas.

Plugins como transversal: marcar que Plugins NO es un bloque más en la pila, sino la banda que la envuelve — la forma de empaquetar y distribuir varias de estas piezas a la vez (a un equipo, p. ej.). No desarrollarlo acá: lo vemos en la Sección 6. Tiempo objetivo: ~3-4 min.
---

## Instrucciones: ajustar el comportamiento sin repetirte

- **Concepto.** Las Instrucciones son el "contrato de trabajo" del agente: reglas en lenguaje natural que valen para todo lo que hagas, sin tener que repetirlas en cada prompt.
- **Ejemplo (Atlas) — qué podría decir un Instructions.** Quién es Atlas, qué empresas sigue, su audiencia, su tono y su regla de oro:

![Tarjeta de instrucciones: persona, reglas y regla de oro](images/s2-3-1-tarjeta-instrucciones.png)

  Una sola vez escribís esto; vale para todos los prompts del Project.
- **Cosas importantes a tener en cuenta.**
  - Mantenelas cortas y claras; son lenguaje natural, no código.
  - Sirven para evitar repetir lo mismo en cada prompt: lo que decís una vez vale para todo el Project.
  - Es el lugar para fijar reglas no negociables (como el disclaimer legal).

### Notes

Conectar con el paradigma: en lugar de re-explicarle a Claude el contexto cada vez, lo escribís una vez en las Instrucciones y queda fijo. Mostrar el texto real de las Instrucciones de Atlas como ejemplo concreto — destacar la regla de oro del disclaimer financiero, que es exactamente el tipo de regla no negociable que conviene pinear acá. Dónde viven: en el panel de contexto del Project (en la GUI) — no es un archivo que edités a mano; lo escribís en el panel y queda asociado al Project. Tiempo objetivo: ~7 min.
---

## Projects: guardar todo en un lugar fijo

- **Concepto.** Un Project es un espacio de trabajo autocontenido: le da al agente una **carpeta propia**, **memoria** dentro del proyecto y un **lugar fijo** para sus tareas. Tiene tres capas persistentes: Instrucciones, base de conocimiento (Knowledge base) y Chats.
- **Ventajas.** Todo queda organizado y reutilizable: las Instrucciones valen para todo el Project, la memoria recuerda tus correcciones y preferencias, y los archivos viven en una carpeta concreta de tu disco.
- **Cosas importantes a tener en cuenta.**
  - Los chats dentro de un mismo Project **no comparten contexto entre sí** — solo se comparte la base de conocimiento.
  - En Cowork, qué carpetas se conceden lo controla el **selector de carpetas del sistema operativo**, no un archivo de configuración.
  - Buena práctica: una carpeta de trabajo dedicada, para saber siempre qué está en alcance (y nunca conceder una carpeta con datos confidenciales o credenciales).

### Notes

El Project es el contenedor de todo lo demás: Instrucciones, archivos, memoria. En la misión, el Project "Inteligencia de Mercado Semanal" apunta a la carpeta `Documentos/Atlas-Mercado`. Subrayar dos puntos prácticos: (1) los chats no se hablan entre sí dentro del Project — si querés que recuerde algo, va a las Instrucciones o a la base de conocimiento; (2) el control de qué carpetas toca Claude es el folder picker del sistema operativo, que es a la vez la garantía de seguridad (Cowork solo ve lo que le concedés) y el límite. La slide siguiente muestra ese selector y el panel de contexto en pantalla. Tiempo objetivo: ~7 min.
---

## El selector de carpetas y el panel de contexto

- **Conceder una carpeta de trabajo.** Cowork no toca tu disco por sí solo: vos le concedés una carpeta con el **selector de carpetas del sistema operativo** (el mismo folder picker que usás para abrir cualquier archivo). Lo que quede fuera de esa carpeta, Cowork no lo ve.

![Selector de carpeta de trabajo del Project](images/project.png)

- **El panel de contexto del Project.** Es donde viven las Instrucciones, la base de conocimiento y la carpeta concedida — la "foto" de todo lo que el agente tiene a mano para ese Project.

![Panel de contexto del Project](images/context.png)

- **Nota de seguridad.** El selector es a la vez tu garantía y tu límite: Cowork solo trabaja sobre lo que le concedés. **Nunca concedas una carpeta con datos sensibles, credenciales o información bajo NDA.** Buena práctica: una carpeta dedicada por Project, para saber siempre qué está en alcance.

### Notes

Slide de apoyo visual, corta y concreta — bajar a pantalla lo que en la slide anterior fue conceptual. Mostrar las dos capturas: (1) el folder picker del sistema cuando concedés una carpeta; (2) el panel de contexto del Project con sus capas. El mensaje de seguridad es el que no hay que saltear: Cowork solo ve lo que le concedés, así que la elección de carpeta ES el control de privacidad — nunca una carpeta con datos sensibles. Aterrizarlo en la misión: Atlas trabaja sobre `Documentos/Atlas-Mercado`, nada más. Tiempo objetivo: ~3 min.
---

# Extender Cowork: Skills y el rol de los archivos MD / metadata

---

## Skills: enseñarle a Claude algo una sola vez

- **Concepto.** Una Skill es una instrucción reutilizable (+ scripts opcionales) que el agente carga cuando tu pedido coincide con su descripción. Un trabajo por Skill: "si escribís 'y además', dividila en dos". La frase clave: *"Todo lo que le explicás a Claude dos veces es una Skill que deberías escribir una vez."*
- **Cómo se crea una Skill en Cowork.** Dos caminos reales (Cowork es GUI: **no hay slash commands**):
  1. **Pedísela en lenguaje natural** — "armame una Skill que haga X". Claude **escribe el archivo `SKILL.md`**, pero Cowork **NO la registra/habilita** solo. Tenés que **habilitarla** en **Customize → Skills** (el botón **Save skill / Save to enable**). Recién ahí queda activa.
  2. **Subís un ZIP** — empaquetás la carpeta de la Skill como `.zip` y la cargás en **Customize → Skills → "+" → Create skill → Upload a skill**, y la activás con el toggle.
- **Requisito.** Las Skills necesitan **Code execution** habilitado (Settings → Capabilities).
- **OJO — la trampa del Save (camino 1).** Es el error más común: pedís la Skill, Claude escribe el archivo… pero si no le das **Save / enable** en Customize, no queda habilitada y parece que "no funciona".
- **Ejemplo (Atlas).** La Skill `reporte-semanal`: lee TODOS los archivos crudos de una carpeta `fuentes/` (uno por portal), consolida por empresa y genera un reporte con formato fijo. La empresa más relevante va primera (⭐). Guarda con sufijo `-new` para no pisar el ejemplo.

### Notes

La Skill es la materialización directa del paradigma "enseñá una vez, reutilizá siempre". Mostrar los dos caminos reales en Cowork: (1) pedírsela en lenguaje natural — Claude escribe el `SKILL.md`, y vos la habilitás en Customize → Skills; (2) subir un ZIP de la carpeta de la Skill por Customize → Skills. Aclarar de entrada que Cowork es GUI: no hay slash commands. El punto que NO hay que saltear es la trampa del Save: es un error real y muy común — pedís la Skill, Claude escribe el archivo, pero si no le das Save / enable no queda habilitada y parece que "no funciona". Mencionar que las Skills requieren Code execution (Settings → Capabilities). Usar `reporte-semanal` como ejemplo concreto: convierte varios archivos desordenados en un reporte prolijo. Tiempo objetivo: ~8 min.
---

## (Sideway) Archivos MD y metadata: el lenguaje común del mundo LLM

- **Concepto.** Casi todo lo que configurás alrededor de un agente — Instrucciones, Skills (`SKILL.md`), archivos de agentes, docs de plugins, salidas — es texto plano en **Markdown** (`.md`). Markdown es la *lingua franca* del mundo LLM.
- **Qué es la metadata / los headers.** Muchos de esos archivos arrancan con un bloque de **metadata** (un "header" en YAML): por ejemplo, un `SKILL.md` declara `name` y `description`. Esa descripción es lo que dispara la Skill — de forma semántica, no por palabra clave.
- **Por qué esto es importante en el mundo LLM.**
  - El modelo lee texto: si la configuración es texto plano legible, el agente la entiende directamente, sin formato propietario.
  - La metadata le dice al sistema *qué es* cada archivo y *cuándo* usarlo (la `description` de una Skill decide cuándo se activa).
  - Es portable y versionable: el mismo estándar `SKILL.md` funciona entre herramientas (Cowork y Codex usan el mismo formato).
- *Nota de alcance:* esto es un sideway de alto nivel — qué es y por qué importa. No entramos en el detalle del formato de archivos.

### Notes

Sideway breve y de alto nivel — explícitamente NO un deep dive de formato de archivos. La idea a transmitir: en el mundo LLM, la configuración es texto plano (Markdown) porque el modelo lee texto, y la metadata (el header YAML) le dice al sistema qué es cada archivo y cuándo usarlo. El ejemplo más tangible es la `description` de una Skill: no es decoración, es lo que decide si la Skill se activa o no para un pedido dado. Cerrar con la portabilidad: el mismo `SKILL.md` sirve en distintas herramientas. Mantenerlo en ~5 min — es contexto, no el plato principal.
---

## Anatomía de un SKILL.md

- Así se ve un `SKILL.md` por dentro: un **bloque de metadata** arriba y el **cuerpo de instrucciones** abajo. Nada más — es texto plano.

![Anatomia de un SKILL.md: metadata y cuerpo](images/s3-3-1-anatomia-skill-md.png)

- **La metadata (el header).** `name` identifica la Skill; `description` es lo que **decide cuándo se activa** — de forma semántica, no por palabra clave exacta. Una buena `description` = la Skill se dispara cuando corresponde.
- **El cuerpo.** Markdown común: los pasos que el agente sigue cuando la Skill se activa.
- *Nota de alcance:* reforzamos el sideway anterior (MD + metadata) con un ejemplo tangible — no entramos en el detalle fino del formato.

### Notes

Slide-ejemplo que aterriza el sideway de MD/metadata. Mostrar el `SKILL.md` partido en dos zonas: arriba el header YAML (`name`, `description`) entre `---`; abajo las instrucciones en Markdown. El punto a martillar: la `description` no es decoración — es exactamente lo que el sistema lee para decidir si esta Skill aplica a tu pedido (activación semántica). Usar `reporte-semanal` para que sea concreto. Mantenerlo alto nivel: es para que "vean cómo se ve", no un tutorial de formato. Tiempo objetivo: ~3-4 min.
---

# Conectar y automatizar: Connectors/MCP y Schedule

---

## Connectors y MCP: las "manos" del agente

- **Qué son los Connectors.** Son lo que le permite al agente tocar sistemas externos que de otro modo no podría: Drive, Gmail, Slack, bases de datos, APIs. "Las manos: lo que el agente puede tocar que de otro modo no podría."
- **Qué es MCP (Model Context Protocol).** El estándar detrás de los Connectors: una forma estandarizada de conectar Claude con sistemas externos. Cualquier app que exponga un servidor MCP se vuelve algo con lo que podés "hablar" (Figma, Vercel, Cal.com, Home Assistant…). El patrón: la plataforma abre sus internals como herramientas MCP; el agente no gana una capacidad nueva, la plataforma se vuelve conversacional.
- En la próxima slide vemos **cómo se registra un Connector** en la práctica (directorio + un clic).

![Flujo de una llamada a un Connector via MCP](images/s4-1-1-flujo-connector-mcp.png)

### Notes

Desarmar el miedo: conectar un servicio externo no es programar. En Cowork es literalmente buscar el servicio en el directorio y darle Connect — como conectás Gmail. Usar el diagrama para explicar qué pasa por debajo: el agente pide datos, el Connector los trae vía el protocolo MCP. MCP es el estándar que hace que cualquier plataforma con API pueda volverse conversacional. Ejemplo de la misión: MT Newswires (noticias de mercado) y Gmail, ambos de un clic. Aclarar que en Cowork no hay archivo de config: todo por la UI. Tiempo objetivo: ~10 min.
---

## Cómo se registra un Connector

- **No estás programando: te conectás.** Registrar un Connector es como conectar Gmail a una app nueva — buscás el servicio en un directorio y le das **Connect**. Configurado por la UI; no hay archivo local que editar.
- **El directorio de Connectors.** Cowork trae un **directorio** con servicios listos para conectar de un clic:

![Directorio de Connectors en Cowork](images/connectors_directory.png)

- **Conexión de un clic.** Buscás el servicio, le das **Connect** y autorizás — y queda disponible para el agente:

![Conexión de un Connector — buscar y conectar](images/connector_browser.png)

- **Ejemplo (Atlas).** **MT Newswires** ya tiene un connector listo: lo buscás y le das Connect, como cualquier app. **Gmail**, igual: un clic en el directorio. Con eso, Atlas pasa a leer noticias de mercado y a dejar borradores de correo — sin que vos programes nada.

### Notes

Slide práctica: mostrar las dos capturas — el directorio de Connectors y la pantalla de conexión — para desarmar el miedo de "esto es técnico". El mensaje es: conectar un servicio es buscar + Connect + autorizar, igual que cuando conectás Gmail a cualquier app. Ejemplos de la misión: MT Newswires (noticias) y Gmail (borradores), ambos de un clic. Recordar que en Cowork todo esto es por la UI, no por archivos de config. Tiempo objetivo: ~5 min.
---

## Schedule: que Cowork trabaje solo

- **Para qué sirve.** Todo lo anterior es reactivo (vos pedís, Claude hace). Schedule hace a Cowork **proactivo**: describís una tarea una vez, elegís una cadencia, y Claude la corre solo.
- **Cómo funciona.**
  - Describís la tarea una vez; Claude guarda el prompt como las instrucciones de la tarea.
  - Elegís cadencia: por hora · diaria · semanal · días de semana · o **a demanda** ("Run now").
  - Cada corrida abre su **propia sesión fresca de Cowork** y avisa al terminar.
  - Tiene los **mismos poderes** que una tarea normal: connectors, skills, plugins instalados.
  - Vive en la pestaña **Scheduled** de la barra lateral.
- **⚠️ LA trampa — corre LOCAL, no en la nube.** Las tareas programadas de Cowork corren **en tu computadora**, no en servidores de Anthropic. Solo se disparan **con la máquina encendida y la app de Claude Desktop abierta**. Si estaba dormida/cerrada a la hora prevista, la corrida se **saltea** — y se ejecuta automáticamente apenas la máquina despierta o reabrís la app (con aviso de "esto se saltó"). No esperes que tu laptop apagada genere el reporte del lunes.
  - *(Aparte, fuera de alcance:)* existen agentes programados **alojados en la nube**, pero son una funcionalidad separada — no es lo que hace el Schedule de Cowork.

![Pestaña Scheduled en Cowork](images/schedule.png)

- **Ejemplo (Atlas).** Cada lunes 8:00: `buscar-accion` → `reporte-semanal` → dejar el reporte como borrador en Gmail, listo antes de la reunión de las 9:00. Tip de demo: no esperar al lunes, usar "Run on demand".

### Notes

Acá Cowork pasa de herramienta a empleado: describís el trabajo una vez y corre solo. Es el momento en que Atlas "trabaja mientras vos dormís" — pero con un asterisco. El punto crítico — y un error clásico — es que el Schedule de Cowork corre LOCAL, en tu máquina, no en la nube de Anthropic: solo se dispara con la computadora despierta y la app abierta; si estaba dormida/cerrada, se saltea y corre apenas volvés (con aviso). Dejarlo bien claro para que nadie espere que su laptop apagada genere el reporte del lunes. (Si alguien pregunta por corridas en la nube: sí existen agentes programados hosteados, pero son otra cosa, fuera del alcance de esta charla.) Para la demo, usar "Run on demand" en lugar de esperar la cadencia real. Tiempo objetivo: ~10 min.
---

# Compartir resultados: Live Artifacts

---

## Artifacts y Live Artifacts: del resultado a algo compartible

- **Qué es un Artifact.** Una salida viva y ejecutable que se renderiza en un panel lateral: componentes React, páginas HTML, gráficos SVG, diagramas, tablas, documentos descargables.
- **Distinción live vs no-live (breve).**
  - **Artifact estándar** (todos los planes): salida de un solo archivo, estática — lo que generás es lo que queda.
  - **Live Artifact** (Cowork, planes pagos): una **página HTML interactiva y persistente** que vive en la pestaña **"Live artifacts"** de Cowork. **Se actualiza con datos actuales** de tus apps conectadas cada vez que la abrís, y **guarda historial de versiones**.
- **Cómo se crea.** Dos formas: (1) **desde una tarea de Cowork** (le pedís que el resultado sea un Live Artifact), o (2) desde la pestaña **Live artifacts → New artifact → Chat with Claude**.
- **Estado actual del compartir — leer con cuidado.** Los Live Artifacts **todavía NO son compartibles**: en el lanzamiento son **para tu propio uso**; compartir está en el roadmap. Además son **locales, no en la nube**: viven en tu computadora y no te siguen entre dispositivos. Y **usan tus connectors sin volver a pedirte permiso** — solo los que aprobaste al crear/actualizar el artifact.
- **Ejemplo (Atlas).** El tablero `pulso-semanal-FECHA`: un Live Artifact nuevo por semana (queda un historial de versiones), con tarjetas por empresa, tabla resumen y un chip "LIVE", refrescado con los datos de la semana. Diseño basado en el boceto del jefe:

![Boceto del tablero "Pulso semanal de mercado" (wireframe del jefe)](images/mockup-tablero.png)

### Notes

Cerramos el círculo de la misión: el jefe quería el reporte de dos formas — el email (que ya resolvimos con Gmail + Schedule) y una página siempre actualizada. El Live Artifact es esa página. Explicar la distinción clave: un Artifact estándar es estático; un Live Artifact persiste en la pestaña Live artifacts, se refresca con datos actuales al abrirlo y guarda versiones. Ser honesto con el estado actual del compartir, porque acá había una confusión que corregimos: hoy los Live Artifacts NO son compartibles (es del roadmap, no de hoy), son locales —no en la nube, no te siguen entre dispositivos— y usan los connectors que aprobaste sin volver a preguntar. (Nota: versiones previas de este material mencionaban un "ShareDuo" con URL pública — eso NO es una capacidad de Cowork; quitado.) Mostrar el boceto del tablero — el "napkin sketch" del jefe — como el spec de diseño que el artifact reproduce. Tiempo objetivo: ~10 min.
---

# Advanced: Subagentes y Plugins

---

## Subagentes: delegar sub-tareas en paralelo

- **Concepto.** Un Subagente es un asistente aislado, con su propio contexto, instrucciones y acceso a herramientas, al que el agente principal le delega un trabajo y del que recibe **un resumen** (no la transcripción completa).
- **Skill vs Subagente (la regla de una línea).** Chico, y debe quedar frente a vos → **Skill** (corre *dentro* de tu conversación). Grande o ruidoso, y debe correr en un proceso aparte → **Subagente** (corre *al lado*, en su propio contexto).
- **En Cowork.** Los Subagentes se coordinan "por debajo" (under the hood): el agente principal los lanza cuando le conviene, y pueden correr **varios en paralelo**.
- **Cómo se agrega un subagente.** Se define igual que una Skill — una **descripción de cuándo usarlo** + sus **instrucciones**. Dos caminos: **pedile a Claude que lo arme** (escribe el archivo del agente, como con las Skills, y lo gestionás en el directorio **Customize**), o viene **empaquetado dentro de un Plugin**. No hace falta tocar archivos a mano.

![Subagentes: patron fan-out / fan-in](images/s6-1-1-subagentes-fanout.png)

### Notes

Nivel avanzado — presentarlo como "para cuando crezcas". La distinción mental útil: si la sub-tarea es chica y querés verla, es una Skill; si es grande o ruidosa y querés que corra aparte sin ensuciar tu conversación, es un Subagente. El ejemplo del deck (8 propuestas de proveedores revisadas en paralelo por tres especialistas → tabla combinada) ilustra el fan-out. Cómo se agrega: explicarlo en paralelo a las Skills — un subagente se define con una descripción (cuándo usarlo) + instrucciones; le pedís a Claude que lo arme (igual que una Skill, se gestiona en Customize) o viene dentro de un Plugin. Mantenerlo alto nivel: no entrar en rutas de archivos ni internals de persistencia. Tiempo objetivo: ~7 min.
---

## Plugins: empaquetar y distribuir un workflow completo

- **Concepto.** Un Plugin es la unidad de distribución de un workflow completo: empaqueta Skills + agentes + hooks + MCP en una sola instalación. "Ship the whole thing."
- **En Cowork.** Se instalan desde un **marketplace de plugins** en la GUI. Un Plugin es una de las vías para **distribuir Skills (y agentes/connectors)**: para usar una Skill en Cowork, la habilitás como skill de usuario (Customize → Skills) o la enviás **dentro de un plugin**. Las skills provistas por plugin funcionan en Chat y en Cowork.
- **Dónde encontrarlos.** Marketplaces oficiales (`anthropics/claude-plugins-official`, `anthropics/knowledge-work-plugins`) y de la comunidad.

### Notes

Cerrar el avanzado con la idea de empaquetado: cuando un workflow está maduro (varias skills + connectors + agentes), un Plugin lo vuelve instalable de una. El punto importante para Cowork: la forma robusta de distribuir una skill (o un agente) a otros es dentro de un plugin; los plugins distribuidos aparecen tanto en Chat como en Cowork. Mencionar los marketplaces oficiales como punto de partida. Tiempo objetivo: ~6 min.
---

## Plugins en una cuenta Team: ciclo de vida

- **Quién lo maneja.** En cuentas **Team / Enterprise**, los **Owners** gestionan los plugins de la organización desde **Organization settings → Plugins**. El resto de los miembros los reciben listos.
- **El ciclo de vida, de punta a punta:**

![Ciclo de vida de un plugin en cuenta Team](images/s6-3-1-ciclo-plugins-team.png)

- **Qué se puede hacer.**
  - El Owner crea un **marketplace privado** de la organización y agrega plugins de dos formas: **subir un ZIP**, o **sincronizar desde un repo de GitHub** (privado) — esta segunda vía **auto-actualiza** cuando cambia el repo.
  - Por cada plugin se fija una **preferencia de instalación**: opcional (el miembro decide), **auto-install** o provisionado por usuario.
  - Los plugins distribuidos aparecen en **chat y en Cowork** para los miembros; cada uno **instala/habilita** desde el directorio de la org, y las **actualizaciones se sincronizan** solas.

### Notes

Slide de cierre del bloque avanzado, orientada a quien algún día administre una cuenta de equipo. La idea: los Plugins no son solo para instalar de a uno; en una cuenta Team, un Owner puede armar un marketplace privado de la organización y repartir workflows a todo el equipo. Recorrer el ciclo con el diagrama: el Owner crea el marketplace y sube plugins (ZIP o, mejor, sincronizando un repo de GitHub que auto-actualiza), fija cómo se instala cada uno (opcional / auto-install / provisionado), y desde ahí se distribuye —aparece tanto en chat como en Cowork— y los miembros lo habilitan desde su directorio, con las actualizaciones sincronizadas. Mantenerlo alto nivel: es el "para cuando esto escala a un equipo". Tiempo objetivo: ~4 min.
---

# Conclusions

## El loop completo y la idea para llevarse

- Lo que construimos, punta a punta — el loop de Atlas combinando todas las piezas:

![El loop completo de la mision Atlas](images/sc-1-1-loop-completo-atlas.png)

- **Las piezas, una línea cada una:** Instrucciones (el contrato) · Projects (el lugar fijo) · Skills (enseñar una vez) · Connectors/MCP (las manos) · Schedule (que corra solo) · Live Artifacts (compartir el resultado).
- **La idea para llevarse:** *"Todo lo que le explicás a Claude dos veces es una Skill que deberías escribir una vez."* Y el gancho: *"Acaban de automatizar un reporte que les iba a comer la mañana de cada lunes. ¿Qué otra tarea recurrente podrían delegarle a su propio Atlas?"*

### Notes

Cierre integrador: mostrar el diagrama del loop completo para que vean cómo cada pieza que aprendimos se engancha con la siguiente. Repasar las seis piezas en una línea cada una. Cerrar con las dos frases ancla: la de la Skill ("enseñá una vez") y el gancho que los invita a pensar qué tarea propia delegarían. Tiempo objetivo: ~5 min + Q&A.
---

## Gobernanza y advertencias (antes de Q&A)

- **Cowork no tiene audit trail** — no es apto para datos regulados o sensibles.
- **Toda salida es un borrador** — verificá cifras, citas y afirmaciones contra la fuente.
- **No metas datos confidenciales / PII / bajo NDA** en la superficie equivocada.
- **Reproducibilidad:** mantené juntos prompt + entradas + salidas, para que el trabajo sea auditable.
- **Capas de guardarraíles:** permisos de carpeta → reglas en Instrucciones → solo plugins verificados → revisión humana.
- *Contexto biomédico:* lo anterior es especialmente relevante si alguna vez aplican esto con datos de pacientes — Cowork no es la herramienta para datos clínicos sensibles.

### Notes

Slide de cierre responsable, breve pero no opcional. Para esta audiencia (bioingeniería), conectar explícitamente: Cowork es excelente para trabajo recurrente de oficina, pero NO para datos de pacientes ni nada regulado — no tiene audit trail. Recordar que toda salida es un borrador que hay que verificar. Dejar esto antes de abrir Q&A. Tiempo objetivo: ~3 min.
---
