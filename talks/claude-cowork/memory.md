# memory.md — claude-cowork

**Current step:** 4 — Draft (reabierto 2026-07-31) awaiting_presenter
**Awaiting:** 2026-07-31 — aplicada la 5ª ronda de feedback (nota de acceso a archivos en 3.1; Instrucciones partida en 3.4 concepto + 3.5 ejemplo, con la captura instructions.png). Polish y Render re-corridos. Awaiting: los recortes de tiempo (64,0 contra un bloque de 60), la lamina de catalogo de skills, y si pasamos a Learnings.

**Topic:** Claude Cowork — capacidades funcionales y de uso para el trabajo diario (enfoque de alto nivel).
**Folder:** talks/claude-cowork/
**Started:** 2026-06-05

---

## Talk briefing

Charla nueva sobre Claude Cowork. En espíritu, similar a la charla existente de Claude (`claude-code-y-cowork`), pero más alto nivel: foco en la parte funcional / de uso de Cowork, dejando de lado Claude Code y los detalles de persistencia y archivos.

---

## Estado actual — 2026-07-31

### El Talk

- **Parte 2** del split del 2026-07-31, que partió en dos la clase combinada de 120 min. La parte 1 (chat, conectores, Schedule, misión parte 1) vive en `talks/claude-desktop-chat`. Esta carpeta conservó nombre e historia.
- Frontmatter: `class: "Claude Cowork"` · `duration: 60 min (a confirmar)` · `date: Julio 2026` · presenters Paulo Veiga y Marco Sánchez Sorondo.
- **6 secciones + Conclusions, 22 slides:** 1 Claude Cowork (4) · 2 Knowledge & Output (4) · 3 Projects (3) · 4 Skills (4) · 5 Subagentes (1) · Conclusions (3: loop de Faro · wrap-up · cuidados) · 6 La misión · parte 2 (1).
- **Orden nuevo (2026-07-31):** Conclusions va **antes** de la Sección 6. El deck cierra en la placa de la misión, no en la lámina de gobernanza. La Sección 6 conserva su número aunque vaya última.
- **Tiempo objetivo total: 61,0 min** sobre 20 slides, contra `duration: 60 min (a confirmar)`. **1 min pasado**, y la lámina de catálogo sigue pendiente (+2-3 min más). Recorte de reserva: Conclusions.1 de 5 a 3 min devuelve a 59,0.
- **Modo de Draft: C** (Presenter Outline).

### Artefactos

- `draft.md` — **canónico y al día**. 13 bloques de fence (11 `ascii` + 1 `markdown` + 1 `text`): 11 atados a una slide y 2 archivados en `Cut material` (el diagrama del Excel y el banner DEMO TIME), que el scan de polish-ascii saltea por estar bajo un heading sin slides. 5 image refs que resuelven (`screenshot-cowork-tab.png` quedó fuera y `cowork.png` entró en su lugar). 28 campos `Presenter feedback`, **todos vacíos**.
- `final.md`, `output/slide-model.json`, `output/html/index.html` — **desactualizados**: se derivaron antes del reorden de Conclusions. Se re-derivan en el próximo Polish + Render.
- `images/` — 36 archivos tras el gc del último Polish (9 tripletes vivos + 5 screenshots referenciados + 4 imágenes del presentador sin referencia). El próximo Polish vuelve a re-derivar slugs; conviene seguirlo de `polish_ascii.py gc`.
- La directiva `<!-- generate-image -->` de la slide 1.1 **sigue sin generar** (el pase del image-illustrator nunca corrió sobre este deck).
- `draft.feedback-archive-2026-07-30.md` y `memory.archive-2026-07-31.md` — históricos, no se leen en el flujo.

### Decisiones permanentes

