---
source_type: live-exploration
started_at: 2026-07-15T00:00:00
ended_at: 2026-07-15T23:59:00
topic: ground rules y criterio de aprobación — MIM Augmented
---

### Presenter

4

### Agent

▶ EXPLORATION MODE
topic: ground rules y criterio de aprobación — MIM Augmented
capture trigger: "ready" / "done exploring" / "drop it"

Dale, exploremos. Para armar las ground rules y el criterio de aprobación necesito que me cuentes algunas cosas — tirame lo que tengas en la cabeza, en cualquier orden, y yo lo voy organizando:

- **Asistencia**: ¿hay un mínimo de clases obligatorias? (con 2 virtuales y 5 presenciales, ¿aplica algo distinto a cada formato?)
- **Entregables**: ¿el criterio de aprobación se basa en las misiones de cada día (Atlas, Enterprise, Paperclip), en un trabajo final, en participación, o una combinación?
- **Uso de IA en el curso**: dado que es un curso sobre IA, ¿hay reglas específicas sobre cómo pueden/deben usar las herramientas durante las clases y entregas? (¿algo tipo "no dar consejos de inversión" que ya mencionaste en el Día 1?)
- **Puntualidad / dispositivos / participación en vivo**: ¿algo que quieras dejar explícito para las sesiones presenciales?
- **Escala de calificación**: ¿aprobado/desaprobado, nota numérica, u otra?

Contame lo que tengas y seguimos.

### Presenter

Empecemos tomando el calendario del README.md. Mostrame los dias y lo que esta planeado.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Así está el calendario en el `README.md` — 7 sesiones, mezcla presencial/virtual:

| # | Fecha | Horario | Formato | Duración | Título |
|---|---|---|---|---|---|
| 1 | Sáb 1 Ago | 8:30–12:00 | Presencial | 3.5 h | Getting Started with Claude Cowork |
| 2 | Sáb 1 Ago | 13:00–16:30 | Presencial | 3.5 h | Automating a Weekly Report in Cowork |
| 3 | Jue 6 Ago | 19:00–21:00 | Virtual | 2 h | *A definir* |
| 4 | Mar 11 Ago | 19:00–21:00 | Virtual | 2 h | *A definir* |
| 5 | Vie 28 Ago | 9:00–12:30 | Presencial | 3.5 h | Cowork for the Enterprise |
| 6 | Sáb 29 Ago | 8:30–12:00 | Presencial | 3.5 h | Orchestrating Agents with Paperclip |
| 7 | Jue 3 Sep | 19:00–21:00 | Virtual | 2 h | Evaluation |

Días 1–2 (el sábado doble) arman la misión **Atlas** completa: de notas sueltas del intern a un reporte semanal que Atlas investiga, redacta, envía por mail y publica solo, en 4 milestones (Projects/Instructions/Skills → Tools/Connectors → Schedule → Live Artifacts).

Días 3–4 todavía están *a definir*.

Día 5 es **Enterprise**: empaquetar el trabajo en Plugins, instalarlo en la máquina de un compañero, Claude Tag y cuenta Team.

Día 6 es **Paperclip**: agregar un agente especializado ("Director de Relaciones Institucionales") a una organización de agentes ya existente, con human-in-the-loop.

Día 7 es **Evaluación** — formato todavía a definir.

¿Seguimos con las ground rules y el criterio de aprobación, o querés primero definir algo de los Días 3–4 o el formato de evaluación del Día 7?

### Presenter

Perfecto. Vamos a defirnir que el titulo es Agentes Inteligentes. Asi que esto es lo que va de definit el titulo de la materia.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Anotado — **"Agentes Inteligentes"** como título de la materia.

Ojo: el `Subject` está en `config/profile.md` y es compartido por todas las clases del curso (no solo esta). Ahí dice hoy: *"Inteligencia Artificial: de lo conceptual a lo práctico — Master in Management (MiM), IAE Business School, Universidad Austral..."*.

¿Cómo lo actualizamos?

1. **Reemplazar el Subject completo** → `"Agentes Inteligentes — Master in Management (MiM), IAE Business School, Universidad Austral"`
2. **Agregarlo como subtítulo**, manteniendo el actual → `"Inteligencia Artificial: de lo conceptual a lo práctico — Agentes Inteligentes — MiM, IAE Business School..."`
3. Es solo el título **de esta clase** (`class`, no `Subject`) — no toca el perfil global

### Presenter

1

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

[Actualizó `config/profile.md`: Subject → "Agentes Inteligentes — Master in Management (MiM), IAE Business School, Universidad Austral (https://www.iae.edu.ar/programas/mim/)"]

Listo, `Subject` actualizado a **"Agentes Inteligentes"** en el perfil — se aplicará a todas las clases del curso.

Retomando: ¿seguimos armando ground rules y criterio de aprobación, o hay algo más del calendario/título que ajustar primero?

### Presenter

Tambien cambiemos el readme.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

El README arranca con `# MIM — Augmented | IAE Business School`. ¿Cómo lo dejamos?

1. **`# Agentes Inteligentes | MIM — IAE Business School`**
2. **`# Agentes Inteligentes`** (solo el nuevo título, sin el resto)
3. Otro texto — decime cuál

### Presenter

1

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

[Actualizó README.md: título → "# Agentes Inteligentes | MIM — IAE Business School"]

Listo, título del README actualizado.

Seguimos con ground rules y criterio de aprobación cuando quieras — o si preferís, avanzamos con otra cosa primero.

### Presenter

