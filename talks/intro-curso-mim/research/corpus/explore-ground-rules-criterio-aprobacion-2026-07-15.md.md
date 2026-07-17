---
source_file: explore-ground-rules-criterio-aprobacion-2026-07-15.md
source_type: chat-export
ingested_at: 2026-07-15
---

# Live exploration — ground rules y criterio de aprobación (MIM Augmented / "Agentes Inteligentes")

## Provenance
- Original location: research/llm-chats/explore-ground-rules-criterio-aprobacion-2026-07-15.md
- Format: live-exploration transcript (.md, captured during Step 2 of the Talksmith workflow — not a ZIP export)
- Author / source (if known): Presenter (course instructor) + Talksmith exploration agent
- Date of original (if known): 2026-07-15 (per frontmatter: started_at/ended_at both 2026-07-15)
- Original frontmatter topic field: "ground rules y criterio de aprobación — MIM Augmented"

## Key claims
This session was framed as an exploration of ground rules / criterio de aprobación, but the presenter redirected it almost entirely toward course positioning, README rewrites, and content decisions. The stated topic (ground rules/approval criteria) was only partially resolved — see Inconsistencies section.

**Course title / framing decisions:**
- Course title changed to **"Agentes Inteligentes"**. This updates `config/profile.md` Subject field (shared across all classes in the course) to: "Agentes Inteligentes — Master in Management (MiM), IAE Business School, Universidad Austral (https://www.iae.edu.ar/programas/mim/)".
- README.md top-level title changed to: `# Agentes Inteligentes | MIM — IAE Business School` (previously `# MIM — Augmented | IAE Business School`).
- The entire "Industry 4.0 — The 8 Stages" narrative framework (Assessment, Strategy, Connectivity, Integration, Analytics, Automation, People, Scale) was **deleted** from the README, along with every "I4.0 Phase" reference across day titles, the Mission Overview table, and the objective text. A proposed replacement framework ("La Escalera del Trabajador Aumentado" — Delegar/Automatizar/[TBD]/Escalar/Orquestar/Evaluar) was drafted by the agent but explicitly **rejected/deleted** by the presenter ("Borremos por ahora ese marco") — the course currently has no narrative framework replacing Industry 4.0.
- Course "second part" philosophy (this is the "por qué" of the course, per the agent): first part of the course was conceptual/theoretical; this second part is about the practice of *augmented work* — how Agents and AI tools multiply what a knowledge worker can do. The explicit teaching goal is NOT to master one product but to internalize a philosophy/way of thinking for delegating and orchestrating work with agents, because tools change fast ("lo que hoy es Cowork, mañana puede tener otro nombre"). Final "Foco de la materia" paragraph and 4 "lo que se llevan" bullets were drafted and approved (see Raw excerpts).

**Calendar (as of session start, from README):**
| # | Fecha | Horario | Formato | Título |
|---|---|---|---|---|
| 1 | Sáb 1 Ago | 8:30–12:00 | Presencial | Getting Started with Claude Cowork |
| 2 | Sáb 1 Ago | 13:00–16:30 | Presencial | Automating a Weekly Report in Cowork |
| 3 | Jue 6 Ago | 19:00–21:00 | Virtual | *A definir* → later filled in this session |
| 4 | Mar 11 Ago | 19:00–21:00 | Virtual | *A definir* — still undefined at session close |
| 5 | Vie 28 Ago | 9:00–12:30 | Presencial | Cowork for the Enterprise |
| 6 | Sáb 29 Ago | 8:30–12:00 | Presencial | Orchestrating Agents with Paperclip |
| 7 | Jue 3 Sep | 19:00–21:00 | Virtual | Evaluation (format still undefined at session close) |

- Días 1–2 build the **Atlas** mission (notes → agent-researched, drafted, emailed, and published weekly report) across 4 milestones: Projects/Instructions/Skills → Tools/Connectors → Schedule → Live Artifacts.
- Día 5 = **Enterprise** mission: package work as Plugins, install on a colleague's machine, Claude Tag, Team account.
- Día 6 = **Paperclip** mission: add a specialized agent ("Director de Relaciones Institucionales") to an existing agent organization, with human-in-the-loop.
- Día 7 = **Evaluación** — format undefined throughout the session.