- Los campos `Presenter feedback` se dejan **vacíos**; el registro de feedback va solo a `config/feedback-backlog.md`.
- ~~El deck cierra en la lámina de gobernanza (Conclusions.3)~~ — **revertido el 2026-07-31 por instrucción explícita del presentador**: las conclusiones cierran la charla y la placa de la misión va última, porque después de la misión termina la clase. Orden interno de Conclusions sin cambios: loop de Faro → wrap-up → cuidados.
- **Faro solo en la misión.** Desde el 2026-07-31 las láminas de enseñanza (secciones 1-5) usan un hilo genérico, **el informe mensual del equipo** (Project "Informe mensual del equipo" · carpeta `Documentos/Informe-Mensual` · Skill `informe-mensual` sobre `notas/`). Faro sobrevive solo en Conclusions.1 (el loop) y en la Sección 6 (la placa), donde es la misión y no un ejemplo.
- **`/skill-creator` no existe en Cowork** (verificado por el presentador, 2026-07-31). Fuera de todo el deck. Se conserva el tip de tipear `/` y el set reducido de slash commands.
- **Sin lámina de repaso de la parte 1** al abrir la Sección 1 — decisión explícita del presentador, nunca ensayada.
- **Subagentes:** el deck no afirma que se creen o configuren a mano en Cowork (los coordina Claude por debajo, sin panel). Verificado contra el corpus y contra dominios oficiales de Anthropic, sin fuente que diga lo contrario.
- **Audit trail:** la actividad de Cowork no entra en la Compliance API; el registro por OpenTelemetry es de Team/Enterprise y no exporta nada por defecto.
- Este repo **no tiene** `config/principles.md` ni `config/diagram-style.md`: se usan las copias del plugin.

### Pendientes abiertos

- **Lámina de catálogo de skills (Sección 4), sin crear.** Reemplaza a la borrada 4.4. Falta que el presentador elija el catálogo y los 5 skills. Candidatos relevados el 2026-07-31: el **directorio dentro de la app** (Personalizar → Habilidades → "+" → Explorar, instalación de un clic, support 14328846) · **skills.sh** (+91.000, se instala con `npx skills add`) · **github.com/anthropics/skills** (~20, oficial) · **vercel.com/docs/agent-resources/skills** (el link que pasó el presentador, perfil developer).
- **Duración.** 58 min contra un bloque de 60, ~2 min de aire que probablemente se coma la lámina de catálogo. Recorte de reserva y **no aplicado**: Conclusions.1 (loop de Faro) de 5 a 3 min, porque sus dos bullets de prosa duplican el mapa de 1.3 y el peso de la lámina está en el diagrama. Segundo candidato, más discutible: 3.3 Instrucciones (5 min).
- **Nombres de skills desalineados.** La Sección 4 enseña `informe-mensual` y el diagrama de Conclusions.1 muestra `buscar-accion` y `reporte-semanal` (las reales de la misión). Es correcto pero se ve raro; decidir si se aclara en voz alta.
- **Layout ASCII-izquierda / bullets-derecha** (slide 1.2): pedido del presentador **no aplicado**, no existe el template. La intención quedó como hint en la slide (`<!-- layout: image-left -->` debajo del heading, hoy ignorado por el render). Espera un cambio en el plugin.
- **Modos de Cowork** (slide 1.4): la lámina no afirma cuál es el default. La captura vieja decía `Ask`, la nueva dice `Auto`. Confirmar contra la app antes de la clase.
- **`screenshot-cowork-tab.png` sin referencia** desde que 1.4 pasó a `cowork.png`. Se conserva en `images/`; candidato al gc del próximo Polish si el presentador no lo quiere para un antes/después.
- **4 majors y 7 minors** del audit del Composer (scope=full, 2026-07-31) sin aplicar, a releer contra el deck partido.
- La **placa ASCII de 6.1** es gemela de la de `talks/claude-desktop-chat` (slide 5.1); desde el split la verificación de gemeleo es cross-talk y manual.
- Anglicismo **"Connector MT Newswires" / "Connector Gmail"** en el ASCII del loop de Conclusions.1 — señalado tres veces, se deja porque el presentador no pidió el cambio.
- **Bonus M6** de la misión (subagente a pedido) sin verificar de primera mano; una demo en vivo sí lo necesitaría.
- **Watch item:** el registro por OpenTelemetry pide Desktop 1.1.4173+ y la doc dice "not captured … at this time" — re-verificar antes de la clase.
- Stubs de Phase 2 del librarian y la carpeta `skills/` de la misión, sin resolver.

