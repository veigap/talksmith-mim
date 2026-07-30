# memory.md — intro-curso-mim

**Current step:** 7 — Render in_progress
**Topic:** Presentación de la materia — ground rules, criterio de aprobación, calendario
**Folder:** talks/intro-curso-mim/
**Started:** 2026-07-15

---

## 2026-07-30 — Step 6 (Polish) reejecutado sobre el `draft.md` vigente
- Status: complete
- Asks log:
  - 2026-07-30 17:31 — "Volve a polish para que se revise el final.md" → Polish reejecutado de punta a punta.
- What was decided: `final.md` se rederivó desde el `draft.md` vigente y se revisó como entregable. El único diagrama y los dos asides atmosféricos conservaron sus recursos existentes porque sus fuentes no cambiaron. La revisión detectó residuos de continuaciones `Resolution:` que la limpieza estándar no consumía en feedback de nivel Thesis/Agenda/Sección; se corrigió la pasada para este entregable y se verificó que no quedara ningún registro de trabajo visible. Las notas de imágenes pendientes se actualizaron al estado real: ambos asides están resueltos.
- Key inputs: `talks/intro-curso-mim/draft.md`; diagrama `images/s1-4-1-agentes-personas-agencia.{ascii,svg,png}`; asides `images/s1-1-1-aside.png` y `images/s6-1-1-aside.png` con sus sellos vigentes.
- Files created/modified: `talks/intro-curso-mim/final.md`, `talks/intro-curso-mim/memory.md`. `draft.md` permaneció read-only.
- Validation: 6 secciones y 13 slides de contenido; 0 feedback residual; 0 fences ASCII activas; 0 directivas de generación activas; 0 referencias de imagen con extensión incompatible. SHA-256 de `final.md`: `d9dc7fd3182a40c6def174dcf4e6acdbc4013025435d498034364029e5920395`, idéntico al que alimentó el último render HTML válido.
- Pending open questions: se conservan las decisiones de contenido registradas en `# Open questions`; próximo paso: Step 7 Render, formato a elegir por el presentador.

## 2026-07-30 — Step 6 (Polish) desde la ronda de Review de esta sesión
- Status: complete
- Ask: "Listo. Pasa a polish" — seguido de un pedido a futuro: "Y al finalizer, genera el HTML-string del resultado."
- `draft.md` → `final.md`: copia verbatim hecha al inicio del paso; `draft.md` queda read-only desde entonces.
- Anti-slop: ofrecida, el presentador respondió "No." — no se aplicó.
- Diagram pass: 1 diagrama render-driving (`s1-4-1-agentes-personas-agencia`, slide "4. La ejecución se delega. La agencia crece.", Sección 1). El SVG/PNG ya existían en `images/` con el digest ASCII vigente (reutilizados, sin redibujar); se dispatcheó igual una crítica ciega (`talksmith:diagram-critic`) sobre el PNG — veredicto `clean` — y se persistió el critique log en `images/.critique/s1-4-1-agentes-personas-agencia.md` (no existía todavía para este slide_id). `stamp-renders` y `cleanup` corridos; `final.md` referencia el PNG (no el SVG).
- Image pass: 2 directivas `generate-image` (bienvenida 1.1, Q&A ahora 6.1). Ambos assets ya existían de un pase anterior (`s1-1-1-aside.png`, y `s6-2-1-aside.png` que se **renombró a `s6-1-1-aside.png`** — junto con su `.imgprompt`/`.imgstamp` — porque la Sección 6 "Preguntas" quedó con una sola slide tras la restructuración de esta ronda de Review). Descripciones sin cambios → idempotencia confirmada (`prepare-render-args` reusó ambos, 0 regeneraciones). `stamp-renders` y `cleanup` corridos; ambas directivas reescritas a `aside:` + `generate-source:`.
- Final tidy-up: `rescue-open` → sin bullets `[open]` para rescatar. Se retiraron los **21 bloques** `Presenter feedback` de `final.md` (12 en forma `### Presenter feedback` de slide + 9 en forma `**Presenter feedback:**` de Thesis/Agenda/Sección) vía script determinístico que preserva el separador `---` siguiente; verificado post-hoc: 0 ocurrencias de la cadena, separadores `---` intactos (23). Auditoría de refs de imagen: 4 refs locales, todas bajo `images/` con extensión `.png`/`.jpg` (0 `.svg`/`.webp`/`.avif`/`.heic`). Se actualizaron dos notas ahora stale en `# Open questions` / Sources del Q&A que decían "imagen pendiente" — ambas imágenes ya estaban resueltas.
- Deliverable: `final.md` — 6 secciones, 13 slides de contenido (594 líneas). Sin campos de feedback, sin fences ASCII activos, sin directivas `generate-image` activas.
- Files created/modified: `talks/intro-curso-mim/final.md`, `talks/intro-curso-mim/images/s6-1-1-aside.{png,imgprompt,imgstamp}` (renombrados desde `s6-2-1-*`), `talks/intro-curso-mim/images/.critique/s1-4-1-agentes-personas-agencia.md` (nuevo), `talks/intro-curso-mim/memory.md`.
- Deuda heredada sin tocar (fuera de alcance, ya flagueada en la ronda de Review de esta sesión): referencias numéricas stale en `# Open questions` / `# Cut material` de rondas anteriores a la restructuración de hoy.
- Next: pedido explícito del presentador de generar el render `html-strict` de `final.md` — Step 7.

## 2026-07-30 — Step 7 Render HTML strict (sobre el `final.md` de esta ronda)
- Status: complete
- Ask: "Y al finalizer, genera el HTML-string del resultado." (pedido a futuro capturado durante Polish).
- FILL: se derivó `output/slide-model.json` desde el `final.md` recién pulido (19 slides: 6 `section-agenda` + 13 de contenido). Cambios respecto de la vista previa de Step 5.5: la slide "La ejecución se delega. La agencia crece." pasó de `code-example` (placeholder de borrador con el ASCII crudo) a `content-image` con el PNG real; las dos slides con `generate-image` pasaron a llevar su campo `aside` con el PNG ya generado.
- Render: `build_html.py --talk talks/intro-curso-mim` → `output/html/index.html`, 19 slides.
- Validation: JSON válido; autores en dos líneas separadas presentes; 4 imágenes de contenido embebidas como data URIs (aside bienvenida, portada Robot-Proof, diagrama de agencia, aside Q&A); 0 referencias a `.svg` en el HTML.
- Files created/modified: `talks/intro-curso-mim/output/slide-model.json`, `talks/intro-curso-mim/output/html/index.html`, `talks/intro-curso-mim/memory.md`.
- Next: Step 8 Learnings (promoción opcional a `config/learnings.md` / knowledge-library).

---

## 2026-07-30 — Review: ronda de notas del presentador (7 bullets, 6 cerrados, 2 open)
- Status: awaiting_presenter
- Ask: "Revisa las notas que puse" — el presentador había editado `draft.md` directamente con bullets de feedback sin estampar.
- Contabilidad vía `talksmith:feedback-cycle` (`find-open` → `stamp` → fix → `close` → `mirror-row`); `find-closed-unmirrored` limpio al cierre.
- **6 bullets cerrados y aplicados:**
  - Slide "La IA expande, el juicio sube de precio" (Sección 1) — eliminada. Contenido (66/58 y 50/46/86, Microsoft WTI 2026) archivado en Cut material.
  - Slide "La tecnología funcionó. El valor no llegó." (Sección 1) — eliminada. Contenido (Bain 2026 + 67/32 Microsoft, incluido el caso Amazon de los speaker notes) archivado en Cut material.
  - Slide "Delegar no es abdicar" (Sección 1) — eliminada. Contenido (38% human-in-the-loop, Zapier 2026 + corroboración de Bain) archivado en Cut material. **Sección 1 pasa de 9 a 6 slides**; slides 7 y 8 renumeradas a 5 y 6 (Entonces qué delegan primero los líderes / Delegar es no volver a explicar).
  - Slide "Qué herramienta para qué trabajo" (Sección 4) — se quitó el item "Producción de Contenido" (NotebookLM · Gamma · Claude, archivado en Cut material) y "Automatización y Análisis de Datos" se dividió en dos filas separadas. La lámina mantiene 3 filas.
  - Slide "Lo que se llevan" (Sección 4) — eliminada. Contenido (4 bullets) archivado en Cut material. **Sección 4 pasa de 3 a 2 slides.**
  - Slide "Cómo se construye la nota" (Sección 5) — texto del ítem Portafolio Grupal corregido (typos: "entregando"→"entregadas", "profilio"→"portafolio", "5 MIM" interpretado como "5 minutos" por consistencia con el pitch grupal de la Sección 6) y compactado a una oración.
