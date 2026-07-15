---
presentation: "Inteligencia Artificial: de lo conceptual a lo práctico — Master in Management (MiM), IAE Business School, Universidad Austral"
class: "Claude Cowork para el día a día"
research: research/corpus/
description: Slides are grouped into Sections. Each Section contains one or more Slides.
presenter: Paulo Veiga, Profesor, IAE Business School
audience: Profesionales del dominio de negocios, no ingenieros — estudiantes del Master in Management (MiM). Sin formación técnica en AI; les interesa el impacto conceptual y práctico de la AI en la gestión y los negocios.
duration: 2 horas
date: Julio 2026
---

# Thesis

**Claim:** Partís del chat de IA que ya usás todos los días y lo extendés paso a paso, con conectores para que vea tu mundo real y tareas programadas para que trabaje solo. El destino es Claude Cowork, donde ese mismo agente trabaja sobre tus carpetas y archivos y cambia por completo la forma de trabajar: delegás resultados combinando sus piezas (Instrucciones, Projects, archivos .md, Schedule y Live Artifacts) sin escribir una línea de código.

**Why it matters:** El salto de chatear un mensaje a la vez a entregar un resultado y guiarlo es lo que vuelve útil a un agente en el trabajo real. Quien lo domina automatiza horas de trabajo manual con la barrera de entrada en cero, y el camino empieza en la herramienta que ya tenés abierta.

**Presenter feedback:**

---

# Agenda

**Narrative arc:** Arrancamos por la herramienta que ya usás todos los días, el chat de IA, y hacemos explícito su límite: responde de memoria de entrenamiento (1). Lo extendemos con conectores, un concepto que vale para todas las IAs: el chat consulta la web, tu mail y tu calendario, y además actúa (2). Con el chat extendido, lo volvemos proactivo con tareas programadas (3). Recién ahí llega el salto grande, Claude Cowork, que es más que "Claude instalado en tu computadora", y lo recorremos en tres tiempos: qué cambia en tu rol cuando dejás de tipear un mensaje a la vez y empezás a entregar un resultado (4), cómo montás tu espacio con la interfaz, las Instrucciones, el Project y la carpeta que le concedés (5), y cómo trabaja ahí adentro y qué te entrega, con los archivos .md, Schedule sobre tus carpetas y Live Artifacts (6). Cerramos con las piezas avanzadas, Skills, Subagentes y Plugins (7). El hilo conductor es una misión concreta, "Atlas", el analista de mercado que se arma pieza por pieza.

**Sections (in delivery order):**

- 1. El chat y sus límites
- 2. Extender el chat
- 3. El chat trabaja solo
- 4. Qué cambia con Cowork
- 5. Tu espacio en Cowork
- 6. Trabajar y entregar
- 7. Piezas avanzadas

**Presenter feedback:**

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: Reescrito el arco narrativo, que era el último resto stale de la reestructura de round 8 y quedó pendiente a propósito hasta este dispatch, cuando las 7 secciones ya existen. El "(4)" viejo enumeraba interfaz, Instrucciones, Projects, `.md`, Schedule y Live Artifacts en una sola cláusula: esas piezas hoy se reparten entre las secciones 4, 5 y 6, así que el salto a Cowork se cuenta en tres tiempos, uno por sección (qué cambia en tu rol / cómo montás tu espacio / cómo trabaja y qué te entrega). Register de round 7 aplicado al texto nuevo: cae el arco "de traer información a actuar" y el "Después ... Recién ahí" se reduce; el "(4)" usa el ancla de la sesión verbatim ("dejás de tipear un mensaje a la vez y empezás a entregar un resultado") en vez de parafrasearla. Se conservan el ancla del presentador "más que 'Claude instalado en tu computadora'" y el hilo conductor de Atlas. Verificados los 7 bullets de la lista contra los H1: presentes, contiguos 1..7 y con el texto idéntico; sin drift, nada que corregir.

---

# 1. El chat y sus límites

**Goal of this section:** Partir de la herramienta que la audiencia ya usa a diario, el chat de IA, y hacer explícito su límite: responde desde su memoria de entrenamiento, con información desactualizada, riesgo de alucinación y cero acceso a tus datos y apps.

**Presenter feedback:**

---

## 1. El chat responde de memoria

### Content

- De fábrica responde de su **memoria de entrenamiento**: recuerda, no busca (foto hasta la **fecha de corte**).
- Tres límites:
  - **Información vieja**: lo posterior al corte no existe.
  - **Alucinación**: inventa con confianza.
  - **No ve TU mundo**.

```ascii
        EL CHAT "COMO VIENE DE FABRICA"
                                             lo que NO ve:
   +---------------------------------+       x  noticias de hoy
   |            CHAT DE IA           |       x  tus mails
   |  +---------------------------+  |       x  tu calendario
   |  |  MEMORIA DE ENTRENAMIENTO |  |       x  tus archivos
   |  |  (foto congelada hasta la |  |       x  las apps de tu trabajo
   |  |   fecha de corte)         |  |
   |  +---------------------------+  |
   |     responde "de memoria"       |
   +---------------------------------+
```
<!-- ascii-note:
intent: mostrar que el chat de IA sin extensiones responde solo desde su memoria de entrenamiento (foto congelada hasta la fecha de corte) y no tiene acceso al mundo del usuario.
emphasize: la caja interna "MEMORIA DE ENTRENAMIENTO (foto congelada)"; la lista de lo que NO ve (noticias de hoy, mails, calendario, archivos, apps) fuera de la caja.
labels: caja exterior = CHAT DE IA; caja interior = memoria de entrenamiento / fecha de corte; columna derecha = lo que no ve.
-->

### Sources

- Anthropic Support — Enabling and using web search: https://support.claude.com/en/articles/10684626-enabling-and-using-web-search — el encuadre oficial: sin búsqueda web, Claude responde limitado a su información de entrenamiento; la búsqueda le da acceso a información actual (referencia también para la Sección 2).
- (concepto general de LLM: fecha de corte / respuestas desde entrenamiento / alucinaciones — material introductorio estándar del curso; sin claim específico de producto.)

### Speaker notes

Arrancar desde lo conocido: pedir a mano alzada quién usó un chat de IA esta semana. Levantan casi todos (ChatGPT, Gemini, Claude). La idea a instalar: ese chat, tal como viene, responde de memoria. No busca nada; recuerda lo que leyó hasta su fecha de corte (knowledge cutoff). Un colega brillante, incomunicado desde esa fecha. Tres consecuencias que ya sufrieron sin saberlo. Datos viejos: precios, noticias, versiones y papers posteriores al corte no existen. Inventos con cara de verdad: cifras y citas que suenan perfectas y son falsas; insistir en verificar toda salida. Y la más limitante: no ve nada tuyo, ni mails, ni calendario, ni archivos, ni apps. Ese tercer límite abre la charla. Tiempo objetivo: ~6 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: COMPACTAR 1.1. Quitado el bullet de narración ("Todos ya usan un chat de IA. La charla arranca ahí.") — vive en Speaker notes ("pedir a mano alzada"). Quitada la enumeración "mails, calendario, archivos, apps" del tercer límite: la columna derecha del ASCII ya la dibuja y el ascii-note la nombra en `emphasize`; el label "No ve TU mundo" queda en lámina. Se conservan la memoria de entrenamiento y los tres límites nombrados. Speaker notes retocadas de 149 a 119 palabras sin perder sustancia del guion.

---

# 2. Extender el chat

**Goal of this section:** Instalar el concepto de conector, válido para todas las IAs: el chat deja de responder de memoria y pasa a consultar información real (búsqueda web, mail, calendario) y hasta a actuar (mandar mails, agendar reuniones). La distinción a fijar es memoria de entrenamiento vs información viva.

**Presenter feedback:**

---

## 1. Chat solo vs chat con conectores

### Content

- **Conector** = extensión que conecta el chat a un sistema externo: web, mail, calendario, documentos.
- Vale igual en ChatGPT, Gemini y Claude.
- Se activa con un clic, sin programar.

```ascii
   CHAT SOLO                        CHAT CON CONECTORES
+----------------+              +----------------+
|     CHAT       |              |     CHAT       |----> [ web ]
|  responde de   |              |  consulta      |----> [ mail ]
|  memoria de    |              |  fuentes       |----> [ calendario ]
|  entrenamiento |              |  REALES antes  |----> [ documentos ]
+----------------+              |  de responder  |
   (aislado)                    +----------------+
                                  (conectado a tu mundo)
```
<!-- ascii-note:
intent: contrastar lado a lado el chat aislado (responde de memoria de entrenamiento) contra el chat con conectores (consulta fuentes reales — web, mail, calendario, documentos — antes de responder).
emphasize: el lado derecho con las flechas hacia web/mail/calendario/documentos; la etiqueta "(conectado a tu mundo)" vs "(aislado)".
labels: izquierda = CHAT SOLO (aislado, memoria de entrenamiento); derecha = CHAT CON CONECTORES (web, mail, calendario, documentos).
-->

### Sources

- Anthropic Support — Enabling and using web search: https://support.claude.com/en/articles/10684626-enabling-and-using-web-search — la búsqueda web como capacidad integrada del chat de Claude.
- Claude blog — Connectors directory: https://claude.com/blog/connectors-directory — el catálogo oficial de conectores de Claude (referencia ampliada en la slide 2.4; verificado 2026-07-09).

### Speaker notes

La slide instala el concepto que ordena la sección: un conector saca al chat de su aislamiento y le da acceso a buscar en la web, leer tu mail, ver tu calendario, consultar tus documentos. Repetir que es transversal: lo que aprendan acá vale para ChatGPT, Gemini y Claude. Los nombres cambian ("connectors", "apps", "extensiones"), la idea es la misma. Usar el diagrama para el contraste: el chat solo responde de memoria; el chat con conectores consulta fuentes reales antes de responder, la web, tu inbox, tu agenda. Cerrar bajando la barrera de entrada: esto se activa con un clic o un toggle en la configuración, sin programar. Tiempo objetivo: ~5 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: COMPACTAR 2.1. Quitado el bullet "Chat solo → responde de memoria. Chat con conectores → consulta fuentes reales antes de responder.": es el ASCII escrito en prosa (las dos columnas del diagrama y el `emphasize` de su ascii-note). El contraste se dice en voz alta desde Speaker notes, ahora explícito ahí. Quedan 3 bullets: qué es un conector, que vale en ChatGPT/Gemini/Claude, y que se activa con un clic. Notes en 110 palabras.

---

## 2. El primer conector: búsqueda web

### Content

- El conector más universal: viene en casi todos los chats (Claude, ChatGPT, Gemini). Se activa con un toggle.
- Mirá el "buscando..." y las fuentes citadas; ahí verificás.
- Regla: si la respuesta pudo cambiar → exigí búsqueda.

```ascii
   la MISMA pregunta: "¿ultima version de X?"

   DE MEMORIA                        CON BUSQUEDA WEB
+------------------+             +------------------+
| entrenamiento    |             | busca AHORA en   |
| hasta fecha de   |             | la web           |
| corte            |             |   |              |
|   |              |             |   v              |
|   v              |             | info REAL y      |
| respuesta        |             | actual + fuentes |
| (quizas vieja o  |             | citadas          |
|  inventada)      |             +------------------+
+------------------+
```
<!-- ascii-note:
intent: contrastar, para una misma pregunta, la respuesta de memoria de entrenamiento (posiblemente vieja o inventada) contra la respuesta con búsqueda web (información real y actual, con fuentes citadas).
emphasize: que es la MISMA pregunta con dos caminos; el lado derecho termina en "info REAL y actual + fuentes citadas"; el lado izquierdo en "quizás vieja o inventada".
labels: izquierda = DE MEMORIA (fecha de corte); derecha = CON BÚSQUEDA WEB (busca ahora, cita fuentes).
-->

### Sources

- Anthropic Support — Enabling and using web search: https://support.claude.com/en/articles/10684626-enabling-and-using-web-search — "Web search expands Claude's knowledge with real-time data"; "Every response includes citations, so you can easily verify sources yourself" (verificado 2026-07-09).
- OpenAI Help — ChatGPT search: https://help.openai.com/en/articles/9237897-chatgpt-search — búsqueda web integrada en ChatGPT, automática cuando la pregunta lo amerita, con citas inline (evidencia de que el concepto es transversal; verificado 2026-07-09).

### Speaker notes

Acá se fija la distinción de la charla: de memoria recuerda hasta la fecha de corte y puede estar viejo o mal; con búsqueda trae información real, ahora, y cita fuentes. Con conexión, demo de 2 minutos: la misma pregunta ("¿cuál es la última versión de X?") con búsqueda apagada y prendida. Señalar el indicador de "buscando..." y las fuentes citadas; enseñarles a mirar eso cada vez. En varios chats ya viene activo por defecto. La regla que se llevan: si la respuesta pudo haber cambiado desde el entrenamiento (precios, noticias, versiones, papers, normativa), exigí búsqueda. Arrancamos por este conector porque ya lo tienen; falta saber cuándo está actuando. Tiempo objetivo: ~7 min (con demo).

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: COMPACTAR 2.2. Quitado el bloque "La distinción de la charla" con sus dos sub-bullets ("De memoria → ..." / "Con búsqueda → ..."): son las dos columnas del ASCII escritas en prosa y ya estaban nombradas en el `emphasize` de su ascii-note. La distinción se dice en voz alta; fundida en la primera oración de Speaker notes en vez de duplicada. Quedan 3 bullets: el conector más universal, mirar las fuentes citadas, y la regla de bolsillo. Notes en 117 palabras.

---

## 3. Conectores y MCP: las "manos" del chat

### Content

- Conectores = **las "manos"**: lo que la IA puede tocar que de otro modo no podría (Drive, Gmail, Calendar, Slack, bases de datos).
- **MCP**: el estándar detrás. Cualquier app con servidor MCP se vuelve conversacional.
- Un equipo técnico puede armar **conectores propios** (custom, vía MCP).

```ascii
+--------+   pide datos    +-----------+   protocolo   +--------------+
| CHAT / | --------------> | Connector |  -- MCP -->   | Servicio ext |
| agente |                 |  (1 clic) |               | Gmail/Calendar|
+--------+ <-------------- +-----------+ <-----------  +--------------+
            devuelve datos
```
<!-- ascii-note:
intent: mostrar el flujo de una llamada a un Connector: el chat/agente pide datos, el Connector traduce vía el protocolo MCP, el servicio externo responde.
emphasize: la etiqueta "MCP" sobre la flecha del medio; el Connector como puente de un clic.
labels: Chat/agente -> Connector (1 clic) -> Servicio externo (Gmail / Calendar); flecha de ida "pide datos", flecha de vuelta "devuelve datos".
-->

### Sources

- corpus/agentic-ai-deck.zip.md — definición de Connector (MCP): "The hands"; slide 5.4 (rango de MCP; "any app that exposes an MCP server").
- "corpus/mision - auto.zip.md" — MT Newswires "ya tiene un connector listo" (Step 2.1); Gmail connector de un clic (M3).
- Model Context Protocol (sitio oficial del estándar): https://modelcontextprotocol.io — qué es MCP y cómo las plataformas exponen herramientas; base de los conectores personalizados.
- Anthropic Support — Getting started with custom connectors using remote MCP: https://support.claude.com/en/articles/11175166-getting-started-with-custom-connectors-using-remote-mcp — los conectores personalizados existen y se agregan vía MCP (mención, sin profundizar).

### Speaker notes

Desarmar el miedo: conectar un servicio externo le da "manos" al chat, sin programar nada. Usar el diagrama para explicar qué pasa por debajo: la IA pide datos y el conector los trae vía MCP (Model Context Protocol), el estándar que vuelve conversacional a cualquier plataforma con API. El patrón: la plataforma abre sus internals como herramientas. Mencionar dos o tres ejemplos del ecosistema (Figma, Vercel, Cal.com, Home Assistant) y seguir. Decir al pasar que un equipo técnico puede desarrollar conectores propios (custom, vía MCP); a nivel usuario alcanza con el directorio, que viene en la próxima slide. Los ejemplos guía de la sección son mail y calendario, porque son los que la audiencia ya tiene. Tiempo objetivo: ~8 min.

### Presenter feedback
- [closed] 2026-06-09 — "Esto - **Cómo se llama / registra un Connector.** En Cowork hay un **directorio de Connectors** con conexión de un clic ("Connect"), configurado por la UI de Settings — no hay archivo local que editar. Ejemplo (Atlas): **MT Newswires** ya tiene un connector listo; lo buscás y le das Connect, como cualquier app. Gmail, igual: un clic en el directorio. vamos a moverlo a un nuevo slide."
  Resolution: SPLIT: el bloque 'Como se llama/registra un Connector' se movio de 4.1 a una nueva slide 4.2 'Como se registra un Connector' (directorio de Connectors, conexion de un clic 'Connect', ejemplo MT Newswires + Gmail). Cableadas las dos imagenes nuevas images/connectors_directory.png y images/connector_browser.png. 4.1 queda con lo conceptual (Connectors + MCP) y un puntero a la slide siguiente; Schedule renumerada 4.2->4.3.
  - Added two images to include in this slide: connectors_directory.png & connector_browser

---

## 4. Buscá, conectá, autorizá

### Content

- No programás: **buscás + Connect + autorizás**. Como conectar Gmail a una app nueva.
- De dónde salen: **directorio oficial de Claude** · comunidad · propios (custom).

![Directorio de Connectors](images/connectors_directory.png)

![Conexión de un Connector — buscar y conectar](images/connector_browser.png)

### Sources

- Claude blog — Discover tools that work with Claude (Connectors directory): https://claude.com/blog/connectors-directory — anuncio oficial del directorio; navegar y conectar de un clic vía claude.ai/directory (verificado 2026-07-09; el directorio en sí requiere login).
- Anthropic Support — Use connectors to extend Claude's capabilities: https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities — cómo se conectan y usan los conectores desde la configuración.
- corpus/agentic-ai-deck.zip.md — matriz 5.6 (Connectors configurados por la Settings UI; directorio + un clic).
- "corpus/mision - auto.zip.md" — "no estás programando: te conectás a un servicio que ya existe".
- Anthropic Support — Getting started with custom connectors using remote MCP: https://support.claude.com/en/articles/11175166-getting-started-with-custom-connectors-using-remote-mcp — la vía de los conectores propios.

### Speaker notes