### Historial

El registro paso a paso completo (Steps 1-8, todas las rondas de Review, Polish, Render y Learnings desde 2026-06-05) está en `memory.archive-2026-07-31.md`.

---

## 2026-07-31 — Step 4 (Draft, reabierto)

- Status: awaiting_presenter
- Asks log:
  - 2026-07-31 — "Volvemos a Draft. ¿Por dónde arrancamos: (1) recorte de tiempo ~6 min, (2) los 4 majors + 7 minors del audit del Composer releídos contra el deck partido, (3) material o slides nuevas, (4) repaso completo con audit fresco?" → pending
  - 2026-07-31 — "Hacé clean de la memoria, que solo quede el estado." → aplicado: `memory.md` reducido a header + briefing + estado actual; historial completo movido a `memory.archive-2026-07-31.md`.
- What was decided: <filled at closure>
- Key inputs: <filled at closure>
- Files created/modified: `memory.md` (reescrito), `memory.archive-2026-07-31.md` (nuevo)
- Pending open questions: ver *Estado actual → Pendientes abiertos*.

---

## 2026-07-31 — Step 4 (Draft, ronda de feedback: Sección 1)

- Status: complete
- What was decided:
  - Slide 1.2 "La nueva habilidad base" **borrada**; la analogía del Excel entró como bullet de 1.1 con la atribución intacta (analistas/industria, NO Anthropic) y su fuente `nextword.substack.com` movida a las Sources de 1.1. Las notes de 1.2 se fundieron en las de 1.1 (2 → 3 min). El ASCII de la lámina quedó archivado entero en `Cut material`: no pasó a 1.1 porque esa slide ya lleva una directiva `generate-image`.
  - Salió **"Eso cambia la forma de trabajar."** del primer bullet de 1.1. Sigue, a propósito, en el Claim de la Thesis y en el Goal de la Sección 1, que no se proyectan.
  - Primer bullet de "De chatear a delegar" reescrito: *"Lo que cambia ahora es el rol: **delegar**. ¿Qué delegamos?"*. La referencia a la clase anterior vive ahora solo en las Speaker notes.
  - **No aplicado:** ASCII a la izquierda y bullets a la derecha. No existe el template; queda en `Open questions` esperando un cambio del plugin.
  - Sección 1 renumerada a 4 slides (3→2, 4→3, 5→4) y barridas las 11 referencias cruzadas a la numeración vieja.
- Key inputs: los dos campos `### Presenter feedback` con contenido (slides 1.2 y 1.3 de la numeración vieja); `slide-templates.md` y `principles.md` del plugin.
- Files created/modified: `draft.md`, `config/feedback-backlog.md` (4 filas), `memory.md`.
- Pending open questions: template de layout imagen-izquierda (bloqueado del lado del plugin); duración 64,0 min contra 60; feedback sin procesar en 1.3, 1.4 y 2.1.

---

## 2026-07-31 — Step 4 (Draft, ronda de feedback: segunda tanda)

- Status: complete
- What was decided:
  - **1.3 El mapa** quedó en el diagrama solo, con una línea de lead arriba. Los tres bullets se fundieron en esa línea y en las Speaker notes; el ASCII y su `ascii-note` siguen intactos byte a byte. ~3 min, sin cambio.
  - **1.4 dejó de ser demo en vivo.** Retitulada **"Dónde se empieza en Cowork"**, con `images/cowork.png` (captura propia de la interfaz actual) en lugar de `screenshot-cowork-tab.png`, que quedó desactualizada y sin referencia. Content reescrito con el patrón de las otras láminas de screenshot (3.2, 4.2, 4.3). El banner ASCII DEMO TIME se archivó en `Cut material`. La Misión 0 sobrevive en notes como demo opcional. De ~6 a ~2 min. La lámina **no afirma cuál es el modo por defecto**.
  - **Sección 2 abre con una lámina nueva**, `2.1 "Qué lee el agente en la carpeta"`: la bisagra entre delegar y la mecánica del `.md`. Resto renumerado (1→2, 2→3, 3→4). Fuente nueva: el post de MindStudio sobre el "LLM wiki" de Karpathy, con la atribución desagregada (post de MindStudio, propuesta de Karpathy). ~2 min.
