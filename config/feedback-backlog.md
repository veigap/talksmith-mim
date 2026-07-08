# Feedback backlog

> Format spec, tagging vocabulary, and pattern-detection rules live in [`${CLAUDE_PLUGIN_ROOT}/schemas/feedback-backlog.md`](${CLAUDE_PLUGIN_ROOT}/schemas/feedback-backlog.md).

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
