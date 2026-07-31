---
presentation: "Agentes Inteligentes — Master in Management (MiM), IAE Business School"
class: "Claude Desktop - Chat"
research: research/corpus/
description: Slides are grouped into Sections. Each Section contains one or more Slides.
presenter: Paulo Veiga y Marco Sánchez Sorondo
audience: Estudiantes del Master in Management (MiM), IAE Business School. Perfil de gestión y negocios, mayormente no técnico; poca exposición previa a agentes de IA.
duration: 60 min (a confirmar)
date: Julio 2026
---

# Thesis

**Claim:** La clase parte del chat de IA de uso diario y hace explícito su límite: responde de memoria de entrenamiento, sin información actual ni acceso a los datos y las apps del usuario. Desde ahí lo extiende con conectores, para que consulte fuentes reales y ejecute acciones sobre el mundo del usuario, y con Schedule, para que trabaje solo con una cadencia fija. La segunda clase retoma ese chat extendido y lo lleva a Claude Cowork.

**Why it matters:** El chat que la audiencia ya usa todos los días rinde una fracción de lo que puede. Con conectores y una tarea programada, esa misma herramienta consulta el inbox y la agenda, busca información actual con sus fuentes citadas, deja un correo redactado y entrega el resumen del lunes sin que nadie lo pida. Automatizar ese trabajo no exige escribir código ni instalar nada.

**Presenter feedback:**

---

# Agenda

**Narrative arc:** La Introducción encuadra la clase abriendo por el problema: las horas que se van en tareas repetitivas y en información dispersa que nadie logra analizar junta, con la barrera de tener que saber programar; recién después llega la respuesta (agentes de IA que ejecutan trabajo, con Claude Desktop y sus dos caras, Chat y Cowork), quién es Anthropic y las cuatro herramientas de Claude (Code, Cowork, Chat/Web, Design) con la base técnica que las relaciona (1). De ahí baja a la superficie que la audiencia ya usa, el chat, y explicita su límite: responde de memoria de entrenamiento; cierra nombrando las dos capacidades que lo extienden, Conectores y Search (2). Los conectores se abren en profundidad como concepto transversal a todas las IAs: qué son, cómo además de traer información actúan sobre el mundo del usuario, dos casos concretos (el conector de búsqueda web y Claude in Chrome, con una lámina propia para el cuidado de prompt injection) y la división entre los conectores que vienen listos y los externos, que se conectan por MCP (3). Con el chat extendido, Schedule lo vuelve proactivo: describir un trabajo una vez, fijar cadencia y saber dónde corre, local o en la nube (4). Cierra una placa divisoria que presenta la misión de la materia, Faro, el analista de mercado virtual de la empresa Atlas, y manda a resolver su parte 1 con lo ya visto, todo dentro del chat y sin instalar nada; la parte 2 y el salto a Claude Cowork quedan para la segunda clase (5). La última lámina cierra la clase en cuatro tiempos: la idea que queda, lo que se puede activar esta semana, la aprobación humana antes de cada acción que importa y el puente a Claude Cowork en la segunda clase.

**Sections (in delivery order):**

- 1. Introducción
- 2. Claude Chat (Desktop)
- 3. Conectores
- 4. Schedule
- 5. La misión · parte 1

**Presenter feedback:**

---

# 1. Introducción

**Goal of this section:** Ubicar el terreno antes de arrancar: el problema que la clase viene a resolver (horas de trabajo manual e información dispersa), cómo se lo va a atacar, quién construye la herramienta y cuáles son las cuatro herramientas de Claude, con la base técnica que las relaciona.

**Presenter feedback:**

---

## 1. El problema: horas que se van en trabajo manual

### Content

- El trabajo de oficina está lleno de tareas **repetitivas**: armar el mismo reporte, pasar datos de un lado a otro, resumir el inbox, consolidar planillas.
- La información vive **dispersa**: mails, planillas, PDFs, sistemas internos. Analizarla junta cuesta horas.
- Hasta ahora, automatizar eso pedía **saber programar** — o resignarse a hacerlo a mano.

<!-- generate-image: right | un escritorio de oficina desbordado de tareas manuales: planillas, mails, reportes apilados, el reloj corriendo -->

### Sources

- (slide organizativa de la clase: encuadre del problema a partir de la realidad de trabajo de la audiencia; sin claims de producto.)

### Speaker notes

Abrir con el dolor, no con la herramienta: preguntar a mano alzada quién arma el mismo reporte todas las semanas, o pasa datos de una planilla a un sistema. La problemática tiene dos caras: tareas repetitivas que consumen horas, e información dispersa en mails, planillas y sistemas que nadie logra analizar junta. Y la barrera histórica: automatizar era territorio de quien programa. Esta clase existe porque esa barrera acaba de caer. Tiempo objetivo: ~2 min.

### Presenter feedback

---

## 2. Cómo lo vamos a atacar

### Content

- Con **agentes de IA**: no solo responden, **ejecutan trabajo** — automatizan tareas y analizan datos.
- La herramienta: **Claude Desktop** y sus dos caras, **Chat y Cowork**.
- El camino: esta clase extiende el chat que ya usan (conectores, Schedule); la segunda baja a Cowork, donde se delega trabajo completo.

<!-- generate-image: right | un camino ascendente en dos tramos: del chat conocido a un agente que trabaja sobre archivos reales -->

### Sources

- (slide organizativa de la clase, mapa del recorrido; sin claims nuevos de producto.)
- Anthropic, Claude Cowork (product page): https://www.anthropic.com/product/claude-cowork; encuadre de Claude Desktop y sus dos caras, Chat y Cowork (ya citada en la slide 1.4 "Las cuatro herramientas de Claude"; Cowork se desarrolla en la segunda clase).

### Speaker notes

La respuesta al dolor de la slide anterior, en alto nivel y sin mecánica: agentes de IA que ejecutan trabajo por vos. No desarrollar acá qué es un agente: el concepto completo se enseña en la segunda clase, la de Cowork, cuando ya se vio qué le faltaba al chat. Presentar la herramienta (Claude Desktop, dos caras) y el mapa del camino: esta clase extiende el chat que ya usan, la segunda da el salto a Cowork. Todo lo que sigue construye pieza por pieza hacia eso. Tiempo objetivo: ~2 min.

### Presenter feedback

---

## 3. Quién es Anthropic

### Content

- **Anthropic** es una empresa de IA (Public Benefit Corporation) fundada en enero de 2021 por Dario y Daniela Amodei junto a un equipo de ex investigadores de OpenAI.
- **Claude** es su familia de modelos, diseñada bajo el criterio "útil, inofensivo y honesto" (helpful, harmless, honest).

### Sources

- Anthropic, company page: https://www.anthropic.com/company; "Anthropic is an AI safety and research company... building reliable, interpretable, and steerable AI systems"; Anthropic es una Public Benefit Corporation (verificado 2026-07-30).
- Wikipedia, "Anthropic": https://en.wikipedia.org/wiki/Anthropic; fundación en enero de 2021 por siete ex empleados de OpenAI, entre ellos Dario y Daniela Amodei (verificado 2026-07-30; fuente secundaria para el dato de fundación, no cubierto en detalle por la company page oficial).

### Speaker notes

Aparte de un minuto, no más: quién está detrás de la herramienta que van a usar toda la charla. Anthropic se fundó en 2021, con los hermanos Amodei entre sus fundadores, varios venidos de OpenAI. Es una Public Benefit Corporation, así que su estatuto la obliga a perseguir el desarrollo responsable de la IA y no solo el retorno financiero; su misión declarada apunta a sistemas confiables, interpretables y dirigibles ("steerable"). Claude es su familia de modelos, con el criterio de diseño "útil, inofensivo y honesto". Nada de historia corporativa: la audiencia viene a usar la herramienta, no a estudiar la empresa. Tiempo objetivo: ~1 min.