- Key inputs: los tres campos `### Presenter feedback` que quedaron fuera de alcance en la primera tanda; `images/cowork.png` y su descripción verificada por el orquestador; el post de MindStudio verificado por el orquestador; el patrón de las láminas de screenshot 3.2 / 4.2 / 4.3 del propio deck.
- Files created/modified: `draft.md`, `config/feedback-backlog.md` (4 filas), `memory.md`.
- Pending open questions: nombres y default de los modos de Cowork, a confirmar contra la app; `screenshot-cowork-tab.png` sin referencia; duración 62,0 min contra 60.

---

## 2026-07-31 — Step 4 (Draft, hint de layout)

- Status: complete
- What was decided: la intención de layout de la slide 1.2 quedó registrada como metadata en `draft.md`, debajo del heading `## 2. De chatear a delegar`: `<!-- layout: image-left -->` más una línea de comentario con el pedido y el bloqueo. La forma y la ubicación siguen los hints de autor del schema (`template:` / `reveal:` / `aside:`, bajo el `##` de la slide); la clave `layout:` la elegí por analogía con el vocabulario del catálogo (`content+image` → `layout: text-left | image-top`) y **no está reconocida todavía**, así que hoy el render la ignora.
- Key inputs: `schemas/draft.md` (fila de slide hints), `config/pptx-styles/slide-templates.md` (`content+image`), `polish_ascii.py scan` corrido sobre el archivo antes y después.
- Files created/modified: `draft.md` (3 líneas), `config/feedback-backlog.md` (fila existente ampliada, sin fila nueva), `memory.md`.
- Pending open questions: el cambio en el plugin. Dos archivos temporales (`.scan-before.md`, `.scan-after.md`) quedaron en la raíz del repo con una línea que dice que se pueden borrar; `device_bash` no tiene permiso de borrado.

---

## 2026-07-31 — Step 4 (Draft, tercera tanda de feedback)

- Status: complete
- What was decided:
  - **2.1** — el bullet del "LLM wiki" bajó a nota al pie en blockquote con la URL de MindStudio visible; el Content queda en 3 bullets. Se sumó que la carpeta es de **lectura y escritura**, fundido en el primer bullet.
  - **Ejemplos genéricos en vez de Faro** en las secciones 1-5. Hilo único: el informe mensual del equipo. Tocó 1.2 (notes), 2.2 (el bloque `markdown`), 2.3 (el ASCII, que renderiza el mismo archivo), 2.4, 3.1, 3.2, 3.3 (las Instrucciones completas, con regla de oro nueva: toda cifra lleva fuente y fecha) y 4.1. Las Sources que citaban `corpus/mision - auto.zip.md` se conservan, reformuladas.
  - **`/skill-creator` fuera** del Narrative arc, el Goal de la Sección 4, el ASCII de 4.2 (rediseñado a tres caminos convergiendo en la compuerta), sus Sources y notes, y 4.3.
  - **4.3 adelgazada** a menú "+" + trampa del Save, de ~3 a ~2 min. Se conserva Code execution y el tip de tipear `/`.
  - **4.4 "Un SKILL.md por dentro" borrada** y archivada íntegra en `Cut material`. La Sección 4 queda en 3 láminas, esperando la de catálogo.
  - **Conclusions movido antes de la Sección 6.** Orden final: 1-5 → Conclusions → 6. Agenda, Goal de la Sección 6 y las tres transiciones de notes (6.1, Conclusions.2, Conclusions.3) reescritas.
- Key inputs: los 6 campos `Presenter feedback` con contenido; verificación web del 2026-07-31 sobre catálogos de skills (support 14328846, skills.sh, anthropics/skills, docs de Vercel).
- Files created/modified: `draft.md`, `config/feedback-backlog.md` (6 filas), `memory.md`.
- Pending open questions: la lámina de catálogo de skills; nombres de skills desalineados entre Sección 4 y Conclusions.1; layout ASCII-izquierda.

