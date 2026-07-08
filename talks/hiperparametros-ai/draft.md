---
presentation: Inteligencia Artificial: de lo conceptual a lo práctico — Master in Management (MiM), IAE Business School, Universidad Austral
class: "Parámetros críticos en AI: las perillas que cambian la respuesta"
research: research/corpus/
description: Slides are grouped into Sections. Each Section contains one or more Slides.
presenter: Paulo Veiga, Profesor, IAE Business School
audience: Profesionales de negocios del Master in Management (MiM), sin formación técnica en AI. Les interesa el impacto conceptual y práctico de la AI en la gestión y la toma de decisiones, no la matemática ni el detalle de ingeniería.
duration: 2 horas (con pausa intermedia y espacio de preguntas)
date: 2026-07-07
---

# Thesis

**Claim:** La misma pregunta, hecha al mismo modelo de AI, puede dar respuestas distintas — más creativas o más precisas, más caras o más baratas, más largas o más cortas — dependiendo de un puñado de "perillas" que casi nadie ve, pero que un profesional de negocios necesita entender para elegir, comprar y usar herramientas de AI con criterio.

**Why it matters:** Cuando una empresa integra AI en un proceso (atención al cliente, análisis de contratos, generación de reportes), estas perillas determinan la calidad, el costo, la velocidad y la consistencia de los resultados — y por lo tanto el ROI. No hay que saber la matemática, pero sí saber *qué palanca cambia qué*, para no comprar humo, no pagar de más, y no confundir "el modelo se equivocó" con "estaba mal configurado".

**Presenter feedback:**

---

# Agenda

**Narrative arc:** Abrimos con un hook concreto — la misma pregunta, dos respuestas distintas — para instalar la idea de que hay perillas ocultas. Damos un mapa mental mínimo de cómo un modelo genera texto (sin matemática), suficiente para entender qué toca cada perilla. Después separamos las perillas de inferencia que el usuario/negocio *sí puede tocar* al usar herramientas y APIs en dos bloques con su propia lógica de negocio: primero **cómo elige las palabras** —el control de aleatoriedad/variedad— con temperatura y top-p (consistencia vs. creatividad); luego **cuánto piensa** —el control del esfuerzo de razonamiento— con Thinking / Deep Thinking (calidad vs. costo y velocidad), cerrando ese bloque con una tabla de bolsillo que recapitula las tres perillas tocables. Luego damos su propio lugar a la decisión más cotidiana y consecuente que casi todos tocan —**qué modelo elegir**— porque es la única perilla siempre expuesta hasta en el chat web y la que fija el eje capacidad vs. costo/velocidad. Cerramos subiendo un nivel a dos parámetros que se deciden *al construir el modelo* y que el negocio no toca pero sí *compra* (tamaño del modelo bajo el capó, learning rate), para entender qué hay detrás de "un modelo más grande" o "más caro", y recapitulamos la idea rectora: no hay configuración universalmente buena, hay una apropiada a cada tarea.

**Sections (in delivery order):**

- 1. Por qué la misma pregunta da respuestas distintas
- 2. Cómo genera un modelo (sin matemática)
- 3. Cómo elige las palabras (temperatura y top-p)
- 4. Cuánto piensa (razonamiento y recapitulación)
- 5. Selección del modelo
- 6. Lo que se decide al construir el modelo

**Presenter feedback:**

- [closed] 2026-07-07 — "También la selección del modelo como un item top level de la agenda."
  Resolution: Nueva Sección 4 top-level 'Selección del modelo' (Slide 4.1 'Elegir el modelo: la perilla que todos tocan'): perilla más consecuente y única siempre expuesta en chat web (Tabla 1 del corpus); eje capacidad vs costo/velocidad entre niveles grande/flagship vs mini/rápido; regla 'el más chico/rápido que resuelva bien la tarea'; ASCII capacidad-vs-costo con ascii-note. Reconciliado el ex-Slide 4.2 'Tamaño del modelo' (ahora Sección 5, Slide 5.2 'Tamaño del modelo: qué es grande por dentro'): se quitó el ángulo de selección/capacidad-vs-costo (movido a Sección 4) y quedó solo el marco conceptual de qué son los parámetros por dentro. Agenda (arco+lista, ahora 5 secciones), Conclusions (framing reordenado a modelo→3 perillas→2 comprados) y Open questions renumerados/reconciliados.
- [closed] 2026-07-07 — "Dividir la Sección 3 'Perillas que SÍ tocás' en dos secciones top-level: una sobre el control de aleatoriedad/variedad (temperatura, top-p) y otra sobre el control del razonamiento (Thinking / Deep Thinking), con el slide 'Resumen: qué perilla para qué' como cierre del segundo bloque. Retitular con nombres audience-friendly y paralelos al resto; agregar goal por sección; renumerar todas las secciones y slides secuencialmente y reconciliar Agenda, Conclusions, Open questions y cross-refs."
  Resolution: La ex-Sección 3 "Perillas que SÍ tocás" (4 slides) se partió en dos secciones top-level: **Sección 3 "Cómo elige las palabras"** (control de aleatoriedad/variedad) con Slide 3.1 Temperatura y Slide 3.2 Top-p; y **Sección 4 "Cuánto piensa"** (control del razonamiento) con Slide 4.1 Razonamiento: Thinking / Deep Thinking y Slide 4.2 Resumen: qué perilla para qué (la tabla de bolsillo recapitula las tres perillas tocables, así que cierra el segundo bloque como recap conjunto). Goals nuevos por sección, paralelos en estilo al resto. Renumeración en cascada: ex-Sección 4 "Selección del modelo" → Sección 5; ex-Sección 5 "Lo que se decide al construir" → Sección 6 (slides 6.1/6.2/6.3). Reconciliados: Agenda (arco narrativo reescrito para nombrar los dos bloques; lista de secciones 5→6), Conclusions (sin cambios de numeración de contenido; refs a "las tres perillas de inferencia" intactas), Open questions (refs "Sección 5"→"Sección 6", "Sección 4"→"Sección 5", entregable = tabla de bolsillo ahora Slide 4.2), y cross-refs internos (goals y speaker notes que decían "Sección 3/4/5" actualizados). Contenido de slides preservado verbatim — regrupación, no reescritura.

---

# 1. Por qué dan respuestas distintas

**Goal of this section:** Instalar, con un ejemplo concreto y sin jerga, la idea central de la clase: detrás de toda herramienta de AI hay parámetros configurables que cambian el resultado, y entenderlos es una competencia de gestión, no de ingeniería.

**Presenter feedback:**

---

## 1. La misma pregunta, dos respuestas

### Content

