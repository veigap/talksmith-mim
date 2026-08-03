# Feedback backlog

> Format spec, tagging vocabulary, and pattern-detection rules live in [`${CLAUDE_PLUGIN_ROOT}/schemas/feedback-backlog.md`](${CLAUDE_PLUGIN_ROOT}/schemas/feedback-backlog.md).

## Tagging vocabulary

Reuse existing tags before inventing new ones. In use: slop-pattern, accuracy, split-talk, add-slide, add-visual, audience, audience-address, bad-order, compact, cut, expand, merge-incorporation, move, positioning, redundancy, rename, restructure, rewrite, roadmap, slide-content, sources, split, style, terminology, time-budget, too-dense, too-vague, visual.

## Entries

<!-- Editor appends entries below this line. -->
- talk: claude-cowork-part2
  date: 2026-08-03
  location: Agenda
  feedback: "En cada una de las secciones agrega un slide demo."
  resolution: Se agregaron demos al cierre de Quiz, Conocimiento Persistente, Artifacts y Plugins; Claude Code ya incluía la demo del tracker mínimo.
  tags: [add-slide, slide-content, audience]
- talk: claude-cowork-part2
  date: 2026-08-03
  location: Slide "7. Cómo se administra Memory" (Sección 2)
  feedback: "Cómo se administra Memory mas descripcion si es algo que le digo en el prompt, lo si lo hace automatico, etc."
  resolution: Lámina reescrita como proceso de cuatro pasos: aprendizaje dentro del Project, corrección por prompt, revisión y limpieza, y promoción de reglas estables a Instructions o archivos. Se añadieron dos fuentes oficiales.
  tags: [rewrite, slide-content, sources, clarity]
- talk: claude-cowork-part2
  date: 2026-08-03
  location: Slide "4. Dos tipos de Artifact" (Sección 3)
  feedback: "No veo nigun slide sbore"
  resolution: Nueva lámina «El ciclo de vida de un Artifact» con creación, iteración/versionado, publicación o compartición, apertura y retiro de acceso. Las láminas siguientes separan las restricciones de distribución, los permisos de refresco y las credenciales del visitante.
  tags: [add-slide, slide-content, sources, visual]
- talk: seguridad-governance-ai
  date: 2026-07-06
  location: Slide "2. PII vs. Personal Data"
  feedback: "Expander en la presentacion la definicion de PII."
  resolution: Definición de PII expandida en lámina: sigla desplegada (Personally Identifiable Information) más ejemplos — nombre, DNI/pasaporte, email, teléfono, foto del rostro, legajo — en bullets y en el diagrama.
  tags: [slide-content, too-vague, rewrite]
- talk: seguridad-governance-ai
  date: 2026-07-06
  location: Slide "2. PII vs. Personal Data"
  feedback: "No mencionar (GDPR) en la presetacion es este momento."
  resolution: Quitado el namecheck GDPR del slide (diagrama y prosa): el conjunto exterior pasa a «Personal Data (la categoría legal amplia)» sin nombrar ley; GDPR se nombra recién en la Sección 9 — speaker notes ajustadas para decir que la norma llega después.
  tags: [slide-content, bad-order, rewrite]
- talk: seguridad-governance-ai
  date: 2026-07-06
  location: Slide "2. PII vs. Personal Data"
  feedback: "Es DATOS PERSONALES igual a PI ? Si es asi, dejar todo en ingles por ahora."
  resolution: PII ≠ Personal Data: PII es el subconjunto que identifica directamente (la distinción es el punto del slide y el Mito 4 depende de ella); ambos términos estandarizados en inglés en lámina (PII / Personal Data), prosa en español; diagrama, ascii-note, Mito 4 y goal de la Sección 2 actualizados.
  tags: [slide-content, terminology, rewrite]
- talk: seguridad-governance-ai
  date: 2026-07-06
  location: Slide "4. La arquitectura, en tres saltos"
  feedback: "Lo que me gustaria aca es 2 slides. 1 que muestre una aquitectura cliente servidor desktop o GTP, luego SaaS y meter un LLM."
  resolution: Agregado slide 2.4 «La arquitectura, en tres saltos» con ASCII de 3 paneles (cliente-servidor en tu oficina → SaaS con servidor de otro → SaaS+LLM donde el tercero puede retener/entrenar); la ex Residencia de datos quedó fundida ahí (pregunta de manager conservada) y el perímetro 2.6 ahora se apoya en ese visual.
  tags: [slide-content, add-visual, split]
- talk: seguridad-governance-ai
  date: 2026-07-06
  location: Slide "4. La arquitectura, en tres saltos"
  feedback: "Creo que en un slide introducir algunos coceptors tales como API, encripcion y residencia de datos. Tal vez en el slide introducir los terminor en forma rapida y cuando se muestra el digrama de infrascturra mostrar en el grafico estos pintos."
  resolution: Agregado slide 2.3 glosario rápido (API / cifrado / residencia, una línea cada uno, con la analogía del mesero) y los tres términos anclados como pins (1)(2)(3) en el diagrama de arquitectura del slide siguiente; el cifrado ex-2.4 y la API ex-3.2 quedaron fundidos/cortados a Cut material; la Sección 3 queda en 3 slides (~7 min), financiando el slide de números 1.9.
  tags: [slide-content, merge, reorder]
- talk: seguridad-governance-ai
  date: 2026-07-06
  location: Section "4. MCP y agentes"
  feedback: "El core impact de MCP es que a pesar que el LLM provider este aprobado, la violacion se puede producir por por estos connectores/mcp servers."
  resolution: Slide 4.2 reescrito para que el mensaje core del beat MCP quede explícito en lámina: aun con el proveedor de LLM aprobado (enterprise, con contrato), la violación puede entrar por los conectores/servidores MCP — cada conector es su propia decisión de confianza (qué puede leer, a dónde puede enviar) — atado a mínimo privilegio; goal de la Sección 4 y speaker notes actualizados (anticipa el Mito 6).
  tags: [slide-content, section-goal, rewrite]
- talk: seguridad-governance-ai
  date: 2026-07-06
  location: Slide "4. Mito 3: "On-prem siempre es más seguro""
  feedback: "Que alguna otra pregunta desafiante podria agregarse que sea realativamente desafiante."
  resolution: Agregado Mito 6 «Tenemos ChatGPT Enterprise, así que ya estamos cubiertos» (slide 8.7, ~1 min): el tier enterprise resuelve retención/entrenamiento pero no shadow AI en cuentas personales, ni conectores mal permisionados, ni la verificación de salidas — la herramienta no reemplaza la gobernanza; cierre y transición del rompemitos movidos de Mito 5 a Mito 6; Sección 8 ~9→10 min compensado con Sección 7 ~13→12 (total sigue en 110 min).
  tags: [slide-content, split]
- talk: seguridad-governance-ai
  date: 2026-07-06
  location: Slide "2. GDPR"
  feedback: "Expanding que significa GRPR.,"
  resolution: Sigla desplegada en lámina: GDPR — General Data Protection Regulation (Reglamento General de Protección de Datos, UE, en vigor desde 2018) con una línea de qué es; la extraterritorialidad pasó a su propio bullet; speaker notes ajustadas para leer la sigla en voz alta al abrir.
  tags: [slide-content, terminology, rewrite]
- talk: seguridad-governance-ai
  date: 2026-07-07
  location: Section "4. MCP y agentes"
  feedback: "Agregar un slide explicando poco mas en detalle que es MCP."
  resolution: Agregado slide 3.2 «MCP, un poco más de cerca» (justo después de «MCP: una API que actúa») — define MCP = Model Context Protocol, estándar abierto 2024 para conectar IA con herramientas/datos externos, sin integraciones a medida por combinación; sin registro dedicado en corpus, contenido de conocimiento general con tono de audiencia no técnica.
  tags: [slide-content, add-slide, expand]
- talk: seguridad-governance-ai
  date: 2026-07-07
  location: Slide "6. El perímetro: de on-prem a la IA"
  feedback: "Borrar este slide. No lo voy a usar."
  resolution: Slide eliminado por completo (Content, Sources, Speaker notes, diagrama ASCII de tres columnas de perímetro).
  tags: [slide-content, remove-slide]
- talk: seguridad-governance-ai
  date: 2026-07-07
  location: Slide "2. El camino del dato"
  feedback: "Borremos este slide."
  resolution: Slide eliminado por completo (diagrama ASCII propio del camino del dato incluido). Sección "3. Detrás de escena" quedó con un único slide divisor tras esta y la siguiente eliminación — plegada como cierre de la Sección "2. Fundamentos" en lugar de sostenerse como sección propia de un solo slide.
  tags: [slide-content, remove-slide, restructure]
- talk: seguridad-governance-ai
  date: 2026-07-07
  location: Slide "3. El LLM no corre en tu compu"
  feedback: "Borrar este slide. Ya voy a hablar del mismo."
  resolution: Slide eliminado por completo. Sección "3. Detrás de escena" (ex "El camino del dato" + este slide) quedó sin contenido propio — divisor plegado como cierre de "2. Fundamentos"; goal de esa sección reescrito; MCP pasa a ser la nueva Sección 3.
  tags: [slide-content, remove-slide, restructure, section-goal]
- talk: seguridad-governance-ai
  date: 2026-07-07
  location: Section "6. Shadow AI"
  feedback: "borrar (sección completa + sus 3 slides hijas: Shadow AI: el riesgo invisible / Consumo vs. enterprise / La jugada del manager)"
  resolution: Sección "6. Shadow AI" eliminada por completo (header + goal + 3 slides). Secciones subsiguientes renumeradas (7→5, 8→6, 9→7, 10→8, 11→9). Callback colgante del dato LayerX en las speaker notes de la Sección "Impacto y responsables" (prometía desarrollo posterior en "Shadow AI") ajustado para no apuntar a una sección inexistente. Contenido de consumo-vs-enterprise no se perdió: equivalente ya cubierto en Mito 1 (rompemitos) y en la mini-checklist del comprador. Tiempo total de la charla ajustado (-8 min aprox.).
  tags: [slide-content, remove-section, restructure, section-goal]
- talk: seguridad-governance-ai
  date: 2026-07-07
  location: Slide "3. Mito 2: "Grande = seguro y compliant""
  feedback: "borrar en este slide y todos los slide Soc2. No voy a hablar de esto."
  resolution: Slide Mito 2 conservado (el mito es general, no depende de SOC 2); única mención de SOC 2 quitada de sus speaker notes. Pedido más amplio aplicado en conjunto: slide "SOC 2: la auditoría del proveedor" eliminado por completo; fila SOC 2 quitada de la tabla del divisor "El mapa de estándares"; checklist del comprador reducida de 5 a 4 preguntas (sin la pregunta de SOC 2 Type II); grep de "SOC" corrido sobre todo el draft para confirmar 0 referencias colgantes.
  tags: [slide-content, remove-topic, rewrite]
- talk: seguridad-governance-ai
  date: 2026-07-07
  location: Slide "1. 〔divisor〕 El mapa de estándares"
  feedback: "Borrar Soc y agregar la ley argentina."
  resolution: Fila SOC 2 quitada de la tabla comparativa de estándares; fila "Ley 25.326 (Argentina)" agregada en su lugar, con nota de que se profundiza en la sección "¿Y en Argentina?" (fuente corpus/argentina-datos-explicado.md.md).
  tags: [slide-content, rewrite, add-content]
- talk: seguridad-governance-ai
  date: 2026-07-07
  location: Slide "2. GDPR"
  feedback: "agregar un slide que sea mas claro sobre a quien aplica GDPR."
  resolution: Agregado slide 7.3 «¿A quién aplica GDPR?» justo después de este slide (antes del callback de Samsung) — desarrolla el criterio de aplicabilidad (ubicación del titular del dato, no de la empresa) con tres ejemplos concretos, fundamentado en corpus/gdpr-explicado.md.md.
  tags: [slide-content, add-slide, expand]
- talk: seguridad-governance-ai
  date: 2026-07-07
  location: Section "10. ¿Y en Argentina?"
  feedback: "Agregar un slide que cubra los gaps actuales de la ley considerando los años."
  resolution: Agregado slide 8.3 «Los gaps de la 25.326, 26 años después» al cierre de la sección — gaps frente a GDPR/regulación de IA moderna (accountability, privacy by design, portabilidad, oposición a decisiones automatizadas) y estado del proyecto de reforma, fundamentado en corpus/argentina-datos-explicado.md.md.
  tags: [slide-content, add-slide, expand]
- talk: seguridad-governance-ai
  date: 2026-07-07
  location: Slide "2. Inyección de prompts"
  feedback: "Agregar un slide que introdusca cual y define que es prompt injection."
  resolution: Agregado slide 9.2 «Qué es la inyección de prompts» justo antes de este slide — define el término en lenguaje de manager y la razón estructural (la IA no distingue instrucción de contenido).
  tags: [slide-content, add-slide, expand]
- talk: seguridad-governance-ai
  date: 2026-07-07
  location: Slide "2. Inyección de prompts"
  feedback: "Agregar un slide con un ejemplo."
  resolution: Agregado slide 9.4 «Un ejemplo concreto» después del slide de directa/indirecta — ejemplo ilustrativo de inyección indirecta vía documento con instrucción oculta, marcado explícitamente como ilustrativo (no sourced a un incidente real documentado en el corpus).
  tags: [slide-content, add-slide, illustrative-example]
- talk: seguridad-governance-ai
  date: 2026-07-07
  location: Slide "3. Tres términos, en 60 segundos"
  feedback: "Tres términos, en 30 segundos ni hacerlo tan infantil como la analogia. Explicar un poco mas."
  resolution: Saqué la analogía del mesero de este slide (queda reservada para el slide "1. MCP: una API que actúa", donde gana peso real: "ya no solo trae el plato — tiene la llave de tu oficina"). En su lugar, cada término suma una oración de "por qué importa" con sustancia de negocio tomada del corpus (las tres preguntas de Riesgo de terceros para API; el matiz cifrado-no-implica-no-entrenamiento para Cifrado; el link a transferencia internacional/GDPR para Residencia). Retitulé el slide a "en 60 segundos" y ajusté el timing en speaker notes (de ~30 a ~60 seg/término) para reflejar el contenido nuevo sin volverlo una clase técnica.
  tags: [slide-content, rewrite, add-content]
- talk: hiperparametros-ai
  date: 2026-07-07
  location: Section "5. Marco de decisión"
  feedback: "Borra todo el 5. Marco de decisión"
  resolution: Sección 5 completa (slides 5.1 "De la tarea a la perilla" con su árbol ASCII y 5.2 "Qué preguntarle a un proveedor" con la checklist) removida del deck activo y movida verbatim a # Cut material (content, sources, speaker notes, diagramas). El deck cierra ahora con Conclusions directamente tras la Sección 4. Referencias reconciliadas: quitada del Agenda (arco narrativo reescrito para cerrar en la Sección 4 con la idea rectora; lista de secciones de 5→4); Open questions actualizado (entregable pasa a ser la tabla de bolsillo 3.4, sin la checklist); dos refs colgantes a "Slide 5.2" en Cut material corregidas (seed/reproducibilidad y Tablas 1–4); Conclusions verificadas — cierran sin marco/checklist manteniendo intacto el framing "tres que tocás + dos que comprás". Slide 3.3 sin forward-reference al árbol 5.1 (ya ablandada en round previo).
  tags: [slide-content, remove-section, restructure]
- talk: hiperparametros-ai
  date: 2026-07-07
  location: Slide "3. Razonamiento: Thinking / Deep Thinking"
  feedback: "Encuadrar el slide de razonamiento (3.3) explícitamente alrededor de los dos modos user-facing 'Thinking' vs 'Deep Thinking' como los rotulan las herramientas, con un baseline 'sin pensar / respuesta directa' como default rápido, mostrando la progresión respuesta directa → Thinking → Deep Thinking; conservar trade-off calidad↔latencia↔costo, guía práctica, fuente al corpus y speaker notes; actualizar el ASCII y su ascii-note; no presentar defaults por versión no verificados como hecho; reflejar la fila de razonamiento en la tabla de bolsillo 3.4."
  resolution: Slide 3.3 retitulado "Razonamiento: Thinking / Deep Thinking"; Content reescrito como progresión de tres escalones (respuesta directa → Thinking → Deep Thinking), product labels en inglés + prosa de negocio en español; trade-off explícito "calidad, latencia y costo suben juntos"; guía "emparejá el modo con la dificultad"; ASCII y ascii-note actualizados a la progresión de tres pasos con ejes calidad/latencia/costo; Sources/speaker notes adaptados manteniendo la cita al corpus (sección "Razonamiento") y hablando en términos generales sin defaults por versión; fila de razonamiento en la tabla de bolsillo 3.4 actualizada al framing Thinking / Deep Thinking.
  tags: [slide-content, terminology, rewrite]
- talk: hiperparametros-ai
  date: 2026-07-07
  location: Agenda
  feedback: "También la selección del modelo como un item top level de la agenda."
  resolution: Nueva Sección 4 top-level 'Selección del modelo' (Slide 4.1 'Elegir el modelo: la perilla que todos tocan'): perilla más consecuente y única siempre expuesta en chat web (Tabla 1 del corpus); eje capacidad vs costo/velocidad entre niveles grande/flagship vs mini/rápido; regla 'el más chico/rápido que resuelva bien la tarea'; ASCII capacidad-vs-costo con ascii-note. Reconciliado el ex-Slide 4.2 'Tamaño del modelo' (ahora Sección 5, Slide 5.2 'Tamaño del modelo: qué es grande por dentro'): se quitó el ángulo de selección/capacidad-vs-costo (movido a Sección 4) y quedó solo el marco conceptual de qué son los parámetros por dentro. Agenda (arco+lista, ahora 5 secciones), Conclusions (framing reordenado a modelo→3 perillas→2 comprados) y Open questions renumerados/reconciliados.
  tags: [slide-content, add-section, restructure]
- talk: hiperparametros-ai
  date: 2026-07-07
  location: Agenda
  feedback: "Dividir la Sección 3 'Perillas que SÍ tocás' en dos secciones top-level: una sobre el control de aleatoriedad/variedad (temperatura, top-p) y otra sobre el control del razonamiento (Thinking / Deep Thinking), con el slide 'Resumen: qué perilla para qué' como cierre del segundo bloque. Retitular audience-friendly y paralelo; agregar goal por sección; renumerar todo secuencialmente y reconciliar Agenda, Conclusions, Open questions y cross-refs."
  resolution: Ex-Sección 3 "Perillas que SÍ tocás" (4 slides) partida en dos secciones top-level — Sección 3 "Cómo elige las palabras" (Slide 3.1 Temperatura, 3.2 Top-p) y Sección 4 "Cuánto piensa" (Slide 4.1 Razonamiento: Thinking / Deep Thinking, 4.2 Resumen: qué perilla para qué, que cierra el bloque como recap conjunto de las tres perillas). Goals nuevos por sección, paralelos en estilo. Renumeración en cascada: ex-Sección 4 "Selección del modelo" → 5; ex-Sección 5 "Lo que se decide al construir" → 6. Reconciliados Agenda (arco+lista 5→6 secciones), cross-refs de goals y speaker notes (Secciones 3/4/5 → 3-4/5/6), Open questions (refs de sección y entregable = tabla de bolsillo ahora Slide 4.2), Cut material (nota histórica del ex-Marco de decisión) y Conclusions (framing de contenido intacto). Contenido de slides preservado verbatim — regrupación, no reescritura.
  tags: [slide-content, split, restructure]
- talk: claude-cowork
  date: 2026-07-08
  location: Whole draft (Agenda + all Sections)
  origin: presenter-chat
  feedback: "Reestructura mayor: aprovechar que los alumnos ya usan IAs en modo chat para introducir extensiones ANTES de Cowork. Nuevo arco: (1) el chat y sus limites (responde de memoria de entrenamiento); (2) Conectores como concepto transversal — chat solo vs con conectores, busqueda web como primer conector, directorio oficial + no oficiales + mencion de custom, ejemplos mail/calendar, capacidad ejecutiva (mandar mails, tickets, mensajes, agendar); (3) tareas programadas desde el chat (ej. resumidor de mails); (4) Cowork — mas que 'Claude en tu computadora', cambia por completo la forma de trabajar — con intro/Instrucciones/Projects/Live Artifacts adentro (A1, B1), slide corta de Schedule (C2), y archivos .md expandido (que es, como se lee, trabajar en .md y exportar al final); (5) Skills se muda al final junto a Subagentes y Plugins."
  resolution: Draft reestructurado de 6+Conclusions a 5+Conclusions secciones con el arco chat-primero. 6 slides nuevas (1.1 limites del chat; 2.1 chat solo vs conectores; 2.2 busqueda web / memoria vs info viva; 2.5 conectores que actuan; 3.1 tareas programadas desde el chat; 4.10 trabaja en .md exporta al final). Intro trio + Instrucciones + Projects + selector + .md + Schedule corto + Live Artifacts consolidados en la seccion 4 (Cowork); Skills/anatomia SKILL.md movidas a la seccion 5 con Subagentes y Plugins. Roadmap 2.2 reescrito al arco nuevo como 4.4 con marcadores (visto)/estamos-aca. Thesis y Agenda reescritas. Todo renumerado; recortes documentados en Cut material; claims nuevos con fuentes oficiales citadas y verificacion online pendiente registrada en Open questions (outage de herramientas web).
  tags: [restructure, add-slide, add-visual, slide-content, sources, roadmap]
- talk: claude-cowork
  date: 2026-07-09
  location: Slide "1. Tareas programadas desde el chat" (seccion 3)
  origin: presenter-chat
  feedback: "hay tareas programadas en claude.ai en el navegador, lo estoy usando ahora"
  resolution: Slide 3.1 reescrita con Claude como ejemplo de primera clase junto a ChatGPT; tareas programadas en claude.ai desde el navegador, corren en la nube (sin compu prendida), beta con rollout desde julio 2026 empezando por Max. Removido el hedge que remitia "la forma Claude" a Cowork. Atribucion triple per L002: observacion firsthand del presentador + release notes oficiales (12138966, verificadas 2026-07-09) + TechCrunch 2026-07-07 (encuadre de terceros). Slug de ChatGPT tasks corregido al canonico 10291617-tasks-in-chatgpt.
  tags: [accuracy, sources, slide-content]
- talk: claude-cowork
  date: 2026-07-09
  location: Slide "11. Schedule en Cowork" (seccion 4)
  origin: presenter-chat
  feedback: "El hecho round-3 'Schedule corre LOCAL (compu despierta + app abierta), NO en la nube' quedo desactualizado: desde 2026-07-07 las tareas programadas corren remoto/en la nube, sin dispositivo online (beta, Max primero)."
  resolution: ACCURACY FIX en 4.11: Content reescrito ("Corren en la nube desde julio 2026"; laptop apagada SI genera el reporte; planes pagos; beta rollout Max-first; nota de que la limitacion vieja ya no aplica); Speaker notes y Sources actualizadas (13854387 re-fetcheada 2026-07-09: "Scheduled tasks run remotely... even when your computer is asleep or the Claude Desktop app is closed"; + release notes 12138966 + TechCrunch; caveats del corpus marcadas desactualizadas). Grep por otros claims "corre local": solo quedan el [closed] historico (audit trail, intacto) y la locality de Live Artifacts en 4.12, claim distinto RE-VERIFICADO vigente contra 14729249 el 2026-07-09 (vigilancia anotada en Open questions).
  tags: [accuracy, sources, slide-content]
- talk: claude-cowork
  date: 2026-07-09
  location: Slide "5. Los conectores tambien actuan" (seccion 2)
  origin: presenter-chat
  feedback: "ya esta chequeado lo del calendario"
  resolution: Accion de Calendar (agendar/crear eventos) marcada como verificada de primera mano por el presentador (2026-07-09) en Sources y Speaker notes de 2.5; sumadas dos fuentes oficiales verificadas que respaldan la capacidad ejecutiva general (11175166 "access and take action in these services"; modelcontextprotocol.io "take actions on your behalf"). Hedge conservado SOLO para tickets y mensajes (sin verificacion por conector). Open question actualizada al estado por-accion.
  tags: [accuracy, sources]
- talk: claude-cowork
  date: 2026-07-09
  location: Open questions (URLs round 4)
  origin: presenter-chat
  feedback: "Re-verificar las 6 URLs pendientes de round 4 ahora que volvio el acceso web; si alguna 404ea o contradice la slide, corregir y reemplazar la fuente."
  resolution: Las 6 verificadas el 2026-07-09: 4 OK sin cambios (web search 10684626; custom connectors 11175166; modelcontextprotocol.io; ChatGPT search 9237897 — corroborado via busqueda por 403 anti-bot del fetch directo); 2 corregidas/reemplazadas (claude.com/directory -> claude.com/blog/connectors-directory + support 11176164, por login-gate; slug de ChatGPT tasks -> 10291617-tasks-in-chatgpt). Citas de slides 2.1/2.2/2.4 actualizadas con quotes y fecha de verificacion; entradas de Open questions marcadas resueltas en draft y memory.
  tags: [sources, accuracy]
- talk: claude-cowork
  date: 2026-07-09
  location: Whole draft (Content fields, todas las secciones)
  origin: presenter-chat
  feedback: "Mucho texto, raro que quedo tan verborragico."
  resolution: Pasada de compactacion deck-wide sobre los campos Content: bullets cortos (una linea, una idea), sin sub-parrafos ni meta-comentario; 21 slides compactadas (las 6 nuevas de round 4 + 3.1 + 4.1-4.12 + 5.1-5.5 + Conclusions.1). El detalle bajo a Speaker notes (crecieron en 1.1, 2.1, 2.2, 2.3, 2.4, 3.1, 4.1, 4.3, 4.7, 4.9, 4.10, 4.12, 5.1, 5.4, Conclusions.1); nada borrado en silencio. Sin cambios en Sources, ascii, ascii-notes ni audit trail [closed]. Mismo estandar que el precedente 'compact' de round 3 en El superpoder.
  tags: [compact, too-dense, slide-content]