---

## 2026-07-31 — Step 4 (lámina nueva) + Step 6 (Polish, 2ª corrida)

- Status: complete
- What was decided:
  - Lámina nueva **4.4 «Grabar una Skill»**, última de la Sección 4, a pedido del presentador ("Let's add in the skill section at the end the 'Record a Skill' slide"). Cubre propósito, uso y límites: es el **tercer camino de creación** y el de menor barrera — se hace la tarea narrándola y Claude propone la Skill.
  - Hechos, todos de la doc oficial (support 12512198, verificado 2026-07-31): planes **Pro, Max y Team**, **Cowork en Claude para Mac**; se entra por el menú **"+"** del chat (el mismo de 4.3) o por Configuración → Habilidades → Agregar; captura **pantalla, clicks, tipeo y voz** hasta **~10 min**; el producto avisa de **no tipear contraseñas ni datos sensibles**; Claude abre una tarea de Cowork, revisa la grabación y **propone** la Skill, nueva o como actualización de una existente; la Skill resultante se edita como cualquier otra. El anuncio en X de la cuenta oficial de Claude (21/07/2026) se cita como cobertura, separado de la doc.
  - **La lámina NO afirma nada sobre retención de las grabaciones ni sobre entrenamiento** — la doc no lo cubre. Queda como pregunta abierta en las Speaker notes.
  - Diagrama nuevo `s4-4-1-flujo-grabar-skill`: flujo vertical de 4 pasos bajando a "SKILL ACTIVA", con el paso 4 destacado como **la trampa del Save**, pariente visual de la compuerta del diagrama de 4.2.
  - Polish re-corrido entero: 10 bloques, **1 renderizado** (el nuevo) y **7 reusados por digest**; `s3-3-1` y `s4-2-1` siguen documentation-only. 13 refs, todas `.png`. Strip: 20 campos H3 + 8 de párrafo.
- Key inputs: support.claude.com/en/articles/12512198 (verificado 2026-07-31); anuncio oficial en X del 21/07/2026; el diagrama de 4.2 como referencia visual.
- Files created/modified: `draft.md`, `final.md`, `images/s4-4-1-flujo-grabar-skill.{ascii,svg,png}`, `config/feedback-backlog.md` (1 fila), `memory.md`.
- Pending open questions:
  - **Duración: 61,0 min contra un bloque de 60**, y la lámina de catálogo todavía no entró.
  - **Disponibilidad de "Record a skill" a confirmar contra la app antes de la clase**: despliegue gradual, solo Mac, planes Pro/Max/Team.
  - La crítica visual ciega automática tampoco se pudo lanzar esta corrida; la revisión del diagrama nuevo la hizo el orquestador a mano sobre el PNG y quedó aprobada.
  - Huérfano nuevo en `images/`: `s4-4-1-anatomia-skill-md.*` sigue compartiendo prefijo con el bloque vivo `s4-4-1-flujo-grabar-skill.*`. El `gc` los distingue por digest, pero conviene correrlo.

---

## 2026-07-31 — Step 7 (Render, html-strict)

- Status: complete
- What was decided:
  - Estilo elegido: **`html-strict`** (Reveal.js, sin `.pptx`). Salida: `output/html/index.html`, 2,0 MB autocontenido (Reveal + fuentes + las 13 imágenes inlineadas). Modelo intermedio en `output/slide-model.json`, estampado con el digest de `final.md`.
  - **28 láminas** en el deck: portada + 7 divisorias de sección + las 20 de contenido. `Open questions` y `Cut material` quedaron fuera, como corresponde. Orden 1-5 → Conclusions → 6, respetado.
  - Las 20 láminas llevan sus Speaker notes verbatim en el panel de notas (tecla `s`).
  - **El hint `<!-- layout: image-left -->` SÍ está soportado hoy** por el render html — la nota vieja de `Open questions` que decía que el catálogo no lo soportaba quedó desactualizada. Se aplicó en 1.2 (el pedido original del presentador, por fin cumplido) y también en 2.3.