- Hook: le hago la misma pregunta a la misma AI dos veces y obtengo dos respuestas distintas. ¿Se equivocó? ¿Está "pensando" distinto?
- No: hay perillas de configuración que deciden cuánta variedad, cuánto detalle y cuánto costo tiene cada respuesta.
- Ejemplo de negocio: un asistente que redacta emails a clientes. ¿Querés que suene siempre igual (marca consistente) o que proponga variantes creativas? Esa decisión es una perilla.

```ascii
   Misma pregunta  ---> [  AI  ] ---> "Respuesta A"
   Misma pregunta  ---> [  AI  ] ---> "Respuesta B (distinta)"
                          ^
                          |
                   perillas ocultas
                   (config del modelo)
```
<!-- ascii-note:
intent: mostrar que la misma entrada produce salidas distintas por culpa de parámetros ocultos, no por error del modelo
emphasize: la caja "perillas ocultas" apuntando al modelo; el contraste Respuesta A vs B
labels: "Misma pregunta", "AI", "Respuesta A", "Respuesta B (distinta)", "perillas ocultas (config del modelo)"
-->

### Sources

- research/corpus/parametros-llm.md.md (temperature como palanca principal de aleatoriedad; el chat web oculta estas perillas con defaults internos)

### Speaker notes

Arranco haciendo, en vivo si se puede, la misma pregunta dos veces en un chat y mostrando que cambia. Pregunto a la sala: "¿la AI se equivocó?". La respuesta intuitiva es sí; la respuesta correcta es que hay una perilla de aleatoriedad activada por defecto. Ese es el gancho de toda la clase: lo que parece magia o error muchas veces es configuración. No entro en ningún detalle técnico todavía — solo instalo la pregunta. Cierro con el ejemplo del asistente de emails para que vean que esto no es curiosidad de laboratorio: es una decisión de producto y de marca.

### Presenter feedback

---

## 2. Esto es gestión, no ingeniería

### Content

- No van a tunear modelos. Van a *elegir, comprar y supervisar* herramientas que otros configuran.
- Saber qué perilla cambia qué = poder pedir lo correcto, entender una factura, y diagnosticar cuando algo falla.
- Tres preguntas de negocio que estas perillas responden: ¿es consistente? ¿cuánto cuesta? ¿es suficientemente bueno para esta tarea?

### Sources

- research/corpus/parametros-llm.md.md (en los chats web casi no se expone nada; en la API de desarrolladores se expone todo — dos audiencias distintas)

### Speaker notes

Aclaro el contrato de la clase: no vamos a hacer matemática ni van a programar. Lo que quiero es que salgan pudiendo tener una conversación inteligente con un proveedor de AI, leer una propuesta técnica sin asustarse, y entender por qué dos herramientas que "hacen lo mismo" cuestan y rinden distinto. Enmarco las tres preguntas de negocio (consistencia, costo, calidad) porque van a ser el hilo con el que evaluemos cada perilla en las Secciones 3, 4 y 5. Menciono que la mayoría de estas perillas están escondidas en el chat web y solo aparecen cuando una empresa integra la AI vía API — que es exactamente el contexto en que ellos las van a encontrar.

### Presenter feedback

---

# 2. Cómo genera el modelo

**Goal of this section:** Dar el modelo mental mínimo — sin fórmulas — de cómo un LLM produce texto palabra por palabra, para que las perillas de las Secciones 3 y 4 tengan dónde "engancharse". Es andamiaje conceptual, no una clase de ingeniería.

**Presenter feedback:**

---

## 1. Predecir la próxima palabra

### Content

- Un modelo de lenguaje hace una sola cosa, muchas veces: predecir la siguiente palabra (token).
- Para cada paso arma una lista de candidatos con un "puntaje de confianza" para cada uno.
- Genera una palabra, la agrega al texto, y vuelve a empezar mirando todo lo que lleva escrito.

```ascii
  "El cielo es ___"

   candidato   confianza
   ---------   ---------
   azul        ####### alta
   gris        ###
   infinito    ##
   verde       #

   -> elige uno -> lo agrega -> repite
```
<!-- ascii-note:
intent: mostrar que en cada paso el modelo produce una lista de candidatos con niveles de confianza y elige uno
emphasize: que "azul" tiene la barra más alta pero no es el único candidato; el ciclo "elige -> agrega -> repite"
labels: frase incompleta "El cielo es ___", columnas "candidato" y "confianza", barras de confianza
-->

### Sources

- research/corpus/parametros-llm.md.md (logits = puntajes crudos por token candidato; el modelo genera token a token; pipeline logits → sampler → token)

### Speaker notes

Este es el único concepto técnico que necesitan retener de toda la clase, y lo doy sin una sola fórmula. Un LLM predice la próxima palabra. Punto. Para hacerlo, en cada paso arma una lista corta de palabras posibles y les pone un puntaje de confianza — uso deliberadamente "confianza" en lugar de "logits" o "probabilidad" para no cargar la cabeza. La clave que quiero que se lleven: el modelo no tiene *una* respuesta, tiene una *lista rankeada* de opciones. Todo lo que hacen las perillas de las Secciones 3 y 4 es intervenir en esa lista: cuánto respetarla, cuánto cortarla, cuánto pensar antes de elegir. Si entienden "lista de candidatos con confianza", entienden todo lo que sigue.

### Presenter feedback

---

## 2. Elegir no es siempre el más probable

### Content

- El modelo no siempre agarra el candidato #1. A veces "tira los dados" entre los mejores.
- Esa elección con algo de azar es lo que hace que la misma pregunta dé respuestas distintas (Sección 1).
- Analogía: no siempre pedís el plato más popular del menú; a veces variás entre los tres primeros.

```ascii
  Candidatos ordenados por confianza:

   azul   [==============]  <- más probable
   gris   [=====]
   claro  [===]
          \______ ruleta ponderada ______/
             el azar cae en una porción
             (proporcional a la confianza)
```
<!-- ascii-note:
intent: mostrar que la selección final es un sorteo ponderado por confianza, no siempre el candidato top
emphasize: la idea de "ruleta ponderada" donde cada candidato ocupa una tajada proporcional a su confianza
labels: candidatos "azul/gris/claro" con barras, etiqueta "ruleta ponderada", "el azar cae en una porción"
-->

### Sources

- research/corpus/parametros-llm.md.md (la temperatura NO selecciona el token; la selección la hace el sampler vía muestreo aleatorio ponderado, "ruleta" con CDF; ejemplo A=0.48/B=0.29/C=0.23)

### Speaker notes