### Presenter feedback

---

## 4. Las cuatro herramientas de Claude

### Content

- **Claude Chat/Web** (claude.ai): el asistente conversacional de uso diario, en el navegador. *El tema de esta clase.*
- **Claude Code**: CLI agéntico en la terminal, para developers. Coding de punta a punta.
- **Claude Cowork**: Claude instalado en la computadora, para quien no programa. Trabajo multipaso sobre carpetas y archivos reales. *El foco de la segunda clase.*
- **Claude Design**: prototipos, mockups y slides a partir de una idea, para quien no tiene formación de diseño (founders, product managers).

```ascii
   LAS CUATRO HERRAMIENTAS DE CLAUDE

+---------------+ +---------------+ +---------------+ +---------------+
|  Web / Chat   | |  Claude Code  | |    Cowork     | |    Design     |
| navegador,    | | terminal,     | | escritorio,   | | prototipos,   |
| tareas        | | developers    | | carpetas y    | | mockups y     |
| puntuales     | |               | | archivos      | | slides        |
+---------------+ +---------------+ +---------------+ +---------------+
        |                 |                 |                 |
        |                 +-- misma base ---+                 |
        |                        |                            |
        +------------------------+----------------------------+
                                 |
                     +--------------------------+
                     |   MISMOS MODELOS CLAUDE  |
                     +--------------------------+

   misma base tecnica = mismos archivos, Skills, MCP y el mismo loop
```
<!-- ascii-note:
intent: mostrar las cuatro herramientas de Claude una al lado de la otra y cómo se relacionan por debajo: las cuatro corren sobre los mismos modelos Claude, y Claude Code y Cowork comparten además la misma base técnica.
emphasize: la caja base "MISMOS MODELOS CLAUDE" como cimiento de las cuatro; el lazo "misma base técnica" que une solo a Claude Code y Cowork; resaltar Web/Chat como el foco de esta clase y Cowork como el de la segunda.
labels: cuatro columnas (Web/Chat = navegador; Claude Code = terminal, developers; Cowork = escritorio, carpetas y archivos; Design = prototipos, mockups y slides) sobre una base de modelos Claude compartida.
-->

### Sources

- Anthropic, Claude Cowork (product page): https://www.anthropic.com/product/claude-cowork; "built on the very same foundations as Claude Code" (confirma que Cowork comparte base con Claude Code; Cowork se desarrolla en la segunda clase).
- Anthropic, Introducing Claude Design by Anthropic Labs: https://www.anthropic.com/news/claude-design-anthropic-labs; lanzamiento en research preview, abril de 2026; "lets you collaborate with Claude to create polished visual work like designs, prototypes, slides, one-pagers, and more"; pensado para quien no tiene trasfondo de diseño (founders, product managers, marketers) (verificado 2026-07-30).
- corpus/agentic-ai-deck.zip.md, "Same engine. Different surface." (distinción Code vs Cowork; key claims; slide 7.1 "Claude Code vs Cowork — the close").
- "corpus/mision - auto.zip.md", framing de arquitectura Cowork (local, GUI, sin terminal).
- Anthropic Engineering, Building agents with the Claude Agent SDK: https://www.anthropic.com/engineering/building-agents-with-the-claude-agent-sdk; el engine de agente común (Agent SDK) sobre el que se construyen Claude Code y Cowork.

### Speaker notes

El catálogo y el mapa en una sola lámina. Cuatro herramientas, cuatro públicos: Chat/Web es el asistente de uso diario en claude.ai, para cualquiera, y el tema de esta clase; Code, para quien programa, en la terminal; Cowork, para quien no programa, instalado en la computadora, el foco de la segunda clase; Design, el más nuevo (research preview de abril de 2026), para armar prototipos, mockups y slides sin formación de diseño.

Con el diagrama, la relación entre ellas: es el mismo agente con varias caras, cambia la superficie y para quién está pensada. El matiz técnico, para decir y no para la lámina: Cowork está construido sobre las mismas bases que Claude Code (el Claude Agent SDK), así que Code y Cowork comparten el mismo engine de agente, con los mismos archivos, las mismas Skills, el mismo MCP y el mismo loop de plan, aprobar y redirigir. Web/Chat es ese mismo modelo en una superficie de chat, sin el loop agéntico completo. Design corre sobre los mismos modelos pero con su propia superficie.

Dejar claro el reparto: esta clase se queda en Chat/Web, y la segunda clase entera es Cowork, la cara para quien no trabaja en una terminal. Claude Code aparece solo como contraste; no entramos en sus internals. No hace falta demo acá. Tiempo objetivo: ~4 min.

### Presenter feedback

---

# 2. Claude Chat (Desktop)

**Goal of this section:** Partir de la superficie que la audiencia ya usa a diario, el chat, y hacer explícito su límite: responde desde su memoria de entrenamiento, con información desactualizada, riesgo de alucinación y cero acceso a los datos y apps del usuario. Cierra nombrando las dos capacidades que lo extienden: Conectores y Search.

**Presenter feedback:**

---

## 1. El chat responde de memoria

### Content

- El chat de IA ya es una herramienta de uso diario.
- De fábrica responde de su **memoria de entrenamiento**: una foto que llega hasta la **fecha de entrenamiento**. No busca información nueva.
- **Información vieja**: lo posterior al corte no existe.
- **Alucinación**: inventa con confianza.

```ascii
        EL CHAT "COMO VIENE DE FABRICA"
                                             lo que NO ve:
   +---------------------------------+       x  noticias de hoy
   |            CHAT DE IA           |       x  los mails
   |  +---------------------------+  |       x  el calendario
   |  |  MEMORIA DE ENTRENAMIENTO |  |       x  los archivos
   |  |  (foto congelada hasta la |  |       x  las apps del trabajo
   |  |   fecha de entrenamiento) |  |
   |  +---------------------------+  |
   |     responde "de memoria"       |
   +---------------------------------+
```
<!-- ascii-note:
intent: mostrar que el chat de IA sin extensiones responde solo desde su memoria de entrenamiento (foto congelada hasta la fecha de entrenamiento) y no tiene acceso al mundo del usuario.
emphasize: la caja interna "MEMORIA DE ENTRENAMIENTO (foto congelada)"; la lista de lo que NO ve (noticias de hoy, mails, calendario, archivos, apps) fuera de la caja.
labels: caja exterior = CHAT DE IA; caja interior = memoria de entrenamiento / fecha de entrenamiento; columna derecha = lo que no ve.
-->

### Sources

- Anthropic Support, Enabling and using web search: https://support.claude.com/en/articles/10684626-enabling-and-using-web-search; el encuadre oficial: sin búsqueda web, Claude responde limitado a su información de entrenamiento; la búsqueda le da acceso a información actual (referencia también para la Sección 3).
- (concepto general de LLM: fecha de corte / respuestas desde entrenamiento / alucinaciones; material introductorio estándar del curso; sin claim específico de producto.)

### Speaker notes

Arrancar desde lo conocido: pedir a mano alzada quién usó un chat de IA esta semana. Van a levantar la mano casi todos (ChatGPT, Gemini, Claude). La idea a instalar: ese chat, tal como viene, responde de memoria. Cuando le preguntás no busca nada; recuerda lo que leyó hasta su fecha de entrenamiento (knowledge cutoff). Un colega brillante que leyó muchísimo hasta una fecha y desde entonces está incomunicado. Tres consecuencias que ya sufrieron sin saberlo. Una, datos viejos: precios, noticias, versiones de software y papers posteriores al corte no existen para el modelo. Dos, inventos con cara de verdad: cifras, citas y referencias que suenan perfectas y son falsas (insistir en verificar toda salida). Tres, la más limitante para el trabajo real: no ve nada tuyo, ni mails, ni calendario, ni archivos, ni apps. Ese tercer límite, el que la lámina deja al diagrama y no repite en texto, es el que abre la charla: ¿y si pudiéramos conectarlo? Tiempo objetivo: ~4 min.