- **Barrida de renumeración** aplicada en Sección 1 (headings, sin más referencias cruzadas activas a las slides eliminadas dentro de esa sección). **Nota de alcance:** las secciones `# Open questions` / `# Cut material` heredan referencias numéricas a slides de rondas anteriores a esta sesión que ya estaban desalineadas con los títulos actuales (numeración de Sección 1 previa a la incorporación del arco Robot-Proof) — esa deuda es anterior a esta ronda y no se tocó; si se quiere, vale una pasada de auditoría de referencias dedicada.
- **2 bullets quedaron `[open]` inicialmente y se resolvieron después, en la misma sesión:**
  - Slide "El portafolio se construye desde el Día 1" (Sección "Cierre y Portafolios"): *"Borrar este slide y seccion."* — ambiguo (la sección tenía 2 slides: esta y "¿Preguntas?"). Pregunté al presentador vía opción múltiple; eligió **"Q&A como sección propia"**. Se borró la slide y la sección; "¿Preguntas?" pasó a ser la nueva Sección 6 "Preguntas" de una sola slide, cerrando el deck. Contenido del portafolio (pitch grupal, entregables, evaluación de pares, reflexión de cierre) archivado en Cut material. Cerrado y espejado.
  - Slide "La herramienta cambia. El criterio queda." (Sección 2): *"Creo es importante marcar que"* — bullet incompleto. El presentador completó la idea por chat: el curso es muy hands-on/práctico, con herramientas para construir agentes que resuelvan los problemas de la Sección 1, pero el foco sigue siendo el criterio y los conceptos, no la herramienta. Se agregó esa idea al Content y a speaker notes; **título cambiado a "El vehículo, no el destino"** (retoma la metáfora ya presente en las notas). Cerrado y espejado.
- **Deck final de esta ronda: 6 secciones / 13 slides de contenido** (antes: 6 secciones / 16 slides). Sin bullets `[open]` restantes; `find-closed-unmirrored` limpio.
- Key inputs: `draft.md` (8 bullets del presentador en total: 7 en campos `Presenter feedback`, uno detectado tarde, más la clarificación por chat de dos de ellos); `config/feedback-backlog.md`; decisión del presentador vía pregunta de opción múltiple (Sección 6) y vía chat (Sección 2, slide 1).
- Files created/modified: `talks/intro-curso-mim/draft.md` (Sección 1: 9→6 slides; Sección 4: 3→2 slides; Sección "Cierre y Portafolios" → "Preguntas" de 2→1 slide; Agenda actualizada; contenido movido a Cut material; Open questions actualizado), `config/feedback-backlog.md` (8 filas espejadas), `talks/intro-curso-mim/memory.md`. **No modificado:** `final.md`, `output/` (siguen correspondiendo al ciclo publicado anterior; desactualizados respecto de este draft).
- Pending open questions: todas las heredadas de rondas anteriores (escala de calificación, mínimo de asistencia, uso de IA en entregas, Día 4, Examen Integrador Día 7, marco narrativo del curso, rúbrica de evaluación de pares — ahora sin lámina propia —, y las decisiones de redacción/imagen listadas en `# Open questions` de `draft.md`). **Deuda pre-existente detectada, no corregida en esta ronda:** varias referencias numéricas en `# Open questions` / `# Cut material` (p. ej. "slide 1.4", "1.6") datan de una numeración de la Sección 1 anterior a la incorporación del arco Robot-Proof y ya no coinciden con los títulos actuales — anterior a esta sesión; valdría una auditoría de referencias dedicada.

---

## 2026-07-30 — Regeneración con iconos offline de Talksmith 0.69.0
- Status: complete
- Render: se regeneró el HTML completo con el conjunto local de iconos incorporado en Talksmith 0.69.0.
- Icon fix: `¿Qué hace valioso al capital humano?` muestra un icono SVG de psicología; el deck no contiene el círculo placeholder que antes se veía como bullet.
- Preserved decisions: la apertura conserva su icono oculto, los autores siguen en dos líneas, el texto de *Robot-Proof* no tiene `:` inicial y el diagrama de agencia permanece vectorial.
- Validation: frescura y las tres pruebas del sitio pasaron; una regresión específica falla si reaparece el círculo placeholder.
- Hosting: la regeneración se publicó y se verificó en la URL estable. La slide de capital humano contiene un icono SVG real y el deck público tiene cero círculos placeholder.
- Public URL: https://agentes-inteligentes-mim.pveiga244377.chatgpt.site/presentation

---

## 2026-07-30 — Regeneración con Talksmith 0.68.3
- Status: complete
- Plugin review: `0.68.3` corrige el uso de PNG en lugar de SVG dentro de los decks HTML y agrega namespaces a los identificadores internos de cada SVG para evitar colisiones.
- Render: se regeneraron `output/slide-model.json` y `output/html/index.html`; el diagrama `La ejecución se delega. La agencia crece.` ahora se incorpora como SVG vectorial.
- Preserved decisions: autores en dos líneas completas, apertura sin icono ni sangría adicional y explicación de `Problemas bien definidos` sin `:` inicial.
- Validation: frescura, enumeraciones, cobertura de campos, cobertura de imágenes y las tres pruebas del sitio pasaron.
- Hosting: la regeneración se publicó y se verificó en la URL estable. La respuesta pública contiene el diagrama SVG vectorial, los autores en líneas separadas y el texto de *Robot-Proof* sin `:` inicial.
- Public URL: https://agentes-inteligentes-mim.pveiga244377.chatgpt.site/presentation

---

## 2026-07-30 — Ajustes tipográficos finales y publicación
- Status: complete
- Cover: la autoría quedó en dos líneas completas: `Paulo Veiga, IAE Business School` y `Claudio Righetti, IAE Business School`.
- Opening: se ocultó el icono automático del callout de `El futuro no va a ser...` y se eliminó el espacio lateral que generaba su sangría.
- Robot-Proof: los tres conceptos terminan con punto y sus explicaciones comienzan directamente con mayúscula; ya no aparece `:` al inicio del cuerpo.
- Validation: pasaron la frescura del modelo, el build del sitio y las tres pruebas de HTML. La URL pública estable fue verificada después del despliegue.
- Public URL: https://agentes-inteligentes-mim.pveiga244377.chatgpt.site/presentation

---

## 2026-07-30 — Presentación completada y publicada
- Status: complete
- Ask: "Let's consider the presentation completed after the publish".
- Final correction: se eliminó `Bienvenidos.` del cuerpo de la primera slide; `Bienvenidos al trabajo aumentado` queda como única bienvenida y la tesis comienza directamente con `El futuro no va a ser...`.
- Render: `draft.md`, `final.md`, `output/slide-model.json` y `output/html/index.html` quedaron sincronizados con Talksmith 0.68.2. El deck conserva 24 slides, autores `Paulo Veiga y Claudio Righetti`, el orden aprobado y las animaciones de enumeración.
- Hosting: el deck se sirve como HTML directo desde `/presentation`, sin iframe contenedor. La raíz pública redirige a esa ruta y ambas respuestas fueron verificadas después del despliegue.
- Public URL: https://agentes-inteligentes-mim.pveiga244377.chatgpt.site
- Learnings: no se promovió una nueva regla; las iteraciones de títulos y el ajuste de redundancia fueron decisiones específicas de este Talk. La promoción al knowledge library se omitió al cerrar la presentación.

---

## 2026-07-30 — Claudio Righetti agregado a la autoría
- Status: complete
- Author line: `Paulo Veiga y Claudio Righetti, IAE Business School` en el frontmatter del Talk y en la portada renderizada. `config/profile.md` no se modificó.
- Render: `draft.md`, `final.md`, el modelo y el HTML se regeneraron; los recursos visuales existentes se reutilizaron.
- Hosting: el deck se publicó directamente como `deck-authors.html`, sin iframe contenedor, y se verificó la línea de autores en el archivo público.
- Cache note: la raíz del dominio conservó temporalmente la redirección anterior; el enlace directo actualizado es https://agentes-inteligentes-mim.pveiga244377.chatgpt.site/deck-authors.html.

---

## 2026-07-30 — Títulos conectados y publicación directa sin iframe
- Status: complete
- Titles: la pantalla global 6 pasó de `Más ejecución, más agencia` a `La ejecución se delega. La agencia crece.`; la pantalla global 9 pasó de `¿Qué delegan los líderes?` a `Entonces, ¿qué delegan primero los líderes?`. Contenido, fuentes y notas no cambiaron.
- Render: `draft.md`, `final.md`, el modelo y el HTML se regeneraron; las comprobaciones de contenido, campos e imágenes pasaron.
- Hosting: se eliminó el iframe contenedor. La raíz pública redirige directamente al HTML autocontenido `deck-connected-titles.html`, publicado como asset nuevo para evitar caché del CDN.
- Verification: la URL pública resolvió al deck directo y devolvió el orden y los títulos nuevos.
- Public URL: https://agentes-inteligentes-mim.pveiga244377.chatgpt.site

---

## 2026-07-30 — Corrección de numeración global y publicación v5
- Status: complete
- Clarification: el presentador contaba las pantallas globales del deck, incluyendo portada y agenda de sección. La pantalla 4 era `Más ejecución, más agencia`; el pedido original movía las pantallas globales 6 y 7, no las slides internas 1.6 y 1.7.
- Corrected order: pantalla 3 `Bienvenidos`; 4 `Human capital is not a toxic asset`; 5 `¿Qué hace valioso al capital humano?`; 6 `Más ejecución, más agencia`; 7 `La IA expande, el juicio sube de precio`; 8 `La tecnología funcionó. El valor no llegó.`; 9 `¿Qué delegan los líderes?`.
- Render: `draft.md`, `final.md`, el modelo y el HTML se regeneraron con el orden global correcto. El diagrama de agencia se reutilizó con su nuevo identificador de slide.
- Publishing: el CDN conservaba `deck.html` aun con query string. Se publicó el deck corregido bajo el asset nuevo `deck-global-order.html` y la página principal apunta a ese archivo. La URL pública se verificó directamente y devuelve el orden corregido.
- Public URL: https://agentes-inteligentes-mim.pveiga244377.chatgpt.site