Acá cierro el círculo con el hook de la Sección 1. La razón por la que la misma pregunta da respuestas distintas es que el paso de "elegir" tiene un componente de azar: es una ruleta donde cada candidato ocupa una tajada proporcional a su confianza. El más probable gana más seguido, pero no siempre. Uso la analogía del menú: no siempre pedís lo más popular, a veces variás entre los tres primeros platos. Esto prepara el terreno para la temperatura, que es literalmente la perilla que decide *cuánto* azar hay en esa ruleta. No menciono "sampler" ni "softmax"; me quedo con "ruleta ponderada por confianza".

### Presenter feedback

---

# 3. Cómo elige las palabras

**Goal of this section:** Recorrer las dos perillas con las que un negocio controla la *aleatoriedad/variedad* de la respuesta al usar herramientas y APIs — temperatura y top-p — traducidas a su impacto de negocio: consistencia vs. creatividad. Es la primera mitad del corazón práctico de la clase (la segunda —cuánto piensa el modelo— viene en la Sección 4).

**Presenter feedback:**

---

## 1. Temperatura: creatividad vs. consistencia

### Content

- La temperatura regula *cuánto azar* hay en la ruleta de la palabra anterior.
- Baja (≈0): casi siempre el candidato más probable → respuestas predecibles, repetibles, "aburridas pero seguras".
- Alta (≈0.8–1.2): más variedad → respuestas creativas, pero más riesgo de incoherencia o error.
- Negocio: baja para extracción de datos, clasificación, respuestas de compliance; alta para brainstorming, copy, ideas.

```ascii
  TEMPERATURA BAJA (~0)          TEMPERATURA ALTA (~1)
  azul  [============]           azul  [======]
  gris  [=]                      gris  [=====]
  claro [ ]                      claro [====]
  -> casi siempre "azul"         -> puede salir cualquiera
  PREDECIBLE / CONSISTENTE       VARIADO / CREATIVO
```
<!-- ascii-note:
intent: contrastar cómo la temperatura baja concentra la elección en el top y la alta aplana la distribución
emphasize: el antes/después; baja = una barra domina, alta = barras parejas; las etiquetas PREDECIBLE vs CREATIVO
labels: dos paneles "TEMPERATURA BAJA (~0)" y "TEMPERATURA ALTA (~1)", barras por candidato, etiquetas de resultado
-->

### Sources

- research/corpus/parametros-llm.md.md (temperature es la palanca principal de aleatoriedad; 0 = casi determinista, 0.8–1.2 = más variedad; ejemplo numérico logits [2.0,1.0,0.5])

### Speaker notes

Primera perilla y la más importante. Explico temperatura como "el volumen del azar". Bajo el volumen (temperatura baja): el modelo casi siempre elige el candidato más confiable; ideal cuando quiero consistencia y control — extraer datos de una factura, clasificar tickets, responder algo de compliance donde no quiero sorpresas. Subo el volumen: el modelo se anima a candidatos menos obvios; ideal para brainstorming, generar variantes de copy, nombres de producto. El mensaje de negocio: no hay una temperatura "buena"; hay una temperatura *apropiada a la tarea*. Uso las dos barras del diagrama para mostrar visualmente cómo la distribución se aplana. Aviso: los valores exactos (0, 1, 1.2) son referencias típicas, no números mágicos, y cambian según la herramienta.

### Presenter feedback

---

## 2. Top-p: la otra forma de dar variedad

### Content

- Top-p (o "nucleus") es una perilla alternativa a la temperatura: en vez de subir el azar, *recorta la lista* de candidatos.
- Top-p = 0.9 → el modelo solo considera los candidatos que juntos suman el 90% de la confianza, y descarta la "cola" improbable.
- Regla práctica clave: se toca *una u otra*, no las dos a la vez — combinarlas suele ser contraproducente.
- Negocio: mismo eje que la temperatura (variedad vs. control); en la práctica muchos equipos ajustan solo una.
- Ojo: en los **modelos de razonamiento** (los que "piensan" antes de responder) varios proveedores **deshabilitan** estas perillas — el modelo fija temperatura y top-p internamente y no las podés tocar.

```ascii
  Lista completa de candidatos (por confianza):
   azul  gris  claro  celeste  turquesa  ...cola larga...

  top_p = 0.9  ->  |<-- se queda con esto -->|  x x x x
                     (los que suman 90%)       descarta la cola
```
<!-- ascii-note:
intent: mostrar que top-p recorta la cola larga de candidatos improbables, quedándose con el núcleo que suma p
emphasize: la frontera del corte al 90%; la "cola larga" descartada con equis
labels: fila de candidatos ordenados, "top_p = 0.9", "se queda con esto (los que suman 90%)", "descarta la cola"
-->

**Disponibilidad de top-p por proveedor** (verificar contra la doc vigente de cada proveedor):

| Proveedor | top-p en la API | En modelos de razonamiento |
|---|---|---|
| OpenAI (GPT) | Sí | Deshabilitado (queda fijo) |
| Anthropic (Claude) | Sí — se ajusta temperatura *o* top-p, no ambos | Deshabilitado con *extended thinking* |
| Google (Gemini) | Sí (`topP`) | Disponible |

### Sources

- research/corpus/parametros-llm.md.md (top_p nucleus sampling, 0.9 típico; se usa EN LUGAR DE temperature, no en conjunto; regla general de Claude: alterar temperature o top_p, no ambos)
- research/corpus/parametros-llm.md.md (RL/RLHF: por qué se deshabilita el sampling —temperatura/top-p— en modelos de razonamiento) — respalda la columna "modelos de razonamiento".
- Disponibilidad exacta por proveedor/modelo: conocimiento de dominio del presenter, **a verificar** contra la doc vigente — los nombres y defaults por modelo NO están verificados en el corpus.

### Speaker notes

Segunda perilla, y la presento como "la prima de la temperatura". Persigue el mismo objetivo — controlar variedad — pero con otro mecanismo: en vez de subir el azar, recorta la lista de candidatos y descarta la cola de opciones raras. Top-p 0.9 significa "quedate con las opciones que entre todas suman el 90% de la confianza". El punto de negocio más accionable de este slide: se ajusta *una u otra*, temperatura o top-p, nunca las dos juntas — es un error común que degrada resultados. Para la audiencia de negocios, el takeaway es: si un proveedor te habla de "top-p", es la misma decisión de variedad-vs-control que ya entendiste con temperatura. No necesito que sepan la mecánica fina; necesito que no se asusten cuando la vean. Cierro con una aclaración importante: en los modelos de razonamiento varios proveedores bloquean estas perillas (las fijan internamente); dejo la tabla de disponibilidad por proveedor como referencia, aclarando que hay que verificarla contra la doc vigente porque cambia seguido.

