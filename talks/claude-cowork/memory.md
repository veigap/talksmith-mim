# memory.md — claude-cowork-funcional

**Current step:** 6 — Polish, complete (2026-07-14) → siguiente: Step 7 (Render, opcional)
**Topic:** Claude Cowork — capacidades funcionales y de uso para el trabajo diario (enfoque de alto nivel).
**Folder:** talks/claude-cowork/
**Started:** 2026-06-05

---

## Talk briefing

Charla nueva sobre Claude Cowork. En espíritu, similar a la charla existente de Claude (`claude-code-y-cowork`), pero más alto nivel: foco en la parte funcional / de uso de Cowork, dejando de lado Claude Code y los detalles de persistencia y archivos.

---

## 2026-06-05 — Step 1 (Frame)
- Status: complete
- Asks log:
  - 2026-06-05 — "¿Querés agregar o afinar algo del briefing (audiencia, outcome, duración)?" → No, el contexto está bien.
  - 2026-06-05 — "Nombre de carpeta (claude-cowork-funcional / cowork-para-el-trabajo-diario / claude-cowork-alto-nivel)" → claude-cowork-funcional
- What was decided: Nueva presentación dentro del subject "AI Generativa para Biomedicina". Foco funcional/alto nivel en Claude Cowork; se deja fuera Claude Code y detalles de persistencia/archivos. Referencia de espíritu: talk existente claude-code-y-cowork.
- Key inputs: Briefing verbatim del presentador (arriba). Perfil del subject ya completo.
- Files created/modified: talks/claude-cowork-funcional/ (árbol completo), memory.md
- Pending open questions: none

## 2026-06-05 — Step 2 (Collect)
- Status: complete
- What was decided: El presentador subió dos ZIPs a research/llm-chats/ y declaró que subió todo el research. Empieza de cero (referirá al talk anterior solo si hace falta).
- Key inputs: research/llm-chats/agentic-ai-deck.zip; "research/llm-chats/mision - auto.zip"
- Files created/modified: ninguno
- Pending open questions: none

## 2026-06-05 — Step 3 (Corpus)
- Status: complete
- Asks log:
  - 2026-06-05 — "¿Transcribir las 3 imágenes ahora / solo texto / diferir?" → 3 (diferir; Phase 2 no corrida)
- What was decided: Dos fuentes estructuradas losslessly (chat-export ambas). Imágenes diferidas.
- Key inputs:
  - corpus/agentic-ai-deck.zip.md — esqueleto 73 slides Code+Cowork; Cowork-funcional extraído verbatim, Code preservado pero marcado fuera-de-foco.
  - "corpus/mision - auto.zip.md" — misión "Atlas" punta a punta (4 hitos, prompts exactos, solución Cowork, equivalente Codex + 2 tablas comparativas, datos de ejemplo, estructura del tablero). Fuente más on-target.