- talk: claude-cowork
  date: 2026-07-09
  location: Slide "1. Tareas programadas desde el chat" + nueva "2. ¿Donde corre tu tarea?" (seccion 3) y "11. Schedule en Cowork" (seccion 4)
  origin: presenter-chat
  feedback: "La parte de schedule hay que expandir. Sobre todo con temas como tengan en cuenta que la computadora este prendida etc."
  resolution: Expandido en slide NUEVA 3.2 '¿Donde corre tu tarea? Local vs nube' (para mantener 3.1 compacta): ambas realidades — nube beta desde jul-2026 (rollout gradual, Max primero) Y modo local mientras no llegue (compu prendida + app abierta; apagada/suspendida => se saltea y corre al volver; ojo notebooks que se suspenden); excepcion documentada: tareas con archivos/apps locales corren local SIEMPRE. ASCII nuevo de bifurcacion '¿donde corre?' con ascii-note. Moraleja: 'antes de confiarle algo, sabe DONDE corre'. 4.11 sincronizada con el mismo marco (cross-ref 3.2 + matiz Cowork: usa archivos locales => corre local => planifica con la compu prendida) y con la quote de la excepcion sumada a Sources. Comportamiento 'se saltea y corre al volver' atribuido a la version anterior del articulo 13854387 (la actual ya no lo detalla) segun L002. Caveat de aprobacion/review de acciones NO agregada: los docs verificados no la documentan.
  tags: [slide-content, accuracy, sources, expand, add-slide, add-visual]
- talk: claude-cowork
  date: 2026-07-09
  location: Whole draft (prosa presenter-facing: Thesis, Agenda, goals, Content, Speaker notes)
  origin: presenter-chat
  feedback: "STYLE PASS deck-wide aplicando el skill desrobotizar del presentador (quitar marcas de escritura de IA en la prosa en espanol)."
  resolution: Aplicadas las reglas nucleo + quick checks + reglas-propias del skill sobre Thesis, Agenda, 5 goals de seccion y los Content/Speaker notes de las 27 slides. ~140 em-dashes reemplazados en prosa (comas, puntos, parentesis); eliminados adverbios en -mente, contrastes binarios "no es X sino Y", meta-comentario ("mencion, sin profundizar", "proxima slide: ..."), formulas de revelacion ("ahi esta la magia"), capsulas ("un toggle y listo"), arcos "de X a Y" ("de preguntar cada vez a suscribirte"), muletillas ("Ojo:", "Y ojo:"), pasiva refleja ("las carpetas se conceden" -> "vos concedes"), hendidas y colones compulsivos. Titulo de seccion 1 restylado ("El chat que ya usas y sus limites"). Sin cambios de sustancia: claims verificados, atribuciones L002, numeros, nombres de producto y mensajes verbatim del presentador intactos; compactacion round 6 preservada (ningun Content crecio). NO tocados: ascii + ascii-notes, ejemplo ```text, image refs (2 em-dashes quedan en alt text), Sources, audit trail [closed], Open questions, Cut material, frontmatter. Self-score prosa del deck: 28/50 antes -> 43/50 despues; ninguna slide <35.
  tags: [style, rewrite, slide-content]
- talk: claude-cowork
  date: 2026-07-15
  location: Whole draft (Thesis, Agenda, goals, titulos, Content, celdas de tabla; notes exentas)
  origin: presenter-chat
  feedback: "hablarle asi a la audiencia es muy slop, el que habla con la audiencia soy yo y no la presentacion. nunca hacerlo si no se pide explicitamente. [Ajuste mid-round: esta mal hablar en segunda persona compulsivamente y sin considerar el contexto — registro por defecto impersonal/tercera persona; segunda persona solo como beat deliberado.]"
  resolution: Cambiado el registro por defecto de toda la prosa de presentacion a impersonal/tercera persona per la regla nueva de reglas-propias.md: Thesis reescrita ("La charla parte del chat de uso diario..."), Agenda, goals de secciones 1 y 4, 4 titulos ("El chat como viene y sus limites"; "sin repetir contexto"; "Trabajar en .md, exportar al final"; "lo mismo del chat"; "¿Donde corre la tarea?"), ~20 bullets de Content ("vos concedes" -> "el usuario concede", "sabe donde corre" -> "saber donde corre", "te avisa" -> "avisa", "tus archivos" -> "archivos/los archivos", imperativos -> infinitivos), celdas de la tabla 4.3 ("Los haces vos" -> "Los hace la persona") y 6 retoques triviales de ascii (misma longitud). SURVIVORS deliberados enumerados y justificados: catchphrase del presentador "Claude instalado en tu compu(tadora)" (cita verbatim, 3 lugares), framing oficial "Claude Code para el resto de tu trabajo" (cita de Anthropic), frase-ancla "Dejas de tipear..." (punchline citada que el orador dice en voz alta), maxima "Todo lo que le explicas a Claude dos veces..." (tagline del corpus, 2 lugares), gancho de cierre "¿Que tarea le delegarias a tu propio Atlas?" (unico beat de interpelacion directa, al cierre), prompts-de-usuario citados ("resumi mi inbox", "¿que mails me perdi ayer?"), voz de usuario en primera persona del roadmap ("quiero info real"). FLAG no tocado: ascii de 4.3 (etiquetas de actor "vos:" requieren redisenio, no trivial). Speaker notes exentas per regla. Cross-refs actualizadas (bullet de Agenda de la seccion 1).
  tags: [style, audience-address, rewrite]
- talk: claude-cowork
  date: 2026-07-15
  location: Whole draft (prosa fuera de zonas exentas)
  origin: presenter-chat
  feedback: "Em-dash purge for real: round 7 reporto 0 pero el grep del orquestador encontro ~27 en prosa."
  resolution: [Ampliado en round 8b a scope DOCUMENTO COMPLETO por pedido del presentador: las exenciones de Sources y audit trail eran incorrectas para la redaccion propia.] Purga total de draft.md: 164 em-dashes antes -> 27 despues (137 reemplazados, solo puntuacion, sin cambiar palabras: coma para separador editorial-titulo en Sources, punto y coma para glosas, ". Fuente:" en Cut material). Residuo final, cada uno justificado: 20 separadores del formato stampeado "- [closed] FECHA — " (formato MAQUINA del skill feedback-cycle: las regexes OPEN_BULLET/CLOSED_BULLET de feedback_cycle.py exigen ese em-dash literal; cambiarlo rompe find-closed-unmirrored/rescue-open) + 7 dentro de citas verbatim (2 en texto verbatim del presentador en bullets [closed]; 5 en citas textuales del corpus como "Claude Code vs Cowork — the close" y "Description drives triggering — semantic, not keyword"). 0 em-dashes fuera de esas dos clases, verificado con clasificador linea por linea. En round 8 previo: 2 alt-texts corregidos y 0 en prosa de presentacion.
  tags: [style, rewrite]
- talk: claude-cowork
  date: 2026-07-15
  location: Slides 2.4, 4.12/4.13 (nueva), 5.1 + Open questions
  origin: presenter-chat
  feedback: "Paulo pusheo su reestructura a origin/main sin rounds 8/8b. Decision del presentador: KEEP OURS (estructura 5 secciones + Conclusions, registro rounds 8/8b); incorporar de la version de Paulo solo el contenido genuinamente nuevo, reescrito en nuestro registro."
  resolution: Incorporados 3 beats de origin/main (b6227a3..1f60102), reescritos per desrobotizar (impersonal, sin tuteo, sin em-dashes, registro compacto): (1) "El tablero de Atlas" como slide NUEVA 4.13 cerrando la seccion 4 (Live Artifact semanal pulso-semanal-FECHA con historial; boceto del jefe como spec, image ref movida desde 4.12 sin duplicar; cierre de mision "mail y tablero, las dos entregas ya estan"); 4.12 adelgazada y sus notes pierden el ejemplo Atlas con puente a 4.13. (2) Seguridad de conectores en 2.4: bullet nuevo "Un conector no oficial, al autorizarse, accede a los datos del usuario. Conectar solo fuentes confiables." + quote oficial de 11175166 sumada a la fuente (ya verificada 2026-07-09); las notes ya cargaban el criterio. (3) Diagrama ASCII de creacion de Skill adaptado a 5.1 (labels impersonales "pedirla"/"subir"; compuerta SAVE/ENABLE como la trampa; render-driving, 5.1 no tiene image ref) + requisito Code execution ya presente, sin duplicar. HALLAZGO L002: support 12512198 (re-verificado 2026-07-15) ya NO documenta el camino lenguaje-natural (solo ZIP) -> fuente de 5.1 reescrita con atribucion honesta (version junio 2026 + verificacion firsthand del presentador) y nueva entrada de vigilancia en Open questions; 12512180 re-verificado OK (Code execution). NO adoptado de Paulo: estructura de 7 secciones, sus splits (2.4/2.5, interfaz/demo, superpoder/habilidad-base), sus titulos con tuteo ("Busca, conecta, autoriza", "Trabaja en .md"), su renumeracion y su redaccion (decision keep-ours del presentador).
  tags: [slide-content, add-slide, add-visual, sources, merge-incorporation]

  location: Frontmatter + Slide "2. El superpoder de Cowork" (seccion 4) + Slide "2. Gobernanza y advertencias" (seccion 6)
  origin: presenter-chat
  feedback: "El frontmatter esta mal. Esta charla es para la audiencia del MiM, no para biomedicina. El encuadre biomedico es un leftover de otra materia."
  resolution: Frontmatter corregido al subject del MiM segun config/profile.md (presentation = "Inteligencia Artificial - de lo conceptual a lo practico — Master in Management (MiM), IAE Business School, Universidad Austral"; presenter = "Paulo Veiga, Profesor, IAE Business School"; audience = profesionales del dominio de negocios, no ingenieros, estudiantes del MiM, sin formacion tecnica en AI; duration = 2 horas). class, date, research y description se mantienen (per-Talk). Los dos closers biomedicos reframeados al mundo de la gestion: 4.2 "Bioingenieria: la habilidad base se redefine ahora" -> "Gestion: ..."; 6.2 "Contexto biomedico / datos de pacientes / datos clinicos sensibles" -> "Dato regulado / informacion de clientes o datos financieros". Speaker notes de 4.2 ("son ingenieros biomedicos, pocos programan") y de 6.2 ("Para esta audiencia de bioingenieria... datos de pacientes") reframeadas al mismo mundo (clientes, informacion financiera, regulado o bajo NDA). Grep deck-wide de biomed/bioingenier/paciente/clinic/ingenier: sin leftovers presenter-facing. Audit trail [closed] (Resolution de round 3 en 4.2, con "bioingenieria" en el texto) intacto por ser append-only. Sin cambios en ascii, ascii-notes, Sources, titulos ni densidad; registro y compactacion de rounds 6-7 preservados.
  tags: [accuracy, audience, slide-content]
- talk: claude-cowork
  date: 2026-07-15
  location: Frontmatter + Sections 1-2 (H1s, Agenda) + Slides 1.1, 2.1, 2.2, 2.4, 2.5
  origin: presenter-chat
  feedback: "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides. Uno de los feedbacks mas importantes del draft."
  resolution: Pasada de densidad sobre las secciones 1-2 con la regla que encontro el Composer: los bullets transcribian el ASCII de la misma lamina (redundancia de Mayer) — si una linea de Content ya esta en el bloque ASCII o nombrada en el `emphasize` de su ascii-note, baja a Speaker notes. Rounds 6 y 7 compactaron DENTRO de cada bullet; ninguno pregunto si el bullet debia existir. Titulos de seccion: "El chat que ya usas y sus limites" (33c) -> "El chat y sus limites" (21c); "Conectores: extender el chat" (28c) -> "Extender el chat" (15c); agenda sincronizada. COMPACTAR 1.1 (bullet de narracion + enumeracion "mails, calendario, archivos, apps" a notes), 2.1 (bullet "Chat solo -> ... Chat con conectores -> ..." era el diagrama en prosa), 2.2 (bloque "La distincion de la charla" + 2 sub-bullets = las dos columnas del ASCII). 2.3 (Conectores y MCP) evaluada y DEJADA: conforma. SPLIT de 2.4 "El directorio de conectores: mail, calendario y compania" (56c, dos ideas) en 2.4 "Busca, conecta, autoriza" (24c; mecanismo de registro + origen de los conectores + las dos capturas connectors_directory.png y connector_browser.png) y 2.5 "Mail y calendario, los ejemplos" (31c; preguntas guia, MT Newswires para Atlas, y el criterio de confianza promovido de notes al body); Sources y las 149w de notes repartidas, ~3 min cada mitad. COMPACTAR 2.6 (ex 2.5): titulo "Los conectores tambien actuan: del leer al hacer" (48c) -> "Los conectores tambien actuan" (29c, cae el arco "del leer al hacer"); 4 ejemplos -> 2 (mail y calendario, los unicos verificados firsthand 2026-07-09); tickets/Slack a notes CON el hedge de capacidad-del-ecosistema intacto (L002: la compactacion no convierte un claim hedgeado en uno plano); bullet de transicion "puede trabajar solo (seccion 3)" a notes. Todas las notes tocadas quedaron bajo ~120 palabras. Seccion 2 renumerada contigua 1..6; ref colgante "slide 2.5" en Open questions -> 2.6. Frontmatter: `presentation` restaurado al Subject verbatim de config/profile.md (dos puntos, no guion) y entre comillas para que parsee como YAML — verificado con yaml.safe_load. Sin tocar: ASCII, ascii-notes, image refs, claims verificados, atribuciones, audit trail [closed] previo, final.md.
  tags: [compact, too-dense, split, slide-content, redundancy]
- talk: claude-cowork
  date: 2026-07-15
  location: Section 3 (H1 + Agenda) + Slides 3.1, 3.2
  origin: presenter-chat
  feedback: "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides. Uno de los feedbacks mas importantes del draft."
  resolution: Pasada de densidad sobre la seccion 3, misma regla que las secciones 1-2: si una linea de Content ya esta en el bloque ASCII o nombrada en el `emphasize` de su ascii-note, baja a Speaker notes. Titulo de seccion "Tareas programadas: el chat trabaja solo" (40c) -> "El chat trabaja solo" (20c); el titulo compuesto colapsa a la clausula derecha y el concepto "tareas programadas" lo sigue cargando el goal de la seccion; agenda sincronizada. COMPACTAR 3.1 (5 bullets -> 3): quitados "Tarea programada = UNA vez + cadencia -> corre sola y te avisa" (el ASCII lo titula y lo dibuja) y "usa tus conectores (mail, web, calendario)" (la caja del medio del diagrama); ambos ya vivian en notes, fue merge; quedan te-suscribis, el ejemplo de las 8:00 y donde existe (ChatGPT/Claude); notes 155w -> 117w. COMPACTAR 3.2 (PARTIR descartado por el Composer: una sola bifurcacion con guion largo, no dos ideas) — el caso mas puro del defecto: las 6 lineas de Content eran el diagrama LOCAL/NUBE transcripto; quedan 2 bullets, la pregunta previa ("sabe donde corre") y la excepcion que sobrevive al rollout de nube ("si la tarea necesita archivos o apps locales, corre local siempre", quote verificada de 13854387 re-fetcheado 2026-07-09, remate de la lamina); nube beta/Max, app abierta, "se saltea y corre al volver" y las notebooks ya estaban en ASCII + emphasize + notes, sin duplicar. Notes de 3.2 212w -> 171w, sobre las ~120 A PROPOSITO: L002 outranks la guia de palabras — intactos la fecha 2026-07-07, el hedge beta + rollout Max-first, la quote verificada de la excepcion local, y la atribucion completa de "se saltea y corre al volver" a la version anterior del articulo. Piso honesto ~145w (nucleo de claims + hedges); lo recortado fue andamiaje de guion. Cross-refs verificados: 4.11 -> "slide 3.2" (Content + notes) y 3.1 -> "proxima slide" siguen resolviendo, la numeracion 3.1/3.2 no cambio. Sin tocar: ASCII, ascii-notes, image refs, Sources, audit trail [closed] previo, final.md.
  tags: [compact, too-dense, slide-content, redundancy]
- talk: claude-cowork
  date: 2026-07-15
  location: Section 4 (H1 + goal + Agenda) + Slides 4.1-4.5 + nueva Section 5 (header) + renumeracion ex-Section 5 -> 7
  origin: presenter-chat
  feedback: "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides. Uno de los feedbacks mas importantes del draft."
  resolution: Pasada de densidad sobre la seccion 4, misma regla que las secciones 1-3: si una linea de Content ya esta en el bloque ASCII o nombrada en el `emphasize` de su ascii-note, baja a Speaker notes. La seccion tenia 12 slides (techo ~8) y con los splits llegaba a 16, asi que se parte en tres; este dispatch hace la primera ("4. Que cambia con Cowork", 5 slides) y abre la segunda. Titulo de seccion "Cowork: cambiar la forma de trabajar" (36c) -> "Que cambia con Cowork" (21c) con goal reescrito al scope angosto (por que es otra categoria de herramienta + que cambia en tu rol; cierra con el mapa). COMPACTAR 4.1 (5 bullets -> 3, quedan las tres superficies): fuera el bullet de transicion hablada y el de "mismos modelos + Agent SDK" (es la base del ASCII y su emphasize); la precision verificada del [closed] 2026-06-08 baja COMPLETA a notes con sus 4 fuentes intactas (L002); 139w -> 125w. PARTIR 4.2 (81c, el peor titulo del deck) en "El superpoder de Cowork" (23c; el claim, sin diagrama, hereda el [closed] 2026-06-09 que pidio compactarla porque hereda el titulo; ancla verbatim del presentador "Cowork NO es Claude instalado en tu compu" conservada, la negacion ES el mensaje) y "La nueva habilidad base" (23c; la analogia; el ASCII Excel->herramientas agenticas y su ascii-note se mudan enteros aca, sin editar, porque son literalmente su contenido). La atribucion de la analogia a analistas e industria (NUNCA a Anthropic) se queda en el body de la mitad B y no baja al ascii-note: es load-bearing (L002) y un ascii-note es pista de render, no texto garantizado. 243w -> 122w + 124w. COMPACTAR 4.3 -> "El cambio de paradigma" (40c -> 22c, cae el arco "de X a Y" que round 7 saco de la prosa pero no de los titulos): estaba sobre el techo de densidad (3 bullets + tabla + ASCII); la tabla Chatear-vs-Delegar y el ASCII ANTES/AHORA son el mismo contraste y el ASCII es la version pobre -> el ASCII entero + su ascii-note a Cut material con motivo de una linea; 150w -> 119w. COMPACTAR 4.4 -> "Bloques que se apilan" (43c -> 21c): fuera los 9 sub-bullets bloque<->problema, verificados uno por uno contra el ASCII de 30 lineas que los dibuja (los 9 estan; Instrucciones y Projects comparten caja) — merge, no borrado; quedan 3 bullets; sus tres [closed] intactos y su sustancia preservada en notes (piramide, promesa de roadmap, Plugins transversal); 181w -> 140w, sobre las ~120 a proposito porque comprimir mas aplastaria uno de los tres beats protegidos. Abierta la seccion "5. Tu espacio en Cowork" (20c) con goal, feedback vacio y boundary; ex-4.5..4.12 re-homeadas ahi y renumeradas contiguas 1..8 con su CONTENIDO INTACTO (dispatches posteriores hacen su contenido y la vuelven a partir). Ex-seccion 5 "Advanced" renumerada a 7 para no duplicar numero; seccion 6 la inserta un dispatch posterior. Cross-refs: corregidos los del scope (Plugins seccion 5 -> 7 en Content y notes de 4.5; "(5)" del arco narrativo -> "(7)"; refs 4.5/4.12 -> 5.1/5.8 en Open questions). Reportados y NO tocados: el ASCII del mapa dice "seccion 5" en el bloque SKILLS/SUBAGENTES (territorio del ilustrador); el "(4)" del arco narrativo enumera piezas que hoy viven en la 5/6; falta la seccion 6 en la Agenda; refs a seccion 4/5 en 5.5, 7.1 y 7.2 (contenido intocado por dispatch); refs historicas dentro de [closed] y Cut material (audit trail append-only). Nueva Open question: el ASCII archivado en Cut material conserva su fence ```ascii (prohibido editarlo), y `polish-ascii scan` detecta por tag, no por contexto -> en Step 6 va a levantar un diagrama descartado; fix propuesto para Polish. Sin tocar: ASCII, ascii-notes, image refs, claims verificados, atribuciones, audit trail [closed] previo, final.md.
  tags: [compact, too-dense, split, restructure, slide-content, redundancy, cut]