Slide práctica. Mostrar las dos capturas (el directorio de conectores y la pantalla de conexión) para desarmar el "esto es técnico". Conectar un servicio es buscar + Connect + autorizar, igual que cuando conectás Gmail a cualquier app; se configura por la UI, sin archivo local que editar. De dónde salen los conectores: el directorio oficial de Claude, servicios de terceros que exponen MCP, y los propios que puede armar un equipo técnico. Nota: las capturas son de la app de Claude (Cowork); el flujo buscar+Connect es el mismo en el chat. Tiempo objetivo: ~3 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: SPLIT (mitad A). La ex 2.4 "El directorio de conectores: mail, calendario y compañía" (56c) cargaba dos ideas: el mecanismo de registro y los ejemplos guía. Esta mitad se queda con el mecanismo (buscar + Connect + autorizar) y el origen de los conectores (oficial / comunidad / propios), más las dos capturas connectors_directory.png y connector_browser.png. Bullets al mínimo (2) porque las dos imágenes ya ocupan la lámina. Los ejemplos guía, MT Newswires y el criterio de confianza pasan a la mitad B (2.5 "Mail y calendario, los ejemplos"). Sources y Speaker notes repartidas: acá quedan las del directorio, la Settings UI y los custom; notes en 96 palabras.

---

## 5. Mail y calendario, los ejemplos

### Content

- Ejemplos guía: **mail y calendario**. "¿Qué mails me perdí ayer? ¿Qué tengo esta semana?"
- Preguntas que el chat aislado no puede responder.
- Atlas: **MT Newswires** listo en el directorio, un clic.
- Conector no oficial: autorizarlo le da acceso a tus datos. **Conectá solo lo confiable.**

### Sources

- "corpus/mision - auto.zip.md" — MT Newswires "ya tiene un connector listo" (Step 2.1); Gmail connector de un clic (M3).
- Anthropic Support — Use connectors to extend Claude's capabilities: https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities — cómo se usan los conectores de mail y calendario desde la configuración.
- Anthropic Support — Getting started with custom connectors using remote MCP: https://support.claude.com/en/articles/11175166-getting-started-with-custom-connectors-using-remote-mcp — la vía de los conectores no oficiales / propios (base del criterio de confianza).

### Speaker notes

Insistir en mail y calendario, los ejemplos guía de la sección: con Gmail conectado el chat lee y resume tu inbox, con Calendar ve tu agenda. "¿Qué mails me perdí ayer?", "¿Qué tengo esta semana?" son preguntas que el chat aislado no puede responder. Ejemplo de la misión: MT Newswires (noticias), ya listo en el directorio, con el que Atlas lee noticias reales del día. Sobre los no oficiales (servicios de terceros que exponen MCP): mismos pasos, más criterio. Autorizar un conector le da acceso a tus datos; conectá solo lo confiable. Tiempo objetivo: ~3 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: SPLIT (mitad B). Segunda mitad de la ex 2.4: los ejemplos guía (mail y calendario, con las dos preguntas), MT Newswires listo para Atlas, y el criterio de confianza para conectores no oficiales, que vivía solo en Speaker notes y sube al body acá. Sin diagrama nuevo; las dos capturas se quedan en la mitad A. Sources repartidas: acá las del corpus de la misión (MT Newswires, Gmail de un clic), el artículo de uso de conectores y el de custom/remote MCP que respalda el criterio de confianza. Notes en 96 palabras. Las dos mitades suman los ~6 min de la slide original.

---

## 6. Los conectores también actúan

### Content

- Además de traer info, un conector expone **acciones**: la IA **hace**.
- Ejemplos:
  - **Mandar / dejar redactado un mail** (borrador en tu Gmail).
  - **Agendar una reunión** (evento en tu calendario).
- Vos conectás y autorizás cada servicio. Mientras aprendés, **borrador antes que envío directo**.

```ascii
        CONECTOR: dos direcciones

   LEER (traer info)          ACTUAR (hacer)
   <------------------        ------------------>
+------+           +----------+           +----------+
| CHAT |  <------- | conector |  ------>  | tu mundo |
+------+   inbox,  +----------+  mandar   | mail     |
           agenda,              mail,     | calendario|
           noticias             agendar,  | tickets  |
                                ticket    | mensajes |
                                          +----------+
```
<!-- ascii-note:
intent: mostrar que un conector funciona en dos direcciones: leer (traer información: inbox, agenda, noticias) y actuar (ejecutar acciones: mandar mail, agendar reunión, abrir ticket, mandar mensaje).
emphasize: las dos flechas opuestas LEER vs ACTUAR sobre el mismo conector; que ACTUAR es la capacidad ejecutiva nueva de esta slide.
labels: izquierda = CHAT; centro = conector; derecha = tu mundo (mail, calendario, tickets, mensajes); flecha de lectura y flecha de acción.
-->

### Sources

- Model Context Protocol — https://modelcontextprotocol.io — el estándar define herramientas que ejecutan acciones sobre sistemas externos, no solo lectura: "AI applications ... which can access your data and take actions on your behalf" (verificado 2026-07-09).
- Anthropic Support — Getting started with custom connectors using remote MCP: https://support.claude.com/en/articles/11175166-getting-started-with-custom-connectors-using-remote-mcp — los conectores permiten a Claude "access and take action in these services" (verificado 2026-07-09).
- "corpus/mision - auto.zip.md" — el connector de Gmail **deja un borrador de correo** para el equipo (capacidad ejecutiva en acción, M3 y loop final).
- Verificación de primera mano del presentador (2026-07-09): la acción de **agendar/crear eventos vía el connector de Calendar** está chequeada y funciona.
- corpus/agentic-ai-deck.zip.md — Connectors como "las manos" del agente (tocar sistemas, no solo leerlos).

### Speaker notes

El giro de la sección: el conector era una antena que traía info; ahora es una mano que actúa. Los dos ejemplos de la lámina están verificados de primera mano: el borrador de Gmail (misión Atlas) y agendar por Calendar, que el docente chequeó y puede demostrar en vivo. El diagrama suma tickets y mensajes: nombrarlos como capacidad del ecosistema (el estándar MCP y los conectores lo permiten), sin prometer un conector puntual que no probamos. La práctica sana mientras aprenden es "borrador, no envío directo"; Atlas deja el borrador en Gmail y no lo manda. Cerrar sembrando la sección 3: una IA que se informa y actúa, más una agenda, puede trabajar sola. Tiempo objetivo: ~6 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: COMPACTAR 2.6 (ex 2.5). Título "Los conectores también actúan: del leer al hacer" (48c) → "Los conectores también actúan" (29c): cae el arco "del leer al hacer", que el style pass de round 7 habría quitado si hubiera tocado títulos. Los cuatro ejemplos bajan a dos, mail y calendario, los únicos verificados de primera mano por el presentador (2026-07-09). Tickets (Jira/ServiceNow) y mensajes (Slack) pasan a Speaker notes, que conservan el hedge intacto: siguen presentados como capacidad del ecosistema, sin prometer un conector puntual que no probamos (L002). Quitado el bullet de cierre "puede trabajar solo (sección 3)": es la transición hablada y ya vive en notes. ASCII y ascii-note sin tocar. Notes de 145 a 118 palabras.

---

# 3. El chat trabaja solo

**Goal of this section:** Que la audiencia entienda qué es una tarea programada (describir un trabajo una vez, fijar una cadencia, que corra sola), cómo se potencia con conectores (el resumidor semanal de mails) y la pregunta práctica antes de confiarle algo: ¿dónde corre? Local, con la computadora prendida, o nube. Todavía desde el mundo del chat.

**Presenter feedback:**

---

## 1. Tareas programadas desde el chat

### Content

- Te **suscribís a una respuesta** en vez de preguntar cada vez.
- El ejemplo: *"todos los días 8:00, resumí mi inbox, lo urgente arriba."*
- Existe en **ChatGPT** ("tasks") y en **Claude** (claude.ai, desde el navegador).

```ascii
        TAREA PROGRAMADA (se describe UNA vez)

  [reloj: lunes 8:00]
        |
        v
  +-----------+   usa conectores   +--------------+
  |  la tarea | -----------------> | mail / web / |
  |  corre    | <----------------- | calendario   |
  |  sola     |    trae la info    +--------------+
  +-----------+
        |
        v
  resumen listo en tu chat, cada semana,
  sin que lo pidas de nuevo
```
<!-- ascii-note:
intent: mostrar el ciclo de una tarea programada: un disparador de calendario (lunes 8:00) ejecuta la tarea, que usa los conectores (mail/web/calendario) para traer información y deja el resultado listo sin intervención del usuario.
emphasize: que se describe UNA vez y corre sola; el reloj como disparador; el uso de conectores dentro de la corrida; el resultado que "aparece" cada semana.
labels: reloj (cadencia) -> la tarea corre sola -> conectores (mail/web/calendario) -> resumen listo en tu chat.
-->

### Sources

- OpenAI Help — Tasks in ChatGPT: https://help.openai.com/en/articles/10291617-tasks-in-chatgpt — tareas programadas en el chat de ChatGPT (evidencia transversal del concepto; verificado 2026-07-09).
- Anthropic Support — Release notes (entrada del 7 de julio de 2026): https://support.claude.com/en/articles/12138966 — "scheduled tasks run with no device online"; sesiones remotas (beta); rollout empezando por Max (verificado 2026-07-09).
- Observación de primera mano del presentador (2026-07-09): tareas programadas activas en claude.ai en el navegador.
- TechCrunch (2026-07-07) — "The coding agent wars are spilling into the rest of the office": https://techcrunch.com/2026/07/07/the-coding-agent-wars-are-spilling-into-the-rest-of-the-office-claude-cowork/ — cobertura de prensa: expansión a web/mobile, corridas en background sin dispositivo activo, rollout Max (encuadre de terceros).
- Anthropic Support — Schedule recurring tasks in Claude Cowork: https://support.claude.com/en/articles/13854387-schedule-recurring-tasks-in-claude-cowork — la forma Cowork (se desarrolla en la sección 6).
- "corpus/mision - auto.zip.md" — el flujo programado de Atlas (Step 3.3): la semilla del "resumidor que corre solo".

### Speaker notes

Describís el trabajo una vez, elegís cadencia (diaria, semanal, a demanda) y corre sola avisándote con el resultado. Además hereda tus conectores: mail, web, calendario. El resumidor de mails engancha porque el inbox desbordado lo viven todos. Variante semanal: "los lunes a las 8:00, resumime la semana del calendario + los mails sin responder". Contarlo en primera persona ("mi resumen de las 8:00"). ChatGPT lo llama "tasks" (recordatorios, briefings, monitoreo); Claude ya las ofrece en claude.ai desde el navegador. Si el rollout lo permite, mostrarlas en vivo desde la cuenta del docente. La pregunta de dónde corre la tarea viene en la próxima slide; no adelantarla. En la sección 6 vuelven, sobre carpetas y archivos reales. Tiempo objetivo: ~6 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: COMPACTAR 3.1. Quitado el bullet "**Tarea programada** = pedido descrito **UNA vez** + cadencia → corre sola y te avisa.": el ASCII lo titula ("TAREA PROGRAMADA (se describe UNA vez)"), lo dibuja (reloj → "la tarea corre sola") y su ascii-note lo nombra en `emphasize`. Quitado "La tarea usa tus **conectores** (mail, web, calendario).": es la caja del medio del diagrama, también en `emphasize`. Las dos ideas ya vivían en Speaker notes, así que fue merge y no traspaso. Quedan 3 bullets: te suscribís a una respuesta, el ejemplo de las 8:00, y dónde existe (ChatGPT / Claude). Notes de 155 a 117 palabras. La observación de primera mano del presentador (claude.ai en el navegador, 2026-07-09) queda intacta en Sources. ASCII y ascii-note sin tocar.

---

## 2. ¿Dónde corre tu tarea? Local vs nube

### Content

- Antes de confiarle algo a una tarea programada, **sabé dónde corre**.
- Si la tarea necesita **archivos o apps locales**, corre **local siempre**.

```ascii
   tu tarea programada: ¿DONDE corre?
              |
      +-------+----------------------+
      v                              v
  LOCAL (hoy, la mayoria)      NUBE (beta, jul 2026 ->)
  · compu prendida             · sin compu prendida
  · app abierta                · rollout gradual (Max 1ro)
  · apagada => se saltea,      · PERO: archivos/apps
    corre al volver              locales => local igual
  · ojo notebooks suspendidas
```
<!-- ascii-note:
intent: mostrar la bifurcación práctica de una tarea programada según dónde corre: LOCAL (computadora prendida + app abierta; si está apagada se saltea y corre al volver; cuidado con notebooks que se suspenden) vs NUBE (sin computadora, beta desde julio 2026, rollout Max primero; excepción: tareas con archivos/apps locales corren local igual).
emphasize: la bifurcación como pregunta ("¿DÓNDE corre?"); en LOCAL los tres cuidados prácticos (prendida, app abierta, se saltea); en NUBE que no hace falta la compu pero es beta/rollout gradual, con la excepción de archivos locales.
labels: raíz = tu tarea programada ¿dónde corre?; rama izquierda = LOCAL (hoy, la mayoría) con cuidados; rama derecha = NUBE (beta, julio 2026) con condiciones.
-->

### Sources

- Anthropic Support — Schedule recurring tasks in Claude Cowork: https://support.claude.com/en/articles/13854387-schedule-recurring-tasks-in-claude-cowork — ejecución remota ("run on their cadence even when your computer is asleep or the Claude Desktop app is closed") y la excepción local: "If a scheduled task requires local files or apps, it will only run locally" (verificado 2026-07-09).
- Anthropic Support — Release notes (7 de julio de 2026): https://support.claude.com/en/articles/12138966 — "scheduled tasks run with no device online"; beta, rollout gradual empezando por Max (verificado 2026-07-09).
- TechCrunch (2026-07-07): https://techcrunch.com/2026/07/07/the-coding-agent-wars-are-spilling-into-the-rest-of-the-office-claude-cowork/ — corridas en background sin dispositivo activo, disponible primero para suscriptores Max (encuadre de terceros).
- Comportamiento local "se saltea y corre al volver": documentado en la versión anterior del artículo 13854387 (verificada en junio 2026, cuando la ejecución era solo local); la versión actual ya no lo detalla — mantenido como cuidado práctico del modo local, con esa atribución.

### Speaker notes

Hoy conviven dos realidades. Una: la nube existe desde el 7 de julio de 2026, la tarea corre sin tu compu, pero es beta y llega de a poco, empezando por el plan Max. Dos: mientras a tu cuenta no le llegue, la tarea corre local. Computadora prendida y app abierta, o no corre. Es lo que la mayoría va a vivir este cuatrimestre. Si la máquina está apagada o suspendida a la hora programada, la corrida se saltea y se ejecuta al volver (comportamiento documentado cuando la ejecución era solo local; el artículo actual ya no lo detalla, decirlo como cuidado práctico y no como spec). Las notebooks se suspenden solas; revisar la configuración de energía si el resumen de las 8:00 nunca aparece. La excepción que sobrevive incluso con nube: una tarea que necesita tus archivos o apps locales corre local siempre. Anticipa la sección 6: las tareas de Cowork viven de tus carpetas. Antes de confiarle el reporte del lunes, contestá "¿dónde corre esto?". Tiempo objetivo: ~5 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: COMPACTAR 3.2 (el Composer descartó PARTIR: es una sola bifurcación con un guion largo, no dos ideas). Era el caso más puro del defecto de la sección: las seis líneas de Content eran el diagrama LOCAL/NUBE transcripto. Quedan 2 bullets: la pregunta que hay que contestar antes de confiarle algo a una tarea, y la excepción que sobrevive al rollout de nube ("si la tarea necesita archivos o apps locales, corre local siempre", quote verificada del artículo 13854387, re-fetcheado 2026-07-09), que es el remate de la lámina. Nube beta/rollout Max, app abierta, "se saltea y corre al volver" y las notebooks que se suspenden solas ya estaban en el ASCII, en su `emphasize` y en Speaker notes: fue merge, nada se perdió ni se duplicó. Notes de 212 a 171 palabras. Quedan sobre las ~120 a propósito (L002 > la guía de palabras): intactos la fecha del 7 de julio de 2026, el hedge beta + rollout Max-first, la quote verificada de la excepción local, y la atribución completa de "se saltea y corre al volver" a la versión anterior del artículo ("el artículo actual ya no lo detalla, decirlo como cuidado práctico y no como spec"). Lo recortado fue andamiaje de guion, no sustancia. ASCII y ascii-note sin tocar.

---

# 4. Qué cambia con Cowork

**Goal of this section:** El salto grande de la charla. Mostrar por qué Cowork es otra categoría de herramienta y qué cambia en tu rol: dejás de tipear un mensaje a la vez y empezás a delegar un resultado. Ubicar las tres superficies de Claude, instalar el superpoder (la herramienta de propósito general del knowledge worker, con el español como lenguaje) y la nueva habilidad base. Cierra con el mapa de lo que viene.

**Presenter feedback:**

---

## 1. Las tres superficies de Claude

### Content

- **Web/Chat**: navegador, tareas puntuales. *Donde estuvimos hasta ahora.*
- **Claude Code**: terminal; developers.
- **Cowork**: GUI de escritorio, trabajo multipaso sobre archivos reales. *El resto de la charla vive acá.*

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
<!-- ascii-note:
intent: mostrar que las tres superficies corren sobre los mismos modelos Claude, y que Code+Cowork además comparten el mismo engine de agente (Claude Agent SDK), mientras Web/Chat es la superficie de chat de ese modelo.
emphasize: la caja base "MISMOS MODELOS CLAUDE" como cimiento de las tres; el lazo "Agent SDK" que une Claude Code y Cowork (no Web/Chat); resaltar Cowork como el foco de la charla.
labels: tres columnas (Web/Chat = chat, Claude Code y Cowork = Agent SDK) sobre una base de modelos Claude compartida.
-->

### Sources

- corpus/agentic-ai-deck.zip.md — "Same engine. Different surface." (key claims; slide 7.1 "Claude Code vs Cowork — the close").
- "corpus/mision - auto.zip.md" — framing de arquitectura Cowork (local, GUI, sin terminal).
- Anthropic — Claude Cowork (product page): https://www.anthropic.com/product/claude-cowork — "built on the very same foundations as Claude Code" (confirma que Cowork comparte base con Claude Code).
- Anthropic Engineering — Building agents with the Claude Agent SDK: https://www.anthropic.com/engineering/building-agents-with-the-claude-agent-sdk — el engine de agente común (Agent SDK) sobre el que se construyen Claude Code y Cowork.