- Files created/modified: research/corpus/*.md (2 registros); companion images/ (3 PNG extraídas, sin transcribir)
- Notas: (a) ShareDuo = sharing nativo de Cowork (update_artifact_settings share="duo"), NO un MCP a instalar — el brief se equivoca, la solución corrige. (b) Falta carpeta skills/ con los 3 skills pre-armados (reporte-semanal, buscar-accion, publicar-tablero) — confirmar con presentador. (c) cowork-vs-codex ya excluye Code (alineado con el foco).
- Pending open questions: 3 imágenes sin transcribir (diferidas); falta carpeta skills/; vigencia de features vs docs oficiales.

## 2026-06-05 — Step 4 (Draft)
- Status: complete
- Modo: C (Presenter Outline) — se estructuró el outline verbatim del presentador contra el corpus. Question budget crítico: 0 preguntas (ninguna bloqueante).
- What was decided:
  - draft.md creado de cero (no existía). Thesis + agenda de 6 secciones + Conclusions (2 slides). 14 slides numeradas en total.
  - Agrupación final (orden del presentador respetado): 1. De chat a agente / dónde encaja Cowork · 2. Lo básico (interfaz + Instrucciones + Projects) · 3. Extender (Skills + sideway MD/metadata) · 4. Conectar y automatizar (Connectors/MCP + Schedule) · 5. Compartir (Live Artifacts) · 6. Advanced (Subagentes + Plugins).
  - Estructura "Concepto / Cosas importantes / Por qué importa" aplicada donde el presentador la pidió (Instrucciones, Projects, MD/metadata sideway).
  - (Demo time) marcado como slide-interstitial de demo en vivo (2.1), con la imagen anotada de la pestaña Cowork como respaldo.
  - Claude Code de-enfatizado: solo aparece como contraste en la sección 1; internals movidos a Cut material.
  - Honradas las accuracy notes del librarian: ShareDuo = sharing integrado (NO MCP), corregido en slide 5.1; trampa del Save de Skills en Cowork renderizada fiel en slide 3.1; carpeta skills/ ausente NO inventada (en Open questions).
- Diagramas insertados (5 ascii blocks, todos con ascii-note): (1) tres superficies / mismo motor [1.1]; (2) cambio de paradigma chat→agente [1.2]; (3) flujo de llamada a Connector vía MCP [4.1]; (4) fan-out de subagentes [6.1]; (5) loop completo de Atlas [Conclusions.1].
- Imágenes cableadas (3 refs, todas existen en disco): screenshot-cowork-tab.png [2.1 Demo]; mockup-tablero.png [5.1 Live Artifacts]. (screenshot-chat-tab.png disponible pero no cableada — la anatomía Cowork cubre la necesidad de la demo; se puede sumar en Review si se quiere.)
- Key inputs: outline verbatim del presentador; profile.md; corpus/agentic-ai-deck.zip.md + "corpus/mision - auto.zip.md".
- Files created/modified: draft.md (nuevo), memory.md
- Pending open questions: fecha de clase sin confirmar (date: 2026-06-XX placeholder); 3 imágenes con pending stub (Phase 2 sin correr) — slides 2.1 y 5.1 citan stubs, re-verificar tras Phase 2; carpeta skills/ ausente del export; vigencia de features point-in-time.

## 2026-06-08 — Step 5 (Review) — round 1
- Status: complete
- What was decided: 3 bullets de Presenter feedback procesados con el ciclo stamp→fix→close→mirror. Sin conflictos (3 slides distintas). Todos cerrados y reflejados en backlog; sanity check limpio (0 closed-unmirrored, 0 unstamped).
  - Bullet 1 — Slide 1.1 "Las tres superficies de Claude": el claim "mismo motor" se verificó y precisó. Reescrito Content (mismos modelos Claude en las tres; Code↔Cowork comparten el Agent SDK, Cowork construido sobre Claude Code; Web/Chat = superficie de chat) y el ASCII (base = "MISMOS MODELOS CLAUDE" + lazo "Agent SDK" uniendo Code y Cowork, no Web/Chat) + ascii-note. Sumadas 2 fuentes externas de Anthropic (product page Cowork + Engineering Agent SDK). Tags: slide-content, accuracy, sources, visual.
  - Bullet 2 — Slide 1.2 "De chat a agente": añadida cita reforzadora de la product page de Cowork ("menos una sesión de chat, más asignarle tareas a un colega") como bullet quotable en Content y remate en Speaker notes; +2 fuentes (product page + Engineering Agent SDK). Tags: slide-content, sources, add-visual.
  - Bullet 3 — Slide 2.1 (Demo): insertada nueva slide 2.2 "Los bloques de Cowork: cada problema, una pieza" antes de Instrucciones, con pirámide ASCII (base→cima: chatear · Instrucciones · Projects · Skills · Connectors/MCP · Schedule · Live Artifacts), cada capa emparejada con su problema recurrente y enmarcada como el roadmap de la charla. Instrucciones renumerada 2.2→2.3, Projects 2.3→2.4. Tags: slide-content, add-visual, split, roadmap.
- Cambios estructurales: Sección 2 pasó de 3 a 4 slides; total de slides 14→15. Diagramas ASCII 5→6 (nuevo: pirámide de building blocks en 2.2). Sin slides eliminadas; nada a Cut material.
- Verificaciones: fences balanceados (12 fences / 6 bloques `ascii`, todos pareados); refs de imagen resuelven en disco (screenshot-cowork-tab.png; mockup-tablero.png — el path usa %20 para el espacio literal, bytes presentes).
- Nuevos tags introducidos en backlog: accuracy, sources, roadmap (reutilizados slide-content, visual, add-visual, split).
- Key inputs: 3 bullets verbatim del presentador; hechos verificados provistos (Cowork built on Claude Code foundations / Agent SDK; mismos modelos en las tres superficies); corpus/agentic-ai-deck.zip.md.
- Files created/modified: draft.md (3 fixes + slide nueva + renumeración), config/feedback-backlog.md (3 filas), memory.md
- Pending open questions: (heredadas) fecha de clase placeholder; pending stubs de imágenes (Phase 2 sin correr); carpeta skills/ ausente; vigencia point-in-time. Nuevas referencias externas (URLs de Anthropic) a re-verificar en Polish si se quiere snapshot.

## 2026-06-08 — Step 5 (Review) — round 2
- Status: complete
- Origen: pedido por chat del presentador (no un bullet de draft.md). Cambio único de tipo add-slide.
- What was decided: Insertada una slide nueva en la Sección 1, entre 1.1 ("Las tres superficies de Claude") y "De chat a agente".
  - Nueva slide 1.2 — "El superpoder de Cowork: la herramienta de propósito general del knowledge worker". Beat de "¿por qué me importa?" colocado tras ubicar las tres superficies; tono motivacional/alto nivel, la mecánica viene después.
  - Content: (a) la idea grande Code=developers / Cowork=knowledge worker (no programa); (b) público — investigadores, analistas, operaciones, legales, finanzas, sin base técnica; (c) analogía del "nuevo Excel" atribuida explícitamente como encuadre de analistas/industria, NO como claim de Anthropic; (d) encuadre OFICIAL de Anthropic citado como tal — "Claude Code para el resto de tu trabajo", la ambición de que todo knowledge worker sienta lo que los ingenieros con Claude Code, nacido generalizando un éxito probado primero con developers; (e) por-qué-importa para bioingeniería (la habilidad base del trabajo del conocimiento se redefine ahora; llegar temprano es ventaja).
  - ASCII render-driving (sin image ref) con ascii-note: Excel (~40 años, lingua franca de oficina) → herramientas agénticas (Claude Code=developers, Cowork=knowledge worker) como la nueva habilidad base.
  - Sources: corpus/agentic-ai-deck.zip.md (posicionamiento Cowork vs Code) + 4 externas — product page Cowork, Cowork research preview blog (claude.com), CNBC (office-worker framing), ensayo "Claude Code is the New Excel" (substack; atribución de la analogía Excel). La analogía Excel atribuida al ensayo, NO a Anthropic.
  - Speaker notes ~4-5 min, motivacionales; cuidado de atribuir la analogía Excel a la industria y "Claude Code para el resto de tu trabajo" como framing propio de Anthropic.
- Cambios estructurales: "De chat a agente" renumerada 1.2→1.3; Sección 1 pasó de 2 a 3 slides; total de slides 15→16. Diagramas ASCII 6→7 (nuevo: Excel→agénticas en 1.2). Sin slides eliminadas; nada a Cut material.
- Verificaciones: fences balanceados (14 líneas ``` / 7 bloques `ascii`, todos pareados); refs de imagen sin cambios y resuelven en disco (screenshot-cowork-tab.png 132 KB; mockup-tablero.png 263 KB).
- Backlog: 1 fila nueva (origin: presenter-chat) con tags [slide-content, sources, positioning, add-slide, add-visual]. Nuevos tags introducidos: positioning, add-slide.
- Key inputs: pedido verbatim del presentador (chat); profile.md; corpus/agentic-ai-deck.zip.md; URLs externas provistas en el pedido.
- Files created/modified: draft.md (slide nueva + renumeración 1.2→1.3), config/feedback-backlog.md (1 fila), memory.md
- Pending open questions: (heredadas, sin cambios) fecha de clase placeholder; pending stubs de imágenes (Phase 2 sin correr); carpeta skills/ ausente; vigencia point-in-time. Las 4 URLs externas nuevas de 1.2 (incl. la del ensayo del "nuevo Excel") deberían re-verificarse en Polish si se quiere snapshot/cita estable.

## 2026-06-09 — Step 5 (Review) — round 3
- Status: complete
- Lote grande: 17 bullets de Presenter feedback procesados con el ciclo stamp→fix→close→mirror (todos del draft.md). Sin conflictos mutuamente excluyentes (los tríos 2.2 y los pares 3.1/2.3/2.4 son complementarios). Sanity check limpio: 0 unstamped, 0 closed-unmirrored.
- Hechos verificados aplicados (provistos por el orquestador + docs oficiales support.claude.com):
  - Skills en Cowork: NO hay slash commands; los dos caminos reales son lenguaje natural (Claude escribe SKILL.md → habilitar en Customize > Skills, "Save to enable") o subir ZIP. Requiere Code execution. Removido "/create-skill" / "/skill-creator" como método de Cowork.
  - Schedule corre LOCAL (compu despierta + app abierta), se saltea y corre al volver; NO en la nube. Agentes en la nube = funcionalidad separada, fuera de alcance (one-liner).
  - ShareDuo NO es capacidad de Cowork: removidas TODAS las referencias + el mecanismo inventado share="duo" (en 5.1 y en el ASCII del loop de Conclusions). Reescrita la realidad oficial de Live Artifacts (local-no-nube, NO compartible aún/roadmap, persiste en pestaña Live artifacts, refresca con datos, versiones, usa connectors aprobados sin re-preguntar; dos formas de crear).
  - Plugins en Team/Enterprise: Owner gestiona en Organization settings; marketplace privado (ZIP o sync GitHub auto-actualiza); preferencia de instalación por plugin; distribución a chat + Cowork; miembros instalan/habilitan; updates sincronizan.
  - Subagente se agrega como una Skill (descripción de cuándo usarlo + instrucciones): pedírselo a Claude (se gestiona en Customize) o vía Plugin. Alto nivel, sin rutas de archivo.
- NUEVAS SLIDES (5): 2.5 "El selector de carpetas y el panel de contexto" (project.png + context.png); 3.3 "Anatomía de un SKILL.md" (ASCII metadata/header vs cuerpo); 4.2 "Cómo se registra un Connector" (connectors_directory.png + connector_browser.png, contenido movido desde 4.1); 6.3 "Plugins en una cuenta Team: ciclo de vida" (ASCII del ciclo + 3 fuentes). [La de 2.1 "Demo time" NO es slide nueva — es un banner ASCII dentro de 2.1.]
- Renumeraciones por inserción: Sección 4 Schedule 4.2→4.3 (por la nueva 4.2 Connector). El resto de inserciones usaron el siguiente número correcto (no requirieron renumerar vecinos). Numeración final por sección verificada contigua: S1=3, S2=5, S3=3, S4=3, S5=1, S6=3, Conclusions=2.
- Conteos: total slides 16→20 (+4 slides nuevas). ASCII blocks 7→10 (nuevos: banner DEMO TIME 2.1 [doc-only], anatomía SKILL.md 3.3, ciclo Plugins Team 6.3; la pirámide 2.2 se reescribió a "bloques apilados + Plugins transversal", no se sumó). Render-driving = 9; doc-only = 1 (el banner DEMO TIME, porque 2.1 ya tiene image ref → el pipeline lo marcaría doc-only; flagged en Open questions). Bloque ```text nuevo en 2.3 (ejemplo de Instructions de Atlas, code-fence, no diagrama).
- Imágenes cableadas nuevas (5, todas existen en disco): project.png, context.png, connectors_directory.png, connector_browser.png, schedule.png. Las 2 corpus (screenshot-cowork-tab, mockup-tablero) sin cambios. Las 7 refs resuelven.
- PASADA TRANSVERSAL de minimización de Claude Code (audiencia sin exposición a Claude Code): comparación Claude Code conservada SOLO en Sección 1 (1.1/1.2). Limpiezas fuera de S1: (a) 2.3 Instrucciones — sacada la equivalencia CLAUDE.md/Claude Code del Content (a notes, neutral) y la mención CLAUDE.md de Sources; (b) 2.4 Projects — borrado "no hay settings.json que editar" de Content + limpiezas en Sources y notes; (c) 6.2 Plugins — quitado "(eso es un mecanismo de Claude Code)" / "a diferencia de Claude Code" de Content y notes; (d) 6.1 Subagentes — quitada la referencia a config "/agents" de Claude Code. Conservados (factuales sobre Cowork, no comparaciones): "No hay slash commands: Cowork es GUI" en 2.1 y 3.1.
- Compactación: 1.2 "El superpoder" reducida de 5 bullets largos a 4 concisos (core preservado; detalle de soporte ya estaba en Speaker notes).
- Fuentes nuevas agregadas (round 3): support.claude.com — use-skills, create-custom-skills (3.1); schedule-recurring-tasks (4.3); use-live-artifacts (5.1, reemplaza la fuente ShareDuo); manage-org-plugins + use-plugins (6.3). claude.com/blog — cowork-plugins-across-enterprise (6.3). code.claude.com/docs — sub-agents (6.1).
- Verificaciones: fences balanceados (22 líneas ``` = 11 opens [10 ascii + 1 text] / 11 closes, todos pareados); 7 refs de imagen resuelven en disco.
- Backlog: 17 filas nuevas en config/feedback-backlog.md. Tags nuevos introducidos: code-minimization, example, compact (reutilizados slide-content, accuracy, sources, visual, add-visual, add-slide, split, cut, too-dense, roadmap).
- Key inputs: 17 bullets verbatim del presentador; hechos verificados + URLs provistos por el orquestador; corpus/'mision - auto.zip.md' (Instructions de Atlas exactas, Step 1.1); corpus/agentic-ai-deck.zip.md.
- Files created/modified: draft.md (17 fixes + 4 slides nuevas + pasada Claude-Code-min + Open questions), config/feedback-backlog.md (17 filas), memory.md
- Pending open questions: (heredadas) fecha de clase placeholder; pending stubs de imágenes; carpeta skills/ ausente; vigencia point-in-time. NUEVA: interacción del banner DEMO TIME en 2.1 (slide con image ref → el banner ASCII quedaría doc-only en Polish; decisión a confirmar con el presentador: mover el banner a slide propia, quitar el screenshot de respaldo, o aceptarlo solo como ASCII). Re-verificar las URLs externas nuevas de round 3 en Polish si se quiere snapshot.

## 2026-06-09 — Step 6 (Polish)
- Status: complete
- What was decided: Producido final.md como deliverable. El render ASCII→SVG ya había corrido (10 bloques render-driving en images/ con sidecars .ascii; plan anotado en images/.critique/plan.annotated.json). Aplicadas las cuatro transformaciones de Step 6 sobre final.md ÚNICAMENTE (draft.md congelado/read-only desde Step 6).
  - (0) Copy: final.md ya existía (copia byte-a-byte de draft.md hecha por el orquestador); se operó sobre él.
  - (a) Inline SVGs: `polish-ascii cleanup` reescribió 10 fences ```ascii → image refs con eco `<!-- ascii-source: -->`, dejando los `<!-- ascii-note: -->` post-fence en su lugar. 1 bloque saltado (el banner DEMO TIME de 2.1, render:null = documentation-only). Confirmado: queda exactamente 1 fence ```ascii (el banner doc-only).
  - (b) Consolidar refs + regla Keynote-safe (solo PNG/JPG): copiadas a images/ las 2 companions del corpus (screenshot-cowork-tab.png, mockup-tablero.png) y reescritos sus refs (sin colisión de nombres). Reescritos los 10 refs SVG de ilustrador a sus companions .png (las 10 .png existen en disco; los .svg quedan en disco como source-of-truth). Auditoría de extensiones: 0 refs prohibidos (.svg/.webp/.avif/.heic). Las 17 refs de imagen resuelven a archivos reales en disco, todas bajo images/.
  - (c) Rescue [open]: `feedback-cycle rescue-open` corrió contra final.md → "no [open] bullets to rescue" (round 3 cerró todo; 0 open). Sin cambios.
  - (d) Strip Presenter feedback: eliminados los 28 bloques (20 H3 `### Presenter feedback` + 8 párrafo `**Presenter feedback:**`, todos vacíos o con solo entradas [closed]+Resolution), cada uno hasta su boundary `---`. Confirmado: 0 strings "Presenter feedback" en final.md. draft.md conserva el log completo como audit trail.
- Conteos finales: 20 slides (## headings); 6 secciones de contenido + Thesis/Agenda/Conclusions/Open questions/Cut material. 10 fences reescritos a image refs; 1 fence ```ascii doc-only restante (banner DEMO TIME 2.1). 12 refs consolidados/reescritos (2 corpus→images/, 10 svg→png). 17 refs totales, todas resuelven.
- Decisión pendiente NO aplicada (a propósito): el banner DEMO TIME en 2.1 se dejó doc-only tal como pidió el orquestador; la decisión de moverlo a slide propia / quitar screenshot queda abierta para el presentador.
- date frontmatter: dejado como placeholder `2026-06-XX` (sin fabricar fecha; el presentador confirma antes de exportar PPTX).
- Key inputs: images/.critique/plan.annotated.json (plan anotado, 11 bloques); sidecars .ascii + .png/.svg en images/; final.md (copia de draft.md).
- Files created/modified: final.md (4 transformaciones); images/screenshot-cowork-tab.png + images/mockup-tablero.png (consolidadas desde corpus); memory.md
- Pending open questions: (heredadas) fecha de clase placeholder (date: 2026-06-XX); pending stubs de imágenes (Phase 2 del librarian sin correr — re-verificar depiction/relevance); carpeta skills/ ausente del export; vigencia point-in-time de features; decisión del banner DEMO TIME 2.1 (doc-only por ahora). Re-verificar URLs externas de rounds 2-3 si se quiere snapshot antes de PPTX.

## 2026-06-09 — Step 7 (Learnings — PROMOTE)
- Status: complete
- What was decided: Promovido UN patrón aprobado por el presentador: verificar afirmaciones sobre productos/features contra documentación oficial y citar las fuentes en la slide antes de presentarlas como hecho. El patrón recurrió ~8× a lo largo del backlog de claude-cowork-funcional (tags accuracy y/o sources).
  - Pass 1 (Promote): nueva entrada **L002** añadida a config/learnings.md tras L001 (formato id/rule/why/where/evidence/date; date 2026-06-09). Rule: cuando una slide afirma un hecho sobre producto/herramienta/feature/versión/precio/capacidad, verificarlo contra documentación oficial/primaria y agregar la(s) fuente(s) a Sources antes de presentarlo como hecho establecido; distinguir el encuadre oficial del vendor del de terceros/analistas y atribuir cada uno.
  - Pass 2 (Move): 9 filas de claude-cowork-funcional con tag accuracy y/o sources movidas de config/feedback-backlog.md → config/feedback-processed.md, cada una con promoted_to: L002 + promoted_at: 2026-06-09.
- Filas movidas (9): 1.1 "mismo motor" [accuracy,sources]; 1.3 "De chat a agente" refuerzo paradigma [sources]; 1.2 "superpoder/nuevo Excel" [sources]; 6.3 "Plugins en Team ciclo de vida" [accuracy,sources]; 6.1 "cómo se agrega un subagente" [sources]; 5.1 "ShareDuo removido" [accuracy,sources]; 4.3 "Schedule local-no-nube" [accuracy,sources]; 3.1 "Skills creation doc" [accuracy,sources]; 3.1 "Skills camino (2) lenguaje natural" [accuracy].
- Filas dejadas intactas en el backlog: las 12 filas restantes de claude-cowork-funcional (sin accuracy/sources: add-slide/add-visual/split/roadmap/cut/code-minimization/example/compact/visual/too-dense) + las 6 filas de senales-1d-biomedicina.
- Key inputs: config/feedback-backlog.md (rows tagged accuracy/sources); patrón aprobado por el presentador (1 solo); formato existente de learnings.md (L001).
- Files created/modified: config/learnings.md (+L002), config/feedback-processed.md (+9 filas con promoted_to/promoted_at), config/feedback-backlog.md (−9 filas), memory.md
- Pending open questions: (heredadas, sin cambios) fecha de clase placeholder; pending stubs de imágenes; carpeta skills/ ausente; vigencia point-in-time; decisión banner DEMO TIME 2.1.

## 2026-06-09 — Step 8 (Render PPTX)
- Status: complete
- Asks log:
  - 2026-06-09 — "¿Promover a biblioteca? ¿Renderizar PPTX?" → 1 (promover) + render
  - 2026-06-09 — "Estilo del deck (strict/free-form)" → a (strict)
  - 2026-06-09 — "Fecha de clase" → mañana = 2026-06-10
- What was decided: Renderizado a PowerPoint en estilo strict desde la base-template. final.md frontmatter date fijada a 2026-06-10.
- Output: output/final.pptx — 27 slides (cover + agenda + 6 secciones/20 slides de contenido + 5 divisores de agenda + 2 Conclusiones), 2.29 MB, OOXML válido. 27 PNGs de critique en output/.critique/.
- Audits: aspect ok; palette/fonts ok (Helvetica/Courier New, paleta §2); cover-fidelity ok; layout-fit ok; block-coverage 0 drops (17/17 imágenes + 2 callouts presentes; "unmatched" del audit = artefacto por matcher de títulos con fuente legacy Roboto, no un drop real). Bug de unidades (body_y EMU vs in) detectado en review visual y corregido + re-render.
- Files created/modified: final.md (date), output/final.pptx, output/final.intermediate.md, output/.critique/*.png, memory.md
- Pending open questions: banner "DEMO TIME" quedó doc-only en 2.1 (decisión diferida); residuos de LibreOffice en output/ (final.pdf, .tmp, lock) host-owned, borrar a mano; carpeta .fc-tmp/ en raíz del repo (residuo), borrar a mano.

## 2026-06-09 — Step 8 (Render) — fix de layout post-render
- Status: complete
- Feedback presentador (chat): "el texto está todo compacto en los paragraphs" — slides con texto a todo el ancho rendían párrafos densos.
- Fix: corregidas in-place 4 slides en output/final.pptx (resto byte-idéntico). 13 (Skills) y 14 (Archivos MD): columna legible ~55%, todos los ítems como bullets consistentes, sin hueco vertical. 17 (Connectors) y 25 (Plugins Team): side-by-side texto-izq / diagrama-der; en 25 el bullet "Qué se puede hacer" se partió en 3 bullets cortos.
- Audits re-corridos: aspect ok, palette/fonts ok, layout-fit ok, block-coverage 0 drops, cover-fidelity ok (modulo falso-positivo Roboto vs Helvetica conocido). 27 PNGs re-rasterizados y verificados visualmente.
- Files: output/final.pptx (27 slides, ~2.29 MB), output/.critique/*.png, memory.md
- Pendiente menor: residuos en output/ (final.pptx.bak, final.pdf, .tmp, lock) host-owned, borrar a mano; .fc-tmp/ en raíz del repo.

## 2026-06-09 — Step 8 (Render) — fix de portabilidad (Keynote/Drive)
- Status: complete
- Feedback presentador (chat): en Drive y Keynote el texto se pisa; en el preview de Cowork no. Causa: cajas de texto de tamaño fijo medidas con métricas de Helvetica + sin autofit → apps que sustituyen/miden distinto desbordan.
- Fix in-place sobre output/final.pptx (slide 1 intacta): (1) autofit shrink-to-fit (<a:normAutofit/>) en 192 text frames (todas las slides 2–27); (2) márgenes internos sanos en 58 frames de cuerpo/título (lIns/rIns 0.1", tIns/bIns 0.05"); (3) resueltos solapes de cajas en slides 5, 10, 24, 27 (alturas recortadas con gutter ≥0.1"); titulos largos con headroom + autofit para wrap a 2 líneas.
- Audits re-corridos: aspect ok, palette/fonts ok (Helvetica/Courier New), layout-fit ok, block-coverage 0 drops, cover-fidelity ok (modulo falso-positivo Roboto vs Helvetica). normAutofit verificado por XML. 27 PNGs re-rasterizados.
- Limitación: no se puede validar Keynote/Drive desde el entorno; el remedio (autofit + sin solapes) es el estándar para ese síntoma. Si persiste en algún slide, iterar puntual.
- Backups: output/final.prefix.bak, final.pptx.bak (host-owned, borrar a mano si se quiere).

## 2026-06-09 — Step 8 (Render) — fix REAL del solape (interlineado, Keynote)
- Status: complete
- Diagnóstico (con screenshot de Keynote del presentador): las líneas de bullets se renderizaban una encima de otra en Keynote/Drive (no en Cowork/LibreOffice). Causa raíz: el interlineado estaba escrito con la unidad equivocada — <a:lnSpc><a:spcPct val="100"/> en vez de val="100000" (OOXML: 100% = 100000). Valores ~100–123 = ~0.1% → Keynote colapsa las líneas. LibreOffice/Cowork lo toleran.
- Fix determinístico: en las 27 slides, todo <a:spcPct val="N"/> con N<1000 → N*1000 (247 valores). Reempaquetado con [Content_Types].xml primero; integridad OK (27 slides, testzip clean). Deck sobrescrito.
- Audits post-fix: aspect ok, palette/fonts ok, block-coverage 0 drops. (autofit normAutofit y márgenes del paso anterior se conservan.)
- NOTA para futuros renders: revisar que el renderer emita lnSpc/spcBef/spcAft spcPct en milésimas de % (100% = 100000). El bug de unidad no se ve en LibreOffice/Cowork, solo en Keynote/PowerPoint/Drive — candidato a regla durable / chequeo en el pipeline pptx.

## 2026-07-08 — Step 5 (Review) — reabierto, round 4
- Status: complete
- Asks log:
  - 2026-07-08 17:11 — "El presentador edita draft.md / deja bullets de feedback y avisa cuando termina" → respondió por chat: reestructura mayor (pedido verbatim abajo)
  - 2026-07-08 — "A) destino de las slides de intro (tres superficies / superpoder / chat→agente)" → A1: se mudan al inicio de la sección de Cowork
  - 2026-07-08 — "B) Instrucciones y Live Artifacts" → B1: ambos quedan dentro de la sección de Cowork
  - 2026-07-08 — "C) Schedule de Cowork vs tareas programadas desde el chat" → C2: se enseña en la sección de chat + queda slide corta en Cowork
- Pedido del presentador (reestructura, resumen fiel): aprovechar que los alumnos ya usan IAs en modo chat para introducir extensiones ANTES de Cowork. Nuevo arco: (1) el chat como está y sus límites (responde de memoria de entrenamiento); (2) Conectores como concepto transversal a todas las IAs — chat solo vs chat con conectores; búsqueda web como primer conector ilustrativo (integrado en casi todos los chats, fácil de configurar); biblioteca oficial de conectores de Claude + no oficiales (mención de conectores personalizados, sin ahondar); ejemplos mail y calendar; diferencia clave memoria-de-entrenamiento vs búsqueda/conector con información real; capacidad ejecutiva (enviar mails, tickets, mensajes, agendar reuniones); (3) tareas programadas desde el chat, usando conectores (ej. resumidor semanal/diario de mails); (4) Cowork + Projects + archivos .md — explicar bien qué es un .md, cómo se lee, y la importancia de llevar la información de trabajo a ese formato (memoria y archivos) por mejor interpretación/edición/creación por parte de la IA, antes de generar el formato final (.docx/.xlsx/PDF); mensaje de apertura de Cowork: es más que "Claude en tu computadora" — cambia por completo la forma de trabajar; (5) Skills se muda al final junto a Subagentes y Plugins (sección avanzada).
- Contexto: la charla ya completó Steps 6–8 (final.md + final.pptx renderizado en strict). Al cerrar esta ronda habrá que re-correr Polish (Step 6) y, si se quiere, re-render PPTX (Step 8) para propagar los cambios.
- What was decided: Reestructura mayor aplicada completa sobre draft.md (una sola pasada, chat-origin, con A1/B1/C2 ya resueltos por el presentador). Arco nuevo de 5 secciones + Conclusions:
  - S1 "El chat que ya usás — y sus límites" (1 slide NUEVA: responde de memoria de entrenamiento — cutoff, alucinación, no ve tu mundo).
  - S2 "Conectores: extender el chat" (5 slides; transversal a todas las IAs): 2.1 NUEVA chat solo vs con conectores; 2.2 NUEVA búsqueda web como primer conector + LA distinción memoria-de-entrenamiento vs búsqueda/conector con info real; 2.3 = ex-4.1 Connectors/MCP reframed chat-first (label del ASCII Cowork→"CHAT/agente"; mención de custom connectors sin ahondar); 2.4 = ex-4.2 directorio reframed (oficial + no oficiales + custom mención; ejemplos guía mail y calendar; MT Newswires conservado); 2.5 NUEVA capacidad ejecutiva (mandar mails/borradores, agendar, tickets, mensajes — con control/autorización).
  - S3 "Tareas programadas: el chat trabaja solo" (1 slide NUEVA, per C2: concepto + tarea programada usando conectores, ej. resumidor semanal/diario de mails; transversal citando ChatGPT tasks; la forma Claude remitida a Cowork).
  - S4 "Cowork: cambiar la forma de trabajar" (12 slides, per A1+B1+C2): 4.1–4.3 = ex-1.1/1.2/1.3 movidas (1.2 abre con el mensaje verbatim del presentador "más que Claude instalado en tu compu — cambia por completo la forma de trabajar"; 1.3 reframed como puente "ya extendiste el chat → ahora delegá"); 4.4 = ex-2.2 roadmap REESCRITO al arco nuevo (bloques chat→conectores→tareas→Cowork→avanzado, marcadores "(visto)"/"estamos acá", Plugins transversal conservado) y posicionado antes de la demo; 4.5 = ex-2.1 Demo (banner DEMO TIME doc-only + screenshot intactos); 4.6 = ex-2.3 Instrucciones; 4.7 = ex-2.4 Projects; 4.8 = ex-2.5 selector/panel; 4.9–4.10 = ex-3.2 sideway .md EXPANDIDO a beat de 2 slides (4.9 qué es un .md / cómo se lee / metadata; 4.10 NUEVA "trabajá en .md, exportá al final": info de trabajo a .md — memoria + archivos — porque la IA interpreta/edita/crea mejor sobre .md; .docx/.xlsx/PDF al último; ASCII pipeline nuevo); 4.11 = ex-4.3 Schedule ADELGAZADA ("lo mismo que viste en el chat, ahora con carpetas y archivos", cross-ref S3, caveat LOCAL conservada, detalle recortado a Cut material); 4.12 = ex-5.1 Live Artifacts cierra la sección.
  - S5 "Advanced: Skills, Subagentes y Plugins": 5.1 = ex-3.1 Skills; 5.2 = ex-3.3 anatomía SKILL.md (re-linkeada al beat .md de S4); 5.3 = ex-6.1 Subagentes; 5.4 = ex-6.2 Plugins; 5.5 = ex-6.3 Plugins en Team.
  - Conclusions (2 slides) al final; conclusions.1 actualizada con el arco nuevo (línea "del chat que respondía de memoria → … → Plugins") y lista de piezas re-ordenada; loop Atlas intacto.
  - Thesis y Agenda reescritas al arco chat-primero (claim de delegación conservado como núcleo).
- Conteos: slides 20→26 (24 de contenido + 2 Conclusions). 6 slides nuevas; 18 movidas/renumeradas (2 de ellas reframed: ex-4.1/4.2); 1 reescrita (roadmap ex-2.2→4.4); 1 adelgazada (ex-4.3→4.11); 1 expandida (ex-3.2→4.9). ASCII blocks 10→16 (6 nuevos: límites del chat 1.1, chat vs conectores 2.1, memoria vs búsqueda viva 2.2, leer vs actuar 2.5, ciclo tarea programada 3.1, pipeline .md 4.10; el banner DEMO TIME sigue doc-only; +1 fence ```text de Instructions sin cambios). 3 entradas nuevas en Cut material (detalle mecánico de Schedule; framing "sideway" de MD; encuadre original del roadmap). Nada eliminado silenciosamente; todos los [closed] históricos conservados con sus slides.
- L002 / fuentes nuevas (round 4): support.claude.com/articles/10684626 (web search), help.openai.com/articles/9237897 (ChatGPT search) y /articles/10291617 (ChatGPT scheduled tasks), claude.com/directory, support.claude.com/articles/11175166 (custom connectors / remote MCP), modelcontextprotocol.io. IMPORTANTE: las herramientas web del entorno estuvieron caídas (outage del clasificador) durante toda la ronda → las URLs se citaron desde conocimiento previo con redacción cautelosa y quedó registrada la VERIFICACIÓN ONLINE PENDIENTE en Open questions del draft. Dos claims deliberadamente esquivados hasta verificar: tareas programadas nativas en el chat de claude.ai (slide 3.1 remite a Cowork) y acciones concretas por conector oficial (slide 2.5 apoyada en MCP-tools + corpus Gmail-borrador).
- Verificaciones corridas: fences balanceados (34 líneas ``` = 17 bloques: 16 ascii + 1 text, todos pareados); 7 image refs y todas resuelven en disco (screenshot-cowork-tab vía corpus companion, connectors_directory, connector_browser, project, context, schedule, mockup-tablero vía corpus companion con %20); numeración contigua por sección (S1=1, S2=1..5, S3=1, S4=1..12, S5=1..5, Conclusions=1..2).
- Backlog: config/feedback-backlog.md CREADO en este repo (no existía) con 1 fila (origin: presenter-chat) tags [restructure, add-slide, add-visual, slide-content, sources, roadmap]. Fila apendeada a mano en el formato del skill (mirror-row requiere bullet en draft.md; el feedback fue por chat), como en round 2. Nota: config/learnings.md no existe en este repo — L002 se aplicó desde su registro en memory.md (Step 7).
- Key inputs: pedido verbatim del presentador (chat) + decisiones A1/B1/C2; draft.md round 3; corpus/agentic-ai-deck.zip.md + "corpus/mision - auto.zip.md"; regla L002 (verificar + citar; distinguir encuadre oficial vs terceros).
- Files created/modified: draft.md (reestructura completa), config/feedback-backlog.md (creado, +1 fila), memory.md
- Pending open questions: (heredadas) fecha de clase placeholder; pending stubs de imágenes (Phase 2); carpeta skills/ ausente; vigencia point-in-time; decisión banner DEMO TIME (ahora slide 4.5). NUEVAS round 4: verificación online de las 6 URLs nuevas (outage); ¿tareas programadas nativas en el chat de claude.ai? (actualizar 3.1 si sí); acciones concretas soportadas por cada conector oficial (2.5); fuente oficial de Google para la mención de Gemini en 2.2 (o suavizar). Tras esta ronda hay que re-correr Step 6 (Polish) y, si se quiere, Step 8 (PPTX): final.md/final.pptx quedaron desactualizados respecto del draft.

## 2026-07-09 — Step 5 (Review) — round 5
- Status: complete
- Origen: presenter-chat (hechos confirmados por el presentador + fuentes verificadas por el orquestador). Acceso web restablecido: TODO verificado online en esta ronda.
- What was decided:
  1. **Slide 3.1 — Claude tiene tareas programadas en claude.ai.** Reescrita con Claude como ejemplo de primera clase junto a ChatGPT: disponibles en el navegador, corren EN LA NUBE (sin compu prendida ni app abierta), beta con rollout desde julio 2026 empezando por Max. Hedge viejo ("la forma Claude se ve en Cowork") removido. Atribución per L002: firsthand del presentador (2026-07-09, "lo estoy usando ahora") + release notes support 12138966 (entrada 2026-07-07, verbatim verificado: "scheduled tasks run with no device online", sesiones remotas beta, rollout Max) + TechCrunch 2026-07-07 (encuadre de terceros, verificado). Speaker notes: sugerida demo en vivo desde la cuenta del docente; caveat de rollout por plan.
  2. **Slide 4.11 — ACCURACY FIX del "corre local".** El hecho round-3 quedó desactualizado el 2026-07-07. Content reescrito: "Corren en la nube (desde julio 2026)" — remoto, en cadencia aunque la compu esté dormida o la app cerrada; planes pagos (Pro/Max/Team/Enterprise); ejecución remota en beta, Max-first; nota explícita de que la limitación vieja ya no aplica. Sources: 13854387 re-fetcheada (AHORA dice "Scheduled tasks run remotely... even when your computer is asleep or the Claude Desktop app is closed") + 12138966 + TechCrunch; caveats del corpus (deck 6.3, misión) marcadas desactualizadas inline. Speaker notes actualizadas. Grep por otros "corre local": solo el [closed] histórico de round 3 (audit trail, intacto por append-only) y la locality de Live Artifacts (claim distinto, ver punto 5).
  3. **Slide 2.5 — Calendar confirmado.** "Agendar/crear eventos vía connector de Calendar" verificado de primera mano por el presentador (2026-07-09) — anotado en Sources y Speaker notes (demo en vivo posible). Sumadas dos fuentes oficiales verificadas para la capacidad ejecutiva general: support 11175166 ("allow Claude to access and take action in these services") y modelcontextprotocol.io ("take actions on your behalf"). Hedge conservado SOLO para tickets y mensajes (nadie los chequeó): presentarlos como capacidad del ecosistema, sin prometer demo.
  4. **Re-verificación de las 6 URLs de round 4** (todas el 2026-07-09): 10684626 web search OK (quotes agregadas a 2.2); 9237897 ChatGPT search OK — fetch directo 403 (anti-bot de help.openai.com) pero existencia y contenido corroborados vía búsqueda; ChatGPT tasks: slug canónico corregido a `10291617-tasks-in-chatgpt` en 3.1; claude.com/directory → redirige a claude.ai/directory (login-gated) → cita reemplazada en 2.1 y 2.4 por el anuncio oficial claude.com/blog/connectors-directory + support 11176164 (use connectors); 11175166 custom connectors OK; modelcontextprotocol.io OK. Entradas correspondientes de Open questions marcadas RESUELTO.
  5. **Chequeo extra (due diligence):** re-verificada la locality de Live Artifacts (support 14729249, artículo actualizado hace un día): SIGUE local / no compartible pese a las sesiones remotas de Cowork → slide 4.12 queda como está; agregada vigilancia en Open questions (candidato #1 a desactualizarse con el rollout web/mobile).
- Verificaciones de estructura: fences balanceados (34 líneas ``` = 17 bloques: 16 ascii + 1 text); 7 image refs, todas resuelven en disco; numeración contigua por sección (S1=1, S2=1..5, S3=1, S4=1..12, S5=1..5, Conclusions=1..2). Sin cambios estructurales en esta ronda (solo contenido/fuentes de 6 slides + Open questions).
- Backlog: 4 filas nuevas en config/feedback-backlog.md (origin: presenter-chat, apendeadas a mano en formato del skill — sin bullets en draft.md). Tag nuevo registrado en el vocabulario: accuracy.
- Key inputs: mensaje del orquestador con hechos del presentador (tareas en claude.ai firsthand; calendar chequeado) + fuentes candidatas; L002; fetches/búsquedas del 2026-07-09.
- Files created/modified: draft.md (slides 3.1, 4.11, 2.5, 2.1, 2.2, 2.4 + Open questions), config/feedback-backlog.md (+4 filas, +tag accuracy), memory.md
- Pending open questions: (heredadas) fecha de clase placeholder; pending stubs de imágenes (Phase 2); carpeta skills/ ausente; decisión banner DEMO TIME (slide 4.5); URLs de round 3 a snapshotear en Polish si se quiere. VIGENTES tras round 5: fuente oficial de Google para la mención de Gemini en 2.2 (o suavizar); verificación por conector de tickets/mensajes (2.5) si se quiere demo en vivo; vigilar locality de Live Artifacts (14729249) durante el rollout web/mobile. Sigue pendiente re-correr Step 6 (Polish) y, si se quiere, Step 8 (PPTX).

## 2026-07-14 — Step 6 (Polish) — re-corrido completo contra el draft nuevo
- Status: complete
- Contexto: el presentador dio el ready de round 5 y trajo el draft re-arquitecturado por branch (5 secciones + Conclusions, 26 slides, arco chat→conectores→tareas programadas→Cowork→advanced; 108.885 bytes vs 77.640 del talk viejo). El final.md/images/ que había en disco eran del talk VIEJO (6 secciones, 20 slides) → Polish se re-corrió desde cero. La branch también reemplazó memory.md (las entradas de Step 6/7 del talk viejo se perdieron con el checkout; este header se corrigió: la carpeta real es talks/claude-cowork/, no claude-cowork-funcional/).
- Pre-Polish (fixes de contenido en draft.md, hechos ANTES de congelar — 4 líneas vs HEAD, verificado por diff):
  - `date:` 2026-06-XX → **Julio 2026** (elegido por el presentador) + nota de Open questions marcada resuelta.
  - 2 refs muertas reparadas: `research/corpus/agentic-ai-deck.zip/images/screenshot-cowork-tab.png` y `research/corpus/mision%20-%20auto.zip/images/mockup-tablero.png` → `images/…`. La carpeta research/ ya no existe; los archivos sí estaban en images/. (Este era el bloqueador #2 registrado: un Polish desde draft.md habría fallado.)
- Illustrator: 17 bloques ASCII (16 render-driving + 1 doc-only = banner DEMO TIME en 4.5, render:null, intencional). **16/16 renderizados**: 10 clean on first pass, 6 clean tras 1 revisión, **0 unresolved, 0 failed**. Cada uno con par .svg + .png en images/ y log de crítica en images/.critique/. sc-1-1 requirió re-render FORZADO: colisionaba de nombre con el render viejo (mismo slug, contenido distinto) y la regla de idempotencia lo habría saltado.
- Editor (4 transformaciones sobre final.md; draft.md verificado byte-idéntico por md5 antes/después):
  - (a) 16 fences → image refs + eco ascii-source. 1 fence ```ascii sobrevive (banner DEMO TIME 4.5).
  - (b) 23 refs live, todos bajo images/, 16 .svg→.png. 0 extensiones prohibidas; 23/23 resuelven; 0 apuntan a los orphans viejos.
  - (c) rescue-open → 0 bullets abiertos (20 closed).
  - (d) 33 bloques de Presenter feedback eliminados (19 H3 + 14 párrafo); 0 strings restantes.
- Verificación independiente (10 checks, todos PASS): 1 fence ascii · 2 líneas ``` · 0 "Presenter feedback" · comentarios HTML 33/33 balanceados · 0 `-->` huérfanos · 21 `--&gt;` escapados · 26 slides · 23/23 refs resuelven · 0 refs a orphans · draft.md solo con los 3 fixes intencionales.
- Logo (setup de proyecto, pedido del presentador): resuelto vía `config/logo.*` — nivel subject, lo heredan TODOS los talks del repo (orden del renderer: frontmatter `logo:` → talks/<Talk>/images/logo.* → **config/logo.*** → placeholder). El presentador subió `config/logo.png` (529×417, **modo RGB sin canal alfa**, fondo gris #E5E5E5 uniforme) y pidió usarlo tal cual → **la portada mostrará el logo dentro de una caja gris**. Se ofreció (y se descartó) la versión con alfa recortada + upscaleada a 960px. Reversible en cualquier momento: el gris es uniforme al 100%, se recorta sin halo. Quedó `config/logo_check_white.png` (preview mío, 296K) en config/ — el presentador rechazó borrarlo; no interfiere (el renderer matchea `logo.png` exacto).
- Files created/modified: draft.md (3 fixes pre-freeze), final.md (regenerado + 4 transformaciones), images/ (16 .svg + 16 .png + 16 .ascii nuevos), images/.critique/ (16 logs + plan/renders/ts-args regenerados), memory.md
- Pending open questions: (heredadas de round 5, sin cambios) fuente oficial de Google para Gemini en 2.2; verificación de tickets/mensajes en 2.5; vigilar locality de Live Artifacts. NUEVAS: (a) el deck html en output/ es del talk VIEJO — **re-render obligatorio antes de compartir**; (b) ~10 sets .svg/.png/.ascii huérfanos en images/ con la numeración vieja (s1-1-1-tres-superficies, s1-2-1-excel, s1-3-1-chat-vs-agente, s2-2-1-bloques, s2-3-1-tarjeta, s3-3-1-anatomia, s4-1-1-flujo-connector, s6-1-1-subagentes, s6-3-1-ciclo-plugins) — el presentador declinó borrarlos; nada en final.md los referencia; (c) el bullet de Open questions sobre el banner DEMO TIME quedó stale en final.md (la decisión ya está tomada: doc-only) — resolver en draft.md en la próxima ronda; (d) logo sin alfa (ver arriba).

## 2026-07-14 — Bugs / inconsistencias detectadas en este Polish
1. **`polish_ascii.py cleanup` no escapa `-->` dentro del eco `ascii-source` — bug real, reincidente y PEOR de lo medido antes.** En este draft: **8 bloques / 21 ocurrencias** (el run anterior contra el talk viejo tuvo 4/10). El comentario HTML cierra en el primer `-->`, el resto del ASCII se filtra al cuerpo renderizado y queda un `-->` suelto. El editor lo parchea a mano (`--&gt;`) **en cada Polish** — el skill lo reintroduce siempre. Máxima prioridad de fix en el plugin: escala con la cantidad de flechas ASCII del talk.
2. **Peligro de espaciado al strippear hasta el boundary `---`.** El primer intento del editor dejó `texto\n---` sin línea en blanco → markdown lo parsea como **setext H2**, corrompiendo silenciosamente 33 boundaries. Lo detectó en verificación y rehízo desde backup. Al menos un bloque del draft tiene el cuerpo pegado al `---` sin blank line.
3. **Colisión de slugs entre re-arquitecturas.** Al renumerarse las secciones, `sc-1-1-loop-completo-atlas` mantuvo el nombre pero cambió de contenido → la regla de idempotencia (match por prefijo `<slide-id>-<n>-`) lo habría saltado como "unchanged" y habría shipeado el diagrama viejo. Detectado comparando mtime del .svg (20:36, run viejo) contra el .ascii re-extraído (21:13). **La idempotencia debería comparar los bytes del ASCII, no el prefijo del nombre.**
4. **`prepare-render-args` hornea paths de sesión/VM en los args.** Los escribe con el prefijo del mount (`/sessions/<slug>/mnt/...`), pero los subagentes corren Read/Write en el HOST → primer Read falla en todos. Se resolvió pasando la traducción en el prompt de dispatch. `--repo-root` con el path host lo arreglaría de raíz.
5. **`validate_svg.py` inalcanzable desde el sandbox Linux** (path host-only bajo /var/folders/...). Consecuencia real: **el auto-repair no corre** (dropear width/height en conflicto, strippear preserveAspectRatio="none"); los 16 renders validaron el contrato a mano y ninguno necesitó reparación, pero un render que sí la necesite se colaría hasta el gate `aspect_ratios.py` de Step 7.
6. **El paso 8 del skill hardcodea `qlmanage`** (macOS-only) para el PNG de crítica, mientras el paso 7 ya prefiere `cairosvg`. En Linux eso degrada a `png_companion: failed` y **mata la crítica visual**. `cairosvg` cubre ambas rasterizaciones sin problema — el paso 8 debería tener el mismo fallback.
7. **`diagram-style.md`: path equivocado en el SKILL.md.** El paso 2 dice `<repo_root>/config/diagram-style.md`, pero el archivo vive en el **plugin** (`${CLAUDE_PLUGIN_ROOT}/config/`). Siguiendo el spec al pie de la letra, todo render toma la rama "sin diagram-style.md → defaults" y **pierde silenciosamente las reglas de estilo**.
8. **`markerUnits="strokeWidth"` es el default de SVG** → una flecha acentuada con stroke más grueso escala su punta y pisa la caja destino. Invisible en el XML. Candidato a regla en diagram-style.md: *"todo marker declara `markerUnits="userSpaceOnUse"`"*.
9. **`refX` / terminación de flechas.** Un shaft que corta *antes* del borde destino (el instinto natural, para no pasarse) deja un gap flotante visible al 2×. Regla candidata: *"el shaft termina SOBRE el borde; la geometría del marker maneja el inset"*.
10. **cairosvg NO avanza el cursor x de un `<tspan>` dentro de `<text text-anchor="middle">`** → el tspan se imprime encima del run hermano. Invisible en el XML, mortal en píxeles. Regla candidata: nunca usar énfasis con tspan inline bajo anchoring middle; bold el `<text>` entero o splitear en `<text>` posicionados.
11. **`<text>` colapsa el whitespace inicial sin `xml:space="preserve"`** → en la slide de anatomía del SKILL.md las continuaciones YAML (que se *definen* por indent) renderizaban flush-left. Fidelidad, no cosmética.
12. **El mount VM se atrasa respecto del host.** `config/logo.png` existía en el host y el sandbox lo reportó ausente ~2 min (dos chequeos independientes). Los borrados/creaciones del usuario no se ven de inmediato: ante una ausencia sospechosa, re-chequear por path host antes de afirmar que un archivo no está.
13. **El `Write` se niega a sobrescribir un archivo no leído en sesión** → un re-render forzado sobre un basename existente obliga a un Read testimonial del archivo viejo primero (riesgo de contaminar el render con el arte viejo).
14. **Borrado de archivos bloqueado en el sandbox** (`rm` → "Operation not permitted"); requiere `allow_cowork_file_delete` con aprobación del usuario. Por eso los ~10 sets huérfanos siguen en images/.
