# memory.md — cowork-part2

**Current step:** 7 — Render complete (html-strict, repolished)
**Topic:** Profundización de Cowork e introducción a Claude Code.
**Folder:** talks/cowork-part2/
**Started:** 2026-08-03

---

## Talk briefing

El objetico es profundizar cowork y una introduccion a Clade Code. Los 3 pilares de cowork que extienden lo que se presento en co-work y chat. Los temas a tocar es Artifacts, Conocimiento: Memoria vs Instructions vs Files , Uso de Plugins + un quiz al principio para confirmar revisar lo aprendido. Antes de empezar, mostrame en el prompt que entendiste.

---

## 2026-08-03 — Step 1 (Frame)
- Status: complete
- Asks log:
  - 2026-08-03 11:53 — "¿Qué querés que cubra esta continuación? Contame objetivo, ideas centrales, casos o ejercicios que querés sumar, y cualquier cierre que tengas en mente." → "El objetico es profundizar cowork y una introduccion a Clade Code. Los 3 pilares de cowork que extienden lo que se presento en co-work y chat. Los temas a tocar es Artifacts, Conocimiento: Memoria vs Instructions vs Files , Uso de Plugins + un quiz al principio para confirmar revisar lo aprendido. Antes de empezar, mostrame en el prompt que entendiste."
  - 2026-08-03 11:54 — "¿Cuál carpeta elegís?" → "cowork-part2"
- What was decided: Nueva clase como continuación de Cowork y chat; se creó la carpeta `cowork-part2`.
- Key inputs: Orden confirmado: review inicial; profundización en los tres pilares de Cowork (Artifacts, conocimiento y plugins); introducción a Claude Code.
- Files created/modified: `talks/cowork-part2/memory.md`; estructura de `research/`, `images/` y `output/`.
- Pending open questions: Materiales adicionales y alcance específico de la introducción a Claude Code.

## 2026-08-03 — Step 2 (Collect)
- Status: complete
- Asks log:
  - 2026-08-03 11:54 — "¿Cómo querés aportar el material de referencia para esta clase?" → "Listo. Ahi subi el contenido del LLM. El mismo tiene una disertacion de que deberia contener a alto nivel."
- What was decided: Usar el contenido del LLM subido como fuente principal de la clase.
- Key inputs: Archivo `research/llm-chats/chat-export-2026-08-03.zip`.
- Files created/modified: `talks/cowork-part2/research/llm-chats/chat-export-2026-08-03.zip`.
- Pending open questions: Confirmar si también se integrarán explícitamente las presentaciones previas como fuentes.

## 2026-08-03 — Step 3 (Corpus)
- Status: complete
- Asks log:
  - 2026-08-03 11:57 — "¿Confirmás que avancemos al armado del borrador?" → "si, avancemos en borrado."
- What was decided: Se estructuró la conversación de planificación como fuente canónica para el borrador.
- Key inputs: Una exportación de LLM con la secuencia, los conceptos, ejemplos y correcciones para la clase.
- Files created/modified: `talks/cowork-part2/research/corpus/chat-export-2026-08-03.zip.md`; `talks/cowork-part2/research/corpus/chat-export-2026-08-03.zip/images/`.
- Pending open questions: Verificar contra documentación oficial cualquier afirmación cambiante sobre funcionalidades de producto antes de fijarla en las diapositivas.

## 2026-08-03 — Step 4 (Draft)
- Status: awaiting_presenter
- Asks log:
  - 2026-08-03 11:58 — "¿Cómo querés llamar a esta clase?" → "2. Cowork: Artifacts, conocimiento y extensiones"
  - 2026-08-03 12:00 — "¿Cuándo se presenta esta clase?" → "Seria Aug 4, 2026"
  - 2026-08-03 12:02 — "¿Qué modo preferís para construir el borrador?" → "Quiero 1. El order es el quiz con las preguntas aprobadas el el chat, conocimiento, plugins, artifacts y Claude Code."
  - 2026-08-03 12:13 — "Revisá draft.md y confirmá si querés aplicar cambios o pasar a Review." → "Hacer que las respuestas del quiz sean mas desafiantes."
  - 2026-08-03 12:16 — "Revisá el quiz actualizado y confirmá si querés más cambios o pasar a Review." → "Fijate de un grafico al la derecha que sea el numero de la pregunta. La seccion deberia llarse Quiz"
  - 2026-08-03 12:18 — "Revisá las placas numéricas y confirmá si querés más cambios o pasar a Review." → pending
- What was decided: Modo B, borrador completo del agente. Orden: quiz, conocimiento, plugins, Artifacts y Claude Code.
- Key inputs: Título de clase: "Cowork: Artifacts, conocimiento y extensiones". Fecha: 2026-08-04.
- Files created/modified: `talks/cowork-part2/draft.md`; `talks/cowork-part2/images/quiz-pregunta-1.svg` a `quiz-pregunta-5.svg`; `talks/cowork-part2/output/slide-model.draft.json`; `talks/cowork-part2/output/html/index.html`.
- Pending open questions: Elegir el plugin de la demo, decidir si el Live Artifact se construye en vivo y definir el proyecto mínimo para Claude Code.

## 2026-08-03 — Step 2 (Collect — reabierto)
- Status: complete
- Asks log:
  - 2026-08-03 — Presenter retomó la sesión y pidió volver al paso de recolección de información.
  - 2026-08-03 — "¿Cómo querés sumar el material nuevo?" → "No, vamos a siguiente paso."
