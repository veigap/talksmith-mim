# memory.md — claude-desktop-chat

**Current step:** 5 — Review (reabierto)
**Awaiting:** 2026-07-31 — Step 6 (Polish) cerrado sobre `final.md`. Pendiente: decisión del presentador sobre Step 7 (Render html-strict) y sobre la duración real del bloque (el deck suma 50 min contra `duration: 60 min (a confirmar)`). 2026-07-31 — el Talk queda en `draft.md` (Step 5 / Review) recién salido del split. No avanzar a Polish sin señal explícita del presentador. Awaiting: revisión del draft partido (Thesis, Agenda y referencias cruzadas reescritas) y confirmación de la duración real de la clase.
**Mode:** C (Presenter Outline) — heredado del Talk combinado del que salió esta mitad.
**Topic:** Claude Desktop, la superficie de chat: el chat que la audiencia ya usa a diario, su límite de memoria de entrenamiento, los conectores que lo abren al mundo real del usuario, Schedule para que trabaje solo, y la parte 1 de la misión de Faro resuelta enteramente dentro del chat.
**Folder:** talks/claude-desktop-chat/
**Started:** 2026-07-31

---

## Talk briefing

Parte 1 de un par de clases para el Master in Management (MiM) del IAE Business School. Sale de partir en dos el Talk combinado de 120 minutos que vivía en `talks/claude-cowork/`. Esta mitad se queda en la superficie de chat de Claude Desktop: encuadre del problema y del catálogo de herramientas de Claude, el chat que responde de memoria de entrenamiento, los conectores como concepto transversal a todas las IAs (incluidos Claude in Chrome y el cuidado de prompt injection), Schedule, y la placa de misión parte 1. La parte 2 (Claude Cowork, archivos .md, Projects, Skills, Subagentes, la placa de misión parte 2 y las Conclusions) queda en `talks/claude-cowork/`, con class "Claude Cowork".

---

## 2026-07-31 — Split del Talk combinado (Step 5, Review)

- Status: complete
- What was decided: el presentador decidió partir la clase de 120 minutos en dos clases independientes. Esta carpeta (`claude-desktop-chat`, class "Claude Desktop - Chat") toma las secciones 1 a 5 del deck original. Encuadre elegido para el trabajo editorial: **mínimo mecánico**, sin slides nuevas. No se agregó slide de cierre ni de repaso; la clase termina en la placa de misión parte 1, que ya funciona como cierre.
- Qué heredó de la carpeta original:
  - 5 secciones contiguas (1 Introducción · 2 Claude Chat (Desktop) · 3 Conectores · 4 Schedule · 5 La misión · parte 1), 18 slides, numeración contigua dentro de cada sección.
  - 13 bloques ASCII con sus `ascii-note`, 2 referencias de imagen (`images/connectors_directory.png`, `images/connector_browser.png`) y 2 directivas `generate-image` (slides 1.1 y 1.2).
  - La carpeta `images/` completa y el corpus (`research/corpus/agentic-ai-deck.zip.md`, `research/corpus/mision - auto.zip.md`), copiados tal cual.
  - Frontmatter con `class: "Claude Desktop - Chat"` y `duration: 60 min (a confirmar)` ya ajustados por el script de split.