- talk: claude-cowork
  date: 2026-07-15
  location: Section 5 (Slides 5.1-5.4 -> 5.1-5.6) + nueva Section 6 (header + Agenda) + re-home ex-5.5..5.8 -> 6.1..6.4
  origin: presenter-chat
  feedback: "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides. Uno de los feedbacks mas importantes del draft."
  resolution: Pasada de densidad sobre la seccion 5, misma regla que las secciones 1-4: si una linea de Content ya esta en el bloque ASCII o nombrada en el `emphasize` de su ascii-note, baja a Speaker notes. Segundo de los tres dispatches que parten la ex-seccion 4 (12 slides, techo ~8). PARTIR 5.1 "(Demo time) Conozcamos la interfaz de Cowork" (44c, dos ideas) en "Demo time" (9c; lamina-interstitial, SOLO el banner ASCII, sin bullets y sin image ref; hereda los dos [closed] previos, el del banner 2026-06-09 porque el banner es su contenido y el de la piramide 2026-06-08 porque su ancla es el beat de la demo; notes 93w cargadas A PROPOSITO porque el guion de la demo ES contenido) y "La interfaz de Cowork" (21c; `screenshot-cowork-tab.png` + 3 bullets: que senalar en vivo, la terna de control modo+aprobar+carpeta, y GUI sin slash commands; notes 96w). La particion RESUELVE el Open question del banner DEMO TIME abierto desde round 3, via su opcion (a): separado del screenshot, el banner vuelve a ser el unico bloque ASCII de su lamina y el pipeline de Polish lo trata como render-driving, asi que el ilustrador SI lo renderiza en Step 6. COMPACTAR 5.2 -> "Instrucciones: el contrato" (54c -> 26c): estaba en 4 bloques (bullet + fence ```text de 12 lineas + parrafo indentado + 2 bullets); quedan 2. El fence ```text SE CONSERVA (lo pidio el [closed] 2026-06-09 "Agregar un ejemplo en el slide") pero recortado a las lineas que cargan el punto (quien es Atlas + la REGLA DE ORO); los 3 bullets de estilo de adentro del ejemplo bajan a notes, que ahora indican leerlos en voz alta. Fuera los 3 bullets de cierre: "Se escribe una vez" repetia el bullet 1, "Cortas y claras" es narracion, y "el lugar de las reglas no negociables" ya lo demuestra la REGLA DE ORO dentro del ejemplo. Notes 86w -> 121w (crecieron por el ejemplo que bajo). COMPACTAR 5.3 "Projects" (titulo 39c intacto, 5 bullets -> 3): los bullets 4 y 5 (folder picker + carpeta dedicada) NO bajaron a notes, se mudaron enteros a 5.5, que los ensena con capturas — salieron de aca y aterrizaron alla, sin duplicar; notes 139w -> 116w. PARTIR 5.4 "El selector de carpetas y el panel de contexto" (46c) — el peor defecto de densidad del deck, 5 bloques (bullet+imagen+bullet+imagen+bullet), dos capturas y 3 bullets en 5.625 pulgadas, la "y" del titulo era el aviso — en "Concede una carpeta" (19c; `project.png` + el selector del sistema + la carpeta como control de privacidad + la buena practica que bajo de 5.3, con "nunca datos confidenciales" fundido en el bullet de seguridad que ya lo dice mas fuerte; notes 89w) y "El panel de contexto" (20c; `context.png` + las tres capas en pantalla; notes 62w). Los dos [closed] del 2026-06-09 de la ex-5.3 que originaron esa lamina se mudaron con su contenido: ambos a la mitad A (el del settings.json porque su resolucion ES el bullet del selector; el del screenshot porque nombra `project.png` verbatim), con nota en la mitad B de que ese [closed] tambien la origino via `context.png`. Abierta la seccion "6. Trabajar y entregar" (19c) con goal, feedback vacio y boundary; ex-5.5..5.8 re-homeadas ahi y renumeradas contiguas 1..4 con su CONTENIDO INTACTO (un dispatch posterior hace su contenido y parte la 6.4). Agenda: agregada la seccion 6; el arco narrativo se deja stale A PROPOSITO (su "(4)" enumera piezas hoy repartidas entre 4/5/6) porque lo reescribe el dispatch final. Fix autorizado aparte: la fence del ASCII archivado en Cut material re-etiquetada de ```ascii a ```text (cero bytes del diagrama cambiados) para que `polish-ascii scan`, que detecta por tag, deje de levantar un diagrama huerfano sin slide contenedora — cierra la Open question de round 8. Cross-refs verificados por grep post-renumeracion: la ref de 7.1 ("Conectar con la seccion anterior... el archivo .md que ya vieron") volvio a resolver SOLA, porque la seccion previa a la 7 es ahora la 6 y si contiene el beat .md. Reportados y NO tocados (fuera de scope): ASCII del mapa en 4.5 dice "seccion 5" (ilustrador); 6.1 Content+notes "seccion 5" -> 7; 7.2 Content "seccion 4" -> 6; 3.1 Sources+notes y 3.2 notes "seccion 4" -> 6. Secciones 5 = 1..6 y 6 = 1..4, contiguas. Sin tocar: ASCII, ascii-notes, claims verificados, atribuciones L002, audit trail [closed] previo, final.md.
  tags: [compact, too-dense, split, restructure, slide-content, redundancy]
- talk: claude-cowork
  date: 2026-07-15
  location: Section 6 (Slides 6.1-6.4 -> 6.1-6.5) + cross-refs en 3.1 / 3.2 / 6.1
  origin: presenter-chat
  feedback: "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides. Uno de los feedbacks mas importantes del draft."
  resolution: Pasada de densidad sobre la seccion 6, misma regla que las secciones 1-5: si una linea de Content ya esta en el bloque ASCII o nombrada en el `emphasize` de su ascii-note, baja a Speaker notes. Tercero y ultimo de los tres dispatches que parten la ex-seccion 4 (12 slides, techo ~8). COMPACTAR 6.1 SOLO EL TITULO: "Archivos .md: el lenguaje en el que la IA piensa mejor" (54c) -> "Archivos .md: la lingua franca" (30c), la frase de la propia lamina y del corpus ("Markdown is the lingua franca"); el titulo cargaba en prosa el argumento que el bullet 4 ya hace. El cuerpo NO se toco por directiva explicita del Composer (4 bullets, sin visual, dentro del techo; las 166w de notes son guion de entrega de una sola idea). COMPACTAR 6.2 (titulo 32c intacto, 5 bullets -> 2): salieron los bullets 1, 2 y 4, que eran las tres cajas del diagrama transcriptas (fuentes -> .md -> entrega), las tres nombradas en el `emphasize` de su ascii-note y ya presentes en notes — merge, no traspaso; quedan el "vale doble" (memoria + archivos de trabajo), que el diagrama NO dibuja, y la regla de bolsillo, conservada VERBATIM porque round 7 evaluo cortarla como epigrama balanceado y la mantuvo a proposito (es la regla didactica que promovio el presentador y las dos clausulas cargan contenido concreto); notes 199w -> 155w; NO llegan a ~120 y se reporta el piso (~150): cinco beats con contenido propio y el recorte salio de andamiaje de guion. COMPACTAR 6.3 -> "Schedule sobre tus carpetas" (80c -> 27c, el segundo peor titulo del deck): la lamina re-ensenaba la 3.2 y sus propias notes lo admitian en la primera linea ("el concepto y los cuidados de donde-corre ya se ensenaron en la seccion 3"), asi que salieron los bullets 3 y 4 (el bloque donde-corre completo, incluida su cross-ref a 3.2), ya presentes verbatim en notes; quedan 3 bullets + `schedule.png` (el puente, cadencias/pestana Scheduled, Atlas lunes 8:00); notes 180w -> 141w; NO llegan a ~120 y se reporta el piso (~140): los hedges dateados no se aplanan (L002 > la guia de palabras), mismo criterio que la 3.2 que quedo en 171w. L002 intacto en 6.3: fecha del 7 de julio de 2026, hedge beta + planes pagos + rollout Max-first, y la quote verificada de la excepcion local (articulo 13854387, verificado 2026-07-09); la unica linea removida de notes fue "se saltea y corre al volver", porque 3.2 la ensena entera y es la que carga su atribucion completa (version anterior del articulo), asi que aca era repeticion SIN su hedge. [closed] 2026-06-09 de la corrida en la nube preservado intacto. PARTIR 6.4 "Artifacts y Live Artifacts: del resultado a algo compartible" (60c, dos ideas + 192w de notes en tres parrafos) en "Artifacts y Live Artifacts" (26c; cae el arco "de X a Y", que ademas prometia lo contrario de lo que la lamina dice porque hoy NO son compartibles; 4 bullets, SIN imagen: que es un Artifact, la distincion estandar/Live, las dos formas de crearlo y el estado de hoy; notes 140w; NO llegan a ~120 y se reporta el piso ~140, los tres claims del estado con su fuente y la nota de ShareDuo son sustancia protegida) y "El tablero de Atlas" (19c; `mockup-tablero.png` se muda entero aca porque el boceto del jefe es el spec de ESE tablero, no una ilustracion del concepto; 2 bullets + 1 imagen; notes 82w). El [closed] 2026-06-09 de ShareDuo se queda con la mitad A, que es donde vive el claim que corrigio: el beat de honestidad sobrevive entero (los tres claims del estado con su fuente oficial support 14729249 — locales, NO compartibles aun, connectors aprobados sin re-preguntar — mas la nota de ShareDuo dicha en voz alta en notes). Seccion 6 = 1..5 contiguas; seccion 7 intacta. Cross-refs corregidos: 6.1 Content + notes "seccion 5" -> 7; 3.1 Sources "se desarrolla en la seccion 4" -> 6; 3.1 notes "En la seccion 4 vuelven" -> 6; 3.2 notes "Anticipa la seccion 4" -> 6. Verificado por grep: la ref de 6.3 a la slide 3.2 resuelve (la seccion 3 no se renumero). Podadas de Open questions las cuatro entradas resueltas (6.1, 3.1, 3.2) con la convencion del archivo (strikethrough + RESUELTO); renumerado el pending-stub de `mockup-tablero.png` 6.4 -> 6.5. Reportados y NO tocados (fuera de scope): ASCII del mapa en 4.5 dice "seccion 5" (ilustrador); 7.2 Content "el `.md` con metadata de la seccion 4" -> 6 (lo hace el dispatch de la seccion 7). Gap L002 reportado, no editado: la fuente support 14729249 en 6.4 no tiene fecha de verificacion registrada en Sources aunque el dispatch la afirma (2026-07-09) — no se agrego para no inventar procedencia. Arco narrativo de la Agenda dejado stale A PROPOSITO (lo reescribe el dispatch final). Sin tocar: ASCII, ascii-notes, claims verificados, atribuciones L002, audit trail [closed] previo, final.md.
  tags: [compact, too-dense, split, restructure, slide-content, redundancy]
- talk: claude-cowork
  date: 2026-07-15
  location: Section 7 (H1 + goal + Agenda) + Slides 7.1-7.5 -> 7.1-7.6 + Sources de 6.4
  origin: presenter-chat
  feedback: "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides. Uno de los feedbacks mas importantes del draft."
  resolution: Pasada de densidad sobre la seccion 7, misma regla que las secciones 1-6: si una linea de Content ya esta en el bloque ASCII o nombrada en el `emphasize` de su ascii-note, baja a Speaker notes. Titulo de seccion "Advanced: Skills, Subagentes y Plugins" (38c) -> "Piezas avanzadas" (16c); la enumeracion de las tres piezas no se pierde, el goal de la seccion se reescribio para nombrarlas explicitas (Skills / Subagentes / Plugins) y agenda sincronizada. PARTIR 7.1 "Skills: ensenarle a Claude algo una sola vez" (44c; 6 bullets sobre el techo de 5, sin visual, 208w de notes, dos ideas) en "Skills: ensenar una vez" (23c; el concepto: definicion + "un trabajo por Skill", la frase ancla del presentador y el ejemplo `reporte-semanal` de Atlas; 3 bullets; notes 113w) y "Como se crea una Skill" (22c; los dos caminos + Code execution + la trampa del Save; notes 139w). Los dos [closed] del 2026-06-09 se mudan ENTEROS a la mitad B: los dos son sobre los caminos de creacion y su verificacion contra la documentacion oficial, y su presencia es lo que marcaba ese beat como lamina propia. Diagrama ASCII NUEVO en 7.2 (el unico que autoriza el dispatch; la mitad B seria si no la unica slide de la seccion sin visual y su contenido tiene forma: dos caminos que convergen en una compuerta): CAMINO 1 (pedila en lenguaje natural -> Claude escribe el SKILL.md) y CAMINO 2 (subi un ZIP, Customize > Skills > "+") convergen en la compuerta SAVE / ENABLE (caja de doble linea, marcada "la trampa") y solo pasada la compuerta hay SKILL ACTIVA, con leyenda al pie "frenar en la compuerta = la Skill no funciona"; ascii-note con intent/emphasize/labels al estilo de los demas; 21 lineas, max 59 columnas, flechas verificadas contra las cajas. L002 respetado en el diagrama: Cowork es GUI, no hay slash commands, se dibujan DOS caminos y no un tercero. Content de 7.2 = 1 bullet (Code execution, lo unico que el ASCII no dice) + el diagrama; los dos caminos y la trampa ya estaban en notes, fue merge. COMPACTAR 7.3 (ex 7.2, "Anatomia de un SKILL.md", titulo 23c intacto): estaba sobre el techo por bloques (1 bullet + diagrama + 2 bullets); salieron los 2 bullets de cierre (Metadata: / Cuerpo:), que son la leyenda que el diagrama ya carga rotulada en sus dos zonas y que el `emphasize` nombra entera; ya vivian en notes (merge), y se les sumo "`name` identifica" y "los pasos que sigue el agente" para no perder un matiz. Se conserva en lamina lo unico que el ASCII NO dice: que la `description` activa por sentido y no por palabra clave (el `emphasize` dice que dispara la Skill, no que lo haga de forma semantica). Notes 91w -> 110w, crecieron a proposito. COMPACTAR 7.4 (ex 7.3) SOLO EL TITULO: "Subagentes: delegar sub-tareas en paralelo" (42c) -> "Subagentes: delegar en paralelo" (31c), 2c sobre el techo era el defecto entero; el cuerpo conforma (4 bullets + 1 diagrama, ninguno transcribe el ASCII) y NO se toco; [closed] 2026-06-09 intacto. COMPACTAR 7.5 (ex 7.4) SOLO EL TITULO: "Plugins: empaquetar y distribuir un workflow completo" (53c, el peor de la seccion) -> "Plugins: empaquetar y distribuir" (32c); cae "un workflow completo", que el bullet 1 ya dice mejor con la cita del corpus ("Ship the whole thing"); el cuerpo son 3 bullets, el mas liviano de la seccion, NO tocado. COMPACTAR 7.6 (ex 7.5): "Plugins en una cuenta Team: ciclo de vida" (41c) -> "Plugins en una cuenta Team" (26c), cae "ciclo de vida" que es lo que el diagrama dibuja; salieron los 3 bullets de cierre (marketplace privado ZIP/GitHub, preferencia de instalacion, llega a chat y Cowork con updates sincronizados) = los pasos 2 a 5 del diagrama transcriptos, los cinco nombrados en `emphasize` y `labels`, y ya presentes en notes con las mismas palabras: merge puro, no se agrego una linea a las notes (111w sin cambios); quedan los Owners (que el diagrama no dice) + la entrada al ciclo + el diagrama. L002 intacto en 7.6: las tres fuentes oficiales sin tocar (support 13837433 manage-org-plugins, support 13837440 use-plugins, blog claude.com/blog/cowork-plugins-across-enterprise) y ningun claim sobre Team/Enterprise perdio respaldo ni hedge. Fix autorizado aparte: agregada "(verificado 2026-07-09)" a la fuente support 14729249 de la slide 6.4 (Artifacts y Live Artifacts), el gap L002 que el dispatch de la seccion 6 reporto y con razon no completo; la fecha se confirma desde memory.md round 5 (2026-07-09: locality de Live Artifacts re-verificada, sigue local / no compartible), y ahora matchea el formato de las fuentes de Schedule. Seccion 7 = 1..6 contiguas. Cross-refs: corregido el del scope, 7.3 Content + notes "el `.md` con metadata de la seccion 4" -> seccion 6. Verificado por grep post-renumeracion que ninguna ref viva apunta a slides de la seccion 7 por numero (las refs a Skills/Plugins desde 4.5, 6.1 y Conclusions son a nivel seccion y la 7 sigue siendo la 7); las "slide 7.1/7.2/7.3" en Sources son slides del deck del corpus, no de esta charla, y no se tocan. Podada de Open questions la entrada resuelta (7.2 -> 7.3, seccion 4 -> 6) con la convencion del archivo. Reportado y NO tocado (fuera de scope): el ASCII del mapa en 4.5 dice "seccion 5" en el bloque SKILLS / SUBAGENTES, hoy seccion 7 (territorio del ilustrador) — es el ultimo cross-ref stale vivo fuera del arco narrativo. Arco narrativo de la Agenda dejado stale A PROPOSITO (lo reescribe el dispatch final); su "(7)" ya resolvia y su texto "Cerramos con las piezas avanzadas" quedo alineado con el H1 nuevo sin editarlo. Sin tocar: los ASCII y ascii-notes preexistentes, image refs, claims verificados, atribuciones L002, audit trail [closed] previo, final.md.
  tags: [compact, too-dense, split, slide-content, redundancy, add-visual]
- talk: claude-cowork
  date: 2026-07-15
  location: Conclusions (1-2 -> 1-3) + Agenda (arco narrativo) + Thesis (verificada) + cross-ref en 5.6
  origin: presenter-chat
  feedback: "Slides has too much text. Mix de compactar sin perder el objetivo de la slide y partir en 2 slides. Uno de los feedbacks mas importantes del draft."
  resolution: Ultimo dispatch de contenido de la pasada de densidad: Conclusions + la tejido conectivo del deck (Agenda, Thesis, barrido final de cross-refs). Misma regla que las secciones 1-7: si una linea de Content ya esta en el bloque ASCII o nombrada en el `emphasize` de su ascii-note, baja a Speaker notes. PARTIR Conclusions.1 "El loop completo y la idea para llevarse" (40c; la "y" del titulo era el aviso, otra vez) en "El loop completo de Atlas" (25c) y "La idea para llevarse" (21c). El takeaway estaba enterrado bajo un diagrama de 15 lineas + el recap del arco + una lista de 7 piezas, en la ULTIMA lamina que la audiencia recuerda (principles.md: la ultima slide es un takeaway). Mitad A se queda con el ASCII del loop entero, sin editar, + 2 bullets; quitada la linea "**Las piezas:** Conectores (las manos) · Schedule (corre solo) · ... · Live Artifacts (compartir)", cuya mitad es el ASCII transcripto (el diagrama dibuja Schedule/Skills/conectores/Live Artifact, nombrados en `emphasize`), reemplazada por el complemento honesto del diagrama, que es lo unico que NO dibuja: Instrucciones, el Project con su carpeta, los `.md`, mas Subagentes y Plugins; los roles de las piezas visibles bajan a notes, que ahora las repasan una por una (merge); notes 83w. ACCURACY FIX de paso (L002): la lista vieja decia "Live Artifacts (compartir)" y la 6.4 ensena con fuente oficial (support 14729249, verificado 2026-07-09) que hoy NO son compartibles; la palabra salio y no se reemplazo por otra promesa. Mitad B deliberadamente casi vacia (3 lineas: el arco, la frase ancla verbatim con su fuente, y la pregunta de cierre en su propio renglon, separada del bullet donde venia pegada): es el remate y no se relleno para que parezca sustancial; notes 84w. Los dos arcos reescritos al deck que existe: el de la Agenda ("(4)" enumeraba interfaz/Instrucciones/Projects/`.md`/Schedule/Live Artifacts en una clausula, piezas hoy repartidas entre 4/5/6 -> el salto a Cowork se cuenta en tres tiempos, uno por seccion) y el de Conclusions.2 ("chat de memoria -> conectores -> tareas programadas -> Cowork (`.md`) -> Skills, Subagentes y Plugins" -> "el chat que responde de memoria -> conectores -> tareas programadas -> Cowork (que cambia, tu espacio, trabajar y entregar) -> piezas avanzadas"). Register de round 7 aplicado al texto nuevo del arco: cae "de traer informacion a actuar" (arco de X a Y) y el "(4)" usa el ancla de la sesion verbatim en vez de parafrasearla. COMPACTAR Conclusions.3 (ex Conclusions.2): titulo "Gobernanza y advertencias (antes de Q&A)" (40c) -> "Gobernanza y advertencias" (25c), el parentesis era un aparte de agenda para el presentador y las notes ya lo decian (merge); 6 bullets -> 4, FUNDIENDO los tres que decian lo mismo desde tres angulos (audit trail / no metas PII-NDA / dato regulado, ademas solapados con el beat de seguridad de la 5.5) en uno mas filoso que conserva las tres partes: la razon (sin audit trail, verbatim del corpus), la lista completa (clientes, financieros, PII, NDA) y el remate; ninguno borrado. El reframe al mundo de la gestion del dispatch del frontmatter se conserva casi verbatim ("con informacion de clientes o datos financieros, nada de esto. Cowork no es la herramienta") con PII y NDA sumados: NO se revirtio al encuadre biomedico. Notes 80w -> 127w, crecieron con autorizacion (absorbieron el aparte del Q&A, el matiz "en la superficie equivocada" y la lectura de los guardarrailes de afuera hacia adentro). DIAGRAMA DE GUARDARRAILES EVALUADO Y DESCARTADO (sugerencia del Composer): con el merge la lamina bajo a 4 bullets y la premisa del flag (6 bullets, sobre el techo) desaparecio; las cuatro capas no son concentricas sino filtros independientes y dibujarlas anidadas implicaria una contencion que no existe, que es el defecto exacto que el presentador cazo en la piramide del round 3 ([closed] 2026-06-09 en 4.5); y es la lamina del cierre responsable, donde la gravedad vale mas que la decoracion. Thesis LEIDA Y NO TOCADA: nombra piezas, no secciones, y las cinco que nombra (Instrucciones, Projects, .md, Schedule, Live Artifacts) siguen existiendo y ensenandose en las secciones 5 y 6; su arco chat -> conectores -> tareas programadas -> Cowork sigue mapeando 1/2/3/4-5-6; el claim sobrevive la reestructura intacto. Barrido final de cross-refs por grep sobre el deck entero: TODAS las refs vivas en prosa resuelven; corregida la unica stale encontrada (5.6 notes "Las tres capas de la lamina anterior" -> "del contexto", doblemente rota tras la particion de la ex 5.4). Verificado que las "slide 7.1/7.2/7.3/5.4/3.19/..." en Sources son slides del deck del corpus y no de esta charla: no se tocan. VERIFICADO Y REPORTADO: el ASCII del loop de Conclusions.1 NO esta stale (nombra solo piezas y pasos, sin un numero de seccion ni de slide), asi que el ASCII del mapa en 4.5 (`SKILLS / SUBAGENTES (avanzado, seccion 5)`, hoy 7) queda como el UNICO cross-ref stale vivo del deck: territorio del ilustrador, no editado. Podadas de Open questions las entradas resueltas (arco narrativo, recap de Conclusions, loop ASCII verificado, 5.6) con la convencion del archivo. Sin tocar: ASCII, ascii-notes, image refs, claims verificados, atribuciones L002, audit trail [closed] previo, final.md.
  tags: [compact, too-dense, split, slide-content, redundancy]
- talk: claude-cowork
  date: 2026-07-15
  location: Slide 4.5 ("Bloques que se apilan") -> bloque ASCII del mapa
  origin: presenter-chat
  feedback: "El ASCII del mapa manda al publico a la seccion equivocada: dice 'seccion 5' para Skills/Subagentes y hoy esa seccion es la 7. Arreglalo en el draft antes del freeze, no en el render."
  resolution: Ultima escritura de contenido a `draft.md` antes del freeze de Step 6. Corregida la etiqueta del bloque `SKILLS / SUBAGENTES` en el ASCII del mapa: `(avanzado, seccion 5)` -> `(avanzado, seccion 7)`. Es el ultimo cross-ref stale de la renumeracion de round 8 (la ex-seccion 5 "Advanced" es hoy la 7 "Piezas avanzadas") y el unico que vivia dentro de un diagrama, razon por la que los ocho dispatches del pase de densidad lo reportaron sin tocarlo: tenian instruccion de no editar ASCII. Se arreglo en `draft.md` y no en `final.md` ni en el SVG porque una etiqueta con el numero de seccion equivocado es un defecto de contenido de Step 4, no de renderizado (principles.md: el renderer nunca arregla contenido); un fix aguas abajo lo taparia y volveria en cada re-render. Sustitucion de un solo caracter, mismo ancho: verificado post-edit que las 28 lineas de la caja siguen midiendo 84 caracteres y que los bordes `||` y `+===+` no se movieron; cero cambio de geometria. El `ascii-note` se reviso y no requeria cambios: `intent`, `emphasize` y `labels` nombran Skills/Subagentes como bloque de la pila pero no citan ningun numero de seccion. Barrido independiente de los 17 bloques ASCII del deck y sus notes (extraidos por tag de fence, no por heuristica): no queda ninguna otra referencia stale a seccion o slide dentro de un diagrama; los unicos numeros en otros bloques son horas ("lunes 8:00"), pasos de un procedimiento, "CAMINO 1/2", "(1 clic)" y "~40 anios", ninguno un cross-ref. Confirma independientemente el reporte del dispatch final: era el unico stale vivo, y ya no queda ninguno en el deck, ni en prosa ni en diagrama. Podada la entrada de Open questions que lo flageaba, con la convencion de tachado del archivo. Sin tocar: el resto del ASCII, el ascii-note, image refs, claims verificados, atribuciones L002, audit trail [closed] previo.
  tags: [accuracy, visual, slide-content]
- talk: intro-curso-mim
  date: 2026-07-16
  location: Slide "1. Manos a la obra"
  feedback: "Dejemos este slide como primer slide que abre la presentacion. No va a ser concluciones pero cierra perfecto toda la resentacion."
  resolution: Movida del cierre a la apertura: es ahora la slide 1.1 y abre el deck (presentador confirmó "abre", no "cierra"). La sección Conclusions se eliminó. Speaker notes reescritas para apertura (decir la frase y hacer silencio, sin explicarla); la transición operativa al Día 1 (formación de equipos + licencia por grupo) que llevaba esta lámina se trasladó íntegra al nuevo slide Q&A (6.2), junto con su cita del README.
  tags: [restructure, bad-order, positioning]
- talk: intro-curso-mim
  date: 2026-07-16
  location: Slide "4. El valor no llegó solo"
  feedback: "Borrar este slide. Podriamos remplazar esto con un slide de mas el impacto en el usu.y eficiencia. Algo que sean numeros."
  resolution: Slide "El manager es la palanca" reemplazada por la nueva 1.4 "El valor no llegó solo", con números verificados de Bain (37% apuntaba a recortar 11%–20% vs. casi 40% *de los que midieron resultados* en 0%–10%; 90% aumenta el presupuesto igual) y su tesis: "la tecnología funcionó, el valor no llegó — el arreglo es organizacional, no tecnológico". Atribución visible en lámina ("Bain 2026"); canónica en Sources: Bain Automation and AI Pathfinder Survey 2026 (n=951). Se conservó el 67/32 de Microsoft como bisagra hacia el manager (a confirmar); los +17/+22/+30 de People Science se cortaron a Cut material por densidad. Ninguna cifra fabricada llegó a lámina.
  tags: [slide-content, accuracy, sources, rewrite]
- talk: intro-curso-mim
  date: 2026-07-16
  location: Slide "2. Objetivos de Aprendizaje"
  feedback: "No mencionemos atlas sino que vamos a tener varias misiones."
  resolution: Objetivo 4 genericizado: "Hands-on con la primera misión aplicada — Atlas" → "Hands-on con las misiones aplicadas — varias misiones a lo largo de la cursada". Ninguna misión se nombra ya en la Sección 2 (barrida completa: Content, Sources y speaker notes). El nombre Atlas se registró en Cut material y sobrevive solo en el cronograma (3.1), donde el pareo día↔misión es una decisión previa deliberada — confirmación pedida en Open questions.
  tags: [slide-content, terminology, cut]
- talk: intro-curso-mim
  date: 2026-07-16
  location: Section "3. Cronograma"
  feedback: "Borremos este slide."
  resolution: Slide "De un chat a una organización de agentes" eliminada; la Sección 3 queda con 1 slide. Contenido completo archivado en Cut material (lead, diagrama ASCII con su ascii-note, y las 3 misiones con su descripción). El render `images/s3-2-1-chat-delegar-orquestar.png` queda huérfano y NO se borró. Consecuencia gestionada: el arco Chat→Delegar→Orquestar ahora sobrevive solo como texto (objetivo 1 de 2.2) — verificado que se lee bien solo, y reforzado en los speaker notes de 2.2 y 3.1.
  tags: [cut, restructure, visual]
- talk: intro-curso-mim
  date: 2026-07-16
  location: Slide "1. Siete sesiones"
  feedback: "El texto de Siete sesiones deberia ir arriba."
  resolution: Pin cambiado de `timeline` a `process`: `timeline` no tiene campo de lead (su formato es un rail vertical de fecha + detalle), por eso el texto introductorio caía debajo de los 7 hitos; `process` sí admite un lead sobre los pasos, y las 7 sesiones son una secuencia numerada legítima. El texto ahora renderiza arriba. Trade-off (se pierde el rail temporal, se gana una tira de tarjetas numeradas) registrado en Open questions para confirmación del presentador.
  tags: [visual, bad-order, style]
- talk: intro-curso-mim
  date: 2026-07-16
  location: Slide "2. Herramientas del Curso"
  feedback: "Borrar Herramientas del Curso como secccion y dejar herramientas del curso como parte de como trabajamos."
  resolution: Sección "Herramientas del Curso" disuelta; la lámina sobrevive intacta como slide 4.2 dentro de "Cómo trabajamos". Deck: 7 → 6 secciones. El goal de la sección vieja se plegó al goal de la Sección 4, y la adyacencia con el Cronograma se preservó (Sección 3 → slide 4.2, misma posición relativa).
  tags: [restructure, bad-order]
- talk: intro-curso-mim
  date: 2026-07-16
  location: Slide "2. Herramientas del Curso"
  feedback: "Estaria bueno que automatizacion es realmente Autonatizacion y Analysis de datos. Burscar en todos lados."
  resolution: "Automatización" → "Automatización y Análisis de Datos" en la slide 4.2, con el body ampliado para nombrar explícitamente el análisis de datos. Grep global aplicado ("buscar en todos lados"): las 2 únicas ocurrencias de la categoría (Content + Sources de la lámina) se actualizaron; "Automatizar" de la slide 1.6 y "Automatizando" del título del Día 2 en 3.1 se dejaron intactos — son otro concepto, no el nombre de la categoría.
  tags: [terminology, slide-content]
- talk: intro-curso-mim
  date: 2026-07-16
  location: Slide "2. Herramientas del Curso"
  feedback: "Creo que esta visualizacion no es clara. Tal vez una tabla simple pero manteniendo los iconos."
  resolution: Visualización rehecha: de 3 tarjetas en fila (card-row) a una lista vertical de 3 filas con ícono por fila, pinneada `icon-list` — cada fila = ícono + categoría + para qué sirve. Es lo más cercano a la "tabla simple con iconos" pedida: el sistema de estilo prohíbe tablas nativas (las tablas pipe se renderizan como grillas de tarjetas). Nota de licencia por grupo preservada.
  tags: [visual, too-vague, rewrite]
- talk: intro-curso-mim
  date: 2026-07-16
  location: Slide "3. Lo que se llevan"
  feedback: "Mover este slide despues de Herramientas del Curso y borrar conclusiones."
  resolution: "Lo que se llevan" movida a slide 4.3, inmediatamente después de Herramientas del Curso (4.2), dentro de "Cómo trabajamos"; la sección Conclusions se eliminó. Speaker notes reescritas: ya no cierra el deck — cierra el bloque de cómo trabajamos y cierra el círculo con la lámina de apertura (1.1).
  tags: [restructure, bad-order, positioning]
- talk: intro-curso-mim
  date: 2026-07-16
  location: Slide "3. Lo que se llevan"
  feedback: "Agregar un slide Q&A. Buscar una imagen a la izquiera para utlizar."
  resolution: Agregado slide 6.2 "Q&A" como cierre del deck, pinneado `closing-hero`. La imagen a la izquierda NO se pudo aplicar: no existe ningún asset candidato en `images/` ni en el corpus — no se inventó ninguna ruta. El slot quedó documentado en un TODO en la lámina (con la ruta exacta de cambio a `content+image`, ya que `closing-hero` es full-bleed y no admite `aside`) y el asset faltante registrado en Open questions.
  tags: [add-slide, add-visual]
- talk: claude-cowork
  date: 2026-07-15
  location: Thesis + goal S2 + notes/Sources de 4.3, 4.12 y ascii-note 5.2
  origin: presenter-chat
  feedback: "mas frases slop: 'X deja de Y y pasa a Z', 'X es lo que Y', 'el cambio/salto viene cuando...', 'X es lo que vuelve util a Y realmente' y similares"
  resolution: Dos familias nuevas agregadas a desrobotizar/reglas-propias (formulas de transformacion y hendidas de revelacion). Barrido del draft: 6 instancias reescritas (Why-it-matters de la tesis, goal de la seccion 2, gloss de fuente y nota de 4.3, nota de 4.12, ascii-note de 5.2); "Lo que ves es lo que hay" (nota 4.9) conservada por ser modismo fijo (WYSIWYG), no formula. Variantes hermanas (ahi es donde / lo que hace la diferencia / ya no X ahora Y) barridas sin hits.
  tags: [style, rewrite, slop-pattern]
- talk: claude-cowork
  date: 2026-07-16
  location: Slides 1.1, 2.1, 2.2, 2.3, 2.5
  origin: presenter-chat
  feedback: "Correcciones s1-s2: 'la charla arranca ahi' slop; 'fecha de corte'->'fecha de entrenamiento'; 'se activa con un clic' es slop y mentira; 'la distincion de la charla' no se entiende; AHORA en minuscula; MCP redefinido; permisos en vez de 'borrador antes que envio'."
  resolution: Aplicado inline: fecha de entrenamiento en bullet+diagrama+notas; "Se activa a través de la biblioteca de conectores. Muchos requieren autenticación."; "Dos modos de responder:"; "busca información real, actualizada"; MCP = "el nombre técnico que se le da a los conectores..."; cierre de 2.5 = cuidado con autorizaciones + mail automático sin revisión humana.
  tags: [style, accuracy, terminology, rewrite]
- talk: claude-cowork
  date: 2026-07-16
  location: Slides 3.1, 3.2
  origin: presenter-chat
  feedback: "Tarea programada = prompt que se ejecuta automaticamente en momento preestablecido y frecuencia definida; sacar 'suscribirse a una respuesta'; sacar 'mientras la nube no llega'; 'sin la computadora prendida'; que significa 'las notebooks se suspenden solas'?"
  resolution: Definición reemplazada; bullet de suscripción eliminado; nube = "corre sin la computadora prendida"; Local sin la cláusula temporal; "notebooks" -> "laptops" en bullet, diagrama y notas (ambigüedad con notebooks de código).
  tags: [terminology, accuracy, rewrite]
- talk: claude-cowork
  date: 2026-07-16
  location: Frontmatter + slides 4.1, 4.2, 4.3 + C2
  origin: presenter-chat
  feedback: "Nadie va a entender 'engine de agente', son alumnos de management; 'vive aca' slop; Cowork es literalmente Claude instalado en una computadora (nunca mas 'compu'); '(encuadre de analistas)' slop; bullet de bioingenieria 100% slop y la charla no es de bioingenieria; 'la frase de la sesion' no es tal; el rol humano casi siempre es tipear el proximo prompt."
  resolution: "misma base técnica" en vez de Agent SDK; Cowork = "Claude Code hecho para ofimática..."; opener 4.2 = "Claude instalado en la computadora... eso cambia la forma de trabajar"; atribución inline del nuevo Excel eliminada; bullet bioingeniería eliminado; AUDIENCIA MiM CONFIRMADA -> frontmatter (presentation+audience) y C2 reencuadrados a gestión; fila del rol humano = "Hacer cada paso intermedio" vs "Revisar el plan y corregir el rumbo"; "compu" purgada del documento y prohibida en reglas-propias.
  tags: [audience, terminology, style, rewrite, slop-pattern]
- talk: claude-cowork
  date: 2026-07-16
  location: Slides 4.4-4.8 (+5.1 por arrastre)
  origin: presenter-chat
  feedback: "Sacar 'ya recorrimos los tres primeros'; por que 'app real'?; modo Ask vs automatico; no aclarar 'sin slash commands'; 'que valen para todo, sin repetirlas' slop; sacar '(como el disclaimer legal)'; un project no es un 'lugar fijo'; 'explorador de archivos'; redaccion humana para la buena practica; 'Lo de afuera, Cowork no lo ve' comas compulsivas."
  resolution: Todo aplicado inline; "lugar fijo" también corregido en el mapa 4.4 y C1; "slash commands" barrido de 5.1 (bullet, diagrama, notas); "folder picker" -> "explorador de archivos" también en notas; 4.8 = "Cowork no tiene acceso a nada fuera de ella salvo que le permitamos hacerlo".
  tags: [style, terminology, rewrite, slop-pattern]
- talk: claude-cowork
  date: 2026-07-16
  location: Slides 4.9, 4.10 + barrido (1.1, 2.4, 4.6, 4.13)
  origin: presenter-chat
  feedback: "'la maquina' es palabra rara, llamar a las cosas por su nombre; 'La estructura tambien la entiende la IA' mal escrito -> 'La IA esta especialmente entrenada para comprender su estructura'; 'el formato final, al ultimo', 'se genera una vez, al final'... sigo??"
  resolution: Regla nueva en reglas-propias ("llamar a las cosas por su nombre"); bullet 4.9 con la redacción del presentador; barrido documento-completo de fragmentos con coma/punto y coma: 4.10 reescrita (5 bullets), 1.1 ("No busca información nueva."), 2.4 (MT Newswires), 4.6 ("Se escriben una sola vez." / "Conviene que sean cortas y claras."), 4.13 ("ya están funcionando").
  tags: [style, rewrite, slop-pattern, terminology]
- talk: claude-cowork
  date: 2026-07-16
  location: Slides 4.11, 4.13, 5.5, C1
  origin: presenter-chat
  feedback: "'lo mismo del chat, ahora con carpetas y archivos' (titulo 4.11); saca s4.13; cita -> 'mas de una vez'; 'El loop de Atlas, punta a punta'."
  resolution: Título 4.11 = "Schedule en Cowork: tareas programadas sobre carpetas y archivos"; slide 4.13 (tablero de Atlas) eliminada con limpieza de referencias (nota 4.12, Open questions; mockup-tablero.png sin uso); cita de Skills = "más de una vez" en 5.1 y C1; "punta a punta" -> "El loop completo de Atlas:" / "El ciclo completo:" (5.5).
  tags: [cut, style, rewrite, slide-content]
- talk: claude-cowork
  date: 2026-07-17
  location: Nueva slide 3.3 + Agenda
  origin: presenter-chat
  feedback: "Ahora hagamos la division: introduce una slide entre cada parte para cortar (desde la seccion 4 en adelante es la segunda)."
  resolution: Insertada slide 3.3 "Fin de la parte 1": placa ASCII de corte (FIN DE LA PARTE 1 / PARTE 2: Claude Cowork) + bullets con el contenido de cada parte; notas marcan la pausa de la clase y que Atlas parte 1 se resuelve con lo visto. Agenda actualizada con la estructura de dos partes. Deck en 28 slides.
  tags: [add-slide, restructure, split]
- talk: claude-cowork
  date: 2026-07-17
  location: Deck-wide image audit + stop-slop pass
  origin: presenter-chat
  feedback: "Ask editor to check if images would be required and also pass the stop slop"
  resolution: Image audit completo: no se agregan imagenes nuevas; las 6 slides sin visual son beats deliberados de texto/codigo/gobernanza, `mockup-tablero.png` queda fuera porque reintroduce el tablero Atlas eliminado, y la decision abierta de 4.5 (banner ASCII + screenshot) sigue vigente. Stop-slop aplicado sobre prosa viva: fuera falso ease ("con un clic", "sin programar"), em dash de frontmatter, "literalmente/justamente", tuteo por defecto en notas tocadas, titulo "del leer al hacer", y formulaciones vagas. Audit trail, citas, Sources, Open questions y Cut material preservados.
  tags: [style, slop-pattern, visual, rewrite]
- talk: claude-cowork
  date: 2026-07-21
  location: Slides 4.9-4.10 (nuevas) + renumeracion 4.11-4.13
  origin: whatsapp-paulo
  feedback: "Agregaria en .md un ejemplo y listaria lo principal como #, -. Sino queda muy abstracto. 1 o 2 slides: 1 mostrando rapido la sintaxis y otro como se ve. Sino queda como un concepto metafisico."
  resolution: Ex-4.9 partida en dos: 4.9 'La sintaxis en un ejemplo' (archivo real de la mision en fence markdown) y 4.10 'El mismo archivo, renderizado' (ASCII render-driving con la correspondencia marca->resultado). Trabajar-en-md/Schedule/Artifacts renumeradas 4.11-4.13.
  tags: [add-slide, slide-content, example]
- talk: claude-cowork
  date: 2026-07-21
  location: Seccion 5 partida en 5/6/7 + Agenda + 4.4 + C1
  origin: whatsapp-paulo
  feedback: "Moveria Plugins a Enterprise: primero te ensenamos a hacerlo para vos. Y parti 'advanced' en skills y sub-agents como topicos distintos, sino queda todo metido ahi."
  resolution: Seccion 'Advanced' explotada en tres: 5 Skills (3 slides), 6 Subagentes (1), 7 Enterprise: distribuir con Plugins (2, con goal y notas reencuadrados a 'primero para el usuario, despues el equipo'). Agenda, arco, mapa 4.4 y arco de C1 actualizados.
  tags: [restructure, sections]
- talk: claude-cowork
  date: 2026-07-21
  location: Nueva slide 5.2 + 5.1 adelgazada + Open questions
  origin: whatsapp-paulo
  feedback: "Se perdio como se crea un skill. En Cowork tenes que usar /create-skill si o si... hay cosas que se crean desde la UI... falta la lista de comandos /." (presentador confirma 2026-07-21: Cowork incluye slash commands reducidos, /skill-creator entre ellos)
  resolution: Nueva 5.2 'Como se crea una Skill en Cowork': /skill-creator como camino principal (guia y revisa el SKILL.md), ZIP desde la UI como alternativa, tip de tipear / para listar comandos, Code execution y trampa del Save; diagrama de compuerta actualizado. 5.1 queda conceptual. Watch item reescrito: confirmar lista de comandos, existencia de /skill-optimizer y si el camino por comando tambien exige Save.
  tags: [accuracy, add-slide, product-change, verify]
- talk: claude-cowork
  date: 2026-07-21
  location: Slide 5.2 (refinada con captura del producto)
  origin: presenter-chat
  feedback: "Captura del panel Configuracion > Habilidades: Agregar ofrece 'Cree con Claude' / 'Escribe las instrucciones' / 'Subir una habilidad'; skill-creator listada como skill de Anthropic. Aclaracion: subir el ZIP no crea la habilidad, importa una existente."
  resolution: 5.2 reescrita con la evidencia: dos caminos de creacion desde el menu Agregar (Crear con Claude en chat / escribir instrucciones en la UI) + ZIP como importacion de una Skill existente + /skill-creator (skill preinstalada de Anthropic) como camino por chat. Diagrama, ascii-note, Sources (captura 2026-07-21) y notas actualizados; goal de la seccion 5 corregido.
  tags: [accuracy, product-change, slide-content]
- talk: claude-cowork
  date: 2026-07-21
  location: Slides 2.3, 4.3, 4.7, 4.11, 4.13, 6.1, 7.1
  origin: presenter-chat
  feedback: "Tenemos un ejemplo practico y simple para cada uno de los conceptos impartidos?"
  resolution: Auditoria concepto por concepto. Siete ejemplos agregados a la cara de la slide: MCP con el flujo MT Newswires (2.3), delegacion concreta del pulso semanal (4.3), Project 'Inteligencia de Mercado Semanal' (4.7), reporte .md de la mision (4.11), el tablero del jefe como ejemplo de Live Artifact con mockup-tablero.png recableada (4.13), las 8 propuestas en paralelo (6.1) y el plugin 'Atlas' con las tres Skills (7.1). Los demas conceptos ya tenian ejemplo en slide.
  tags: [example, slide-content, audit]
- talk: claude-cowork
  date: 2026-07-21
  location: Slide 6.1 + goal seccion 6
  origin: presenter-chat
  feedback: "'Regla de una linea: chico y visible -> Skill. Grande o ruidoso -> Subagente' es AI slop y ademas la regla esta mal: skills y subagentes no son disjuntos (una skill puede usar un subagente y al reves). Directamente no los compares ni aclares que oscurece."
  resolution: Bullet eliminado de 6.1; goal de la seccion 6 sin la comparacion; notas reescritas (el subagente se ensena por su uso, sin oponerlo a Skills). Regla nueva en desrobotizar/reglas-propias: "Nada de reglas de dedo con flechas ni falsas dicotomias".
  tags: [accuracy, slop-pattern, slide-content]
- talk: claude-cowork
  date: 2026-07-21
  location: Deck completo (rename) + slide 4.6 + missions/CoWork/mission.md
  origin: presenter-chat
  feedback: "Decisiones: (1a) el analista de la charla pasa a llamarse Faro y Atlas queda como la empresa; (2) YPF/Vista/Tenaris sin tecnologicas; y la mision se reestructura al orden de la clase y se parte en 2 como la presentacion."
  resolution: Barrido Atlas->Faro en la charla (23 reemplazos: agenda, 2.4, 2.5, 3.3, 4.3, 4.4, 4.6 con empresas YPF/Vista/Tenaris y carpeta Faro-Mercado, 4.7/4.8, 4.11/4.12, 5.1, 7.1 plugin "Faro", C1); Atlas queda solo como empresa. mission.md reescrita: 2 partes / 6 milestones en el orden de la clase, claims corregidos (sin ShareDuo, donde-corre actualizado, pestania Scheduled, /skill-creator y menu Agregar en M6), Parte 2 independiente.
  tags: [naming, consistency, restructure, mission]
- talk: claude-cowork
  date: 2026-07-21
  location: missions/CoWork (Mision 0 nueva) + slides 3.3 y 4.5
  origin: presenter-chat
  feedback: "Incorporar una variante del flujo de DIAA2026/caso_finanzas_desordenado como introductorio a la utilidad de Cowork, adaptada a nuestro caso ficticio, misma filosofia, sin perder la ejercitacion existente y replicando todo el flujo externo."
  resolution: Creada la Mision 0 'el escritorio del pasante' en el universo Atlas/Faro: gen_escritorio_pasante.py (regenerable; adaptado de gen_caso_finanzas.py), carpeta escritorio-del-pasante/ (5 archivos, 4 formatos: xlsx cotizaciones, docx pulso FINAL final, pdf guia v3, md notas, txt viejo; 4 errores plantados verificables cruzando documentos) y guia intro-escritorio-pasante.md con los 5 ejercicios del flujo externo mapeados a capacidades. Enganches: demo de 4.5 pasa a usar esta carpeta (ejercicios 1-2 en vivo), nota en 3.3, y aviso en la Parte 2 de mission.md (el pulso-semanal.md resultante es el insumo del M3). La mision Faro quedo intacta.
  tags: [mission, add-material, demo, cross-course]
- talk: claude-cowork
  date: 2026-07-28
  location: final.md + output/ + missions/CoWork (guias)
  origin: presenter-chat
  feedback: "Vamos con el re-polish liviano + render y a reescribir las guias de resolucion viejas."
  resolution: Re-Polish liviano (0 diagramas redibujados: los 19 SVG vigentes; solo cambio la nota del loop por el rename) + final.md regenerado (Faro, YPF/Vista/Tenaris, enganches Mision 0) + modelo parcheado con notas re-extraidas y render html (18 menciones Faro, Atlas solo como empresa). Guia de resolucion NUEVA mission-res.md (canonica, 2 partes / 6 milestones, prompts exactos, sin ShareDuo ni /schedule, con /skill-creator + trampa del Save + Mision 0 + tabla de facilitador y timing de 2 bloques); las dos guias viejas quedaron con banner de OBSOLETA (la Codex ademas señala que no hay variante Codex de la mision nueva). Los PDF viejos siguen siendo de la mision anterior.
  tags: [polish, render, mission, docs]
- talk: claude-cowork
  date: 2026-07-28
  location: Slide 5.2 (capturas) + missions/CoWork (variante OpenAI) + formato de entrega
  origin: presenter-chat
  feedback: "En que formato presentamos la resolucion de las 2 partes? + hace una variante de Codex + capturas del menu + y el panel de Habilidades."
  resolution: Capturas cableadas en 5.2 (skills-panel.png en el deck; skills-menu-chat.png en draft/final; el diagrama de caminos paso a doc-only). Variante OpenAI nueva mission-res-codex.md: Parte 1 en ChatGPT (search + connectors + Tasks, con la diferencia honesta de la entrega por notificacion) y Parte 2 en Codex (AGENTS.md, MCP, Automations, tablero HTML + Sites con URL, $skill-creator sin trampa del Save); banner de la guia Codex vieja apunta a la nueva. Formato de entrega: recomendacion en chat (md canonico + PDF por parte), a decision del presentador.
  tags: [product-evidence, mission, codex, slide-content]
- talk: claude-cowork
  date: 2026-07-28
  location: mission.md M4/M6 + mission-res.md (Paso 6.6) + mission-res-codex.md + Open questions del draft
  origin: presenter-chat
  feedback: "Podriamos introducir el concepto de subagentes en algun lugar apropiado tambien."
  resolution: Dos toques: semilla de observacion en M4 (ver el reparto en paralelo mientras corre la investigacion) y Paso 6.6 Bonus en M6 (subagente `investigador`, uno por ticker, prompt exacto, criterio blando y caveat de verificacion; el fan-out calca la slide 6.1). "Y despues" de M6 queda solo con Plugins. Codex: nota de que no hay equivalente definible por el usuario. Watch item nuevo en el draft: probar la creacion de subagentes en Cowork antes del workshop. PDFs mission y parte 2 regenerados; parte 1 sin cambios.
  tags: [mission, subagents, add-material, verify]
- talk: intro-curso-mim
  date: 2026-07-16
  location: Agenda
  feedback: "Antes de la agenda, empecemos con un slide con con text biemvenidos. Si podemos conseguir una imagen para poner a la izquierda seria bueno para llenar."
  resolution: Resuelto absorbiendo el pedido en la apertura existente, no creando una segunda primera lámina: "Manos a la obra" sigue abriendo el deck, ahora con un gesto explícito de bienvenida y una directiva `generate-image: left` para crear una imagen editorial abstracta de apertura. La imagen todavía no se genera en draft; se genera en Polish (Step 6) si la sesión tiene generación de imágenes. Si el presentador quiere una lámina "Bienvenidos" separada antes de 1.1, este cierre se revierte y se crea como slide nuevo.
  tags: [add-visual, merge-incorporation, positioning]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Section "1. Qué pensamos y por qué"
  feedback: "Agregar como slides 4 y 5 un arco basado en Robot-Proof: la primera con la portada a la izquierda y tres ideas sobre problemas bien definidos, correlación/causalidad y realidades ambiguas; la segunda debe cerrar con: El capital humano se vuelve ‘tóxico’ cuando solo representa conocimiento y habilidades rutinarias. Su valor vuelve a crecer cuando desarrolla metacognición, creatividad, adaptación y juicio."
  resolution: Se agregaron las slides 1.4 y 1.5: la primera usa la portada local de Robot-Proof a la izquierda y desarrolla problemas bien definidos, correlación/causalidad y ambigüedad; la segunda cierra con la tesis acordada sobre capital humano, metacognición, creatividad, adaptación y juicio.
  tags: [add-material, add-visual, slide-content]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "4. Human capital is not a toxic asset"
  feedback: "Cambiar el título ‘El valor humano empieza donde la respuesta no está clara’ por ‘Human capital is not toxic asset’."
  resolution: El título de la slide 1.4 se cambió a ‘Human capital is not a toxic asset’, incorporando el artículo requerido en inglés.
  tags: [slide-content, wording]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "4. El valor humano empieza donde la respuesta no está clara"
  feedback: "Revertir el último cambio de título y volver a ‘El valor humano empieza donde la respuesta no está clara’."
  resolution: Se revirtió el último cambio: la slide 1.4 recuperó el título ‘El valor humano empieza donde la respuesta no está clara’.
  tags: [slide-content, wording]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "4. Human capital is not a toxic asset"
  feedback: "Dejar ‘Human capital is not a toxic asset’ como título definitivo de la slide 1.4."
  resolution: La slide 1.4 queda titulada ‘Human capital is not a toxic asset’; no se modificaron el contenido, la portada ni la slide siguiente.
  tags: [slide-content, wording]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "5. ¿Qué hace valioso al capital humano?"
  feedback: "Cambiar el título ‘El criterio es el activo’ por ‘¿Qué hace valioso al capital humano?’."
  resolution: La slide 1.5 se tituló ‘¿Qué hace valioso al capital humano?’; el remate y las notas permanecen sin cambios.
  tags: [slide-content, wording]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Agenda
  feedback: "Aplicar la pasada completa de títulos acordada después de incorporar el gancho de Robot-Proof."
  resolution: Se aplicó la secuencia completa de títulos acordada en las seis secciones, conservando sin cambios el contenido, las fuentes y las notas de cada slide.
  tags: [slide-content, wording, narrative]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Section "1. Qué pensamos y por qué"
  feedback: "Mover las slides 1.6 y 1.7 inmediatamente después de la slide 1.3."
  resolution: Las anteriores slides 1.6 y 1.7 se movieron inmediatamente después de la 1.3 y ahora son 1.4 y 1.5; el arco de Robot-Proof pasó a 1.6 y 1.7, sin cambios de contenido, fuentes ni notas.
  tags: [restructure, bad-order, positioning]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Section "1. Qué pensamos y por qué"
  feedback: "Interpretar la numeración como global: mover las slides globales 6 y 7 inmediatamente después de la slide global 3."
  resolution: Se corrigió la interpretación a numeración global: las anteriores pantallas 6 y 7, correspondientes al arco de Robot-Proof, quedaron como pantallas 4 y 5; ‘Más ejecución, más agencia’ y ‘La IA expande, el juicio sube de precio’ pasaron a las pantallas 6 y 7.
  tags: [restructure, bad-order, positioning, numbering]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Section "1. Qué pensamos y por qué"
  feedback: "Cambiar los títulos globales 6 y 9 por ‘La ejecución se delega. La agencia crece.’ y ‘Entonces, ¿qué delegan primero los líderes?’."
  resolution: Se cambiaron únicamente los títulos de las pantallas globales 6 y 9 por ‘La ejecución se delega. La agencia crece.’ y ‘Entonces, ¿qué delegan primero los líderes?’; contenido, fuentes y notas permanecen sin cambios.
  tags: [title, flow, clarity, transition]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Thesis
  feedback: "Agregar a Claudio Righetti en la línea de autores de la presentación."
  resolution: La línea de autoría de la presentación quedó como ‘Paulo Veiga y Claudio Righetti, IAE Business School’; el perfil general del repositorio no se modificó.
  tags: [metadata, authors, cover]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "1. Bienvenidos al trabajo aumentado"
  feedback: "El slide tiene dos veces bienvenido."
  resolution: Se eliminó “Bienvenidos.” del cuerpo; la bienvenida queda expresada una sola vez en el título y el contenido comienza directamente con la tesis del curso.
  tags: [slide-content, wording, clarity]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Thesis
  feedback: "Hace que los autores estén uno abajo del otro."
  resolution: Los autores se separaron en líneas independientes — Paulo Veiga y Claudio Righetti — con IAE Business School en una tercera línea común.
  tags: [metadata, authors, cover, layout]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Thesis
  feedback: "Deberia ser Paulo Veiga, IAE Business School y Claudio Righetti, IAE Business School"
  resolution: La portada muestra dos líneas de autoría: ‘Paulo Veiga, IAE Business School’ y ‘Claudio Righetti, IAE Business School’.
  tags: [metadata, authors, cover, layout]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "1. Bienvenidos al trabajo aumentado"
  feedback: "El text **El futuro no va a ser de las empresas que simplemente usan IA. Va a ser de los managers que están aumentados por ella.** tiene un bullet. no es necesario y genera mucha identacion"
  resolution: En la versión HTML, la apertura conserva el callout pero oculta su icono y elimina el espacio reservado para él, reduciendo la sangría.
  tags: [slide-content, layout, html]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "2. Human capital is not a toxic asset"
  feedback: "Por que el texto ': cuando el objetivo, los datos y el criterio de éxito están claros, la IA puede buscar y evaluar respuestas a una escala que una persona no alcanza.' contine ':' ?"
  resolution: Se eliminó el separador inicial de los tres cuerpos: cada concepto termina con punto y la explicación comienza directamente con mayúscula.
  tags: [slide-content, wording, punctuation]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "5. La IA expande, el juicio sube de precio"
  feedback: "Borrar este slide"
  resolution: Slide eliminada a pedido del presentador. Contenido completo (dos bullets con datos de Microsoft WTI 2026: 66/58 y 50/46/86) archivado en Cut material; la Sección 1 pasa de 9 a 6 slides tras esta y las otras dos eliminaciones de la ronda.
  tags: [slide-content, remove-slide, restructure]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "6. La tecnología funcionó. El valor no llegó."
  feedback: "Borrar este slide."
  resolution: Slide eliminada a pedido del presentador. Contenido completo (datos de Bain 2026 y el 67/32 de Microsoft WTI 2026) archivado en Cut material.
  tags: [slide-content, remove-slide, restructure]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "9. Delegar no es abdicar"
  feedback: "Borrar"
  resolution: Slide eliminada a pedido del presentador. Contenido completo (38% human-in-the-loop, Zapier 2026, y la corroboración de Bain en notas) archivado en Cut material; la Sección 1 queda en 6 slides.
  tags: [slide-content, remove-slide, restructure]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "2. Qué herramienta para qué trabajo"
  feedback: "borrar Producción de Contenido como item. Y parti automatizacion y analiss de datos como dos iteams."
  resolution: Se quitó 'Producción de Contenido' como item (movido a Cut material) y 'Automatización y Análisis de Datos' se dividió en dos filas separadas: Automatización y Análisis de Datos, ambas sobre Claude Cowork. La lámina mantiene tres filas.
  tags: [slide-content, split, cut, restructure]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "3. Lo que se llevan"
  feedback: "Borrar este slide."
  resolution: Slide eliminada a pedido del presentador. Contenido completo (4 bullets sobre qué se llevan los alumnos) archivado en Cut material; la Sección 4 queda en 2 slides.
  tags: [slide-content, remove-slide, restructure]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "1. Cómo se construye la nota"
  feedback: "Revisar el texto: Misiones resueltas y reflexiones del equipo que entregando a lo largo de la cursada. Presentacion de 5 MIM del profilio por el equipo.  y hacermo mas compacto."
  resolution: Se corrigió la redacción del ítem Portafolio Grupal (errores de tipeo: 'entregando' → 'entregadas', 'profilio' → 'portafolio', '5 MIM' interpretado como '5 minutos' por consistencia con el pitch grupal de la slide 6.1) y se compactó a una sola oración.
  tags: [compact, too-dense, slide-content, wording]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "1. El portafolio se construye desde el Día 1"
  feedback: "Borrar este slide y seccion."
  resolution: Desambiguado por el presentador: se borró la slide y la sección entera 'Cierre y Portafolios'. Contenido de la slide del portafolio archivado en Cut material. '¿Preguntas?' se convirtió en su propia sección nueva de una sola slide, cerrando el deck. El deck pasa de 6 a 6 secciones (Cierre y Portafolios → Preguntas) y de 16 a 12 slides de contenido tras toda la ronda.
  tags: [slide-content, remove-slide, remove-section, restructure]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "1. El vehículo, no el destino"
  feedback: "Creo es importante marcar que"
  resolution: Bullet inicial incompleto, completado por el presentador en chat: el curso es muy hands-on/práctico con herramientas que ayudan a construir agentes para resolver los problemas de la Sección 1, pero el foco sigue siendo el criterio y los conceptos, no la herramienta. Se agregó esa idea al Content y se reforzó en speaker notes; el título se cambió de "La herramienta cambia. El criterio queda." a "El vehículo, no el destino" (retoma la metáfora ya presente en las notas: "Cowork es el vehículo, no el destino").
  tags: [slide-content, rewrite, title, add-content]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "1. El vehículo, no el destino"
  feedback: "El texto 'El foco no es dominar una herramienta...' no es correcto. Esta el foco al reves."
  resolution: Se invirtió el orden del Content: la frase que abre ahora cuenta qué van a hacer ("vas a construir agentes de verdad, con herramientas reales, para resolver los problemas que ya vimos"), y recién después subraya que el foco no es la herramienta sino la filosofía y el criterio. Orden confirmado explícitamente por el presentador: "Primero es contar que vamos a hacer y luego subrayar que el foco no es la herramienta." El título "El vehículo, no el destino" se mantuvo sin cambios.
  tags: [slide-content, rewrite, bad-order]
- talk: claude-cowork
  date: 2026-07-30
  location: Agenda
  feedback: "La charla se va a llamar Claude CoWork + Claude Advance Chat"
  resolution: Frontmatter class: renombrado de 'Claude Cowork para el dia a dia' a 'Claude CoWork + Claude Advance Chat', verbatim segun el pedido del presentador.
  tags: [rename]
- talk: claude-cowork
  date: 2026-07-30
  location: Section "1. Advance Chat: el chat de uso diario, llevado más lejos"
  feedback: "Nos falta un slide que explique y connecte con la introduccion. Este slide debe mecionar que el foco va a ser de la presentacion de introduction en talk va a ser empezar user Claude CoWork + Advance Clade Chat para poder realizar automatizacion y analysis de datos."
  resolution: Agregada nueva Seccion 'Apertura' (antes de Thesis, sin numerar, mismo patron que Conclusions/Open questions/Cut material) con 4 slides; la primera, 'De que trata esta charla', encuadra el foco en una linea: empezar a usar Claude Cowork + Advance Chat para automatizar tareas y analizar datos en el trabajo diario.
  tags: [add-slide, restructure, positioning]
- talk: claude-cowork
  date: 2026-07-30
  location: Section "1. Advance Chat: el chat de uso diario, llevado más lejos"
  feedback: "Vamos a agregar una slide sobre Claude and Antropic."
  resolution: Agregada nueva slide 'Claude y Anthropic' (Apertura, slide 2) con 3 bullets verificados: fundacion en enero de 2021 por Dario y Daniela Amodei y equipo ex-OpenAI, mision de desarrollo responsable de IA como Public Benefit Corporation, y Claude como familia de modelos bajo el criterio util/inofensivo/honesto. Se consolidaron los dos bullets casi duplicados del presentador sobre la fundacion en uno solo. Fuentes: company page oficial de Anthropic + Wikipedia (verificado 2026-07-30).
  tags: [add-slide, accuracy, sources, compact]
- talk: claude-cowork
  date: 2026-07-30
  location: Section "1. Advance Chat: el chat de uso diario, llevado más lejos"
  feedback: "Vamos a agregar tambien un slide sobre Claude tools y los sabores que tiene. cual es el uso de cada uno y audiencia."
  resolution: Agregada nueva slide 'Los sabores de Claude' (Apertura, slide 3): Claude Code (developers), Claude Cowork (knowledge workers, angulo de esta charla), Claude Chat/Web (uso diario, cualquier usuario) y Claude Design (research preview abril 2026, para quien no tiene formacion de diseno); corregido el nombre 'Claude Designer' del borrador del presentador a 'Claude Design', el nombre real y verificado del producto (fuente: anuncio oficial de Anthropic, abril 2026).
  tags: [add-slide, accuracy, sources]
- talk: claude-cowork
  date: 2026-07-30
  location: Section "1. Advance Chat: el chat de uso diario, llevado más lejos"
  feedback: "Mover ## 1. Las tres superficies de Claude despues de slide Claude tools."
  resolution: Movida la slide completa 'Las tres superficies de Claude' (Content, ASCII, ascii-note, Sources, Speaker notes y su feedback [closed] verbatim) de la Seccion 4 (era 4.1) a la nueva Seccion 'Apertura', como su 4ta slide, justo despues de 'Los sabores de Claude'. Seccion 4 renumerada 2-13 -> 1-12; referencias vivas a slides 4.5/4.13 en Open questions actualizadas a 4.4/4.12. Dos frases de encuadre temporal (Content: 'donde estuvimos hasta ahora'; Speaker notes: apertura 'hasta aca, todo paso en la superficie de chat') se ajustaron para la nueva posicion, ya que la slide paso de estar despues de 3 secciones de chat a ser la apertura de toda la charla; todo lo demas (ASCII, ascii-note, Sources, feedback [closed] de 2026-06-08) se preservo intacto.
  tags: [move, restructure, split]
- talk: claude-cowork
  date: 2026-07-30
  location: Section "1. Advance Chat: el chat de uso diario, llevado más lejos"
  feedback: "El chat como viene y sus límites desaparece y es parte de una seccion advance chat."
  resolution: Seccion 1 renombrada de 'El chat como viene y sus limites' a '1. Advance Chat: el chat de uso diario, llevado mas lejos'; conserva verbatim la slide 'El chat responde de memoria' y su Goal se amplio para cerrar con el adelanto de Advance Chat (Conectores y Search).
  tags: [rename, restructure]
- talk: claude-cowork
  date: 2026-07-30
  location: Section "1. Advance Chat: el chat de uso diario, llevado más lejos"
  feedback: "Vamos a introducir un slide sobre Advance Chat capabilities mencionado que hay dos concepto que vamos a introducir: Connectores y Search"
  resolution: Insertada nueva slide 1.2 'Advance Chat: dos capacidades que vienen' al final de la Seccion 1 (bridge/teaser corto, sin profundizar): nombra Conectores y Search como las dos capacidades que la Seccion 2 desarrolla en profundidad.
  tags: [add-slide, roadmap]
- talk: intro-curso-mim
  date: 2026-07-30
  location: Slide "1. ¿Preguntas?"
  feedback: "El slide de Q & A dice preguntas 3 veces. Revisaste correctamnete la asignacion ?"
  resolution: Se mantuvo el pin single-point, pero se eliminó la duplicación entre título y punto central: la slide conserva ‘¿Preguntas?’ como título y ahora usa ‘Cronograma, evaluación o logística: conversemos ahora’ como contenido.
  tags: [deduplication, template-assignment]
- talk: claude-cowork
  date: 2026-07-30
  location: Agenda / documento completo
  feedback: "Veamos como reoganizar en las siguientes secciones: Introduction (Anthropic, Objetivo, Claude Desktop en general) / Claude Desktop - Chat / Connectores / Automatizacion / Mission (nuevo slide que solo divide) / Claude Cowork / Knowleade & Ouput (all content about MD) / Projects / Instructions / Skils / Subagents."
  resolution: Reestructura a 11 secciones en el orden pedido, sin agregar slides de contenido. La ex-Apertura pasa a Seccion 1 (Introduccion). La ex-Seccion 4 (Cowork, 12 slides) se abrio en cinco secciones tematicas: Claude Cowork (6), Knowledge & Output (7), Projects (8), Instrucciones (9), mas las ya existentes Skills (10) y Subagentes (11). Agenda reescrita (arco narrativo + lista de 11 secciones); goals nuevos para las 4 secciones sin header previo; renumeracion de slides dentro de cada seccion.
  tags: [restructure, bad-order, split, rename]
- talk: claude-cowork
  date: 2026-07-30
  location: Seccion 5 "La mision"
  feedback: "Mission (nuevo slide que solo divide)" + "No agregar nuevos slides"
  resolution: Los dos pedidos se reconciliaron reutilizando la placa divisoria que ya existia ('Fin de la parte 1', ex-4.3) en vez de crear una slide nueva. Decision del presentador consultada en chat: se reemplaza el corte de clase por la mision. Retitulada 'La mision: Faro', ASCII y Content reescritos para presentar a Faro (el analista de mercado de Atlas) y anunciar que se arma pieza por pieza; el corte de clase baja a Speaker notes como sugerencia de pausa.
  tags: [restructure, rename, slide-content, add-visual]
- talk: claude-cowork
  date: 2026-07-30
  location: documento completo
  feedback: "Borrar plugins y Artifacts"
  resolution: Borradas 4 slides: 'Artifacts y Live Artifacts', 'Plugins: empaquetar y distribuir un workflow completo' y 'Plugins en una cuenta Team: ciclo de vida' (con toda la seccion Enterprise), mas 'Schedule en Cowork' (el presentador eligio borrarla al no tener lugar en la estructura nueva). Barrido de rastros: Thesis, arco narrativo de Agenda, mapa de bloques de 6.3 (ASCII sin la banda PLUGINS ni Live Artifacts, Content, ascii-note, Sources, notes), loop ASCII y lista de piezas de Conclusions.1, guardarrailes de Conclusions.2 (plugins verificados -> conectores verificados), como se agrega un subagente (11.1), notes de 10.1 y el walkthrough de la demo (6.4). Verificado: 0 menciones vivas de Plugins/Artifacts fuera del audit trail. Las capturas schedule.png y mockup-tablero.png quedan en disco sin referenciar, por si se reponen.
  tags: [cut, restructure, slide-content]
- talk: claude-cowork
  date: 2026-07-30
  location: Seccion 2
  feedback: "Claude Desktop: el chat deberia ser Claude Chat (Desktop)"
  resolution: Seccion 2 retitulada 'Claude Chat (Desktop)' en el H1 y en la lista de secciones de la Agenda. El arco narrativo no nombraba la seccion, no requirio cambio; el goal de la Seccion 1 conserva 'Claude Desktop' porque ahi se refiere a la aplicacion de escritorio, no a esta seccion.
  tags: [rename]
- talk: claude-cowork
  date: 2026-07-30
  location: Seccion 4 / documento completo
  feedback: "Automatización deberia ser Schedule. Usemos schedule en toda la presentation."
  resolution: Seccion 4 retitulada 'Schedule' (H1 + lista de la Agenda + arco narrativo + goal). Terminologia unificada en 29 puntos de prosa viva: Thesis, titulo de la slide 4.1 ('Schedule desde el chat'), la definicion del concepto, el mapa de bloques de 6.3 (Content, caja ASCII 'SCHEDULE' con geometria preservada, ascii-note y notes), el loop de Conclusions ('[Schedule] dispara', arco y lista de piezas), y las notes de 5.1, 6.2 y C.1. Se dejo 'tareas programadas' en dos glosas de Sources que describen productos de terceros (las "tasks" de ChatGPT y la observacion de primera mano en claude.ai): ahi el termino no nombra la feature de Cowork.
  tags: [terminology, rename, slide-content]
- talk: claude-cowork
  date: 2026-07-30
  location: Secciones 8 y 9 / documento completo
  feedback: "Borremos Instrucciones como seccion y que sea parte de projects." + "Listo, appliquemos estos cambios" (aprobacion de la tabla de titulos propuesta en chat)
  resolution: (1) La seccion 'Instrucciones' se elimino como seccion propia; su unica slide paso a ser 8.3, dentro de Projects, despues del selector de carpetas. Secciones 10 y 11 renumeradas a 9 y 10; el deck queda en 10 secciones y 30 slides. Goal de Projects reescrito para incluir las Instrucciones; Agenda (lista + arco narrativo) y las referencias cruzadas actualizadas (Skills seccion 10 -> 9; Open questions slides 10.1-10.2 -> 9.1-9.2 y 11.1 -> 10.1). (2) Aplicada la tabla de titulos completa: 24 slides retituladas para sacar jerga ('sabores'), nombres largos y solapamientos (1.3 vs 1.4 se pisaban; 7.1 y 9.3 sonaban iguales). La 4.2 quedo '¿Donde corre? Local o nube', alineada con el cambio de terminologia a Schedule.
  tags: [restructure, rename, cut, slide-content]
- talk: claude-cowork
  date: 2026-07-30
  location: Secciones 5 y 11 / frontmatter / slide 1.1
  feedback: "Agregar en 11 - otro La mission. Existen 2" + "La presentacion se deberia llamar Claude Desktop - Chat & Cowork" + "Tambien el autor el Paulo Veiga y Marco Sanchez Sorondo" + "Revisar el titulo tiene que ser la misma que introduction presentation."
  resolution: (1) La mision se parte en dos placas divisorias, espejando mission.md ("las dos partes"): seccion 5 'La mision, parte 1: Faro en el chat' (se resuelve con conectores y Schedule, lo ya visto) y seccion 11 NUEVA 'La mision, parte 2: Faro en Cowork' (Projects, Instrucciones, .md, Skills y Subagentes; con la nota de mission.md de que la parte 2 no exige la parte 1 resuelta). Placa ASCII gemela de la primera. Deck: 11 secciones, 31 slides. Los nombres de seccion se diferencian con 'parte 1' y 'parte 2' porque el roadmap del template resuelve la seccion activa por nombre y dos entradas identicas lo dejarian ambiguo. (2) frontmatter class: -> 'Claude Desktop - Chat & Cowork'. (3) frontmatter presenter: -> 'Paulo Veiga y Marco Sanchez Sorondo'. (4) Alineado el titulo con la apertura: la slide 1.1 abre con el nombre exacto de la charla, y se retiro 'Advance Chat' de la prosa viva (queda solo en el audit trail), incluida la lead de la slide 2.2.
  tags: [add-slide, restructure, rename, slide-content, terminology]
- talk: claude-cowork
  date: 2026-07-30
  location: Slide 3.2 "El primer conector: busqueda web"
  feedback: "cambiemos El primer conector: busqueda web Caso 1: Web Search Connector"
  resolution: Slide retitulada "Caso 1: Web Search Connector" y movida a 3.3 por la reordenacion de la seccion. Content, ASCII, ascii-note, Sources y notes sin cambios: el titulo ya instala el encuadre de "casos" y no hizo falta linea de enlace.
  tags: [rename, move]
- talk: claude-cowork
  date: 2026-07-30
  location: Slide 3.2 "El primer conector: busqueda web"
  feedback: "agregemos tambien un slide que es Caso 2: Claude In Chrome. Explicar el connector desde el lado funcional."
  resolution: Slide nueva 3.4 "Caso 2: Claude in Chrome", explicada desde lo funcional: extension de Chrome con panel lateral, trabaja dentro de la sesion ya iniciada, navega/hace clic/completa formularios/maneja pestanas, conocimiento incorporado de Slack, Google Calendar, Gmail, Google Docs y GitHub, disponibilidad en planes pagos y solo en Chrome de escritorio, y se habilita desde Connectors en Claude Desktop. ASCII nuevo (pagina abierta + panel lateral, flecha de lectura y flecha de accion). Todo verificado 2026-07-30 contra la doc oficial de Anthropic (support 12012173), citada como fuente del proveedor.
  tags: [add-slide, slide-content, add-visual, sources]
- talk: claude-cowork
  date: 2026-07-30
  location: Slide 3.2 "El primer conector: busqueda web"
  feedback: "Agregar un slide con 4 casos  Claude In Chrome es util."
  resolution: Slide nueva 3.5 "Cuando sirve Claude in Chrome" con cuatro casos elegidos para perfil de gestion (cargar datos en un CRM/ERP web, comparar proveedores entre pestanas, coordinar agenda y correo, relevar un portal que no exporta), mas el cuidado de seguridad que pidio el presentador: prompt injection, con las recomendaciones oficiales (sitios confiables, perfil de navegador separado, revision humana antes de aprobar). Citado support 12902428 "Use Claude in Chrome safely", que documenta el riesgo como abierto ("the chances of an attack are still non-zero"). Los cuatro casos se atribuyen como adaptacion del presentador, no como casos publicados por Anthropic.
  tags: [add-slide, slide-content, audience, sources, accuracy]
- talk: claude-cowork
  date: 2026-07-30
  location: Slide 3.2 "El primer conector: busqueda web"
  feedback: "Agregar una slide sobre que existen Out of The Box connectors Y Customs"
  resolution: Slide nueva 3.6 "Out of the box y externos" con la taxonomia en ASCII de dos ramas. El eje es "out of the box vs externos": el presentador corrigio la palabra "custom" en chat, asi que la familia se nombra "externos" en todo el deck. Se agrega que toda la rama externa se conecta por protocolo MCP y que el criterio de confianza cambia entre las dos familias (el catalogo paso por Anthropic, un conector externo no).
  tags: [add-slide, add-visual, terminology, slide-content]
- talk: claude-cowork
  date: 2026-07-30
  location: Slide 3.2 "El primer conector: busqueda web"
  feedback: "Mover ## 4. Donde se buscan y como se conectan y este se sria aout of the box"
  resolution: La slide "Donde se buscan y como se conectan" se movio a 3.7 y se retitulo "Out of the box: donde se buscan y como se conectan", como cara practica de esa familia. Conserva sus dos capturas (connectors_directory.png, connector_browser.png). El bullet "De donde salen: directorio / comunidad / propios (custom)" se retiro porque la taxonomia ahora vive en 3.6; el criterio de confianza y el ejemplo de MT Newswires (con el pedido de noticias de YPF, recuperado de la ex-3.3) quedan en la slide.
  tags: [move, rename, slide-content]
- talk: claude-cowork
  date: 2026-07-30
  location: Slide 3.3 "MCP: el nombre tecnico de los conectores"
  feedback: "MCP: el nombre tecnico de los conectores va a ser external connectors. Agregar que todos los conectores externos se connectar por MCP protocol."
  resolution: Slide retitulada "External connectors: todo pasa por MCP" y movida al cierre de la seccion (3.8). Content reescrito alrededor de la familia externa: definicion, el hecho nuevo de que todos se conectan por MCP, el ejemplo de flujo reescrito contra un ERP de la empresa (el de MT Newswires paso a 3.7, que es out of the box) y el equipo tecnico que expone un servidor MCP. ASCII conservado con labels actualizados (Connector externo, Servicio CRM/ERP/base) y ascii-note en espejo.
  tags: [rename, move, slide-content, terminology]
- talk: claude-cowork
  date: 2026-07-30
  location: Slide 3.5 "Los conectores no solo traen: tambien hacen"
  feedback: "Mover ## 1. Que es un conector despues de ue es un connector. El titulo deberia tambien revisando."
  resolution: La slide se movio a 3.2, inmediatamente despues de "Que es un conector", y se retitulo "Los conectores tambien actuan" (mas corto, sin la formula "no solo X: tambien Y"). Bloque movido intacto (Content, ASCII, ascii-note, Sources). El puntero adelantado "Un chat que se informa y actua puede trabajar solo (seccion 4)" se reubico al cierre de la seccion (3.8), porque desde la posicion 2 disparaba demasiado temprano; las notes se reescribieron en la apertura y el cierre por el mismo motivo.
  tags: [move, rename, bad-order, slide-content]
- talk: claude-cowork
  date: 2026-07-30
  location: Slide 4.1 "Schedule desde el chat"
  feedback: "Schedule desde el chat remente deberia ser Schedule"
  resolution: Slide 4.1 retitulada "Schedule", alineada con el nombre de la seccion. No habia referencias cruzadas al titulo viejo en prosa viva.
  tags: [rename, terminology]
- talk: claude-cowork
  date: 2026-07-30
  location: Section 6 "Claude Cowork" (slides 6.1-6.4)
  feedback: "[Composer audit, blocker 3 - time budget] Recortar la Seccion 6 de ~21 a 18 min de Tiempo objetivo, sin borrar slides ni bullets de Content con informacion unica."
  resolution: Re-sumada la seccion contra el draft.md actual (no coincidia con el baseline del audit): 6.1 sin cambios (2 min); 6.2 "La nueva habilidad base" recorto un parrafo de notes duplicado verbatim con 6.1 (4.5 a 3 min); 6.2bis "De chatear a delegar" notes comprimidas (5 a 4 min); 6.3 "El mapa" notes fusionadas sin perder beats (3.5 a 3 min); 6.4 "Demo" notes de la demo ajustadas de pacing, sin cortar el ejercicio en vivo (8 a 6 min). Nuevo total de seccion: 18 min, sobre contenido de Content intacto.
  tags: [time-budget, compact]
- talk: claude-cowork
  date: 2026-07-30
  location: Section 8 "Projects" (slides 8.1-8.3)
  feedback: "[Composer audit, blocker 3 - time budget] Recortar la Seccion 8 de 17 a 11 min de Tiempo objetivo."
  resolution: Notes recortadas en las 3 slides (8.1 el contenedor, 8.2 conceder carpeta, 8.3 Instrucciones), sin tocar bullets de Content ni las capturas de pantalla: 7 a 4 min, 3 a 2 min, 7 a 5 min. Nuevo total de seccion: 11 min, coincide con el target del audit.
  tags: [time-budget, compact]
- talk: claude-cowork
  date: 2026-07-30
  location: Section 10 "Subagentes" (slide 10.1)
  feedback: "[Composer audit, blocker 3 - time budget] Recortar la Seccion 10 de 7 a 4 min de Tiempo objetivo."
  resolution: Notes de la unica slide de la seccion comprimidas a la mitad (fan-out, criterio Skill-vs-Subagente, como se agrega), Content y ASCII intactos. Nuevo total de seccion: 4 min, coincide con el target del audit.
  tags: [time-budget, compact]
- talk: claude-cowork
  date: 2026-07-30
  location: Slide 9.2 "Como se crea una Skill en Cowork"
  feedback: "[Composer audit, blocker 3 - time budget] Recortar la slide 9.2 de 6 a 5 min de Tiempo objetivo."
  resolution: Notes recortadas (retirado un comentario meta sobre el draft y el aviso de vigencia acortado), Content, capturas y ASCII intactos. Nuevo tiempo de slide: 5 min.
  tags: [time-budget, compact]
- talk: claude-cowork
  date: 2026-07-30
  location: "deck-wide (Tiempo objetivo, todas las slides)"
  feedback: "[Composer audit, blocker 3 - time budget] El dispatch del orquestador daba como baseline actual ~155 min con Seccion 3 en 42, Seccion 1 en 11.5 y la slide 2.1 en 6 min; re-sumar el draft.md actual antes de cortar."
  resolution: "Re-sumado el draft.md ACTUAL (no el baseline recibido): total real previo a esta ronda = 129.5 min (Seccion 1 = 6, Seccion 2 = 6 [2.1 = 4], Seccion 3 = 25, Seccion 4 = 8, Seccion 5 = 2, Seccion 6 = 23, Seccion 7 = 12, Seccion 8 = 17, Seccion 9 = 13.5, Seccion 10 = 7, Seccion 11 = 2, Conclusions = 8). Las Secciones 1 y 3 y la slide 2.1 ya estaban en o por debajo del target del audit (6<7, 25<26, 4=4) — no se tocaron, para no recortar contenido que no lo necesitaba. Se aplicaron los recortes reales a Seccion 6 (23 a 18), Seccion 8 (17 a 11), Seccion 10 (7 a 4) y slide 9.2 (6 a 5). Nuevo total real: 114.5 min, dentro de la clase de 120 min. Discrepancia entre el baseline del dispatch y el draft.md real reportada al orquestador para reconciliar con el historial de forks paralelos en memory.md."
  tags: [time-budget, accuracy]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide 1.1 "Qué vamos a hacer hoy" (Sección 1, Introducción)
  origin: presenter-chat
  feedback: "Reemplazar la slide de apertura por dos: primero el problema (horas en trabajo manual, información dispersa, la barrera de saber programar) y después cómo lo vamos a atacar (agentes de IA que ejecutan trabajo, Claude Desktop con sus dos caras, el camino de la clase). Contenido aprobado verbatim."
  resolution: La slide 1.1 se partió en dos, con el texto verbatim aprobado. Nueva 1.1 "El problema: horas que se van en trabajo manual" (tres bullets de dolor) y nueva 1.2 "Cómo lo vamos a atacar" (agentes, herramienta, camino), cada una con su directiva `<!-- generate-image: right | ... -->` y ~2 min de Tiempo objetivo. "Quién es Anthropic" pasó a 1.3 y "Las cuatro herramientas de Claude" a 1.4. Ajustados el "Goal of this section" de la Sección 1 (ahora abre por el problema) y la cláusula de apertura del arco narrativo de la Agenda (problema → solución). Sources de las dos slides nuevas en el estilo organizativo del deck; la única cita de producto (Claude Desktop, dos caras) reapunta a la product page de Cowork ya citada. Total del deck: 114.5 → 117.5 min.
  tags: [split, add-slide, add-visual, slide-content, positioning, roadmap, time-budget]
- talk: claude-cowork
  date: 2026-07-31
  location: Sección 6 "Claude Cowork" (numeración de slides)
  origin: presenter-chat
  feedback: "La sección 6 tiene dos slides numeradas ## 2 ('La nueva habilidad base' y 'De chatear a delegar'); debe leerse 1, 2, 3, 4, 5."
  resolution: Renumeradas las tres slides posteriores al duplicado, sin tocar contenido: "De chatear a delegar" 2 → 3, "El mapa: piezas que se apilan" 3 → 4, "Demo: la interfaz de Cowork" 4 → 5. Barrido de referencias cruzadas en Open questions: tres menciones a "slide 6.4" (Demo/screenshot-cowork-tab, stub pendiente, banner DEMO TIME) reapuntadas a 6.5, y la referencia al mapa de la charla "(6.3)" a 6.4. La numeración de slides ahora es contigua dentro de las 11 secciones y de Conclusions.
  tags: [accuracy, restructure]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide 10.1 "Subagentes: varios trabajando a la vez" (Sección 10)
  origin: composer-audit
  feedback: "[blocker 1] El bullet 'Se agrega como una Skill … se le pide a Claude y se gestiona en Customize' afirma como hecho la creación de subagentes por el usuario en Cowork. El propio registro citado dice lo contrario (corpus/agentic-ai-deck.zip.md: 'Cowork subagents are coordinated under the hood — no manual /agents config exposed in the GUI', repetido en la matriz 4.10 con Cowork ⚠️). La otra fuente, code.claude.com/docs/en/sub-agents, es documentación de Claude Code, no de Cowork. Las Open questions del propio deck registraban que la creación a pedido en Cowork 'no está verificada de primera mano'."
  resolution: "Un intento de verificación por L002 antes de reescribir (búsqueda restringida a support.claude.com, claude.com y anthropic.com): no apareció ninguna fuente oficial que documente creación o configuración de subagentes en Cowork; todo lo hallado es de Claude Code, el Agent SDK o la plataforma. Se aplicó la versión que sostiene el corpus. El bullet del 'cómo se agrega' se reemplazó por dos: 'No se configuran a mano: los coordina Claude solo, según la tarea. No hay panel de subagentes en Cowork' y uno accionable, 'pedir el trabajo en partes separables, que es lo que habilita el paralelo'. Se conservó el valor de la slide (qué es un subagente, contexto aislado, resumen, el fan-out de las 8 propuestas) y el bloque ASCII, intactos. El Goal de la Sección 10 pasó de 'cómo se agrega' a 'cómo aparece en Cowork'. Sources: la cita del corpus ahora nombra explícitamente la frase 'under the hood' como evidencia sobre Cowork, y la doc de Claude Code quedó etiquetada como documentación de Claude Code usada solo para el concepto general, con la aclaración de que /agents y .claude/agents/ no están expuestos en Cowork y no se citan como evidencia sobre Cowork. Speaker notes reescritas para que el presentador no enseñe el claim retirado y tenga respuesta si le preguntan por configurarlos. La entrada de Open questions se reescribió: el deck ya no hace la afirmación, y queda como watch item qué habría que verificar de primera mano si el presentador quiere demostrar el bonus M6."
  tags: [accuracy, sources, slide-content]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide 11.1 "La misión, parte 2: Faro en Cowork" (Sección 11)
  origin: composer-audit
  feedback: "[blocker 2] La misión promete un entregable que la clase nunca enseña: el Milestone 5 de missions/CoWork/mission.md pide generar el tablero del jefe, pero el deck cortó las slides de Artifacts y Live Artifacts (Cut material, 2026-07-30) y ya no menciona ningún tablero; el loop de Conclusions termina en el borrador de Gmail. Opción (a) sugerida: nombrar el entregable en 11.1 y apuntarlo al mecanismo que el deck ya enseña."
  resolution: "Aplicada la opción (a), solo del lado del deck (mission.md no se tocó: el presentador lo va a reescribir aparte, y el deck debe quedar consistente sea cual sea el resultado). Se agregó un bullet a 11.1, FUERA del bloque ASCII para no romper el gemeleo con 5.1: 'El entregable final es el tablero para el jefe: se arma en .md y se exporta al formato de entrega, con el flujo de la sección 7'. Es un puntero a lo que la slide 7.3 ya enseña (se edita en .md, se entrega en el formato que pida el jefe, 'generame el entregable'), no una pieza nueva: 11.1 sigue siendo una placa divisoria, sin ASCII nuevo y sin cambios de geometría. Speaker notes de 11.1 ampliadas para que el presentador nombre el entregable y diga de dónde sale. Verificado que las dos placas de misión siguen siendo gemelas byte a byte salvo las cuatro cadenas intencionales."
  tags: [accuracy, slide-content, roadmap]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide 9.2 "Cómo se crea una Skill en Cowork" (Sección 9)
  origin: composer-audit
  feedback: "[major] La peor slide del deck por lejos: un bullet de entrada + tres caminos numerados + DOS capturas + un bullet + cuatro bullets más + un diagrama ASCII. Son dos imágenes Y un diagrama Y ~9 bullets contra un techo de un visual más ≤5 bullets. Además carga cuatro ideas independientes: los tres caminos de creación, el menú '+' del chat, los requisitos (slash commands / Code execution) y la trampa del Save. Sugerido: partir en 9.2a (los tres caminos del menú Agregar + skills-panel.png + el ASCII) y 9.2b (desde el chat: /skill-creator + skills-menu-chat.png + la trampa del Save); los requisitos bajan a Speaker notes."
  resolution: "Aplicado el split como lo sugirió el Composer, con el reparto de assets prescrito. Sección 9 pasa de 3 a 4 slides. Nueva 9.2 \"Crear una Skill desde el panel\" (30c): 1 bullet de entrada + `skills-panel.png` + el bloque ASCII con su ascii-note, ambos sin editar. Los tres caminos numerados NO se mudaron a la otra mitad ni se conservaron en lámina: son exactamente las tres cajas del menú Agregar que el ASCII ya dibuja y que su `emphasize` nombra como bloque, así que bajaron a Speaker notes por la regla de redundancia de Mayer — es lo que deja la mitad A en 1 bullet + visual, dentro del techo. Nueva 9.3 \"Crear una Skill desde el chat\" (29c): el menú \"+\", `skills-menu-chat.png`, `/skill-creator` y la trampa del Save (3 bullets + 1 imagen). Requisitos a notes: Code execution habilitado y el set reducido de slash commands (con el tip de tipear `/`), ambos en las notes de 9.3, donde vive el camino por comando. Ex 9.3 \"Un SKILL.md por dentro\" renumerada a 9.4 sin tocar contenido. Tiempo: 5 min → 3 + 3 (con demo cada una), el único +1 del dispatch, contra los -4 de los otros cuatro ítems. FENCE COUNT SIN CAMBIOS: el bloque ASCII se mudó entero a la mitad A, ni uno nuevo ni uno borrado (26 bloques: 24 ascii + 1 markdown + 1 text, verificado antes y después). Las dos capturas quedan ahora en slides distintas y ambas resuelven en disco. Cross-refs barridos: las notes de 9.1 (\"la creación paso a paso viene en la próxima slide; la anatomía del archivo, en la siguiente\") reapuntadas a las dos slides siguientes más el cierre de sección; el Goal de la Sección 9 reescrito a \"por sus dos caminos\"; la entrada de Open questions sobre slash commands (\"slides 9.1–9.2\") corregida a 9.2–9.3, que es donde vive el claim. En las notes de la mitad A se explicita que el diagrama adelanta el camino por chat y la compuerta del Save, para que el presentador los anticipe en una frase y no los desarrolle ahí. Sources repartidas: la captura de primera mano se partió por lo que cada mitad afirma (menú Agregar → 9.2; skill-creator y slash commands → 9.3), support 12512198 (doc atrasada, solo camino ZIP) a 9.2 y support 12512180 (habilitar desde el panel + Code execution) a 9.3, que es la que enseña la trampa. Sin tocar: el ASCII, su ascii-note, los claims verificados y sus hedges."
  tags: [split, add-slide, too-dense, redundancy, compact, move, slide-content, rename, time-budget]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide 6.4 "El mapa: piezas que se apilan" (Sección 6)
  origin: composer-audit
  feedback: "[major] Los nueve sub-bullets (`El chat → respondía solo de memoria`, `Conectores → quiero info real`, …) son el diagrama ASCII transcripto línea por línea: el diagrama ya aparea cada bloque con su frase-problema y ya lleva los marcadores `(visto)` y `<== ACÁ`. El presentador va a leer uno o el otro en voz alta. Sugerido: borrar los nueve sub-bullets, dejar los tres bullets de entrada y el diagrama."
  resolution: "Aplicado tal cual: fuera los nueve sub-bullets bloque↔problema, verificados uno por uno contra el ASCII de 30 líneas que los dibuja (los nueve están, cada uno con su frase-problema a la derecha, y los marcadores `(visto)` / `<== ACA` también). Quedan los tres bullets de entrada (\"bloques que se apilan\", \"el mapa de la charla\", \"cada bloque = un problema conocido\") y el diagrama. La sustancia no se borró: las notes ahora leen el diagrama de abajo hacia arriba (los tres recorridos con su problema, el marcador de \"estamos acá\") y ganan lo que la lámina nunca dijo y el diagrama tampoco, que es a qué sección corresponde cada bloque de arriba (`.md` → 7, Projects e Instrucciones → 8, Skills → 9, Subagentes → 10), útil como promesa de roadmap. Tiempo objetivo sin cambios (~3 min): la lámina es la placa de orientación de la charla y se recorre igual, solo que ahora sobre el diagrama y no leyendo bullets. Sin tocar: el ASCII, su ascii-note, Sources ni el título."
  tags: [redundancy, compact, cut, too-dense, slide-content]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide 7.3 "Trabajar en .md, exportar al final" (Sección 7)
  origin: composer-audit
  feedback: "[major] Seis bullets más un diagrama, y los bullets 1, 4 y 6 repiten las tres etapas del diagrama (fuentes → .md → entrega). Los 6 min son además el slide más largo del deck, empatado. Sugerido: conservar la regla de bolsillo, el claim de que la IA interpreta/edita mejor sobre .md, y el aterrizaje en Faro; la mecánica de fuentes/entrega baja a notes y la carga el diagrama."
  resolution: "Aplicado como se sugirió, 6 bullets → 4. Salieron el bullet 1 (\"la información de trabajo va en archivos .md mientras el trabajo sigue abierto\") y el bullet 4 (\"el entregable se genera una sola vez cuando el trabajo está listo\"): son la caja central y la caja derecha del diagrama, ambas nombradas en el `emphasize` de su ascii-note. Quedan el claim de que la IA interpreta/edita/crea mejor sobre `.md`, el alcance (memoria + archivos de trabajo del Project), la regla de bolsillo VERBATIM y el aterrizaje en Faro. Notes reescritas para absorber las dos etapas con su matiz completo (\"mientras el trabajo sigue abierto\" y el \"una sola vez\" del entregable), con la indicación explícita de recorrer el flujo sobre el diagrama porque la lámina ya no lo dice en texto. HILO DE 11.1 PRESERVADO A PROPÓSITO: la slide sigue enseñando \"se trabaja en .md y al final se exporta al formato de entrega\" y la regla de bolsillo, que es la frase que lo carga (\"se edita en `.md` y se entrega en el formato que pida el jefe\"), quedó intacta en lámina; las notes ahora nombran explícitamente que este es el mecanismo que 11.1 da por enseñado cuando promete el entregable para el jefe. Tiempo 6 → 4 min. Sin tocar: el ASCII, su ascii-note, Sources ni el título."
  tags: [redundancy, compact, cut, too-dense, slide-content, time-budget]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide 8.1 "Un Project: carpeta, memoria e instrucciones" (Sección 8)
  origin: composer-audit
  feedback: "[major] Seis bullets, sin visual, en un slide fundacional — y el bullet 5 (\"El usuario concede las carpetas con el explorador de archivos del sistema operativo\") está repetido verbatim como bullet 1 de 8.2, que es donde vive la captura. El título mide 47 caracteres contra el techo de 40. Sugerido: bajar los bullets 5–6 (pertenecen a 8.2), acortar el título a \"Qué es un Project\", y considerar promover \"tres capas persistentes\" a un ASCII chico porque tiene forma."
  resolution: "Aplicados el trim y el retítulo. Título \"Un Project: carpeta, memoria e instrucciones\" (47c) → \"Qué es un Project\" (17c); el compuesto colapsa y las tres piezas las sigue diciendo el bullet 1. Bullets 6 → 4: fuera el bullet 5, que era duplicación literal del bullet 1 de 8.2 (merge puro, la sustancia ya vive allá con su captura), y fuera el bullet 6 (buena práctica de carpeta dedicada + sin datos confidenciales), que se mudó a las Speaker notes de 8.2, donde está el beat de seguridad y la lámina del selector: salió de acá y aterrizó allá, sin duplicar y sin agregarle un bullet a 8.2. Notes de 8.1 reescritas en consecuencia (el control por explorador de archivos se anticipa en una frase y se remite a la lámina siguiente). Tiempo 4 → 3 min. ASCII DE \"TRES CAPAS\" EVALUADO Y NO HECHO, por directiva explícita del dispatch (el fence count debía quedar fijo en esta pasada por una preocupación abierta en el pipeline de render) y además por criterio propio: \"Instrucciones · Knowledge base · Chats\" es una enumeración plana de tres etiquetas, no una forma (ni flujo, ni jerarquía, ni comparación), y el único aspecto con forma del Project —que contiene carpeta, memoria e instrucciones— ya lo dibuja la pila del mapa de 6.4. Se reporta al presentador como no recomendado; si igual lo quiere, es un dispatch aparte. Sin tocar: Sources ni el resto de la sección."
  tags: [compact, cut, redundancy, move, rename, too-dense, slide-content, time-budget]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide Conclusions.2 "Antes de cerrar: cuidados"
  origin: composer-audit
  feedback: "[major] Seis bullets densos sin visual, en el slide que carga la carga ética de la charla — exactamente donde la audiencia debería estar leyendo menos y escuchando más. Aparte, \"Cowork no tiene audit trail\" se afirma como hecho de producto pero se apoya solo en `corpus/agentic-ai-deck.zip.md` (un deck interno de junio de 2026), sin fuente oficial de Anthropic, y es el tipo de claim que una audiencia de escuela de negocios puede repetir en el trabajo. Sugerido: partir en dos slides, o cortar a tres bullets y el resto a notes; y o bien sourcear el claim del audit trail contra doc oficial, o reencuadrarlo como \"esta charla lo trata como no auditable\" con la atribución al deck interno visible."
  resolution: "Elegida la opción de CORTAR A TRES (no el split): el deck ya está ajustado de tiempo y este es el cierre, que gana si se habla en vez de leerse. 6 bullets → 3. Quedan: toda salida es un borrador, la prohibición de datos (clientes / financieros / PII / NDA) con su razón, y las capas de guardarraíles. Bajaron a notes la reproducibilidad (prompt + entradas + salidas juntos) y el \"en el trabajo real, sin aprobación del área correspondiente\", ambos con su texto completo. Tiempo 3 → 2 min. VERIFICACIÓN DEL CLAIM DE AUDIT TRAIL (un intento por L002, restringido a support.claude.com / claude.com / anthropic.com): SÍ apareció fuente oficial, y CONTRADICE la afirmación plana del deck interno. Dos artículos, ambos verificados 2026-07-31: support 13364135 (Use Claude Cowork safely) dice \"Cowork activity is not captured in the Compliance API at this time. Team and Enterprise owners can stream Cowork events to your SIEM and observability tools through OpenTelemetry\"; support 14477985 (Monitor Claude Cowork activity with OpenTelemetry) documenta el registro completo (prompts, tool/MCP calls con parámetros, acceso a archivos, skills y plugins, decisiones de aprobación humana, requests y errores, todo ligado por un `prompt.id`), disponible solo en planes Team y Enterprise, con Claude Desktop 1.1.4173+, y con la salvedad de que \"Events are only exported when an admin configures an OTLP endpoint. No data flows by default.\" Así que el claim se reescribió con el matiz real en vez de reencuadrarse como opinión de la charla: la lámina ahora dice que la actividad de Cowork no queda en el registro de auditoría estándar, que solo hay rastro si la organización lo configura aparte (Team/Enterprise) y que por defecto no se registra nada — la advertencia sobrevive entera y además es más útil para esta audiencia, porque en una cuenta personal el rastro directamente no existe. Sources: agregadas las dos fuentes oficiales con su cita verbatim y su fecha de verificación; la cita del deck interno se conserva pero etiquetada como corregida contra ellas, sin borrar el rastro. Notes reescritas para que el presentador diga bien el matiz (Compliance API vs. OpenTelemetry, planes, opt-in del administrador) y no repita el claim viejo, y se les puso al frente que en esta lámina la audiencia tiene que escuchar y no leer. Nueva entrada en Open questions con la corrección, la evidencia y el watch item (\"at this time\" sugiere que puede cambiar; re-verificar antes de la clase). Título \"Antes de cerrar: cuidados\" (25c) intacto."
  tags: [compact, cut, too-dense, accuracy, sources, slide-content, time-budget]
- talk: claude-cowork
  date: 2026-07-31
  location: Talk completo — Thesis, Agenda, Open questions, Cut material y refs cruzadas de las 6 secciones + Conclusions
  origin: presenter-chat
  feedback: "Partir la charla de 120 min en dos clases. Este folder se queda como PARTE 2 (Cowork en adelante); la parte 1 (chat, conectores, Schedule, misión parte 1) se va a un folder nuevo, talks/claude-desktop-chat. Alcance del framing: mínimo mecánico — no autorizar slides nuevas, ni lámina de apertura, ni recap de la parte 1; solo lo que el formato exige."
  resolution: "El corte de secciones lo hizo un script (ex 6-11 → 1-6, ya contiguas); acá se hizo el encuadre. THESIS reescrita para esta charla sola: declara el chat extendido (conectores + Schedule) como material de la clase anterior y punto de partida, y pone el claim en el salto a Cowork sobre carpetas y archivos reales más la delegación combinando .md, Projects, Instrucciones, Skills y Subagentes; dice explícitamente que no vuelve sobre la parte 1. AGENDA reescrita en sus dos mitades: el Narrative arc narra ahora solo las seis secciones nuevas más las Conclusions, en la misma voz densa de un párrafo, y la lista Sections pasa de 11 a 6 ítems que coinciden 1 a 1 con los H1 (de paso se resolvió la discrepancia cosmética heredada 'Knowledge & Output (.md)' vs el H1). BARRIDO DE 27 REFS CRUZADAS en 8 slides, la parte de más valor del pase: 12 números internos viejos renumerados (notes de 1.4 con sus cuatro punteros de sección 7/8/9/10 → 2/3/4/5; 2.2 Content y notes, Skills 9 → 4; 2.3 notes, la placa de la misión 11.1 → 6.1; 4.4 Content + ascii-note + notes, la sección 7 → 2; 6.1 Content y notes, el flujo de la sección 7 → 2) y 15 referencias hacia atrás a material de la parte 1 REFORMULADAS a 'la clase anterior' en vez de borradas, para que el hilo entre las dos clases se siga oyendo (1.1, 1.3 Content y notes, 1.4 en sus tres capas —el mapa pasa a presentarse como el de las dos clases y los tres bloques '(visto)' quedan atribuidos a la anterior—, 6.1 goal/Content/notes, Conclusions.1 Content + ascii-note + notes, Conclusions.2 notes). En 6.1 el 'no hace falta haber resuelto la parte 1' se puso en negrita y se reforzó en las notes, porque tras el split es más importante, no menos. En Conclusions.1 el loop sigue abriendo con [Schedule] dispara —el ASCII no se tocó— pero la prosa de alrededor ahora dice que ese disparador es pieza de la clase anterior, y el 'arco de hoy' pasó a 'arco completo' partido en clase anterior / hoy. OPEN QUESTIONS podado: fuera las 4 entradas exclusivas de la parte 1 (URLs de round 4, tareas programadas en el chat, capacidad ejecutiva por conector, sourcing de Gemini) y filtrada la de URLs de round 3; renumeradas 6.5 → 1.5 (x3), 9.2–9.3 → 4.2–4.3, 10.1 → 5.1, 6.4 → 1.4; dos entradas nuevas, la del split con los artefactos que quedaron obsoletos y la de 'sin recap de la parte 1' como decisión consciente. CUT MATERIAL podado: fuera el detalle mecánico del Schedule de Cowork; reencuadradas por numeración las tres entradas que citaban slides viejas. La placa ASCII de 6.1 quedó intacta byte a byte; se deja anotado que su restricción de gemeleo con la placa de la parte 1 ya no se puede verificar dentro de un solo archivo, porque la gemela vive ahora en el otro Talk. Presenter feedback vacío en las 27 apariciones. Verificaciones 9/9 PASS: YAML OK con class 'Claude Cowork'; 13 bloques de fence pareados sin cambio; 5 image refs y 2 citas de corpus resuelven; secciones 1-6 y slides contiguos; Agenda 1 a 1 con los H1; 0 [open] / 0 [closed]; grep de numeración vieja limpio; Tiempo objetivo total 64,5 min sobre 19 slides, contra un duration declarado de 60 min (a confirmar). NO SE TOCARON, y quedan desactualizados a propósito: final.md, output/slide-model.json, output/html/index.html (describen el deck combinado) y los slugs s6-*..s11-* de images/, que el próximo Polish re-deriva y conviene seguir de un polish_ascii.py gc."
  tags: [split-talk, restructure, split, cut, roadmap, positioning, slide-content, time-budget]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Conclusions.1 "Qué nos llevamos de esta clase" (nueva) + Agenda (Narrative arc) + slide 5.1 (Speaker notes)
  origin: presenter-chat
  feedback: "Agregar una lámina de cierre que resuma lo que se vio en la clase. Tras el split, este Talk no tenía bloque `# Conclusions`: terminaba en la placa de misión parte 1, porque el encuadre del split había sido mínimo mecánico y sin slides nuevas."
  resolution: "Bloque `# Conclusions` nuevo, con UNA slide, ubicado después de `# 5. La misión · parte 1` y antes de `# Open questions`, siguiendo el patrón del Talk hermano (bloque no numerado, sin `Goal of this section` y sin `**Presenter feedback:**` a nivel bloque; Conclusions NO se agregó a la lista `Sections (in delivery order)`, que sigue 1:1 con los cinco H1 numerados). Título `## 1. Qué nos llevamos de esta clase` (30c, bajo el techo de 40 que varias slides del deck ya violan). Cinco bullets, uno por beat del arco real: el chat de fábrica que responde de memoria con sus tres límites; los conectores que lo sacan del aislamiento y además ejecutan acciones con autorización y revisión humana; los dos casos (búsqueda web y Claude in Chrome, con el prompt injection) más la división out of the box vs externos por MCP; Schedule con la pregunta de dónde corre; y la parte 1 de la misión resuelta sin salir del chat, con el puente explícito a Claude Cowork como cierre. Sin claims nuevos: cada afirmación ya está sourceada en su slide de origen, y `### Sources` lo declara en el estilo de slide organizativa que el deck ya usa en 1.1 y 1.2. DIAGRAMA: NO se agregó, por decisión. El arco de cuatro beats (chat de memoria → conectores → Schedule → misión) es una secuencia de etiquetas, no una forma; un ASCII de cuatro cajas en fila repetiría los bullets sin agregar información, y la slide ya está en el tope de densidad. El deck queda en 13 bloques ASCII, sin cambios. EFECTOS COLATERALES CORREGIDOS: el `Narrative arc` de la Agenda cerraba la clase en la placa de misión, ahora suma la cláusula del repaso de cierre; las Speaker notes de 5.1, editadas en el split para decir que era la última lámina de la clase, ahora anuncian el repaso que viene y avisan de no cerrar del todo ahí. Tiempo de la slide: ~3 min, contra los 10 de margen que había. Total del deck 50 → 53 min sobre 19 slides, con `duration: 60 min (a confirmar)`; la entrada de Open questions sobre la duración se actualizó con los números nuevos. `### Presenter feedback` presente y vacío, como en todo el deck (decisión permanente del presentador). VERIFICACIONES 8/8 PASS: YAML parsea con `class: \"Claude Desktop - Chat\"`; 26 líneas de fence = 13 bloques pareados, sin bloques nuevos; las 2 referencias de imagen resuelven en `images/`; secciones 1-5 contiguas e intactas y Conclusions con exactamente 1 slide; Agenda 1:1 con los cinco H1 numerados (Conclusions correctamente ausente); 19 `### Presenter feedback` + 7 `**Presenter feedback:**`, todos vacíos, 0 `[open]` y 0 `[closed]`; título de 30 caracteres; total 53 min. `final.md` y `output/` NO se tocaron y quedan desactualizados a propósito: el presentador re-corre Polish y Render."
  tags: [add-slide, slide-content, split-talk, roadmap, positioning, time-budget]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide Conclusions.1 "Repaso: las piezas y cómo se combinan" (nueva) + Agenda (Narrative arc) + notes de Conclusions.2
  origin: presenter-chat
  feedback: "Agregar una slide de conclusiones que resuma lo que se vio en la clase. Las dos que hay no son un repaso: la primera es el loop de Faro (el payoff de la misión) y la segunda el beat de gobernanza. No ponerla última, el deck cierra a propósito en los cuidados."
  resolution: "Slide nueva insertada PRIMERA en Conclusions (repaso → loop de Faro → cuidados), con renumeración 1→2 y 2→3. Razón de la ubicación: el loop de Faro termina con una pregunta retórica al público ('¿Qué otra tarea recurrente podrían delegarle a su propio Faro?') y un repaso plano después de ese gancho lo desinfla; además el orden material → aplicación → advertencias es el mismo que usa cada sección de la charla. Título 'Repaso: las piezas y cómo se combinan' (37c). Cinco bullets, uno por beat del arco: el chat extendido de la clase anterior como base y Cowork bajando a la computadora; el cambio de rol a delegar un resultado completo; los .md como formato de trabajo con el entregable generado al final; el Project sobre carpeta concedida con las Instrucciones como contrato; Skills y Subagentes, cerrando con la idea organizadora de que las piezas se combinan y cada trabajo usa solo las que necesita. Sin claims nuevos: cada punto ya está enseñado y sourceado en 1.1, 1.3, 2.3, 3.1, 3.3, 4.1 y 5.1, y Sources lo dice explícito además de citar los dos records del corpus. SIN DIAGRAMA a propósito: el mapa de 1.4 ya es esta misma lista dibujada como bloques apilados, así que un segundo diagrama de las mismas piezas sería redundancia de Mayer (el audit del Composer ya venía marcando redundancia acá); las notes mandan a volver un momento a 1.4 si hace falta apoyo visual. Ajustes de vecindad: el Narrative arc de la Agenda ahora describe el cierre en tres tiempos (repaso, loop, gobernanza), y las notes de Conclusions.2 perdieron las dos instrucciones que quedaron duplicadas ('recordar el arco entero' y 'repasar las piezas en una línea cada una'), reemplazadas por la indicación de que el repaso ya pasó y de que el trabajo de esa lámina es el diagrama. Registro impersonal per la regla propia de desrobotizar sobre segunda persona en láminas; sin em dashes en prosa nueva. TIEMPO: la slide va a ~2 min y el total pasa de 64,5 a 66,5 min contra duration 60 min (a confirmar); recomendación registrada y NO aplicada, bajar Conclusions.2 (el loop) de 5 a 3 min, porque el repaso nuevo ya cubre sus bullets de arco y piezas. Presenter feedback presente y vacío (28 campos, todos vacíos, 0 [open] / 0 [closed]). Verificaciones 8/8 PASS. No se tocaron final.md ni output/."
  tags: [add-slide, restructure, bad-order, slide-content, redundancy, time-budget]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Conclusions.1 (retitulada "El lunes: qué hacer con esto") + Agenda (Narrative arc) + slide 5.1 (Speaker notes)
  origin: presenter-chat
  feedback: "Más que un summary, un wrap-up."
  resolution: "Refinamiento del pedido anterior (la slide de cierre agregada el mismo día). La versión que había era un summary: cinco bullets, uno por sección, en orden de dictado (chat de memoria → conectores → dos casos y la división → Schedule → la misión), o sea un índice en pasado para gente que acababa de sentarse a ver todo eso. Reescrita como wrap-up: contesta '¿y ahora qué?' en vez de '¿qué vimos?'. TÍTULO 'Qué nos llevamos de esta clase' (30c) → 'El lunes: qué hacer con esto' (28c), que ancla el cierre en la acción y respeta el patrón de dos puntos del deck. CONTENT de 5 bullets a 4, uno por beat de cierre en vez de uno por sección: (1) la idea única, el chat consulta información actual y ejecuta acciones sobre mail y agenda, y eso se resuelve con configuración, sin instalar nada ni escribir código; (2) lo accionable ya, activar la búsqueda, conectar mail y agenda y dejar programado un trabajo recurrente; (3) el cuidado como última palabra del tema y no como bullet enterrado, ninguna acción que importe se ejecuta sin aprobación humana y Anthropic documenta el prompt injection como riesgo abierto que no es cero; (4) hacia dónde sigue, la segunda clase retoma este chat extendido y sigue en Claude Cowork sobre carpetas y archivos. Sin claims nuevos: los cuatro puntos ya están enseñados y sourceados en 2.1, 3.2, 3.3, 3.6, 3.8, 4.1 y 5.1, y `### Sources` no cambió, sigue en el estilo de slide organizativa. TRES REGLAS PROPIAS DE desrobotizar cambiaron la redacción respecto del borrador natural: la fórmula de transformación 'deja de X y pasa a Y' (que era literalmente como venía formulado el beat de la idea única) se reemplazó por el estado nuevo dicho plano; la etiqueta autorreferente tipo 'la idea que ordena todo' se cortó del bullet y quedó solo en las notas del orador; el registro de slide se mantuvo impersonal ('la cuenta que ya está en uso' en vez de 'la cuenta que ya tienen'), con la segunda persona reservada a las Speaker notes. Sin em dashes. SIGUE SIN DIAGRAMA, misma razón que antes y con más fuerza: cuatro etiquetas en fila no son una forma; el deck queda en 13 bloques ASCII. SPEAKER NOTES reescritas de repaso a cierre: arrancan diciendo que la lámina no vuelve sobre el temario, recorren los cuatro beats, marcan la advertencia como última palabra del tema con puntero a 3.6, y cierran con el puente a Cowork y la consigna antes del Q&A; `Tiempo objetivo: ~3 min` sin cambio, así que el total del deck sigue en 53 min sobre 19 slides. VECINDAD: el `Narrative arc` de la Agenda cerraba con 'un repaso corto de las cuatro piezas de la clase', que ya no describía la lámina, y ahora describe el cierre en cuatro tiempos; las notes de 5.1 decían 'la siguiente recorre lo que se vio' y ahora dicen 'la siguiente dice qué hacer el lunes con lo visto'. `Sections (in delivery order)` sin tocar. Presenter feedback presente y vacío. Verificaciones 8/8 PASS. `final.md` y `output/` no se tocaron y quedan desactualizados a propósito."
  tags: [slide-content, positioning, roadmap, add-slide, time-budget]
- talk: claude-cowork
  date: 2026-07-31
  location: Conclusions.2 (retitulada "Lo que se llevan: cambió el rol", movida de 1 a 2) + Conclusions.1 (loop de Faro, renumerada y notes) + Agenda (Narrative arc) + Open questions
  origin: presenter-chat
  feedback: "Más que un summary, un wrap-up."
  resolution: "Refinamiento del pedido anterior (la slide de cierre agregada el mismo día). Lo que había era un summary: cinco bullets, uno por sección, en orden de dictado (Cowork → delegar → .md → Projects/Instrucciones → Skills/Subagentes), o sea un índice en pasado para gente que acababa de ver todo eso. Reescrita como wrap-up, que contesta '¿y ahora qué?' en vez de '¿qué vimos?'. UBICACIÓN REVISADA Y CAMBIADA: de primera a SEGUNDA en Conclusions, orden nuevo loop de Faro → wrap-up → cuidados (renumeración: loop 2→1, wrap-up →2, cuidados sigue 3). El argumento que la había puesto primera era que un recap plano después del gancho del loop lo desinflaba; con un wrap-up se da vuelta, porque el beat accionable del wrap-up ('elegí una tarea recurrente y armala una vez') es literalmente la respuesta a la pregunta con la que cierra el loop ('¿Qué otra tarea recurrente podrían delegarle a su propio Faro?'): antes se la roba, después la contesta. Segunda razón: un wrap-up es un cierre y el cierre del deck es la lámina de gobernanza, así que el wrap-up tiene que quedar pegado a ella. No se movió a última por instrucción explícita. TÍTULO 'Repaso: las piezas y cómo se combinan' (37c) → 'Lo que se llevan: cambió el rol' (31c), que respeta el patrón de dos puntos del deck. CONTENT de 5 bullets, uno por beat de cierre en vez de uno por sección: (1) el rol cambió, ahora se delega un resultado completo y se guía el proceso; (2) los .md, el Project, las Instrucciones, las Skills y los Subagentes son piezas al servicio de eso y cada trabajo usa solo las que necesita; (3) el chat extendido de la clase anterior sigue en pie y se le suma la computadora, en una sola cláusula; (4) la consigna para el lunes, elegir una tarea propia que se repite todas las semanas y armarla una sola vez; (5) la barrera de entrada en cero, se opera en español y no hace falta escribir código. Sin claims nuevos: todo ya enseñado y sourceado en 1.1, 1.3, 1.4, 2.3, 3.1, 3.3, 4.1 y 5.1, y Sources sigue en el estilo de slide organizativa. El caveat opcional ('lo que se arma una vez hay que revisarlo') quedó FUERA del Content a propósito: con el wrap-up pegado a la lámina de cuidados le pisaba el trabajo; se movió a las Speaker notes como puntero a la lámina siguiente. DOS REGLAS PROPIAS DE desrobotizar cambiaron la redacción: el pedido venía formulado como contraste binario ('el cambio no es de herramienta, es de rol'), que cae a la vez en contraste negativo con coma y en fórmula de transformación, así que el beat se conserva pero afirmado plano ('El rol cambió'); y se evitó la hendida de revelación ('lo que cambió es el rol'). Registro impersonal de lámina, segunda persona solo en notas, sin em dashes. SIGUE SIN DIAGRAMA, misma razón: el mapa de 1.4 ya es esta lista dibujada como bloques apilados y un segundo dibujo de las mismas piezas es redundancia de Mayer; el deck queda en 13 bloques de fence. VECINDAD: el Narrative arc de la Agenda describe el cierre en el orden nuevo; las notes del loop perdieron 'la lámina anterior ya repasó las piezas', que dejó de ser cierta al quedar primera, y ganaron la instrucción de dejar la pregunta retórica en el aire porque la contesta la lámina que sigue. TIEMPO: ~2 min sin cambio, el total no creció; corrección de bookkeeping, la suma real de las 20 líneas Tiempo objetivo da 66,0 min y no los 66,5 anotados antes, contra duration 60 min (a confirmar). RECORTE del loop de Faro 5→3 min: se sigue recomendando y sigue SIN APLICAR, pero con justificación nueva, porque la vieja ('el repaso ya cubre sus bullets de arco y piezas') caducó al dejar el wrap-up de enumerar secciones; lo que queda en pie es que esos dos bullets duplican el mapa de 1.4 y que el peso de la lámina está en el diagrama. Presenter feedback presente y vacío (28 campos, todos vacíos, 0 [open] / 0 [closed]). Verificaciones 8/8 PASS. No se tocaron final.md ni output/ ni el Talk hermano."
  tags: [slide-content, positioning, restructure, bad-order, redundancy, time-budget]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "3. Quién es Anthropic"
  feedback: "Pongamos etas 4 cajas:"
  resolution: Slide 1.3 reescrita con las cuatro cajas del presentador (Que es, Por que existe, Como se estructura, Que la distingue) como items etiquetados, con fuentes por caja.
  tags: [slide-content, restructure, source-request]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "3. Quién es Anthropic"
  feedback: "Que es"
  resolution: Bullet cortado del presentador; se interpreto como el inicio de la caja 1 'Que es', ya cubierta por la reescritura de la slide.
  tags: [slide-content, unclear-feedback]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "4. Las cuatro herramientas de Claude"
  feedback: "Agreguemos un slide que sea de titulo "Claude Desktop Chat". Revisa el texto y hacelo mas compacto."
  resolution: Slide nueva 1.5 'Claude Desktop Chat', en tres bullets compactos (mismo producto, diferencias perifericas, foco en aspectos avanzados) mas la nota de que el core comun hace que todo aplique tambien a Cowork.
  tags: [new-slide, positioning, density]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "4. Las cuatro herramientas de Claude"
  feedback: "Agreguemos otro slide "Chat en Clade desktop y muestra la imagen chat-home.png"
  resolution: Slide nueva 1.6 'El chat en Claude Desktop', con images/chat-home.png como lamina de pantalla.
  tags: [new-slide, visual, screenshot]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Section "2. Context augmentation"
  feedback: "Esta seccion deberia ser "Context augmentation""
  resolution: Titulo de seccion cambiado a 'Context augmentation' y Goal reescrito alrededor del in-context learning como concepto ordenador.
  tags: [section-title, terminology, restructure]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "1. El chat responde de memoria"
  feedback: "Borremos la seccion Claude Chat (Desktop) y el slide "El chat responde de memoria" es parte de connector ahora."
  resolution: La seccion se renombro 'Context augmentation' y quedo como paraguas conceptual (memoria + ICL + las dos vias); Web search y Connectors salieron como secciones propias despues de ella.
  tags: [restructure, section-move]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "1. El chat responde de memoria"
  feedback: "Agreguemos que esto es importante en parte de In-context learning: In-context learning (ICL) es la capacidad de un modelo de lenguaje de adaptar su comportamiento o "aprender" una tarea nueva solo a partir de lo que ve en el prompt — sin que se le actualicen los pesos ni se reentrene."
  resolution: El in-context learning se agrego como cuarto bullet de la slide y como el concepto que da nombre a la seccion Context augmentation, con la definicion del presentador citada en Sources.
  tags: [slide-content, concept-depth]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "2. Dos formas de enriquecer el modelo"
  feedback: "Lo que viene: conectores y búsqueda. El titulo deberia ser mas "2 formas de enriquecer el modelo""
  resolution: Slide retitulada 'Dos formas de enriquecer el modelo' y reescrita alrededor de las dos vias: buscar en la web y conectar el chat a los sistemas del usuario.
  tags: [slide-title, positioning]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "1. La misma pregunta, dos modos de responder"
  feedback: "Elevemos esto como una seccion que es "web search". En la terminologia no usemos el termino connector. Lo vamos a introducir luego."
  resolution: Web search es ahora la seccion 3, previa a Connectors; su prosa no usa el termino Connector, que se introduce recien en la seccion 4.
  tags: [restructure, new-section, terminology]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "1. La misma pregunta, dos modos de responder"
  feedback: "Agregar un slide que muestre webseaerch.png solamente que es un screenshot."
  resolution: Slide nueva 3.2 'La busqueda en pantalla', solo con images/websearch.png y sin texto que compita con la imagen.
  tags: [new-slide, visual, screenshot]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "1. La misma pregunta, dos modos de responder"
  feedback: ""Regla: si la respuesta pudo cambiar → búsqueda obligada." marcalo como algo imporante."
  resolution: La regla paso a bullet destacado en negrita y con los ejemplos (precios, noticias, versiones, papers, normativa); las Speaker notes la marcan como lo unico que la audiencia tiene que anotar de la seccion.
  tags: [emphasis, slide-content]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Section "4. Connectors"
  feedback: "Usemos Connectors en vez de Conectores en toda la presentacion."
  resolution: Terminologia unificada a 'Connector/Connectors' en todo el deck: thesis, agenda, titulos de seccion y slide, Content, ASCII, Sources y Speaker notes.
  tags: [terminology, global-rename]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "4. El directorio de Connectors"
  feedback: "Mirar el layout de las imagenes. No esta quedando bien."
  resolution: Las dos capturas se separaron en dos slides (4.4 El directorio de Connectors y 4.5 Buscar, conectar y autorizar), una imagen por lamina, para que cada una se lea proyectada.
  tags: [visual, layout, restructure]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Section "5. Claude in Chrome"
  feedback: "Borrá la slide "Cuidado: prompt injection"."
  resolution: Slide 'Cuidado: prompt injection' eliminada del deck; el contenido completo, su ASCII y su fuente quedaron archivados en Cut material, y el tema sobrevive en las Speaker notes de 5.1 y en el tercer bullet de la lamina de cierre.
  tags: [cut-slide, density]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "3. Out of the box y externos"
  feedback: "Agregar que los out of the box estan curados por Anthropic"
  resolution: La curacion de Anthropic entro como bullet propio en el Content, como linea nueva en el ASCII (CURADOS por Anthropic / SIN curacion), en las Speaker notes y en la cita de Sources por contraste con 'not been verified by Anthropic'.
  tags: [slide-content, accuracy, trust]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "6. External connectors: todo pasa por MCP"
  feedback: "Agreguemos un slide como agregar un external connect. Usemos el screenshot custom-connector.png y el texto Y esta tabla:"
  resolution: Dos slides nuevas al final de la seccion 4: 4.7 'Agregar un external connector' con images/custom-connector.png, y 4.8 'Donde buscar servidores MCP publicados' con la tabla de cinco directorios del presentador.
  tags: [new-slide, visual, screenshot, reference-table]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "1. Describir una vez, que corra sola"
  feedback: "Agregar un slide con el screenshot schedule.png que es que muestra donde esta y como clearlo."
  resolution: Slide nueva 6.2 'Donde vive el Schedule', con images/schedule.png; la vieja 6.2 paso a 6.3.
  tags: [new-slide, visual, screenshot]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "1. El lunes: qué hacer con esto"
  feedback: "Mover la conclusion antes de la mission"
  resolution: El bloque Conclusions se movio completo delante de la seccion 7; las Speaker notes de ambas laminas y el Narrative arc se reescribieron para el orden nuevo, y el Q&A queda despues de la placa de mission.
  tags: [restructure, bad-order]
- talk: claude-desktop-chat
  date: 2026-07-31
  location: Slide "1. La misión, parte 1: Faro en el chat"
  feedback: "Aca borrar todo y solo mencioar que vamos a trabajar en la mission !. Es un slide que da pie a mostrar."
  resolution: Slide reducida a la placa ASCII mas una linea ('Ahora vamos a la mission'); los tres bullets de Faro pasaron a las Speaker notes, que ahora encuadran la lamina como pie para mostrar la consigna en vivo.
  tags: [density, slide-content, divider]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "2. La nueva habilidad base"
  feedback: "borremos este slides. Lo que me gustaria es tomar "El nuevo Excel" y cambuar en "Cowork, de proposito general" que hay una analogia con lo que fue "excel" como herrienta para knowleage workers."
  resolution: Slide 1.2 eliminada; la analogia entro como cuarto bullet de 1.1 ("Hay analistas que la llaman el nuevo Excel...", con la atribucion a la industria y no a Anthropic) y la fuente nextword.substack.com paso a las Sources de 1.1. Las Speaker notes de 1.2 (cuatro decadas de Excel, cuidado de atribucion, cierre sobre alumnos de management) se fundieron en las de 1.1, que subio de 2 a 3 min. El ASCII Excel -> herramientas agenticas quedo archivado completo en Cut material, con su ascii-note; no paso a 1.1 porque esa lamina ya lleva una directiva generate-image. Seccion 1 renumerada de 5 a 4 slides.
  tags: [cut-slide, merge-incorporation, compact, sources]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "1. Cowork, de proposito general"
  feedback: "Borrar" Eso cambia la forma de trabajar."
  resolution: La frase salio del primer bullet de Content de 1.1, que queda con la primera oracion sola. Se conserva a proposito en el Claim de la Thesis y en el Goal of this section de la Seccion 1, que son prosa de trabajo y no se proyectan.
  tags: [cut, slide-content]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "3. De chatear a delegar"
  feedback: "El chat quedo extendido en la clase anterior. Lo que cambia ahora es el rol: delegar. ->  "Lo que cambia ahora es el rol: delegar. Que delegamos ?""
  resolution: Primer bullet reescrito como "Lo que cambia ahora es el rol: delegar. Que delegamos?" con ortografia de espanol (signos de apertura y tilde). La referencia a la clase anterior sale de la lamina y sobrevive en las Speaker notes, que ademas ahora contestan la pregunta en vivo con la tabla y el ejemplo del reporte semanal.
  tags: [rewrite, slide-content, compact]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "3. De chatear a delegar"
  feedback: "poner el ascci a la izquiera y los bullets los items del list a derecha. IMPORTANTE: si no existe template para esto, avisame y voy a introducir cambios en el plugin."
  resolution: NO APLICADO, falta template en el plugin. El catalogo no tiene variante imagen-izquierda: content+image renderiza texto-izquierda / imagen-derecha y su unico layout alternativo es image-top; el aside admite side left pero recorta a full-bleed y esta prohibido para diagramas que se leen. Registrado en Open questions de draft.md, a la espera de que el presentador modifique el plugin. AMPLIADO 2026-07-31: la intencion quedo ademas registrada como metadata en la propia slide, debajo del heading, con la forma de los hints de autor del schema: <!-- layout: image-left --> mas una linea de comentario que explica el pedido y el bloqueo. La clave layout: no esta reconocida todavia, asi que hoy el render la ignora; verificado con polish_ascii.py scan que el conteo de bloques y los warnings no cambian.
  tags: [layout, visual]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "3. El mapa: piezas que se apilan"
  feedback: "Pongamos solo la imagen y una nota arriba con sun summary chico."
  resolution: Los tres bullets de Content se reemplazaron por una sola linea de lead ("Cada bloque resuelve un problema conocido y se apila sobre el anterior; cada tarea usa solo los que necesita"), que funde el bullet 1 y el 3. El bloque ASCII y su ascii-note quedaron intactos byte a byte. El bullet 2 (abajo la clase anterior, arriba lo que queda) se absorbio en las Speaker notes, que ya leian el diagrama de abajo hacia arriba y ahora nombran ese corte de entrada; nada fue a Cut material. Tiempo sin cambios, ~3 min.
  tags: [density, visual, compact]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "4. Demo: la interfaz de Cowork"
  feedback: "Esot no va a ser demo en vivo sino un screenshot es cowork.png. Mira como hacemos lo mismo en la presentacion con otros screenshots"
  resolution: La lamina dejo de ser un corte a demo en vivo. Retitulada "Donde se empieza en Cowork"; el image ref paso de screenshot-cowork-tab.png (interfaz vieja) a images/cowork.png (captura propia de la interfaz actual, con + New, el toggle Chat/Cowork y Project or folder circulados). Content reescrito con el patron de las otras laminas de screenshot del deck (3.2, 4.2, 4.3): un bullet antes de la captura y tres despues, nombrando lo que esta circulado. El banner ASCII DEMO TIME y su ascii-note quedaron archivados en Cut material. Sources ahora citan la captura propia; el corpus queda solo para el beat de control. Las notes reencuadran la Mision 0 como demo opcional. Tiempo de ~6 min a ~2 min. Precaucion de exactitud: la lamina no afirma cual es el modo por defecto (la captura vieja decia Ask, la nueva dice Auto); queda anotado en Open questions para confirmar contra la app.
  tags: [visual, screenshot, restructure, rename, accuracy, time-budget]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "1. Como se escribe un .md"
  feedback: "Falta realmente un slide antes que introdusca connectando con la necesidad de delegar que el output y que como parte de lo que tenemos en los folders es usualemnte conocimiento/intrucciones, necesitamos un formato que sea efficiente."
  resolution: Lamina nueva 2.1 "Que lee el agente en la carpeta", primera de la seccion, con el resto renumerado (2.1 -> 2.2, 2.2 -> 2.3, 2.3 -> 2.4). Cuatro bullets sin diagrama nuevo: delegar significa que el agente trabaja sobre lo que hay en la carpeta; lo que hay ahi es conocimiento e instrucciones; ese material necesita un formato que lea la maquina; y la idea del LLM wiki. Es la bisagra entre 1.2 (cambio de rol) y la mecanica del .md. Goal de la seccion y Narrative arc actualizados; ~2 min.
  tags: [add-slide, positioning, slide-content]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "1. Como se escribe un .md"
  feedback: "Agregar https://www.mindstudio.ai/blog/andrej-karpathy-llm-wiki-knowledge-base-claude-code como link para mas detalles."
  resolution: El link entro como primera fuente de la lamina nueva 2.1, con la atribucion desagregada: el post es del equipo de MindStudio (6 de abril de 2026) y RECOGE la propuesta del LLM wiki de Andrej Karpathy, no es un texto de el. En lamina la idea se nombra ("La idea del LLM wiki que propone Andrej Karpathy") sin comillas de cita textual. Verificado 2026-07-31.
  tags: [sources, accuracy]
- talk: claude-cowork
  date: 2026-07-31
  location: Seccion "4. Skills" (lamina nueva 4.4 "Grabar una Skill")
  feedback: "Let's add in the skill section at the end the 'Record a Skill' slide. It should cover the usage and purpose."
  resolution: Lamina nueva 4.4 "Grabar una Skill", ultima de la Seccion 4, que pasa de 3 a 4 laminas. Seis bullets etiquetados (tercer camino de creacion; donde esta, en el mismo menu "+" del chat de 4.3 y en Configuracion > Habilidades > Agregar; para que sirve, la tarea que uno hace de memoria y le costaria escribir en pasos; que captura, pantalla, clicks, tipeo y voz hasta ~10 min; el cuidado de no tipear contrasenas ni informacion sensible; disponibilidad Pro/Max/Team y solo Mac) mas un ASCII de cuatro tiempos (grabar y narrar > Claude mira > propone la Skill > revisar, editar y guardar) que desemboca en la misma compuerta del Save que marca el diagrama de 4.2. Sources: la doc oficial support 12512198 sostiene todos los datos y el anuncio del 21 de julio de 2026 en la cuenta oficial de Claude en X queda citado como cobertura, para el encuadre de "para que sirve"; se deja explicito que ninguna fuente documenta retencion ni uso para entrenamiento de las grabaciones, asi que el deck no lo afirma y va como pregunta abierta en las Speaker notes. Actualizados el Goal de la Seccion 4 y el Narrative arc (los dos caminos de creacion pasan a tres). Tiempo ~3 min: el tally del deck sube de 58,0 a 61,0 sobre un bloque de 60, anotado en Open questions junto con el watch item de disponibilidad (despliegue gradual, solo Mac, confirmar contra la app antes de la clase) y la actualizacion de la entrada de la Seccion 4, que ahora tiene 4 laminas con la de catalogo todavia pendiente.
  tags: [add-slide, slide-content, add-visual, sources, time-budget]
- talk: claude-cowork
  date: 2026-07-31
  location: Seccion "3. Projects" (lamina nueva 3.3 "¿Los lee todos?")
  feedback: "Agregar sobre project un slide que resuma esto: Titulo: Cuando le das archivos a la IA, ¿los lee todos? … Subtitulo: Dos formas de trabajar, y cual conviene en cada caso … Si son pocos archivos / Si son muchos archivos (multiplica por 10) / Si ademas queres que trabaje sobre los archivos … Las tres reglas practicas (subi lo que importa; nombres claros; PDFs escaneados) … Notas del orador: la analogia del expediente … Cierre sugerido: 'La calidad de lo que sale depende menos del modelo que de como ordenaste lo que entra.'"
  resolution: Lamina nueva 3.3 "¿Los lee todos?", tercera de la Seccion 3, insertada entre "Conceder una carpeta" (3.2) e "Instrucciones", que se renumero a 3.4; el arco de la seccion queda que es el espacio, como se le da la carpeta, que hace con lo que hay adentro y como se fija su comportamiento. Titulo corto en lamina y el titulo largo del presentador como linea de lead. Content con tres bloques etiquetados (pocos archivos, muchos archivos, trabajar sobre los archivos) mas un grupo aparte de tres reglas practicas con los iconos del presentador (📁 🏷️ 📄). Sin ASCII y sin image ref, por densidad textual. Verificacion de fuentes contra Anthropic Support "Retrieval augmented generation (RAG) for projects" (support 11473015, verificado 2026-07-31): confirmados el cambio automatico de modo al acercarse al limite de la ventana de contexto, el 10x de capacidad y el "no setup required"; NO hay umbral numerico documentado, asi que el deck no lo inventa. Dos claims del pedido se bajaron de tono por exactitud: "consume mucho de tu limite de uso" paso a "ocupar la ventana de contexto entera en cada vuelta" (la doc no habla del plan de uso) y "depende de que la busqueda encuentre lo correcto" salio de la lamina, porque la doc afirma lo contrario ("Response accuracy remains consistent with in-context processing"); la lamina describe solo el cambio de mecanismo y las dos posiciones quedan nombradas en las Speaker notes, con la decision registrada en Open questions. La regla de los PDFs escaneados se conserva con una aclaracion en notes de que aplica sobre todo al material que se carga como base de conocimiento, porque en Cowork el agente puede abrir el PDF con herramientas. Las notes enganchan con 2.1 para que las dos laminas no se pisen (2.1 ensena QUE hay en la carpeta, 3.3 QUE hace la herramienta con eso) y cierran con la analogia del expediente y la frase de cierre del presentador. Actualizados el Goal de la Seccion 3, el Narrative arc y la referencia cruzada 3.3 -> 3.4 de las Sources de Conclusions.2. Tiempo ~3 min: el tally del deck sube de 61,0 a 64,0 sobre un bloque de 60, con dos candidatos de recorte anotados en Open questions.
  tags: [add-slide, slide-content, sources, accuracy, time-budget]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "1. Que es un Project"
  feedback: "Agregar aca la nota que cowork hace uso efficiente para no cargar todos los archivos en memoria."
  resolution: Entro como nota al pie al final del Content de 3.1, no como un bullet mas, para no competir con los cuatro bullets de definicion: "Cowork trabaja la carpeta concedida con herramientas de archivo: abre, busca y escribe los archivos que la tarea necesita, en lugar de traer el contenido entero a la conversacion." Verificado contra Claude docs "Desktop and filesystem access" (https://claude.com/docs/cowork/3p/local-access, verificado 2026-07-31), que sostiene el modelo de acceso por herramientas ("the agent can then read, create, and modify files anywhere inside those folders"; "The agent can read, write, and search files ... with its file tools") y quedo agregada como segunda fuente de la lamina. PRECAUCION DE EXACTITUD: la doc no dice nada sobre memoria ni sobre consumo de contexto, asi que la nota NO afirma un mecanismo interno ni cifras; se queda en el modelo de acceso. Para que no pise a la lamina vecina 3.3 "¿Los lee todos?", que trata el par leer-todo / buscar-fragmentos de la BASE DE CONOCIMIENTO del Project, las Speaker notes de 3.1 ganaron un parrafo que separa los dos caminos y remite a la lamina de aca a dos. Tiempo sin cambios, ~3 min.
  tags: [slide-content, sources, accuracy]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "4. Instrucciones: el contrato de trabajo"
  feedback: "Instrucciones. Dividamos este slide en 2. Uno que explique que son las instrucciones."
  resolution: La lamina se partio en dos y la Seccion 3 pasa de 4 a 5 laminas. La 3.4 "Instrucciones: el contrato de trabajo" queda como lamina de concepto (que son, que el usuario las escribe una vez y valen para todos los chats, que conviene que sean cortas y claras, que es el lugar de las reglas no negociables y donde viven: el panel de contexto del Project en la interfaz, no un archivo que se edita a mano) y se lleva la captura nueva. La 3.5 "Un ejemplo de Instrucciones" se lleva el bloque ```text completo byte por byte, con su hint <!-- ascii-render: documentation-only --> intacto arriba de la fence: como la lamina nueva no tiene image ref, sin ese hint el pipeline lo tomaria como diagrama y lo renderizaria a SVG, y es una superficie de codigo. Verificado con polish_ascii.py scan que el bloque sigue saliendo render_hint=documentation-only / documentation_only=true y que el conteo de bloques (10) y los warnings no cambian. Alrededor del bloque quedo lo minimo: una linea de lead y un bullet que pone el foco en la REGLA DE ORO como la restriccion dura que se fija ahi. Las Sources se repartieron (corpus/agentic-ai-deck.zip.md con el panel de contexto y la matriz 3.3 en la de concepto; "corpus/mision - auto.zip.md" con el texto exacto de las Instrucciones de Atlas en la del ejemplo) y las Speaker notes tambien, sin perder nada: el "en lugar de re-explicarle el contexto cada vez" y el donde-viven con el concepto; el recorrido del ejemplo y el detalle de la regla de oro con el ejemplo. Los 5 min originales se repartieron ~2 (concepto) + ~3 (ejemplo), asi que el tally del deck SE MANTIENE en 64,0 sobre un bloque de 60 y las lineas "Tiempo objetivo" pasan de 21 a 22. Actualizados el Goal de la Seccion 3 y el Narrative arc. Barrido de referencias cruzadas a "3.4": la unica que apuntaba a Instrucciones, en las Sources de Conclusions.2, sigue siendo correcta porque el concepto se quedo en 3.4; el candidato de recorte "3.4 de 5 a 4 min" de Open questions se reemplazo por "3.5 de 3 a 2 min".
  tags: [split, add-slide, slide-content, time-budget]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "4. Instrucciones: el contrato de trabajo" (lamina de concepto tras el split)
  feedback: "Y agrega el screenshot instructions.png ramplazando documentation-only"
  resolution: La captura images/instructions.png (verificada en disco antes de escribir la ref, 347 KB) entro en la lamina de concepto 3.4 con el patron de las otras laminas de screenshot del deck (3.2, 4.2, 4.3): bullets antes de la captura y bullets despues. El bloque de texto que ocupaba ese lugar no se borro, se mudo entero a la lamina nueva 3.5 con su hint documentation-only intacto. La captura muestra el panel derecho de un Project en la app de escritorio con Instructions rodeado en violeta y debajo Memory, Context (con la carpeta concedida) y Scheduled, asi que no solo ubica las Instrucciones: muestra las tres capas que enumera 3.1 y la carpeta que trata 3.2. Eso se aprovecho en el alt text, en las Sources (entrada nueva de captura propia) y en las Speaker notes, que la usan para cerrar las dos laminas anteriores antes de entrar al ejemplo. Dos cosas quedaron anotadas en Open questions: (a) el idioma mezclado de las capturas, esta en ingles ("Instructions") y las de la Seccion 4 en espanol ("Habilidades"), con la opcion de nombrarlo al pasar (ya esta en las notes de 3.4) o unificar el idioma de la app y resacarlas; y (b) que al mostrar el panel de contexto entero se solapa con context.png, que ya esta en 3.2, con tres opciones para decidir con el presentador (dejar las dos y decir el enganche, sacar context.png de 3.2, o recortar instructions.png al bloque de Instructions).
  tags: [add-visual, visual, slide-content]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "3. El mapa: piezas que se apilan" (Seccion 1)
  feedback: "Es posible que 'Cada bloque resuelve un problema conocido y se apila sobre el anterior; ...' de la diagrama necesita resaltado. Si es una limitacion del style template, avisame."
  resolution: La linea de lead dejo de ser un parrafo suelto y paso a llevar un rotulo en negrita al frente, "**Idea clave:**", que es el recurso de enfasis que el schema de draft admite en el Content y que el render html-strict ya sabe destacar. NO es una limitacion del template: la lamina no tiene un slot de callout propio porque su Content es una sola linea de lead mas el diagrama, y meterla en blockquote la bajaria a nota al pie (que es como se lee la nota de 3.1), justo lo contrario de lo pedido. Si se quiere mas peso visual del que da la negrita, la salida es cambiarle el template a la lamina, no el texto; queda anotado por si el presentador lo pide.
  tags: [emphasis, slide-content, template]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "4. Donde se empieza en Cowork" (Seccion 1)
  feedback: "solo deja la imagen, no pongas el texto."
  resolution: El Content quedo con la sola referencia a images/cowork.png. Los cuatro bullets (+ New, el toggle Chat/Cowork, Project or folder y el selector de modo) bajaron a las Speaker notes, fundidos con lo que ya estaba ahi y sin perder informacion ni el cuidado sobre el modo por defecto. Sources sin cambio. Tiempo objetivo sin cambio (~2 min): la lamina ya era de apoyo visual y ahora todo el recorrido va hablado sobre la captura.
  tags: [slide-content, visual, trim]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "2. Como se escribe un .md" (Seccion 2)
  feedback: "Falta un slide que introdusca que es un MD. Este slide deberia ser un una imagen que muestre como se ve en formato texto y como es la represantacion visual de ese texto. Podes generarla ?"
  resolution: Fusion, elegida por el presentador entre tres opciones. Las ex 2.2 ("Como se escribe un .md", fence markdown con el archivo crudo) y 2.3 ("El mismo archivo, ya formateado", fence ascii con el render) se unieron en una sola lamina, "2. Que es un .md - el texto y lo que se ve", con UN bloque ascii de dos paneles lado a lado unidos por una flecha: a la izquierda LO QUE SE ESCRIBE (el .md crudo) y a la derecha LO QUE SE VE (el mismo archivo formateado), con las etiquetas laterales que atan cada marca a su elemento visual. Ese bloque es el que el pase de Polish renderiza a imagen, asi que la imagen pedida sale de ahi y no de generacion de imagen. Sources fusionadas sin duplicar, notes fusionadas. La Seccion 2 bajo de 4 a 3 laminas y el deck recupero ~2 min. El Goal de la Seccion 2 y el Narrative arc se reescribieron; se barrieron las referencias cruzadas a la numeracion vieja (2.4 -> 2.3). La ex 2.3 quedo archivada entera en Cut material.
  tags: [merge-slides, slide-content, visual, time-budget]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "4. Grabar una Skill" (Seccion 4)
  feedback: "Falta un slide que explique somo se usa un skill. Y exsite dos formas: En forma explicita usandolo como command (/) o decide el uso en funcion del prompt."
  resolution: Lamina nueva "2. Como se usa una Skill", ubicada por decision del presentador DESPUES de 4.1 (que es una Skill) y ANTES de los tres caminos de creacion: primero usar, despues fabricar. Cubre los dos modos de invocacion con el hilo generico del deck (informe-mensual sobre notas/): explicito, /informe-mensual; y automatico, "armame el informe de mayo con lo que hay en notas/", donde Claude compara el pedido contra la description de la Skill. De ahi sale el consejo practico: la description no es decoracion, es el disparador. Diagrama ascii nuevo con los dos caminos convergiendo en SKILL EN EJECUCION, pariente visual de las compuertas de 4.3 y 4.5. NIVEL DE CERTEZA DECLARADO: el camino explicito esta verificado de primera mano; el mecanismo de activacion semantica por description lo sostiene hoy solo el deck interno del equipo y no una fuente oficial de producto, asi que quedo marcado como pendiente de verificacion en Sources y en Speaker notes. ~2 min. La Seccion 4 paso a 5 laminas y se barrieron las referencias cruzadas (4.2->4.3, 4.3->4.4, 4.4->4.5, incluida la mencion dentro del ascii-note de Grabar una Skill).
  tags: [add-slide, slide-content, verification-pending]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "1. El loop completo de Faro" (Conclusions)
  feedback: "borrar este slide."
  resolution: Borrada y archivada entera en Cut material (Content, el bloque ascii con su ascii-note, Sources y Speaker notes) para poder reponerla tal cual. Conclusions quedo en dos laminas y el deck recupero ~5 min. El arrastre se limpio: las notes de "Lo que se llevan" abrian con "El loop de Faro que se acaba de ver..." y retomaban la pregunta que quedaba abierta ahi, asi que esa apertura se reescribio para llegar desde los Subagentes y la pregunta (que tarea de las que hacen todas las semanas le delegarian a un agente?) se replanteo dentro de la propia lamina antes de bajar la consigna. Tambien se reescribio la transicion de salida de 5.1 y se actualizaron el Narrative arc y las referencias cruzadas en Sources. Con esto el candidato de recorte historico "Conclusions.1 de 5 a 3 min" queda cerrado por via de la eliminacion.
  tags: [delete-slide, time-budget, transitions]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "3. Trabajar en .md, exportar al final" (Seccion 2), retitulada por el presentador a "Interar en .md"
  feedback: "El foco no es sobre trabajar sino como usar el .md para iterar. Revisar el contenido para que este alineado a esto."
  resolution: Lamina reenfocada de "donde se trabaja" a "donde se itera". Titulo corregido a "3. Iterar en .md, exportar al final" (el presentador lo habia dejado como "Interar", typo). El Content se reescribio entero alrededor del beat nuevo, que ahora abre con un lead destacado - con la IA nada sale bien a la primera y el trabajo son muchas vueltas sobre el mismo archivo - y sigue con: que es una vuelta (pedidos chicos y concretos sobre el archivo que ya existe, con tres ejemplos), por que la vuelta sale barata en .md (la IA reescribe el archivo entero sin romper nada porque ve la estructura directa; en .docx/.xlsx cada vuelta atraviesa capas de formato y se degrada), la regla de bolsillo reformulada de "se edita" a "se itera", y la entrega como paso unico al final. Salieron los dos bullets viejos que hablaban de trabajo en general ("interpreta, edita y crea mejor" y el de memoria + archivos de trabajo); lo de la memoria del agente sobrevive en las Speaker notes, que es donde no compite con el foco. El DIAGRAMA se rediseño: dejo de ser un flujo lineal de tres cajas y ahora la caja central lleva un bucle explicito con los tres pedidos de ejemplo dentro, retitulado "DONDE VIVE LA ITERACION"; el ascii-note se reescribio (intent/emphasize/labels) marcando el bucle como el corazon del diagrama y el contraste entre las MUCHAS vueltas del centro y la UNA entrada y UNA salida de los costados. Speaker notes reescritas en cinco parrafos, abriendo con el permiso explicito de que nada sale bien a la primera (el que espera el resultado perfecto en el primer prompt se frustra y abandona) y cargando el peso en el tramo del medio. Sources sin cambio: ninguna afirmacion nueva. Tiempo objetivo sin cambio (~4 min); el deck sigue en 58,0. Actualizados el Goal de la Seccion 2, el Narrative arc y las dos menciones del titulo viejo en Open questions y Cut material. NOTA PARA POLISH: el bloque ascii cambio, asi que el proximo pase lo re-renderiza (ya no reusa por digest).
  tags: [reframe, slide-content, diagram, speaker-notes]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "3. Los lee todos?" (Seccion 3), grupo "Tres reglas practicas"
  feedback: "tiene emoji. Removelos"
  resolution: Sacados los tres emoji de cabecera (carpeta, etiqueta, hoja) de los bullets "Subir lo que importa", "Nombres de archivo claros" y "PDFs escaneados". El texto quedo igual, y el patron de los tres bullets ahora coincide byte a byte con el del grupo de arriba de la misma lamina (negrita sin punto + frase), que nunca llevo emoji. Efecto colateral bienvenido: cerraba una anotacion vieja de Open questions que decia que en el render html los tres emoji se colapsaban a un unico glifo de nota, porque el icono de un bloque destacado lo fija su tipo y no se elige por item; sin emoji el problema desaparece en vez de quedar como limitacion del renderer. Verificado que no quedan otros emoji de simbolo en el resto del draft (los tres hits restantes son el signo de advertencia dentro de citas del corpus y de Open questions, no contenido proyectado).
  tags: [typography, slide-content, render]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "1. Que es una Skill" (Seccion 4)
  feedback: "Rehacer el contenido de que es un skill. El contenido debe definir en cards el que es un skill. Lo que existe ahora es confuso."
  resolution: Content rehecho de cero en formato de tarjetas. El diagnostico de la confusion: el primer bullet metia tres cosas distintas en una sola linea (que es una Skill, cuando se activa, y la regla de un trabajo por Skill), y el "cuando se activa" ademas ya no pertenece a esta lamina desde que se agrego la 4.2 "Como se usa una Skill". La lamina abre ahora con la frase ancla ("Todo lo que le explicas a Claude mas de una vez es una Skill que deberias escribir una vez") como lead, y baja a CUATRO tarjetas paralelas, cada una una idea sola: (1) Es un instructivo escrito - una tarea explicada en pasos, guardada en un archivo, en espanol y sin codigo; (2) Se ensena una vez - despues la tarea sale siempre igual, mismos pasos y mismo formato de salida; (3) Un trabajo por Skill - si al describirla aparece un "y ademas", son dos; (4) Queda disponible - vive en la lista de Habilidades y esta a mano en cualquier chat, no dentro de uno. Cierra con el ejemplo presentado como el hilo de toda la seccion (informe-mensual sobre notas/). El formato de las tarjetas replica el de los tres bullets de 3.3 (negrita sin punto + frase), que es lo que el render html-strict levanta como cards. Speaker notes reescritas para recorrer las cuatro tarjetas de a una, con la bajada de barrera explicita en la primera ("Skill" suena a programacion y no lo es) y una linea final que dice que esta lamina NO contesta como se dispara una Skill, a proposito, porque eso es la 4.2. Sources sin cambio: las dos entradas del corpus ya sostenian folder+SKILL.md, "one job per skill" y la frase ancla. Tiempo objetivo sin cambio (~4 min); el deck sigue en 58,0.
  tags: [rewrite, slide-content, cards, clarity]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "3. Crear una Skill desde el panel" (Seccion 4), diagrama del menu Agregar
  feedback: "Falta en el grafico es grabar"
  resolution: El diagrama mostraba solo tres entradas del menu Agregar y le faltaba la cuarta, "Graba tu pantalla". Entro como caja propia y, ya que estaba, se aprovecho para hacer explicita la distincion que la lamina venia enseniando solo de palabra: cada entrada lleva ahora una marca al costado, CREAR o IMPORTAR. Quedan tres caminos de creacion (Crear con Claude, Escribir las instrucciones, Grabar tu pantalla) y uno de importacion (Subir un ZIP), los cuatro desembocando en la misma compuerta de guardar/habilitar. El bullet del Content paso de "dos caminos para crear y uno para importar" a "tres caminos para crear y uno para importar". El ascii-note se reescribio entero (intent/emphasize/labels) sumando el corte crear-vs-importar como segundo foco despues de la compuerta. Speaker notes reescritas en cuatro parrafos, con la entrada de grabacion nombrada solo al pasar porque tiene lamina propia dos slides mas adelante (4.5). SOURCES: la cuarta entrada NO estaba sostenida por la verificacion de primera mano del 2026-07-21 (esa captura mostraba tres opciones), asi que se apoya en support.claude.com/12512198 re-verificada el 2026-07-31, que es la misma fuente de 4.5 y documenta la ruta Configuracion > Habilidades > Agregar > "Graba tu pantalla". Se agrego ademas una tercera entrada de Sources advirtiendo que images/skills-panel.png es del 21 de julio y puede no mostrar todavia esa entrada, con la instruccion de re-mirar el panel y resacar antes de la clase; el mismo cuidado quedo dicho en las notes por si el panel proyectado y el diagrama no coinciden. NOTA PARA POLISH: el bloque ascii de esta lamina es documentation-only (la lamina lleva captura), asi que el cambio no dispara render.
  tags: [diagram, slide-content, sources, verification-pending]
- talk: claude-cowork
  date: 2026-07-31
  location: Slide "1. Subagentes: varios trabajando a la vez" (Seccion 5)
  feedback: "Agregar un slide con cards de como se crea un subagente en cowork" (mas un briefing largo del presentador: no hay boton de crear subagente, son archivos Markdown con frontmatter YAML, y en Cowork el camino para que persistan es empaquetarlos en un plugin)
  resolution: Lamina nueva 5.2 "Armar un subagente propio". El pedido chocaba de entrada con una decision verificada del deck ("en Cowork los subagentes no se crean ni se configuran a mano, los coordina Claude por debajo, sin panel"), asi que se pregunto antes de escribir; el presentador respondio con el briefing completo, que RESUELVE la tension en vez de contradecir la decision: no hay panel (sigue siendo cierto) Y ademas un subagente es un archivo, asi que se puede armar uno propio. Las dos afirmaciones conviven y la lamina lo dice explicitamente. TODO VERIFICADO CONTRA FUENTE OFICIAL antes de escribir, no se tomo el briefing como fuente: code.claude.com/docs/en/sub-agents (2026-07-31) sostiene "Subagents are Markdown files with YAML frontmatter", que name y description son los DOS UNICOS campos obligatorios (el briefing no lo distinguia), que la description define "when Claude should delegate to this subagent", y "Each subagent runs in its own context window with a custom system prompt, specific tool access, and independent permissions"; code.claude.com/docs/en/plugins sostiene el manifiesto .claude-plugin/plugin.json y la carpeta agents/ EN LA RAIZ del plugin (la doc advierte explicitamente que agents/ no va adentro de .claude-plugin/); claude.com/docs/cowork/guide/plugins es la que ata todo a Cowork - "A plugin is a package that extends what Claude can do in Cowork. Installing one can add skills, MCP connectors, subagents, slash commands, or hooks in a single step". Estructura: lead ("En Cowork no hay un boton de crear subagente"), cuatro tarjetas (es un archivo .md; la description es el disparador; corre aparte con contexto propio; para que persista, un plugin), un bloque de ejemplo markdown con hint ascii-render documentation-only para que Polish no lo tome por diagrama, y una cita al pie que separa los dos casos que se confunden (los subagentes que Claude lanza solo para paralelizar NO requieren configuracion; esto es querer uno propio). El ejemplo se cambio del code-improver de la doc a "revisor-de-informes", que es el hilo generico del deck y no un caso de programacion. Las rutas .claude/agents/ y ~/.claude/agents/ NO entraron a la lamina porque son de Claude Code y no de Cowork: viven solo en las Speaker notes, por si preguntan. Notes de 5.1 ajustadas (ya no cierra la seccion, y la frase "si alguien pregunta por configurarlos, la respuesta honesta es que no se configuran a mano" se reemplazo por un reenvio a la lamina nueva); la transicion de cierre de la seccion se mudo a las notes de 5.2. Goal de la Seccion 5 y Narrative arc reescritos. PENDIENTE PARA EL PRESENTADOR: es la lamina mas tecnica del deck para una audiencia de management, marcada como opcional en el recorrido en Goal y notes; y suma 3 min, con lo que el deck pasa de 58,0 a 61,0 sobre un bloque de 60.
  tags: [add-slide, slide-content, cards, verified-web, time-budget, scope]

- date: 2026-08-01
  talk: claude-cowork
  location: slide 4.3
  feedback: "4.3 se tiene que remplazar por -> debe introducir que existe 3 formas de crear un skill. idealmente solo con cards con una summary de cada una"
  tags: [structure, slide-replace, visual-form]
  resolution: Lamina nueva "Tres formas de crear una Skill": lead de una linea + 3 tarjetas (desde el panel / desde el prompt / grabando la pantalla) + cierre en negrita sobre la compuerta de guardar-habilitar. Sin ASCII, sin imagen, sin tabla, por pedido explicito de "solo cards". La lamina anterior ("Antes de escribir una: el directorio") se archivo integra y verbatim en Cut material. En el FILL se clasifico card-row en vez del icon-list que dictaba el discriminador, justamente para honrar el pedido de tarjetas.

- date: 2026-08-01
  talk: claude-cowork
  location: slide 4.5
  feedback: "Metodo 2: Crear una Skill desde el prompt tiene que ser re-scrita explicando como desde el prompt se puede crear una."
  tags: [content-rewrite, accuracy, sources]
  resolution: Reescrita entera. La lamina mostraba el menu "+" del chat y la trampa del Save, o sea no ensenaba lo que decia su titulo. Ahora son 5 tarjetas numeradas con el flujo conversacional documentado - describir lo que se quiere, Claude pregunta por el proceso, subir materiales, Claude escribe el SKILL.md y empaqueta, probar y ver "Usando [nombre]" - mas el cierre en la compuerta. Fuente nueva verificada: claude.com/resources/tutorials/how-to-create-a-skill-with-claude-through-conversation. Se deja asentado que support 12512198 no documenta este camino. El material viejo, incluida la captura skills-menu-chat.png, se archivo en Cut material.

- date: 2026-08-01
  talk: claude-cowork
  location: slide 4.4
  feedback: "Rename Metodo 1: Crear una Skill desde el panel -> Metodo 1: Crear desde el panel"
  tags: [titles]
  resolution: Aplicado.

- date: 2026-08-01
  talk: claude-cowork
  location: slide 4.5
  feedback: "Metodo 2: Crear una Skill desde el prompt -> Rename Metodo 2: Crear desde el prompt"
  tags: [titles]
  resolution: Aplicado.

- date: 2026-08-01
  talk: claude-cowork
  location: slide 4.6
  feedback: "Metodo 3: Grabar una Skill -> Metodo 3: Crear grabando una skill una Skill."
  tags: [titles]
  resolution: Aplicado como "Metodo 3: Crear grabando una Skill", normalizando la repeticion de tipeo del pedido original. PENDIENTE DE CONFIRMAR con el presentador.