**Day 3 defined in this session — "Construyendo Presentaciones con IA" (later translated to English):**
- Goal: separate knowledge from its visualization — structure content as agent-navigable plain markdown first, then choose how to render it (deck, dashboard, wiki) without rewriting content.
- Directly inspired by the MindStudio/Karpathy LLM-wiki article (see corpus record `karpathy-llm-wiki-mindstudio.web.md`) — the agent read this article live via web_fetch mid-session.
- Tools: NotebookLM, Gamma, Claude (Cowork / Claude Design).
- Session flow evolved through multiple rounds of presenter feedback into an "evolution" narrative (manual slides → all-in-one generative tools → limits of that wave, incl. explicit discussion of how knowledge gets lost when the focus is only the presentation → the Karpathy LLM-wiki pattern → demo → discussion), then was explicitly condensed ("Resumilo") into the final README table.
- Explicitly recognized as mirroring Talksmith's own `draft.md` → `final.md` → deck pattern (agent's own observation, not necessarily presenter-endorsed framing).

**Learning objectives (5 points, approved as "perfecto" by presenter) — final version:**
1. Comprender el cambio de paradigma — de chatear a delegar.
2. Desarrollar criterio profesional — filosofía por sobre herramienta puntual.
3. Conocer las principales herramientas de agentes — Claude Cowork, Paperclip y otras.
4. Hands-on con la primera misión aplicada (Atlas). [Presenter explicitly changed "Experimentar" framing to "Hands-on."]
5. Reflexionar sobre el impacto en la gestión y los negocios — y cómo aplicarlo a mi propio trabajo. [Presenter explicitly pushed to add the "cómo aplicarlo" / "qué hago yo, a partir de mañana" angle — this was not in the agent's first draft.]

**Evaluation structure (adapted from a slide image the presenter described, "Evaluación del Curso"):**
| Componente | % | Detalle |
|---|---|---|
| Portafolio Grupal | 40% | Misiones resueltas con guía de prompts y reflexiones del equipo — se van a ir presentando a lo largo del curso (presenter explicitly asked NOT to list individual missions by name here) |
| Examen Integrador | 40% | Evaluación individual — 45 minutos |
| Participación | 20% | Actividades prácticas y compromiso durante sesiones presenciales y virtuales |
- Presenter confirmed "Portafolio Grupal" = the course's named missions (Atlas Días 1-2, Enterprise Día 5, Paperclip Día 6), then reversed and asked to NOT list them explicitly in the table.
- **Open / never confirmed**: whether the 45-minute Examen Integrador happens on Día 7 (Evaluation) — the agent asked this twice (once mid-session, once near the end) and it was never answered by the presenter.

**Cierre y Portafolios (adapted from another slide image, "Cierre y Portafolios"):**
- Slide described 5 "misiones resueltas" but the course only has 3 named missions (Atlas, Enterprise, Paperclip) plus undefined Días 3–4 — the agent flagged this numeric mismatch explicitly. Presenter resolved it by removing the specific number: "vamos a ir entregando misiones dirante la cursada," and explicitly deferred further detail ("vamos a ser más específicos luego").
- Final structure: 01 Pitch grupal (5 min) · 02 Portafolio completo (misiones entregadas + guía de prompts + reflexiones) · 03 Evaluación de pares (rúbrica) · 04 Reflexión de cierre (próximos pasos profesionales).

**Tools table ("Herramientas del Curso"), iterated 4 times based on presenter feedback:**
- v1 (agent draft): 3 columns — Agentes y Orquestación | Análisis y Conocimiento | Producción de Contenido.
- v2 (presenter: "Partiria Agentes y Orquestación en dos"): 4 columns — Automatización | Agentes | Análisis y Conocimiento | Producción de Contenido.
- v3 (presenter: fold NotebookLM etc. into Producción de Contenido): back to 3 columns — **Automatización** (Claude Cowork) | **Agentes** (Paperclip) | **Producción de Contenido** (NotebookLM · Gamma AI · Claude).
- Final addition: a note that a Cowork license will be provided **per group**, not per student — presenter-specified, not previously documented anywhere.

**"Cómo vemos el futuro de los knowledge workers" section (major new README section, added and then heavily revised):**
- Presenter's own thesis, stated directly in-chat: not replacement, but amplification — tools don't replace managers, they amplify day-to-day efficiency. Presenter then asked the agent to search the web for supporting data on "most common tasks for managers that get amplified."
- Agent ran two live web searches ("AI agents amplify knowledge workers managers tasks 2026 research report" and "most common tasks managers delegate to AI agents survey 2026") and surfaced: Microsoft's "agent bosses" framing and Frontier-Firm data (see corpus record `microsoft-work-trend-index-2026.web.md` — **note**: the corpus record for that source flags that the literal phrase "agent bosses" was not found in the actually-captured page.md text, so this may be a paraphrase introduced by the live web search rather than a direct Microsoft quote — flag before using in slides), ~6.4 hours/week saved and 9x–66x cost reduction for standardized work (unsourced/uncited figure — no article in this corpus substantiates the "6.4 hours" or "9x-66x" figures directly), and adoption survey data now corroborated by the Zapier corpus record (`zapier-agentic-ai-adoption-survey-2026.web.md`): data management 47%, document analysis/summary 41%, report generation 36%, plus mentions of "research synthesis" and "meeting summarization" that the agent could not find hard percentages for.
- Presenter explicitly said the course leans on Microsoft's framing specifically ("Me gusta el enfoque de microsoft"), had the agent read the *full* WTI report via web_fetch (beyond the initial search snippet), and had the section built into the README before Objective.
- Presenter then walked this content through several rounds of trims: reposition to top of README (before Objective) → remove Copilot-specific mention, compress to intro paragraph + 4 bullets → reframe Microsoft's WTI as "one of several" references rather than the sole source → move citation links to footnotes `[1]` → translate the whole README to English → promote "What kind of work do leaders actually delegate?" from prose to its own `##` subtitle with a data table → add a "delegation follows repetition / automation and delegation are often the same move" idea → explicitly reject connecting this idea to specific course tools (Cowork Day 2 / Paperclip Day 6), keeping it at the philosophy level only → shorten again ("Can be shorter?") → finally rewrite the Objective section to open by directly citing this thesis and the delegated-work table, instead of repeating the message from scratch.
- A `# References` section with 3 numbered sources (Microsoft WTI, MindStudio/Karpathy, Zapier) was added at the end of the README.
- Whole README was translated to English in this pass, including "Presencial" → "In-person" globally (via sed), with the agent manually catching and fixing leftover Spanish fragments afterward.
- Session ended with an "Export to PDF" request — README.md converted via pandoc + xelatex (DejaVu Sans font for special characters ●/✓, emojis stripped via regex, table of contents included), verified with pdftotext, and delivered to the presenter.

## Definitions and terminology
- **"Agente Inteligentes"**: new course title (replacing implicit "MIM — Augmented" framing), scoped to `class` field for this specific class, NOT the shared `Subject` — though the presenter later did choose to also update the shared `Subject` in `config/profile.md`.
- **Frontier Professionals / Frontier Firms / Owned Intelligence**: Microsoft WTI terms carried into the discussion; see the Microsoft corpus record for full definitions.
- **Human-in-the-loop**: raised by the agent as the "dominant management style" (38% of companies per Zapier survey) and connected qualitatively to the course's own governance approach (Cowork Día 2's "no audit trail, every output is a draft" framing, Paperclip Día 6) — though per the presenter's explicit instruction, this connection was ultimately kept at a philosophical level and NOT written into the README as a direct tool reference.
- **Declarative repetition**: presenter-introduced framing — the goal of delegating a task isn't just to do it once with agent help, but to describe it declaratively (a Skill, an Instruction, a plain-markdown spec of "what good looks like") so it repeats on its own. Presenter treated "automate" and "delegate" as "often the same move in disguise."