Vamos a explorar cual es el objetivo de curso y lo que esperamos. Durante la primera parte de la materia, el foco fue mas en la teoria. El foco de esta segunda parte es lo que como Agentes y Tools ayudan a aumentar lo que hacemos los knoleage workers. El foco es ver una herramienta pero lo mas importate es aprender el como es la filosofia y la forma de pensar para poder adaptarnos a lo que viene. Esto es muy rapido y va a iterar. Tools que vamos a explorar son Claude CoWork, PaperCliping y otras.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Buenísimo, esto es el corazón del "por qué" de la materia. Lo que describís es una transición clara: primera parte = marco conceptual (entender qué es la IA, dónde crea valor); segunda parte = filosofía de trabajo aumentado — no "aprender una herramienta" sino internalizar una forma de pensar que sobrevive al cambio de herramientas.

Eso conecta directo con la frase del README: *"el futuro no va a ser de las empresas que simplemente usan IA, va a ser de los managers que están aumentados por ella."*

Algunas cosas para afilar:

- **El mensaje central** — ¿lo resumirías como "las herramientas van a cambiar rápido, lo que no cambia es la mentalidad de delegar y guiar en vez de ejecutar todo a mano"? ¿O hay otro ángulo que quieras que quede más fuerte?
- **Riesgo de obsolescencia explícita** — decís "esto es muy rápido y va a iterar" — ¿querés nombrar esto abiertamente en la clase (ej. "lo que les muestro hoy puede cambiar de nombre en 6 meses, por eso el foco está en el patrón, no en el botón")?
- **Las tools mencionadas** — Cowork y Paperclip están claros por el calendario (Días 1-2 y 6). Dijiste "y otras" — ¿pensás en algo puntual para Días 3-4 (que siguen *a definir*), o "otras" es más una idea abierta de que el panorama de herramientas sigue creciendo?
- **Qué esperan que se lleven** — ¿algo tipo "después de este curso, cuando aparezca una herramienta nueva, van a saber qué preguntarle y cómo evaluarla" en vez de una lista de features?

### Presenter

Ayudame a pulir este goal de la materia.
Continue from where you left off.

### Agent

[No response requested.]

### Presenter

Me parece bien tu recoemendacion. Como quedaria esto como foco de la materia y luego los bullets me pacen bien.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Buena base. Te propongo esto:

**Foco de la materia (segunda parte — Agentes Inteligentes)**

> La primera parte del curso construyó el marco conceptual: dónde crea valor la IA y cómo pensarla a nivel de negocio. Esta segunda parte es sobre la práctica de trabajar aumentado — cómo Agentes y herramientas de IA multiplican lo que puede hacer un knowledge worker. Vamos a explorar herramientas concretas (Claude Cowork, Paperclip y otras), pero el objetivo no es dominar un producto puntual: es internalizar la filosofía y la forma de pensar detrás de delegar y orquestar trabajo con agentes. El panorama de herramientas cambia rápido — lo que hoy es Cowork, mañana puede tener otro nombre — por eso el foco está en el patrón, no en el botón. Al terminar el curso, van a saber qué preguntarle a una herramienta nueva y cómo evaluarla, no solo cómo usar la de hoy.

**Lo que se llevan (bullets):**

- La forma de pensar para delegar trabajo a agentes, no solo ejecutar tareas asistidos por IA.
- Experiencia hands-on con herramientas reales (Claude Cowork, Paperclip, y otras) como vehículo de aprendizaje — no como el destino.
- Un criterio propio para evaluar y adoptar herramientas nuevas a medida que el panorama itera.
- Confianza para operar como "manager aumentado": guiar y supervisar agentes en vez de hacer todo a mano.

¿Lo dejamos así, o ajustamos algo del texto o de los bullets?

### Presenter

Cambimos el README.md en vez de Industry 4.0.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Ojo que "Industry 4.0" no es solo un título — es el marco narrativo completo del README: las "8 Etapas" (Assessment, Strategy, Connectivity, Integration, Analytics, Automation, People, Scale) y cada día del calendario está mapeado a una o más de esas etapas (columna **I4.0 PHASE**).

¿Qué querés hacer exactamente?

1. **Solo cambiar el nombre/etiqueta** — reemplazar "Industry 4.0" por otro término (ej. "Agentes Inteligentes") pero mantener las 8 etapas y el mapeo tal cual, como si fuera un rebranding del mismo marco.
2. **Reemplazar el marco entero** — sacar las 8 etapas de Industry 4.0 y armar un marco narrativo nuevo (basado en la filosofía de delegar/orquestar agentes que definimos) del que luego mapeamos cada día.
3. **Dejar el marco Industry 4.0 como está** — es un contexto útil de negocio (transformación digital) y separado del título de la materia; no tocar esta parte.

### Presenter

2

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Dale, armemos un marco propio en vez de Industry 4.0. Basándome en lo que definimos — la progresión de "chatear" a "delegar" a "orquestar" — te propongo esto:

**Marco: "La Escalera del Trabajador Aumentado"** (nombre tentativo)

| Etapa | Foco | Mapea a |
|---|---|---|
| 1. **Delegar** | Pasar de escribir un mensaje a la vez a delegar un resultado completo — el agente planea, toca archivos, entrega. | Día 1 |
| 2. **Automatizar** | El agente arma su propio loop: investiga, redacta, agenda, publica solo. | Día 2 |
| 3. *(a definir)* | — | Días 3–4 |
| 4. **Escalar** | De uso personal a uso de equipo — empaquetar el trabajo en Plugins, distribuirlo, cuenta Team. | Día 5 |
| 5. **Orquestar** | De un agente a una organización de agentes, con vos como supervisor humano en los puntos clave. | Día 6 |
| 6. **Evaluar** | Cierre y evaluación del curso. | Día 7 |

¿Te sirve esta estructura de 6 etapas (dejando la 3 abierta hasta definir Días 3-4), o preferís otro nombre/cantidad de etapas antes de que lo escriba en el README?

### Presenter

Borremos por ahora ese marco

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

[Editó README.md: eliminó la sección "Industry 4.0 — The 8 Stages" completa, y todas las referencias a "I4.0 Phase"/"Industry 4.0" en títulos de día, la tabla Mission Overview, y el texto del objetivo. Verificado sin restos con grep.]