### Presenter feedback

---

# 4. Cuánto piensa

**Goal of this section:** Recorrer la perilla con la que un negocio controla *cuánto razona* el modelo antes de responder — el esfuerzo de razonamiento (Thinking / Deep Thinking) — traducida a su impacto de negocio: calidad vs. costo y velocidad; y cerrar con una tabla de bolsillo que recapitula las tres perillas tocables (temperatura, top-p y razonamiento). Es la segunda mitad del corazón práctico de la clase.

**Presenter feedback:**

---

## 1. Razonamiento: Thinking / Deep Thinking

### Content

- Perilla nueva y muy actual, hoy expuesta de frente al usuario: cuánto *razona* el modelo internamente antes de contestar. Las herramientas la exponen, cada vez más, como **modos con nombre**.
- Pensala como una progresión de tres escalones, no un interruptor de sí/no:
  - **Respuesta directa** (sin pensar): el modelo contesta al toque. Rápido y barato; es el default para tareas simples (una búsqueda, un formateo, una pregunta trivial).
  - **"Thinking"** (pensar): el modelo razona un poco antes de responder. Buen equilibrio para la mayoría de las tareas no triviales; agrega algo de latencia y costo.
  - **"Deep Thinking"** (pensar profundo / *extended thinking*): el modelo razona mucho más. Es lo mejor para tareas difíciles, de varios pasos o analíticas; notablemente más lento y más caro (pagás también el razonamiento interno que no ves).
- Cómo aparece según la herramienta (en términos generales, sin defaults por versión): varias ya ofrecen un botón o modo de "Thinking" y uno de "Deep Thinking" / *extended thinking*; otras te dejan graduar el esfuerzo por niveles o asignar un **presupuesto de pensamiento** (tokens de razonamiento). Los nombres exactos y los defaults cambian seguido entre proveedores.
- Trade-off de negocio: subir de escalón mejora la calidad en tareas difíciles, pero **calidad, latencia y costo suben juntos**. No hay modo "bueno": hay uno *apropiado a la dificultad de la tarea*.
- Guía práctica: **emparejá el modo con la dificultad**. Tarea simple → respuesta directa. Tarea no trivial del día a día → Thinking. Análisis, planificación o problema multi-paso → Deep Thinking. Pensar de más en una tarea fácil es tirar plata (y a veces empeora la respuesta).

```ascii
  RESPUESTA DIRECTA  -->   THINKING          -->   DEEP THINKING
  (sin pensar)             (pensar)                (pensar profundo)

  + rápido                 razona un poco          razona mucho más
  + barato                 buen balance            mejor en tareas difíciles
  tareas simples           tareas no triviales     análisis / multi-paso

  calidad  ------------------------------------------->  sube
  latencia ------------------------------------------->  sube
  costo    ------------------------------------------->  sube

  Regla: emparejá el modo con la dificultad de la tarea
```
<!-- ascii-note:
intent: mostrar la progresión de tres niveles de razonamiento como los exponen las herramientas — respuesta directa (rápido/barato, tareas simples) → Thinking (razonamiento moderado, balance) → Deep Thinking (razonamiento profundo, mejor en tareas difíciles pero más lento/caro)
emphasize: la progresión de izquierda a derecha (directa → Thinking → Deep Thinking) y cómo calidad, latencia y costo suben juntos; la regla de ajustar el modo a la dificultad
labels: "RESPUESTA DIRECTA (sin pensar)", "THINKING (pensar)", "DEEP THINKING (pensar profundo)", ejes calidad ↑ / latencia ↑ / costo ↑, la regla de cierre
-->

### Sources

- research/corpus/parametros-llm.md.md (sección "Razonamiento": thinking / extended thinking = razonamiento interno del modelo antes de la respuesta final; reasoning_effort por niveles y presupuesto de thinking como formas de graduarlo; trade-off directo calidad ↔ latencia ↔ costo; los tokens de razonamiento se facturan aunque no se vean; más razonamiento no siempre es mejor —"overthinking" en tareas fáciles—; analogía "¿que piense 5 segundos o 5 minutos?").
- Nota: los defaults y nombres de versión por modelo (GPT-5.x, Claude 4.7/4.8, niveles UI exactos) que menciona el corpus están marcados como NO verificados; este slide habla en términos generales — describe los modos "Thinking" / "Deep Thinking" como los rotulan las herramientas y la progresión respuesta directa → Thinking → Deep Thinking, sin atribuir un modo o default concreto a un modelo o versión específico.

### Speaker notes

Tercera perilla tocable, y la más "de hoy". Hasta hace poco esto vivía escondido en la API; ahora aparece de frente en las herramientas que usan todos los días, con nombres propios: "Thinking" (pensar) y "Deep Thinking" (pensar profundo / extended thinking). La lámina la presento como una progresión de tres escalones, no un interruptor: respuesta directa → Thinking → Deep Thinking. (1) Respuesta directa: el modelo contesta al toque, rápido y barato, es el default para lo simple. (2) Thinking: razona un poco antes de contestar, buen equilibrio para la mayoría de las tareas no triviales del día a día. (3) Deep Thinking: razona mucho más, es lo mejor para análisis, planificación y problemas de varios pasos. La idea de negocio es simple: podés graduar cuánto "piensa" el modelo. Uso la analogía del corpus: "¿que piense 5 segundos o 5 minutos?". El trade-off hay que decirlo claro y es el corazón del slide: al subir de escalón, calidad, latencia y costo suben JUNTOS —y sí, pagás también los tokens de pensamiento internos aunque no los veas—. Para una búsqueda rápida o formatear un texto, ir a Deep Thinking es tirar plata; incluso puede empeorar la respuesta por "sobre-pensar". El mensaje, igual que con temperatura: no hay un modo "bueno", hay uno *apropiado a la dificultad de la tarea* — emparejá el modo con la tarea. Importante para no quedar mal: NO atribuyo un modo o default concreto a un modelo/versión puntual (el corpus los marca como no verificados); hablo de los modos "Thinking" / "Deep Thinking" como los rotulan las herramientas y de la progresión en general, diciendo que los nombres exactos cambian entre proveedores.

### Presenter feedback