### Speaker notes

Abrir conectando con el recorrido: hasta acá todo pasó en la superficie de chat, ahora la IA baja a tu computadora. Primero, el mapa. La precisión técnica, para decir y no para la lámina: las tres caras corren sobre los mismos modelos Claude. Cowork está construido sobre las mismas bases que Claude Code (el Claude Agent SDK), así que Code y Cowork comparten además el engine de agente, con los mismos archivos, Skills, MCP y el mismo loop de plan, aprobar y redirigir. Web/Chat es ese mismo modelo en una superficie de chat, sin el loop agéntico completo. El resto de la charla vive en Cowork, la cara para quien no vive en una terminal. Claude Code aparece solo como contraste. Tiempo objetivo: ~5 min.

### Presenter feedback

- [closed] 2026-06-08 — "No estoy tan seguro si es correcto que es el mismo motor. Hhay distintos motores agenticos que empujan todo. Revisar esto y conformarlo con fuentes."
  Resolution: Claim verificado y precisado: las tres superficies comparten los mismos modelos Claude; Claude Code y Cowork comparten el engine de agente (Claude Agent SDK, Cowork está construido sobre las bases de Claude Code); Web/Chat es ese modelo en superficie de chat. Reescrito el primer bullet de Content y el ASCII (base = MISMOS MODELOS CLAUDE + lazo Agent SDK Code↔Cowork) y ascii-note; añadidas dos fuentes externas de Anthropic.
- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: COMPACTAR 4.1. Quitado el bullet de transición hablada ("Ya extendiste el chat. Ahora la IA baja a tu computadora. Primero, el mapa."): vive en la primera oración de Speaker notes. Quitado el bullet "Mismos modelos Claude en las tres caras; Code y Cowork comparten además el engine de agente (Agent SDK). Web/Chat = superficie de chat.": es la base del ASCII (caja "MISMOS MODELOS CLAUDE" + lazo Agent SDK) y su ascii-note lo nombra entero en `emphasize`. El claim del [closed] del 2026-06-08 NO se perdió ni se aflojó: la precisión verificada (mismos modelos Claude en las tres; Code y Cowork comparten el Agent SDK porque Cowork está construido sobre las bases de Claude Code; Web/Chat = ese modelo en superficie de chat) pasa completa a Speaker notes, y sus cuatro fuentes quedan intactas en Sources (L002). Quedan 3 bullets: las tres superficies. Notes de 139 a 125 palabras; quedan levemente sobre las ~120 porque la precisión verificada bajó del body a las notas. ASCII y ascii-note sin tocar.

---

## 2. El superpoder de Cowork

### Content

- Cowork **no** es "Claude instalado en tu compu": **cambia por completo la forma de trabajar.**
- La **herramienta de propósito general del knowledge worker**. El "lenguaje de programación" es el español.
- Anthropic: **"Claude Code para el resto de tu trabajo"**.

### Sources

- corpus/agentic-ai-deck.zip.md — posicionamiento Cowork vs Claude Code ("Same engine. Different surface."; Cowork = la cara para knowledge workers sin terminal; slide 7.1 "Claude Code vs Cowork — the close").
- Anthropic — Claude Cowork (product page): https://www.anthropic.com/product/claude-cowork — encuadre oficial: Cowork como "Claude Code para el resto de tu trabajo"; construido sobre las mismas bases que Claude Code.
- Claude blog — Cowork research preview ("Claude Code power for knowledge work"): https://claude.com/blog/cowork-research-preview — la ambición de llevar el poder de Claude Code al trabajo del conocimiento; Cowork generaliza un éxito probado primero con developers.
- CNBC — Anthropic's Claude Cowork targets the office worker: https://www.cnbc.com/2026/02/24/anthropic-claude-cowork-office-worker.html — encuadre de público general / office worker (tercero, no Anthropic).

### Speaker notes

El beat de "¿y a mí por qué me importa?". Abrir con las palabras del presentador: Cowork NO es "Claude instalado en tu computadora", es un cambio completo en la forma de trabajar. Hasta acá la audiencia extendió un chat; esta lámina anuncia otra categoría de herramienta. El "lenguaje de programación" acá es el español: describís lo que querés y el agente lo hace. Lo que sí es de Anthropic, y va citado como framing propio, es "Claude Code para el resto de tu trabajo": que cualquier knowledge worker sienta con Cowork lo que los ingenieros ya sienten con Claude Code. Cowork generaliza algo que funcionó primero con developers. La analogía que engancha viene en la próxima lámina. Tiempo objetivo: ~2-3 min.

### Presenter feedback

- [closed] 2026-06-09 — "El contenido esta bien pero es mucho texto, necesitamos hacerla mas compacto. No pierdas el core."
  Resolution: Compactado el Content de 1.2 al core (Cowork = herramienta de proposito general del knowledge worker / 'Claude Code para el resto de tu trabajo'; analogia 'nuevo Excel' atribuida a analistas; por que importa para bioingenieria), reduciendo de 5 bullets largos a 4 concisos. El detalle de soporte (publico, paralelo developers, 'nacido generalizando') ya vive en Speaker notes. Visual ASCII conservado.
- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: PARTIR (mitad A). La ex 4.2 "El superpoder de Cowork: la herramienta de propósito general del knowledge worker" (81c) cargaba dos ideas: el claim (Cowork es otra categoría de herramienta) y la analogía (el nuevo Excel). El [closed] del 2026-06-09 pedía compactarla y se compactó, pero volvió a pasarse de largo: compactar era el movimiento equivocado porque son dos láminas. Esta mitad se queda con el claim y con el título, así que hereda ese [closed]. Título a "El superpoder de Cowork" (23c). Se conserva verbatim el ancla del presentador "Cowork NO es Claude instalado en tu compu": es un contraste binario, pero la negación ES el mensaje (protegido desde el style pass de round 7). Sin diagrama: el ASCII Excel→herramientas agénticas es contenido de la mitad B y se va entero con ella. Sources repartidas: acá el corpus del deck, la product page ("Claude Code para el resto de tu trabajo", framing propio de Anthropic, L002), el blog de research preview y CNBC. Notes de 243 a 122 palabras.

---

## 3. La nueva habilidad base

### Content

- **"El nuevo Excel"** *(encuadre de analistas e industria, no de Anthropic)*.
- Gestión: la habilidad base se redefine **ahora**; llegar temprano es ventaja.

```ascii
TRABAJO DE OFICINA: la herramienta de proposito general

 ~40 anios                              ahora
+----------------------+    ===>    +-----------------------------+
| EXCEL                |            | HERRAMIENTAS AGENTICAS      |
| lingua franca del    |            | Claude Code  (developers)   |
| trabajo de oficina   |            | Cowork       (knowledge     |
| (sin programar)      |            |               worker)       |
+----------------------+            +-----------------------------+
 la habilidad base de ayer           la nueva habilidad base
```
<!-- ascii-note:
intent: encuadrar el "superpoder" de Cowork como herramienta de propósito general del knowledge worker, usando la analogía Excel (40 años, habilidad base de oficina) -> herramientas agénticas (Claude Code para developers, Cowork para knowledge workers) como la nueva habilidad base.
emphasize: la flecha temporal de Excel (ayer) a las herramientas agénticas (ahora); el paralelo Claude Code=developers / Cowork=knowledge worker; que la analogía Excel es encuadre de industria, no claim oficial.
labels: dos cajas — EXCEL (lingua franca, sin programar) a la izquierda; HERRAMIENTAS AGENTICAS (Claude Code = developers, Cowork = knowledge worker) a la derecha; pie "habilidad base de ayer" -> "nueva habilidad base".
-->

### Sources

- "Claude Code is the New Excel" (ensayo de analista): https://nextword.substack.com/p/claude-code-is-the-new-excel — origen de la analogía del "nuevo Excel" (atribuir AQUÍ, NO a Anthropic).
- CNBC — Anthropic's Claude Cowork targets the office worker: https://www.cnbc.com/2026/02/24/anthropic-claude-cowork-office-worker.html — encuadre de terceros sobre el trabajo de oficina como destino de la herramienta (prensa, no Anthropic).
- corpus/agentic-ai-deck.zip.md — el paralelo que dibuja el diagrama: Claude Code = developers, Cowork = la cara para knowledge workers sin terminal (slide 7.1 "Claude Code vs Cowork — the close").

### Speaker notes

El gancho es la analogía del Excel, dicha con cuidado. Durante unas cuatro décadas, saber Excel fue la habilidad base del trabajo de oficina: sin programar, resolvías el 80% del trabajo de conocimiento. La tesis de varios analistas de la industria es que las herramientas agénticas, Claude Code para los que programan y Cowork para los que no, van camino a ser esa nueva habilidad base. Atribuirlo a analistas e industria, "hay quien lo llama el nuevo Excel", y NO a Anthropic. Cerrar aterrizándolo en la audiencia: vienen del mundo de la gestión, no programan, y por eso les sirve. La habilidad base se está redefiniendo ahora y llegar temprano es ventaja. Ahora pasamos a la mecánica: cómo se delega. Tiempo objetivo: ~2-3 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: PARTIR (mitad B). Segunda mitad de la ex 4.2 (81c): la analogía del Excel y por qué le importa a esta audiencia. Título "La nueva habilidad base" (23c). El ASCII Excel→herramientas agénticas y su ascii-note se movieron enteros desde la mitad A, sin editar: son literalmente el contenido de esta lámina, y por eso la mitad A se quedó sin visual propio. El [closed] del 2026-06-09 se quedó con la mitad A, que hereda el título de la lámina original. Content en 2 bullets: la atribución de la analogía y el remate para gestión. El par "Claude Code = developers / Cowork = knowledge worker" y los "~40 años de Excel" salen del body porque el diagrama los dibuja y su ascii-note los nombra en `emphasize`; se dicen en voz alta desde Speaker notes. La atribución NO baja al ascii-note: se queda en el body, en lámina, porque es load-bearing (L002) y un ascii-note es una pista de render, no texto garantizado. La analogía es de analistas e industria, nunca de Anthropic. Sources repartidas: acá el ensayo de nextword (origen de la analogía), CNBC (encuadre de prensa) y el corpus del deck (el paralelo del diagrama). Notes de 243 a 124 palabras. Las dos mitades suman los ~4-5 min de la lámina original.

---

## 4. El cambio de paradigma

### Content

- La frase de la sesión: **"Dejás de tipear un mensaje a la vez y empezás a entregar un resultado."**
- Anthropic: *"menos una sesión de chat, más asignarle tareas a un colega."*
- Chatear vs delegar:

| | Chatear | Delegar a un agente |
|---|---|---|
| Cómo trabajás | Un mensaje a la vez | Describís un resultado |
| Los pasos | Los hacés vos | El agente planifica y ejecuta |
| La salida | Texto en la ventana | Archivos en tu disco |
| Tu rol | Tipear el próximo prompt | Leer el plan, guiar a mitad de camino |

### Sources

- corpus/agentic-ai-deck.zip.md — "Stop prompting. Start delegating." (slide 2.3 the reframe); tabla "Chatting vs Delegating" (slide 3.16).
- "corpus/mision - auto.zip.md" — "el verdadero premio no es Atlas: sos vos, dominando Claude Cowork"; "Conversá, no programes."
- Anthropic — Claude Cowork (product page): https://www.anthropic.com/product/claude-cowork — refuerza el paradigma: trabajar con Cowork "se parece menos a una sesión de chat y más a asignarle tareas a un colega".
- (técnico, opcional) Anthropic Engineering — Building agents with the Claude Agent SDK: https://www.anthropic.com/engineering/building-agents-with-the-claude-agent-sdk — por qué el loop plan→ejecutar→guiar es lo que define a un agente frente a un chat.

### Speaker notes

El concepto-ancla de la charla. Los conectores y las tareas programadas extendieron qué puede hacer el chat; el agente cambia tu rol. Desarrollar la frase de la sesión: el agente planifica y trabaja sobre tus archivos reales, y vos lo guiás en lugar de hacer cada paso. Son dos formas de trabajar, no dos productos. Usar la tabla para hacerlo concreto: la salida deja de ser texto en una ventana y pasa a ser archivos en tu disco. Anticipar la misión: vamos a "contratar" a Atlas, un analista de mercado virtual, y entrenarlo una vez para que después trabaje solo. Cerrar citando a Anthropic, "menos una sesión de chat, más asignarle tareas a un colega". Tiempo objetivo: ~5 min.

### Presenter feedback

- [closed] 2026-06-08 — "Existe algin ling adicional que podriamos poner que refuerze este paradigma ?"
  Resolution: Añadidas referencias externas que refuerzan el paradigma de delegación: cita de la product page de Cowork ('menos una sesión de chat, más asignarle tareas a un colega') como bullet quotable en Content y como remate en Speaker notes, más el enlace de Anthropic Engineering sobre el Agent SDK.
- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: COMPACTAR 4.4 (ex 4.3). Título "De chat a agente: el cambio de paradigma" (40c) → "El cambio de paradigma" (22c): colapsa el compuesto y mata el arco "de X a Y" que el style pass de round 7 sacó de la prosa pero nunca de los títulos. La lámina estaba sobre el techo de densidad: 3 bullets + tabla + ASCII. La tabla (Chatear vs Delegar) y el ASCII (ANTES/AHORA) son el MISMO contraste y el ASCII es la versión pobre, así que el ASCII se fue entero a Cut material con su ascii-note, sin editar, y con el motivo de una línea. La tabla se queda. Quitado el bullet de transición ("Ya extendiste qué hace el chat. Ahora cambia tu rol: pasás a delegar."): Speaker notes ya lo decían entero en su segunda oración ("los conectores y las tareas programadas extendieron qué puede hacer el chat; el agente cambia tu rol"), así que fue merge y no traspaso. Intactos el ancla de la sesión y la cita de Anthropic con su atribución y sus fuentes: el [closed] del 2026-06-08 sigue en pie (L002). De Speaker notes salió "si se llevan una sola idea, que sea esta: el valor está en delegar un resultado y guiar el proceso", porque repetía el ancla que ya está en lámina; también merge, no pérdida. Notes de 150 a 119 palabras. Ambas sumadas a Sources.

---

## 5. Bloques que se apilan

### Content

- **Bloques que se apilan**: no es una escalera; usás solo los que necesitás.
- El mapa de la charla: ya recorrimos los tres primeros y **estamos acá**. Volvé para ubicarte.
- **Plugins** = capa transversal de distribución (sección 7).

```ascii
+============== PLUGINS (capa transversal: empaquetan y distribuyen) ==============+
||                                                                                ||
||  +----------------------+  "quiero compartir el resultado vivo"                ||
||  | LIVE ARTIFACTS       |                                                      ||
||  +----------------------+                                                      ||
||  +----------------------+  "no quiero repetir la tarea / delegar en paralelo"  ||
||  | SKILLS / SUBAGENTES  |  (avanzado, seccion 7)                               ||
||  +----------------------+                                                      ||
||  +----------------------+  "quiero que la IA entienda mi material"             ||
||  | ARCHIVOS .MD         |                                                      ||
||  +----------------------+                                                      ||
||  +----------------------+  "contexto fijo + todo en un lugar"                  ||
||  | INSTRUCCIONES +      |                                                      ||
||  | PROJECTS             |                                                      ||
||  +----------------------+                                                      ||
||  +----------------------+  "quiero que trabaje sobre mis archivos"   <== ACA   ||
||  | COWORK: carpetas     |                                                      ||
||  +----------------------+                                                      ||
||  +----------------------+  "quiero que corra solo"                   (visto)   ||
||  | TAREAS PROGRAMADAS   |                                                      ||
||  +----------------------+                                                      ||
||  +----------------------+  "quiero info real + que actue"            (visto)   ||
||  | CONECTORES           |                                                      ||
||  +----------------------+                                                      ||
||  +----------------------+  "respondia solo de memoria"               (visto)   ||
||  | EL CHAT              |                                                      ||
||  +----------------------+                                                      ||
+==================================================================================+
   los bloques se apilan (cada uno suma autonomia); PLUGINS los distribuye a todos
```
<!-- ascii-note:
intent: presentar el arco completo de la charla como bloques que se apilan (no una pirámide/escalera estricta): el chat (base) -> conectores -> tareas programadas -> Cowork (carpetas/archivos) -> Instrucciones+Projects -> archivos .md -> Skills/Subagentes -> Live Artifacts, con Plugins como BANDA TRANSVERSAL que envuelve/distribuye todo. Los tres bloques de abajo están marcados "(visto)" y el bloque Cowork lleva el marcador "estamos acá".
emphasize: el marcador "<== ACÁ" en el bloque Cowork; los "(visto)" en chat/conectores/tareas programadas; que Plugins es transversal (banda que rodea la pila, distinto color), NO un nivel más; el par bloque↔problema en cada nivel.
labels: banda exterior = PLUGINS (capa transversal, distribución). Bloques apilados (base→cima): El chat · Conectores · Tareas programadas · Cowork: carpetas · Instrucciones+Projects · Archivos .md · Skills/Subagentes · Live Artifacts, cada uno con su frase-problema a la derecha.
-->

### Sources

- corpus/agentic-ai-deck.zip.md — progresión de building blocks del deck (Instrucciones → Projects → Skills → Connectors/MCP → Schedule → Live Artifacts); la idea de "pila" es la lectura ordenada de esa progresión, re-secuenciada al arco chat-primero de esta charla.
- "corpus/mision - auto.zip.md" — la misión Atlas arma estas piezas una por una.

### Speaker notes

El mapa de toda la sesión: arranca en el chat que ya usan, no en Cowork. Aprovechar el efecto acumulado: los tres de abajo ya los recorrimos; señalar "estamos acá", Cowork, donde la IA trabaja sobre carpetas y archivos reales. Leer cada bloque por su problema, que el diagrama trae al lado: cada pieza nace de una frustración concreta. Cuidado con la metáfora: no es una pirámide donde cada capa depende de todas las de abajo; los bloques se apilan y se combinan. Prometer el roadmap: vamos a recorrer cada bloque, uno por uno, en este orden, y pueden volver acá entre secciones para ubicarse. Al final, la pila entera es Atlas. Plugins envuelve la pila y no es un bloque más: empaqueta y distribuye varias piezas a la vez. Lo vemos en la sección 7. Tiempo objetivo: ~3-4 min.