---

## 2026-07-30 — Polish, HTML 0.68.1 y publicación pública v2
- Status: complete
- Ask: "Listo, aplica el cambio y publica".
- Polish: `draft.md` se aprobó y volvió a derivarse en `final.md`. Se reutilizaron el diagrama y las dos imágenes editoriales existentes porque sus huellas no cambiaron; la portada de *Robot-Proof* se conservó. Se eliminó un diagrama generado huérfano y no quedan bloques de feedback, ASCII activo ni directivas de generación activas en el entregable.
- Render: `html-strict` produjo 24 slides más portada con Talksmith 0.68.1. La sección 1 quedó reordenada como 1.3 → evidencia organizacional y delegación → arco de *Robot-Proof*. Los 28 elementos de las nueve slides enumerativas incluyen ahora al primer elemento en la secuencia de aparición.
- Validation: pasaron frescura, enumeraciones, cobertura de campos, cobertura de imágenes, build del sitio y dos pruebas sobre la presentación publicada.
- Publishing: el sitio público existente se actualizó a la versión 2 y mantiene la URL https://agentes-inteligentes-mim.pveiga244377.chatgpt.site.
- Next: Step 8 Learnings.

---

## 2026-07-30 — Review: reordenamiento de las slides 1.4–1.7
- Status: awaiting_presenter
- Ask: "Slide 6 & 7 tiene que ir despues del 3".
- What changed: las anteriores slides 1.6 `La tecnología funcionó. El valor no llegó.` y 1.7 `¿Qué delegan los líderes?` se movieron después de la 1.3 y ahora son 1.4 y 1.5. El arco de *Robot-Proof* pasó a 1.6 y 1.7. No se modificaron contenido, fuentes ni speaker notes.
- Review bookkeeping: feedback cerrado y espejado en `config/feedback-backlog.md`.
- Render state: `final.md`, `output/slide-model.json`, `output/html/index.html` y la publicación pública siguen correspondiendo al ciclo anterior hasta volver a ejecutar Polish, Render y publicación.

---

## 2026-07-30 — Step 7 Render HTML strict + publicación pública
- Status: complete
- Ask: "Podrias publicar el html el un url publica ?"
- Style: `html-strict`
- Render: se regeneró `output/slide-model.json` desde el `final.md` vigente. Resultado: 24 slides modeladas más portada, 25 pantallas visibles. Las comprobaciones de frescura, enumeraciones, cobertura de campos y cobertura de imágenes pasaron.
- Output local: `talks/intro-curso-mim/output/html/index.html`.
- Publishing: se creó un sitio público reutilizable bajo `output/public-site/`, se validó su build y se publicó la versión 1.
- Public URL: https://agentes-inteligentes-mim.pveiga244377.chatgpt.site
- Next: Step 8 Learnings.

## 2026-07-30 — Step 6 Polish desde Review aprobado
- Status: complete
- Ask: "listo. movamos todos los estadios hasta llegar a la presentacion"
- Review closure: no había feedback abierto ni cierres sin espejar. `draft.md` quedó congelado y `final.md` se regeneró desde esa fuente.
- Diagram pass: se encontró un diagrama. Su ASCII coincide con el render ya validado, por lo que se reutilizaron `images/s1-2-1-agentes-personas-agencia.svg/.png` y se renovó la huella sin redibujarlo.
- Image pass: las dos directivas atmosféricas coincidían con sus huellas y reutilizaron `images/s1-1-1-aside.png` y `images/s6-2-1-aside.png`. La portada nueva `images/robot-proof-cover.jpg` quedó incorporada como aside izquierdo de la slide 1.4.
- Final tidy-up: se reemplazó el fence ASCII por su imagen PNG, se resolvieron las dos directivas de generación, se retiraron 26 bloques/campos de feedback y cuatro restos de `Resolution:` que el helper dejó fuera de sus bloques. No quedan fences ASCII activos, directivas activas `generate-image`, campos de feedback ni referencias a formatos incompatibles.
- Deliverable: `final.md` contiene 6 secciones y 18 slides de contenido, con 4 referencias visuales locales existentes.
- Next: Step 7 Render requiere una elección explícita de estilo.

## 2026-07-30 — Review: pasada completa de títulos
- Status: awaiting_presenter
- Ask: aprobar la revisión de títulos a partir del nuevo gancho de Robot-Proof.
- What changed: se aplicó la secuencia completa acordada. En la sección 1 se renombraron 1.1, 1.2, 1.6, 1.8 y 1.9; se conservaron 1.3, 1.4, 1.5 y 1.7. También se reemplazaron los títulos genéricos de objetivos, cronograma, reglas, herramientas, evaluación, portafolio y preguntas.
- Scope: solo cambiaron encabezados visibles y referencias activas dentro del draft. Contenido, fuentes, speaker notes e historial de feedback permanecen intactos.
- Review bookkeeping: feedback cerrado y espejado en `config/feedback-backlog.md`.

## 2026-07-30 — Review: título de la slide 1.5
- Status: awaiting_presenter
- Ask: opción 1 para reemplazar `El criterio es el activo`.
- What changed: la slide 1.5 queda titulada `¿Qué hace valioso al capital humano?`; su remate y sus notas permanecen sin cambios.
- Review bookkeeping: feedback cerrado y espejado en `config/feedback-backlog.md`.

## 2026-07-30 — Review: título definitivo de la slide 1.4
- Status: awaiting_presenter
- Ask: dejar `Human capital is not a toxic asset` en la slide 1.4.
- What changed: la slide 1.4 recuperó ese título. El contenido, la portada y la slide 1.5 permanecen sin cambios.
- Review bookkeeping: feedback cerrado y espejado en `config/feedback-backlog.md`.

## 2026-07-30 — Review: reversión del título de Robot-Proof
- Status: awaiting_presenter
- Ask: "reverti"
- What changed: se revirtió únicamente el último cambio de título. La slide 1.4 vuelve a `El valor humano empieza donde la respuesta no está clara`; las dos slides nuevas, su contenido y la portada permanecen sin cambios.
- Review bookkeeping: feedback cerrado y espejado en `config/feedback-backlog.md`.

## 2026-07-30 — Review: título de Robot-Proof confirmado
- Status: awaiting_presenter
- Ask: reemplazar el título de la slide 1.4 y luego conservarlo.
- What changed: la slide 1.4 queda titulada `Human capital is not a toxic asset`. Se incorporó el artículo `a` para que la frase sea gramaticalmente correcta en inglés; el contenido y la portada no cambiaron.
- Review bookkeeping: feedback cerrado y espejado en `config/feedback-backlog.md`; no quedan cierres sin registrar.

## 2026-07-30 — Review: dos slides de Robot-Proof
- Status: awaiting_presenter
- Ask: agregar dos slides como posiciones 4 y 5; la primera con la portada de *Robot-Proof* a la izquierda y la segunda con el remate sobre capital humano “tóxico”.
- What changed: se agregaron `1.4 El valor humano empieza donde la respuesta no está clara` y `1.5 El criterio es el activo`. La primera desarrolla problemas bien definidos, correlación frente a causalidad y realidades ambiguas. La segunda conserva como tesis proyectada la formulación acordada sobre conocimiento rutinario, metacognición, creatividad, adaptación y juicio.
- Asset: se descargó la portada aportada por el presentador a `images/robot-proof-cover.jpg` (1015×1500) y se vinculó como imagen lateral izquierda de la slide 1.4.
- Sources and precision: se agregó el extracto oficial de Wiley y se distinguió la cita de Ming sobre *human capital* de la síntesis en español. Se evitó la afirmación absoluta de que un modelo nunca puede razonar causalmente; el texto proyectado dice que escalar patrones no garantiza explicación causal ni transferencia cuando cambia el contexto.
- Review bookkeeping: feedback cerrado y espejado en `config/feedback-backlog.md`; no quedan cierres sin registrar.
- Render state: `final.md` y el HTML siguen correspondiendo al ciclo anterior. Próximo paso: revisión del presenter sobre `draft.md`.

## 2026-07-30 — Reapertura a Draft / Review
- Status: awaiting_presenter
- Ask: "Voldamos a Draft."
- What was decided: el Talk vuelve a Step 5 / Review y `draft.md` recupera el rol de fuente autoritativa para la próxima ronda de edición.
- Render state: `final.md`, `output/slide-model.json` y `output/html/index.html` quedan como referencia del ciclo anterior y se consideran obsoletos hasta volver a ejecutar Polish y Render.
- Awaiting presenter: editar `talks/intro-curso-mim/draft.md` directamente o enviar los cambios por chat.

