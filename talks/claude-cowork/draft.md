---
presentation: "Agentes Inteligentes — Master in Management (MiM), IAE Business School"
class: "Claude Cowork"
research: research/corpus/
description: Slides are grouped into Sections. Each Section contains one or more Slides.
presenter: Paulo Veiga y Marco Sánchez Sorondo
audience: Estudiantes del Master in Management (MiM), IAE Business School. Perfil de gestión y negocios, mayormente no técnico; poca exposición previa a agentes de IA.
duration: 60 min (a confirmar)
date: Julio 2026
---

# Thesis

**Claim:** En la clase anterior el chat quedó extendido: conectores para que vea el mundo real y Schedule para que trabaje solo. Esta clase da el salto siguiente, Claude Cowork, donde ese mismo agente baja a la computadora y trabaja sobre carpetas y archivos reales. Eso cambia la forma de trabajar: el usuario delega resultados completos combinando sus piezas (archivos `.md`, Projects, Instrucciones, Skills y Subagentes) sin escribir una línea de código.

**Why it matters:** Un agente se vuelve útil en el trabajo real cuando se le delega un resultado y se guía su proceso, en vez de chatearle un mensaje por vez. Quien domina esa forma de delegar automatiza horas de trabajo manual con la barrera de entrada en cero. La clase asume el chat extendido como punto de partida y no vuelve sobre él: arranca donde terminó la anterior.

**Presenter feedback:**

---

# Agenda

**Narrative arc:** La clase arranca donde terminó la anterior, con el chat ya extendido por conectores y Schedule, y da el salto grande de una: Claude Cowork instalado en la computadora, trabajando sobre carpetas y archivos reales. La primera sección ubica ese salto: Cowork como herramienta de propósito general del knowledge worker, la analogía de la nueva habilidad base de oficina, el cambio de rol de chatear a delegar un resultado, el mapa de piezas que se apilan y el primer contacto con la interfaz sobre la app (1). De ahí las piezas se recorren una por una, en el orden en que se apilan. Los archivos `.md` primero, porque son el formato en el que la IA lee, edita y entrega: cómo se escriben, cómo se ven una vez formateados y el hábito de trabajar en `.md` y exportar recién al final (2). Después el espacio de trabajo: qué agrupa un Project, cómo se le concede una carpeta real del disco con el explorador del sistema, dónde vive su contexto y cómo las Instrucciones fijan de una vez el comportamiento del agente adentro de ese espacio (3). Con el espacio armado llegan las Skills, la forma de enseñar una tarea una sola vez: qué es una Skill, sus dos caminos de creación (el panel de Habilidades y el chat con `/skill-creator`, con la trampa del Save) y la anatomía del `SKILL.md` (4). La última pieza, ya de nivel avanzado, son los Subagentes: para qué tipo de sub-tarea conviene delegar en paralelo y cómo aparecen en Cowork, coordinados por debajo y sin panel propio (5). Una placa divisoria manda a resolver la parte 2 de la misión de Faro, el analista de mercado virtual de Atlas, ya en Cowork y sobre la carpeta real del equipo, sin exigir la parte 1 resuelta (6). El cierre abre con un repaso de lo que se vio, las piezas de la clase y la idea de que se combinan según lo que pida cada trabajo; después recorre el loop completo de Faro, que engancha las piezas de las dos clases, y termina en las advertencias de gobernanza antes de Q&A.

**Sections (in delivery order):**

- 1. Claude Cowork
- 2. Knowledge & Output
- 3. Projects
- 4. Skills
- 5. Subagentes
- 6. La misión · parte 2

**Presenter feedback:**

---

# 1. Claude Cowork

**Goal of this section:** El salto grande de la charla. Cowork es Claude instalado en la computadora, trabajando sobre carpetas y archivos reales; eso cambia la forma de trabajar. Ubica el superpoder de Cowork como herramienta de propósito general, el paso de chatear a delegar resultados, el mapa de piezas que se apilan y el primer contacto con la interfaz.

**Presenter feedback:**

---

## 1. Cowork, de propósito general

### Content

- Cowork = Claude instalado en la computadora, trabajando sobre las carpetas y archivos del usuario. **Eso cambia la forma de trabajar.**
- La **herramienta de propósito general del knowledge worker**. El "lenguaje de programación" es el español.
- Anthropic: **"Claude Code para el resto de tu trabajo"**.

<!-- generate-image: right | el salto de escala del trabajo de oficina cuando la herramienta deja de ser un accesorio y pasa a ser la base -->

### Sources

- corpus/agentic-ai-deck.zip.md, posicionamiento Cowork vs Claude Code ("Same engine. Different surface."; Cowork = la cara para knowledge workers sin terminal; slide 7.1 "Claude Code vs Cowork — the close").
- Anthropic, Claude Cowork (product page): https://www.anthropic.com/product/claude-cowork; encuadre oficial: Cowork como "Claude Code para el resto de tu trabajo"; construido sobre las mismas bases que Claude Code.
- Claude blog, Cowork research preview ("Claude Code power for knowledge work"): https://claude.com/blog/cowork-research-preview; la ambición de llevar el poder de Claude Code al trabajo del conocimiento; Cowork generaliza un éxito probado primero con developers.
- CNBC, Anthropic's Claude Cowork targets the office worker: https://www.cnbc.com/2026/02/24/anthropic-claude-cowork-office-worker.html; encuadre de público general / office worker.

### Speaker notes

El beat de "¿y a mí por qué me importa?". Cowork es Claude instalado en la computadora, con acceso a las carpetas y archivos del usuario; eso habilita una forma de trabajar distinta de la del chat. En la clase anterior la audiencia extendió un chat; esta slide anuncia otra categoría de herramienta. Tono motivacional y de alto nivel; la mecánica viene después.

Lo que sí es de Anthropic, y conviene citarlo como su framing propio, es "Claude Code para el resto de tu trabajo": que cualquier knowledge worker sienta con Cowork lo que los ingenieros ya sienten con Claude Code. Cowork generaliza algo que ya funcionó primero con developers.

Aterrizarlo en la audiencia: son alumnos de management y la mayoría no programa; por eso Cowork les sirve. La analogía que engancha viene en la lámina siguiente. Tiempo objetivo: ~2 min.

### Presenter feedback

---

## 2. La nueva habilidad base

### Content

- Hay analistas que llaman a las herramientas agénticas **"el nuevo Excel"**: la nueva habilidad base del trabajo de oficina. La analogía es de analistas y de la industria, no de Anthropic.
- Lo que Excel fue para la planilla, estas herramientas lo son para el trabajo completo: se opera en español y no hace falta escribir código.

```ascii
TRABAJO DE OFICINA: la herramienta de proposito general

 ~40 anios                              ahora
+----------------------+    ===>    +-----------------------------+
| EXCEL                |            | HERRAMIENTAS AGENTICAS      |
| lingua franca del    |            | Claude Code  (developers)   |
| trabajo de oficina   |            | Cowork       (knowledge     |
| (sin escribir codigo)|            |               worker)       |
+----------------------+            +-----------------------------+
 la habilidad base de ayer           la nueva habilidad base
```
<!-- ascii-note:
intent: encuadrar el "superpoder" de Cowork como herramienta de propósito general del knowledge worker, usando la analogía Excel (40 años, habilidad base de oficina) -> herramientas agénticas (Claude Code para developers, Cowork para knowledge workers) como la nueva habilidad base.
emphasize: la flecha temporal de Excel (ayer) a las herramientas agénticas (ahora); el paralelo Claude Code=developers / Cowork=knowledge worker; que la analogía Excel es encuadre de industria, no claim oficial.
labels: dos cajas; EXCEL (lingua franca, sin escribir código) a la izquierda; HERRAMIENTAS AGENTICAS (Claude Code = developers, Cowork = knowledge worker) a la derecha; pie "habilidad base de ayer" -> "nueva habilidad base".
-->

### Sources