### Presenter feedback
- [closed] 2026-06-09 — "Es la represnetacion como piramide la correcta ?."
  Resolution: Revisado: la piramide estricta implicaba erroneamente que cada capa depende de todas las de abajo. Cambiado a un diagrama de 'bloques que se apilan' (se combinan, no se exigen), con texto que lo aclara, y Plugins como banda transversal. ascii-note y Speaker notes actualizados para quitar la lectura de piramide-dependencia.
- [closed] 2026-06-09 — "Tenemos que hacer claro que vamos a ir sobre cada uno de estos conceptos."
  Resolution: Agregada linea explicita en Content y Speaker notes: 'este es el mapa de la charla; vamos a recorrer cada bloque, uno por uno, en este orden' — y que se puede volver a la slide como 'estamos aca' entre secciones.
- [closed] 2026-06-09 — "deberiamos aregar tal vez plugins como transversar como una forma de distribuir parte de todo esto.  Agregar un slide si no existe sobre esto."
  Resolution: Plugins representado como CAPA TRANSVERSAL de distribucion en el diagrama (banda que envuelve la pila de bloques, no un peldano mas), con bullet dedicado en Content. La slide de Plugins ya existe (6.2) y ademas se agrego una slide nueva de ciclo de vida de Plugins en Team (6.3); ascii-note actualizado para marcar Plugins como transversal.
- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: COMPACTAR 4.5 (ex 4.4). Título "El mapa de la charla: bloques que se apilan" (43c) → "Bloques que se apilan" (21c). Quitados los 9 sub-bullets que emparejaban cada bloque con su problema recurrente: el diagrama de 30 líneas los dibuja uno por uno, con la frase-problema al lado de cada bloque, y su ascii-note los nombra en `emphasize` ("el par bloque↔problema en cada nivel") y los lista enteros en `labels`. Verificados los 9 pares contra el ASCII antes de quitarlos: los 9 están dibujados (Instrucciones y Projects comparten caja). Fue merge, no borrado: la lámina sigue mostrando cada par, en el diagrama que es su lugar. Quedan 3 bullets: que no es una escalera, "estamos acá" para ubicarse, y Plugins como capa transversal. Los tres [closed] previos siguen en pie y su sustancia queda intacta en Speaker notes: el cuidado con la metáfora de la pirámide (2026-06-09), la promesa explícita de recorrer cada bloque uno por uno (2026-06-09) y Plugins como banda que envuelve la pila, no un peldaño más (2026-06-09). Notes de 181 a 140 palabras; quedan sobre las ~120 a propósito, porque comprimir más aplastaría alguno de esos tres beats protegidos. Cross-ref corregido en Content y en Speaker notes: la sección de Plugins pasó de 5 a 7. ASCII y ascii-note sin tocar (el ASCII todavía dice "seccion 5" en el bloque SKILLS / SUBAGENTES: reportado para un pase del ilustrador).
- [closed] 2026-07-15 — "El ASCII del mapa manda al público a la sección equivocada: dice 'seccion 5' para Skills/Subagentes y hoy esa sección es la 7. Arreglalo en el draft antes del freeze, no en el render." (origin: presenter-chat)
  Resolution: Corregido en el ASCII del mapa, línea del bloque `SKILLS / SUBAGENTES`: `(avanzado, seccion 5)` → `(avanzado, seccion 7)`. Es el último cross-ref stale de la renumeración de round 8 (la ex-sección 5 "Advanced" es hoy la 7 "Piezas avanzadas") y el único que vivía dentro de un diagrama, razón por la que los dispatches del pase de densidad lo reportaron sin tocarlo. Se arregla acá y no en `final.md` ni en el SVG porque una etiqueta con el número de sección equivocado es un defecto de contenido de Step 4, no de renderizado: el ilustrador nunca corrige contenido, así que un fix aguas abajo volvería a aparecer en cada re-render. Sustitución de un solo carácter, mismo ancho: las 28 líneas de la caja siguen midiendo 84 caracteres y los bordes `||` / `+===+` quedan intactos; cero cambios de geometría. El `ascii-note` se revisó y NO requería cambios: sus tres campos (`intent`, `emphasize`, `labels`) nombran Skills/Subagentes como bloque de la pila pero no citan ningún número de sección. Barrido independiente de los 17 bloques ASCII y sus notes del deck: no queda ninguna otra referencia stale a sección o slide dentro de un diagrama.

---

# 5. Tu espacio en Cowork

**Goal of this section:** Montar el lugar donde trabaja el agente: la interfaz de Cowork, las Instrucciones como contrato de trabajo, el Project como espacio fijo con su carpeta y su memoria, y la carpeta que le concedés, que es tu control de privacidad.

**Presenter feedback:**

---

## 1. Demo time

### Content

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
<!-- ascii-note:
intent: tarjeta/banner de "DEMO TIME" como señal visual fuerte al tope de la slide, para marcar el corte de conceptos a demo en vivo sobre la app real.
emphasize: el texto grande "> DEMO TIME"; sensación de cartel/placa (no un diagrama de flujo); que abajo se lee "pasamos a la app real de Cowork".
labels: banner DEMO TIME; subtítulo "Pasamos a la app real de Cowork".
-->

### Sources

- corpus/agentic-ai-deck.zip.md — slide 3.19 (modelo de aprobación Cowork); la demo de arranque sugerida ("organizá esta carpeta de 8 PDFs por tema y dame un resumen de un párrafo de cada uno").

### Speaker notes

Momento de demo en vivo. Cerrás los conceptos y abrís Cowork. Demo sugerida de arranque, la del deck: "Organizá esta carpeta de 8 PDFs por tema y dame un resumen de un párrafo de cada uno." Dejarlos ver a Claude planificar, tocar archivos y entregar, sin explicar la mecánica todavía. Que la sorpresa haga el trabajo. La anatomía de la pantalla viene en la lámina siguiente. Si la conexión falla o la demo se cuelga, saltar directo a esa lámina, que tiene la captura anotada de respaldo. Tiempo objetivo: ~5 min (la demo).

### Presenter feedback

- [closed] 2026-06-08 — "Antes de ir a "Instrucciones: ajustar el comportamiento sin repetirte", me gustaria algun especie de grafico introductorio que describa el problema (eg: no me quierio repetir -> Skill) y que ejemplifique esto tal vez en una especie de piramide de conceptors que se van apilando y proveyendo algo mas rico."
  Resolution: Insertada nueva slide 2.2 'Los bloques de Cowork: cada problema, una pieza' entre la demo y Instrucciones, con pirámide ASCII (base→cima: chatear, Instrucciones, Projects, Skills, Connectors/MCP, Schedule, Live Artifacts) que empareja cada capa con su problema recurrente ('no me quiero repetir → Skill') y la enmarca como el roadmap de la charla. Instrucciones renumerada a 2.3 y Projects a 2.4; sección 2 ahora tiene 4 slides.

- [closed] 2026-06-09 — "Agregar alguna imagen diga algo asi como "Demo time" !"
  Resolution: Agregado un banner ASCII render-driving '> DEMO TIME' (tipo tarjeta/placa, con ascii-note) al tope de la slide 2.1 como senal visual fuerte del corte a demo en vivo. No existe un asset con ese nombre; el banner ASCII es el deliverable que el ilustrador renderiza.

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: PARTIR (mitad A). La ex 5.1 "(Demo time) Conozcamos la interfaz de Cowork" (44c) cargaba dos ideas: la señal de corte a demo y la anatomía de la interfaz. Esta mitad se queda con la señal de corte. Título "Demo time" (9c). Lámina-interstitial: solo el banner ASCII, sin bullets y sin image ref. Quitado el bullet "**DEMO EN VIVO**: tour de la pestaña Cowork sobre la app real.": el banner lo dice ("Pasamos a la app real de Cowork") y su ascii-note lo nombra en `emphasize` y en `labels`. Las notes de una lámina-interstitial de demo SON el guion de la demo, así que quedan cargadas a propósito (93w): eso es contenido, no relleno. La partición resuelve además el Open question del banner (round 3): al separarse del screenshot, el banner queda como único bloque ASCII de su lámina y el pipeline de Polish lo trata como render-driving, así que el ilustrador SÍ lo renderiza en Step 6. Los dos [closed] previos se quedan acá, con la mitad que hereda la identidad de demo: el del 2026-06-09 porque el banner es su contenido, y el del 2026-06-08 porque su ancla es el beat de la demo. Sources repartidas: acá la demo de arranque del deck y el modelo de aprobación; la anatomía del screenshot va a la mitad B.

---

## 2. La interfaz de Cowork

### Content

![Anatomía de la pestaña Cowork — interfaz anotada](images/screenshot-cowork-tab.png)

- Señalar en vivo: modo **"Ask"**, selector de carpeta, pestañas **Scheduled** y **Live artifacts**, panel de **Project**.
- El control es la terna: **modo + aprobar/redirigir + carpeta concedida**.
- **Sin slash commands**: Cowork es GUI.

### Sources

- corpus/agentic-ai-deck.zip.md — "screenshot-cowork-tab.png" (anatomía Cowork, 14 elementos anotados; el asset más Cowork-funcional de la fuente); slide 3.19 (modelo de aprobación Cowork).

### Speaker notes

Recorrido de 2-3 minutos por la pantalla, sobre la app real, o sobre la captura anotada si la demo falló. Señalar el selector de modo, que viene en "Ask before acting" por defecto, cómo se concede una carpeta de trabajo, y dónde viven Scheduled y Live artifacts, que usamos más adelante. El control que tienen es esa terna: el modo, aprobar o redirigir cada paso, y qué carpeta le concediste. Aclarar de entrada que Cowork es GUI: no hay slash commands que memorizar, todo se hace con el mouse y en español. Tiempo objetivo: ~3 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: PARTIR (mitad B). Segunda mitad de la ex 5.1 (44c): la anatomía de la interfaz. Título "La interfaz de Cowork" (21c). El image ref `screenshot-cowork-tab.png` se muda entero acá, que es su lámina: la captura anotada de 14 elementos ES el contenido de este beat. Content en 1 imagen + 3 bullets (qué señalar en vivo, la terna de control, y que Cowork es GUI sin slash commands); el tercero se separó del segundo, que los tenía fundidos en una línea. Sin ASCII: el banner DEMO TIME se fue entero con la mitad A, sin editar, y esa separación es justamente lo que lo vuelve render-driving. Sources: acá la anatomía del screenshot. Notes en 96 palabras. Las dos mitades suman los ~8 min de la lámina original.

---

## 3. Instrucciones: el contrato

### Content

- Instrucciones = el **"contrato de trabajo"**: reglas en lenguaje natural que valen para todo, sin repetirlas.
- Ejemplo (Atlas):

```text
Sos Atlas, el analista de mercado de un equipo de trabajo.
Preparás un pulso semanal para colegas NO técnicos (incluido el jefe),
que se lee en 2 minutos antes de la reunión de los lunes.

· REGLA DE ORO: tus reportes son informativos y de uso interno.
  NUNCA son recomendaciones de inversión ni asesoramiento financiero.
  Siempre incluís esa aclaración al final.
```

### Sources

- corpus/agentic-ai-deck.zip.md — "the project context panel (GUI)" como lugar de las Instrucciones en Cowork; matriz de disponibilidad 3.3 (Persistent instructions, Cowork ⚠️).
- "corpus/mision - auto.zip.md" — texto exacto de las Project Instructions de Atlas (Step 1.1); "las Instrucciones son su contrato de trabajo".

### Speaker notes

Conectar con el paradigma: en lugar de re-explicarle el contexto cada vez, lo escribís una vez y vale para todo el Project. Mostrar el texto real de las Instrucciones de Atlas. Leer en voz alta lo que no entró en la lámina: Atlas sigue Apple, Microsoft y Nvidia, escribe en español claro y breve, sin jerga financiera, y si usa un término técnico lo explica en una línea. Destacar la regla de oro del disclaimer: acá van las reglas no negociables. Consejo de escritura: cortas y claras, en lenguaje natural. Dónde viven: en el panel de contexto del Project. No es un archivo que edités a mano; lo escribís en el panel y queda asociado al Project. Tiempo objetivo: ~7 min.

### Presenter feedback
- [closed] 2026-06-09 — "Sacar "En Cowork viven en el panel de contexto del Project (la GUI), no en un archivo `.md` editable. Equivalen al `CLAUDE.md` de Claude Code — mismo concepto, distinto mecanismo." Dejarlo en las notas. Re-revisa que la audiencia no tiene contacto con Claude Code asi que es conveniente no connectar o mencionar en el resto de la presentacion."
  Resolution: Removida de Content la frase 'En Cowork viven en el panel de contexto del Project (la GUI), no en un archivo .md editable. Equivalen al CLAUDE.md de Claude Code...'. Movida a Speaker notes en forma neutral ('viven en el panel de contexto del Project, no es un archivo que edites') SIN la equivalencia con Claude Code/CLAUDE.md, por la directiva de minimizar Claude Code fuera de la Seccion 1. Tambien limpiada la mencion a CLAUDE.md en Sources.