- Key inputs: `final.md` polished; `config/profile.md` y `config/logo.png` (portada).
- Files created/modified: `output/html/index.html`, `output/slide-model.json`, `memory.md`.
- Pending open questions:
  - **4.2 perdió la captura `skills-panel.png`.** El template de superficie de código no tiene ranura de imagen y la lámina traía captura + fence. Se priorizó el fence. Arreglos posibles: partir 4.2 en dos láminas, o dejar que el ASCII se renderice a imagen y que la captura entre como lámina visual.
  - **3.2 apretada:** las dos capturas (`project.png`, `context.png`) caen en una grilla de 3 columnas y quedan a ~1/3 del ancho, ilegibles en proyección. Candidata a partirse en dos láminas.
  - **1.3** (el mapa) y **1.4** (`cowork.png`): las imágenes quedan chicas para su nivel de detalle; chequear en sala.
  - **4.3** quedó visualmente vacía a la izquierda.
  - El roadmap de las divisorias numera por posición, así que Conclusions sale `06` y la Sección 6 sale `07`. Es cromo del renderer, no del contenido.
  - En la superficie de código la sangría se preservó codificando espacios duros, porque la caja no fija `white-space: pre`. Si el plugin lo agrega, se puede revertir (afecta 2.2, 3.3, 4.2).

---

## 2026-07-31 — Step 4 (lámina 3.3) + Polish + Render, 3ª vuelta

- Status: complete
- What was decided:
  - Lámina nueva **3.3 «¿Los lee todos?»** en la Sección 3, entre "Conceder una carpeta" y las Instrucciones, que pasó a **3.4**. La sección queda en 4 láminas. Contenido del presentador: los tres casos (pocos archivos → lectura completa · muchos archivos → búsqueda de fragmentos, 10x capacidad · trabajar sobre los archivos → abrir, modificar y guardar) más tres reglas prácticas (subir lo que importa, nombres claros, PDFs escaneados sin capa de texto).
  - **Choque de fuentes, resuelto a propósito.** El presentador escribió que con búsqueda "ahora depende de que la búsqueda encuentre lo correcto"; la doc oficial (support 11473015, verificado 2026-07-31) afirma lo contrario: *"Response accuracy remains consistent with in-context processing"*. La **lámina quedó neutral** (describe el mecanismo, no la fiabilidad) y las **Speaker notes llevan las dos posiciones con nombre**. El 10x sí está respaldado por esa misma fuente, igual que el carácter automático del cambio; **no hay umbral numérico documentado** y el deck no inventa uno.
  - "Consume mucho de tu límite de uso" se bajó a "ocupar la ventana de contexto entera en cada vuelta", que es lo defendible.
  - Polish y Render re-corridos. Polish: 10 bloques, **0 renderizados** (ninguno nuevo, la lámina no lleva diagrama), 8 reusados por digest, 2 documentation-only (`s3-4-1` Instrucciones, `s4-2-1`). 13 refs, todas `.png`. Render html-strict: **29 láminas** (portada + 7 divisorias + 21 de contenido), 2,03 MB.
- Key inputs: el comentario del presentador en el `Presenter feedback` de 3.2; support.claude.com/en/articles/11473015 (RAG for projects, verificado 2026-07-31).
- Files created/modified: `draft.md`, `final.md`, `config/feedback-backlog.md` (1 fila), `output/html/index.html`, `output/slide-model.json`, `memory.md`.
- Pending open questions:
  - **Duración: 64,0 min contra un bloque de 60 — 4 min pasado.** El recorte de reserva (Conclusions.1 de 5 a 3) ya no alcanza solo: devuelve a 62,0. Candidatos adicionales anotados: 3.4 Instrucciones de 5 a 4 (la lámina más larga) y 2.4 de 4 a 3. Y la lámina de catálogo de skills todavía no entró.
  - **3.3 quedó la lámina más densa del deck** (auto-ajuste a ~0,64 contra 0,78-0,97 de sus pares). Entra completa y se lee, pero la salida natural si molesta es partirla en dos: los tres modos por un lado, las tres reglas por otro.
  - En el render, los tres emoji de las reglas (📁 🏷️ 📄) se colapsan a un único glifo de nota, porque el ícono de un bloque destacado lo fija su tipo y no se elige por ítem. El encabezado "Tres reglas prácticas" no se imprime: el grupo se lee por la banda acentuada.
  - Sigue abierto lo de 4.2 (pierde la captura) y 3.2 (dos capturas apretadas en grilla de 3 columnas).

