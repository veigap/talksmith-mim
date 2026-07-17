# Feedback backlog

> Format spec, tagging vocabulary, and pattern-detection rules live in [`${CLAUDE_PLUGIN_ROOT}/schemas/feedback-backlog.md`](${CLAUDE_PLUGIN_ROOT}/schemas/feedback-backlog.md).

## Tagging vocabulary

Reuse existing tags before inventing new ones. In use: restructure, add-slide, add-visual, slide-content, sources, roadmap, positioning, compact, accuracy, too-dense, expand, too-vague, rewrite, bad-order, terminology, style, audience-address.

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