### Presenter feedback

---

## 2. Lo que viene: conectores y búsqueda

### Content

- El chat de memoria tiene un techo. Dos capacidades lo extienden y recorren el resto de la charla.
- **Conectores**: el chat deja de estar aislado y accede a fuentes reales (web, mail, calendario, documentos), y hasta actúa.
- **Search**: el primer conector, el más universal, ya integrado en casi todos los chats. Trae información actual y cita sus fuentes.
- Los dos conceptos se profundizan en la próxima sección.

### Sources

- Anthropic Support, Enabling and using web search: https://support.claude.com/en/articles/10684626-enabling-and-using-web-search; ya citada en esta sección y desarrollada en la Sección 3.
- Claude blog, Connectors directory: https://claude.com/blog/connectors-directory; el catálogo oficial de conectores de Claude, desarrollado en la Sección 3.

### Speaker notes

Slide puente, corta a propósito: recién vimos que el chat de memoria tiene un techo; acá se nombra, sin desarrollar, lo que lo levanta. Dos ideas para instalar antes de seguir: Conectores (el chat deja de estar aislado) y Search (el primero y más universal de los conectores). La Sección 3 recién ahí los abre en profundidad, con demo incluida. No adelantar contenido de esa sección; el objetivo de esta slide es solo nombrar el mapa. Tiempo objetivo: ~2 min.

### Presenter feedback

---

# 3. Conectores

**Goal of this section:** Instalar el concepto de conector, válido para todas las IAs: con conectores, el chat consulta información real (búsqueda web, mail, calendario) y también actúa sobre el mundo del usuario (mandar mails, agendar reuniones); sin ellos, responde de memoria. Sobre esa base, dos casos concretos (el conector de búsqueda web y Claude in Chrome, este último con una lámina propia para el prompt injection) y la división entre los conectores que vienen listos y los externos, que se conectan por MCP.

**Presenter feedback:**

---

## 1. Qué es un conector

### Content

- **Conector** = extensión que conecta el chat a un sistema externo: web, mail, calendario, documentos.
- Vale igual en ChatGPT, Gemini y Claude.
- Se activa a través de la biblioteca de conectores. Muchos requieren autenticación.

```ascii
   CHAT SOLO                        CHAT CON CONECTORES
+----------------+              +----------------+
|     CHAT       |              |     CHAT       |----> [ web ]
|  responde de   |              |  consulta      |----> [ mail ]
|  memoria de    |              |  fuentes       |----> [ calendario ]
|  entrenamiento |              |  REALES antes  |----> [ documentos ]
+----------------+              |  de responder  |
   (aislado)                    +----------------+
                                  (conectado al mundo real)
```
<!-- ascii-note:
intent: contrastar lado a lado el chat aislado (responde de memoria de entrenamiento) contra el chat con conectores (consulta fuentes reales; web, mail, calendario, documentos; antes de responder).
emphasize: el lado derecho con las flechas hacia web/mail/calendario/documentos; la etiqueta "(conectado al mundo real)" vs "(aislado)".
labels: izquierda = CHAT SOLO (aislado, memoria de entrenamiento); derecha = CHAT CON CONECTORES (web, mail, calendario, documentos).
-->

### Sources

- Anthropic Support, Enabling and using web search: https://support.claude.com/en/articles/10684626-enabling-and-using-web-search; la búsqueda web como capacidad integrada del chat de Claude.
- Claude blog, Connectors directory: https://claude.com/blog/connectors-directory; el catálogo oficial de conectores de Claude (referencia ampliada en la slide 3.7; verificado 2026-07-09).

### Speaker notes

La slide instala el concepto que ordena la sección: un conector saca al chat de su aislamiento y le da acceso a buscar en la web, leer mail, ver calendario, consultar documentos. Repetir que es transversal: vale para ChatGPT, Gemini y Claude. Los nombres cambian ("connectors", "apps", "extensiones"), la idea es la misma. Usar el diagrama para el contraste: mismo chat, ahora con líneas hacia afuera, y antes de responder puede ir a buscar información a la fuente (la web, inbox, agenda). El contraste que la lámina ya no repite en texto y el diagrama sí dibuja: chat solo responde de memoria, chat con conectores consulta fuentes reales antes de responder. Cerrar bajando la barrera de entrada: esto se activa desde la configuración o desde la biblioteca de conectores; algunos conectores piden autenticación. Tiempo objetivo: ~3 min.

### Presenter feedback

---

## 2. Los conectores también actúan

### Content

- Además de traer info, un conector expone **acciones**: la IA **hace**.
- Verificado de primera mano: **dejar redactado un mail** (borrador en Gmail) y **agendar una reunión** (evento en el calendario).
- Abrir un ticket (Jira, ServiceNow) o mandar un mensaje (Slack): **capacidad del ecosistema**, sin conector puntual probado en clase.
- Cuidado con las autorizaciones y los permisos. **Un mail enviado sin revisión humana puede generar muchos problemas.**

```ascii
        CONECTOR: dos direcciones

   LEER (traer info)          ACTUAR (hacer)
   <------------------        ------------------>
+------+           +----------+           +----------+
| CHAT |  <------- | conector |  ------>  | el mundo |
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

- Model Context Protocol, https://modelcontextprotocol.io; el estándar define herramientas que ejecutan acciones sobre sistemas externos, no solo lectura: "AI applications ... which can access your data and take actions on your behalf" (verificado 2026-07-09).
- Anthropic Support, Getting started with custom connectors using remote MCP: https://support.claude.com/en/articles/11175166-getting-started-with-custom-connectors-using-remote-mcp; los conectores permiten a Claude "access and take action in these services" (verificado 2026-07-09).
- "corpus/mision - auto.zip.md", el connector de Gmail **deja un borrador de correo** para el equipo (capacidad ejecutiva en acción, M3 y loop final).
- Verificación de primera mano del presentador (2026-07-09): la acción de **agendar/crear eventos vía el connector de Calendar** está chequeada y funciona.
- corpus/agentic-ai-deck.zip.md, Connectors como "las manos" del agente (tocar sistemas, no solo leerlos).

### Speaker notes

Segunda idea de la sección, pegada a la definición: el conector no se queda en traer información, también ejecuta acciones sobre los sistemas conectados. Los dos primeros ejemplos están verificados de primera mano y se pueden demostrar en vivo: el borrador de Gmail (misión de Faro) y agendar por Calendar, que el docente chequeó. Los otros dos, tickets y mensajes, son capacidad del ecosistema (el estándar MCP y los conectores lo permiten) y así están marcados en la lámina: no prometer una demo en vivo de esos dos sin chequear antes. Balancear con el control: nada de esto pasa sin que el usuario haya conectado y autorizado el servicio. La práctica sana mientras aprenden es "borrador, no envío directo"; Faro hace eso, deja el borrador en Gmail y no lo manda. Cerrar anunciando que las slides que siguen bajan a casos concretos, empezando por el conector que ya tienen. Tiempo objetivo: ~3 min.

### Presenter feedback

---

## 3. Caso 1: Web Search Connector

### Content

- El conector más universal: viene en casi todos los chats (Claude, ChatGPT, Gemini). Se activa con un toggle.
- La misma pregunta admite **dos modos de responder**, y el usuario decide cuál.
- El "buscando..." y las fuentes citadas marcan el punto de verificación.
- Regla: si la respuesta pudo cambiar → búsqueda obligada.

```ascii
   la MISMA pregunta: "¿ultima version de X?"

   DE MEMORIA                        CON BUSQUEDA WEB