## 2026-07-30 — Step 7 Render HTML strict
- Status: awaiting_presenter
- Ask: "Genera le HTML"
- Style: `html-strict`
- What was done: regenerated `output/slide-model.json` from the current polished `final.md`, producing 22 modeled slides plus the cover (23 displayed screens), then rendered the self-contained HTML deck.
- Model checks: freshness stamp matches `final.md`; degenerate enumeration, field coverage, and image coverage audits all passed.
- Visual QA: checked cover, opening, the wide amplification diagram, the seven-session timeline, and Q&A in desktop and mobile-landscape viewports. The wide diagram was moved to an image-top layout and visible Markdown emphasis was removed from projected text. All 4 rendered images loaded, no slide overflow was detected, and the browser console reported no warnings or errors.
- Output: `talks/intro-curso-mim/output/html/index.html`.
- Awaiting presenter: review the HTML and request any content or visual adjustments before Step 8 Learnings.

## 2026-07-30 — Step 6 (Polish) desde draft reabierto
- Status: complete
- Ask: "Listo. Movamos a la siguiente estapa"
- Review closure: no había feedback nuevo sin estampar. Se registró en `config/feedback-backlog.md` un cierre anterior que faltaba espejar; el control final no encontró cierres sin registrar.
- What was decided: `final.md` se volvió a derivar de `draft.md`; desde la copia, `draft.md` quedó de solo lectura. El entregable conserva 6 secciones / 16 slides.
- Diagram pass: el único diagrama activo, `images/s1-2-1-agentes-personas-agencia.svg/.png`, coincidía con el ASCII vigente y se reutilizó; `final.md` referencia la variante PNG.
- Image pass: se regeneraron los asides de apertura y Q&A en 1024x1536. La primera variante de apertura introdujo una silueta humana, contraria al brief; se corrigió en una segunda y última generación con composición abstracta de flujos, capas y nodos. Assets finales: `images/s1-1-1-aside.png` y `images/s6-2-1-aside.png`, con sidecars y huellas actualizadas.
- Final tidy-up: no había feedback `[open]` para rescatar; se quitaron 24 campos de `Presenter feedback`. El helper dejó dos líneas `Resolution:` huérfanas, que se retiraron de `final.md`; el historial permanece en `draft.md` y en el backlog. La validación final no encontró fences ASCII, directivas activas `generate-image`, campos de feedback, resoluciones huérfanas ni referencias a formatos no compatibles.
- Files created/modified: `config/feedback-backlog.md`, `talks/intro-curso-mim/final.md`, los dos PNG de aside y sus `.imgprompt`/`.imgstamp`, y `talks/intro-curso-mim/memory.md`.
- Pending open questions: se conservan en `final.md` las decisiones de contenido todavía abiertas. Próximo paso: Step 7 Render; `output/slide-model.json` y `output/html/index.html` siguen siendo el render anterior hasta entonces.

## 2026-07-30 — Reapertura a draft stage
- Status: awaiting_presenter
- Ask: "retomemos to draft stage."
- What was decided: el Talk vuelve a Step 5 / Review. `draft.md` vuelve a ser la fuente autoritativa para la siguiente ronda; `final.md`, `output/slide-model.json` y `output/html/index.html` quedan como renders anteriores hasta que se re-corra Polish y Render.
- Current draft state: `draft.md` conserva campos `Presenter feedback` y directivas `generate-image` para la apertura/bienvenida y Q&A. Los assets existentes en `images/` quedan disponibles para reutilizar o reemplazar.
- Awaiting presenter: editar `talks/intro-curso-mim/draft.md` directamente o responder en chat con los cambios que quiere aplicar.

## 2026-07-17 — Draft return + regenerate prompt-driven images
- Status: complete
- Ask: "It's king of returning to draft stage and regenerate all images."
- What was done: treated `draft.md` as the source of truth, regenerated the two prompt-driven aside images using the updated abstract editorial guidance, replaced `images/s1-1-1-aside.png` and `images/s6-2-1-aside.png`, refreshed their `.imgprompt`/`.imgstamp` sidecars, re-derived `final.md` from `draft.md`, refreshed `output/slide-model.json`, and rebuilt `output/html/index.html`.
- Assets: `images/s1-1-1-aside.png` (welcome/opening) and `images/s6-2-1-aside.png` (Q&A) are now 1024×1536 PNGs in the abstract editorial style. Existing diagram asset `images/s1-2-1-agentes-personas-agencia.png` was reused.
- Output: `talks/intro-curso-mim/output/html/index.html` refreshed with 22 modeled slides.

## 2026-07-17 — Draft image prompt guidance updated
- Status: complete
- Ask: "All the prompts in draft.md must be updated to following your guidace on image."
- What changed: updated both `generate-image` directives in `draft.md` (welcome/opening 1.1 and Q&A 6.2) to follow the new preferred aesthetic: abstract editorial vector, symbolic systems, white negative space, black anchor masses, coral/red accents, parallel lines and flow ribbons, no literal classroom/horizon scenes, no readable text/logos/letters/numbers.
- Note: superseded by the following regeneration pass, which updated `final.md`, assets, slide model, and HTML.

## 2026-07-17 — Step 7 Render HTML strict
- Status: complete
- Ask: "generate now the html"
- Style: `html-strict`
- What was done: refreshed `output/slide-model.json` from the current polished `final.md`, checked the structured model for lone-item enumeration mistakes, and rendered the self-contained HTML deck.
- Output: `talks/intro-curso-mim/output/html/index.html` (cover + 22 modeled slides; 6 section roadmap slides + 16 content slides).
- Notes: This render uses the current polished image refs: `images/s1-1-1-aside.png`, `images/s1-2-1-agentes-personas-agencia.png`, and `images/s6-2-1-aside.png`.

## 2026-07-17 — Reapertura a draft.md + revisión visual del Editor
- Status: awaiting_presenter
- Origen: presenter-chat — "Return to draft and editor review if we can add images."
- What was decided: El Talk vuelve a Step 5/Review y `draft.md` es nuevamente el archivo autoritativo. `final.md` y cualquier render previo quedan obsoletos hasta re-correr Step 6 (Polish) desde este draft.
- Visual pass: no se generó ninguna imagen nueva. `images/` solo contiene los renders de diagramas ya existentes; el diagrama `s3-2-1-chat-delegar-orquestar` quedó huérfano porque su slide fue borrada. Con Talksmith 0.65.0, el Editor corrigió el comportamiento conservador anterior: los pedidos atmosféricos sin asset ya no quedan como bloqueo; se expresan como `generate-image`.
- Draft edits: se agregaron dos directivas `generate-image: left`: una en 1.1 "Manos a la obra" para absorber el pedido de bienvenida con imagen, y otra en 6.2 "Q&A" para el cierre. Ambas se generarían recién en Step 6/Polish si hay capacidad de generación de imágenes; si no, el texto sigue funcionando.
- Pending presenter decision: confirmar si la bienvenida queda absorbida en 1.1 o si quiere una lámina "Bienvenidos" separada; confirmar si Q&A debe pasar a formato texto+imagen o volver al hero limpio sin imagen. Para slides de datos, decidir si procesamos/validamos imágenes existentes del corpus (Bain Figura 1, Zapier human-in-the-loop) antes de usarlas.

## 2026-07-17 — Step 6 (Polish) rerun desde draft reabierto
- Status: complete
- Asks log:
  - 2026-07-17 — "¿Querés que haga una pasada anti-slop slide por slide sobre el texto antes de generar/insertar imágenes y limpiar `final.md`?" → "Si"
- What was decided: `final.md` fue re-derivado desde el `draft.md` actual y queda como deliverable autoritativo para render. Deck final: 6 secciones / 16 slides. `draft.md` no se tocó durante Polish.
- Anti-slop pass: aplicada sobre `final.md` antes de renderizar assets. Se limpiaron patrones visibles en lámina: contrastes `no X sino Y`, exceso de segunda persona en copy proyectado, remates con guion largo y frases de densidad baja. Speaker notes, Sources, Open questions y Cut material se preservaron salvo correcciones necesarias de estado.
- Diagram pass: 1 diagrama render-driving en 1.2; se reutilizó el render existente `images/s1-2-1-agentes-personas-agencia.svg/.png`, se validó SVG, aspect audit ok, se estampó el digest actual y `final.md` referencia el PNG Keynote-safe.
- Image pass: 2 imágenes atmosféricas generadas y consolidadas como asides: `images/s1-1-1-aside.png` (bienvenida/apertura) y `images/s6-2-1-aside.png` (Q&A). Las directivas `generate-image` fueron reemplazadas por `aside` refs con `generate-source`.
- Final tidy-up: `rescue-open` no encontró feedback abierto; se eliminaron 24 campos/bloques de `Presenter feedback` de `final.md`; no quedan fences `ascii`, directivas `generate-image`, feedback markers, ni refs a `.svg/.webp/.avif/.heic`. Auditoría de refs: 3 imágenes locales, todas existen.
- Files created/modified: `talks/intro-curso-mim/final.md`, `talks/intro-curso-mim/images/s1-1-1-aside.png`, `talks/intro-curso-mim/images/s1-1-1-aside.imgprompt`, `talks/intro-curso-mim/images/s1-1-1-aside.imgstamp`, `talks/intro-curso-mim/images/s6-2-1-aside.png`, `talks/intro-curso-mim/images/s6-2-1-aside.imgprompt`, `talks/intro-curso-mim/images/s6-2-1-aside.imgstamp`, `talks/intro-curso-mim/memory.md`.
- Pending open questions: se mantienen las decisiones de contenido registradas en `final.md` (escala de calificación, asistencia mínima, política de IA en entregas, Día 4, Examen Integrador Día 7, decisiones de ubicación/renombre, y validación de imágenes de datos como Bain Figura 1). Próximo paso: Step 7 Render, estilo a elegir por el presentador.

