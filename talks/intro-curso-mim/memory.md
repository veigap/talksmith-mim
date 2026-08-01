# memory.md — intro-curso-mim

**Current step:** 7 — Render complete (html-strict)
**Topic:** Presentación de la materia — ground rules, criterio de aprobación, calendario
**Folder:** talks/intro-curso-mim/
**Started:** 2026-07-15

## Step 5 — Review · 2026-08-01 (edición directa del presentador)

**What was decided:** El presentador editó `draft.md` a mano (sin bullets de feedback) en dos tandas sobre el Cronograma (slide 3.1). Estado final de los siete días:

| Día | Antes | Ahora |
|---|---|---|
| 1 | Primeros pasos con Claude Cowork · misión **Atlas** | Intro/Claude Desktop - Chat |
| 2 | Automatizando un reporte semanal en Cowork · misión **Atlas** | Claude CoWork |
| 5 | Cowork para la empresa · misión **Enterprise** | Claude Cowork para la Empresa |
| 6 | Orquestando agentes con Paperclip · misión **Paperclip** | Orquestando agentes con Paperclip |

Neto: **ninguna misión se nombra ya en lámina en ningún lugar del deck** (2.2 tampoco). Los días 3, 4 y 7 quedaron intactos.

También borró de `draft.md` las secciones `# Open questions` y `# Cut material` completas (~140 líneas). El detalle histórico de esas secciones sigue recuperable en git.

**Editor — dos correcciones derivadas aplicadas** (surfaced primero, aplicadas al quedar el lead factualmente contradicho por su propia lámina):

1. Lead de 3.1: *"…Cada día tiene su propio foco; cuatro de ellos sostienen una misión."* → *"…Cada día tiene su propio foco, y el recorrido va de chatear a delegar y orquestar."*
2. Speaker notes de 3.1: se reescribió el párrafo que anunciaba los nombres de misión en lámina (ahora dice que no se nombran y que están en el README para decirlos de palabra); *"misión pesada"* → *"trabajo pesado"*; y el arco pasó a *"Día 1 chatear (Claude Desktop) · Días 2–3–5 delegar (Cowork) · Día 6 orquestar (Paperclip)"*.

Ambas son revertibles con un edit; el presentador las tiene señaladas en chat.

## Step 6 — Polish · 2026-08-01

**Files created/modified:** `final.md` regenerado desde `draft.md`.

- 1 diagrama ASCII (`s1-4-1-agentes-personas-agencia`) — **reusado** (SVG estampado con el mismo digest).
- 2 asides generados (`s1-1-1-aside.png`, `s6-1-1-aside.png`) — **reusados** (mismo digest de descripción).
- Ref `.svg` → `.png` reescrita (regla Keynote-safe).
- `rescue-open`: sin bullets `[open]`. `strip_feedback`: 13 campos H3 + 8 labels de párrafo.

## Step 7 — Render · 2026-08-01

**What was decided:** Estilo **html-strict** (elegido por el presentador). Sin `.pptx` en esta pasada.

**Files created/modified:**

- `output/slide-model.json` — parcheado sólo en el slide 3.1 (lead, 7 `milestones`, `notes`) y re-estampado contra el `final.md` vigente.
- `output/html/index.html` — 19 slides, ~4,5 MB; `.icons/` sin cambios (16 archivos).

**Auditorías:** `degenerate_enum` ok · `field_coverage` ok · `image_coverage` ok.

## Errata conocida — `replaceState` en el preview

Abrir `output/html/index.html` dentro de un panel de preview con iframe `srcdoc` (el visor de Claude, y cualquier embed similar) tira `SecurityError: Failed to execute 'replaceState' on 'History'`. **Causa:** `html_style.py:656` inicializa Reveal con `hash:true`, y Reveal llama `history.replaceState` con una URL absoluta que un documento `about:srcdoc` no puede escribir. **No es un defecto del deck** — abierto desde el disco en un navegador no aparece, y aun en el preview el deck navega bien (sólo se pierde el deep-link por hash).

**Fix opcional en el plugin** (`skills/md-to-deck/html_style.py`): cambiar `hash:true` por `hash: window.self === window.top` — conserva el deep-link cuando la página es top-level y lo desactiva dentro de un iframe.

## Nota operativa de entorno (Cowork remoto)

Sesión en la nube: el repo vive en la máquina del presentador y se llega por el puente de dispositivo. Polish y Render corrieron sobre una copia de trabajo en el contenedor (`draft.md`, `images/`, `config/`, `output/slide-model.json`) y los resultados se escribieron de vuelta a disco. `research/` (838 MB) no se copia — Steps 6 y 7 no lo necesitan.

**Trampa observada:** `device_stage_files` sirvió bytes cacheados de una copia anterior de `draft.md` (misma ruta, mismo `mtime` reportado, contenido viejo). Verificar siempre el tamaño en bytes del archivo staged contra `stat` en el dispositivo antes de trabajar sobre él.