+------------------+             +------------------+
| entrenamiento    |             | busca ahora en   |
| hasta fecha de   |             | la web           |
| entrenamiento    |             |   |              |
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
labels: izquierda = DE MEMORIA (fecha de entrenamiento); derecha = CON BÚSQUEDA WEB (busca ahora, cita fuentes).
-->

### Sources

- Anthropic Support, Enabling and using web search: https://support.claude.com/en/articles/10684626-enabling-and-using-web-search; "Web search expands Claude's knowledge with real-time data"; "Every response includes citations, so you can easily verify sources yourself" (verificado 2026-07-09).
- OpenAI Help, ChatGPT search: https://help.openai.com/en/articles/9237897-chatgpt-search; búsqueda web integrada en ChatGPT, automática cuando la pregunta lo amerita, con citas inline (evidencia de que el concepto es transversal; verificado 2026-07-09).

### Speaker notes

Acá se fija la distinción memoria vs información viva. Los dos modos, que el diagrama contrasta y la lámina no repite en texto: de memoria, recuerda hasta la fecha de entrenamiento y puede estar viejo o mal; con búsqueda, va a buscar información real y actualizada y cita fuentes. Con conexión, hacerlo en demo de 2 minutos: la misma pregunta ("¿cuál es la última versión de X?" o "¿qué pasó ayer con Y?") con búsqueda apagada y prendida, y comparar. Señalar el indicador de "buscando..." y las fuentes citadas; enseñarles a mirar eso cada vez. Es el conector más fácil de activar (un toggle en la configuración; en varios chats ya viene activo por defecto). La regla práctica que se llevan: si la respuesta pudo haber cambiado desde el entrenamiento (precios, noticias, versiones, papers, normativa), exigí búsqueda. Arrancamos por este conector porque ya lo tienen; falta saber cuándo está actuando. Tiempo objetivo: ~5 min (con demo).

### Presenter feedback

---

## 4. Caso 2: Claude in Chrome

### Content

- **Claude in Chrome**: una extensión de Chrome. Claude abre un panel al costado de la página y ve lo mismo que ve el usuario.
- Trabaja dentro de la sesión del navegador ya iniciada, en los sitios donde el usuario ya está identificado.
- Qué hace ahí: navega, hace clic, completa formularios y encadena varios pasos entre pestañas.
- Trae conocimiento incorporado de **Slack, Google Calendar, Gmail y Google Docs**, así que responde a un pedido en lenguaje corriente ("agendá una reunión").
- Se habilita desde la biblioteca de conectores (*Connectors*) en Claude Desktop, como cualquier otro.

```ascii
   PAGINA WEB ABIERTA          CLAUDE IN CHROME
   (sesion ya iniciada)        (panel lateral)
+------------------------+   +--------------------+
|                        |   |                    |
|  formulario del CRM    |-->| lee lo que hay     |
|  hilo de mail          |   | en la pantalla     |
|  tablero del proveedor |   |                    |
|                        |<--| navega, hace clic, |
|                        |   | completa campos,   |
+------------------------+   | maneja pestanas    |
                             +--------------------+
```
<!-- ascii-note:
intent: mostrar que Claude in Chrome trabaja en un panel al costado de la página abierta, dentro de la sesión que el usuario ya tiene iniciada: lee lo que aparece en pantalla y ejecuta acciones sobre ese mismo sitio.
emphasize: las dos flechas opuestas (de la página hacia Claude = leer; de Claude hacia la página = actuar); que el panel convive con la página en la misma ventana.
labels: izquierda = página web abierta (sesión ya iniciada); derecha = Claude in Chrome (panel lateral), con lo que lee y lo que hace.
-->

### Sources

- Anthropic Support, Get started with Claude in Chrome: https://support.claude.com/en/articles/12012173-get-started-with-claude-in-chrome; "Claude in Chrome is a browser extension that allows Claude to read, click, and navigate websites alongside you"; panel lateral que acompaña la navegación; manejo de varias pestañas; "Claude has built-in knowledge of how to navigate popular platforms including Slack, Google Calendar, Gmail, Google Docs, and GitHub"; disponible en todos los planes pagos (Pro, Max, Team, Enterprise), solo en Chrome de escritorio ("not supported on other Chromium-based web browsers or mobile devices"); se habilita como conector desde Settings → Connectors en Claude Desktop (fuente oficial del proveedor; verificado 2026-07-30).

### Speaker notes

Segundo caso concreto, y el que más sorprende a esta audiencia. La idea a instalar: hasta acá el conector traía datos de un servicio; Claude in Chrome opera el navegador que el usuario ya tiene abierto, con las sesiones ya iniciadas. Por eso entra a sistemas que no tienen API ni integración: si el usuario puede hacerlo con el mouse, Claude puede hacerlo. Mostrar el panel lateral en la pantalla si hay conexión; con eso solo se entiende. Disponibilidad, para decir y no para la lámina: planes pagos (Pro, Max, Team, Enterprise) y solo en Chrome de escritorio, no en otros navegadores basados en Chromium ni en móvil. Las dos slides que siguen completan el beat: primero cuándo conviene usarlo, después el cuidado de seguridad; no adelantar ninguno acá. Tiempo objetivo: ~3 min.

### Presenter feedback

---

## 5. Cuándo sirve Claude in Chrome

### Content

- **Cargar datos en un sistema web**: pasar al CRM o al ERP lo que llegó por mail o en una planilla, campo por campo.
- **Comparar proveedores**: precios y condiciones abiertos en varias pestañas, consolidados en un cuadro.
- **Coordinar agenda y correo**: leer el hilo, agendar la reunión en Google Calendar y dejar la respuesta escrita.
- **Relevar un portal que no exporta**: listados de precios, licitaciones o estados de pedido, volcados a una tabla.

```ascii
   EL PATRON COMUN DE LOS CUATRO CASOS

   +-----------------------------+
   | un sitio web SIN exportar   |
   | ni integracion (sin API)    |
   +-----------------------------+
                 |
                 v
   +-----------------------------+      a mano: pestana por
   | una tarea repetitiva sobre  | ---> pestana, campo por
   | esa misma pantalla          |      campo, todas las semanas
   +-----------------------------+
                 |
                 v
   +-----------------------------+
   | CLAUDE IN CHROME opera el   |
   | navegador ya abierto        |
   +-----------------------------+
                 |
                 v
   el dato queda cargado / la tabla queda armada
```
<!-- ascii-note:
intent: mostrar el denominador común de los cuatro casos de uso, en vez de repetirlos en texto: un sitio web sin exportación ni integración, más una tarea repetitiva sobre esa misma pantalla, es exactamente el terreno donde Claude in Chrome opera el navegador que ya está abierto.
emphasize: la caja "CLAUDE IN CHROME opera el navegador ya abierto" como el punto de la lámina; el contraste entre el camino manual (pestaña por pestaña, campo por campo) y el resultado de abajo.
labels: cadena vertical de tres cajas (sitio sin exportar → tarea repetitiva → Claude in Chrome) con el remate "el dato queda cargado / la tabla queda armada" al pie.
-->

### Sources