## Talk briefing

Esta es realmente la presentacion de la materia, grownd rules, criterio de aprovacion, dias. El caledario, esta definido en el README.md.

---

## 2026-07-15 — Step 1 (Frame)
- Status: complete
- Asks log:
  - 2026-07-15 00:00 — "¿De qué se trata esta clase?" → "Esta es realmente la presentacion de la materia, grownd rules, criterio de aprovacion, dias. El caledario, esta definido en el README.md."
  - 2026-07-15 00:00 — "Nombre de carpeta (kebab-case)" → "intro-curso-mim"
- What was decided: Talk folder `intro-curso-mim` creado. Contenido: presentación de la materia (Industry 4.0 / MIM Augmented), ground rules, criterio de aprobación, y calendario de 7 clases (ya definido en README.md del repo, no requiere fuentes nuevas para el calendario en sí).
- Key inputs: Briefing verbatim del presentador; calendario y estructura del curso ya documentados en `README.md` del working directory (7 sesiones, Atlas mission Días 1-2, etc.).
- Files created/modified: talks/intro-curso-mim/ (tree), talks/intro-curso-mim/memory.md
- Pending open questions: none

## 2026-07-15 — Step 2 (Collect)
- Status: in_progress
- Asks log:
  - 2026-07-15 00:00 — "¿Cómo querés traer material — archivos, chats exportados, una URL, o explorar en vivo conmigo?" → "explorar en vivo conmigo" (opción 4)
- What was decided: Sesión de exploración en vivo capturada en `research/llm-chats/explore-ground-rules-criterio-aprobacion-2026-07-15.md`. Cubrió, en orden: calendario del curso, cambio de título de la materia a "Agentes Inteligentes" (profile.md Subject actualizado), reescritura del README (título, remoción del marco Industry 4.0, definición del Día 3 "Building Presentations with AI" basado en el patrón LLM wiki de Karpathy), foco/objetivo de la segunda parte de la materia, Objetivos de Aprendizaje (5 puntos), Evaluación del Curso (40% Portafolio Grupal / 40% Examen Integrador / 20% Participación — base, sin cerrar si el examen va en Día 7), Cierre y Portafolios (base), Herramientas del Curso (Automatización / Agentes / Producción de Contenido + nota de licencia Cowork por grupo — no escrita aún en README), sección "How we see the future of knowledge workers" + "What kind of work do leaders actually delegate?" en README con research web (Microsoft 2026 Work Trend Index, MindStudio/Karpathy, Zapier), traducción completa del README al inglés, y exportación del README a PDF.
- Key inputs: Dos artículos leídos vía web_fetch (MindStudio sobre LLM wiki de Karpathy; Microsoft 2026 Work Trend Index completo). Dos búsquedas web sobre tareas delegadas a agentes por managers. Cuatro imágenes de referencia de slides de la primera parte del curso (formato ancla para Objetivos de Aprendizaje, Evaluación, Cierre y Portafolios, Herramientas del Curso).
- Files created/modified: config/profile.md (Subject), README.md (título, estructura completa, sección knowledge workers + tabla de tareas delegadas, Día 3, referencias, traducción a inglés), README.pdf, talks/intro-curso-mim/research/llm-chats/explore-ground-rules-criterio-aprobacion-2026-07-15.md
- Pending open questions:
  - Ground rules todavía sin definir: asistencia mínima, uso de IA en clases/entregas, puntualidad/dispositivos en presenciales, escala de calificación.
  - Confirmar si el Examen Integrador (45 min) va en el Día 7 (Evaluation).
  - "Herramientas del Curso" (Automatización/Agentes/Producción de Contenido) y "Cierre y Portafolios" fueron acordados en el chat pero no están escritos todavía en ningún archivo del Talk — falta decidir dónde viven (¿README, o contenido de `draft.md` en Step 4?).
  - Objetivos de Aprendizaje y Evaluación del Curso (40/40/20) cerrados en el chat pero tampoco persistidos fuera de esta transcripción — están disponibles en el archivo de exploración para que el Editor los use en Step 4.

- Asks log:
  - 2026-07-15 00:10 — "Suma como fuentes los articulos referenciados en el readme." → confirmado, se capturaron las 3 URLs de la sección References del README.
  - 2026-07-15 00:12 — "¿Sumás más material, o pasamos al Paso 3 (Corpus)?" → "No, listo"
- What was decided: Presenter confirmó fin de Collect. Avanza a Step 3.
- Files created/modified (cont.): talks/intro-curso-mim/research/web/microsoft-work-trend-index-2026/ (metadata.yaml, original.html, page.md, assets/), talks/intro-curso-mim/research/web/karpathy-llm-wiki-mindstudio/ (metadata.yaml, original.html, page.md, assets/), talks/intro-curso-mim/research/web/zapier-agentic-ai-adoption-survey-2026/ (metadata.yaml, original.html, page.md, assets/)
- Status: complete

## 2026-07-15 — Step 3 (Corpus)
- Status: complete
- Asks log:
  - 2026-07-15 00:15 — "¿Qué hacemos con las imágenes pendientes de los 3 artículos web — procesarlas ahora, solo texto, o dejarlo para más adelante?" → "Dejarlo para más adelante" (opción 3)
- What was decided: Librarian corrió Fase 1 (texto) sobre las 4 fuentes crudas. 4 registros creados en research/corpus/. Las 33 imágenes de los 3 artículos web quedan extraídas en disco pero sin transcribir (`<!-- pending: process_images -->`) — se procesan más adelante si hace falta para las slides.
- Key inputs: 4 fuentes (1 chat export, 3 capturas web). research/articles/ vacío, correctamente salteado.
- Files created/modified: talks/intro-curso-mim/research/corpus/explore-ground-rules-criterio-aprobacion-2026-07-15.md.md (+ companion images/ vacía), talks/intro-curso-mim/research/corpus/microsoft-work-trend-index-2026.web.md (+ companion images/, 6 archivos), talks/intro-curso-mim/research/corpus/karpathy-llm-wiki-mindstudio.web.md (+ companion images/, 12 archivos), talks/intro-curso-mim/research/corpus/zapier-agentic-ai-adoption-survey-2026.web.md (+ companion images/, 15 archivos)
- Pending open questions:
  - Imágenes de los 3 artículos web: transcripción diferida (process_images) hasta que se necesite para slides.
  - Ground rules sin resolver: asistencia mínima, uso de IA en clases/entregas, puntualidad/dispositivos, escala de calificación.
  - Verificar antes de citarlos en la clase: cifras "6.4 horas ahorradas", "9x-66x reducción de costo", "agent bosses" no están respaldadas literalmente en el texto capturado del reporte de Microsoft — revisar contra el original antes de usarlas como definitivas.
  - Confirmar si el Examen Integrador (45 min) va en el Día 7.
  - Día 4 del calendario sigue sin definir.
  - "Herramientas del Curso" y "Cierre y Portafolios" acordados en el chat pero no escritos aún fuera de la transcripción de exploración.

## 2026-07-15 — Step 4 (Draft)
- Status: complete
- Modo: **C — Presenter Outline**
- Asks log:
  - 2026-07-15 00:20 — "Modo de draft (A/B/C)" → "C" (Presenter Outline)
  - 2026-07-15 00:22 — "Nombre de esta clase (class)" → "Agentes Inteligentes - Bienvenidos"
  - 2026-07-15 00:24 — "Fecha de dictado (date)" → "Sáb 1 Ago 2026" (2026-08-01)
- Presenter outline (verbatim):
  - Que pensamos y por que vemos importamte (lo que pusimos en el readme) — "Seguro aca podemos expandir a 3 slides con datos etc."
  - Objectivo de Aprendizaje (lo discutimos)
  - Cronograma.
  - Evaluacion del Curso
  - Cierre y Portafolios
  - Herramientas del Curso