## Evidence and examples
- Slide images described by the presenter inline (not actual image files — these are the presenter's verbal/textual descriptions of existing slides they're referencing, no image bytes exist in the raw source for this chat transcript):
  1. "Objetivos de Aprendizaje" — 5-point numbered card slide (Comprender el panorama GenAI 2026, Desarrollar criterio profesional, Conocer los principales modelos GenAI, Experimentar la primera misión aplicada, Reflexionar sobre el impacto en negocios) — used as a structural template, then substantially reworded for "Agentes Inteligentes."
  2. "Evaluación del Curso" — pie chart + cards (40% Portafolio Grupal / 40% Examen Integrador / 20% Participación) — adopted directly, same percentages.
  3. "Cierre y Portafolios" — 4-step slide (Pitch grupal, Portafolio completo with "5 misiones resueltas," Evaluación de pares, Reflexión de cierre) — adopted with the "5 misiones" claim removed due to mismatch with the actual 3-mission course structure.
  4. "Herramientas del Curso" — 3-column slide (Modelos de Lenguaje: Claude/ChatGPT/Gemini/Perplexity; Análisis y Conocimiento: NotebookLM; Producción de Contenido: Gamma AI/Canva AI) — used as a structural template, then completely re-populated with course-specific tools (Cowork, Paperclip) rather than the generic tools shown in the slide.