- Anthropic Support, Get started with Claude in Chrome: https://support.claude.com/en/articles/12012173-get-started-with-claude-in-chrome; completado de formularios y campos, consolidación entre varias pestañas, workflows multipaso que siguen corriendo en segundo plano, conocimiento incorporado de Gmail y Google Calendar (base de los cuatro casos; fuente oficial del proveedor; verificado 2026-07-30).
- (los cuatro casos son adaptación del presentador al perfil de gestión de la audiencia, apoyados en las capacidades documentadas arriba; no son casos publicados por Anthropic.)

### Speaker notes

Los cuatro casos están elegidos para un perfil de gestión, no de desarrollo. El denominador común, que el diagrama dibuja, es un sitio web sin exportación ni integración y una tarea repetitiva de copiar y pegar. Preguntar a mano alzada quién carga datos a mano en un sistema interno: ahí aterriza el primer caso. El segundo es el que mejor muestra el manejo de varias pestañas a la vez. El tercero se apoya en que Claude ya sabe moverse dentro de Gmail y Google Calendar. El cuarto es el clásico portal del proveedor o del organismo público sin botón de exportar. Terminados los cuatro, frenar: la lámina que sigue es el cuidado, y merece su propio tiempo. Tiempo objetivo: ~2 min.

### Presenter feedback

---

## 6. Cuidado: prompt injection

### Content

- **Prompt injection**: una página, un mail o un documento pueden traer instrucciones ocultas que Claude tome como pedidos del usuario.
- Anthropic lo documenta como riesgo vigente: hay clasificadores que revisan el contenido entrante y cada acción antes de ejecutarla, y aun así el riesgo no es cero.
- Tres cuidados: **sitios confiables**, un **perfil de navegador separado** de las cuentas sensibles, **revisión humana** antes de aprobar cada acción.

```ascii
   PROMPT INJECTION: como funciona el ataque

   +-------------------------------+
   |  pagina / mail / documento    |
   |                               |
   |   ...texto visible...         |
   |   [ INSTRUCCION OCULTA ]      |
   +-------------------------------+
                  |
                  |  Claude lee TODO lo que hay en la pantalla
                  v
   +-------------------------------+
   |  Claude puede tomar esa       |
   |  instruccion como si fuera    |
   |  un pedido del usuario        |
   +-------------------------------+
                  |
                  v
        una accion que nadie pidio
```
<!-- ascii-note:
intent: explicar el mecanismo del prompt injection en tres pasos: una página o un mail traen una instrucción oculta entre el texto visible, Claude lee toda la pantalla y puede confundir esa instrucción con un pedido del usuario, y el resultado es una acción que nadie pidió.
emphasize: la caja "[ INSTRUCCION OCULTA ]" dentro del documento, en contraste con el texto visible; el remate "una accion que nadie pidio" al pie.
labels: arriba = página / mail / documento con instrucción oculta; medio = Claude la toma como pedido del usuario; abajo = una acción que nadie pidió.
-->

### Sources

- Anthropic Support, Use Claude in Chrome safely: https://support.claude.com/en/articles/12902428-use-claude-in-chrome-safely; "The biggest risk facing browser-using AI tools is prompt injection attacks where malicious instructions hidden in web content (websites, emails, documents) could trick Claude into taking unintended actions"; clasificadores que revisan el contenido entrante y cada acción antes de ejecutarla; "the chances of an attack are still non-zero"; recomendaciones de sitios confiables, perfil de navegador separado y revisión de las acciones propuestas (fuente oficial del proveedor, que documenta el riesgo como abierto; verificado 2026-07-30).

### Speaker notes

Lámina propia porque es el cuidado de seguridad más importante de la charla y no puede quedar como el último bullet de una lista de casos de uso. Frenar el ritmo y darle su tiempo. Prompt injection es el riesgo central de cualquier IA que navegue, y lo documenta el propio Anthropic: una página o un mail pueden traer texto oculto con instrucciones, y Claude puede leerlas como si vinieran del usuario. Anthropic corre clasificadores que revisan el contenido entrante y cada acción antes de ejecutarla, y aun así aclara que el riesgo no es cero: decirlo con esas palabras, sin suavizarlo. La postura que enseña esta charla es la de siempre: sitios confiables, un perfil de navegador separado de las cuentas sensibles, y el humano aprueba antes de que se ejecute algo que importa. Si hay una sola cosa que la audiencia se lleve de la sección de conectores, que sea esta. Tiempo objetivo: ~3 min.

### Presenter feedback

---

## 7. Out of the box y externos

### Content

- Los conectores se dividen en dos familias, según quién los prepara: los que vienen listos con el producto y los que conecta el equipo.
- Toda la familia externa se conecta por el **protocolo MCP**.
- El criterio de confianza cambia entre las dos: un conector del catálogo pasó por Anthropic; autorizar uno externo le da acceso a los datos del usuario, así que conviene reservarlo para servicios confiables.

```ascii
                  CONECTORES
                       |
        +--------------+---------------+
        v                              v
  OUT OF THE BOX                   EXTERNOS
  vienen listos                    los conecta el equipo
  · busqueda web                   · CRM / ERP
  · Claude in Chrome               · base interna
  · Gmail / Calendar / Drive       · servicio de un tercero
        |                              |
        v                              v
  se activan desde la              todos por el
  biblioteca de conectores         protocolo MCP
```
<!-- ascii-note:
intent: separar los conectores en dos familias según quién los prepara: los que vienen listos con el producto (out of the box) y los externos que conecta un equipo, y marcar que toda la rama externa pasa por el protocolo MCP.
emphasize: las dos ramas como categorías paralelas; el remate de cada rama (biblioteca de conectores a la izquierda, protocolo MCP a la derecha).
labels: raíz = CONECTORES; rama izquierda = OUT OF THE BOX (búsqueda web, Claude in Chrome, Gmail/Calendar/Drive); rama derecha = EXTERNOS (CRM/ERP, base interna, servicio de un tercero).
-->

### Sources

- Claude blog, Discover tools that work with Claude (Connectors directory): https://claude.com/blog/connectors-directory; el catálogo oficial de conectores listos para usar (verificado 2026-07-09).
- Anthropic Support, Use connectors to extend Claude's capabilities: https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities; los conectores listos se activan desde la configuración de Claude.
- Anthropic Support, Getting started with custom connectors using remote MCP: https://support.claude.com/en/articles/11175166-getting-started-with-custom-connectors-using-remote-mcp; los conectores fuera del catálogo se agregan vía MCP y "allow you to connect Claude to services that have not been verified by Anthropic, and allow Claude to access and take action in these services" (verificado 2026-07-09).
- Model Context Protocol (sitio oficial del estándar): https://modelcontextprotocol.io; el protocolo por el que se conectan los servicios externos.

### Speaker notes

El ordenador mental de la sección: no todos los conectores salen del mismo lugar. Los out of the box vienen con el producto y el usuario solo los activa; los dos casos vistos hasta acá, búsqueda web y Claude in Chrome, están en esa familia, igual que Gmail, Calendar y Drive. Los externos son los que una empresa monta contra sus propios sistemas (CRM, ERP, una base interna), y ahí aparece el estándar: todos hablan MCP. Para esta audiencia el mensaje es de rol. La familia out of the box la maneja cualquier usuario desde la biblioteca de conectores; la externa la arma un equipo técnico y después el usuario la usa desde el mismo lugar que las otras. Las dos slides que siguen bajan a cada familia, una por vez. Tiempo objetivo: ~2 min.

### Presenter feedback

---

## 8. Out of the box: buscar y conectar

### Content

- Flujo básico: **buscar + Connect + autorizar**. Como conectar Gmail a una app nueva.
- El **directorio oficial de Claude** lista los conectores listos para usar, incluidos proveedores de datos del sector, por ejemplo un proveedor de noticias financieras.

![Directorio de Connectors](images/connectors_directory.png)