- corpus/agentic-ai-deck.zip.md, posicionamiento Cowork vs Claude Code ("Same engine. Different surface."; Cowork = la cara para knowledge workers sin terminal; slide 7.1 "Claude Code vs Cowork — the close").
- Anthropic, Claude Cowork (product page): https://www.anthropic.com/product/claude-cowork; encuadre oficial: Cowork como "Claude Code para el resto de tu trabajo"; construido sobre las mismas bases que Claude Code.
- Claude blog, Cowork research preview ("Claude Code power for knowledge work"): https://claude.com/blog/cowork-research-preview; la ambición de llevar el poder de Claude Code al trabajo del conocimiento; Cowork generaliza un éxito probado primero con developers.
- CNBC, Anthropic's Claude Cowork targets the office worker: https://www.cnbc.com/2026/02/24/anthropic-claude-cowork-office-worker.html; encuadre de público general / office worker.
- "Claude Code is the New Excel" (ensayo de analista): https://nextword.substack.com/p/claude-code-is-the-new-excel; origen de la analogía del "nuevo Excel" (atribuir AQUÍ, NO a Anthropic).

### Speaker notes

El gancho que mejor funciona es la analogía del Excel, dicha con cuidado: durante unas cuatro décadas, Excel fue la habilidad base del trabajo de oficina. La tesis de varios analistas es que las herramientas agénticas (Claude Code para quien programa, Cowork para quien no) van camino a ese lugar — atribuido a analistas e industria, "hay quien lo llama el nuevo Excel", NO a Anthropic. Lo que sí es de Anthropic es "Claude Code para el resto de tu trabajo": que cualquier knowledge worker sienta con Cowork lo que los ingenieros sienten con Claude Code. Cerrar aterrizándolo en la audiencia: alumnos de management, la mayoría no programa. Después de este beat pasamos a la mecánica, cómo se delega. Tiempo objetivo: ~3 min.

### Presenter feedback

---

## 3. De chatear a delegar

### Content

- El chat quedó extendido en la clase anterior. Lo que cambia ahora es el rol: **delegar**.
- Ejemplo de delegación: *"armá el pulso semanal de YPF, Vista y Tenaris con el formato del reporte de ejemplo y dejalo en la carpeta"*. Un resultado completo, no un mensaje por vez.
- Anthropic: *"menos una sesión de chat, más asignarle tareas a un colega."*
- Chatear vs delegar:

| | Chatear | Delegar a un agente |
|---|---|---|
| La forma de trabajo | Un mensaje a la vez | Se describe un resultado |
| Los pasos | Los hace la persona | El agente planifica y ejecuta |
| La salida | Texto en la ventana | Archivos en el disco |
| El rol humano | Hacer cada paso intermedio | Revisar el plan y corregir el rumbo |

```ascii
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

### Sources

- corpus/agentic-ai-deck.zip.md, "Stop prompting. Start delegating." (slide 2.3 the reframe); tabla "Chatting vs Delegating" (slide 3.16).
- "corpus/mision - auto.zip.md", "el verdadero premio no es Atlas: sos vos, dominando Claude Cowork"; "Conversá, no programes."
- Anthropic, Claude Cowork (product page): https://www.anthropic.com/product/claude-cowork; refuerza el paradigma: trabajar con Cowork "se parece menos a una sesión de chat y más a asignarle tareas a un colega".
- (técnico, opcional) Anthropic Engineering, Building agents with the Claude Agent SDK: https://www.anthropic.com/engineering/building-agents-with-the-claude-agent-sdk; por qué el loop plan→ejecutar→guiar define a un agente frente a un chat.

### Speaker notes

El concepto-ancla de la charla. En la clase anterior, los conectores y Schedule extendieron qué puede hacer el chat; el agente cambia tu rol: en vez de pedir un paso intermedio, se describe un resultado completo que el agente planifica y ejecuta sobre archivos reales mientras vos supervisás. Si se llevan una sola idea, que sea esta: el valor está en aprender a delegar un resultado y guiar el proceso. Usar la tabla para hacerlo concreto: la salida son archivos en el disco, no texto en una ventana. Anticipar la misión: vamos a "contratar" a Faro y entrenarlo una vez para que después trabaje solo. Cerrar citando a Anthropic: "menos una sesión de chat, más asignarle tareas a un colega". Tiempo objetivo: ~4 min.

### Presenter feedback

---

## 4. El mapa: piezas que se apilan

### Content

- **Bloques que se apilan**: cada tarea combina solo los bloques que necesita.
- El mapa de las dos clases: abajo lo de la clase anterior, arriba lo que queda por recorrer.
- Cada bloque = un problema conocido:

```ascii
   +----------------------+  "quiero delegar en paralelo"
   | SUBAGENTES           |
   +----------------------+
   +----------------------+  "no quiero repetir la tarea"
   | SKILLS               |
   +----------------------+
   +----------------------+  "no quiero repetir el contexto"
   | INSTRUCCIONES        |
   +----------------------+
   +----------------------+  "agrupar el trabajo de un tema"
   | PROJECTS             |
   +----------------------+
   +----------------------+  "quiero que la IA entienda mi material"
   | ARCHIVOS .MD         |
   +----------------------+
   +----------------------+  "quiero que trabaje sobre mis archivos"   <== ACA
   | COWORK: carpetas     |
   +----------------------+
   +----------------------+  "quiero que corra solo"                   (visto)
   | SCHEDULE             |
   +----------------------+
   +----------------------+  "quiero info real + que actue"            (visto)
   | CONECTORES           |
   +----------------------+
   +----------------------+  "respondia solo de memoria"               (visto)
   | EL CHAT              |
   +----------------------+

   los bloques se apilan: cada tarea combina solo los que necesita
```
<!-- ascii-note:
intent: presentar el arco completo de las dos clases como bloques que se apilan (no una pirámide/escalera estricta): el chat (base) -> conectores -> Schedule -> Cowork (carpetas/archivos) -> archivos .md -> Projects -> Instrucciones -> Skills -> Subagentes. Los tres bloques de abajo son los de la clase anterior y están marcados "(visto)"; el bloque Cowork lleva el marcador "estamos acá".
emphasize: el marcador "<== ACÁ" en el bloque Cowork; los "(visto)" en chat/conectores/Schedule, que son de la clase anterior; el par bloque↔problema en cada nivel.
labels: bloques apilados (base→cima): El chat · Conectores · Schedule · Cowork: carpetas · Archivos .md · Projects · Instrucciones · Skills · Subagentes, cada uno con su frase-problema a la derecha.
-->

### Sources

- corpus/agentic-ai-deck.zip.md, progresión de building blocks del deck (Instrucciones → Projects → Skills → Connectors/MCP); la idea de "pila" es la lectura ordenada de esa progresión, re-secuenciada al arco chat-primero de esta charla.
- "corpus/mision - auto.zip.md", la misión Atlas arma estas piezas una por una.

### Speaker notes

El mapa del arco completo, que empieza antes de esta clase: la base es el chat que la audiencia ya usa. Leer el diagrama, no la lámina: cada bloque va con su frase-problema al lado y esa es la lectura en voz alta. De abajo hacia arriba, los tres que trajimos de la clase anterior: el chat respondía solo de memoria, los conectores traen información real y actúan, Schedule hace que corra solo. Un repaso de una línea por bloque alcanza; no volver a enseñarlos. Señalar "estamos acá": Cowork, donde la IA empieza a trabajar sobre carpetas y archivos reales. Los cinco de arriba son el roadmap de esta clase y cada uno tiene su sección: archivos `.md` para que la IA entienda el material (sección 2), Projects para agrupar el trabajo de un tema e Instrucciones para no repetir el contexto (sección 3), Skills para no repetir la tarea (sección 4) y Subagentes para delegar en paralelo (sección 5). Cuidado con la metáfora: los bloques se apilan y se combinan, cada tarea usa solo los que necesita. Decir que pueden volver a esta slide entre secciones para ubicarse. Al final, la pila entera es Faro. Tiempo objetivo: ~3 min.

### Presenter feedback

---

## 5. Demo: la interfaz de Cowork

### Content

```ascii
   __________________________________________
  /                                          /|
 /            >   D E M O   T I M E          / |