- Nota del presenter: "Titulos que me gustaria que este, pero eso puede ser mas de 1 slide"
- What was decided: `draft.md` completo en español, 6 secciones / 12 slides, siguiendo los 6 títulos del outline del presentador en su orden original. Tesis: amplificación, no reemplazo — el curso enseña la forma de pensar para delegar y orquestar, no una herramienta. Estructura: S1 "Qué pensamos y por qué lo vemos importante" (3 slides, per pedido explícito del presentador: tesis + 4 ideas con datos + qué delegan los líderes) · S2 "Objetivos de Aprendizaje" (2 slides: Foco de la materia + los 5 objetivos) · S3 "Cronograma" (2 slides: las 7 sesiones + el arco Chat→Delegar→Orquestar con las 3 misiones) · S4 "Evaluación del Curso" (1 slide, 40/40/20) · S5 "Cierre y Portafolios" (1 slide, 4 pasos) · S6 "Herramientas del Curso" (1 slide, 3 columnas + nota de licencia por grupo) · Conclusions (2 slides: "Lo que se llevan" + "Manos a la obra"). Dos diagramas ASCII (ecuación de la agencia en 1.1; arco del curso en 3.2), ambos con `ascii-note`; sin imágenes del corpus usadas (los candidatos de Zapier están sin transcribir y en inglés). Fact-check aplicado: solo se usaron cifras respaldadas por el corpus (66/58, 50/46, 86, +17/+22/+30, 67 vs 32, 47/41/36, 38 human-in-the-loop); las cifras marcadas por el librarian (6,4 h, 9x–66x, "agent bosses") quedaron fuera de toda slide y registradas en Open questions + Cut material.
- Key inputs: `research/corpus/explore-ground-rules-criterio-aprobacion-2026-07-15.md.md` (fuente primaria — objetivos, evaluación, cierre y portafolios, herramientas, foco de la materia, "lo que se llevan", nota de licencia); `README.md` de la raíz (secciones "How we see the future of knowledge workers" + "What kind of work do leaders actually delegate?" → S1; tabla Schedule + Track narrative + Mission Overview → S3; frase de cierre del Objective → conclusions.2); `research/corpus/microsoft-work-trend-index-2026.web.md` y `research/corpus/zapier-agentic-ai-adoption-survey-2026.web.md` (respaldo de datos de S1); `config/profile.md` (presenter, audience, duration, idioma español).
- Revisión post-Composer (`scope=full`, 2026-07-15): se aplicaron 10 ítems del punch-list ([blocker] de ground rules excluido — surfaced al presentador aparte). Cambios estructurales: **secciones reordenadas** (1 Qué pensamos y por qué → 2 Objetivos → 3 Cronograma → **4 Herramientas del Curso** → 5 Evaluación → 6 Cierre y Portafolios) para que Cowork/Paperclip se presenten antes de que el arco de 3.2 los nombre. **Sección 1 pasó de 3 a 6 slides**: la vieja 1.3 se dividió en tres (tabla de delegación / repetición declarativa / human-in-the-loop 38%) y la vieja 1.2 en dos (ideas 1+2 se quedan; idea 3 "el manager es la palanca" promovida a slide propia con 67/32 de titular; idea 4 Frontier plegada a speaker notes). **Atribución de fuente visible en lámina** para toda estadística (learning `Fuente visible en lámina para toda estadística`), distinguiendo *Microsoft WTI 2026* (n≈20.000) de *Microsoft People Science 2025* (n=1.800) y *Zapier 2026*. Objetivo 1 extendido a "de chatear a delegar **y orquestar**" para que 2.2 y 3.2 nombren el mismo arco de tres estadios que la Tesis. Cuatro títulos acortados a presupuesto (H1 ≤25 / H2 ≤40). 2.1 "Foco de la materia" conservada pero adelgazada (dos párrafos de prosa → speaker notes, deduplicados). Día 5 nombrado una sola vez, con cada misión pareada a su título en español (Atlas / Enterprise / Paperclip). Deck resultante: 6 secciones / 15 slides (13 de contenido + 2 de conclusiones). Fact-check intacto: ninguna cifra no sustanciada llegó a lámina.
- Files created/modified: talks/intro-curso-mim/draft.md (creado; reestructurado tras revisión del Composer), talks/intro-curso-mim/memory.md
- Pending open questions:
  - **Ground rules siguen sin definir y no hay slide que las cubra** — asistencia mínima, uso de IA en clases/entregas, puntualidad/dispositivos, escala de calificación (aprobado/desaprobado vs. numérica). El briefing original pedía que esta clase las cubriera: decidir en Step 5 si va una sección nueva o se comunican por otro canal. Si va, ahora caería entre la Sección 5 (Evaluación) y la 6 (Cierre).
  - **`README.md` de la raíz no tiene registro en `research/corpus/`** — lo citan las slides 1.2, 1.3, 1.4, 1.5, 3.1, 3.2 y conclusions.2 sin protección contra drift. Correr el librarian sobre `README.md` y re-apuntar las citas (trabajo de librarian, no del editor).
  - **Slide 1.2, idea 1**: el titular del README ("la IA expande **quién** puede hacer trabajo de alto valor" — acceso) excedía a sus cifras (66/58 miden **cuánto** trabajo hacen los usuarios existentes, y son auto-reportadas). Se suavizó a "expande **cuánto** trabajo de alto valor podés hacer". Confirmar con el presentador si mantiene la versión suavizada o vuelve a su redacción original asumiendo el claim más amplio.
  - Confirmar si el Examen Integrador (45 min) va en el Día 7 — afecta slides 5.1 y 3.1.
  - Día 4 sigue sin definir: aparece como "A definir" en 3.1 y ausente del arco de 3.2.
  - Cantidad de misiones del portafolio deliberadamente abierta; rúbrica de evaluación de pares sin definir (6.1, punto 03).
  - El curso quedó sin marco narrativo (I4.0 borrado, "Escalera" rechazada) — 2.2, 3.2 y la Agenda usan Chat→Delegar→Orquestar como estructura implícita; decidir si se adopta como marco explícito.
  - Cifras no sustanciadas (6,4 h/semana, 9x–66x, "agent bosses") y la fuente Deloitte nunca capturada — no usadas; verificar contra el original si el presentador las quiere.
  - Slides 1.2/1.3 (Microsoft) y 1.4/1.6 (Zapier) citan corpus records con `<!-- pending: process_images -->` — re-verificar tras librarian Fase 2 (los pendings son solo de la sección Images; el texto citado está transcripto).
  - Decisiones de juicio a confirmar: `duration: 2 horas` (default de profile) vs. 3,5 h del Día 1 / 25 min del bloque de framing — la Sección 1 pasó de 3 a 6 slides, lo que aumenta la presión sobre ese número; el reorden de secciones respecto del outline original del presentador; títulos de sesión traducidos al español (resuelto parcialmente pareando el nombre de misión en inglés); título de S1 normalizado y acortado a "Qué pensamos y por qué"; slide extra "Foco de la materia" (2.1) — el Composer confirmó que se gana el lugar, se mantiene.