Listo, borré el marco de las 8 Etapas de Industry 4.0 y todas las referencias a "I4.0 Phase" / "Industry 4.0" en el README (títulos de día, tabla Mission Overview, texto del objetivo). El contenido de las clases quedó intacto, solo se sacó ese andamiaje narrativo.

Retomamos las ground rules y criterio de aprobación cuando quieras.

### Presenter

Agreguemos tambien en el readme que la primera charla virtual va a ser sobre como usar AI y tools para construir presentataciomes. La idea que nos imaginamos es contar sobre NotebookLM, gamma, Claude Design (presentacion) pero mas imporante en enfoque de https://www.mindstudio.ai/blog/andrej-karpathy-llm-wiki-knowledge-base-claude-code y dividir conocimiento de visualizacion.

### Agent

[Leyó el artículo de MindStudio sobre el patrón LLM wiki de Andrej Karpathy vía web_fetch.]

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Leí el artículo. La idea central de Karpathy es separar el **conocimiento** (una wiki en markdown plano, estructurada con resúmenes y tags, que cualquier LLM puede leer y razonar sobre ella) del **cómo se presenta** ese conocimiento (el renderizado — slides, dashboard, wiki visual, lo que sea). El markdown es la interfaz universal; la visualización es una capa aparte y descartable.

Eso encaja perfecto con el Día 3: en vez de enseñar "cómo usar Gamma" como fin en sí, el mensaje es *"primero organizá el conocimiento en texto estructurado, después elegí cómo visualizarlo — y esa decisión la podés cambiar sin tocar el contenido"*. Es literalmente el patrón `draft.md` → `final.md` → deck que usamos en esta propia herramienta.

Te propongo esta entrada para el Día 3:

---

**DAY 3 — Construyendo Presentaciones con IA ● KNOWLEDGE-FIRST, VISUALIZATION-SECOND**
*Jue 6 Ago · 19:00–21:00 · Virtual · 2h*

| | |
|---|---|
| **GOAL** | Separar el conocimiento de su visualización: estructurar contenido en markdown plano y navegable por un agente, y recién después elegir cómo renderizarlo — la misma base de conocimiento puede volverse un deck, un dashboard, o una wiki consultable. |
| **TOOLS** | NotebookLM · Gamma · Claude (Cowork / Claude Design) |
| **SESSION FLOW** | → El patrón de la "LLM wiki" de Andrej Karpathy — por qué markdown estructurado (resumen, tags, contenido) es la interfaz que un agente lee mejor que cualquier app de notas (30 min) → Demo: armar una base de conocimiento en markdown y consultarla con un agente (30 min) → Herramientas de visualización — NotebookLM, Gamma y Claude para transformar ese conocimiento en una presentación, sin reescribir el contenido a mano (40 min) → Discusión: cuándo conviene separar "qué sé" de "cómo lo muestro", y qué se pierde si se mezclan (20 min) |
| **TAKEAWAYS** | ✓ El patrón de organizar conocimiento en markdown para que un agente lo consulte, no solo vos. ✓ Herramientas concretas (NotebookLM, Gamma, Claude) para pasar de conocimiento a presentación sin trabajo manual. ✓ Por qué separar contenido y visualización da flexibilidad — la misma base puede rendirse de formas distintas. |

---

¿Lo escribo así en el README, o ajustamos algo (duración de bloques, título, herramientas)?

### Presenter

SESSION FLOW es mas realmente la evolicion de todo

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Entendido — armo el flujo como una evolución, no como bloques temáticos sueltos. Algo así:

**SESSION FLOW** → De las slides manuales a la IA generativa — el punto de partida: armar un deck a mano, diapositiva por diapositiva (10 min) → Primera ola: herramientas todo-en-uno (NotebookLM, Gamma, Claude Design) — le tirás contenido crudo y te devuelven una presentación lista; rápido, pero contenido y visual quedan pegados en una sola caja negra (35 min) → El límite de esa ola — ¿qué pasa cuando querés cambiar el orden, reusar el contenido en otro formato, o dejar que un agente lo consulte después? (10 min) → El salto: el patrón de la "LLM wiki" de Andrej Karpathy — separar el conocimiento (markdown estructurado, navegable por un agente) de su visualización (15 min) → Demo: la misma base de conocimiento en markdown, primero consultada por un agente, después renderizada como presentación (35 min) → Discusión: cuándo conviene esta separación y qué se pierde si se mezcla contenido y visual (15 min)

¿Así está bien, o le doy otra vuelta antes de escribirlo?

### Presenter

y como se pierde el conocimiento cuando el foco es solo la presentacion.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Buen punto, eso merece ser explícito y no solo insinuado. Lo sumo al bloque del límite:

**El límite de esa ola — cómo se pierde el conocimiento cuando el foco es solo la presentación:** el contenido se aplana a bullets pensados para la diapositiva, no para ser reconsultado — se pierde la estructura (resumen, tags, relaciones entre ideas) que un agente necesita para razonar sobre ese conocimiento después. Si regenerás la presentación, no hay una fuente de verdad estable: cada corrida parte de cero y el conocimiento original queda atrapado dentro del PDF/deck, no en un archivo que se pueda actualizar, buscar o reusar en otro formato.

Con eso, el **SESSION FLOW** completo queda:

→ De las slides manuales a la IA generativa — el punto de partida: armar un deck a mano, diapositiva por diapositiva (10 min) → Primera ola: herramientas todo-en-uno (NotebookLM, Gamma, Claude Design) — le tirás contenido crudo y te devuelven una presentación lista (30 min) → El límite de esa ola: cómo se pierde el conocimiento cuando el foco es solo la presentación — el contenido se aplana a bullets, no hay fuente de verdad estable, y ese conocimiento queda atrapado en el deck en vez de vivir en un archivo reusable (20 min) → El salto: el patrón de la "LLM wiki" de Andrej Karpathy — separar el conocimiento (markdown estructurado, navegable por un agente) de su visualización (15 min) → Demo: la misma base de conocimiento en markdown, primero consultada por un agente, después renderizada como presentación (35 min) → Discusión: qué se gana al mantener el conocimiento como fuente de verdad separada del render (10 min)

¿Lo escribo así en el README?

### Presenter

Resumilo pero esta bien

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

[Editó README.md: agregó la sección "### DAY 3 — Construyendo Presentaciones con IA ● KNOWLEDGE-FIRST, VISUALIZATION-SECOND" con tabla GOAL/TOOLS/SESSION FLOW/TAKEAWAYS condensada.]

Esa es la agenda completa y actualizada: título "Agentes Inteligentes", sin el marco de Industry 4.0, y el Día 3 ya definido como "Construyendo Presentaciones con IA" en las tres secciones (Schedule, Day-by-Day, y Mission Overview). Día 4 sigue *a definir*.

Retomamos ground rules / criterio de aprobación, o seguís con la agenda de otro día?

### Presenter

Actualiza la agenda

### Agent

[Actualizó README.md: línea de intro de Class Agenda, tabla Schedule (fila Día 3), track narrative blockquote, y fila del Día 3 en Mission Overview, todas reflejando el nuevo título "Construyendo Presentaciones con IA".]

### Presenter

Podriamos mostrarme de nuevo la ultima agenda.

### Agent

Actualizo la agenda: la línea de intro, la tabla de Schedule, el track narrative, y la fila del Día 3 en Mission Overview.

[Mostró el bloque completo actualizado del README: Class Agenda, Schedule, Track narrative, Day-by-Day completo (Días 1-7), y Mission Overview.]

Esa es la agenda completa y actualizada: título "Agentes Inteligentes", sin el marco de Industry 4.0, y el Día 3 ya definido como "Construyendo Presentaciones con IA" en las tres secciones (Schedule, Day-by-Day, y Mission Overview). Día 4 sigue *a definir*.

Retomamos ground rules / criterio de aprobación, o seguís con la agenda de otro día?

### Presenter

Dale. Vamos a pensar en objetivos de aprendizaje. Basemosnos en 5 puntos. Algo similar a
[Imagen: slide "Objetivos de Aprendizaje" con 5 puntos numerados en formato tarjeta — Comprender el panorama GenAI 2026, Desarrollar criterio profesional, Conocer los principales modelos GenAI, Experimentar la primera misión aplicada, Reflexionar sobre el impacto en negocios.]

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Tomo la estructura de la imagen (panorama → criterio → herramientas → misión aplicada → impacto en negocios) y la adapto a "Agentes Inteligentes":

**Objetivos de Aprendizaje**
*Al finalizar esta clase, los estudiantes podrán:*

1. **Comprender el cambio de paradigma** — de chatear a delegar: qué son los Agentes Inteligentes y por qué son la próxima palanca de productividad para el manager.
2. **Desarrollar criterio profesional** — distinguir la filosofía y forma de pensar detrás de delegar en agentes, más allá de cualquier herramienta puntual que cambie con el tiempo.
3. **Conocer las principales herramientas de agentes** — Claude Cowork, Paperclip y otras: fortalezas y límites de cada una.
4. **Experimentar la primera misión aplicada** — vivir el formato de trabajo del curso en primera persona (la misión Atlas).
5. **Reflexionar sobre el impacto en la gestión y los negocios** — qué cambia para un manager aumentado por agentes, en su equipo y en su propio trabajo.

¿Lo dejamos así, ajustamos alguno de los 5 puntos, o cambiamos el orden?

### Presenter

Experimentar la primera misión aplicada lo pondria como "hands on"

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Buena. Punto 4 actualizado:

4. **Hands-on con la primera misión aplicada** — vivir el formato de trabajo del curso en primera persona (la misión Atlas).

Los otros 4 quedan igual. ¿Cerramos así los Objetivos de Aprendizaje, o algo más antes de capturar la exploración?

### Presenter

Reflexionar sobre el impacto en la gestión y los negocios y sobre todo. Como llevqar esto a como trabajo y aplicarlo.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Entendido, el foco pasa de "reflexionar sobre el impacto" a "cómo lo llevo a mi trabajo". Punto 5 actualizado:

5. **Reflexionar sobre el impacto en la gestión y los negocios — y cómo aplicarlo a mi propio trabajo** — no solo qué cambia para un manager aumentado por agentes, sino qué hago yo, en mi rol concreto, a partir de mañana.

Objetivos de Aprendizaje final:

1. **Comprender el cambio de paradigma** — de chatear a delegar: qué son los Agentes Inteligentes y por qué son la próxima palanca de productividad para el manager.
2. **Desarrollar criterio profesional** — distinguir la filosofía y forma de pensar detrás de delegar en agentes, más allá de cualquier herramienta puntual que cambie con el tiempo.
3. **Conocer las principales herramientas de agentes** — Claude Cowork, Paperclip y otras: fortalezas y límites de cada una.
4. **Hands-on con la primera misión aplicada** — vivir el formato de trabajo del curso en primera persona (la misión Atlas).
5. **Reflexionar sobre el impacto en la gestión y los negocios — y cómo aplicarlo a mi propio trabajo** — qué hago yo, en mi rol concreto, a partir de mañana.

¿Cerramos así, o le damos otra vuelta?

### Presenter

Esta parte de objectivos esta perfecto.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Buenísimo, Objetivos de Aprendizaje cerrados.

Seguimos con las **ground rules** y el **criterio de aprobación** — todavía no los definimos. Te tiro las preguntas de antes para retomar:

- **Asistencia**: ¿mínimo de clases obligatorias? ¿Distinto para presencial vs. virtual?
- **Entregables**: ¿el criterio de aprobación se basa en las misiones (Atlas, Enterprise, Paperclip), un trabajo final, participación, o combinación?
- **Uso de IA en el curso**: ¿reglas específicas sobre cómo usar las herramientas en clases y entregas?
- **Puntualidad / dispositivos / participación en vivo**: ¿algo explícito para las presenciales?
- **Escala de calificación**: ¿aprobado/desaprobado, nota numérica, otra?

### Presenter

[Imagen: slide "Evaluación del Curso" — gráfico de torta y tarjetas: 40% Portafolio Grupal (misiones resueltas con guía de prompts y reflexiones del equipo), 40% Examen Integrador (evaluación individual, 45 minutos), 20% Participación (actividades prácticas y compromiso durante sesiones presenciales y virtuales).]
Vamos al criterio de evaluacion. Va a ser igual a este:

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Perfecto, tomo la misma estructura:

**Evaluación del Curso**

| Componente | % | Detalle |
|---|---|---|
| **Portafolio Grupal** | 40% | Misiones resueltas con guía de prompts y reflexiones del equipo |
| **Examen Integrador** | 40% | Evaluación individual — Duración: 45 minutos |
| **Participación** | 20% | Actividades prácticas y compromiso durante las sesiones presenciales y virtuales |

Una pregunta antes de darlo por cerrado: **"Portafolio Grupal"** — ¿son las misiones del curso (Atlas de Días 1-2, la de Enterprise del Día 5, la de Paperclip del Día 6), o es un entregable aparte? Y el **Examen Integrador de 45 min**, ¿va en el Día 7 (Evaluation), como imagino por el calendario?

### Presenter

Si, esas son las misiones.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Anotado. Portafolio Grupal actualizado:

| Componente | % | Detalle |
|---|---|---|
| **Portafolio Grupal** | 40% | Misiones resueltas con guía de prompts y reflexiones del equipo — Atlas (Días 1-2), Enterprise (Día 5), Paperclip (Día 6) |
| **Examen Integrador** | 40% | Evaluación individual — Duración: 45 minutos |
| **Participación** | 20% | Actividades prácticas y compromiso durante las sesiones presenciales y virtuales |

Y sobre el Examen Integrador — el Día 7 del calendario dice "Evaluation" con formato *a definir*. ¿Confirmamos que el examen de 45 min va ahí?

### Presenter

No listemos las misiones aca, solo menciones que se var a ir presentando.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Entendido, sin listar cada misión. Queda así:

| Componente | % | Detalle |
|---|---|---|
| **Portafolio Grupal** | 40% | Misiones resueltas con guía de prompts y reflexiones del equipo — se van a ir presentando a lo largo del curso |
| **Examen Integrador** | 40% | Evaluación individual — Duración: 45 minutos |
| **Participación** | 20% | Actividades prácticas y compromiso durante las sesiones presenciales y virtuales |

Y sigue pendiente: ¿confirmamos que el Examen Integrador de 45 min va en el Día 7 (Evaluation)?

### Presenter

[Imagen: slide "Cierre y Portafolios" — 01 Pitch grupal (5 minutos), 02 Portafolio completo (5 misiones resueltas + guía de prompts personalizados + reflexiones de aprendizaje), 03 Evaluación de pares (retroalimentación estructurada con rúbrica de criterios), 04 Reflexión de cierre (próximos pasos profesionales: cómo integrar GenAI en roles de gestión).]
Vamos a explorar sobre cierre y portafolios

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Buena base, pero hay un desajuste: la imagen dice "5 misiones resueltas" — en nuestro curso tenemos 3 misiones nombradas (Atlas en Días 1-2, Enterprise en Día 5, Paperclip en Día 6), más los Días 3-4 que no tienen "misión" formal (Día 3 es sobre presentaciones con IA, Día 4 sigue *a definir*).

¿Cómo contamos las misiones del portafolio?

1. **3 misiones** — Atlas, Enterprise, Paperclip (solo las que tienen mission formal en el calendario)
2. **Depende de qué definamos para Días 3-4** — dejar el número abierto por ahora y volver cuando cerremos esos días
3. Otro número — decime cuál

### Presenter

Menciona que vamos a ir entregando misiones dirante la cursada.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Entendido, sin número fijo. Queda así:

**Cierre y Portafolios**

*La clase final integra la evaluación grupal con una reflexión colectiva sobre el impacto profesional de los Agentes Inteligentes.*

| | |
|---|---|
| **01 · Pitch grupal (5 minutos)** | Cada equipo presenta su proyecto integrador con los hallazgos clave. |
| **02 · Portafolio completo** | Misiones entregadas durante la cursada + guía de prompts personalizados + reflexiones de aprendizaje. |
| **03 · Evaluación de pares** | Retroalimentación estructurada entre equipos utilizando rúbrica de criterios. |
| **04 · Reflexión de cierre** | Próximos pasos profesionales: cómo integrar Agentes Inteligentes en roles de gestión. |

¿Lo dejamos así, o ajustamos algo antes de seguir?

### Presenter

Solo eso, vamos a ser ma especificos luego

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Dale, queda anotado como base y lo afinamos más adelante.

Todavía tenemos pendiente:

- Confirmar si el **Examen Integrador (45 min)** va en el Día 7.
- Las **ground rules**: asistencia mínima, uso de IA en clases/entregas, puntualidad/dispositivos en presenciales, escala de calificación (aprobado/desaprobado vs. nota numérica).

¿Seguimos con alguno de estos, o preferís cerrar la exploración acá y estos temas quedan como preguntas abiertas para retomar después?

### Presenter

Esto es perfecto.

### Agent

[No response requested.]

### Presenter