/__________________________________________/  |
|                                          |   |
|     [ Pasamos a la app de Cowork ]       |  /
|__________________________________________| /
|__________________________________________|/
```
<!-- ascii-note:
intent: tarjeta/banner de "DEMO TIME" como señal visual fuerte al tope de la slide, para marcar el corte de conceptos a demo en vivo sobre la app.
emphasize: el texto grande "> DEMO TIME"; sensación de cartel/placa (no un diagrama de flujo); que abajo se lee "pasamos a la app de Cowork".
labels: banner DEMO TIME; subtítulo "Pasamos a la app de Cowork".
-->

- **DEMO EN VIVO**: tour de la pestaña Cowork sobre la app.

![Anatomía de la pestaña Cowork (interfaz anotada)](images/screenshot-cowork-tab.png)

- Señalar en vivo: modo **"Ask"** vs modo automático, selector de carpeta, panel de **Project**.
- Control = modo + aprobar/redirigir + carpeta.

### Sources

- corpus/agentic-ai-deck.zip.md, "screenshot-cowork-tab.png" (anatomía Cowork, 14 elementos anotados; el asset más Cowork-funcional de la fuente); slide 3.19 (modelo de aprobación Cowork).

### Speaker notes

Momento de demo en vivo, de los conceptos a la app. Abrir Cowork y recorrer 2 minutos señalando el selector de modo (Ask before acting por defecto), cómo se concede una carpeta y dónde vive el panel de Project. La barra lateral tiene otras pestañas que esta clase no cubre; mencionarlas al pasar si preguntan. Demo sugerida: la carpeta `missions/CoWork/escritorio-del-pasante/` (Misión 0): conceder la carpeta, pedir "¿qué hay acá y en qué estado está?" y un ordenamiento con renombres, aprobando cada acción (ejercicios 1 y 2 de intro-escritorio-pasante.md; 3 a 5 quedan para el workshop). Dejarlos ver a Claude planificar, tocar archivos y entregar, sin explicar la mecánica todavía. La carpeta es regenerable por script; la imagen anotada queda de respaldo si la demo falla. Tiempo objetivo: ~6 min (incluida la demo).

### Presenter feedback

---

# 2. Knowledge & Output

**Goal of this section:** El rol central de los archivos .md en el trabajo con Cowork: cómo se escriben, cómo se ven una vez formateados y por qué conviene trabajar en ese formato y exportar al final al que pida el destinatario.

**Presenter feedback:**

---

## 1. Cómo se escribe un .md

### Content

- Un `.md` (Markdown) = **texto plano** + marcas de estructura: `#` para títulos, `-` para listas, `**negrita**`, `|` para tablas.
- Un archivo de la misión, tal como se escribe:

```markdown
# Pulso semanal de mercado
Semana 2026-05-18 · YPF · Vista · Tenaris

## Resumen
- YPF **sube 3,1%** tras el anuncio de perforación.
- Vista presenta resultados el jueves.

| Empresa | Cierre | Variación |
|---------|--------|-----------|
| YPF     | $42,10 | +3,1%     |
```

- Se escribe y se lee con cualquier editor de texto. La IA está entrenada para comprender su estructura.

### Sources

- corpus/agentic-ai-deck.zip.md, "Markdown is the lingua franca".
- "corpus/mision - auto.zip.md", el reporte semanal de la misión como archivo `.md` (formato del reporte de ejemplo).

### Speaker notes

Beat de enseñanza propio, no un paréntesis: en el mundo de agentes el formato de los archivos importa, y gana el más simple. Esta slide muestra la sintaxis con un archivo real de la misión: un `#` marca el título, `##` un subtítulo, `-` una viñeta, los asteriscos la negrita y las barras verticales una tabla. Recorrerla rápido, sin detenerse en detalle fino de formato: la idea es que las marcas son pocas y se aprenden en minutos. Señalar que es texto plano, sin formato propietario: se abre con cualquier editor, en cualquier computadora. La próxima slide muestra el mismo archivo renderizado. Tiempo objetivo: ~3 min.

### Presenter feedback

---

## 2. El mismo archivo, ya formateado

### Content

- El mismo texto, abierto en cualquier visor de Markdown:

```ascii
+------------------------------------------------+
|  PULSO SEMANAL DE MERCADO                      |  <- "#" = titulo
|  Semana 2026-05-18 · YPF · Vista · Tenaris     |
|                                                |
|  Resumen                                       |  <- "##" = subtitulo
|   • YPF sube 3,1% tras el anuncio de           |  <- "-" = viñeta
|     perforacion.        (** = negrita)         |
|   • Vista presenta resultados el jueves.       |
|                                                |
|  +---------+--------+-----------+              |
|  | Empresa | Cierre | Variacion |              |  <- "|" = tabla
|  | YPF     | $42,10 | +3,1%     |              |
|  +---------+--------+-----------+              |
+------------------------------------------------+
```
<!-- ascii-note:
intent: mostrar el archivo .md de la slide anterior ya renderizado (título grande, subtítulo, viñetas, negrita, tabla con bordes), con flechas laterales que conectan cada elemento visual con la marca de sintaxis que lo produce.
emphasize: la correspondencia marca -> resultado (# -> título, - -> viñeta, ** -> negrita, | -> tabla); que es el MISMO archivo de la slide anterior.
labels: documento renderizado a la izquierda; a la derecha, la marca de sintaxis que genera cada elemento.
-->

- Las marcas se convierten en formato: títulos, viñetas, negrita, tabla.
- **Metadata (header YAML)**: declara *qué es* el archivo y *cuándo* usarlo. Vuelve con las Skills (sección 4).
- La **lingua franca** del mundo LLM: el modelo lee texto. Portable y versionable.

### Sources

- corpus/agentic-ai-deck.zip.md, "Markdown is the lingua franca"; definición de Skill (SKILL.md con YAML frontmatter: name + description; "Description drives triggering — semantic, not keyword").
- "corpus/mision - auto.zip.md", "mismo estándar SKILL.md" entre Cowork y Codex (Cowork vs Codex).

### Speaker notes

El remate del par: el archivo de la slide anterior, ahora formateado. Recorrer la correspondencia con el diagrama: el `#` se volvió título, los `-` viñetas, los asteriscos negrita, las barras una tabla con bordes. Si hay conexión, mejor en vivo: abrir el archivo en un visor de Markdown y alternar entre fuente y render. La idea a transmitir: el modelo lee texto, y cuanto menos formato opaco haya entre el contenido y el modelo, mejor trabaja. Por eso es portable y versionable; el mismo estándar funciona entre herramientas. Presentar la metadata (header YAML entre `---`) como la etiqueta del frasco: dice qué es el archivo y cuándo usarlo. La `description` de una Skill cumple esa función (activación semántica, no por palabra clave; sección 4). La próxima slide baja esto a la práctica: en qué formato conviene trabajar. Tiempo objetivo: ~3 min.

### Presenter feedback

---

## 3. Trabajar en .md, exportar al final

### Content

- La IA **interpreta, edita y crea mejor sobre `.md`** que sobre .docx/.xlsx.
- Aplica tanto a la **memoria** del agente como a los **archivos de trabajo** del Project.
- Regla de bolsillo: *se edita en `.md` y se entrega en el formato que pida el jefe.*
- En la misión: el reporte se consolida como `.md` en el Project; el mail y el tablero se generan al final.

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

- corpus/agentic-ai-deck.zip.md, "Markdown is the lingua franca" (la configuración y el material del mundo LLM es texto plano; el modelo lee texto).
- "corpus/mision - auto.zip.md", el flujo de Atlas trabaja sobre archivos `.md` en el Project (reporte `.md` consolidado) y el entregable final se genera al último (borrador de mail, tablero).

### Speaker notes

La slide de práctica de la sección, el hábito concreto que se llevan. La analogía útil: el `.md` es tu mesa de trabajo y el `.docx`/PDF es la vitrina. Nadie construye dentro de la vitrina. El porqué, para decir: en texto plano la IA ve la estructura directa; en formatos ricos atraviesa capas que agregan ruido y errores. Recorrer el flujo con el diagrama, que es lo que la lámina ya no dice en texto: las tres etapas se leen ahí. Llega material en cualquier formato (.docx, PDF, mails, páginas web) y el primer pedido al agente es "convertime esto a `.md`". Mientras el trabajo sigue abierto, toda la información vive en `.md`: las idas y vueltas (resumir, corregir, reescribir, fusionar) pasan por ahí, donde la IA es más precisa y barata de iterar. El entregable (.docx, .xlsx, PDF, slides) se genera **una sola vez**, recién cuando el trabajo está listo: un único pedido final, "generame el entregable". El documento "lindo" es la salida, no el medio de trabajo. Aplica a la memoria también: lo que el agente debe recordar de forma estable vive como texto plano (Instrucciones, memoria del Project), y los archivos que va a leer y editar una y otra vez (notas, borradores, datos de referencia) van en `.md` dentro de la carpeta del Project. Aterrizar con Faro: su reporte se consolida como `.md` en el Project y las salidas "lindas" (mail, tablero) se generan al final. Ese es el mecanismo que la placa de la misión (6.1) da por enseñado cuando nombra el entregable para el jefe. Tiempo objetivo: ~4 min.

### Presenter feedback

---

# 3. Projects

**Goal of this section:** El espacio de trabajo de Cowork: qué agrupa un Project, cómo se le concede una carpeta real del disco, dónde vive su contexto y cómo las Instrucciones fijan de una vez el comportamiento del agente en ese espacio.

**Presenter feedback:**

---

## 1. Qué es un Project

### Content

- Project = espacio de trabajo autocontenido: **carpeta propia + memoria + instrucciones**.
- El de la misión: **"Inteligencia de Mercado Semanal"**, apuntado a la carpeta `Documentos/Faro-Mercado`.
- Tres capas persistentes: Instrucciones · Knowledge base · Chats.
- Los chats del Project **no comparten contexto entre sí** (solo la base de conocimiento).

### Sources

- corpus/agentic-ai-deck.zip.md, definición de "Project (Chat/Cowork)" (tres capas; chats no comparten contexto); "Working directory + permissions" (folder picker del sistema).
- "corpus/mision - auto.zip.md", "el Proyecto le da a Atlas una carpeta propia, memoria y un lugar fijo" (Step 1.1).

### Speaker notes

El Project es el contenedor de todo lo demás: Instrucciones, archivos, memoria. Todo queda organizado y reutilizable: las Instrucciones valen para todo el Project, la memoria recuerda preferencias, los archivos viven en una carpeta concreta del disco. En la misión, el Project "Inteligencia de Mercado Semanal" apunta a `Documentos/Faro-Mercado`. Un punto práctico que sorprende: los chats no comparten contexto entre sí, solo las Instrucciones y la base de conocimiento. La carpeta se concede con el explorador de archivos del sistema, garantía de seguridad y límite a la vez, y la slide siguiente lo muestra en pantalla, así que acá solo anticiparlo. Tiempo objetivo: ~3 min.

### Presenter feedback

---

## 2. Conceder una carpeta y ver el contexto

### Content

- El usuario concede la carpeta con el **explorador de archivos del sistema**. Cowork no tiene acceso a nada fuera de ella salvo que le permitamos hacerlo.

![Selector de carpeta de trabajo del Project](images/project.png)

- El **panel de contexto**: Instrucciones + base de conocimiento + carpeta concedida.

![Panel de contexto del Project](images/context.png)

- Seguridad: la carpeta ES el control de privacidad. **Nunca datos sensibles, credenciales o NDA.**

### Sources

- corpus/agentic-ai-deck.zip.md, "Working directory + permissions" (folder picker del sistema; lo concedido define el alcance); definición del panel de contexto del Project.
- "corpus/mision - auto.zip.md", el Project "Inteligencia de Mercado Semanal" apunta a `Documentos/Faro-Mercado` (Step 1.1).

### Speaker notes

Slide de apoyo visual: mostrar las dos capturas, el explorador de archivos al conceder una carpeta y el panel de contexto del Project. Mensaje de seguridad: Cowork solo ve lo que le concedés, así que la carpeta ES el control de privacidad, nunca datos sensibles. De ahí la buena práctica que conviene decir en voz alta: usar una carpeta dedicada al trabajo del Project y revisar antes que no tenga adentro nada confidencial. Faro trabaja sobre `Documentos/Faro-Mercado`, nada más. Tiempo objetivo: ~2 min.

### Presenter feedback

---

## 3. Instrucciones: el contrato de trabajo

### Content

- Instrucciones = el **"contrato de trabajo"**: reglas en lenguaje natural que aplican a todo el Project.
- Ejemplo (Faro):

<!-- ascii-render: documentation-only -->
```text
Sos Faro, el analista de mercado de Atlas, una empresa de
insumos de perforación para Vaca Muerta.
Preparás un pulso semanal para colegas NO técnicos (incluido el jefe),
que se lee en 2 minutos antes de la reunión de los lunes.

· Empresas que seguís: YPF, Vista y Tenaris.
· Escribís en español, claro y breve, sin jerga financiera.
  Si usás un término técnico, lo explicás en una línea.
· REGLA DE ORO: tus reportes son informativos y de uso interno.
  NUNCA son recomendaciones de inversión ni asesoramiento financiero.
  Siempre incluís esa aclaración al final.
```

  Se escriben una sola vez.
- Conviene que sean cortas y claras.
- El lugar de las **reglas no negociables**.

### Sources

- corpus/agentic-ai-deck.zip.md, "the project context panel (GUI)" como lugar de las Instrucciones en Cowork; matriz de disponibilidad 3.3 (Persistent instructions, Cowork ⚠️).
- "corpus/mision - auto.zip.md", texto exacto de las Project Instructions de Atlas (Step 1.1); "las Instrucciones son su contrato de trabajo".

### Speaker notes

En lugar de re-explicarle el contexto a Claude cada vez, se escribe una vez en las Instrucciones y queda fijo. Mostrar el texto real de Faro y destacar la regla de oro del disclaimer financiero: el tipo de regla no negociable que conviene fijar acá. Dónde viven: en el panel de contexto del Project (GUI), no un archivo que se edita a mano. Tiempo objetivo: ~5 min.

### Presenter feedback

---

# 4. Skills

**Goal of this section:** Enseñarle a Claude tareas reutilizables: qué es una Skill, cómo se crea por sus dos caminos (el menú Agregar del panel de Habilidades, donde el ZIP importa una existente, y el chat con `/skill-creator` y la trampa del Save) y la anatomía del SKILL.md.

**Presenter feedback:**

---

## 1. Qué es una Skill

### Content

- **Skill** = instrucción reutilizable que se carga cuando el pedido coincide con su descripción. **Un trabajo por Skill.**
- *"Todo lo que le explicás a Claude más de una vez es una Skill que deberías escribir una vez."*
- Faro: `reporte-semanal` consolida la carpeta `fuentes/` en un reporte con formato fijo.

### Sources

- corpus/agentic-ai-deck.zip.md, definición de Skill (folder + SKILL.md, "one job per skill"); "Anything you explain to Claude twice is a skill you should write once."
- "corpus/mision - auto.zip.md", el ejemplo `reporte-semanal` (lee la carpeta `fuentes/`, consolida por empresa, formato fijo, sufijo `-new`).

### Speaker notes

Arranca el bloque avanzado, partido por tema: esta sección cubre Skills y la siguiente, Subagentes. La Skill materializa el "enseñá una vez, reutilizá siempre". Usar `reporte-semanal` como ejemplo concreto: lee TODOS los archivos crudos de `fuentes/` (uno por portal), consolida por empresa, la más relevante primera (⭐), y guarda con sufijo `-new` para no pisar el ejemplo. Convierte varios archivos desordenados en un reporte prolijo. El criterio "un trabajo por Skill": si aparece "y además", conviene dividirla en dos. La creación paso a paso viene en las dos slides siguientes, una por camino (el panel y el chat); la anatomía del archivo cierra la sección. Tiempo objetivo: ~4 min.

### Presenter feedback

---

## 2. Crear una Skill desde el panel

### Content

- Desde **Configuración → Habilidades → Agregar**: dos caminos para crear una Skill y uno para importar una ya hecha.

![El panel de Habilidades: Examinar y el menú Agregar](images/skills-panel.png)

```ascii
     CREAR UNA SKILL EN COWORK

 Configuracion > Habilidades > AGREGAR          en el chat
 +-------------------+---------------------+   +------------------+
 | Crear con Claude  | Escribir las        |   | /skill-creator   |
 | (ida y vuelta de  | instrucciones en    |   | guia y revisa    |
 |  chat)            | la UI               |   | el SKILL.md      |
 +-------------------+---------------------+   +------------------+
 | Subir una habilidad (ZIP):              |            |
 | importa una Skill ya existente          |            |
 +-----------------------------------------+            |
                      \                                /
                       v                              v
                  +==================================+
                  |   GUARDAR / HABILITAR            |  <== la trampa
                  |   (lista de Habilidades)         |
                  +==================================+
                                  |
                                  v
                         +-----------------+
                         |  SKILL ACTIVA   |
                         +-----------------+

   frenar en la compuerta = la Skill "no funciona"
```
<!-- ascii-note:
intent: mostrar los caminos del menú Agregar del panel Habilidades (Crear con Claude en un ida y vuelta de chat; escribir las instrucciones directo en la UI; subir un ZIP, que IMPORTA una Skill ya existente en vez de crear una) más el comando /skill-creator en el chat, que guía y revisa el SKILL.md. Todos convergen en la misma compuerta: guardar y habilitar la Skill en la lista.
emphasize: la compuerta "GUARDAR / HABILITAR" como cuello de botella (caja de doble línea, marcada "la trampa") y la leyenda inferior; el menú Agregar con sus tres opciones como bloque de la UI, separado del camino por comando.
labels: bloque UI = menú Agregar (Crear con Claude / Escribir instrucciones / Subir ZIP); bloque chat = /skill-creator (guía y revisa); compuerta = guardar/habilitar en la lista de Habilidades; salida = Skill activa.
-->

### Sources

- Verificación de primera mano de los presentadores (2026-07-21, captura del panel Configuración → Habilidades): el menú **Agregar** ofrece "Cree con Claude", "Escribe las instrucciones de la habilidad" y "Subir una habilidad".
- Anthropic Support, How to create custom skills: https://support.claude.com/en/articles/12512198-how-to-create-custom-skills; la versión actual del artículo (re-verificada 2026-07-15) documenta solo el camino ZIP; los otros dos caminos del menú Agregar y el comando `/skill-creator` todavía no aparecen ahí (doc atrasada respecto del producto; atribuido a la captura).

### Speaker notes

La primera de las dos slides prácticas de creación: el camino por el panel. Con conexión, hacerlo en vivo: Configuración → Habilidades → Agregar, y nombrar las tres opciones del menú mientras se ven en la captura. "Crear con Claude" abre un ida y vuelta de chat donde Claude escribe el `SKILL.md`; "Escribir las instrucciones" edita la habilidad directo en la UI; "Subir una habilidad" importa una Skill ya existente desde su ZIP, por ejemplo una que compartió un colega, así que no crea nada nuevo. El diagrama adelanta dos cosas que enseña la lámina siguiente: el camino por chat y la compuerta de guardar y habilitar, donde convergen todos los caminos; anticiparlas en una frase y no desarrollarlas todavía. La captura queda de respaldo por si la demo falla. La doc oficial va detrás del producto en este punto; re-mirar el panel el día de la clase. Tiempo objetivo: ~3 min (con demo).

### Presenter feedback

---

## 3. Crear una Skill desde el chat

### Content

- Las habilidades también están a mano **desde el chat**: el menú **"+"** las lista, con "Administrar" y "Explorar habilidades".

![El menú + del chat: las habilidades disponibles, administrar y explorar](images/skills-menu-chat.png)

- En el chat, el comando **`/skill-creator`** (una skill de Anthropic que viene preinstalada) guía la creación y revisa el resultado.
- **La trampa del Save:** la Skill tiene que quedar guardada y habilitada en la lista de Habilidades, o "no funciona".

### Sources

- Verificación de primera mano de los presentadores (2026-07-21, captura del panel Configuración → Habilidades): `skill-creator` figura en la lista como skill de Anthropic; Cowork incluye un set reducido de slash commands.
- Anthropic Support, Use Skills in Claude: https://support.claude.com/en/articles/12512180-use-skills-in-claude; habilitar Skills desde el panel de Habilidades; requiere Code execution ("This feature requires code execution to be enabled"; re-verificado 2026-07-15).

### Speaker notes

La segunda mitad del paso a paso: la misma Skill, pero desde el chat. Mostrar el menú "+" con las habilidades disponibles, "Administrar" y "Explorar habilidades", y después tipear `/` para que aparezca la lista de comandos. Cowork incluye un set reducido de slash commands, bastante menos que Claude Code; no hace falta recorrerlos, alcanza con el tip de tipear `/`. Crear `reporte-semanal` con `/skill-creator`, que guía la escritura y revisa el resultado. Requisito a mencionar antes de la demo: las Skills piden **Code execution** habilitado, si no, el panel no las corre. Y el aviso que más problemas ahorra, la trampa del Save: la Skill recién creada tiene que quedar guardada y habilitada en la lista de Habilidades, o parece que "no funciona"; es la compuerta que el diagrama de la lámina anterior marca. La captura queda de respaldo por si la demo falla. Tiempo objetivo: ~3 min (con demo).

### Presenter feedback

---

## 4. Un SKILL.md por dentro

### Content

- Un `SKILL.md` por dentro: **metadata** arriba, **instrucciones** abajo. Es el `.md` con metadata de la sección 2.

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
intent: mostrar la anatomía de un SKILL.md; un bloque de metadata (YAML frontmatter: name + description) arriba y el cuerpo de instrucciones en Markdown abajo. Refuerza el beat de archivos .md/metadata de la sección 2 (Knowledge & Output).
emphasize: la separación visual en dos zonas; METADATA/HEADER (name, description; "qué es / cuándo se activa") vs CUERPO (las instrucciones; "qué hace"); que la `description` dispara la Skill.
labels: zona superior = metadata/header (YAML, name + description); zona inferior = cuerpo (instrucciones en Markdown); etiquetas laterales "cuándo se activa" y "qué hace".
-->

- **Metadata:** `name` identifica; `description` **decide cuándo se activa** (semántico, no por palabra clave).
- **Cuerpo:** Markdown común, los pasos que sigue el agente.

### Sources

- corpus/agentic-ai-deck.zip.md, definición de Skill (SKILL.md con YAML frontmatter: name + description; "Description drives triggering — semantic, not keyword").
- "corpus/mision - auto.zip.md", la Skill `reporte-semanal` (entrada `fuentes/`, consolida por empresa, estructura fija, sufijo `-new`).

### Speaker notes

Slide-ejemplo que aterriza dos cosas a la vez: la anatomía de una Skill y el beat de archivos `.md` + metadata de la sección 2. Mostrar el `SKILL.md` partido en dos zonas: arriba el header YAML (`name`, `description`) entre `---`, abajo las instrucciones en Markdown. El punto a fijar: el sistema lee la `description` para decidir si esta Skill aplica a tu pedido (activación semántica). Usar `reporte-semanal` para que sea concreto. Mantenerlo alto nivel: es para que vean cómo se ve, no un tutorial de formato. Tiempo objetivo: ~3-4 min.

### Presenter feedback

---

# 5. Subagentes

**Goal of this section:** La pieza avanzada del cierre: qué es un Subagente, para qué tipo de sub-tarea conviene y cómo aparece en Cowork.

**Presenter feedback:**

---

## 1. Subagentes: varios trabajando a la vez

### Content

- **Subagente** = asistente aislado, contexto propio; devuelve **un resumen** (no la transcripción).
- Ejemplo: **8 propuestas de proveedores**, un subagente por propuesta; los 8 corren en paralelo y el agente principal arma la tabla comparativa final.
- En Cowork corren "por debajo", **varios en paralelo**.
- **No se configuran a mano:** los coordina Claude solo, según la tarea. No hay panel de subagentes en Cowork.
- Lo que sí está en la mano del usuario: **pedir el trabajo en partes separables** ("compará estas 8 propuestas"), que es lo que habilita el paralelo.

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

- corpus/agentic-ai-deck.zip.md, definición de Subagent (aislado, devuelve un resumen); "Skill vs Subagent" (slide 4.9 tabla); demo 4.8 (8 propuestas en paralelo). Para el comportamiento en Cowork: "Cowork subagents are coordinated under the hood — no manual `/agents` config exposed in the GUI" y la matriz 4.10 (Cowork ⚠️, misma frase).
- **Documentación de Claude Code** (no de Cowork), Subagents: https://code.claude.com/docs/en/sub-agents. Se usa **solo para el concepto general** de subagente (contexto propio, devuelve un resumen). La configuración manual que describe (`/agents`, archivos en `.claude/agents/`) **es de Claude Code y no está expuesta en Cowork**; no se cita como evidencia sobre Cowork.

### Speaker notes

Nivel avanzado: un subagente conviene cuando una sub-tarea es pesada o genera mucho texto intermedio que nadie necesita leer — corre aparte y vuelve con el resumen. No es opuesto de las Skills (se combinan); acá solo se enseña qué es. El ejemplo del fan-out: 8 propuestas de proveedores, un subagente por propuesta, corren en paralelo y el agente principal arma la tabla comparativa. Ser claro con el límite: en Cowork esto pasa por debajo, lo decide Claude según la tarea, y no hay pantalla donde el usuario arme o edite subagentes (eso existe en Claude Code, que es otra herramienta y queda fuera de esta clase). Lo accionable para la audiencia es cómo se pide el trabajo: si la tarea se puede partir en pedazos independientes, conviene decirlo así, porque es lo que habilita el paralelo. Si alguien pregunta por configurarlos, la respuesta honesta es que en Cowork hoy no se configuran a mano. Alto nivel, sin internals. Tiempo objetivo: ~4 min.

### Presenter feedback

---

# 6. La misión · parte 2

**Goal of this section:** Placa de misión y cierre del recorrido de piezas. Manda a resolver la parte 2 en Cowork, sobre la carpeta real del equipo, con Projects, Instrucciones, archivos .md, Skills y Subagentes, y deja claro que no exige la parte 1 (que se mandó en la clase anterior) resuelta. Sin contenido nuevo.

**Presenter feedback:**

---

## 1. La misión, parte 2: Faro en Cowork

### Content

```ascii
   ______________________________________________
  |                                              |
  |   LA MISION - PARTE 2                        |
  |                                              |
  |   FARO EN COWORK                             |
  |   sobre la carpeta real del equipo           |
  |                                              |
  |   Projects + .md + Skills + Subagentes       |
  |______________________________________________|
```
<!-- ascii-note:
intent: placa divisoria de misión, gemela de la placa de la parte 1 que va en la clase anterior. Cartel, no diagrama de flujo: manda a resolver la parte 2 en Cowork con las piezas recién enseñadas.
emphasize: "LA MISION - PARTE 2" arriba y "FARO EN COWORK" en el centro, en el tipo más grande de la placa; el mismo diseño que la placa de la parte 1 de la clase anterior.
labels: arriba = LA MISION, PARTE 2; centro = FARO EN COWORK (sobre la carpeta real del equipo); abajo = Projects, archivos .md, Skills y Subagentes.
-->

- **Parte 2, en Cowork:** Faro baja a la computadora y trabaja sobre la carpeta real del equipo.
- Las piezas de esta mitad: **Projects, Instrucciones, archivos `.md`, Skills y Subagentes.**
- El entregable final es **el tablero para el jefe**: se arma en `.md` y se exporta al formato de entrega, con el flujo de la sección 2.
- **No hace falta haber resuelto la parte 1** de la clase anterior: la parte 2 arranca del material que ya viene con la misión.

### Sources

- `missions/CoWork/mission.md`, tabla "Las dos partes" y la nota "La Parte 2 no exige la Parte 1 resuelta": arranca de los materiales incluidos, la herencia del pasante en `reportes/`.
- "corpus/mision - auto.zip.md", el flujo de Faro en Cowork: carpeta del Project, reporte consolidado y Skills reutilizables.

### Speaker notes

Placa de misión con el mismo formato que la de la parte 1 de la clase anterior, para que se lea como el cierre del arco entero. Acá ya están todas las piezas sobre la mesa. Decir qué cambia respecto de la parte 1: Faro deja de vivir en el chat y pasa a trabajar sobre la carpeta real del equipo, con su Project, sus Instrucciones, sus archivos `.md` y sus Skills. Nombrar el entregable con el que cierra la misión, el tablero que se le lleva al jefe, y decir de dónde sale: no es una pieza nueva, se arma con el flujo de la sección 2, se consolida en `.md` mientras el trabajo está abierto y recién al final se le pide a Claude el formato de entrega. Decirlo con todas las letras, porque ahora importa más que antes: **la parte 2 no exige tener resuelta la parte 1**, que quedó como tarea de la clase anterior. Arranca del material incluido en la misión, la pila de notas en crudo que dejó el pasante, así que quien no la hizo entra igual. Si alguien sí viene de la parte 1, los conectores ya autorizados se reutilizan y el arranque es más corto. Cerrar mandando al material de la misión antes de pasar a las conclusiones. Tiempo objetivo: ~2 min.

### Presenter feedback

---

# Conclusions

## 1. Repaso: las piezas y cómo se combinan

### Content

- Con el chat extendido de la clase anterior como base, **Cowork** baja a la computadora y trabaja sobre carpetas y archivos.
- El cambio de rol: **delegar un resultado completo** y guiar el proceso.
- Los archivos **`.md`** son el formato de trabajo. El entregable con formato se genera una sola vez, al final.
- Un **Project** sobre una carpeta concedida, con las **Instrucciones** como contrato del espacio.
- **Skills** para enseñar una tarea una vez y **Subagentes** para delegar en paralelo. Las piezas se combinan: **cada trabajo usa solo las que necesita.**

### Sources

- Sin material nuevo: repaso de las secciones 1 a 6; cada punto conserva la fuente de su slide de origen (1.1, 1.3, 2.3, 3.1, 3.3, 4.1, 5.1).
- corpus/agentic-ai-deck.zip.md, progresión de building blocks; es la misma pila del mapa de 1.4.
- "corpus/mision - auto.zip.md", la misión Atlas arma estas piezas una por una.

### Speaker notes

Primera de las tres láminas de cierre y la única que repasa contenido. La audiencia acaba de ver todo esto, así que no hay que re-explicar nada: una frase por bullet y seguir. Ritmo rápido, tono de "esto es lo que se llevan".

Si conviene apoyarse en algo visual, volver un momento al mapa de la slide 1.4, que es exactamente esta lista dibujada como bloques apilados. No hace falta un diagrama nuevo acá.

Lo único que sí conviene decir despacio es el remate: las piezas se combinan y cada trabajo usa solo las que necesita. Nadie tiene que armar las cinco para empezar; con un Project y un par de archivos `.md` ya se trabaja distinto. Mencionar al pasar que la misión parte 2 es donde van a combinarlas por su cuenta.

Handoff: de acá se pasa al loop completo de Faro, que muestra estas mismas piezas enganchadas en un flujo que corre solo. Tiempo objetivo: ~2 min.

### Presenter feedback

---

## 2. El loop completo de Faro

### Content

- El loop completo de Faro, que engancha las piezas de las dos clases. Arranca en el Schedule, que quedó armado en la clase anterior:

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
   v
[Connector Gmail] deja el borrador listo para el equipo
```
<!-- ascii-note:
intent: mostrar el loop completo de la misión de Faro, encadenando las piezas de las dos clases (Schedule y conectores de la anterior; Skills y Project de esta), disparado por el Schedule cada lunes.
emphasize: la secuencia de arriba abajo Schedule -> Skills -> Connectors -> borrador de correo; que todo arranca de un solo disparador, el Schedule, que es pieza de la clase anterior.
labels: pasos del loop (Schedule, buscar-accion, reporte-semanal, Gmail) y las piezas usadas en cada uno.
-->

- **El arco completo:** *clase anterior*, chat de memoria → conectores → Schedule; *hoy*, Cowork (`.md`) → Projects → Instrucciones → Skills → Subagentes.
- **Las piezas de hoy:** `.md` (el lenguaje) · Projects (el espacio de trabajo) · Instrucciones (el contrato) · Skills (enseñar una vez) · Subagentes (delegar en paralelo). Y las dos que ya traían: Conectores (las manos) y Schedule (corre solo).
- **Para llevarse:** *"Todo lo que le explicás a Claude más de una vez es una Skill que deberías escribir una vez."* ¿Qué tarea recurrente le delegarías a tu propio Faro?

### Sources

- "corpus/mision - auto.zip.md", "el loop completo (Cowork version)"; gancho de cierre.
- corpus/agentic-ai-deck.zip.md, "Anything you explain to Claude twice is a skill you should write once" (slide 7.3).

### Speaker notes

Cierre integrador de las dos clases: mostrar el diagrama del loop completo para que vean cómo cada pieza se engancha con la siguiente. El loop arranca arriba con el Schedule, que es de la clase anterior; decirlo al pasar, sin re-enseñarlo, porque es justamente lo que muestra que las dos mitades son una sola cosa. La lámina anterior ya repasó las piezas una por una, así que acá no hay que volver a listarlas: los dos bullets de arco y piezas quedan de apoyo visual y se leen de corrido, o directamente se saltean. El trabajo de esta lámina es el diagrama, que muestra las piezas enganchadas y corriendo solas. Cerrar con las dos frases ancla: la de la Skill ("enseñá una vez") y el gancho completo, dicho en voz alta: "Acaban de automatizar un reporte que les iba a comer la mañana de cada lunes. ¿Qué otra tarea recurrente podrían delegarle a su propio Faro?". Tiempo objetivo: ~5 min + Q&A (candidato a recortar a ~3 min ahora que el repaso vive en la lámina anterior).

### Presenter feedback

---

## 3. Antes de cerrar: cuidados

### Content

- **Toda salida es un borrador**: cifras, citas y afirmaciones se verifican contra la fuente.
- **Nada de datos de clientes, financieros, PII ni bajo NDA.** La actividad de Cowork no queda en el registro de auditoría estándar: solo hay rastro si la organización lo configura aparte (Team/Enterprise), y por defecto no se registra nada.
- **Capas de guardarraíles:** permisos de carpeta → reglas en Instrucciones → solo conectores verificados → revisión humana.

### Sources

- Anthropic Support, Use Claude Cowork safely: https://support.claude.com/en/articles/13364135-use-claude-cowork-safely (verificado 2026-07-31): "Cowork activity is **not captured** in the Compliance API at this time"; recomienda evitar conceder acceso a archivos locales con información sensible.
- Anthropic Support, Monitor Claude Cowork activity with OpenTelemetry: https://support.claude.com/en/articles/14477985-monitor-claude-cowork-activity-with-opentelemetry (verificado 2026-07-31): el registro de actividad de Cowork existe vía OpenTelemetry, solo en planes Team y Enterprise, y "Events are only exported when an admin configures an OTLP endpoint. No data flows by default."
- corpus/agentic-ai-deck.zip.md, slide 7.2 (Governance & verification, verbatim); la afirmación "No audit trail in Cowork" de ese deck interno quedó corregida contra las dos fuentes oficiales de arriba.

### Speaker notes

Slide de cierre responsable, breve y obligatoria: acá la audiencia tiene que estar escuchando, no leyendo. Decirlo sin vueltas: Cowork sirve para trabajo recurrente de oficina y no para datos regulados, confidenciales o de clientes. El matiz que conviene decir bien, porque es el que se van a repetir en la oficina: no es que Cowork no deje ningún rastro, es que su actividad no entra en el registro de auditoría estándar de la cuenta (la Compliance API), y el registro que sí existe (OpenTelemetry hacia el SIEM de la empresa) es de planes Team y Enterprise y solo funciona si un administrador lo configura; por defecto no se exporta nada. Traducción para ellos: en una cuenta personal, nadie va a poder reconstruir después qué hizo el agente. Recordar que toda salida es un borrador que hay que verificar, lo mismo que se dijo en la clase anterior sobre el chat: el modelo puede alucinar, el conector cita fuentes, el humano verifica. Dos cosas que no están en la lámina y sí conviene decir: guardar juntos el prompt, las entradas y las salidas es lo que vuelve reproducible el trabajo, y en el trabajo real, con datos de la empresa o de clientes, nada de esto sin aprobación del área que corresponda. Los guardarraíles se leen de afuera hacia adentro. Dejar esto antes de abrir Q&A. Tiempo objetivo: ~2 min.

### Presenter feedback

---

# Open questions

- ~~Fecha de la clase sin confirmar~~; resuelto 2026-07-14: `date: Julio 2026`.
- **Split del 2026-07-31:** esta charla es la parte 2 de lo que era una clase de 120 min. La parte 1 (chat, conectores, Schedule, misión parte 1) vive ahora en `talks/claude-desktop-chat`. Consecuencias abiertas: (a) `duration` quedó en `60 min (a confirmar)` y la suma de "Tiempo objetivo" da **66,5 min** desde que se agregó el repaso de Conclusions.1 (2026-07-31, +2 min sobre los 64,5 previos), así que hay que confirmar el bloque real o recortar ~6,5 min; el recorte recomendado por el editor es Conclusions.2 (el loop de Faro) de 5 a 3 min, porque el repaso nuevo ya cubre sus dos bullets de arco y piezas; (b) `final.md`, `output/slide-model.json` y `output/html/index.html` describen el deck combinado y están **desactualizados**; (c) los SVG/PNG en `images/` llevan slugs `s6-*`..`s11-*` de la numeración vieja, así que el próximo Polish re-deriva slugs y conviene seguirlo de un `polish_ascii.py gc`.
- **Sin recap de la parte 1 (decisión del presentador, 2026-07-31):** el deck arranca directo en Cowork y solo remite a "la clase anterior" en prosa. Si al ensayar se siente abrupto, la pieza que falta sería un slide de repaso de una lámina al inicio de la Sección 1; no está y es decisión consciente.
- Imágenes diferidas (Phase 2 del librarian no corrida): la imagen citada desde el corpus (`screenshot-cowork-tab.png` en slide 1.5) proviene de un registro con `<!-- pending: process_images -->`. La imagen existe en disco y se referencia; re-verificar depiction/relevance tras correr librarian Phase 2. (`mockup-tablero.png` quedó sin uso tras la reestructura del 2026-07-30, que borró la slide de Artifacts.)
- Slide 1.5 (Demo time) cita pending stub corpus/agentic-ai-deck.zip.md; re-verify after librarian Phase 2.
- **Slash commands en Cowork (slides 4.2–4.3):** verificado de primera mano por los presentadores (2026-07-21): Cowork incluye un set reducido de slash commands, `/skill-creator` entre ellos, y la creación de Skills pasa por ese comando (el camino "lenguaje natural" de junio quedó subsumido ahí). La doc oficial (support 12512198) sigue documentando solo el camino ZIP. Decisión del presentador (2026-07-21): en la clase se muestra solo `/skill-creator`; `/skill-optimizer` queda fuera, y NO se releva la lista completa de comandos (alcanza con el tip de tipear `/`). Pendiente antes de la clase: probar si la Skill creada por comando también exige el Save/enable de la trampa.
- **Subagente a pedido (bonus M6 de la misión):** **RESUELTO del lado del deck (2026-07-31):** la slide 5.1 dejó de afirmar que el usuario agrega o gestiona subagentes en Cowork. Ahora dice lo que sostiene el corpus: los coordina Claude por debajo, sin configuración manual (corpus/agentic-ai-deck.zip.md, "no manual `/agents` config exposed in the GUI"; matriz 4.10, Cowork ⚠️). Búsqueda en fuentes oficiales (2026-07-31, support.claude.com / claude.com / anthropic.com): no aparece ninguna que documente creación o configuración de subagentes en Cowork; todo lo hallado es de Claude Code, el SDK o la plataforma. Queda como watch item, no como reclamo del deck: si el presentador quiere demostrar en vivo la creación de un subagente `investigador` a pedido, hace falta verificar de primera mano en el producto (a) que el pedido en lenguaje natural cree algo persistente y no una delegación de una sola vez, y (b) que quede visible o reutilizable en alguna parte de la interfaz. Sin esas dos cosas verificadas, no se demuestra ni se menciona como capacidad; el bonus M6 de la misión se cae sin bloquear la misión.
- **Audit trail de Cowork (Conclusions.3, ex Conclusions.2) — RESUELTO 2026-07-31:** el deck afirmaba "Cowork no tiene audit trail" apoyado solo en `corpus/agentic-ai-deck.zip.md` (deck interno, junio 2026). La verificación contra fuentes oficiales encontró que el claim es falso como hecho plano: existe registro de actividad de Cowork vía OpenTelemetry (support 14477985) con prompts, tool calls, acceso a archivos, skills y decisiones de aprobación, pero solo en planes Team/Enterprise, solo si un administrador configura un endpoint OTLP y sin exportar nada por defecto; y la actividad de Cowork no entra en la Compliance API (support 13364135 y 14477985, ambos verificados 2026-07-31). La lámina y las notes se reescribieron con ese matiz y citan las dos fuentes oficiales. Watch item: el registro por OpenTelemetry pide Claude Desktop 1.1.4173 o posterior, y la frase "not captured in the Compliance API **at this time**" sugiere que puede cambiar; re-verificar antes de la clase.
- Falta la carpeta `skills/` con los tres skills pre-armados (`reporte-semanal`, `buscar-accion`, `publicar-tablero`) en el export; confirmado por el librarian en Step 3. No se inventa su contenido. Si la clase incluye una demo en vivo de las skills ya armadas, confirmar con el presentador si las tiene aparte.
- Vigencia de features vs docs oficiales: fechas/versiones (Live Artifacts abril 2026, planes pagos, etc.) son point-in-time; re-verificar contra docs oficiales antes de presentar.
- **Slide 1.5; interacción pipeline del banner DEMO TIME:** la slide tiene un bloque ```ascii (banner "DEMO TIME") Y un image ref (`screenshot-cowork-tab.png`, respaldo). El pipeline de Polish marca como documentation-only TODO bloque ASCII en una slide que tiene image ref → el banner NO se renderizará a SVG en Step 6 tal como está. Decisión ya tomada en Polish (2026-07-17): opción (c), doc-only, la slide conserva el screenshot.
- **Piezas borradas por decisión del presentador (2026-07-30):** salieron del deck las slides de Schedule en Cowork, Artifacts y Live Artifacts, y las dos de Plugins (incluida la sección Enterprise). Las fuentes y capturas asociadas siguen en disco (`schedule.png`, `mockup-tablero.png`) por si se quieren reponer. Si se reponen, hay que volver a nombrarlas en el mapa de la charla (1.4) y en el loop de Conclusions.
- Nuevas URLs externas (round 3) a re-verificar en Polish si se quiere snapshot/cita estable, ya filtradas a las que esta parte cita o podría reponer: support.claude.com (use-skills, create-custom-skills, use-live-artifacts, manage-org-plugins, use-plugins), claude.com/blog (cowork-plugins-across-enterprise), code.claude.com/docs (sub-agents). (Las de chat, búsqueda web, conectores y tareas programadas se fueron con la parte 1 al split del 2026-07-31.)
- **Live Artifacts y el update del 7 de julio de 2026:** la locality de Live Artifacts ("viven en tu computadora, no compartibles aún") se RE-VERIFICÓ el 2026-07-09 contra support article 14729249 (actualizado recientemente) y sigue vigente pese a que las sesiones de Cowork ahora pueden correr remotas. Vigilar este punto: es el candidato más probable a quedar desactualizado con el rollout web/mobile.

# Cut material

- **Detalles internos de Claude Code** (Plan mode, slash commands completos, project-directory skills, config de `/agents`, dynamic workflows, las dos misiones hands-on basadas en Code, árboles `~/.claude/...`): fuera de foco por diseño de esta charla (companion funcional/alto nivel). Claude Code aparece solo como contraste en la Sección 1 (Claude Cowork). Fuente: corpus/agentic-ai-deck.zip.md (Code-related slides preservadas pero marcadas fuera de foco).
- **Comparación detallada Cowork vs Codex** (las dos tablas y el re-solución completa de Codex): disponible en el corpus para un ángulo "vs la alternativa", pero excluida para no diluir el foco en *usar* Cowork. Podría incorporarse como un slide opcional si el presentador lo pide en Review. Fuente: "corpus/mision - auto.zip.md" (cowork-vs-codex).
- **`buscar-accion` con Claude in Chrome / web_fetch a Yahoo Finance** como tema técnico propio: mencionado de pasada en el loop completo (Conclusions) pero no desarrollado como slide, para mantener el nivel alto. Fuente: "corpus/mision - auto.zip.md" (M2).
- **Auto memory** como concepto separado: absorbido dentro de Projects (la memoria es una de las tres capas del Project) en lugar de un slide propio, para no fragmentar el básico. Fuente: corpus/agentic-ai-deck.zip.md (Auto memory 3.7).
- **Framing "sideway" de los archivos MD** (round 4): la ex-slide "(Sideway) Archivos MD y metadata" dejó de ser un aparte y se expandió a un beat de enseñanza propio, hoy la **Sección 2 (Knowledge & Output)**: cómo se escribe un `.md`, el mismo archivo formateado y el hábito de trabajar en `.md` y exportar al final; la nota original "esto es un sideway de alto nivel — es contexto, no el plato principal" se retiró porque el presentador lo promovió a contenido central. Fuente: draft round 3, slide 3.2.
- **Título/encuadre original del roadmap** (round 4): la ex-slide 2.2 "Los bloques de Cowork: cada problema, una pieza" codificaba el arco viejo (solo bloques de Cowork, empezando en "un prompt/chatear" como bloque de Cowork). Reescrita como la actual **1.4 "El mapa: piezas que se apilan"** con el arco completo (chat → conectores → tareas programadas → Cowork → avanzado) y marcadores "(visto)" / "estamos acá"; tras el split del 2026-07-31, los tres bloques "(visto)" de abajo son los de la clase anterior. Los pares problema↔bloque originales de Instrucciones/Projects/Skills/Connectors/Schedule/Live Artifacts se conservan (reformulados) en el diagrama nuevo. Fuente: draft round 3, slide 2.2.