- Two live web searches performed by the agent (queries preserved above) and one live full-report `web_fetch` of the Microsoft WTI page — this is the origin of the `microsoft-work-trend-index-2026.web.md`, `karpathy-llm-wiki-mindstudio.web.md`, and `zapier-agentic-ai-adoption-survey-2026.web.md` corpus sources; a fourth source (Deloitte Insights — Agentic AI strategy) was surfaced by the agent's search and cited as a "Sources" link but was **not** captured/ingested into research/web/ and therefore has no corpus record — flag as a gap if the presenter wants it included later.

## Inconsistencies / open questions
- **The session's stated topic — ground rules and criterio de aprobación — was never actually completed.** The agent explicitly re-raised the original open questions twice (mid-session and near the very end) and they were never answered:
  - Asistencia: ¿mínimo de clases obligatorias? ¿distinto presencial vs. virtual? — **never answered**.
  - Uso de IA en el curso: ¿reglas específicas sobre cómo usar las herramientas en clases y entregas? — **never answered**.
  - Puntualidad / dispositivos / participación en vivo para presenciales — **never answered**.
  - Escala de calificación: ¿aprobado/desaprobado, nota numérica, u otra? — **never answered**. (The 40/40/20 evaluation breakdown was defined, but not the pass/fail vs. numeric grading scale question.)
  - The session closed with the presenter saying "Listo. ya termine la exploracion." immediately after an unrelated PDF-export request — the ground rules topic was abandoned, not explicitly deferred by name at closure (contrast with earlier points in the session where open items *were* explicitly flagged as "queda pendiente").
- **Whether the 45-min Examen Integrador happens on Día 7** — asked twice by the agent, never confirmed by the presenter.
- **Días 3–4**: Día 3 was fully defined in this session (Construyendo Presentaciones con IA); **Día 4 remains "a definir"** at session close — never discussed.
- **Rejected/abandoned thread**: the "Escalera del Trabajador Aumentado" 6-stage framework (Delegar/Automatizar/TBD/Escalar/Orquestar/Evaluar) was proposed by the agent as a replacement for the deleted Industry 4.0 framework, then explicitly rejected by the presenter ("Borremos por ahora ese marco") — the README currently has no organizing narrative framework at all. This is a genuine open gap, not resolved elsewhere in the session.
- **Self-correction on evaluation criteria wording**: presenter first confirmed "Portafolio Grupal" = the 3 named missions, then reversed course and asked the agent to remove the explicit mission list from that table row — a direct in-session contradiction/correction, both states preserved above.
- **Presenter pushback pattern**: multiple direct rejections/redirections of the agent's proposals — rejecting the 6-stage framework outright, correcting "Experimentar" to "Hands-on" in objective #4, insisting the Day 3 session flow read as an "evolución" rather than discrete blocks, explicitly forbidding a tool-specific connection (Cowork/Paperclip) in the delegation-philosophy paragraph, and asking twice for the same content to be shortened.
- **Unverified/possibly-hallucinated figures surfaced via live web search** (flagged for downstream fact-check before use in slides): "agent bosses" as a literal Microsoft term (not found in the captured Microsoft page.md — see that corpus record); "~6.4 hours per week saved" and "9x–66x cost reduction" figures attributed to knowledge workers using agents in production — no corpus source in this ingestion substantiates either figure precisely; a fourth cited source, Deloitte Insights ("Agentic AI strategy"), was never actually captured into research/web/, so its claims are unverifiable from this corpus.
- Two chat turns show "[No response requested.]" from the Agent (after "Continue from where you left off." with no real continuation, and after "Si hay algun articulo importante..." which the presenter followed immediately with a different instruction) — preserved as-is, not condensed, per the no-condensing rule for chat exports.