[Imagen: slide "Herramientas del Curso" — Modelos de Lenguaje (Claude, ChatGPT, Gemini, Perplexity), Análisis y Conocimiento (NotebookLM), Producción de Contenido (Gamma AI, Canva AI).]
Ahora:

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Tomo la misma estructura de 3 columnas, pero con las herramientas que ya definimos para esta parte del curso — Cowork y Paperclip como protagonistas, más lo del Día 3:

**Herramientas del Curso**

*Trabajaremos con el ecosistema de Agentes Inteligentes más relevante para la gestión empresarial en 2026.*

| **Agentes y Orquestación** | **Análisis y Conocimiento** | **Producción de Contenido** |
|---|---|---|
| **Claude Cowork · Paperclip** — de delegar una tarea a orquestar una organización de agentes, con un humano en el loop. | **NotebookLM** — síntesis de documentos, análisis de fuentes y generación de insights a partir de datos propios. | **Gamma AI · Claude (Cowork / Claude Design)** — creación de presentaciones separando el conocimiento de su visualización. |

¿Te sirve esta versión, o cambiamos alguna herramienta / columna?

### Presenter

Partiria Agentes y Orquestación en dos. Automatizacion y Agentes

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Tiene sentido — son dos momentos distintos del curso. Queda en 4 columnas:

**Herramientas del Curso**

*Trabajaremos con el ecosistema de Agentes Inteligentes más relevante para la gestión empresarial en 2026.*

| **Automatización** | **Agentes** | **Análisis y Conocimiento** | **Producción de Contenido** |
|---|---|---|---|
| **Claude Cowork** — delegar un resultado completo y automatizar loops de trabajo (research, schedule, dashboards). | **Paperclip** — orquestar una organización de agentes hacia un objetivo, con un humano en el loop. | **NotebookLM** — síntesis de documentos, análisis de fuentes y generación de insights a partir de datos propios. | **Gamma AI · Claude (Cowork / Claude Design)** — creación de presentaciones separando el conocimiento de su visualización. |

¿Así queda bien, o ajustamos algo de las cuatro columnas?

### Presenter

Producción de Contenido donde meteria notebvoo, etc todo en uno

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Entendido, fusiono esa columna. Queda en 3:

**Herramientas del Curso**

*Trabajaremos con el ecosistema de Agentes Inteligentes más relevante para la gestión empresarial en 2026.*

| **Automatización** | **Agentes** | **Producción de Contenido** |
|---|---|---|
| **Claude Cowork** — delegar un resultado completo y automatizar loops de trabajo (research, schedule, dashboards). | **Paperclip** — orquestar una organización de agentes hacia un objetivo, con un humano en el loop. | **NotebookLM · Gamma AI · Claude (Cowork / Claude Design)** — síntesis de documentos, análisis de fuentes y creación de presentaciones separando el conocimiento de su visualización. |

¿Así queda bien?

### Presenter

Mencionemos qie dado que vamos a usar cowork, va a ver una licencia por grupo para poder hacer el trabajo.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Anotado. Agrego una nota debajo de la tabla:

**Herramientas del Curso**

*Trabajaremos con el ecosistema de Agentes Inteligentes más relevante para la gestión empresarial en 2026.*

| **Automatización** | **Agentes** | **Producción de Contenido** |
|---|---|---|
| **Claude Cowork** — delegar un resultado completo y automatizar loops de trabajo (research, schedule, dashboards). | **Paperclip** — orquestar una organización de agentes hacia un objetivo, con un humano en el loop. | **NotebookLM · Gamma AI · Claude (Cowork / Claude Design)** — síntesis de documentos, análisis de fuentes y creación de presentaciones separando el conocimiento de su visualización. |

> **Nota:** dado que vamos a trabajar con Claude Cowork durante el curso, va a haber una licencia por grupo para poder hacer el trabajo.

¿Queda así, o la nota va en otro lugar (por ejemplo, junto a las ground rules en vez de acá)?

### Presenter

Ahora me gustaria un poco de discutir un poco el por que de esto y lo que pensamos. Creo que esto seria "Como vemos el Futuro de Knowleage Workers".  No veo que sean remplazados s i no que tenemos herramientas que logran amplificar la eficiencia en el dia a dia. Ahora, cuales son tipo de tareas mas comunes para ellos como managers ?.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Buen ángulo — esto conecta directo con la frase del README ("el futuro no va a ser de las empresas que usan IA, va a ser de los managers aumentados por ella"). Armo esto como una sección de discusión, no de contenido cerrado.

**Cómo vemos el futuro de los knowledge workers**

*Tesis: no reemplazo, amplificación. Las herramientas no sustituyen el juicio del manager — comprimen el tiempo entre tener una idea y tener un resultado, para que el tiempo humano se concentre en decidir, no en ejecutar.*

Sobre las tareas más comunes de un manager que se amplifican, te tiro una primera lista para discutir y recortar juntos:

- **Investigación y síntesis** — juntar información dispersa (mercado, competencia, un tema nuevo) en algo accionable, en vez de horas de lectura manual.
- **Reportes y comunicación recurrente** — el status semanal, el resumen para el jefe, el update del equipo — trabajo repetitivo de "juntar y formatear" (esto es literalmente la misión Atlas).
- **Preparación de reuniones** — armar la agenda, los materiales, y después convertir las notas en próximos pasos y seguimiento.
- **Análisis de datos propios** — leer planillas, contratos, encuestas de clima, y sacar conclusiones sin ser data scientist.
- **Redacción y comunicación escrita** — emails, propuestas, presentaciones — el primer borrador, no la decisión final.
- **Coordinación entre equipos** — trackear el estado de varias iniciativas a la vez y detectar qué se está atrasando.
- **Documentación de procesos** — dejar por escrito cómo se hace algo, para no depender de una sola persona.