- [closed] 2026-06-09 — "Agregar un ejemplo en el slide de que podria ser un Instructions."
  Resolution: Agregado en Content un bloque de ejemplo concreto de Project Instructions (Atlas, de corpus/'mision - auto.zip.md'): quien es Atlas, empresas que sigue (Apple/Microsoft/Nvidia), audiencia no tecnica, tono espanol sin jerga, y la REGLA DE ORO 'nunca recomendaciones de inversion / no asesoramiento financiero'.

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: COMPACTAR 5.3 (ex 5.2). Título "Instrucciones: ajustar el comportamiento sin repetirte" (54c) → "Instrucciones: el contrato" (26c): el título ya cargaba en prosa lo que el primer bullet define, y "el contrato" es el ancla que la lámina y las notes usan. Estaba sobre el techo de densidad con 4 bloques (bullet + fence ```text de 12 líneas + un párrafo indentado + 2 bullets más); quedan 2 (el bullet del contrato y el ejemplo). El fence ```text SE CONSERVA: lo pidió el [closed] del 2026-06-09 ("Agregar un ejemplo en el slide de que podria ser un Instructions"), pero se recortó a las líneas que cargan el punto, quién es Atlas y la REGLA DE ORO. Los tres bullets de estilo de adentro del ejemplo (empresas que sigue, español sin jerga, explicar el término técnico) bajan a Speaker notes, que ahora indican leerlos en voz alta: el ejemplo sigue completo en el guion. Quitados los tres bullets de cierre: "Se escribe una vez; vale para todo el Project" repetía el bullet 1; "Cortas y claras" es narración y pasa a notes; "El lugar de las reglas no negociables" ya lo demuestra la REGLA DE ORO dentro del ejemplo, y se dice en voz alta. El [closed] del 2026-06-09 sobre CLAUDE.md sigue respetado: las notes dicen dónde viven las Instrucciones sin nombrar Claude Code. Notes de 86 a 121 palabras (crecieron por el ejemplo que bajó).

---

## 4. Projects: guardar todo en un lugar fijo

### Content

- Project = espacio autocontenido: **carpeta propia + memoria + lugar fijo**.
- Tres capas persistentes: Instrucciones · Knowledge base · Chats.
- Los chats del Project **no comparten contexto entre sí** (solo la base de conocimiento).

### Sources

- corpus/agentic-ai-deck.zip.md — definición de "Project (Chat/Cowork)" (tres capas; chats no comparten contexto).
- "corpus/mision - auto.zip.md" — "el Proyecto le da a Atlas una carpeta propia, memoria y un lugar fijo" (Step 1.1).

### Speaker notes

El Project es el contenedor de todo lo demás: Instrucciones, archivos, memoria. Las ventajas, para desarrollar a viva voz: todo queda organizado y reutilizable. Las Instrucciones valen para todo el Project, la memoria recuerda tus correcciones y preferencias, y los archivos viven en una carpeta concreta de tu disco. En la misión, el Project "Inteligencia de Mercado Semanal" apunta a `Documentos/Atlas-Mercado`. El punto práctico que sorprende: los chats no se hablan entre sí dentro del Project; si querés que recuerde algo, va a las Instrucciones o a la base de conocimiento. Las dos láminas que siguen bajan a pantalla cómo le concedés la carpeta y qué ve en el panel de contexto. Tiempo objetivo: ~6 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: COMPACTAR 5.4 (ex 5.3). Título sin cambios (39c, bajo el techo). De 5 bullets a 3. Los bullets 4 y 5 ("Vos concedés las carpetas con el selector del sistema operativo" y "Buena práctica: carpeta dedicada, nunca una con datos confidenciales") NO bajaron a notes: son el contenido de la lámina siguiente, que los enseña con capturas, así que se mudaron enteros a 5.5 "Concedé una carpeta". Sin duplicar: salieron de acá y aterrizaron allá. Quedan 3 bullets: el espacio autocontenido, las tres capas y los chats que no comparten contexto. Sources: quitada la cláusula "Working directory + permissions (folder picker del sistema)" del registro del corpus, porque ese claim se fue con los bullets; la fuente sigue citada en 5.5. Los dos [closed] del 2026-06-09 se mudaron a 5.5 con el contenido que originaron (el del settings.json porque su resolución ES el bullet del selector de carpetas; el del screenshot porque nombra `project.png` verbatim y engendró la lámina que ahora es 5.5). Notes de 139 a 116 palabras; el beat "el folder picker es el control de seguridad" salió de acá porque se fue con su contenido, y la línea de cierre ahora anuncia las DOS láminas siguientes. Tiempo de ~7 a ~6 min; los ~3 min de la ex 5.4 se reparten en ~2 + ~2, así que el bloque sigue en ~10 min.

---

## 5. Concedé una carpeta

### Content

- Vos concedés la carpeta con el **selector del sistema operativo**. Lo de afuera, Cowork no lo ve.

![Selector de carpeta de trabajo del Project](images/project.png)

- La carpeta ES tu control de privacidad: **nunca datos sensibles, credenciales o NDA.**
- Buena práctica: una **carpeta dedicada** al Project.

### Sources

- corpus/agentic-ai-deck.zip.md — "Working directory + permissions" (folder picker del sistema; lo concedido define el alcance).
- "corpus/mision - auto.zip.md" — el Project "Inteligencia de Mercado Semanal" apunta a `Documentos/Atlas-Mercado` (Step 1.1).

### Speaker notes

Baja a pantalla lo que contó la lámina anterior. Mostrar la captura del selector: es el mismo diálogo de carpetas del sistema operativo que ya usan todos los días. Ese es el control de qué toca Claude, y también su límite: Cowork solo ve lo que le concedés. No saltear el mensaje de seguridad: nunca una carpeta con datos sensibles, credenciales o material bajo NDA. La práctica sana es una carpeta dedicada al Project y nada más. Aterrizarlo en la misión: Atlas trabaja sobre `Documentos/Atlas-Mercado`. Tiempo objetivo: ~2 min.

### Presenter feedback

- [closed] 2026-06-09 — "Borrar no hay `settings.json` que editar."
  Resolution: Borrada la clausula 'no hay settings.json que editar' de Content; tambien limpiadas las menciones a settings.json en Sources y Speaker notes (referencia incidental a Claude Code) — queda 'lo controla el selector de carpetas del sistema operativo, no un archivo de configuracion'.
- [closed] 2026-06-09 — "Agregar un slide donde vamos a mostrar screenshoot de el selector de archivos y contecto como screenshoot. Usa project.png que esta en images."
  Resolution: Insertada nueva slide 2.5 'El selector de carpetas y el panel de contexto' tras Projects: como se concede una carpeta de trabajo (folder picker del sistema), donde vive el contexto del Project, y nota de seguridad (nunca conceder carpetas con datos sensibles). Cableadas ambas imagenes: images/project.png y images/context.png (ambas existen en disco).
- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: PARTIR (mitad A). La ex 5.4 "El selector de carpetas y el panel de contexto" (46c) era el peor defecto de densidad del deck: 5 bloques (bullet + imagen + bullet + imagen + bullet), dos capturas y 3 bullets en una lámina de 5.625 pulgadas, que desborda seguro. La "y" del título era el aviso. Esta mitad se queda con el acto de conceder la carpeta y con `project.png`. Título "Concedé una carpeta" (19c). Content en 3 bullets + 1 imagen: el selector del sistema, la carpeta como control de privacidad, y la carpeta dedicada. Bajaron acá los bullets 4 y 5 de la ex 5.3: el del selector se fundió con el bullet 1, que decía lo mismo, y el de la buena práctica quedó como bullet 3, con su "nunca datos confidenciales" fundido en el bullet de seguridad, que ya lo dice más fuerte (credenciales y NDA incluidos). Merge, no borrado. Los dos [closed] del 2026-06-09 vienen de la ex 5.3 con su contenido: el del settings.json porque su resolución es el bullet del selector, y el del screenshot porque nombra `project.png` verbatim. Sources repartidas: acá el folder picker y la carpeta de Atlas. Notes en 89 palabras.

---

## 6. El panel de contexto

### Content

![Panel de contexto del Project](images/context.png)

- El **panel de contexto** muestra qué sabe el Project: Instrucciones + base de conocimiento + carpeta concedida.

### Sources

- corpus/agentic-ai-deck.zip.md — definición del panel de contexto del Project ("the project context panel (GUI)").

### Speaker notes

Mostrar la captura del panel de contexto. Es donde el Project te muestra qué sabe: las Instrucciones que escribiste, la base de conocimiento que le cargaste y la carpeta que le concediste. Las tres capas del contexto, ahora en pantalla. El valor práctico: de un vistazo auditás qué contexto tiene el Project antes de pedirle nada. Tiempo objetivo: ~2 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides."
  Resolution: PARTIR (mitad B). Segunda mitad de la ex 5.4 (46c): el panel de contexto. Título "El panel de contexto" (20c). El image ref `context.png` se muda entero acá. Content en 1 imagen + 1 bullet: las tres capas en pantalla. El [closed] del 2026-06-09 que engendró la lámina original ("Agregar un slide donde vamos a mostrar screenshoot de el selector de archivos y contecto") nombra `project.png` verbatim, así que se quedó con la mitad A; queda registrado acá que también originó esta mitad y que `context.png` cumple su segunda parte. Sources repartidas: acá la definición del panel de contexto del corpus. Notes en 62 palabras. Las dos mitades suman los ~3 min de la lámina original más el minuto que cedió la ex 5.3.

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: Cross-ref stale corregido en el barrido final del deck: Speaker notes decían "Las tres capas de la lámina anterior, ahora en pantalla" → "Las tres capas del contexto". La ref estaba doblemente rota tras la partición de la ex 5.4: la lámina anterior es hoy 5.5 "Concedé una carpeta", que no tiene tres capas, y las "tres capas" de 5.4 "Projects" son otra terna (Instrucciones · Knowledge base · Chats) que no coincide con la que esta lámina lista (Instrucciones + base de conocimiento + carpeta concedida). Content, imagen y Sources sin tocar.

---

# 6. Trabajar y entregar

**Goal of this section:** Cómo trabaja el agente dentro de ese espacio: los archivos `.md` como material de trabajo, las tareas programadas corriendo solas sobre tus carpetas, y lo que te entrega al final.

**Presenter feedback:**

---

## 1. Archivos .md: la lingua franca

### Content

- Un `.md` (Markdown) = **texto plano** + estructura liviana: `#` títulos, `-` listas, `**negrita**`, tablas.
- Se lee a ojo con cualquier editor, y la máquina entiende la estructura.
- **Metadata (header YAML)**: declara *qué es* el archivo y *cuándo* usarlo. Vuelve con las Skills (sección 7).
- La **lingua franca** del mundo LLM: el modelo lee texto. Portable y versionable.

### Sources

- corpus/agentic-ai-deck.zip.md — "Markdown is the lingua franca"; definición de Skill (SKILL.md con YAML frontmatter: name + description; "Description drives triggering — semantic, not keyword").
- "corpus/mision - auto.zip.md" — "mismo estándar SKILL.md" entre Cowork y Codex (Cowork vs Codex).

### Speaker notes

Beat de enseñanza propio, no un paréntesis: en el mundo de agentes el formato de tus archivos importa, y gana el más simple. Abrir un `.md` real en pantalla si se puede. Mostrar que es texto plano con marcas mínimas (un `#`, unas listas) y que igual se ve estructurado; se abre con cualquier editor, en cualquier máquina, sin formato propietario. Lo que ves es lo que hay. La idea a transmitir: el modelo lee texto, y cuanto menos formato opaco haya entre tu contenido y el modelo, mejor trabaja. Por eso es portable y versionable; el mismo estándar funciona entre herramientas. Presentar la metadata (header YAML entre `---`) como la etiqueta del frasco: dice qué es el archivo y cuándo usarlo. La `description` de una Skill es eso (activación semántica, no por palabra clave; sección 7). Alcance: qué es y por qué importa, sin detalle fino de formato. La próxima slide lo baja a la práctica: en qué formato conviene trabajar. Tiempo objetivo: ~5 min.

### Presenter feedback

- [closed] 2026-06-09 — "Agregar un slide que muestre como es un skill que muestren un poco la anatomia de MD y metadata."
  Resolution: Insertada nueva slide 3.3 'Anatomia de un SKILL.md' tras el sideway, con ASCII render-driving de un SKILL.md real: bloque de metadata/header YAML (name/description = 'que es / cuando se activa') vs cuerpo Markdown (instrucciones = 'que hace'), usando reporte-semanal como ejemplo. ascii-note incluido. Alto nivel, refuerza el sideway MD/metadata sin deep dive de formato.

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: COMPACTAR 6.1, solo el título. "Archivos .md: el lenguaje en el que la IA piensa mejor" (54c) → "Archivos .md: la lingua franca" (30c): el título cargaba en prosa el argumento que el bullet 4 ya hace, y "lingua franca" es la frase de la propia lámina (y del corpus: "Markdown is the lingua franca"). El cuerpo NO se tocó: 4 bullets, sin visual, dentro del techo de densidad, y las 166 palabras de notes son guion de entrega de una sola idea. El Composer fue explícito en no inventar trabajo acá. Sí se arreglaron los dos cross-refs stale de la renumeración de round 8: Content "Vuelve con las Skills (sección 5)" → sección 7, y Speaker notes "activación semántica, no por palabra clave; sección 5" → sección 7. La ex-sección 5 "Advanced" es hoy la 7.

---

## 2. Trabajá en .md, exportá al final

### Content

- Vale doble: la **memoria** del agente (texto plano) y tus **archivos de trabajo** (en el Project).
- Regla de bolsillo: *editá en `.md`, entregá en lo que pida tu jefe.*

```ascii
   FLUJO DE TRABAJO CON LA IA

  fuentes            TRABAJO (muchas idas       entrega (1 vez,
  (lo que llega)     y vueltas con la IA)       al final)
+--------------+     +-----------------+      +---------------+
| .docx  pdf   | --> |    ARCHIVOS     | -->  | .docx  .xlsx  |
| mails  webs  |     |      .MD        |      | PDF    slides |
+--------------+     | la IA lee/edita |      +---------------+
                     | /crea MEJOR aca |
  "convertime        +-----------------+        "generame el
   esto a .md"        iterás acá, barato          entregable"
```
<!-- ascii-note:
intent: mostrar el flujo de trabajo recomendado con la IA: las fuentes (docx, pdf, mails, webs) se convierten a archivos .md, TODO el trabajo iterativo con la IA pasa sobre los .md (donde interpreta/edita/crea mejor), y el formato final (.docx/.xlsx/PDF/slides) se genera una sola vez al final.
emphasize: la caja central "ARCHIVOS .MD" como el lugar donde vive el trabajo (la IA trabaja MEJOR acá); que la entrega es un paso único al final, no el medio de trabajo.
labels: izquierda = fuentes (lo que llega); centro = archivos .md (trabajo iterativo); derecha = entrega final (.docx/.xlsx/PDF/slides); leyendas "convertime esto a .md" y "generame el entregable".
-->

### Sources

- corpus/agentic-ai-deck.zip.md — "Markdown is the lingua franca" (la configuración y el material del mundo LLM es texto plano; el modelo lee texto).
- "corpus/mision - auto.zip.md" — el flujo de Atlas trabaja sobre archivos `.md` en el Project (reporte `.md` consolidado) y el entregable final se genera al último (borrador de mail, tablero).

### Speaker notes

El hábito concreto que se llevan. La analogía: el `.md` es tu mesa de trabajo y el `.docx`/PDF es la vitrina. Nadie construye dentro de la vitrina. El porqué: en texto plano la IA ve la estructura directa, y por eso interpreta, edita y crea mejor ahí; en .docx/.xlsx atraviesa capas que agregan ruido y errores. Recorrer el flujo con el diagrama. Llega material en cualquier formato y el primer pedido es "convertime esto a `.md`". Las idas y vueltas (resumir, corregir, reescribir, fusionar) pasan sobre los `.md`, más precisas y baratas de iterar. Cuando está listo, un único pedido: "generame el `.docx`/Excel/PDF", una sola vez al final. El "vale doble": lo que debe recordar vive como texto plano (Instrucciones, memoria del Project); los archivos que lee y edita van en `.md` en la carpeta. Atlas: su reporte se consolida como `.md` y las salidas lindas (mail, tablero) salen al último. Tiempo objetivo: ~6 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: COMPACTAR 6.2. Título sin cambios (32c, bajo el techo). De 5 bullets a 2. Salieron los bullets 1, 2 y 4, que eran las tres cajas del diagrama transcriptas: "Llevá tu información de trabajo a `.md`; el formato final, al último" (cajas izquierda y derecha, y la leyenda "convertime esto a .md"), "La IA interpreta, edita y crea mejor sobre `.md` que sobre .docx/.xlsx" (la caja central, nombrada en `emphasize`: "la IA trabaja MEJOR acá") y "El entregable (.docx, .xlsx, PDF, slides) se genera una vez, al final" (la caja derecha, también en `emphasize`: "la entrega es un paso único al final"). Las tres ya vivían en Speaker notes: fue merge, no traspaso ni borrado. Quedan 2 bullets: el "vale doble" (memoria + archivos de trabajo), que el diagrama NO dibuja, y la regla de bolsillo. La regla se conserva verbatim: el round 7 evaluó cortarla como epigrama balanceado y la mantuvo a propósito, porque es la regla didáctica que promovió el presentador y las dos cláusulas cargan contenido concreto. Notes de 199 a 155 palabras. NO llegan a ~120 sin perder sustancia, y lo reporto como piso: son cinco beats con contenido propio (la analogía mesa/vitrina, el porqué del texto plano, el recorrido de las tres cajas del diagrama, el "vale doble" y el aterrizaje en Atlas), y las tres cajas que bajaron de Content son parte de por qué el guion no se achica más. El recorte de 44 salió de andamiaje de guion, no de contenido. El piso honesto es ~150. ASCII y ascii-note sin tocar.

---

## 3. Schedule sobre tus carpetas

### Content

- Ya lo conocés (sección 3): una vez + cadencia → corre sola. En Cowork, además, **sobre tus carpetas y archivos**, con tus Instrucciones, connectors y skills.
- Cadencias: por hora / diaria / semanal / **"Run now"**. Vive en la pestaña **Scheduled**.

![Pestaña Scheduled en Cowork](images/schedule.png)

- Atlas, lunes 8:00: `buscar-accion` → `reporte-semanal` → borrador en Gmail antes de la reunión de las 9:00.

### Sources

- Anthropic Support — Schedule recurring tasks in Claude Cowork: https://support.claude.com/en/articles/13854387-schedule-recurring-tasks-in-claude-cowork — versión ACTUALIZADA (verificada 2026-07-09): "Scheduled tasks run remotely, so they run on their cadence even when your computer is asleep or the Claude Desktop app is closed"; planes pagos; beta con rollout Max-first. Excepción clave para Cowork: "If a scheduled task requires local files or apps, it will only run locally".
- Anthropic Support — Release notes (7 de julio de 2026): https://support.claude.com/en/articles/12138966 — Cowork en web/mobile, sesiones remotas (beta), "scheduled tasks run with no device online", rollout empezando por Max (verificado 2026-07-09).
- TechCrunch (2026-07-07): https://techcrunch.com/2026/07/07/the-coding-agent-wars-are-spilling-into-the-rest-of-the-office-claude-cowork/ — cobertura de prensa de la expansión y las corridas en background (encuadre de terceros).
- corpus/agentic-ai-deck.zip.md — slide 6.1 (Scheduled tasks, Cowork proactivo). *(La caveat "app abierta" de 6.3 quedó desactualizada por el update del 7 de julio de 2026.)*
- "corpus/mision - auto.zip.md" — el flujo programado de Atlas (Step 3.3); "Run on demand" como tip de demo. *(Su caveat local también quedó desactualizada.)*

### Speaker notes

Slide corta a propósito: dónde-corre ya se enseñó en la sección 3; acá, la forma Cowork. Abrir con el puente: "es la tarea programada que viste en el chat, pero ahora el que corre es el agente, sobre tus carpetas, con tus Instrucciones y skills". Cada corrida abre su sesión fresca y avisa al terminar. El marco de la slide 3.2 en una línea: desde el update del 7 de julio de 2026 hay ejecución remota en la nube (beta, planes pagos, rollout que empieza por Max); mientras no te llegue, corre local, computadora prendida + app abierta. El matiz Cowork: como estas tareas trabajan sobre archivos de tu disco, caen en la excepción documentada "requiere archivos/apps locales, corre local". Planificá con la compu prendida aunque tengas la beta de nube. Para la demo, "Run on demand". Tiempo objetivo: ~5 min.

### Presenter feedback
- [closed] 2026-06-09 — "Buscar informacion sobre "corrida en la nueve" y links a esto. No lo he visto."
  Resolution: Corregido: el Schedule de Cowork corre LOCAL (en tu computadora), no en la nube de Anthropic; solo se dispara con la maquina despierta + app abierta; si esta dormida/cerrada se saltea y corre al volver (con aviso). Aparte de una linea: existen agentes programados hosteados en la nube pero son otra cosa, fuera de alcance. Sumada la fuente de soporte (schedule-recurring-tasks). Cableada images/schedule.png. Notes actualizadas.

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: COMPACTAR 6.3. Título "Schedule en Cowork: lo mismo que viste en el chat, ahora con carpetas y archivos" (80c, el segundo peor del deck) → "Schedule sobre tus carpetas" (27c): el título contaba en prosa el puente que el bullet 1 ya hace, y "sobre tus carpetas" es el único delta contra la sección 3. La lámina re-enseñaba la 3.2 y sus propias notes lo admitían en la primera línea ("el concepto y los cuidados de dónde-corre ya se enseñaron en la sección 3"). Salieron de Content los bullets 3 y 4: "¿Dónde corre? Igual que en el chat (slide 3.2): nube en beta (Max primero); si no te llegó → local: compu prendida + app abierta" y "Las tareas de Cowork usan tus archivos locales → corren local. Planificá con la compu prendida". Los dos estaban ya en Speaker notes, con las mismas fechas y hedges: fue merge, no borrado. Quedan 3 bullets + la captura: el puente, cadencias/pestaña Scheduled y el ejemplo de Atlas del lunes 8:00. L002 intacto: la fecha del 7 de julio de 2026, el hedge beta + planes pagos + rollout Max-first y la quote verificada de la excepción ("requiere archivos/apps locales, corre local", artículo 13854387, verificado 2026-07-09) siguen en Speaker notes y en Sources sin aplanar. La única línea que salió de las notes es "si estaba apagada, la corrida se saltea y se recupera al volver": la 3.2 la enseña entera y es la que carga su atribución completa (versión anterior del artículo 13854387, "el artículo actual ya no lo detalla"), así que acá era repetición sin su hedge. Notes de 180 a 141 palabras. NO llegan a ~120 y lo reporto como piso: quedan sobre la guía a propósito (L002 > la guía de palabras), porque los hedges dateados (7 de julio de 2026, beta + planes pagos + rollout Max-first, la quote de la excepción local) no se pueden aplanar. El piso honesto es ~140. Mismo criterio que la 3.2, que quedó en 171 por la misma razón. El cross-ref a la slide 3.2 sigue resolviendo: la sección 3 no se renumeró y su slide 2 sigue siendo "¿Dónde corre tu tarea? Local vs nube". El [closed] del 2026-06-09 queda intacto.

---

## 4. Artifacts y Live Artifacts

### Content

- **Artifact** = salida viva en un panel lateral: HTML, gráficos, tablas, documentos.
- **Estándar** (todos los planes): estático. **Live** (Cowork, pago): página interactiva y persistente que **se refresca con datos actuales** y guarda **versiones** (pestaña "Live artifacts").
- Se crea desde una tarea, o desde la pestaña (**New artifact**).
- Estado hoy: **NO compartibles aún** (roadmap) · **locales** (no te siguen entre dispositivos) · usan tus connectors **sin re-preguntar**.

### Sources

- corpus/agentic-ai-deck.zip.md — definición de Artifact (dos tiers); slide 5.13 (Standard vs Advanced; Live Artifacts en Cowork); matriz 5.16 (Cowork ✓ full Artifacts + Live Artifacts).
- Anthropic Support — Use Live Artifacts in Claude Cowork: https://support.claude.com/en/articles/14729249-use-live-artifacts-in-claude-cowork — realidad oficial: persisten en la pestaña Live artifacts, se refrescan con datos actuales, guardan versiones; limitaciones: locales (no en la nube), NO compartibles aún (en roadmap), usan los connectors aprobados sin volver a preguntar; dos formas de crearlos (desde una tarea o desde la pestaña) (verificado 2026-07-09).

### Speaker notes

El jefe quería el reporte de dos formas: el email, que ya resolvimos con Gmail + Schedule, y una página siempre actualizada. El Live Artifact es esa página. La distinción: el estándar es un solo archivo estático, lo que generás es lo que queda; el Live persiste en la pestaña Live artifacts, se refresca con datos actuales de tus apps conectadas al abrirlo y guarda historial de versiones. Ser honesto con el estado, porque acá corregimos una confusión: hoy los Live Artifacts NO son compartibles (es del roadmap), son locales (no te siguen entre dispositivos) y usan los connectors que aprobaste sin volver a preguntar. Nota: versiones previas de este material mencionaban un "ShareDuo" con URL pública; eso NO es una capacidad de Cowork y se quitó. El tablero de Atlas viene en la lámina siguiente. Tiempo objetivo: ~6 min.

### Presenter feedback

- [closed] 2026-06-09 — "Busca informacion sobre ShareDuo en oficial de CoWork, me parece que esto no esta en co-work. Me parece que esto es incorrecto."
  Resolution: MAJOR FIX: removidas TODAS las referencias a ShareDuo y el mecanismo inventado share='duo' (no es capacidad de Cowork). Reescrita la realidad oficial de Live Artifacts: pagina HTML interactiva persistente en la pestania Live artifacts, se refresca con datos actuales, guarda versiones; limitaciones: local (no nube, no sigue entre dispositivos), NO compartible aun (roadmap), usa connectors aprobados sin re-preguntar; dos formas de crear. Tambien limpiada la referencia a ShareDuo en el ASCII del loop de Conclusions. Reemplazada la fuente por la URL oficial de live-artifacts; notes actualizadas.

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: PARTIR (mitad A). La ex 6.4 "Artifacts y Live Artifacts: del resultado a algo compartible" (60c) cargaba dos ideas y 192 palabras de notes en tres párrafos separados: la distinción estático/Live con su estado honesto, y el tablero de Atlas. Esta mitad se queda con el concepto. Título "Artifacts y Live Artifacts" (26c): se fue el arco "del resultado a algo compartible", que además prometía lo contrario de lo que la lámina dice, porque hoy NO son compartibles. Content en 4 bullets, sin imagen: qué es un Artifact, la distinción estándar/Live, las dos formas de crearlo y el estado de hoy. El [closed] del 2026-06-09 sobre ShareDuo se queda acá, con su contenido: es el fix de exactitud del round 3, donde una capacidad reclamada resultó no existir y el mecanismo inventado share='duo' se removió de todo el deck. Los tres claims del estado honesto quedan intactos con su fuente oficial (support 14729249: locales, NO compartibles aún, connectors aprobados sin re-preguntar) y la nota de ShareDuo sigue en Speaker notes, dicha en voz alta. Ningún hedge aplanado. Sources repartidas: acá la definición de dos tiers del corpus y el artículo oficial de Live Artifacts. Notes en 140 palabras: NO llegan a ~120 y lo reporto como piso, porque los tres claims del estado con su fuente y la nota de ShareDuo son sustancia protegida (L002) y ocupan la mitad del guion. El piso honesto es ~140. Las dos mitades suman los ~10 min de la lámina original (~6 + ~4).

---

## 5. El tablero de Atlas

### Content

- Atlas: un Live Artifact nuevo por semana, `pulso-semanal-FECHA`. Queda el historial.
- El boceto del jefe es el spec:

![Boceto del tablero "Pulso semanal de mercado" (wireframe del jefe)](images/mockup-tablero.png)

### Sources

- "corpus/mision - auto.zip.md" — Skill `publicar-tablero` (un artifact por semana, `pulso-semanal-FECHA`); estructura del mockup del tablero (boceto del jefe).

### Speaker notes

Desarrollar el ejemplo: un Live Artifact nuevo por semana, con el ID `pulso-semanal-FECHA`, así queda historial de tableros. Adentro, tarjetas por empresa, tabla resumen y un chip "LIVE", refrescado con los datos de la semana. Mostrar el boceto del jefe, el "napkin sketch", como el spec de diseño que el artifact reproduce: lo dibujó a mano y el agente lo construye. El cierre de la sección: el jefe pidió mail y tablero, y las dos entregas ya están. Tiempo objetivo: ~4 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: PARTIR (mitad B). Segunda mitad de la ex 6.4 (60c): el tablero de Atlas. Título "El tablero de Atlas" (19c). El image ref `mockup-tablero.png` se muda entero acá, que es su lámina: el boceto del jefe es el spec de ESTE tablero, no una ilustración del concepto de Artifact. Content en 2 bullets + 1 imagen: el artifact semanal con su ID, y el boceto como spec. Sources repartidas: acá el registro de la misión (Skill `publicar-tablero` + estructura del mockup). Notes en 82 palabras, del párrafo del ejemplo Atlas y de la línea del napkin sketch de la lámina original. El [closed] del ShareDuo se quedó con la mitad A, que es donde vive el claim que corrigió.

---

# 7. Piezas avanzadas

**Goal of this section:** Cierre de nivel avanzado, con las tres piezas: **Skills** (enseñarle a Claude tareas reutilizables, cómo se crean, su trampa del Save y la anatomía del SKILL.md), **Subagentes** (delegar trabajo pesado en paralelo) y **Plugins** (distribuir workflows completos, incluido el ciclo de vida en cuentas Team).

**Presenter feedback:**

---

## 1. Skills: enseñar una vez

### Content

- **Skill** = instrucción reutilizable que se carga cuando tu pedido coincide con su descripción. **Un trabajo por Skill.**
- *"Todo lo que le explicás a Claude dos veces es una Skill que deberías escribir una vez."*
- Atlas: `reporte-semanal` consolida la carpeta `fuentes/` en un reporte con formato fijo.

### Sources

- corpus/agentic-ai-deck.zip.md — definición de Skill (folder + SKILL.md, "one job per skill"); "Anything you explain to Claude twice is a skill you should write once."
- "corpus/mision - auto.zip.md" — el ejemplo `reporte-semanal` (lee la carpeta `fuentes/`, consolida por empresa, formato fijo, sufijo `-new`).

### Speaker notes

Arranca el bloque avanzado. La Skill materializa el "enseñá una vez, reutilizá siempre": una instrucción escrita una sola vez, que Claude carga cuando tu pedido coincide con su descripción. Usar `reporte-semanal` para que sea concreto: lee TODOS los archivos crudos de `fuentes/` (uno por portal), consolida por empresa, la más relevante primera (⭐), y guarda con sufijo `-new` para no pisar el ejemplo. Convierte varios archivos desordenados en un reporte prolijo. El criterio "un trabajo por Skill": si escribís "y además", dividila en dos. La frase de la lámina es el filtro que se llevan: lo que explicás dos veces, escribilo una. Cómo se crea viene en la próxima. Tiempo objetivo: ~4 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: PARTIR (mitad A). La ex 7.1 "Skills: enseñarle a Claude algo una sola vez" (44c) tenía 6 bullets (techo: 5), ningún visual y 208 palabras de notes, y cargaba dos ideas: qué es una Skill y cómo se crea una en Cowork. Esta mitad se queda con el concepto. Título "Skills: enseñar una vez" (23c). Content en 3 bullets: la definición con "un trabajo por Skill", la frase ancla del presentador ("Todo lo que le explicás a Claude dos veces es una Skill que deberías escribir una vez") y el ejemplo `reporte-semanal` de Atlas. Sources repartidas: acá el corpus del deck (definición + la frase) y el registro de la misión (`reporte-semanal`). Notes en 113 palabras. Los dos [closed] del 2026-06-09 se van enteros a la mitad B: los dos son sobre los caminos de creación y su verificación contra la documentación oficial, que es el contenido de esa lámina. Las dos mitades suman los ~8 min de la original (~4 + ~4).

---

## 2. Cómo se crea una Skill

### Content

- Requisito: **Code execution** habilitado (Settings → Capabilities).

```ascii
     CREAR UNA SKILL EN COWORK (GUI, sin slash commands)

 CAMINO 1                       CAMINO 2
 +---------------------+        +---------------------+
 | pedila en lenguaje  |        | subi un ZIP         |
 | natural: Claude     |        | Customize > Skills  |
 | escribe el SKILL.md |        | > "+"               |
 +---------------------+        +---------------------+
            \                          /
             v                        v
        +==================================+
        |   SAVE / ENABLE                  |  <== la trampa
        |   (Customize > Skills)           |
        +==================================+
                        |
                        v
               +-----------------+
               |  SKILL ACTIVA   |
               +-----------------+

   frenar en la compuerta = la Skill "no funciona"
```
<!-- ascii-note:
intent: mostrar los dos caminos reales para crear una Skill en Cowork (pedirla en lenguaje natural, con Claude escribiendo el SKILL.md; o subir un ZIP) y que los dos convergen en la misma compuerta, Save / enable en Customize → Skills. Solo pasada esa compuerta la Skill queda activa.
emphasize: la compuerta "SAVE / ENABLE" como cuello de botella del dibujo (caja de doble línea, marcada "la trampa") y la leyenda de abajo "frenar en la compuerta = la Skill no funciona"; que los dos caminos convergen en ella y ninguno la esquiva; que Cowork es GUI y no hay un tercer camino por slash command.
labels: camino 1 = pedila en lenguaje natural (Claude escribe el SKILL.md); camino 2 = subí un ZIP (Customize → Skills → "+"); compuerta = Save / enable (Customize → Skills); salida = Skill activa.
-->

### Sources

- Anthropic Support — Use Skills in Claude: https://support.claude.com/en/articles/12512180-use-skills-in-claude — habilitar Skills en Customize → Skills; requiere Code execution.
- Anthropic Support — How to create custom skills: https://support.claude.com/en/articles/12512198-how-to-create-custom-skills — los dos caminos en Cowork (pedírsela en lenguaje natural y habilitarla; o subir un ZIP).

### Speaker notes

Los dos caminos reales en Cowork, que es GUI y no tiene slash commands. Uno: pedírsela en lenguaje natural; Claude escribe el `SKILL.md` y vos la habilitás en Customize → Skills. Dos: subir un ZIP de la carpeta de la Skill; el camino completo es Customize → Skills → "+" → Create skill → Upload a skill, activando con el toggle. No saltear la trampa del Save, un error real y común: pedís la Skill, Claude escribe el archivo, y si no le das Save / enable no queda habilitada y parece que "no funciona". Los dos caminos terminan en la misma compuerta, y ahí es donde la gente se frena. Las Skills requieren Code execution (Settings → Capabilities). El `SKILL.md` es el archivo `.md` con metadata que ya vieron; la próxima lámina lo abre. Tiempo objetivo: ~4 min.

### Presenter feedback
- [closed] 2026-06-09 — "Revisar (2) pidiéndole la creación durante el prompt, en lenguaje natural. No estoy seguro que co-work funcione."
  Resolution: Confirmado el camino (2): en Cowork pedir la Skill en lenguaje natural SI funciona — Claude escribe el SKILL.md, pero NO queda habilitada hasta darle Save/enable en Customize > Skills (la trampa del Save, que se conserva). Removido '/create-skill' / '/skill-creator' como metodo de Cowork (son slash commands de Claude Code, no existen en la GUI de Cowork). Reescrito el bloque 'Como se crea una Skill en Cowork' con los dos caminos reales + requisito Code execution; notes actualizadas.
- [closed] 2026-06-09 — "Busca mas info sobre cowork y skill creation en la documentacion para estar seguros que esto sea correcto."
  Resolution: Verificado contra documentacion oficial de Anthropic (support.claude.com): en Cowork (GUI, sin slash commands) los dos caminos reales son pedir la Skill en lenguaje natural (Claude escribe el SKILL.md y vos la habilitas en Customize > Skills) o subir un ZIP (Customize > Skills > + > Create skill > Upload). Requiere Code execution (Settings > Capabilities). Sumadas dos fuentes de soporte (use-skills + create-custom-skills).
- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: PARTIR (mitad B). Segunda mitad de la ex 7.1 (44c): cómo se crea una Skill en Cowork. Título "Cómo se crea una Skill" (22c). Los dos [closed] del 2026-06-09 se mudan enteros acá con su contenido: los dos son sobre esta lámina (los dos caminos reales de creación y su verificación contra la documentación oficial de Anthropic), y su presencia es lo que marca este beat como lámina propia. Diagrama ASCII NUEVO (el único que autoriza este dispatch): los dos caminos convergen en la compuerta Save / enable, y solo pasada la compuerta la Skill queda activa; la trampa del Save queda dibujada como el cuello de botella, que es lo que hace que la gente crea que "no funciona". L002 respetado en el diagrama: Cowork es GUI, no hay slash commands, así que se dibujan DOS caminos y no un tercero. Content en 1 bullet + el diagrama: el requisito de Code execution es lo único que el ASCII no dice. Los dos caminos y la trampa están en el bloque y nombrados en el `emphasize` de su ascii-note, así que bajan a Speaker notes, donde ya vivían: fue merge, no traspaso. Sources repartidas: acá los dos artículos de soporte (use-skills, create-custom-skills), que son los que respaldan los caminos y el requisito. Notes en 139 palabras: NO llegan a ~120 y lo reporto como piso. Esta lámina es la que carga el guion entero de creación, y lo que la infla es sustancia verificada de los dos [closed] del 2026-06-09 (L002): el camino ZIP completo paso por paso (Customize → Skills → "+" → Create skill → Upload a skill, activando con el toggle), la trampa del Save con su síntoma ("parece que no funciona"), el requisito de Code execution con su ruta (Settings → Capabilities) y la aclaración de que Cowork es GUI sin slash commands, que es la corrección exacta que pidió el primero de los dos. El piso honesto es ~135. Mismo criterio que la 3.2 (171w) y la 6.3 (141w).

---

## 3. Anatomía de un SKILL.md

### Content

- Un `SKILL.md` por dentro: es el `.md` con metadata de la sección 6, abierto.

```ascii
+--------------------------------------------------------------+
| ---                                                          |  <-- METADATA / HEADER (YAML)
| name: reporte-semanal                                        |      "que es" + "cuando se activa"
| description: Genera el pulso semanal de mercado a partir     |
|   de la carpeta fuentes/ de la semana. Usar cuando pidan     |
|   "reporte semanal" o "pulso de la semana".                  |
| ---                                                          |
+--------------------------------------------------------------+
| # Reporte semanal                                            |  <-- CUERPO (Markdown)
|                                                              |      "que hace": las instrucciones
| 1. Leé TODOS los archivos de fuentes/ y consolidá           |
|    por empresa.                                              |
| 2. Generá el reporte con esta estructura exacta...          |
| 3. Guardá con sufijo -new (no pises el original).           |
+--------------------------------------------------------------+
```
<!-- ascii-note:
intent: mostrar la anatomía de un SKILL.md — un bloque de metadata (YAML frontmatter: name + description) arriba y el cuerpo de instrucciones en Markdown abajo. Refuerza el beat de archivos .md/metadata de la sección Cowork.
emphasize: la separación visual en dos zonas — METADATA/HEADER (name, description; "qué es / cuándo se activa") vs CUERPO (las instrucciones; "qué hace"); que la `description` es lo que dispara la Skill.
labels: zona superior = metadata/header (YAML, name + description); zona inferior = cuerpo (instrucciones en Markdown); etiquetas laterales "cuándo se activa" y "qué hace".
-->

- La `description` activa la Skill por **sentido**, no por palabra clave.

### Sources

- corpus/agentic-ai-deck.zip.md — definición de Skill (SKILL.md con YAML frontmatter: name + description; "Description drives triggering — semantic, not keyword").
- "corpus/mision - auto.zip.md" — la Skill `reporte-semanal` (entrada `fuentes/`, consolida por empresa, estructura fija, sufijo `-new`).

### Speaker notes

Slide-ejemplo que aterriza dos cosas a la vez: la anatomía de una Skill y el beat de archivos `.md` + metadata de la sección 6. Mostrar el `SKILL.md` partido en dos zonas: arriba el header YAML entre `---`, con `name`, que identifica, y `description`, que decide cuándo se activa; abajo el cuerpo, Markdown común, los pasos que sigue el agente. El punto a fijar: el sistema lee la `description` para decidir si esta Skill aplica a tu pedido, por sentido y no por palabra clave. Usar `reporte-semanal` para que sea concreto. Mantenerlo alto nivel: es para que vean cómo se ve, no un tutorial de formato. Tiempo objetivo: ~3-4 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: COMPACTAR 7.3 (ex 7.2). Título "Anatomía de un SKILL.md" (23c) intacto; la lámina estaba sobre el techo de densidad por bloques (1 bullet + diagrama + 2 bullets). Salieron los 2 bullets de cierre ("**Metadata:** `name` identifica; `description` decide cuándo se activa" y "**Cuerpo:** Markdown común, los pasos que sigue el agente"): son la leyenda que el diagrama ya carga rotulada en sus dos zonas, y su ascii-note las nombra enteras en `emphasize` ("la separación visual en dos zonas — METADATA/HEADER vs CUERPO"). Ya vivían en notes ("arriba el header YAML, abajo las instrucciones en Markdown"), así que fue merge; se les sumó `name` identifica y "los pasos que sigue el agente" para no perder ni un matiz. Se conserva en lámina lo único que el ASCII NO dice: que la `description` activa por sentido y no por palabra clave (el `emphasize` dice que la `description` dispara la Skill, no que lo hace de forma semántica). Quedan 2 bloques: 1 bullet + diagrama + 1 bullet de remate. Cross-ref stale corregido: "Es el `.md` con metadata de la sección 4" → sección 6, que es donde vive hoy el beat de archivos `.md` (6.1 y 6.2); misma corrección en la primera línea de Speaker notes. Notes de 91 a 110 palabras: crecieron a propósito, es el destino de la leyenda que bajó, y siguen bajo las ~120. ASCII y ascii-note sin tocar.

---

## 4. Subagentes: delegar en paralelo

### Content

- **Subagente** = asistente aislado, contexto propio; devuelve **un resumen** (no la transcripción).
- Regla de una línea: chico y visible → **Skill**. Grande o ruidoso → **Subagente**.
- En Cowork corren "por debajo", **varios en paralelo**.
- Se agrega como una Skill (descripción + instrucciones): pedíselo a Claude, o viene en un **Plugin**.

```ascii
                +------------------+
                | agente principal |
                +------------------+
                  /      |       \
                 v       v        v
          +--------+ +--------+ +--------+
          | sub A  | | sub B  | | sub C  |
          |contexto| |contexto| |contexto|
          |propio  | |propio  | |propio  |
          +--------+ +--------+ +--------+
                 \       |       /
                  v      v      v
                +------------------+
                | resumen combinado|
                +------------------+
```
<!-- ascii-note:
intent: mostrar el patron fan-out/fan-in: el agente principal reparte una tarea entre varios subagentes que corren en paralelo con contexto propio, y junta los resultados en un resumen combinado.
emphasize: el paralelismo (tres subagentes a la vez) y que cada uno tiene contexto aislado; el resumen combinado al final.
labels: agente principal -> sub A / sub B / sub C (contexto propio) -> resumen combinado.
-->

### Sources

- corpus/agentic-ai-deck.zip.md — definición de Subagent (aislado, devuelve un resumen); "Skill vs Subagent" (slide 4.9 tabla); matriz 4.10 (Cowork ⚠️, under the hood); demo 4.8 (8 propuestas en paralelo).
- Claude Docs — Subagents: https://code.claude.com/docs/en/sub-agents — concepto general de subagente (un spec: cuándo usarlo + instrucciones).

### Speaker notes

Nivel avanzado, presentarlo como "para cuando crezcas". La distinción mental útil: si la sub-tarea es chica y querés verla, es una Skill; si es grande o ruidosa y querés que corra aparte sin ensuciar tu conversación, es un Subagente. El ejemplo del deck ilustra el fan-out: 8 propuestas de proveedores revisadas en paralelo por tres especialistas, con tabla combinada al final. Cómo se agrega, en paralelo a las Skills: un subagente se define con una descripción (cuándo usarlo) más instrucciones; le pedís a Claude que lo arme (se gestiona en Customize, igual que una Skill) o viene dentro de un Plugin. Mantenerlo alto nivel, sin rutas de archivos ni internals de persistencia. Tiempo objetivo: ~7 min.

### Presenter feedback
- [closed] 2026-06-09 — "Agregar como se agrega un agente."
  Resolution: Agregado beat 'Como se agrega un subagente' en Content (alto nivel): se define como una Skill (descripcion de cuando usarlo + instrucciones); le pedis a Claude que lo arme (se gestiona en Customize) o viene dentro de un Plugin; sin rutas de archivo ni internals. Reescrito el bullet 'En Cowork' (quitada la referencia a config /agents de Claude Code). Sumada fuente de docs de Subagents.
- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: COMPACTAR 7.4 (ex 7.3), SOLO EL TÍTULO: "Subagentes: delegar sub-tareas en paralelo" (42c) → "Subagentes: delegar en paralelo" (31c), 2 caracteres sobre el techo de 40 y ese era el defecto entero. Cae "sub-tareas", que el bullet 1 y el diagrama ya cargan. El cuerpo conforma y NO se tocó: 4 bullets + 1 diagrama, dentro del techo de densidad, y ninguno de los 4 transcribe el ASCII (el diagrama dibuja el fan-out/fan-in; los bullets dan la definición, la regla Skill-vs-Subagente, el paralelismo en Cowork y cómo se agrega). Sources, Speaker notes, ASCII y ascii-note sin tocar. El [closed] del 2026-06-09 ("Agregar como se agrega un agente") queda intacto y su beat sigue en lámina, que es donde lo puso.

---

## 5. Plugins: empaquetar y distribuir

### Content

- **Plugin** = la unidad de distribución: empaqueta Skills + agentes + connectors en una instalación. *"Ship the whole thing."*
- En Cowork se instalan desde un **marketplace** en la GUI; lo que traen funciona en Chat y en Cowork.
- Dónde: marketplaces oficiales de Anthropic y de la comunidad.

### Sources

- corpus/agentic-ai-deck.zip.md — definición de Plugin ("Ship the whole thing"; "the way to get a skill into Cowork"); slide 4.5 (caveat de project-skills en Cowork); matriz 5.11 (Cowork ✓ GUI marketplace); slide 5.10 (marketplaces).

### Speaker notes

Cerrar el avanzado con la idea de empaquetado: cuando un workflow madura (varias skills, connectors, agentes, incluso hooks y MCP), un Plugin lo vuelve instalable de una. El punto para Cowork: la forma robusta de distribuir una skill o un agente a otros es dentro de un plugin. Para usar una Skill en Cowork la habilitás como skill de usuario (Customize → Skills) o la recibís dentro de un plugin, y los plugins distribuidos aparecen en Chat y en Cowork. Mencionar los marketplaces oficiales (`anthropics/claude-plugins-official`, `anthropics/knowledge-work-plugins`) y los de la comunidad. Recordar el mapa: Plugins es la banda que envuelve todos los bloques de la charla. Tiempo objetivo: ~6 min.

### Presenter feedback

- [closed] 2026-06-09 — "Agregar un Slide the life-cycle de pluggin en la cuenta Team y que se peude hacer. Buscar en la documencaion de Claude."
  Resolution: Insertada nueva slide 6.3 'Plugins en una cuenta Team: ciclo de vida': Owner crea marketplace privado (subir ZIP o sync repo GitHub que auto-actualiza) -> fija preferencia de instalacion por plugin (opcional/auto-install/provisionar) -> distribucion a miembros (aparece en chat y en Cowork) -> miembros instalan/habilitan desde el directorio, updates sincronizan. ASCII render-driving del ciclo + ascii-note. 3 fuentes de soporte/blog de Anthropic.
- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: COMPACTAR 7.5 (ex 7.4), SOLO EL TÍTULO: "Plugins: empaquetar y distribuir un workflow completo" (53c, el peor de la sección) → "Plugins: empaquetar y distribuir" (32c). Cae "un workflow completo", que el bullet 1 ya dice mejor y con la cita del corpus ("Ship the whole thing"). El cuerpo es de 3 bullets, el más liviano de la sección, sin visual y bien bajo el techo: NO se tocó. Sources y Speaker notes sin tocar. El [closed] del 2026-06-09, que originó la lámina del ciclo de vida en Team, queda intacto y su slide sigue siendo la siguiente.

---

## 6. Plugins en una cuenta Team

### Content

- En Team/Enterprise, los **Owners** gestionan los plugins de la org (Organization settings → Plugins).
- El ciclo, punta a punta:

```ascii
+-----------------+     +------------------------+     +----------------------+
| OWNER crea un   | --> | agrega plugins:        | --> | fija preferencia de  |
| marketplace     |     | · subir ZIP            |     | instalacion por      |
| privado (org)   |     | · sync repo GitHub     |     | plugin (opcional /   |
|                 |     |   (auto-actualiza)     |     | auto-install / prov.)|
+-----------------+     +------------------------+     +----------------------+
                                                                  |
                                                                  v
+---------------------------+     +-----------------------------------------+
| MIEMBROS instalan/        | <-- | se DISTRIBUYE a los miembros            |
| habilitan desde el        |     | (aparece en chat Y en Cowork)          |
| directorio de la org      |     |                                         |
| (updates se sincronizan)  |     |                                         |
+---------------------------+     +-----------------------------------------+
```
<!-- ascii-note:
intent: mostrar el ciclo de vida de un plugin en una cuenta Team/Enterprise — del Owner que crea un marketplace privado a los miembros que lo instalan, con updates que se sincronizan.
emphasize: el rol del OWNER (marketplace privado: subir ZIP o sync GitHub) y la preferencia de instalación por plugin; que se distribuye a chat Y a Cowork; que los miembros instalan desde el directorio y las actualizaciones se sincronizan solas.
labels: flujo de 5 pasos — Owner crea marketplace privado -> agrega plugins (ZIP / sync GitHub) -> fija preferencia de instalación (opcional/auto-install/provisionar) -> distribución (chat + Cowork) -> miembros instalan/habilitan (updates sincronizan).
-->

### Sources

- Anthropic Support — Manage Claude Cowork plugins for your organization: https://support.claude.com/en/articles/13837433-manage-claude-cowork-plugins-for-your-organization — Owners gestionan plugins en Organization settings; marketplace privado (ZIP o sync GitHub); preferencia de instalación por plugin.
- Anthropic Support — Use plugins in Claude: https://support.claude.com/en/articles/13837440-use-plugins-in-claude — miembros instalan/habilitan desde el directorio; updates sincronizan; disponibles en chat y Cowork.
- Claude blog — Cowork plugins across the enterprise: https://claude.com/blog/cowork-plugins-across-enterprise — distribución de plugins a nivel organización (chat + Cowork).

### Speaker notes

Slide de cierre del bloque avanzado, orientada a quien algún día administre una cuenta de equipo. En una cuenta Team, un Owner puede armar un marketplace privado de la organización y repartir workflows a todo el equipo. Recorrer el ciclo con el diagrama: el Owner crea el marketplace y sube plugins (ZIP o, mejor, sincronizando un repo de GitHub que auto-actualiza), fija cómo se instala cada uno (opcional / auto-install / provisionado), el plugin se distribuye y aparece en chat y en Cowork, y los miembros lo habilitan desde su directorio con las actualizaciones sincronizadas. Mantenerlo alto nivel: es el "para cuando esto escala a un equipo". Tiempo objetivo: ~4 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: COMPACTAR 7.6 (ex 7.5). Título "Plugins en una cuenta Team: ciclo de vida" (41c) → "Plugins en una cuenta Team" (26c): cae "ciclo de vida", que es literalmente lo que el diagrama dibuja y lo que el bullet "El ciclo, punta a punta:" anuncia. Salieron los 3 bullets de cierre ("**Marketplace privado**: se carga por ZIP o sync de repo GitHub (auto-actualiza)", "Por plugin: preferencia de instalación (opcional / auto-install / provisionado)" y "Llega a chat y Cowork; los miembros habilitan y los updates se sincronizan solos"): son los pasos 2 a 5 del diagrama transcriptos, los cinco nombrados en el `emphasize` y en el `labels` de su ascii-note, y los tres ya estaban en Speaker notes con las mismas palabras — merge, no traspaso, no se agregó una sola línea a las notes. Quedan 2 bloques: los 2 bullets (los Owners como responsables, que el diagrama no dice, y la entrada al ciclo) + el diagrama. L002 intacto: las tres fuentes oficiales quedan sin tocar (support 13837433 manage-org-plugins, support 13837440 use-plugins, y el post del blog claude.com/blog/cowork-plugins-across-enterprise), y ningún claim sobre el ciclo de vida en Team/Enterprise perdió su respaldo ni su hedge; lo que salió de lámina sigue dicho en voz alta desde notes, contra las mismas fuentes. Notes en 111 palabras, sin cambios (ya contenían los tres bullets). ASCII y ascii-note sin tocar.

---

# Conclusions

## 1. El loop completo de Atlas

### Content

- Todas las piezas de hoy, enganchadas en un solo loop:

```ascii
Lunes 8:00
   |
   v
[Schedule] dispara
   |
   v
[Skill buscar-accion] --(Connector MT Newswires + web_fetch Yahoo)--> guarda fuentes/
   |
   v
[Skill reporte-semanal] consolida --> reporte .md en el Project
   |
   +--> [Connector Gmail] deja borrador para el equipo
   |
   v
[Skill publicar-tablero] --> Live Artifact pulso-semanal-FECHA (pestaña Live artifacts)
```
<!-- ascii-note:
intent: mostrar el loop completo de la mision Atlas, encadenando todas las piezas vistas en la charla, disparado por Schedule cada lunes.
emphasize: la secuencia de izquierda a/arriba-abajo Schedule -> Skills -> Connectors -> Live Artifact; que todo arranca de un solo disparador.
labels: pasos del loop (Schedule, buscar-accion, reporte-semanal, Gmail, publicar-tablero) y las piezas usadas en cada uno.
-->

- Lo que el loop no dibuja y lo sostiene: las **Instrucciones** (el contrato), el **Project** con su carpeta (el lugar fijo) y los archivos `.md` (el material). **Subagentes** y **Plugins**, para cuando esto crezca.

### Sources

- "corpus/mision - auto.zip.md" — "el loop completo (Cowork version)".

### Speaker notes

Cierre integrador: recorrer el diagrama para que vean cómo cada pieza engancha con la siguiente. Un solo disparador, el lunes a las 8:00, y el resto cae solo. Repasar en una línea lo que se ve: Schedule dispara, las Skills hacen el trabajo, los conectores traen y entregan, el Live Artifact publica. Y nombrar lo que no se ve y lo sostiene: las Instrucciones que escribieron una vez, el Project con su carpeta, y los `.md` donde vive todo. Tiempo objetivo: ~3 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: PARTIR (mitad A). La ex Conclusions.1 "El loop completo y la idea para llevarse" (40c) cargaba dos ideas, y la "y" del título era el aviso: el loop integrador y la idea para llevarse. Es la última lámina que la audiencia recuerda y el takeaway estaba enterrado debajo de un diagrama de 15 líneas, el recap del arco y una lista de 7 piezas. Esta mitad se queda con el loop. Título "El loop completo de Atlas" (25c). El ASCII del loop y su ascii-note se quedan acá enteros, sin editar: son el contenido de esta lámina. Content en 2 bullets + el diagrama. Quitada la línea "**Las piezas:** Conectores (las manos) · Schedule (corre solo) · ... · Live Artifacts (compartir)": la mitad de la lista es el ASCII transcripto (el diagrama dibuja Schedule, las Skills, los conectores y el Live Artifact, y su ascii-note los nombra en `emphasize`), y además la lista se escribió para el arco viejo y ya no era exacta. Reemplazada por el complemento honesto del diagrama, que es lo único que no dibuja: Instrucciones, el Project con su carpeta, los `.md`, más Subagentes y Plugins. Los roles de las piezas que sí se ven ("las manos", "corre solo") bajan a Speaker notes, que ahora los repasan uno por uno. Arreglado de paso un claim que la reestructura dejó falso: la lista vieja decía "Live Artifacts (compartir)", y la slide 6.4 enseña con fuente oficial (support 14729249, verificado 2026-07-09) que hoy NO son compartibles; la palabra salió y no se reemplazó por otra promesa (L002). El arco de hoy y la frase ancla se van enteros a la mitad B. Sources repartidas: acá el registro de la misión (el loop completo, versión Cowork). Notes en 83 palabras. Las dos mitades suman los ~5 min de la lámina original (~3 + ~2).

---

## 2. La idea para llevarse

### Content

- **El arco de hoy:** el chat que responde de memoria → conectores → tareas programadas → Cowork (qué cambia, tu espacio, trabajar y entregar) → piezas avanzadas.

- *"Todo lo que le explicás a Claude dos veces es una Skill que deberías escribir una vez."*

- ¿Qué tarea recurrente le delegarías a tu propio Atlas?

### Sources

- corpus/agentic-ai-deck.zip.md — "Anything you explain to Claude twice is a skill you should write once" (slide 7.3).
- "corpus/mision - auto.zip.md" — gancho de cierre.

### Speaker notes

Recordar el arco en una línea: el chat que ya usaban y respondía de memoria, los conectores, las tareas programadas, el salto a Cowork, las piezas avanzadas. Después la frase ancla y el gancho, dicho en voz alta: "Acaban de automatizar un reporte que les iba a comer la mañana de cada lunes. ¿Qué otra tarea recurrente podrían delegarle a su propio Atlas?". Dejar la pregunta en el aire. Queda una lámina más, la de gobernanza, y ahí sí Q&A. Tiempo objetivo: ~2 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: PARTIR (mitad B). Segunda mitad de la ex Conclusions.1 (40c): la idea para llevarse. Título "La idea para llevarse" (21c). Lámina deliberadamente casi vacía: tres líneas, el arco, la frase ancla y la pregunta. Es el remate, y no se rellenó para que parezca sustancial; una lámina con dos líneas y una pregunta es la forma correcta acá. Sin diagrama: el ASCII del loop se quedó entero con la mitad A, sin editar. El arco se reescribió para el deck que existe hoy: el viejo ("chat de memoria → conectores → tareas programadas → Cowork (`.md`) → Skills, Subagentes y Plugins") codificaba la estructura de 5 secciones y colapsaba en "Cowork (`.md`)" lo que hoy son tres secciones; el nuevo las nombra ("Cowork (qué cambia, tu espacio, trabajar y entregar)") y arranca en "el chat que responde de memoria", que es el título del beat de apertura. La frase ancla se conserva verbatim con su fuente. La pregunta de cierre se separó del bullet de la frase, donde venía pegada al final de una línea ya larga: es la última cosa que se dice y necesita su propio renglón. Sources repartidas: acá el corpus del deck (la frase) y el gancho de cierre de la misión. Notes en 84 palabras.

---

## 3. Gobernanza y advertencias

### Content

- **Sin audit trail**: con información de clientes, datos financieros, PII o material bajo NDA, nada de esto. Cowork no es la herramienta.
- **Toda salida es un borrador**: verificá cifras, citas y afirmaciones contra la fuente.
- **Reproducibilidad:** mantené juntos prompt + entradas + salidas, para que el trabajo sea auditable.
- **Capas de guardarraíles:** permisos de carpeta → reglas en Instrucciones → solo plugins verificados → revisión humana.

### Sources

- corpus/agentic-ai-deck.zip.md — slide 7.2 (Governance & verification, verbatim); "No audit trail in Cowork."

### Speaker notes

Slide de cierre responsable, breve y obligatoria. Para esta audiencia de gestión, decirlo sin vueltas: Cowork sirve para trabajo recurrente de oficina y NO para datos de clientes, información financiera ni nada regulado o bajo NDA, porque no tiene audit trail. Aplica igual a dónde lo pegás: elegir mal la superficie es el mismo error. Recordar que toda salida es un borrador que hay que verificar, lo mismo que enseñó la sección 1: el modelo puede alucinar, el conector cita fuentes, el humano verifica. Leer los guardarraíles de afuera hacia adentro: la carpeta concedida marca el límite, las Instrucciones marcan las reglas, los plugins verificados marcan de quién te fiás, y al final siempre hay un humano. Dejar esto antes de abrir Q&A. Tiempo objetivo: ~3 min.

### Presenter feedback

- [closed] 2026-07-15 — "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides." (origin: presenter-chat)
  Resolution: COMPACTAR Conclusions.3 (ex Conclusions.2). Título "Gobernanza y advertencias (antes de Q&A)" (40c) → "Gobernanza y advertencias" (25c): el paréntesis era un aparte de agenda para el presentador, no información para la audiencia, y las notes ya lo decían ("Dejar esto antes de abrir Q&A"), así que fue merge y no traspaso. Estaba en 6 bullets, sobre el techo de 5. Tres decían lo mismo desde tres ángulos: "**Cowork no tiene audit trail**: no sirve para datos regulados o sensibles", "**No metas datos confidenciales / PII / bajo NDA** en la superficie equivocada" y "*Dato regulado:* con información de clientes o datos financieros, nada de esto. Cowork no es la herramienta"; además el beat de seguridad de la 5.5 ("nunca datos sensibles, credenciales o NDA") ya cubre el mismo terreno. Los tres se FUNDIERON en un bullet más filoso que conserva las tres partes: la razón (sin audit trail, claim verbatim del corpus), la lista completa (clientes, financieros, PII, NDA) y el remate. Ninguno se borró. El reframe al mundo de la gestión del dispatch previo se conserva casi verbatim ("con información de clientes o datos financieros, nada de esto. Cowork no es la herramienta") y se le sumaron PII y NDA, que venían del bullet fundido: NO se revirtió al encuadre biomédico. Quedan 4 bullets, bajo el techo. El matiz "en la superficie equivocada" bajó a Speaker notes, que ahora lo dicen en voz alta. Notes de 80 a 127 palabras: crecieron a propósito y con autorización, porque absorbieron el aparte del Q&A, el matiz de la superficie y la lectura de los guardarraíles de afuera hacia adentro. DIAGRAMA DE GUARDARRAÍLES EVALUADO Y DESCARTADO (el Composer lo sugirió; el motivo está en el reporte del dispatch): con el merge la lámina ya bajó a 4 bullets, así que la premisa del flag (6 bullets, sobre el techo) desapareció; las cuatro capas no son concéntricas sino filtros independientes, y dibujarlas anidadas implicaría una contención que no existe, que es exactamente el defecto que el presentador cazó en la pirámide del round 3 ([closed] 2026-06-09 en 4.5); y es la lámina del cierre responsable, donde la gravedad vale más que la decoración. L002 intacto: la fuente del corpus (slide 7.2 Governance & verification, verbatim; "No audit trail in Cowork") sin tocar.

---

# Open questions

- ~~Fecha de la clase sin confirmar~~ — resuelto 2026-07-14: `date: Julio 2026`.
- Imágenes diferidas (Phase 2 del librarian no corrida): las imágenes citadas desde el corpus (`screenshot-cowork-tab.png` en slide 5.2, `mockup-tablero.png` en slide 6.5) provienen de registros con `<!-- pending: process_images -->`. Las imágenes existen en disco y se referencian; re-verificar depiction/relevance tras correr librarian Phase 2. *(Renumeradas desde 4.5 / 4.12 en round 8, al partirse la sección 4; desde 5.1 / 5.8 al partirse la sección 5; y `mockup-tablero.png` desde 6.4 al partirse esa lámina en 6.4 + 6.5.)*
- Slides 5.1 (Demo time) y 5.2 (La interfaz de Cowork) citan pending stub corpus/agentic-ai-deck.zip.md — re-verify after librarian Phase 2. *(Las dos mitades de la ex 5.1 / ex 4.5 citan el mismo registro.)*
- Slide 6.5 "El tablero de Atlas" (ex 6.4 mitad B / ex 5.8 / ex 4.12) cita pending stub "corpus/mision - auto.zip.md" (mockup-tablero) — re-verify after librarian Phase 2.
- Falta la carpeta `skills/` con los tres skills pre-armados (`reporte-semanal`, `buscar-accion`, `publicar-tablero`) en el export — confirmado por el librarian en Step 3. No se inventa su contenido. Si la clase incluye una demo en vivo de las skills ya armadas, confirmar con el presentador si las tiene aparte.
- Vigencia de features vs docs oficiales: fechas/versiones (Live Artifacts abril 2026, planes pagos, etc.) son point-in-time; re-verificar contra docs oficiales antes de presentar.
- ~~**Slide 5.1 (ex 4.5) — interacción pipeline del banner DEMO TIME**~~ — **RESUELTO en round 8 (2026-07-15), opción (a):** la slide se partió en 5.1 "Demo time" (banner ASCII solo, sin image ref) y 5.2 "La interfaz de Cowork" (`screenshot-cowork-tab.png`). Al no compartir lámina con una imagen, el banner vuelve a ser el único bloque ASCII de su slide y el pipeline de Polish lo trata como render-driving: el ilustrador lo renderiza en Step 6.
- ~~**Interacción pipeline del ASCII archivado en `# Cut material` (round 8)**~~ — **RESUELTO en round 8 (2026-07-15):** aplicado el fix recomendado; la fence del diagrama ANTES/AHORA archivado se re-etiquetó de ```ascii a ```text. Cero bytes del ASCII cambiaron; `polish-ascii scan` (que detecta por tag) ya no lo levanta como diagrama huérfano sin slide contenedora.
- **Cross-refs stale tras la renumeración de rounds 8** (sección 4 partida en 4/5/6; ex-sección 5 "Advanced" → 7). Estado tras el dispatch final (Conclusions + Agenda + Thesis), que barrió el deck entero por grep:
  - ~~`Agenda` → **Narrative arc**: el "(4)" enumera interfaz, Instrucciones, Projects, `.md`, Schedule y Live Artifacts, que hoy se reparten entre las secciones 4, 5 y 6~~ — **RESUELTO en round 8 (2026-07-15), dispatch final:** arco reescrito para las 7 secciones; el salto a Cowork se cuenta en tres tiempos, uno por sección (4 / 5 / 6). Los 7 bullets de la lista se verificaron contra los H1: presentes, contiguos y con texto idéntico.
  - ~~`Agenda` → **Sections**: falta la sección 6~~ — **RESUELTO en round 8 (2026-07-15):** agregada "- 6. Trabajar y entregar"; la lista ya no salta de 5 a 7.
  - ~~Conclusions.1 → recap de piezas y arco escritos para la estructura de 5 secciones~~ — **RESUELTO en round 8 (2026-07-15), dispatch final:** la lámina se partió; el recap de piezas (mitad A) se reemplazó por el complemento del diagrama y el arco (mitad B) se reescribió a las 7 secciones. De paso se corrigió un claim que la reestructura había dejado falso: "Live Artifacts (compartir)" contra la 6.4, que enseña con fuente oficial que hoy NO son compartibles.
  - ~~Slide 4.5 ("Bloques que se apilan") → ASCII del mapa: el bloque `SKILLS / SUBAGENTES` dice `(avanzado, seccion 5)`; hoy es la sección 7~~ — **RESUELTO en round 8 (2026-07-15), última escritura a `draft.md` antes del freeze de Step 6:** corregido a `(avanzado, seccion 7)` en el ASCII. Se arregló en el draft y no en el render porque una etiqueta con el número de sección equivocado es un defecto de contenido de Step 4: el ilustrador nunca corrige contenido, así que un fix aguas abajo reaparecería en cada re-render. Sustitución de un carácter, mismo ancho: geometría intacta (28 líneas de caja × 84 caracteres, bordes sin mover). El `ascii-note` no citaba número de sección y no se tocó. **Ya no queda ningún cross-ref stale vivo en el deck**, ni en prosa ni dentro de un diagrama.
  - ~~Conclusions.1 → ASCII del loop de Atlas: verificar si referencia la estructura vieja~~ — **VERIFICADO en round 8 (2026-07-15), dispatch final: NO está stale.** El diagrama y su ascii-note nombran solo piezas y pasos del loop (Schedule, `buscar-accion`, MT Newswires, `reporte-semanal`, Gmail, `publicar-tablero`, Live Artifact), sin un solo número de sección ni de slide. No requiere pase del ilustrador. La 4.5 es el único ASCII con el problema.
  - ~~Slide 5.6 ("El panel de contexto") → Speaker notes: "Las tres capas de la lámina anterior"~~ — **RESUELTO en round 8 (2026-07-15), dispatch final:** ref doblemente rota tras la partición de la ex 5.4 (la lámina anterior es hoy 5.5, que no tiene tres capas; y las tres capas de 5.4 son otra terna). Corregida a "Las tres capas del contexto".
  - ~~Slide 6.1 (ex 5.5 / ex 4.9, "Archivos .md") → Content: "Vuelve con las Skills (sección 5)" y Speaker notes: "activación semántica, no por palabra clave; sección 5"~~ — **RESUELTO en round 8 (2026-07-15), dispatch de la sección 6:** las dos refs apuntan hoy a la sección 7 ("Advanced: Skills, Subagentes y Plugins").
  - ~~Slide 7.2 ("Anatomía de un SKILL.md") → Content: "Es el `.md` con metadata de la sección 4"~~ — **RESUELTO en round 8 (2026-07-15), dispatch de la sección 7:** corregido a "sección 6" en Content y en Speaker notes. La slide es hoy la **7.3** (la ex 7.1 se partió en 7.1 + 7.2).
  - ~~Slide 7.1 ("Skills") → Speaker notes: "Conectar con la sección anterior..."~~ — **RESUELTO en round 8 (2026-07-15) por la reestructura:** la sección anterior a la 7 es ahora la 6 "Trabajar y entregar", que sí contiene el beat `.md` (6.1 y 6.2). La ref volvió a resolver sin editar una sola palabra.
  - ~~Slide 3.1 ("Tareas programadas") → Speaker notes: "En la sección 4 vuelven, sobre carpetas y archivos reales" y Sources: "la forma Cowork (se desarrolla en la sección 4)"~~ — **RESUELTO en round 8 (2026-07-15), dispatch de la sección 6:** las dos refs apuntan hoy a la sección 6 "Trabajar y entregar", donde vive Schedule sobre tus carpetas (6.3).
  - ~~Slide 3.2 ("¿Dónde corre tu tarea?") → Speaker notes: "Anticipa la sección 4: las tareas de Cowork viven de tus carpetas"~~ — **RESUELTO en round 8 (2026-07-15), dispatch de la sección 6:** hoy sección 6. La ref inversa de 6.3 a la slide 3.2 se verificó y resuelve: la sección 3 no se renumeró.
  - Refs históricas dentro de `[closed]` (6.2 / 6.3 / 2.2 / 2.5 / 3.3 / 1.2 / 5.x) y en `# Cut material` (ex-slide 4.3, nueva 4.11, ex-slide 3.2, 4.9, 4.10, ex-slide 2.2): son registro de rounds pasados, no punteros vivos. **No se tocan** (audit trail append-only).
- Nuevas URLs externas (round 3) a re-verificar en Polish si se quiere snapshot/cita estable: support.claude.com (use-skills, create-custom-skills, schedule-recurring-tasks, use-live-artifacts, manage-org-plugins, use-plugins), claude.com/blog (cowork-plugins-across-enterprise), code.claude.com/docs (sub-agents).
- ~~URLs nuevas de round 4~~ — **RESUELTO en round 5 (2026-07-09):** las 6 citas se verificaron online. Resultados: web search 10684626 OK; ChatGPT search 9237897 OK (existencia+contenido corroborados vía búsqueda; el fetch directo da 403 por bloqueo anti-bot de help.openai.com); ChatGPT tasks OK con slug canónico corregido a `10291617-tasks-in-chatgpt`; directorio de conectores: claude.ai/directory requiere login → cita reemplazada por el anuncio oficial claude.com/blog/connectors-directory + support 11176164; custom connectors 11175166 OK; modelcontextprotocol.io OK.
- ~~Tareas programadas en el chat de Claude~~ — **RESUELTO en round 5:** claude.ai SÍ tiene tareas programadas en el navegador (observación de primera mano del presentador 2026-07-09 + release notes del 7 de julio de 2026, support article 12138966: corren en la nube sin dispositivo online, beta, rollout Max-first). Slide 3.1 actualizada con Claude como ejemplo de primera clase.
- **Capacidad ejecutiva por conector (slide 2.6), estado por acción:** Gmail-borrador verificado (corpus/misión); **Calendar-agendar VERIFICADO por el presentador (2026-07-09)**; tickets (Jira/ServiceNow) y mensajes (Slack) siguen presentados como capacidad del ecosistema (MCP/conectores lo permiten — fuentes oficiales citadas) sin verificación por conector puntual — no prometer demos en vivo de esos dos sin chequear antes.
- Claim "búsqueda web integrada en casi todos los chats" (slide 2.2): verificado citable para Claude y ChatGPT; Gemini se menciona de pasada sin fuente propia — agregar fuente oficial de Google o suavizar la mención al presentar.
- **Live Artifacts y el update del 7 de julio de 2026:** la locality de Live Artifacts ("viven en tu computadora, no compartibles aún") se RE-VERIFICÓ el 2026-07-09 contra support article 14729249 (actualizado recientemente) y sigue vigente pese a que las sesiones de Cowork ahora pueden correr remotas. Vigilar este punto: es el candidato más probable a quedar desactualizado con el rollout web/mobile.

# Cut material

- **ASCII "ANTES (chat) / AHORA (agente / Cowork)"** de la ex-slide 4.3, hoy 4.4 "El cambio de paradigma" (round 8): duplica la tabla Chatear vs Delegar, que cubre lo mismo con cuatro dimensiones en vez de dos. La lámina estaba sobre el techo de densidad (3 bullets + tabla + ASCII) y el ASCII era la versión pobre del contraste. — fuente: draft round 7, slide 4.3 "De chat a agente: el cambio de paradigma". Fuente del diagrama y su intención de render, preservadas verbatim:

```text
ANTES (chat)                    AHORA (agente / Cowork)
+----------+                    +------------------------+
| vos: msg | --> respuesta      | vos: "entrega X"       |
| vos: msg | --> respuesta      |        |               |
| vos: msg | --> respuesta      |        v               |
| vos: msg | --> respuesta      | agente: planifica      |
+----------+                    | agente: toca archivos  |
 paso a paso, lo hacés vos      | vos: leés y guiás      |
                                +------------------------+
                                 entregás un resultado
```
<!-- ascii-note:
intent: contrastar el modo "chat" (un mensaje a la vez, vos hacés cada paso) contra el modo "agente" (delegás un resultado, el agente planifica y ejecuta sobre tus archivos).
emphasize: la flecha de paradigma de izquierda (ANTES) a derecha (AHORA); que en AHORA el agente hace el trabajo y vos guiás.
labels: ANTES (chat) vs AHORA (agente / Cowork).
-->

- **Detalles internos de Claude Code** (Plan mode, slash commands completos, project-directory skills, config de `/agents`, dynamic workflows, las dos misiones hands-on basadas en Code, árboles `~/.claude/...`): fuera de foco por diseño de esta charla (companion funcional/alto nivel). Claude Code aparece solo como contraste en la sección de Cowork. — fuente: corpus/agentic-ai-deck.zip.md (Code-related slides preservadas pero marcadas fuera de foco).
- **Comparación detallada Cowork vs Codex** (las dos tablas y el re-solución completa de Codex): disponible en el corpus para un ángulo "vs la alternativa", pero excluida para no diluir el foco en *usar* Cowork. Podría incorporarse como un slide opcional si el presentador lo pide en Review. — fuente: "corpus/mision - auto.zip.md" (cowork-vs-codex).
- **`buscar-accion` con Claude in Chrome / web_fetch a Yahoo Finance** como tema técnico propio: mencionado de pasada en el loop completo (Conclusions) pero no desarrollado como slide, para mantener el nivel alto. — fuente: "corpus/mision - auto.zip.md" (M2).
- **Auto memory** como concepto separado: absorbido dentro de Projects (la memoria es una de las tres capas del Project) en lugar de un slide propio, para no fragmentar el básico. — fuente: corpus/agentic-ai-deck.zip.md (Auto memory 3.7).
- **Detalle mecánico del Schedule de Cowork** (round 4, al adelgazar la ex-slide 4.3 a la nueva 4.11 por decisión C2): los sub-bullets "Describís la tarea una vez; Claude guarda el prompt como las instrucciones de la tarea" y "Tiene los mismos poderes que una tarea normal: connectors, skills, plugins instalados", y el aparte explícito sobre agentes programados alojados en la nube como funcionalidad separada (conservado solo en Speaker notes). El concepto general de tarea programada ahora se enseña en la sección 3 (desde el chat). — fuente: draft round 3, slide 4.3 "Schedule: que Cowork trabaje solo".
- **Framing "sideway" de los archivos MD** (round 4): la ex-slide 3.2 "(Sideway) Archivos MD y metadata" dejó de ser un aparte y se expandió a un beat de enseñanza de dos slides dentro de la sección Cowork (4.9 "qué es un .md / cómo se lee" + 4.10 "trabajá en .md, exportá al final"); la nota original "esto es un sideway de alto nivel — es contexto, no el plato principal" se retiró porque el presentador lo promovió a contenido central. — fuente: draft round 3, slide 3.2.
- **Título/encuadre original del roadmap** (round 4): la ex-slide 2.2 "Los bloques de Cowork: cada problema, una pieza" codificaba el arco viejo (solo bloques de Cowork, empezando en "un prompt/chatear" como bloque de Cowork). Reescrita como 4.4 "El mapa de la charla: bloques que se apilan" con el arco nuevo (chat → conectores → tareas programadas → Cowork → avanzado) y marcadores "(visto)" / "estamos acá". Los pares problema↔bloque originales de Instrucciones/Projects/Skills/Connectors/Schedule/Live Artifacts se conservan (reformulados) en el diagrama nuevo. — fuente: draft round 3, slide 2.2.