- [closed] 2026-07-07 — "El slide de razonamiento (3.3) debe encuadrarse explícitamente alrededor de los dos modos user-facing como los rotulan las herramientas: 'Thinking' vs 'Deep Thinking', manteniendo un baseline 'sin pensar / respuesta directa' como default rápido; título con 'Thinking / Deep Thinking'; conservar el trade-off calidad↔latencia↔costo, la guía práctica, la fuente al corpus y las speaker notes; actualizar el diagrama ASCII (y su ascii-note) a la progresión respuesta directa → Thinking → Deep Thinking; no presentar defaults por versión no verificados como hecho. Reflejar también la fila de razonamiento en la tabla de bolsillo (3.4)."
  Resolution: Slide 3.3 retitulado "Razonamiento: Thinking / Deep Thinking"; Content reescrito como progresión de tres escalones (respuesta directa → Thinking → Deep Thinking) con nombres de producto en inglés y prosa de negocio en español; trade-off ahora explícito como "calidad, latencia y costo suben juntos" al subir de escalón; guía práctica reescrita a "emparejá el modo con la dificultad"; ASCII y ascii-note actualizados a la progresión de tres pasos con ejes calidad/latencia/costo; Sources y speaker notes adaptados manteniendo la cita al corpus (sección "Razonamiento") y hablando en términos generales (sin defaults por versión). Fila de razonamiento en la tabla de bolsillo de 3.4 actualizada al framing Thinking / Deep Thinking.

---

## 2. Resumen: qué perilla para qué

### Content

- Tabla de bolsillo de las tres perillas tocables y su impacto de negocio.

| Perilla | Qué controla | Subir | Bajar |
|---|---|---|---|
| Temperatura | Variedad / azar | Más creativo, menos consistente | Más predecible, ideal control |
| Top-p | Variedad (alternativa) | Más opciones consideradas | Solo lo más seguro |
| Razonamiento (Thinking / Deep Thinking) | Cuánto "piensa" antes de responder | Deep Thinking: mejor en tareas difíciles, más lento y caro | Respuesta directa / Thinking: más rápido y barato, ok para tareas simples |

- Regla de oro: elegí la perilla por la *tarea*, no por defecto. Y recordá: temperatura y top-p se ajustan *una u otra*, no las dos a la vez.

### Sources

- research/corpus/parametros-llm.md.md (síntesis de temperature, top_p y razonamiento / reasoning_effort)

### Speaker notes

Slide de consolidación de las dos secciones de perillas tocables (3 "Cómo elige las palabras" y 4 "Cuánto piensa"). No lo leo entero — lo dejo como tabla de referencia y camino sobre las columnas de "subir/bajar" recordando el ejemplo de negocio de cada perilla. El cierre conceptual: estas perillas se ajustan por *tarea*, no hay un preset universal. Un mismo equipo puede tener temperatura baja para su bot de soporte y alta para su generador de campañas, y esfuerzo de razonamiento alto para el análisis jurídico y bajo para el FAQ. Esta tabla es la que les digo que fotografíen; es el entregable práctico de la primera mitad de la clase (las tres perillas tocables). Buen punto para la pausa intermedia de la clase de 2 horas.

### Presenter feedback

---

# 5. Selección del modelo

**Goal of this section:** Dar su propio lugar a la decisión que casi todos los usuarios efectivamente tocan —*qué modelo elegir*— porque es la única perilla siempre expuesta hasta en el chat web, la primera que enfrenta un negocio, y la que fija de entrada el eje capacidad vs. costo/velocidad. El takeaway de gestión: no siempre querés el más grande; querés el más chico/rápido que resuelva bien la tarea.

**Presenter feedback:**

---

## 1. Elegir el modelo: la perilla que todos tocan

### Content