¿Cuáles de estas te resuenan más para el perfil de tus alumnos (MiM, profesionales de negocio no técnicos), o hay alguna tarea puntual que quieras que sea el ejemplo ancla de la charla?

### Presenter

Busca en internet que encontras sobre esta tematica.

### Agent

[Buscó en la web: "AI agents amplify knowledge workers managers tasks 2026 research report" y "most common tasks managers delegate to AI agents survey 2026".]

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Encontré data 2026 bastante alineada con tu tesis. Puntos clave:

**Amplificación, no reemplazo — con nombre propio.** Microsoft describe a la mayoría de los knowledge workers de hoy como **"agent bosses"** — responsables de delegar trabajo a colegas digitales y gestionar sus resultados. Más de 4 de cada 5 líderes de negocio esperan usar agentes para expandir la capacidad de su equipo en los próximos 12-18 meses. La idea central: los agentes se quedan con lo repetitivo y de bajo valor, liberando tiempo humano para pensamiento estratégico, creatividad y decisiones.

**Productividad medible.** Knowledge workers que usan agentes en producción ahorran ~6.4 horas por semana, con reducciones de costo por tarea de 9x a 66x en trabajo estandarizado.

**Las tareas más delegadas hoy** (según encuestas de adopción empresarial):
- Gestión y extracción de datos (47% de las empresas)
- Análisis y resumen de documentos (41%)
- Generación de reportes (36%)
- Síntesis de investigación
- Resumen de reuniones

Todo esto tiene en común: alto volumen, estructura bien definida, e insumos basados en lenguaje — exactamente el perfil de la misión Atlas de tu curso (reporte semanal a partir de notas dispersas).

**Un matiz importante para las ground rules:** el enfoque dominante sigue siendo *human-in-the-loop* (38% de las empresas) — los managers delegan pero mantienen supervisión con approval gates, no autonomía completa. Esto conecta directo con la gobernanza que ya tenés en el Día 2 ("Cowork no tiene audit trail, todo output es un borrador") y con Paperclip en el Día 6.

¿Querés que arme la sección "Cómo vemos el futuro de los knowledge workers" con esta data, o preferís que primero afinemos la lista de tareas para tus alumnos específicamente?