## Images / diagrams
No image files exist in the raw source for this chat transcript — the presenter's messages contain inline textual descriptions of slide images (marked `[Imagen: ...]` in the original transcript) that were never uploaded as image bytes/attachments to this chat-export file itself. These descriptions are preserved verbatim in the Evidence and examples section above. The companion folder `explore-ground-rules-criterio-aprobacion-2026-07-15.md/images/` has been created per schema (empty companion folder is valid — no bytes to extract).

## Raw / preserved excerpts
> El foco es ver una herramienta pero lo mas importate es aprender el como es la filosofia y la forma de pensar para poder adaptarnos a lo que viene.

> **Foco de la materia (segunda parte — Agentes Inteligentes)**
> La primera parte del curso construyó el marco conceptual: dónde crea valor la IA y cómo pensarla a nivel de negocio. Esta segunda parte es sobre la práctica de trabajar aumentado — cómo Agentes y herramientas de IA multiplican lo que puede hacer un knowledge worker. Vamos a explorar herramientas concretas (Claude Cowork, Paperclip y otras), pero el objetivo no es dominar un producto puntual: es internalizar la filosofía y la forma de pensar detrás de delegar y orquestar trabajo con agentes. El panorama de herramientas cambia rápido — lo que hoy es Cowork, mañana puede tener otro nombre — por eso el foco está en el patrón, no en el botón. Al terminar el curso, van a saber qué preguntarle a una herramienta nueva y cómo evaluarla, no solo cómo usar la de hoy.

> **Lo que se llevan (bullets):**
> - La forma de pensar para delegar trabajo a agentes, no solo ejecutar tareas asistidos por IA.
> - Experiencia hands-on con herramientas reales (Claude Cowork, Paperclip, y otras) como vehículo de aprendizaje — no como el destino.
> - Un criterio propio para evaluar y adoptar herramientas nuevas a medida que el panorama itera.
> - Confianza para operar como "manager aumentado": guiar y supervisar agentes en vez de hacer todo a mano.

> No solo queremos hacerlo, sino poder repetirlo en forma declarativa. [...] "That's why 'automate' and 'delegate' are often the same move in disguise."

> **Nota:** dado que vamos a trabajar con Claude Cowork durante el curso, va a haber una licencia por grupo para poder hacer el trabajo.

> Todavía tenemos pendiente:
> - Confirmar si el Examen Integrador (45 min) va en el Día 7.
> - Las ground rules: asistencia mínima, uso de IA en clases/entregas, puntualidad/dispositivos en presenciales, escala de calificación (aprobado/desaprobado vs. nota numérica).
> ¿Seguimos con alguno de estos, o preferís cerrar la exploración acá y estos temas quedan como preguntas abiertas para retomar después?

> Sources (from the agent's live web-search summary mid-session):
> - [2026 Work Trend Index report: Agents, human agency, and opportunity](https://www.microsoft.com/en-us/worklab/work-trend-index/agents-human-agency-and-the-opportunity-for-every-organization)
> - [AI Agent Use Cases for Knowledge Workers: What's Actually Working in 2026](https://www.mindstudio.ai/blog/ai-agent-use-cases-knowledge-workers-2026)
> - [Zapier — State of agentic AI adoption survey [2026]](https://zapier.com/blog/ai-agents-survey/)
> - [Deloitte Insights — Agentic AI strategy](https://www.deloitte.com/us/en/insights/topics/technology-management/tech-trends/2026/agentic-ai-strategy.html)