- Qué se reescribió en esta pasada:
  - **Thesis** (Claim + Why it matters): ahora describe solo esta clase (chat de memoria → conectores → Schedule) y cierra apuntando a la segunda clase. Salieron las promesas de Cowork, Projects, Skills, Subagentes, archivos .md y "delegar resultados".
  - **Agenda**: el `Narrative arc` pasó de narrar once secciones a narrar cinco, en el mismo párrafo denso de la casa; la lista `Sections (in delivery order)` quedó 1:1 con los cinco H1.
  - **Open questions**: se podaron las entradas exclusivas de la parte 2 (screenshots de la interfaz de Cowork y el stub de la slide 6.5, slash commands de Skills 9.2-9.3, subagentes a pedido, audit trail de Conclusions.2, carpeta `skills/` de la misión, banner DEMO TIME de 6.5, piezas borradas el 2026-07-30, locality de Live Artifacts, y las URLs de round 3 que no son de esta mitad). Se conservaron las que tocan chat, conectores, Claude in Chrome, Schedule y el sourcing de Gemini, con los números de slide verificados contra este archivo (3.2, 3.3, 4.1 siguen apuntando bien). Se agregaron tres entradas nuevas: duración a confirmar, asides sin renderizar, y la nota del split con el puntero a la carpeta hermana.
  - **Cut material**: quedaron solo los dos ítems cortados de estas cinco secciones (detalles internos de Claude Code, con el puntero corregido a la slide 1.4; y el detalle mecánico del Schedule de Cowork, con la referencia corregida a la sección 4). Se agregó una entrada que aclara que el material de la parte 2 se mudó, no se cortó.
  - **Referencias cruzadas**: 11 arreglos en las cinco secciones (13 referencias distintas), más 2 punteros corregidos en `# Cut material`. Todo lo que apuntaba a secciones 6-11 o a las Conclusions ahora apunta a "la segunda clase" / "la clase de Cowork". Los más notables: slide 1.2 (bullet de contenido del camino, Sources y notes), slide 1.4 (dos bullets de contenido, el `ascii-note`, Sources y dos pasajes de las notes), slide 4.2 (las notes que anticipaban la sección 6 de Cowork sobre archivos locales) y slide 5.1 (las notes que mandaban la parte 2 "más adelante" y proponían una pausa a mitad de clase; ahora cierran la clase).
  - Las referencias internas que siguen siendo válidas se dejaron intactas: "Sección 3" en 2.2, "sección 4" en 3.9, "la sección 5" para el reveal de Faro en 3.8, "slide 3.7" en 3.1.
- Nota sobre la placa de misión: el ASCII de la slide 5.1 era byte-idéntico al de la vieja slide 11.1 (placa gemela). Ahora viven en Talks distintos, así que la restricción de gemelas ya no aplica dentro de un mismo archivo. El ASCII de 5.1 se dejó exactamente como estaba.
- Key inputs: `draft.md` post-split (794 líneas), `talks/claude-cowork/memory.md` (formato del header y de las entradas), `config/profile.md`.
- Files created/modified: `talks/claude-desktop-chat/draft.md` (Thesis, Agenda, Open questions, Cut material, referencias cruzadas), `talks/claude-desktop-chat/memory.md` (nuevo).
- Verificación: frontmatter parsea, `class: "Claude Desktop - Chat"`; 26 líneas de fence = 13 bloques ASCII, sin cambios; las 2 referencias de imagen resuelven en `images/`; las 2 citas de corpus resuelven en `research/corpus/`; secciones 1-5 contiguas y slides contiguas dentro de cada una; la Agenda coincide 1:1 con los H1; 18 campos `### Presenter feedback` y 7 `**Presenter feedback:**`, todos vacíos, 0 `[open]` y 0 `[closed]`; suma de "Tiempo objetivo" = **50 min** sobre 18 slides.
- Pending open questions:
  - Duración real de la clase sin confirmar. El frontmatter dice `60 min (a confirmar)` y los tiempos objetivo suman ~50 min sin Q&A ni pausa.
  - Polish (Step 6) y Render (Step 7) nunca corrieron para esta carpeta: no existen `final.md` ni `output/`. Los SVG y PNG en `images/` vienen del Polish del Talk combinado; hay que re-correr Polish desde cero contra este `draft.md`.
  - Las 2 directivas `generate-image` de las slides 1.1 y 1.2 siguen sin imagen: la sesión del último Polish no tenía capacidad de generación de imágenes.
  - Los ítems heredados de vigencia de fuentes (nube de Schedule beta desde julio 2026, planes pagos de Claude in Chrome, sourcing de Gemini en 3.3) siguen abiertos en `# Open questions`.

---

## 2026-07-31 — Polish (Step 6)