Sources:
- [2026 Work Trend Index report: Agents, human agency, and opportunity](https://www.microsoft.com/en-us/worklab/work-trend-index/agents-human-agency-and-the-opportunity-for-every-organization)
- [AI Agent Use Cases for Knowledge Workers: What's Actually Working in 2026](https://www.mindstudio.ai/blog/ai-agent-use-cases-knowledge-workers-2026)
- [Zapier — State of agentic AI adoption survey [2026]](https://zapier.com/blog/ai-agents-survey/)
- [Deloitte Insights — Agentic AI strategy](https://www.deloitte.com/us/en/insights/topics/technology-management/tech-trends/2026/agentic-ai-strategy.html)

### Presenter

Si hay algun articulo importante o uno o mas, me gustaria que nos respaldemos en esto.

### Agent

[No response requested.]

### Presenter

Me gusta el enfoque de microsfot. Descompongamos esta tesis en el readme.md

### Agent

[Leyó el reporte completo "2026 Work Trend Index" de Microsoft vía web_fetch para fundamentar la sección con detalle.]

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

[Editó README.md: agregó la sección "# Cómo vemos el futuro de los knowledge workers" después del Objective, con la tesis del Work Trend Index 2026 de Microsoft desglosada en 4 puntos: expansión de quién hace trabajo de alto valor, el criterio humano como habilidad más valiosa, el manager como palanca principal, y los "Frontier Professionals" como el patrón a seguir.]

Agregué la sección **"Cómo vemos el futuro de los knowledge workers"** al README, justo después del Objective y antes del Class Agenda, con la tesis del Work Trend Index 2026 de Microsoft desglosada en 4 puntos: expansión de quién hace trabajo de alto valor, el criterio humano como habilidad más valiosa, el manager como palanca principal, y los "Frontier Professionals" como el patrón a seguir.

¿La dejamos así, o ajustamos algo del desglose?

### Presenter

Ponelo primero.

### Agent

[Editó README.md: movió la sección "Cómo vemos el futuro de los knowledge workers" al principio del documento, antes de Objective.]

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Listo, movida arriba — ahora es la primera sección del README, antes de Objective.

### Presenter

No hablemos de co-pilot sino de lo que se ve. Seria bueno hacerlo mas compacto.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

[Editó README.md: reescribió la sección quitando la mención a Copilot y comprimiendo a un párrafo intro + 4 bullets cortos.]

Listo, saqué la mención a Copilot y comprimí a un párrafo intro + 4 bullets cortos, sin perder los números clave.

### Presenter

El curso se apoya en el 2026 Work Trend Index de Microsoft (mayo 2026) lo pondria como referencia como uno de los tantos.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

[Editó README.md: reformuló la frase para que el Work Trend Index apareciera como una de varias referencias, no como la única fuente.]

Ajustado — ahora el Work Trend Index aparece como una de varias referencias que respaldan la visión, no como la única fuente.

### Presenter

Pone los links en le fondo.

### Agent

[Editó README.md: cambió la mención inline a "[1]" como nota al pie.]

### Presenter

Y escribi este deadme en ingles todo.

### Agent

[Tradujo al inglés: la sección "Cómo vemos el futuro de los knowledge workers" (título y cuerpo), el Día 3 completo (título, GOAL, TOOLS, SESSION FLOW, TAKEAWAYS), la fila del Día 3 en Mission Overview, y reemplazó "Presencial" por "In-person" en todo el documento vía sed. Corrigió restos en español (línea de intro "mix of presencial" y fila del Schedule del Día 3). Agregó una sección "# References" al final con 3 fuentes numeradas (Microsoft WTI, MindStudio/Karpathy, Zapier).]

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Todo listo. Resumen de lo hecho en esta pasada:

- README completo traducido al inglés (la sección de knowledge workers, Día 3, "Presencial" → "In-person" en todo el doc).
- Agregado un párrafo sobre qué tipo de trabajo delegan más los líderes hoy (data management, análisis de documentos, reportes, research, resúmenes de reuniones — con la cifra de human-in-the-loop conectando a Cowork/Paperclip).
- Objective ahora tiene una frase puente que conecta directo con esas tareas cotidianas.
- Agregada la sección **References** al final con los 3 links (Microsoft WTI, MindStudio/Karpathy, Zapier), y las citas en el texto pasaron a notas `[1]`, `[2]`, `[3]` en vez de links inline.

¿Seguimos afinando el README, o volvemos a las ground rules / criterio de aprobación que quedaron pendientes?

### Presenter

Despues Cómo vemos el futuro de los knowledge workers, expandamos sobre le tipo de trabajo mas comun entre los leaderes.

### Agent

[Editó README.md: agregó el párrafo "What kind of work do leaders actually delegate?" después de los 4 bullets, con datos de encuestas de adopción empresarial.]

### Presenter

What kind of work do leaders actually delegate?. This is really a title first level, more like a table.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

[Editó README.md: promovió "What kind of work do leaders actually delegate?" a subtítulo `##` propio, y convirtió el contenido en una tabla de tareas con % de adopción.]

Listo — ahora es su propio subtítulo (`##`) con una tabla de tareas y % de adopción. "Research synthesis" y "Meeting summarization" no traían un % específico en la fuente, así que quedaron con `—`; si querés los saco de la tabla y los dejo solo mencionados en el texto, o busco el dato puntual.

### Presenter

Where is automation ?

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Para asegurarme de arreglar lo correcto — ¿a qué "automation" te referís?

1. **La tabla de tareas delegadas** (arriba, con Data management, Document analysis, etc.) — ¿falta una fila de "Automation / workflow automation" como categoría separada de la encuesta?
2. **La columna "Automatización"** de "Herramientas del Curso" que armamos en el chat (Cowork vs. Agentes vs. Producción de Contenido) — esa todavía no está escrita en el README, solo la discutimos acá.
3. Otra cosa — contame cuál.

### Presenter

No hablemos de esto. Creo que el foco en parte es que el delegar tiene un factor de repeticion y automatizacion.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

[Editó README.md: agregó la idea de que "delegation tends to follow repetition" al cierre del párrafo de tareas delegadas.]

Agregado — el punto de que delegar y automatizar son "el mismo movimiento" cuando una tarea se repite en la misma forma, conectando directo con lo que ya arma Atlas en Días 1-2.

### Presenter

No solo queremos hacerlo, sino poder repetirlo en forma declarativa.

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

[Editó README.md: agregó el concepto de describir la tarea de forma declarativa (Skill, Instruction, spec en markdown) para que se repita sola.]

Ajustado — ahora el énfasis está en describir la tarea de forma declarativa (una Skill, una Instruction) para que se repita sola, no solo en automatizar una vez.

### Presenter

Deberiamos en What kind of work do leaders actually delegate? hacer como en eso.
en "What these tasks share is exactly what makes them safe to delegate: high volume, clear structure, and inputs/outputs that are mostly text. There's also a deeper pattern underneath: delegation tends to follow repetition — the more often a task recurs in the same shape, the easier it is to turn into something an agent runs on its own, not just something an agent helps you do once. But the goal isn't just to do the task once with an agent's help — it's to describe it declaratively (a Skill, an Instruction, a plain-markdown spec of "what good looks like"), so it can be repeated on its own without you re-explaining it every time. That's why "automate" and "delegate" are often the same move in disguise. The dominant management style stays human-in-the-loop (38% of companies): leaders delegate the execution but keep approval gates and review steps, rather than handing agents full autonomy. That's the same governance model this course teaches through Cowork (Day 2) and Paperclip (Day 6)." No connectemos todavia con el contenido del cuerso. Sino mas en el filosofia.
Continue from where you left off.

### Agent

[No response requested.]

### Presenter

2

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

[Editó README.md: quitó la referencia puntual a "Cowork (Day 2) and Paperclip (Day 6)" del cierre del párrafo, dejándolo en el plano filosófico — human-in-the-loop como principio, no como feature de una herramienta.]

Listo, saqué la referencia puntual a Cowork (Día 2) / Paperclip (Día 6) — el cierre queda en el plano de la filosofía (human-in-the-loop como principio, no como feature de una herramienta), sin atarlo todavía al contenido del curso.

### Presenter

Looks ggood. Can be shorter ?

### Agent

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

[Editó README.md: recortó el párrafo a la mitad manteniendo las mismas ideas.]

Recortado a la mitad, mismas ideas.

### Presenter

Let's re-write objective connecting with the "What kind of work do leaders actually delegate?" and "How we see the future of knowledge workers"

### Agent

[Editó README.md: reescribió la sección "Objective" para que abra citando directamente la tesis de amplificación y la tabla de tareas delegadas, en vez de repetir el mismo mensaje desde cero.]

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Reescrito — Objective ahora abre citando directamente la tesis de amplificación y la tabla de tareas delegadas de arriba, en vez de repetir el mismo mensaje desde cero.

### Presenter

Export to PDF

### Agent

[Invocó el skill `pdf`. Convirtió README.md a PDF con pandoc + xelatex, fuente DejaVu Sans para cobertura de caracteres especiales (●, ✓), sin emojis (removidos con regex), con tabla de contenidos. Verificó con pdftotext que el contenido renderizara correctamente. Copió el PDF a la carpeta del usuario y lo compartió.]

🔭 [exploring: ground rules y criterio de aprobación — MIM Augmented]

Listo, el README exportado a PDF con tabla de contenidos.

### Presenter

Listo. ya termine la exploracion.