- What was decided: No se agregó material nuevo; el corpus queda como estaba (una fuente: la exportación del chat de planificación). Step 3 sin trabajo pendiente — `articles/` y `web/` vacíos.
- Note: existe `draft-old.md` en la carpeta (el `draft.md` previo fue renombrado); al retomar Draft hay que decidir si se restaura ese borrador o se redacta uno nuevo. La pregunta pendiente sobre las placas numéricas del quiz aplica solo si se restaura el borrador previo.

## 2026-08-03 — Step 4 (Draft — segunda ronda, borrador nuevo)
- Status: awaiting_presenter
- Asks log:
  - 2026-08-03 — "¿Retomamos el borrador existente (draft-old.md) o redactamos uno nuevo desde el corpus?" → "Redactar uno nuevo desde el corpus"
  - 2026-08-03 — "Revisá el nuevo draft.md y confirmá si querés cambios o pasar a Review." → pending
- What was decided: Draft v2 redactado desde cero a partir del corpus (Modo B); `draft-old.md` se conservó como referencia, sin tocar. El quiz aprobado se reusó casi verbatim con sus SVG numéricos.
- Key inputs: Corpus (chat de planificación); quiz y feedback ya aprobados de draft-old.md; learnings (fuente visible para estadísticas — sin cifras externas en este deck).
- Estructura: 1. Quiz (6) · 2. Conocimiento (8) · 3. Plugins (5) · 4. Artifacts (7) · 5. Claude Code (7) · Conclusions (2) — 35 láminas.
- Revisión (Composer, scope=full): 1 blocker + 1 major + 3 minors, todos aplicados: claims de producto de Plugins marcados "a confirmar contra doc oficial" y sumados a Open questions (3.1/3.2/3.4, notas 5.2/5.5, 2.5, 4.3/4.4/4.6); H1 de secciones 2 y 5 acortados ("2. Conocimiento", "5. Claude Code"); 2.2+2.3 fusionadas en lámina ancla (ejemplos preservados en notas).
- Files created/modified: `talks/claude-cowork-part2/draft.md` (nuevo, v2).
- Pending open questions: Elegir plugin de la demo; Live Artifact en vivo o no; proyecto mínimo para Claude Code; verificación de claims de producto contra documentación oficial. El output/html/index.html existente corresponde al draft viejo (stale) — se regenerará al pasar a Review.

## 2026-08-03 — Step 5 (Review — ronda 1)
- Status: awaiting_presenter
- Asks log:
  - 2026-08-03 — "¿Está completo el comentario sobre el ciclo de vida de Artifacts y los permisos de Live?" → Se verificó: compartir y permisos están cubiertos, pero falta una lámina explícita de ciclo de vida; pendiente de decisión del presenter.
  - 2026-08-03 — "El ciclo de vida no está completo como lámina explícita: ¿lo agregamos antes de cerrar Review?" → "Quiero que hagas el research y completes el slide"
  - 2026-08-03 — "Revisá la lámina nueva sobre el ciclo de vida de Artifacts. ¿Querés otros cambios o cerramos Review?" → pending
  - 2026-08-03 — Presenter pidió preview → se generó la vista html-strict --draft (41 láminas, luego 43).
  - 2026-08-03 — "Revisar el feedback" → 12 bullets en draft.md aplicados (11 closed, 1 [open] por texto truncado en 3.4 "Dos tipos de Artifact": «No veo nigun slide sbore»).
  - 2026-08-03 — Feedback por chat: conceptos básicos en "Software hecho de archivos"; nueva lámina Claude Code "para quién / resultado final"; directiva deck-wide "más contenido y visuales" → aplicados.
- What was decided: Secciones reordenadas — Artifacts antes que Plugins. Eliminados: El Project delimita, Caso Faro (sweep completo), Caso informe comercial, Tracker de competidores, Demo de Live Artifact (todo a Cut material). Nuevas: Memory ×3 (qué es / cómo se usa / cómo se administra), Datos o procedimiento, Ciclo de vida de Artifacts, Compartir Artifacts, Credenciales de conexión, Plugins de Anthropic, Claude Code "Para quién y qué produce". Pasada de enriquecimiento deck-wide (tablas, cards, 7 ASCII, 4 generate-image).
- Research: 8 registros web nuevos en research/corpus/ (live artifacts, publicar/compartir, plugins docs/blog/directorio/uso/administración, Claude Code Desktop). Claims "a confirmar" de Plugins y UI de Claude Code resueltos contra doc oficial.
- Estructura: 1. Quiz (7) · 2. Conocimiento Persistente (9) · 3. Artifacts (9) · 4. Plugins (7) · 5. Claude Code (8, incluida la demo) · Conclusions (2) — 42 láminas.
- Files created/modified: draft.md; research/corpus/*.web.md ×8; output/slide-model.draft.json; output/html/index.html (vista en vivo refrescada, con guard de hash para iframe).
- Pending open questions: alcance de memoria por Project sin confirmar contra doc; plugin para ejercicio de auditoría (4.4); proyecto mínimo demo Claude Code; preparación del ejemplo real de Live Artifact. Lámina 4.5 con 11 cards excede el envelope (~6) — candidata a split en próxima ronda.