---

## 2026-07-31 — Step 4/5 (5ª ronda) + Polish + Render, 4ª vuelta

- Status: complete
- What was decided:
  - **3.1 «Qué es un Project»** ganó una nota al pie: Cowork trabaja la carpeta concedida **con herramientas de archivo** — abre, busca y escribe lo que la tarea necesita, en vez de traer el contenido entero a la conversación. Fuente: Claude docs, *Desktop and filesystem access* (https://claude.com/docs/cowork/3p/local-access, verificado 2026-07-31): *"the agent can then read, create, and modify files anywhere inside those folders"* y *"read, write, and **search** files … with its **file tools**"*. **La doc no dice nada sobre "memoria" ni sobre consumo de contexto**, así que la lámina no lo afirma. Las notes separan explícitamente este caso (carpeta de Cowork, herramientas) del de 3.3 (base de conocimiento, leer todo vs fragmentos).
  - **La lámina de Instrucciones se partió en dos.** `3.4 Instrucciones: el contrato de trabajo` es la de **concepto**, con la captura nueva **`images/instructions.png`** (panel de contexto de un Project, con Instructions rodeado en violeta y debajo Memory, Context y Scheduled). `3.5 Un ejemplo de Instrucciones` se lleva el fence ```text completo, byte por byte, con su hint `ascii-render: documentation-only` **intacto** — sin ese hint el pipeline lo tomaría por diagrama, porque la lámina no lleva imagen. Los 5 min originales se repartieron en ~2 + ~3.
  - **La Sección 3 quedó en 5 láminas:** Qué es un Project · Conceder una carpeta · ¿Los lee todos? · Instrucciones (concepto) · Un ejemplo.
  - Polish: 10 bloques, **0 renderizados** (ninguno nuevo), 8 reusados por digest, 2 documentation-only (`s3-5-1`, `s4-2-1`). 14 refs, todas `.png`. Render html-strict: **30 láminas** (portada + 7 divisorias + 22 de contenido), 2,55 MB.
  - En el render: 3.4 quedó `content-image` (texto izquierda, captura derecha, sin recorte); 3.5 quedó superficie de código, 11 líneas contra un tope de 18, con la sangría preservada; la nota de 3.1 renderizó como banda destacada bajo las tarjetas, no como una tarjeta más.
- Key inputs: los 3 bullets del presentador; claude.com/docs/cowork/3p/local-access; `images/instructions.png` (aportada por el presentador, verificada por el orquestador).
- Files created/modified: `draft.md`, `final.md`, `images/instructions.png`, `config/feedback-backlog.md` (3 filas), `output/html/index.html`, `output/slide-model.json`, `memory.md`.
- Pending open questions:
  - **Duración: 64,0 min contra 60 — 4 min pasado**, sin cambio respecto de la ronda anterior (la partición repartió los minutos, no los sumó). Plan de recorte que cierra en 60: Conclusions.1 de 5 a 3, 3.5 de 3 a 2, y 2.4 de 4 a 3. Y la lámina de catálogo de skills sigue sin entrar.
  - **Idioma mezclado en las capturas:** `instructions.png` muestra la app **en inglés** ("Instructions"), mientras `skills-panel.png` y `skills-menu-chat.png` están en español. O se menciona al pasar, o se resacan (implica rehacer los círculos violeta).
  - **Posible solape** entre `instructions.png` (3.4) y `context.png` (3.2): las dos muestran el panel de contexto. Decidir si una sobra; sacar `context.png` bajaría 3.2 de 2 a 1,5 min.
  - Sigue abierto: 4.2 pierde su captura; 3.2 con dos capturas apretadas; 3.3 es la lámina más densa del deck.