![Conexión de un Connector: buscar y conectar](images/connector_browser.png)

- Ejemplos guía: **mail y calendario**. "¿Qué mails me perdí ayer? ¿Qué tengo esta semana?"

### Sources

- Claude blog, Discover tools that work with Claude (Connectors directory): https://claude.com/blog/connectors-directory; anuncio oficial del directorio; navegar y conectar de un clic vía claude.ai/directory (verificado 2026-07-09; el directorio en sí requiere login).
- Anthropic Support, Use connectors to extend Claude's capabilities: https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities; cómo se conectan y usan los conectores desde la configuración.
- corpus/agentic-ai-deck.zip.md, matriz 5.6 (Connectors configurados por la Settings UI; directorio + un clic).
- "corpus/mision - auto.zip.md", MT Newswires "ya tiene un connector listo" (Step 2.1); Gmail connector de un clic (M3); "no estás programando: te conectás a un servicio que ya existe".
- Anthropic Support, Getting started with custom connectors using remote MCP: https://support.claude.com/en/articles/11175166-getting-started-with-custom-connectors-using-remote-mcp; la vía de los conectores no oficiales y la base del criterio de confianza: "allow you to connect Claude to services that have not been verified by Anthropic, and allow Claude to access and take action in these services" (verificado 2026-07-09).

### Speaker notes

Slide práctica de la familia out of the box. Mostrar las dos capturas (el directorio de conectores y la pantalla de conexión) para desarmar el "esto es técnico". Conectar un servicio implica buscarlo, tocar Connect y autorizarlo, igual que cuando se conecta Gmail a cualquier app; se configura por la UI, sin archivo local que editar. Insistir en mail y calendario, los ejemplos guía de la sección: con Gmail conectado el chat lee y resume el inbox, con Calendar ve la agenda. Son preguntas que el chat aislado no puede responder. Mencionar que el directorio también trae proveedores de datos de sector, sin nombrar todavía el de la misión: el reveal de Faro es la sección 5 y adelantarlo acá lo gasta. Nota: las capturas son de la app de Claude (Cowork); el flujo buscar+Connect es el mismo en el chat. Tiempo objetivo: ~2 min.

### Presenter feedback

---

## 9. External connectors: todo pasa por MCP

### Content

- **Conectores externos**: los que una empresa conecta contra sus propios sistemas o los de un tercero, fuera del catálogo listo para usar.
- Todos se conectan por **MCP** (Model Context Protocol), el estándar que traduce el pedido del usuario en llamadas al servicio conectado.
- Ejemplo: el usuario pide "los pedidos abiertos del cliente X" → el conector consulta el ERP de la empresa y devuelve la respuesta al chat.
- Un chat que se informa y actúa puede trabajar **solo** (sección 4).

```ascii
+--------+   pide datos    +-----------+   protocolo   +----------------+
| CHAT / | --------------> | Connector |  -- MCP -->   | Servicio       |
| agente |                 |  externo  |               | CRM/ERP/base   |
+--------+ <-------------- +-----------+ <-----------  +----------------+
            devuelve datos
```
<!-- ascii-note:
intent: mostrar el flujo de una llamada a un conector externo: el chat/agente pide datos, el conector traduce el pedido vía el protocolo MCP, el servicio de la empresa responde.
emphasize: la etiqueta "MCP" sobre la flecha del medio, como el estándar único de toda la familia externa; el conector como puente entre el chat y el servicio.
labels: Chat/agente -> Connector externo -> Servicio (CRM / ERP / base interna); flecha de ida "pide datos", flecha de vuelta "devuelve datos".
-->

### Sources

- corpus/agentic-ai-deck.zip.md, definición de Connector (MCP): "The hands"; slide 5.4 (rango de MCP; "any app that exposes an MCP server").
- Model Context Protocol (sitio oficial del estándar): https://modelcontextprotocol.io; qué es MCP y cómo las plataformas exponen herramientas; base de los conectores externos.
- Anthropic Support, Getting started with custom connectors using remote MCP: https://support.claude.com/en/articles/11175166-getting-started-with-custom-connectors-using-remote-mcp; los conectores fuera del catálogo se agregan vía MCP remoto.
- "corpus/mision - auto.zip.md", MT Newswires "ya tiene un connector listo" (Step 2.1); Gmail connector de un clic (M3).

### Speaker notes

Cierre técnico de la sección, sin asustar a nadie. La familia externa es la que una empresa arma contra sus propios sistemas, y toda ella pasa por el mismo estándar: MCP, el Model Context Protocol. Usar el diagrama para explicar qué pasa por debajo: el chat pide datos, el conector traduce ese pedido en llamadas al servicio, el servicio responde. El patrón se repite siempre: la plataforma expone sus acciones como herramientas y la IA las usa. La imagen que mejor funciona, para decir: los conectores son las manos de la IA, lo que puede tocar y que de otro modo no podría (Drive, Gmail, Calendar, Slack, bases de datos). Quién lo arma: el equipo técnico expone un servidor MCP y ese servicio queda disponible como un conector más; nadie de esta clase va a escribir uno. Cerrar sembrando la sección 4: un chat que se informa y actúa, más una cadencia fija, trabaja solo. Tiempo objetivo: ~2 min.

### Presenter feedback

---

# 4. Schedule

**Goal of this section:** Que la audiencia entienda qué es Schedule (describir un trabajo una vez, fijar una cadencia, que corra sola), cómo se potencia con conectores (el resumidor semanal de mails) y la pregunta práctica antes de confiarle algo: ¿dónde corre? Local, con la computadora prendida, o nube. Todavía desde el mundo del chat.

**Presenter feedback:**

---

## 1. Describir una vez, que corra sola

### Content

- **Schedule** = describir un trabajo una vez y fijarle una cadencia; el prompt se ejecuta solo, sin volver a pedirlo.
- El ejemplo: *"todos los días 8:00, resumí mi inbox, lo urgente arriba."*
- Existe en **ChatGPT** ("tasks") y en **Claude** (claude.ai, desde el navegador).

```ascii
        SCHEDULE (se describe UNA vez)

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
  resumen listo en el chat, cada semana,
  sin pedirlo de nuevo
```
<!-- ascii-note:
intent: mostrar el ciclo de un Schedule: un disparador de calendario (lunes 8:00) ejecuta la tarea, que usa los conectores (mail/web/calendario) para traer información y deja el resultado listo sin intervención del usuario.
emphasize: que se describe UNA vez y corre sola; el reloj como disparador; el uso de conectores dentro de la corrida; el resultado que "aparece" cada semana.
labels: reloj (cadencia) -> la tarea corre sola -> conectores (mail/web/calendario) -> resumen listo en tu chat.
-->

### Sources

- OpenAI Help, Tasks in ChatGPT: https://help.openai.com/en/articles/10291617-tasks-in-chatgpt; tareas programadas en el chat de ChatGPT (evidencia transversal del concepto; verificado 2026-07-09).
- Anthropic Support, Release notes (entrada del 7 de julio de 2026): https://support.claude.com/en/articles/12138966; "scheduled tasks run with no device online"; sesiones remotas (beta); rollout empezando por Max (verificado 2026-07-09).
- Observación de primera mano del presentador (2026-07-09): tareas programadas activas en claude.ai en el navegador.
- TechCrunch (2026-07-07), "The coding agent wars are spilling into the rest of the office": https://techcrunch.com/2026/07/07/the-coding-agent-wars-are-spilling-into-the-rest-of-the-office-claude-cowork/; cobertura de prensa: expansión a web/mobile, corridas en background sin dispositivo activo, rollout Max (encuadre de terceros).
- Anthropic Support, Schedule recurring tasks in Claude Cowork: https://support.claude.com/en/articles/13854387-schedule-recurring-tasks-in-claude-cowork; la forma Cowork del Schedule.
- "corpus/mision - auto.zip.md", el flujo programado de Atlas (Step 3.3): la semilla del "resumidor que corre solo".

