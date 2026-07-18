# Feedback backlog

> Format spec, tagging vocabulary, and pattern-detection rules live in [`${CLAUDE_PLUGIN_ROOT}/schemas/feedback-backlog.md`](${CLAUDE_PLUGIN_ROOT}/schemas/feedback-backlog.md).

## Tagging vocabulary

Reuse existing tags before inventing new ones. In use: slop-pattern, accuracy, add-slide, add-visual, audience, audience-address, bad-order, compact, cut, expand, merge-incorporation, positioning, redundancy, restructure, rewrite, roadmap, slide-content, sources, split, style, terminology, too-dense, too-vague, visual.

## Entries

<!-- Editor appends entries below this line. -->
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