- Elegir el modelo es la primera y más consecuente "perilla" que casi todos tocan de verdad: es lo único que se elige explícitamente hasta en el chat web (donde temperatura, top-p y el resto vienen con defaults ocultos).
- El trade-off central: modelos más capaces (el "grande"/*flagship*) dan mejor calidad pero suelen ser más lentos y más caros por consulta; modelos más chicos/rápidos (el "mini") son más baratos y ágiles, y muchas veces alcanzan de sobra.
- Las herramientas suelen ofrecer, en términos generales, un modelo *grande / flagship* (máxima capacidad) y uno *mini / rápido* (económico y veloz), a veces con escalones intermedios. Hablamos de familias/niveles, no de nombres o defaults de versión puntuales (esos cambian seguido entre proveedores).
- Guía práctica: **el más chico/rápido que resuelva bien la tarea.** Empezá por el mini; subí al grande sólo si la calidad no alcanza.
- Ojo: al elegir el modelo estás fijando implícitamente muchas cosas que *no* controlás directamente — su tamaño, con qué y cómo fue entrenado. Elegir el modelo es elegir todo ese paquete de una (lo vemos por dentro en la Sección 6).

```ascii
  CAPACIDAD  ^
  (calidad)  |                      * GRANDE / flagship
             |                        (mejor calidad,
             |                         más lento y caro)
             |            * intermedio
             |
             |   * MINI / rápido
             |     (más barato y ágil,
             |      suele alcanzar)
             +-------------------------------->
                        COSTO / LATENCIA por consulta

  Regla: el más chico/rápido que resuelva BIEN la tarea
```
<!-- ascii-note:
intent: mostrar el eje capacidad vs costo/latencia entre niveles de modelo (mini rápido → intermedio → grande/flagship), y que la elección óptima no es "el más grande" sino el más chico que resuelva bien la tarea
emphasize: la diagonal ascendente (más capacidad cuesta más costo/latencia); el contraste MINI vs GRANDE; la regla de cierre
labels: eje Y "CAPACIDAD (calidad)", eje X "COSTO / LATENCIA por consulta", puntos "MINI / rápido", "intermedio", "GRANDE / flagship", regla de cierre
-->

### Sources

- research/corpus/parametros-llm.md.md (Tabla 1: la selección de modelo es lo ÚNICO siempre expuesto en todos los chats web —claude.ai, ChatGPT, Gemini—; temperatura y el resto vienen con defaults internos) — respalda que la selección de modelo es la única perilla siempre expuesta al usuario.
- Conocimiento de dominio del presenter — no respaldado por el corpus. El eje capacidad-vs-costo/velocidad entre niveles de modelo (grande/flagship vs mini/rápido) y la regla "el más chico que alcance" es conocimiento de dominio del presenter; el corpus no lo trata explícitamente. Los nombres y defaults de versión por proveedor NO están verificados y no se citan como hecho.

### Speaker notes

Esta es, en la práctica, la perilla número uno: la única que todos tocan, hasta en el chat web, donde el resto está escondido con defaults. Por eso le doy sección propia. El mensaje de negocio es idéntico en espíritu al de la temperatura: no hay un modelo "bueno", hay uno apropiado a la tarea. Desactivo la intuición "más grande = mejor siempre": el grande (flagship) es más capaz pero más lento y más caro por consulta; el mini es más barato y ágil y muchas veces alcanza de sobra —sobre todo en tareas simples y de alto volumen (un bot que responde 100.000 veces por día algo trivial no necesita el flagship)—. La guía es una sola frase que quiero que se lleven: "el más chico/rápido que resuelva bien la tarea"; empezá por el mini y subí sólo si la calidad no da. Hablo de niveles (grande/flagship vs mini/rápido) a propósito, sin atribuir un nombre o default a un modelo puntual, porque esos cambian seguido y el corpus los marca como no verificados. Y dejo sembrada la idea de que elegir el modelo fija de una muchas cosas que no controlás —su tamaño, su entrenamiento—: eso es lo que abrimos en la Sección 6.

### Presenter feedback

---

# 6. Lo que se decide al construir

**Goal of this section:** Subir un nivel de abstracción a lo que queda fijado cuando elegís un modelo pero el negocio NO toca directamente — qué significa el *tamaño* del modelo bajo el capó (cantidad de parámetros) y el learning rate — para que entiendan qué hay detrás de "un modelo más grande" o "más caro de entrenar", y por qué eso les importa como compradores. (La *elección* entre modelos ya se trató en la Sección 5; acá miramos qué hay adentro.)

**Presenter feedback:**

---

## 1. Dos momentos: entrenar vs. usar

### Content

- Las perillas de las Secciones 3 y 4 se tocan al *usar* el modelo (inferencia). Estas dos se deciden al *construirlo* (entrenamiento).
- Por eso las vemos a nivel conceptual: para entender qué comprás, no para tunearlas.

```ascii
   ENTRENAMIENTO (una vez, caro)     USO / INFERENCIA (cada consulta)
   +--------------------------+      +---------------------------+
   | tamaño del modelo        |      | temperatura, top-p,       |
   | learning rate            | ==>  | tokens máx., contexto     |
   +--------------------------+      +---------------------------+
   lo decide quien lo construye      lo tocás vos al usarlo
```
<!-- ascii-note:
intent: separar los dos momentos del ciclo de vida — parámetros de entrenamiento (fijos, del constructor) vs de inferencia (tocables por el usuario)
emphasize: la flecha del entrenamiento hacia el uso; qué caja controla el negocio y cuál el proveedor
labels: dos cajas "ENTRENAMIENTO (una vez, caro)" y "USO / INFERENCIA (cada consulta)", contenido de cada una
-->

### Sources

- research/corpus/parametros-llm.md.md (distinción implícita entrenamiento vs inferencia; los parámetros de sampling se setean afuera al usar el modelo)

### Speaker notes

Bisagra de la clase. Hasta acá vimos perillas que se tocan cada vez que usás la AI. Ahora subo un escalón: hay decisiones que se toman *una sola vez*, cuando se construye el modelo, y que ya vienen "horneadas" en lo que comprás. El negocio no entrena modelos de cero — es carísimo — pero sí elige entre modelos que difieren en estas decisiones, y las paga. Por eso trato tamaño y learning rate a nivel conceptual: no para que los ajusten, sino para que entiendan qué significa "un modelo más grande" o "más caro" cuando un proveedor se los ofrece. El diagrama de dos cajas ancla la distinción entrenamiento-vs-uso que van a necesitar para el resto de la sección.

### Presenter feedback

---

## 2. Tamaño del modelo: qué es "grande" por dentro

### Content

- Cuando en la Sección 5 hablamos de un modelo "grande" o "chico", ¿qué es lo que efectivamente cambia por dentro? El "tamaño" es la **cantidad de parámetros**: cuánta capacidad de aprender y capturar patrones tiene el modelo — la analogía imperfecta pero útil es "la cantidad de neuronas".
- Más parámetros → más capacidad de representar patrones complejos, pero también más cómputo por consulta (de ahí que el grande sea más lento y caro, como vimos al elegir).
- Es una decisión de *construcción*: la fija quien entrena el modelo, no la tocás. Vos elegís entre modelos ya construidos (Sección 5); acá sólo entendemos qué hay detrás de la etiqueta "grande".

```ascii
  MODELO CHICO            MODELO GRANDE
  [ o o ]                 [ o o o o o o o o ]
  pocos parámetros        muchos parámetros
  menos cómputo/consulta  más cómputo/consulta

  "Tamaño" = cantidad de parámetros (capacidad),
  fijada al construir el modelo
```
<!-- ascii-note:
intent: explicar qué significa el "tamaño" de un modelo por dentro — la cantidad de parámetros (capacidad) fijada al construirlo, no una perilla que el usuario toca
emphasize: el contraste visual pocos vs muchos parámetros; que es una propiedad de construcción, no de uso
labels: "MODELO CHICO / MODELO GRANDE", "pocos vs muchos parámetros", "menos vs más cómputo/consulta", nota de cierre
-->

### Sources

- Conocimiento de dominio del presenter — no respaldado por el corpus. El corpus NO trata el tamaño del modelo (cantidad de parámetros) como parámetro; el contenido conceptual sobre parámetros/capacidad/cómputo es conocimiento de dominio del presenter, no citado en el corpus. (El punto de *elección* de modelo, sí respaldado por la Tabla 1 del corpus, se trata en la Sección 5.)

### Speaker notes

Primer parámetro de construcción, y lo trato como el "detrás de escena" de la decisión de la Sección 5. Allá ya vimos *cómo elegir* entre un modelo grande y uno chico (el eje capacidad-vs-costo y la regla "el más chico que alcance"). Acá no repito esa decisión: contesto la pregunta "¿y qué es, por dentro, un modelo grande?". Respuesta: cantidad de parámetros. Uso la analogía de "neuronas": más parámetros, más capacidad de capturar patrones complejos —y más cómputo por consulta, que es exactamente por qué el grande sale más caro y lento—. El punto de gestión: esto lo fija quien construye el modelo; el negocio no lo tunea, sólo elige entre modelos ya horneados. Es puro andamiaje conceptual para que "grande/chico" deje de ser una etiqueta opaca. Lo mantengo corto: una lámina, sin fórmulas.

### Presenter feedback

---

## 3. Learning rate: cómo aprende el modelo

### Content

- El learning rate es el "tamaño del paso" con que el modelo ajusta lo que aprende en cada corrección durante el entrenamiento.
- Muy grande: aprende rápido pero inestable, "se pasa de largo" y no converge.
- Muy chico: estable pero lentísimo y caro de entrenar.
- Negocio: no lo tocás nunca, pero explica por qué entrenar/afinar un modelo es un arte caro, y por qué "afinar tu propio modelo" no es gratis ni trivial.

```ascii
  Bajar por la montaña hacia la mejor versión del modelo:

  PASO GRANDE (LR alto)        PASO CHICO (LR bajo)
     o                            o
      \  rebota, se pasa           \
       \_/  \_/                     `._
      inestable                    `._  lento pero seguro
                                       *  (llega)
```
<!-- ascii-note:
intent: ilustrar learning rate como tamaño de paso al descender hacia el óptimo; pasos grandes rebotan, pasos chicos son lentos pero estables
emphasize: el contraste de trayectoria — rebote inestable vs descenso lento y seguro
labels: "PASO GRANDE (LR alto) inestable", "PASO CHICO (LR bajo) lento pero seguro (llega)", metáfora de la montaña
-->

### Sources

- Conocimiento de dominio del presenter — no respaldado por el corpus. El corpus (research/corpus/parametros-llm.md.md) NO menciona learning rate; este parámetro fue nombrado explícitamente por el presenter y se trata a nivel conceptual desde su conocimiento del dominio.

### Speaker notes

Segundo parámetro de construcción, y el más abstracto — lo trato con la máxima economía. Uso la metáfora de bajar una montaña con niebla hacia el punto más bajo (la "mejor versión" del modelo). El learning rate es el tamaño de cada paso. Pasos gigantes: avanzás rápido pero te pasás de largo y rebotás, nunca te asentás. Pasos minúsculos: llegás seguro pero tardás una eternidad (y en cómputo, eternidad = mucha plata). Encontrar el paso justo es parte del arte —y el costo— de entrenar. Por qué le importa a un gerente: cuando un proveedor ofrece "afinamos un modelo con tus datos" (fine-tuning), estas decisiones están detrás del precio y del riesgo de que salga mal. Learning rate es la razón conceptual de por qué "hacé tu propio modelo" nunca es tan simple ni tan barato como suena. No doy ninguna fórmula; me quedo en la montaña.

### Presenter feedback

---

# Conclusions

## 1. Lo que se llevan

### Content

- 🎯 Detrás de toda AI hay perillas que cambian calidad, costo, velocidad y consistencia.
- 🧭 Antes que nada elegís el **modelo**: la única perilla siempre expuesta, y la que fija el eje capacidad vs. costo/velocidad. Regla: el más chico/rápido que resuelva bien la tarea.
- ⚙️ Después, tres perillas de inferencia las tocás al usar: temperatura, top-p y el esfuerzo de razonamiento. Y dos parámetros los comprás horneados al elegir el modelo: su tamaño (parámetros) y su learning rate.
- 🧠 No hay configuración "buena": hay una apropiada a la tarea.
- 💸 Entender las perillas = decidir con criterio de negocio, no comprar humo.

### Sources

- research/corpus/parametros-llm.md.md (síntesis integral de la clase)

### Speaker notes

Recapitulo en pocos golpes, sin reabrir contenido. El mensaje que quiero que persista una semana después: no necesitás ser ingeniero para gestionar AI con criterio, pero sí necesitás saber que estas perillas existen y qué mueve cada una. Ordeno la recapitulación por lo que efectivamente decide un usuario: primero la elección del **modelo** (la única perilla siempre expuesta, con su regla "el más chico/rápido que alcance"); después las tres perillas de inferencia que se tocan al usar (temperatura, top-p, razonamiento); y por debajo, los dos parámetros que se compran horneados al elegir el modelo (tamaño y learning rate). Y remato con la frase-tesis: no hay configuración universalmente buena, hay una apropiada a cada tarea — quien entiende eso deja de tratar la AI como una caja mágica y empieza a tratarla como una herramienta que se calibra.

### Presenter feedback

---

## 2. Cierre y preguntas

### Content

- Pregunta para llevarse: pensá una tarea de AI de tu trabajo — ¿qué perilla cambiarías y por qué?
- Espacio de preguntas.

### Sources

- research/corpus/parametros-llm.md.md

### Speaker notes

Cierro con una pregunta accionable en vez de un "gracias": que cada uno piense una tarea concreta de su trabajo y qué perilla ajustaría. Esto ancla la clase en su realidad y suele disparar las mejores preguntas. Abro el espacio de Q&A. Si sobra tiempo o la sala es técnica, tengo material de reserva en Cut material (la mecánica profunda del razonamiento —RL, test-time compute, think tool—, penalizaciones de repetición, seed y reproducibilidad) para profundizar a demanda.

### Presenter feedback

---

# Open questions

- Objetivo de aprendizaje explícito y encaje en secuencia: falta confirmar del presenter qué querés que "se lleven" como resultado medible y si esta clase es suelta o parte de una secuencia (heredado de Step 1). El draft asume clase autónoma con entregable = la tabla de bolsillo de perillas (Slide 4.2). (El marco de decisión y la checklist de proveedor se removieron a pedido del presenter en Review — ver # Cut material.)
- Demo en vivo (Slide 1.1): confirmar si el presenter quiere hacer la doble-pregunta en vivo en una herramienta real o usar capturas. Afecta preparación técnica de la clase.
- Valores numéricos ilustrativos (temperatura 0–1.2, top-p 0.9): están marcados como referencias típicas, no como defaults verificados. El corpus advierte que los defaults por modelo y nombres de versión (GPT-5.x, Claude Opus 4.7/4.8) NO están verificados — el draft evita citarlos como hecho. Confirmar que este nivel de generalidad es el deseado para la audiencia.
- Profundidad de la Sección 6 (learning rate): learning rate es el concepto más abstracto para esta audiencia. Confirmar en Review si el nivel actual (una sola lámina, pura metáfora) es suficiente o excesivo.
- Sourcing de la Sección 6 (contenido de entrenamiento sin respaldo del corpus): el corpus (parametros-llm.md.md) NO cubre learning rate ni trata el tamaño del modelo como parámetro (solo respalda que la selección de modelo es lo único siempre expuesto en los chats web, Tabla 1 — punto usado en la Sección 5). Todo el contenido de construcción de la Sección 6 (Slides 6.2 tamaño-por-dentro y 6.3 learning rate) es conocimiento de dominio del presenter, marcado honestamente como tal en las líneas de Sources. Considerar agregar una fuente que respalde el material de entrenamiento (parámetros/capacidad, learning rate) para no depender solo de conocimiento de dominio no citado.
- Sourcing de la Sección 5 (Selección del modelo): el punto "la selección de modelo es la única perilla siempre expuesta" SÍ está respaldado por la Tabla 1 del corpus; el eje capacidad-vs-costo/velocidad entre niveles (grande/flagship vs mini/rápido) y la regla "el más chico que alcance" es conocimiento de dominio del presenter, marcado como tal. No se citan nombres ni defaults de versión por proveedor (no verificados).

# Cut material

- **Razonamiento — capa técnica profunda** (corpus, extenso): la perilla de razonamiento en sí (reasoning_effort low/medium/high, presupuesto de thinking) se PROMOVIÓ al deck como Slide 3.3 a pedido del presenter. Queda en Cut material sólo la mecánica profunda: la `think` tool, test-time compute, por qué el transformer conecta razonamiento con generar más tokens, el token de fin-de-thinking, RL/RLHF, y por qué se deshabilita temperatura/top-p en modelos de razonamiento (esto último se menciona brevemente en Slide 3.2). Material de profundización a demanda para una sala técnica.
- **Penalizaciones de repetición** (frequency_penalty, presence_penalty, repetition_penalty): perillas reales pero de segundo orden para negocio; se mencionan como existentes solo si hay preguntas.
- **top_k y min_p**: variantes de recorte de candidatos; redundantes con top-p para el nivel de la clase. Fuera salvo pregunta técnica.
- **seed y reproducibilidad "best effort"**: el detalle de por qué el mismo seed no garantiza la misma salida (hardware, batching, cambios del provider) es fascinante pero técnico. Vivía destilado en la checklist de proveedor (ex-Slide 5.2), que se removió del deck en Review; queda como material de reserva a demanda.
- **Salida estructurada / tools / function calling** (response_format, tool_choice): relevante para quien construye agentes, no para el marco conceptual de esta clase. Fuera.
- **logit_bias, logprobs, n, cache_control**: perillas de nicho; fuera del alcance de una clase introductoria de negocio.
- **Tablas detalladas "qué está expuesto en cada chat/API"** (corpus, Tablas 1–4): útiles como referencia pero demasiado densas para lámina; el concepto ("en el chat web casi nada; en la API todo") se destila en Slide 1.2.
- **La fórmula del softmax y el ejemplo numérico de logits**: deliberadamente omitidos — la clase promete "sin matemática". La intuición se transmite con las barras de confianza (Slides 2.1, 3.1).
- **RL / RLHF / policy**: aparece en el corpus para explicar por qué se deshabilita temperatura en modelos de razonamiento; irrelevante para el alcance elegido. Fuera.

---

## Ex-"Marco de decisión" (era la Sección 5 original — removida del deck en Review, 2026-07-07)

Removida completa a pedido del presenter ("Borra todo el 5. Marco de decisión"). Conservada verbatim acá por si se quisiera reponer. Eran dos slides: el árbol "de la tarea a la perilla" y la checklist de proveedor. El deck ahora cierra con las Conclusions después de la Sección 6 ("Lo que se decide al construir"). Nota: la numeración de secciones cambió varias veces después de esta remoción — se agregó "Selección del modelo" y luego se partió la ex-Sección "Perillas que SÍ tocás" en dos ("Cómo elige las palabras" y "Cuánto piensa"), por lo que "Lo que se decide al construir" pasó a ser la Sección 6; esta ex-sección "Marco de decisión" no tiene relación con la Sección 6 actual.

**Ex-Slide 5.1 — De la tarea a la perilla**

Content:
- Empezá por la tarea, no por la perilla. Tres preguntas de negocio deciden la configuración:
- ¿Necesito consistencia o creatividad? → temperatura / top-p.
- ¿La tarea es difícil o de varios pasos, y cuánto quiero pagar por respuesta? → esfuerzo de razonamiento.
- ¿Qué tan difícil es la tarea vs. cuánto quiero pagar? → tamaño del modelo.

```ascii
  PROBLEMA DE NEGOCIO
        |
        v
  +-------------------+     +-------------------------+
  | ¿consistente o    | --> | temperatura / top-p     |
  |  creativo?        |     +-------------------------+
  +-------------------+
  +-------------------+     +-------------------------+
  | ¿difícil / multi- | --> | esfuerzo de razonamiento|
  |  paso vs. costo?  |     +-------------------------+
  +-------------------+
  +-------------------+     +-------------------------+
  | ¿dificultad vs    | --> | tamaño del modelo       |
  |  presupuesto?     |     +-------------------------+
  +-------------------+
```
<!-- ascii-note:
intent: árbol de decisión que mapea cada pregunta de negocio a la(s) perilla(s) correspondiente(s)
emphasize: el flujo "problema de negocio" bajando a tres preguntas, cada una apuntando a su grupo de perillas
labels: "PROBLEMA DE NEGOCIO", las tres preguntas, y las perillas destino a la derecha
-->

Sources:
- research/corpus/parametros-llm.md.md (síntesis: qué parámetro controla qué, aplicado a decisiones de uso)

Speaker notes:
Slide-herramienta. Invierto el orden mental: la gente de negocios tiende a preguntar "¿qué temperatura pongo?"; la pregunta correcta es "¿qué necesita esta tarea?" y de ahí baja la perilla. Camino el árbol con un ejemplo real por rama: (1) un bot de compliance necesita consistencia → temperatura baja; (2) una tarea de análisis jurídico difícil justifica un modelo grande, un FAQ no. El mensaje: la configuración se *deriva* del problema. Esta es la lámina que quiero que apliquen el lunes en su trabajo.

**Ex-Slide 5.2 — Qué preguntarle a un proveedor**

Content:
- Checklist para evaluar o comprar una solución de AI, sin ser ingeniero:
- ⚙️ ¿Qué modelo usa por debajo y puedo elegir tamaño según costo?
- 🎯 ¿Puedo controlar la consistencia (temperatura/top-p) por tipo de tarea?
- 🧠 ¿Puedo ajustar cuánto "razona" el modelo (esfuerzo de razonamiento) según la dificultad de la tarea, y cómo impacta eso en costo y velocidad?
- 💸 ¿Cómo se factura y cómo controlo el costo por consulta?
- 🔁 ¿Los resultados son reproducibles o esperables que varíen?

Sources:
- research/corpus/parametros-llm.md.md (en la API se expone todo; seed y reproducibilidad "best effort", no garantiza determinismo total)

Speaker notes:
Este es el entregable más "portable" de la clase: una checklist que pueden llevar a cualquier reunión con un proveedor de AI. Cada pregunta corresponde a una perilla que ya entendieron. La última —reproducibilidad— la agrego para vacunarlos contra una expectativa equivocada frecuente: mucha gente asume que "la misma entrada da la misma salida siempre", y en AI generativa eso no está garantizado ni siquiera fijando semillas, por cómo corre el hardware. Si un proveedor promete determinismo perfecto, que sospechen. No entro en el detalle técnico del porqué; solo instalo la expectativa correcta. Les digo: con estas preguntas ya negocian mejor que la mayoría.