### Speaker notes

Slide-concepto de la sección, en dos mitades. Primera: se describe el trabajo una vez, se elige cadencia (diaria, semanal, a demanda) y corre solo, avisando con el resultado. Segunda, que el diagrama dibuja en su caja del medio y la lámina ya no repite en texto: la tarea hereda los conectores ya configurados (mail, web, calendario). El resumidor de mails funciona como ejemplo porque el inbox desbordado es un problema que la audiencia vive. Variante semanal: "los lunes a las 8:00, resumime la semana del calendario + los mails sin responder". Contarlo en primera persona si se puede ("mi resumen de las 8:00"). Marcar que existe en los dos mundos: ChatGPT lo llama "tasks" (recordatorios, briefings diarios, monitoreo) y Claude ya las ofrece en claude.ai desde el navegador. Si el rollout lo permite, mostrarlas EN VIVO desde la cuenta del docente, que ya las usa. La pregunta de dónde corre la tarea (nube o local, computadora prendida) viene en la próxima slide; no adelantarla. Tiempo objetivo: ~5 min.

### Presenter feedback

---

## 2. ¿Dónde corre? Local o nube

### Content

- Antes de confiarle algo a un Schedule: **saber dónde corre**.
- Los Schedule que usan **archivos o apps locales** corren local **siempre**, incluso con la ejecución en la nube disponible.

```ascii
   el Schedule: ¿DONDE corre?
              |
      +-------+----------------------+
      v                              v
  LOCAL (hoy, la mayoria)      NUBE (beta, jul 2026 ->)
  · computadora prendida       · sin computadora prendida
  · app abierta                · rollout gradual (Max 1ro)
  · apagada o suspendida:      · PERO: archivos/apps
    la corrida puede perderse    locales => local igual
  · ojo laptops suspendidas
```
<!-- ascii-note:
intent: mostrar la bifurcación práctica de un Schedule según dónde corre: LOCAL (computadora prendida + app abierta; si está apagada o suspendida la corrida puede perderse; cuidado con laptops que se suspenden) vs NUBE (sin computadora prendida, beta desde julio 2026, rollout Max primero; excepción: tareas con archivos/apps locales corren local igual).
emphasize: la bifurcación como pregunta ("¿DÓNDE corre?"); en LOCAL los tres cuidados prácticos (prendida, app abierta, la corrida puede perderse); en NUBE que no hace falta la computadora prendida pero es beta/rollout gradual, con la excepción de archivos locales.
labels: raíz = el Schedule ¿dónde corre?; rama izquierda = LOCAL (hoy, la mayoría) con cuidados; rama derecha = NUBE (beta, julio 2026) con condiciones.
-->

### Sources

- Anthropic Support, Schedule recurring tasks in Claude Cowork: https://support.claude.com/en/articles/13854387-schedule-recurring-tasks-in-claude-cowork; ejecución remota ("run on their cadence even when your computer is asleep or the Claude Desktop app is closed") y la excepción local: "If a scheduled task requires local files or apps, it will only run locally" (verificado 2026-07-09).
- Anthropic Support, Release notes (7 de julio de 2026): https://support.claude.com/en/articles/12138966; "scheduled tasks run with no device online"; beta, rollout gradual empezando por Max (verificado 2026-07-09).
- TechCrunch (2026-07-07): https://techcrunch.com/2026/07/07/the-coding-agent-wars-are-spilling-into-the-rest-of-the-office-claude-cowork/; corridas en background sin dispositivo activo, disponible primero para suscriptores Max (encuadre de terceros).
- Comportamiento local "se saltea y corre al volver": documentado en la versión anterior del artículo 13854387 (verificada en junio 2026, cuando la ejecución era solo local); la versión actual ya no lo detalla; mantenido como cuidado práctico del modo local, con esa atribución.

### Speaker notes

La slide del consejo práctico que pidió el presentador: "tengan en cuenta que la computadora esté prendida". Hoy conviven dos realidades y hay que enseñar las dos. Una: la ejecución en la nube existe desde el 7 de julio de 2026, la tarea corre sin tu computadora, pero es beta y llega de a poco, empezando por el plan Max. Dos: mientras a tu cuenta no le llegue, la tarea corre local. Computadora prendida y app abierta, o no corre. Los cuidados del modo local son los que la mayoría de la audiencia va a vivir este cuatrimestre. Si la computadora está apagada o suspendida a la hora programada, la corrida puede perderse: la versión anterior del artículo 13854387 (verificada en junio de 2026, cuando la ejecución era solo local) documentaba que la tarea se salteaba y corría al volver, y la versión actual ya no lo detalla. Decirlo como cuidado práctico con esa atribución, nunca como spec vigente. Las laptops se suspenden solas; revisar la configuración de energía si el resumen de las 8:00 nunca aparece. Cerrar con la excepción que sobrevive incluso con nube: una tarea que necesita archivos o apps locales corre local siempre. Eso anticipa la segunda clase, donde Cowork trabaja sobre carpetas y archivos reales. Antes de confiarle el reporte del lunes a una tarea, contestar "¿dónde corre esto?". Aviso de vigencia: la nube es beta con rollout gradual desde el 7 de julio de 2026; re-verificar el estado del rollout el día de la clase, porque es el dato más probable de haber cambiado. Tiempo objetivo: ~3 min.

### Presenter feedback

---

# 5. La misión · parte 1

**Goal of this section:** Primera de las dos placas de misión. Presenta a Faro, el analista de mercado virtual de Atlas, y manda a resolver la parte 1 con lo ya visto: el chat, los conectores y Schedule. Sin contenido nuevo.

**Presenter feedback:**

---

## 1. La misión, parte 1: Faro en el chat

### Content

```ascii
   ______________________________________________
  |                                              |
  |   LA MISION - PARTE 1                        |
  |                                              |
  |   FARO EN EL CHAT                            |
  |   el analista de mercado de Atlas            |
  |                                              |
  |   con lo visto: conectores + Schedule        |
  |______________________________________________|
```
<!-- ascii-note:
intent: primera placa divisoria de misión. Cartel, no diagrama de flujo: presenta a Faro y manda a resolver la parte 1 con las piezas que ya se enseñaron (chat, conectores, Schedule).
emphasize: "LA MISION - PARTE 1" arriba y "FARO EN EL CHAT" en el centro, en el tipo más grande de la placa.
labels: arriba = LA MISION, PARTE 1; centro = FARO EN EL CHAT (el analista de mercado de Atlas); abajo = con lo visto, conectores y Schedule.
-->

- **Faro** es el analista de mercado virtual de Atlas: sigue la actualidad del sector, arma un reporte semanal y lo deja listo para la reunión del lunes.
- **Parte 1, en el chat que ya usan:** el correo semanal llega solo al inbox del jefe, con conectores y Schedule.
- Nadie escribe código. Se arma combinando piezas.

### Sources

- "corpus/mision - auto.zip.md", la misión completa de punta a punta: el analista virtual, el reporte semanal y el borrador de correo antes de la reunión.
- `missions/CoWork/mission.md`, tabla "Las dos partes": parte 1 en claude.ai (conectores y tareas programadas), parte 2 en Cowork.

### Speaker notes