- Status: complete
- What was decided: primera corrida de Polish para esta carpeta. `final.md` se derivó de `draft.md` por copia byte a byte y desde ahí todo el trabajo fue mecánico —SVGs, referencias de imagen, rescate de feedback y stripping— sin reescribir prosa. `draft.md` quedó congelado y se verificó al cierre que su md5 no cambió (`d7f75b62df0a8b21262aed83d5006ab7`).
- Pasada de diagramas (diagram-illustrator, previa a esta mitad editorial): 13 bloques ASCII, los 13 render-driving, 12 reusados por stamp y 1 re-renderizado (`s1-4-1`, el ASCII de las cuatro herramientas que se reescribió en el split). 0 fallidos, 0 documentation-only.
- **Fences inlineadas:** `polish_ascii.py cleanup` reescribió las 13 fences ```` ```ascii ```` a referencias de imagen con su eco `<!-- ascii-source: -->`, dejando cada `<!-- ascii-note: -->` en su lugar. 0 saltadas por falta de mapping. Verificado: **0 fences de cualquier tipo sobreviven** en `final.md` (741 líneas).
- **Referencias consolidadas:** las 13 referencias nuevas se reescribieron de `.svg` a su companion `.png` por la regla Keynote-safe; los `.svg` quedan en disco como fuente de verdad. Las 2 capturas heredadas (`connectors_directory.png`, `connector_browser.png`) ya cumplían y no se tocaron. Total: **15 referencias**, todas bajo `images/`, todas `.png`, todas resuelven en disco, 0 extensiones prohibidas (`.svg` / `.webp` / `.avif` / `.heic`).
- **Rescate de feedback:** `feedback_cycle.py rescue-open` reportó *no [open] bullets to rescue*, como se esperaba —los campos de feedback de este Talk están vacíos por decisión permanente del presentador (0 `[open]`, 0 `[closed]`).
- **Stripping de feedback:** `strip_feedback.py` sacó los **25 bloques** de `Presenter feedback` de `final.md` (18 `### Presenter feedback` a nivel slide + 7 `**Presenter feedback:**` en Thesis, Agenda y los 5 headers de sección; 0 bullets legacy). Verificado: 0 ocurrencias del string en `final.md`, y la garantía de línea en blanco antes de cada `---` se cumple en los 23 bordes de slide/sección (el único `---` sin línea en blanco delante es el cierre del frontmatter, que es correcto). `draft.md` conserva los 25 campos intactos y vacíos para futuras rondas de review.
- **Garbage collection de `images/`:** la carpeta arrastraba 128 archivos del deck combinado, con varias tripletas viejas que difieren de las vivas solo por slug (`s2-1-1-chat-solo-vs-conectores` vs la viva `s3-1-1-...`, `s1-1-1-chat-de-fabrica` vs `s2-1-1-...`, `s2-5-1-conector-dos-direcciones` vs `s3-2-1-...`, `s2-2-1-memoria-vs-busqueda` vs `s3-3-1-...`). Se corrió `polish_ascii.py gc` primero en dry-run y se auditó la lista contra las referencias vivas: 0 solapamientos con archivos referenciados, 0 colisiones de stem, y las 2 capturas del presentador ausentes de la lista. Recién ahí se aplicó. **29 tripletas huérfanas, 87 archivos borrados; 128 → 41** (13 diagramas × 3 + 2 capturas). Nota operativa: el primer `--apply` falló con `Operation not permitted` porque el mount FUSE de Cowork bloquea `unlink`; hubo que habilitar borrado en la carpeta antes de re-correrlo.
- **Asides sin renderizar:** siguen las **2 directivas reales** `<!-- generate-image: right | ... -->` en las slides 1.1 y 1.2, sin imagen. El image-illustrator devolvió `unavailable`: esta sesión no tiene capacidad de generación de imágenes. Se dejaron en su lugar a propósito —son comentarios HTML, renderizan inocuas, y su descripción es la clave de idempotencia de una futura pasada. (Hay una tercera aparición del string `generate-image` en `# Open questions`, pero es prosa que documenta el pendiente, no una directiva.)
- Nota de estilo: **`config/diagram-style.md` no existe en este subject repo**, así que la pasada de diagramas corrió con las reglas visuales estándar que trae el plugin. Si el presentador quiere fijar paleta o convenciones propias, ese archivo es el lugar.
- Key inputs: `draft.md` (congelado), el plan de render anotado del diagram-illustrator, skills `talksmith:polish-ascii` y `talksmith:feedback-cycle`.
- Files created/modified: `talks/claude-desktop-chat/final.md` (nuevo), `talks/claude-desktop-chat/images/` (87 archivos huérfanos podados), `talks/claude-desktop-chat/memory.md`.
- Verificación de cierre: frontmatter parsea, `class: "Claude Desktop - Chat"`; 0 fences; 15 referencias válidas sin extensiones prohibidas; 0 `Presenter feedback` en `final.md` y 25 en `draft.md`; md5 de `draft.md` sin cambios; 5 secciones y 18 slides, con los encabezados idénticos a los de `draft.md`.
- Pending open questions:
  - Las 2 directivas `generate-image` de las slides 1.1 y 1.2 siguen pendientes. Re-correr el paso de image-illustrator en una sesión con generación de imágenes, o borrarlas.
  - Duración real de la clase sin confirmar (sigue de la entrada anterior).
  - Step 7 (Render) nunca corrió: `output/` sigue vacío.