## 2026-07-15 / 2026-07-16 — Step 5 (Review)
- Status: in_progress
- Asks log:
- What was decided: Dos rondas de Review. La **Ronda 1 (2026-07-15) nunca se registró** y se reconstruye acá desde la evidencia que dejó en los archivos; la **Ronda 2 (2026-07-16)** se registra en vivo. Al cierre de esta entrada el deck queda en **6 secciones / 16 slides**.

  **⚠️ Ronda 1 (2026-07-15) — reconstruida, no registrada en su momento. Alcance de la evidencia:** esta ronda corrió sin dejar bullets de feedback estampados en `draft.md`, así que **no existe rastro verbatim de qué pidió el presentador**. Lo que sigue es lo único que la evidencia física sostiene (cierre de Step 4 = 6 secciones/15 slides; cierre de Step 6 = 7/16; el campo `Sources` de la slide de ground rules; y el bloque de ground rules de `# Open questions`). **No se infiere ningún ask más allá de esto — si el presentador pidió otras cosas en esa ronda, se perdieron.**
  - **Ground rules resueltas en su parte de conducta.** El presentador aportó tres reglas *directamente en la revisión* (no provienen de ninguna fuente cruda: la slide lo declara explícito — "no tiene registro en `research/corpus/`"). Citas suyas preservadas en el `Sources` de la lámina: formuló la primera como **"computadoras cerradas"** y **pidió generalizarla** → se acordó **"pantallas cerradas"** (laptop + teléfono + tablet) con la salvedad **"salvo cuando trabajamos"** explícita; las otras dos textuales: **"estar presente"** y **"puntualidad — empezamos en punto"** (fue enfático con el "en punto").
  - **Sección nueva "Cómo trabajamos"** creada para alojarlas (1 slide: "Tres reglas para trabajar juntos", pin `icon-list`). Deck **6 secciones/15 slides → 7/16**. Con esto se levantó el `[blocker]` de ground rules que Step 4 había dejado abierto y que el Composer había marcado.
  - **La ubicación difirió del plan de Step 4**, que anticipaba la sección "entre la Sección 5 (Evaluación) y la 6 (Cierre)". Terminó en **posición 5**, antes de Evaluación (que pasó a 6) y Cierre (a 7), estableciendo el par *cómo trabajamos* → *cómo se aprueba*. **No hay evidencia de si el presentador pidió esa ubicación o si fue criterio del editor.**
  - **Quedó fuera de alcance:** las ground rules definidas cubren solo conducta en aula y puntualidad. Los tres huecos del briefing original (escala de calificación, mínimo de asistencia, uso de IA en las entregas) **siguen abiertos** — el presentador no los abordó y no se inventaron. Cuatro reglas más se le ofrecieron y las **declinó explícitamente**; están en `# Cut material`, recuperables.

  **Ronda 2 (2026-07-16) — 11 bullets del presentador, 10 aplicados y cerrados, 1 deliberadamente `[open]`.** Toda la contabilidad vía el skill `talksmith:feedback-cycle` (`stamp` → fix → `close` → `mirror-row`); `find-closed-unmirrored` limpio al cierre. **Dos bullets llegaron como párrafo suelto y no como bullet** (Agenda y 3.1), invisibles para `find_open_notes.py` — se normalizaron a bullet (texto verbatim intacto) y se estamparon por CLI como el resto.
  - **Reestructura (4 bullets).** Sección "Herramientas del Curso" **disuelta** → su lámina sobrevive intacta como slide **4.2** dentro de "Cómo trabajamos" (7→6 secciones), preservando la adyacencia con el Cronograma que motivó el reorden de Step 4. **"Lo que se llevan"** movida a **4.3** (mid-deck, confirmado explícitamente por el presentador). **"Manos a la obra"** movida al frente como **1.1**: **abre** el deck — el bullet era auto-contradictorio ("primer slide que abre" vs. "cierra perfecto") y el presentador eligió *abre*. Sección **"Conclusions" eliminada**. Nada se perdió: ambas láminas se reubicaron y el encabezado se registró en `# Cut material`.
  - **Slide borrada: "De un chat a una organización de agentes"** (vieja 3.2). Contenido completo archivado en `# Cut material` (lead + ASCII del arco con su `ascii-note` + las 3 misiones con descripción). **Dos consecuencias gestionadas, no ocultadas:** (a) el render `images/s3-2-1-chat-delegar-orquestar.png` queda **huérfano y NO se borró** (registrado en Cut material); (b) era el único enunciado explícito del arco CHAT→DELEGAR→ORQUESTAR — se verificó que el **objetivo 1 de 2.2 se lee bien solo**, y el arco se reforzó en los speaker notes de 2.2 (marcado como el único lugar donde ya se nombra) y 3.1 (trazable en voz alta sobre el calendario).
  - **Slide reemplazada: "El manager es la palanca" → 1.4 "El valor no llegó solo"** (Bain). Cifras verbatim-verificadas contra `corpus/bain-ai-budget-returns-2026.web.md`: 37% apuntaba a recortar 11%–20% vs. casi 40% **de los que midieron resultados** en 0%–10% (**el calificador es load-bearing y se preservó en lámina en itálica** — el denominador no son las 951); 90% aumenta el presupuesto igual; más la tesis citable ("la tecnología funcionó, el valor no llegó" / "el arreglo es organizacional, no tecnológico"). Atribución visible en lámina (`Bain 2026`) por el learning de fuente-en-lámina; canónica en `Sources`: **Bain Automation and AI Pathfinder Survey 2026 (n=951)**. **Juicio del editor:** se conservó el **67%/32%** de Microsoft como bisagra entre el "organizacional" de Bain y la tesis del deck (el manager); los **+17/+22/+30** de People Science se cortaron a `# Cut material` por densidad. Ambas decisiones a confirmar.
  - **Genericización de "Atlas"** en el objetivo 4 de 2.2 → "varias misiones a lo largo de la cursada". Barrida acotada a la **Sección 2** (Content + Sources + speaker notes): 3.1 **sigue** nombrando Atlas/Enterprise/Paperclip por día, porque el pareo día↔misión es decisión previa deliberada y este bullet **no** dijo "en todos lados" — a diferencia del de "Automatización", que sí lo dijo y sí se aplicó globalmente. Confirmación pedida.
  - **"Automatización" → "Automatización y Análisis de Datos"** (4.2), con grep global ("buscar en todos lados"): las 2 ocurrencias de la **categoría** actualizadas; "Automatizar" (1.6) y "Automatizando" (título del Día 2 en 3.1) **no** se tocaron — son otro concepto, no el nombre de la categoría.
  - **Visualización de 4.2 rehecha**: 3 tarjetas en fila → **lista vertical de 3 filas con ícono por fila** (`icon-list`). Es lo más cercano a la "tabla simple con iconos" pedida: el sistema de estilo **prohíbe tablas nativas** (las tablas pipe se renderizan como grillas de tarjetas). Nota de licencia por grupo preservada.
  - **3.1 "Siete sesiones": pin `timeline` → `process`.** `timeline` **no tiene campo de lead** (rail vertical de fecha+detalle), por eso el texto introductorio renderizaba **debajo** de los 7 hitos; `process` sí admite lead y las 7 sesiones son una secuencia numerada legítima. Trade-off real (se pierde el rail temporal) → registrado en `# Open questions`.
  - **Slide nuevo: 6.2 "Q&A"** (`closing-hero`), cierra el deck. **La imagen pedida NO se aplicó: no existe ningún asset candidato** en `images/` ni en el corpus. **No se fabricó ninguna ruta** (una ref rota rompe el render); el slot quedó documentado en un TODO en la lámina y el asset faltante en `# Open questions`. Se le trasladó la transición operativa al Día 1 (formación de equipos + licencia por grupo) que llevaba la vieja lámina de cierre, con su cita del README — nada se perdió.
  - **Bullet `[open]` a propósito (Agenda):** *"Antes de la agenda, empecemos con un slide con con text biemvenidos…"*. **No aplicado, y no es un descuido:** colisiona con la confirmación del mismo día de que **"Manos a la obra" (1.1) abre el deck**, y arrastra el mismo hueco de asset que el Q&A. Necesita desambiguación del presentador (¿antes de 1.1, reemplaza a 1.1, o queda absorbido?). Queda `[open]` para que el `rescue-open` de Step 6 (c) lo empuje a `# Open questions` de `final.md`.
  - **Dos defectos de render arreglados en el origen** (estaban parcheados en el modelo de render, no en el draft, así que regresaban en cada re-corrida): **1.2** pinneada `statement` (que **no** renderiza imágenes → su diagrama de tesis se caía en silencio) → **`content+image`**; **1.7** pinneada `stat` (espera 2–4 figuras) con una sola cifra (38%) → **`big-number`**, con el Content reordenado para que la cifra sea `body[0]` según el contrato del template.
  - **Disciplina de fact-check sostenida.** Las cifras fabricadas ("6,4 h/semana", "9x–66x", "agent bosses", "McKinsey Global AI Survey 2026", "Bain Agentic AI Benchmark 2026", payback 4,1/6,7/9,3 meses) **no aparecen en ninguna lámina** — verificado por grep; sobreviven solo en el registro de fact-check de `# Open questions` / `# Cut material`, ahora ampliado con la verificación de 2026-07-16 de que **esos dos estudios no existen**. El pedido del presentador de "impacto y eficiencia con números" se resolvió con fuente primaria verificada (Bain), no con las cifras que originalmente se querían para esa lámina. El único número de eficiencia real disponible (caso **Amazon**: 26 min → 2 min, −92%) quedó en speaker notes, etiquetado como anécdota de una sola empresa y **no** como benchmark.
  - **Barrida de renumeración** aplicada a prosa, `Sources`, speaker notes, `# Open questions`, `# Cut material` **y bloques ASCII** (el fallo conocido de barridas solo-prosa): 0 referencias colgadas: `conclusions.*`, `slide 3.2` y `slide 7.1` no existen; los únicos "3.2" restantes son históricos ("vieja 3.2") y deliberados.
- Key inputs: `draft.md` (11 bullets del presentador en campos `Presenter feedback`); **`research/corpus/bain-ai-budget-returns-2026.web.md`** (fuente primaria nueva, con su aviso de citación — reemplaza cifras fabricadas); `corpus/microsoft-work-trend-index-2026.web.md` (67/32); `corpus/zapier-agentic-ai-adoption-survey-2026.web.md` (38% human-in-the-loop); `${CLAUDE_PLUGIN_ROOT}/config/pptx-styles/slide-templates.md` (catálogo de templates — resolvió los pins `content+image` / `big-number` / `process` / `icon-list` / `closing-hero` y la exclusión de `aside` en full-bleed); `config/profile.md` (idioma: español); skill `talksmith:feedback-cycle`.
- Files created/modified: `talks/intro-curso-mim/draft.md` (reestructurado: 7→6 secciones, 16 slides; 10 bullets cerrados con Resolution, 1 `[open]`), `config/feedback-backlog.md` (10 filas espejadas), `talks/intro-curso-mim/memory.md`. **No modificado:** `images/` (el render huérfano de la vieja 3.2 se conserva), `final.md` (se re-deriva en Step 6 — está **desactualizado** respecto de este draft).
- Pending open questions:
  - **Ronda 1 de Review no tiene rastro verbatim** — reconstruida acá solo hasta donde la evidencia física llega. Si se quiere el audit trail completo, hay que recuperarlo de la transcripción de esa sesión. **No se inventó ningún ask.**
  - **1 bullet `[open]`** (slide de bienvenida antes de la Agenda) esperando desambiguación del presentador — colisiona con "Manos a la obra" como apertura.
  - **Dos assets de imagen faltantes** bloquean pedidos explícitos: la del **Q&A (6.2)** y la del **slide de bienvenida**. No hay candidatos en `images/` ni en el corpus (las imágenes del corpus son gráficos en inglés con marca de consultora o logos). El presentador tiene que dejar los archivos.
  - **Decisiones de juicio del editor a confirmar** (todas en `# Open questions` de `draft.md`): el 67/32 retenido en 1.4 · si el caso Amazon sube a lámina · el pin `timeline`→`process` de 3.1 y su costo visual · si "Atlas" también sale del cronograma · "Lo que se llevan" dentro de una sección cuyo título no lo cubre · Q&A colgado de "Cierre y Portafolios" · la Figura 1 de Bain como imagen candidata para 1.4 (pendiente Fase 2 del librarian).
  - **Nuevo pending stub**: 1.4 y 1.7 citan `corpus/bain-ai-budget-returns-2026.web.md`, que tiene `<!-- pending: process_images -->` — re-verificar tras librarian Fase 2 (los pendings son solo de la sección *Images*; el texto citado está transcripto y verificado verbatim).
  - Siguen abiertas sin cambios: escala de calificación · mínimo de asistencia · uso de IA en las entregas · Examen Integrador en Día 7 (afecta 5.1 y 3.1) · Día 4 sin definir · rúbrica de evaluación de pares (6.1) · cantidad de misiones · marco narrativo del curso (ahora **sin lámina**, solo texto) · `README.md` sin registro en el corpus (lo citan 1.1, 1.3, 1.5, 1.6, 3.1, 6.2) · slide 1.3 idea 1 ("cuánto" vs. "quién") · `duration: 2 horas` vs. 16 slides.
  - **`final.md` quedó obsoleto** — refleja la estructura 7/16 previa. Hay que re-correr Step 6 (Polish) sobre este `draft.md`; el Step 6 registrado abajo es de la estructura vieja.