Primera placa de misión, corta. Hasta acá se vieron capacidades sueltas: conectores, capacidad ejecutiva, Schedule, todo dentro del chat que la audiencia ya tiene y sin instalar nada. Esta slide le pone un destino concreto a lo aprendido. Presentar a Faro en dos frases: el analista de mercado virtual de Atlas, que sigue la actualidad del sector, consolida un reporte semanal y deja el borrador de correo listo antes de la reunión del lunes. Decir con qué se resuelve la parte 1: solo con el chat, los conectores y Schedule, sin instalar nada. Aclarar que la parte 2 se resuelve en la segunda clase, ya en Cowork, y que no depende de esta. Dejar la consigna de la parte 1 y anunciar que la próxima arranca con Cowork instalado. Después de esta placa queda la lámina de cierre, así que no cerrar del todo acá: esta fija el destino, y la siguiente dice qué hacer el lunes con lo visto. Tiempo objetivo: ~2 min.

### Presenter feedback

---

# Conclusions

## 1. El lunes: qué hacer con esto

### Content

- **El chat consulta información actual y ejecuta acciones sobre el mail y la agenda.** Alcanza con configurar la cuenta que ya está en uso, sin instalar nada ni escribir código.
- **Para esta semana:** activar la búsqueda, conectar el mail y la agenda, y dejar programado un trabajo recurrente.
- **Ninguna acción que importe se ejecuta sin aprobación humana.** Anthropic documenta el prompt injection como riesgo abierto y aclara que no es cero.
- **La segunda clase** retoma este chat extendido y sigue en **Claude Cowork**, donde el agente trabaja sobre carpetas y archivos del usuario.

### Sources

- (slide de cierre: recapitulación de material ya presentado. Cada afirmación está sourceada en su slide de origen, en las secciones 2, 3, 4 y 5. Sin claims nuevos de producto.)

### Speaker notes

Cierre de la clase. La audiencia acaba de ver todo el material, así que esta lámina no vuelve sobre el temario: contesta qué hacer con lo visto. Bajar el ritmo y darle una frase a cada bullet.

Primero, la idea que se llevan: el chat que ya usan todos los días consulta información actual y ejecuta acciones sobre el mail y la agenda, y eso se resuelve con configuración, sin instalar nada ni escribir código. Es el punto que ordena los otros tres.

Después, lo concreto para esta semana: activar la búsqueda, conectar mail y calendario y dejar una tarea programada corriendo. Se puede tener andando con la cuenta que ya tienen, y si se van con una sola cosa hecha, que sea esta.

La advertencia va acá y es la última palabra sobre el tema, no un bullet enterrado: el humano aprueba antes de que se ejecute algo que importa, y el prompt injection es un riesgo abierto que el propio Anthropic documenta y no da por resuelto. Volver un momento a la lámina 3.6 si alguien pide detalle.

Cerrar con el puente: la parte 1 de Faro se resuelve con esto, dentro del chat, y la próxima clase arranca con Claude Cowork instalado, ya sobre carpetas y archivos. Dejar la consigna clara antes de abrir Q&A. Tiempo objetivo: ~3 min.

### Presenter feedback

---

# Open questions

- ~~Fecha de la clase sin confirmar~~; resuelto 2026-07-14: `date: Julio 2026`.
- **Duración de esta clase sin confirmar (2026-07-31):** el frontmatter dice `60 min (a confirmar)`. La suma de los "Tiempo objetivo" de las 19 slides da ~53 min sin Q&A ni pausa (actualizado 2026-07-31 con la slide de cierre); confirmar con el presentador el bloque real y ajustar el frontmatter.
- Vigencia de features vs docs oficiales: fechas y versiones citadas (nube de Schedule beta desde el 7 de julio de 2026, planes pagos de Claude in Chrome, disponibilidad del directorio de conectores) son point-in-time; re-verificar contra docs oficiales antes de presentar.
- URL externa a re-verificar en Polish si se quiere snapshot o cita estable: support.claude.com `13854387-schedule-recurring-tasks-in-claude-cowork` (citada en las dos slides de la sección 4).
- ~~URLs nuevas de round 4~~; **RESUELTO en round 5 (2026-07-09):** las 6 citas se verificaron online. Resultados: web search 10684626 OK; ChatGPT search 9237897 OK (existencia+contenido corroborados vía búsqueda; el fetch directo da 403 por bloqueo anti-bot de help.openai.com); ChatGPT tasks OK con slug canónico corregido a `10291617-tasks-in-chatgpt`; directorio de conectores: claude.ai/directory requiere login → cita reemplazada por el anuncio oficial claude.com/blog/connectors-directory + support 11176164; custom connectors 11175166 OK; modelcontextprotocol.io OK.
- ~~Tareas programadas en el chat de Claude~~; **RESUELTO en round 5:** claude.ai SÍ tiene tareas programadas en el navegador (observación de primera mano del presentador 2026-07-09 + release notes del 7 de julio de 2026, support article 12138966: corren en la nube sin dispositivo online, beta, rollout Max-first). Slide 4.1 actualizada con Claude como ejemplo de primera clase.
- **Capacidad ejecutiva por conector (slide 3.2), estado por acción:** Gmail-borrador verificado (corpus/misión); **Calendar-agendar VERIFICADO por el presentador (2026-07-09)**; tickets (Jira/ServiceNow) y mensajes (Slack) siguen presentados como capacidad del ecosistema (MCP/conectores lo permiten; fuentes oficiales citadas) sin verificación por conector puntual; no prometer demos en vivo de esos dos sin chequear antes.
- Claim "búsqueda web integrada en casi todos los chats" (slide 3.3): verificado citable para Claude y ChatGPT; Gemini se menciona de pasada sin fuente propia; agregar fuente oficial de Google o suavizar la mención al presentar.
- **Asides generados sin renderizar (slides 1.1 y 1.2):** las dos directivas `<!-- generate-image: ... -->` siguen sin imagen. La sesión que corrió el último Polish no tenía capacidad de generación de imágenes. Re-correr el paso de image-illustrator en una sesión que sí la tenga, o borrar las directivas.
- **Split del 2026-07-31:** esta clase salió de partir en dos el Talk combinado de 120 min. La parte 2 (Cowork, .md, Projects, Skills, Subagentes, la placa de misión parte 2 y las Conclusions) vive en `talks/claude-cowork/`. Las open questions de esas piezas quedaron allá; si una decisión de esta clase afecta a la otra, sincronizar a mano.

# Cut material

- **Detalles internos de Claude Code** (Plan mode, slash commands completos, project-directory skills, config de `/agents`, dynamic workflows, las dos misiones hands-on basadas en Code, árboles `~/.claude/...`): fuera de foco por diseño de esta charla (companion funcional/alto nivel). Claude Code aparece solo como contraste en la slide 1.4 "Las cuatro herramientas de Claude". Fuente: corpus/agentic-ai-deck.zip.md (Code-related slides preservadas pero marcadas fuera de foco).
- **Detalle mecánico del Schedule de Cowork** (round 4, al adelgazar la ex-slide 4.3 por decisión C2): los sub-bullets "Describís la tarea una vez; Claude guarda el prompt como las instrucciones de la tarea" y "Tiene los mismos poderes que una tarea normal: connectors, skills, plugins instalados", y el aparte explícito sobre agentes programados alojados en la nube como funcionalidad separada (conservado solo en Speaker notes). El concepto general de tarea programada se enseña en la sección 4, desde el chat. La slide de Schedule en Cowork salió del deck por decisión del presentador (2026-07-30). Fuente: draft round 3, slide 4.3 "Schedule: que Cowork trabaje solo".
- **Contenido de la parte 2 (split del 2026-07-31):** Cowork, los archivos .md, Projects, Skills, Subagentes, la placa de misión parte 2 y las Conclusions no se cortaron, se mudaron a `talks/claude-cowork/`. Su material cortado y sus open questions viajaron con ellas.