---

## 2026-07-31 — Slide de cierre (Step 5, Review reabierto)

- Status: complete
- What was decided: el presentador pidió una lámina de conclusiones que resuma lo visto. Revierte la decisión del split, que había cerrado la clase en la placa de misión sin recap. Se agregó un bloque `# Conclusions` con **una sola slide**, después de `# 5. La misión · parte 1` y antes de `# Open questions`, siguiendo el patrón del Talk hermano (bloque no numerado, sin "Goal of this section" y sin `**Presenter feedback:**` a nivel bloque).
- La slide: `## 1. Qué nos llevamos de esta clase` (30 caracteres, bajo el techo de 40). Cinco bullets que recorren el arco real del deck: el chat de memoria con sus tres límites, los conectores que lo sacan del aislamiento y además actúan, los dos casos más la división out of the box / externos por MCP, Schedule con la pregunta de dónde corre, y la parte 1 de la misión con el puente a la segunda clase. Sin claims nuevos: todo lo afirmado ya está sourceado en su slide de origen, y `### Sources` lo declara en el estilo de slide organizativa que el deck ya usa (1.1, 1.2).
- **Sin diagrama, por decisión:** el arco de cuatro beats es una secuencia de etiquetas, no una forma. Un ASCII de cuatro cajas en fila repetiría los bullets sin agregar información, y la slide ya tiene la densidad tope. El deck queda en 13 bloques ASCII, sin cambios.
- Efectos colaterales corregidos: el `Narrative arc` de la Agenda cerraba la clase en la placa de misión, ahora menciona el repaso de cierre; las Speaker notes de 5.1 afirmaban ser "la última lámina de la clase", que ya es falso, y ahora anuncian el repaso que viene. La lista `Sections (in delivery order)` NO se tocó: Conclusions no es una sección numerada.
- Key inputs: pedido del presentador vía chat; `talks/claude-cowork/draft.md` (patrón estructural del bloque `# Conclusions`); `config/profile.md`; skill `talksmith:desrobotizar` aplicada a la prosa nueva.
- Files created/modified: `talks/claude-desktop-chat/draft.md`, `talks/claude-desktop-chat/memory.md`, `config/feedback-backlog.md`.
- Verificación: YAML parsea, `class: "Claude Desktop - Chat"`; 26 líneas de fence = 13 bloques pareados, sin bloques nuevos; las 2 referencias de imagen resuelven; secciones 1-5 contiguas e intactas, Conclusions con exactamente 1 slide; Agenda 1:1 con los cinco H1 numerados; 19 `### Presenter feedback` y 7 `**Presenter feedback:**`, todos vacíos, 0 `[open]` y 0 `[closed]`; suma de "Tiempo objetivo" = **53 min** sobre 19 slides.
- Pending open questions:
  - `final.md` y `output/` quedaron desactualizados a propósito: no incluyen la slide nueva. Re-correr Polish (Step 6) y Render (Step 7).
  - Duración real de la clase sin confirmar: 53 min contra `duration: 60 min (a confirmar)`.
  - Las 2 directivas `generate-image` de las slides 1.1 y 1.2 siguen pendientes.