## 2026-07-15 — Step 6 (Polish)
- Status: complete
- What was decided: `final.md` derivado de `draft.md` (copia verbatim previa, byte-idéntica) y limpiado con las cuatro transformaciones de Step 6. `draft.md` queda **read-only y sin tocar** desde este paso (verificado: 46.594 bytes, mtime 22:14, anterior a la copia; conserva sus 25 campos `Presenter feedback` como audit trail durable). Deck final: **7 secciones / 16 slides** (14 de contenido + 2 de conclusiones), sin campos de trabajo visibles.
  - **(a) Inline SVGs.** Los 2 bloques ASCII render-driving se reemplazaron por refs de imagen vía `polish-ascii cleanup` (one-shot, plan fresco, exit 0): `fences rewritten: 2 · skipped: 0`. No queda ninguna fence ` ```ascii ` en `final.md`. Cada bloque conserva su `<!-- ascii-source: -->` (eco del ASCII original) y su `<!-- ascii-note: -->` post-fence, según el contrato del skill.
  - **(b) Consolidación + formato Keynote-safe.** Ambas refs ya nacían con prefijo `images/` → no hizo falta copiar nada ni resolver colisiones. Auditoría de extensión: las dos apuntaban a `.svg` (prohibido — Keynote no renderiza SVG embebido y lo muestra como caja vacía al importar `.pptx`). Se reapuntaron a los PNG deliverables que el illustrator ya había producido (contrato *PNG companion* de `ascii-to-svg`); los `.svg` quedan en disco como source-of-truth. Cero refs con extensión prohibida (`.svg`/`.webp`/`.avif`/`.heic`) tras la auditoría. No hubo fuentes externas WebP/AVIF/HEIC que rasterizar ni SVG externos huérfanos.
  - **(c) Rescate de feedback `[open]`.** `feedback_cycle.py rescue-open` → *"no [open] bullets to rescue"*. Step 5 cerró todo; no había bullets `[open]` ni `[closed]` estampados en el draft. La sección `# Open questions` se conservó **verbatim** — sus ítems son prosa autoral del editor (no bullets de feedback) y siguen genuinamente sin resolver: **no se inventó ninguna respuesta**.
  - **(d) Strip de `Presenter feedback`.** 25 campos eliminados de `final.md`: 16 en forma H3 (`### Presenter feedback`, nivel slide) + 9 en forma párrafo (`**Presenter feedback:**`, niveles Thesis / Agenda / Section). 0 en forma legacy bullet. **Los 25 estaban vacíos** — el script usado rehusaba descartar en silencio cualquier campo con contenido (habría sido preservado y reportado); no se activó. Residual en `final.md`: 0 ocurrencias de la cadena. Separadores `---` intactos (27 = 25 entre slides + 2 delimitadores de frontmatter); sin líneas en blanco triples.
- Detalle por bloque de diagrama (illustrator, ambos limpios en la primera pasada — 0 iteraciones de corrección):
  - **`s1-1-1-agentes-personas-agencia`** — slide `1.1` "Amplificación, no reemplazo" (el diagrama de la tesis). Intent: mostrar que ejecución delegada y agencia humana crecen juntas, no en suma cero. Renderizado a SVG (3.302 B) + PNG deliverable (59.151 B). Pasó validación y aspect audit; estampado con su digest ASCII. Alt en lámina: *"Los agentes toman la ejecución, las personas ganan agencia: crecen juntas, no en suma cero"*.
  - **`s3-2-1-chat-delegar-orquestar`** — slide `3.2` "De un chat a una organización de agentes" (el arco del curso). Intent: mostrar el arco como progresión de tres estadios (CHAT → DELEGAR → ORQUESTAR), no como temario suelto. Renderizado a SVG (3.108 B) + PNG deliverable (56.293 B). Pasó validación y aspect audit; estampado con su digest ASCII. Alt en lámina: *"El arco del curso: de un chat a delegar (Cowork) y a orquestar una organización de agentes (Paperclip)"*.
  - Ambos digests quedan estampados: si el ASCII no cambia en `draft.md`, una re-corrida de Polish los saltea sin re-renderizar.
- Key inputs: `talks/intro-curso-mim/draft.md` (congelado, autoritativo); `.talksmith-tmp/plan.annotated.json` (plan del illustrator con `render = {svg_basename, alt}` por bloque); los 4 sidecars/renders en `talks/intro-curso-mim/images/`; `config/profile.md` (idioma de presentación: español).
- Files created/modified: talks/intro-curso-mim/final.md (derivado + limpiado: 2 fences → refs PNG, 25 campos de feedback removidos), talks/intro-curso-mim/memory.md. **Eliminado:** `.talksmith-tmp/` en la raíz del working directory (7 archivos: `polish_ascii.py`, `validate_svg.py`, `rasterize.py`, `audit_aspect.py`, `plan.annotated.json`, `ts-args/s1-1-1.json`, `ts-args/s3-2-1.json`) — staging del illustrator, no versionado y sin dependencias del deliverable (verificado: ni `final.md` ni `images/` lo referencian). `images/.critique/` se conserva (ya está gitignorado). **No modificado:** `draft.md`.
- Pending open questions:
  - **No existe entrada de Step 5 (Review) en este `memory.md`.** El paso corrió —el draft pasó de 6 secciones/15 slides (cierre de Step 4) a 7/16, con la Sección 5 "Cómo trabajamos" incorporada y las ground rules resueltas el 2026-07-15— pero su cierre nunca se escribió, y `draft.md` no tiene bullets de feedback estampados (`[open]`/`[closed]`) que documenten la ronda. El rastro de qué pidió el presentador y qué se cambió en Review quedó sin registrar. No se fabrica acá: hay que reconstruirlo desde la transcripción de la sesión si se quiere el audit trail completo.
  - Siguen abiertas, sin cambios, todas las de la sección `# Open questions` de `final.md` (el presentador no las abordó; ninguna se inventó): **escala de calificación** (aprobado/desaprobado vs. numérica) · **mínimo de asistencia** · **política de uso de IA en las entregas** (Portafolio 40% + Examen 40%) · si el **Examen Integrador (45 min) va en el Día 7** (afecta 6.1 y 3.1) · **Día 4** (Mar 11 Ago) sin definir (aparece "A definir" en 3.1 y ausente del arco de 3.2) · rúbrica de evaluación de pares (7.1, punto 03) · cantidad de misiones (abierta a propósito) · marco narrativo del curso (¿se adopta Chat→Delegar→Orquestar como explícito?).
  - **`README.md` de la raíz sigue sin registro en `research/corpus/`** — lo citan 1.2, 1.3, 1.4, 1.5, 3.1, 3.2 y `conclusions.2` sin protección contra drift. Trabajo de librarian, no del editor.
  - **Slide 1.2, idea 1**: pendiente la decisión del presentador entre la redacción suavizada ("expande **cuánto** trabajo de alto valor podés hacer") y la original del README ("expande **quién**" — claim de acceso que hoy el corpus no respalda con cifras).
  - **`duration: 2 horas` vs. 16 slides** — la tensión persiste sin cerrar; es lo único de ese bloque que el presentador no resolvió.
  - Cifras deliberadamente fuera de toda lámina y que deben seguir afuera hasta verificarse contra el original: "6,4 horas/semana", "9x–66x", "agent bosses" (más Deloitte, nunca capturado). El strip de Step 6 no las introdujo: ninguna llegó a `final.md`.
  - Pending stubs del corpus: 1.2/1.3 (Microsoft) y 1.4/1.6 (Zapier) citan records con `<!-- pending: process_images -->` — re-verificar tras librarian Fase 2. Los pendings son solo de la sección *Images*; el texto citado está transcripto y verificado.
