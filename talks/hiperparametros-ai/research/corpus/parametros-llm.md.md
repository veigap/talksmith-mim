---
source_file: parametros-llm.md
source_type: chat-export
ingested_at: 2026-07-07
---

# Parámetros configurables en LLMs (transcripción Q&A)

## Provenance
- Original location: research/llm-chats/parametros-llm.md
- Format: markdown chat transcript (Q&A, español)
- Author / source (if known): No identificado. Transcripción de una sesión de preguntas y respuestas con un LLM sobre parámetros configurables.
- Date of original (if known): No indicada. Menciona modelos hasta GPT-5.x / Claude Opus 4.7-4.8, lo que ubica el contenido en 2025 o posterior.

## Key claims

- **No todos los parámetros están en todas las APIs**: dependen del modelo/provider. El chat agrupa los parámetros por qué controlan.
- **`temperature` es la palanca principal de aleatoriedad/sampling.** Escala la distribución de probabilidad: 0 = casi determinista; valores altos (0.8-1.2) = más variedad.
- **`temperature` reescala los *logits* antes del softmax** (antes de convertir puntajes crudos en probabilidades): `P(token_i) = exp(logit_i / T) / Σ exp(logit_j / T)`. El `T` divide al logit. T→0 agranda los logits y el token top se lleva casi toda la probabilidad (*greedy*); T=1 usa la distribución tal cual; T>1 aplana la distribución (más variedad, más riesgo de incoherencia).
- **La temperatura NO selecciona el token.** La temperatura arma/deforma la distribución; la selección la hace el **sampler** mediante **muestreo aleatorio ponderado** (una "ruleta" donde cada token ocupa una porción proporcional a su probabilidad; se usa la CDF / suma acumulada, y el número aleatorio -donde entra el `seed`- cae en la porción correspondiente).
- **`top_p` (nucleus sampling)** se queda con el conjunto mínimo de tokens que suma esa probabilidad acumulada (0.9 típico). **Se usa en lugar de `temperature`, no en conjunto** — tocar los dos a la vez suele ser contraproducente.
- **`top_k`** limita a los K tokens más probables (más crudo que top_p). **`min_p`** (más nuevo) filtra tokens por debajo de un umbral relativo al token más probable; buen balance a temperaturas altas; lo soportan varios backends open source.
- **Penalizaciones de repetición**: `frequency_penalty` (penaliza según cuántas veces apareció ya un token), `presence_penalty` (penaliza si el token apareció al menos una vez — empuja temas nuevos), `repetition_penalty` (variante multiplicativa en backends tipo vLLM/llama.cpp, no en la API de OpenAI).
- **Longitud/corte**: `max_tokens` / `max_output_tokens` (techo de la respuesta — clave para costo y para no cortar generaciones largas); `stop` / `stop_sequences` (strings que cortan la generación).
- **`seed`** fija el muestreo para (idealmente) obtener la misma salida, pero es **"best effort"**, no garantiza determinismo total. Razones: (1) hardware/paralelización GPU (floating point no perfectamente asociativo; el orden de acumulación de sumas cambia mínimamente los logits y puede voltear un empate cercano), (2) batching (compartir batch en servidores afecta el cálculo), (3) cambios del lado del provider (actualización de modelo/infra rompe el mapeo — OpenAI acompaña el seed con `system_fingerprint`), (4) `temperature=0` (greedy) no es lo mismo que seed y tampoco es 100% determinista por el punto 1. Determinismo real y duro solo corriendo el modelo uno mismo con hardware fijo, batch de tamaño 1 y kernels deterministas.
- **Razonamiento (lo más "de hoy", modelos 2024-2025 en adelante)**: `reasoning_effort` (OpenAI, serie o / GPT-5: low/medium/high, cuánto "piensa"); presupuesto de thinking (Anthropic extended thinking, Gemini: asignás tokens al razonamiento interno). Trade-off directo entre calidad, latencia y costo.
- **Salida estructurada / tools**: `response_format` (JSON mode o structured outputs con JSON Schema — garantiza que la salida valide contra el esquema, fundamental para agentes); `tools` + `tool_choice` (definís funciones disponibles y forzás o dejás libre el llamado).
- **Menos frecuentes pero útiles**: `logit_bias` (sube/baja la probabilidad de tokens específicos por ID — prohibir o forzar palabras); `logprobs` / `top_logprobs` (devuelve probabilidades, útil para evals, confidence scoring, detección de alucinaciones); `n` (cantidad de respuestas por request, útil para best-of-n); control de caché de prompt (`cache_control` en Anthropic — no cambia la salida pero sí costo/latencia).
- **En los chats web prácticamente NO se expone nada.** En claude.ai (web) sólo elegís el **modelo**; temperature y el resto vienen con defaults internos. En ChatGPT web es parecido (elegís modelo; en "Advanced" hay algunos toggles tipo "reasoning effort" sólo en o1/o3; no hay temperature explícita; Custom GPTs dan un poco más de control). En Gemini web lo único que tocás es el modelo (más JSON mode). Razón: la mayoría de usuarios no sabe qué es y los que saben usan la API; el chat web mantiene la interfaz limpia con defaults "razonables". Excepción: en algunos productos Team/Enterprise, OpenAI expone "temperature" vía settings de admin. En Claude API (devs) exponés todo.
- **"Thinking" = razonamiento interno del modelo antes de la respuesta final.** El modelo dedica tokens a "pensar" (desglosar el problema, explorar caminos, chequear su propio razonamiento) sin mostrarte el proceso crudo completo; luego da la respuesta limpia. Visible en Claude.ai (Extended Thinking, bloque plegable), ChatGPT (serie o: "Reasoning"/"Thinking") y Gemini (indicador "Thinking"). Mejora mucho la calidad en tareas complejas (matemática, lógica, código, análisis multi-paso); para preguntas simples aporta poco. Cada token de thinking se factura aparte (a menudo el doble que tokens normales) y aumenta la latencia. **El thinking que ves en la UI es una versión mostrada del proceso, no necesariamente el razonamiento crudo completo** — cada empresa decide cuánto exponer.
- **Thinking vs Effort son dos niveles distintos**: Thinking = **el mecanismo** (la capacidad de razonar internamente; on/off). Effort (`reasoning_effort`) = **la perilla que regula** cuánto de ese mecanismo se usa (low/medium/high). Analogía: Thinking es "el modelo puede pensar antes de hablar"; Effort es "¿que piense 5 segundos o 5 minutos?". OpenAI usa `reasoning_effort` explícito; Anthropic lo maneja como presupuesto de tokens; Gemini tiene su propio control de presupuesto — misma familia de idea (una en niveles, la otra en tokens).
- **`reasoning_effort` lo fija la capa que llama (agente/app/request), no está "horneado" en los pesos** — pero lo que regula es el comportamiento del *modelo* (cuánto razona internamente). El agente no "hace" el effort; le dice al modelo cuánto esfuerzo aplicar. Misma lógica que temperature (la seteás afuera, modifica cómo samplea el modelo).
- **Deep Research NO es un parámetro tipo temperature; es un modo/feature agéntica** que activás con un toggle. En vez de responder de una, navega automáticamente decenas/cientos de sitios (y opcionalmente Gmail, Drive, Chat), razona y arma un reporte de varias páginas en minutos. Loop: (1) construye un plan de investigación / outline; (2) el usuario acepta o modifica el plan; (3) navega la web iterativamente (busca → encuentra → lanza nueva búsqueda según lo aprendido, repite); (4) entrega un reporte con citas. Suele tardar 5-10 minutos. Es feature de pago (Gemini Advanced / Google One AI Premium). Equivalentes: ChatGPT "Deep Research" (sobre o3) y Claude modo "Research".
- **`reasoning_effort` en detalle**: le decís al modelo cuántos *tokens de razonamiento* ocultos gastar antes de la respuesta final; no toca el prompt ni el formato de salida. Niveles típicos: `minimal` (casi no razona, agregado con GPT-5), `low`, `medium` (default general), `high` (razona a fondo, explora más caminos, verifica su trabajo). Es el mismo modelo, con más o menos "cancha". Los tokens de razonamiento se facturan como tokens de salida aunque no se vean. **Contra-intuitivo: más razonamiento no siempre es mejor** — en tareas fáciles un effort alto puede llevar a "overthinking" y empeorar la respuesta.
- **`reasoning_effort` (API) vs "effort" en la UI**: son la misma idea en dos capas. API = parámetro crudo, valor directo (`minimal/low/medium/high...`). UI (ChatGPT) = selector de nivel de esfuerzo con etiquetas en lenguaje humano, renombrado (antes Standard/Extended/Heavy; ahora Instant / Medium / High / Extra High, más Pro Standard y Pro Extended). Diferencias: (1) granularidad (API valor directo; UI niveles pre-empaquetados con nombres que cambian seguido), (2) **auto-routing** (en API `high` es `high`; en el chat hay una capa de ruteo automático que puede pisar la elección), (3) trace visible (UI muestra el "Thinking" desplegable; API normalmente no devuelve tokens de razonamiento), (4) en la UI el "effort" viene acoplado a la selección de modelo; en la API son ejes más separados.
- **API vs UI NO es lo mismo que agente vs modelo** — son dos distinciones diferentes que se cruzan. API vs UI = quién configura y cómo se presenta (en ambos casos el que *ejecuta* el razonamiento es el modelo). Agente vs modelo = **Modelo** es la cosa que razona (tiene la capacidad de thinking y la ejecuta); **Agente / capa que llama** es quien *setea* el parámetro (no razona; instruye al modelo). La UI de ChatGPT es sólo un caso particular de "capa que llama": una app que setea el effort por vos y lo disfraza con nombres comerciales.
- **Extended thinking en Claude = una sola pasada del modelo**, NO un agente iterando. Cuando Claude "piensa", genera tokens de razonamiento antes de la respuesta final, todo dentro de una única llamada al modelo (monólogo interno lineal; sin loop ni múltiples llamadas). Un **agente iterando** es un loop *alrededor* del modelo (llama → mira resultado → decide si vuelve a llamar), orquestado por código externo. Son ejes independientes y se combinan (un agente puede en cada iteración llamar a un Claude con extended thinking). `thinking_budget` = cuántos tokens de razonamiento usa el modelo en una llamada; iteraciones del agente = cuántas llamadas hace el orquestador.
- **Hay tres "think" distintos**: (1) **Extended thinking** = razonamiento interno, una pasada, antes de responder (modo/param, regulado por `thinking_budget`); (2) **`think` tool** = una herramienta que Anthropic definió literalmente llamada `think`, un scratchpad que el modelo invoca en medio de un flujo con tools para parar a anotar/estructurar su pensamiento después de recibir resultados de otras tools (no busca nada afuera, no cambia estado); (3) **"Thinking" en la UI** = lo que te muestran del #1 (bloque desplegable). Extended thinking sirve para razonar *antes* de arrancar; la think tool para reflexionar *entre pasos* de un flujo agéntico.
- **Según la documentación oficial de OpenAI, `effort`**: control a nivel de request que indica cuánta profundidad de razonamiento (cuántos tokens ocultos de chain-of-thought) asignar antes de la respuesta final; no toca el prompt ni el formato de salida. Valores (dependen del modelo): `none, minimal, low, medium, high, xhigh`. Menos effort = velocidad y menor uso de tokens; más effort = piensa más completo, mayor calidad. Mecánicamente: en `low` puede podar caminos temprano y devolver la primera solución razonable; en `high` explora múltiples ramas, hace backtrack y verifica su propio trabajo. **Adaptativo**: no es un presupuesto fijo y ciego — el modelo modula dentro de cada nivel (menos tokens en tareas simples, más en complejas); el effort pone el techo/intensidad.
- **Defaults por modelo (doc OpenAI)**: gpt-5.5 usa `medium` por defecto; gpt-5.1 tiene `reasoning_effort` en `none` por defecto (al migrar desde modelos de razonamiento previos puede necesitarse pasar un nivel explícito para que ocurra razonamiento); gpt-5-pro sólo soporta effort `high` (su default aunque no se pase); gpt-5.1-codex-max agrega el nivel `xhigh`.
- **Gotchas de la doc OpenAI**: con reasoning models varios parámetros clásicos quedan **deshabilitados** — `temperature`, `top_p`, `presence_penalty`, `frequency_penalty`, `logprobs`, `top_logprobs`, `logit_bias` y `max_tokens` no están soportados (se usa `max_completion_tokens` / `max_output_tokens`). Las llamadas a tools en paralelo no se soportan cuando `reasoning_effort` está en `minimal`.
- **Por qué el transformer conecta razonamiento con generar más tokens**: un transformer hace una cantidad **FIJA** de cómputo por token (mismo forward pass, mismas capas/operaciones); un token "fácil" y uno "difícil" consumen exactamente el mismo cómputo. La única forma de gastar más cómputo en un problema es **generar más tokens**. Los "reasoning tokens" son tokens comunes (mismo mecanismo de next-token prediction: logits → temperature → sampler → token; un token de thinking y uno de respuesta son indistinguibles a nivel de máquina; el chain-of-thought va a un scratchpad interno). El **contexto es una memoria de trabajo**: cada token generado se appendea al contexto y los siguientes lo leen vía self-attention → convierte un problema difícil en una secuencia de muchos forward passes (esto es *test-time compute*, cómputo en serie; el contexto es la cinta de una máquina de Turing improvisada).
- **Dónde entra el `effort` mecánicamente**: controlar effort = controlar cuántos tokens de pensamiento genera antes de cortar. El modelo tiene un **token especial de fin-de-thinking** ("dejo de pensar y empiezo a responder") que compite con los demás en la distribución en cada paso. El modelo fue entrenado con RL para generar cadenas de razonamiento y aprender *cuándo* emitir ese token según la dificultad. El `effort` es una **señal de condicionamiento** metida en el contexto: como el modelo se entrenó con esa señal correlacionada a la longitud del razonamiento, condicionar en "high" reshape la distribución del próximo token (baja la probabilidad de emitir "ya terminé" temprano, sube la de seguir generando pasos). `effort` no es un mecanismo aparte: es un sesgo sobre la decisión next-token de "sigo pensando vs. respondo ya".
- **Por qué se deprecó/deshabilitó `temperature` en los reasoning models**: choca con lo que el RL entrenó. El razonamiento es una **trayectoria aprendida, no texto libre** (cada token condiciona el siguiente; el RL entrenó esa trayectoria para que sea correcta). Temperature mete ruido que en una cadena larga **se acumula y se propaga**: un token de razonamiento raro elegido por azar es un paso de cálculo equivocado que queda escrito en el contexto, y como los pasos siguientes lo *leen*, arrastran el error (error compuesto, no creatividad). Además el reasoning model ya gestiona internamente cuándo explorar/consolidar (la exploración está en la política RL, escrita como texto). Por qué lo bloquean en vez de dejarlo en 1.0: (1) los parámetros se calibraron durante el RL a un régimen de sampling específico; (2) las penalties son dañinas — `frequency/presence_penalty` penalizan repetir, pero el razonamiento repite a propósito (reformula, re-chequea); (3) evitan que el usuario se dispare en el pie subiendo temperature esperando "creatividad" y degradando la precisión.
- **RL = Reinforcement Learning (aprendizaje por refuerzo)**: paradigma donde el modelo aprende por prueba y error a partir de recompensas, no copiando ejemplos. Ciclo: produce algo → se evalúa y se le da una recompensa (puntaje) → ajusta pesos para hacer más probable lo de recompensa alta → repetir millones de veces → aprende una **política (policy)**. RLHF (RL from Human Feedback): humanos rankean respuestas, se entrena un "modelo de recompensa" que aprende el gusto humano, y RL optimiza el LLM contra ese juez (convirtió modelos crudos en asistentes útiles y educados). En reasoning models la recompensa muchas veces es **automática y verificable** (ej: problemas de matemática con respuesta conocida — se chequea si el resultado es correcto). Lo potente: nadie le enseñó *cómo* razonar paso a paso; el modelo descubrió solo, a fuerza de recompensa, que le conviene desglosar, explorar ramas, hacer backtracking y verificar.
- **En Claude, `temperature` nunca se "deprecó" globalmente** — se vuelve incompatible al activar extended thinking (que arrancó en Claude 3.7 Sonnet). En modelos sin thinking, temperature sigue viva. Doc textual: el thinking no es compatible con modificar temperature ni top_k, ni con forzar el uso de tools; con thinking activado sólo podés tocar `top_p` entre 0.95 y 1. Error de validación: la temperatura sólo puede fijarse en 1 cuando el thinking está habilitado (otro valor con thinking on → el request falla). Regla general de Claude (independiente del thinking): alterar temperature *o* top_p, no los dos a la vez. Cambio de régimen: Claude 3.7 → 4.x usaban `thinking: {type: "enabled", budget_tokens: N}` (presupuesto explícito, temperature fija en 1 al activar thinking); Claude 4.7/4.8 en adelante el default pasó a **adaptive thinking** (el modelo decide cuánto razonar por request) con niveles de effort (incluido `xhigh` entre `high` y `max`); los modos por presupuesto de modelos viejos ya no se usan en 4.7+. En Opus 4.7/4.8, como el thinking es adaptativo y prendido por defecto, en la práctica el régimen normal ya es sin temperature configurable.

## Definitions and terminology

- **`temperature` (T)**: factor que divide los logits antes del softmax; reescala la distribución de probabilidad. Controla aleatoriedad. No selecciona el token.
- **logits**: puntajes crudos, sin normalizar, que el modelo produce para cada token candidato.
- **softmax**: función que convierte los logits en probabilidades: `P(token_i) = exp(logit_i / T) / Σ exp(logit_j / T)`.
- **sampler / sampling**: mecanismo que efectivamente *elige* un token de la distribución final, vía muestreo aleatorio ponderado.
- **greedy decoding / argmax**: caso límite con `temperature=0`, el token más probable se elige siempre.
- **`top_p` (nucleus sampling)**: se queda con el conjunto mínimo de tokens que suma la probabilidad acumulada p (descarta la cola larga).
- **`top_k`**: deja sólo los K tokens más probables, el resto a probabilidad 0.
- **`min_p`**: descarta todo lo que esté por debajo de un umbral relativo al token top.
- **`frequency_penalty` / `presence_penalty` / `repetition_penalty`**: penalizaciones de repetición (ver Key claims).
- **`seed`**: fija el punto de partida del muestreo aleatorio; reproducibilidad "best effort".
- **`system_fingerprint`** (OpenAI): identificador que acompaña al seed; si cambia, la reproducibilidad no está garantizada.
- **thinking / extended thinking**: razonamiento interno del modelo antes de la respuesta final, en una sola pasada.
- **`reasoning_effort` / effort**: perilla que gradúa cuántos tokens de razonamiento gasta el modelo (niveles: none/minimal/low/medium/high/xhigh según modelo).
- **`thinking_budget`** (Anthropic): presupuesto de tokens de razonamiento (equivalente por-tokens del effort de OpenAI).
- **`think` tool** (Anthropic): herramienta-scratchpad que el modelo invoca entre pasos de un flujo con tools (distinta del extended thinking).
- **Deep Research / Research**: modo agéntico (no un parámetro) que planea → busca → lee → sintetiza y entrega un reporte con citas.
- **agente**: loop de orquestación *alrededor* del modelo (múltiples llamadas), controlado por código externo. Distinto del razonamiento interno del modelo (una llamada).
- **test-time compute**: cómputo en serie que gana capacidad generando más tokens (usando el contexto como scratchpad).
- **RL (Reinforcement Learning)**: entrenamiento por recompensa (prueba y error) en vez de por imitación. Produce una **política (policy)**.
- **RLHF (RL from Human Feedback)**: RL usando un modelo de recompensa entrenado con rankings humanos.
- **policy (política)**: estrategia aprendida de qué token generar en cada situación para maximizar la recompensa esperada.
- **response_format / structured outputs**: JSON mode o salida validada contra un JSON Schema.
- **tools / tool_choice / function_calling**: definición de funciones disponibles y control de su invocación.

## Evidence and examples

- **Ejemplo numérico de temperature** (logits `[2.0, 1.0, 0.5]`):

  | Token | logit | T=0.5 | T=1.0 | T=2.0 |
  |-------|-------|-------|-------|-------|
  | A | 2.0 | ~0.84 | ~0.63 | ~0.48 |
  | B | 1.0 | ~0.11 | ~0.23 | ~0.29 |
  | C | 0.5 | ~0.05 | ~0.14 | ~0.23 |

  A T=0.5 el token A domina (84%) → respuesta predecible; a T=2.0 la distribución se aplana.

- **Ejemplo de muestreo aleatorio ponderado (ruleta / CDF)** con probabilidades finales A=0.48, B=0.29, C=0.23:

  ```
  A: 0.00 – 0.48
  B: 0.48 – 0.77
  C: 0.77 – 1.00
  ```
  Sale el random (ej: 0.63) → cae en el rango de B → se elige B. "Cada uno gana proporcional a su tajada", no "el más probable gana siempre".

- **Pipeline completo del sampling**:
  ```
  logits → [temperature deforma] → [top_k/top_p/min_p recortan] →
           → normalizar → muestreo aleatorio ponderado (con seed) → token elegido
  ```

- **Cómo se pasa el effort en la API (OpenAI)**:
  ```json
  reasoning: {
    "effort": "low",     // "low", "medium", "high"...
    "summary": "auto"    // resumen del razonamiento
  }
  ```

- **Loop del scratchpad de razonamiento (contexto como memoria de trabajo)**:
  ```
  Problema → [genera paso 1] → paso 1 ahora está en el contexto →
           → [genera paso 2, atendiendo al paso 1] → paso 2 en contexto →
           → [genera paso 3, leyendo 1 y 2] → ... → [respuesta final]
  ```

- **Ejemplo de RL verificable**: problemas de matemática con respuesta conocida — el modelo genera una cadena de razonamiento larga, se chequea automáticamente si el resultado es correcto (recompensa alta) o no (baja); el modelo aprende qué cadenas llevan a respuestas correctas.

- **Analogías usadas en el chat**:
  - Thinking vs Effort: "el modelo puede pensar antes de hablar" vs "¿que piense 5 segundos o 5 minutos?".
  - Effort como asignación de cómputo, no prompt engineering.
  - El contexto como "la cinta de una máquina de Turing improvisada".
  - RL: "practicar y recibir devolución de un entrenador" vs "estudiar copiando de un libro".

## Inconsistencies / open questions

- **Refinamiento iterativo de la tabla "qué está expuesto".** El chat construye y reconstruye la tabla de parámetros expuestos varias veces, progresivamente reducida y ampliada:
  1. Primero una tabla completa de ~19 parámetros × 4 columnas (claude.ai web / ChatGPT web / Claude API / OpenAI API).
  2. Luego "solo los que se puedan tocar" agregando Gemini (5 filas, 3 columnas web).
  3. Luego agrega `deep research` (modo) como fila.
  4. Luego agrega `top_k` (explícitamente para dejar constancia de que NO está expuesto en ninguno de los tres chats web).
  5. Finalmente una tabla nueva "opción B" sobre **cómo cada uno expone el effort/thinking** (5 columnas, incluyendo las dos APIs). Todas se preservan íntegras abajo en *Raw / preserved excerpts*.
- **Auto-corrección "agente vs modelo".** La pregunta del usuario "effort es en el agente, no el modelo" recibe un "Sí y no — hay dos capas": el effort se *setea* en la capa que llama (agente/app/request) pero *regula* el comportamiento del modelo. Más adelante ("Uno es el Agente vs el Modelo?") se aclara que la distinción API vs UI **no** es lo mismo que agente vs modelo — son dos ejes cruzados.
- **Auto-corrección "en Claude, no es esto el agente cuánto itera la respuesta?".** Respuesta enfática: **No.** Extended thinking = una sola pasada del modelo; un agente iterando = loop externo de orquestación con múltiples llamadas. Son mecanismos de niveles diferentes.
- **Matiz sobre `seed`.** El usuario pregunta si mismo seed → siempre misma respuesta. Respuesta: "En teoría sí, en la práctica no del todo." Se enumeran cuatro razones (hardware/paralelización, batching, cambios del provider, temperature=0 ≠ seed). Determinismo real sólo corriendo el modelo uno mismo.
- **Matiz sobre `temperature` en Claude.** Se aclara explícitamente que temperature "nunca se deprecó de forma global" en Claude — sólo se vuelve incompatible con extended thinking. Corrige la posible interpretación de que "murió por decreto": "murió condicionada al razonamiento".
- **Contra-intuición explícita**: más razonamiento (effort alto) no siempre es mejor — en tareas fáciles puede llevar a "overthinking" y empeorar la respuesta.
- **Sobre el trace de "Thinking" en la UI**: es "una versión mostrada del proceso, no necesariamente el razonamiento crudo completo — cada empresa decide cuánto exponer". Zona gris sobre cuánto del razonamiento real se muestra.
- **Nota de datación / verificación**: el transcript cita defaults y nombres de modelos muy específicos (gpt-5.5 = medium, gpt-5.1 = none, gpt-5-pro = high, gpt-5.1-codex-max = xhigh; Claude Opus 4.7/4.8 con adaptive thinking; niveles UI "Instant/Medium/High/Extra High"). Estas cifras y nombres provienen de la respuesta del LLM y no están verificadas contra documentación oficial dentro del transcript; conviene contrastarlas antes de citarlas como hechos en la charla.

## Images / diagrams

<Ninguna. El source es una transcripción de texto pura (con tablas y bloques de código en línea); no carga imágenes. La carpeta compañera research/corpus/parametros-llm.md/images/ existe pero está vacía.>

## Raw / preserved excerpts

### Fórmula del softmax con temperatura
```
P(token_i) = exp(logit_i / T) / Σ exp(logit_j / T)
```
- **T → 0**: los logits se agrandan muchísimo, el más alto se lleva casi toda la probabilidad. Salida casi determinista (siempre el token top). Es *greedy*.
- **T = 1**: usás la distribución tal cual la produjo el modelo, sin deformar.
- **T alta (>1)**: aplanás la distribución, los tokens menos probables ganan chance. Más variedad, pero también más riesgo de incoherencia.

### Tabla 1 — Lista completa de parámetros y si está expuesto (verbatim)

| Parámetro | claude.ai (web) | ChatGPT web | Claude API | OpenAI API |
|-----------|-----------------|------------|-----------|-----------|
| **temperature** | — | — | X | X |
| **top_p** | — | — | X | X |
| **top_k** | — | — | — | — |
| **min_p** | — | — | — | — |
| **frequency_penalty** | — | — | X | X |
| **presence_penalty** | — | — | X | X |
| **repetition_penalty** | — | — | — | — |
| **max_tokens** / max_output_tokens | — | — | X | X |
| **stop_sequences** | — | — | X | X |
| **seed** | — | — | X (parcial) | X (parcial) |
| **response_format** (JSON/structured) | — | X (JSON mode) | X (full) | X (full) |
| **tools / function_calling** | — | X (GPTs custom) | X | X |
| **tool_choice** | — | — | X | X |
| **reasoning_effort** (o1/o3) | — | X (solo o1/o3) | — | X (solo o1) |
| **thinking_budget** (extended thinking) | — | — | X | — |
| **logit_bias** | — | — | X | X |
| **logprobs / top_logprobs** | — | — | X | X |
| **n** (multiple responses) | — | — | X | X |
| **cache_control** (prompt caching) | — | — | X | — |
| **model selection** | X | X | X | X |

### Tabla 2 — Solo los tocables, agregando Gemini (verbatim)

| Parámetro / Modo | claude.ai (web) | ChatGPT web | Gemini (web) |
|-----------|-----------------|------------|------------|
| **temperature** | — | — | — |
| **response_format** (JSON) | — | X | X |
| **tools / function_calling** | — | X | X |
| **reasoning_effort** | — | X (o1/o3) | — |
| **model selection** | X | X | X |

Lo único que tocás en los tres es el modelo. ChatGPT suma JSON mode y reasoning; Gemini suma JSON mode. Nada de temperature en ninguno del lado web.

### Tabla 3 — Agregando deep research (verbatim)

| Parámetro / Modo | claude.ai (web) | ChatGPT web | Gemini (web) |
|-----------|-----------------|------------|------------|
| **temperature** | — | — | — |
| **response_format** (JSON) | — | X | X |
| **tools / function_calling** | — | X | X |
| **reasoning_effort** | — | X (o1/o3) | — |
| **deep research** (modo) | X (Research) | X | X |
| **model selection** | X | X | X |

### Tabla 4 — Agregando top_k (verbatim)

| Parámetro / Modo | claude.ai (web) | ChatGPT web | Gemini (web) |
|-----------|-----------------|------------|------------|
| **temperature** | — | — | — |
| **top_k** | — | — | — |
| **response_format** (JSON) | — | X | X |
| **tools / function_calling** | — | X | X |
| **reasoning_effort** | — | X (o1/o3) | — |
| **deep research** (modo) | X (Research) | X | X |
| **model selection** | X | X | X |

### reasoning_effort en detalle — tabla de trade-offs (verbatim)

| Effort | Calidad (en tareas difíciles) | Latencia | Costo |
|--------|------------------------------|----------|-------|
| minimal | baja | mínima | mínimo |
| low | media | baja | bajo |
| medium | buena | media | medio |
| high | máxima | alta | alto |

### Thinking vs Effort (verbatim)

| | Thinking | Effort |
|---|---|---|
| Qué es | El proceso de razonar | El nivel de intensidad de ese proceso |
| Tipo | Capacidad on/off | Perilla graduable (low/med/high) |
| Quién lo usa | Claude (extended thinking), Gemini | OpenAI serie o (o1/o3), GPT-5 |
| Equivalente | "pensar" | "cuánto pensar" |

### reasoning_effort UI (ChatGPT) vs concepto API (verbatim)

| UI (ChatGPT hoy) | Equivale a | Concepto API |
|---|---|---|
| Instant | sin thinking | (modelo Instant) |
| Medium | ex-"Thinking Standard" | reasoning_effort medio |
| High | ex-"Thinking Extended" | reasoning_effort alto |
| Extra High | ex-"Thinking Heavy" | reasoning_effort máximo |

### Quién setea el effort / cómo se presenta (verbatim)

| | Quién setea el effort | Cómo te lo presenta |
|---|---|---|
| **API directa** | vos, en el request | valor crudo (`low/medium/high`) |
| **Tu agente** | el config del agente | como vos lo definas |
| **UI de ChatGPT** | la app de ChatGPT por vos | niveles con nombre + auto-router |

### Extended thinking vs Agente iterando (verbatim)

| | Extended thinking | Agente iterando |
|---|---|---|
| Qué es | Razonamiento interno del modelo | Loop de orquestación |
| Cuántas llamadas al modelo | Una | Varias |
| Quién controla | El modelo, adentro | Código/orquestador, afuera |
| Qué produce | Tokens de thinking + respuesta, en un tiro | Secuencia de acciones/llamadas |

### Extended thinking vs `think` tool (verbatim)

| | Extended thinking | `think` tool |
|---|---|---|
| Qué es | Razonamiento interno del modelo | Una tool que el modelo invoca |
| Cuándo ocurre | Antes de empezar a responder | Durante un flujo con tools, entre pasos |
| Para qué sirve | Pensar el problema de entrada | Frenar a reflexionar *después* de recibir resultados de otras tools |
| Cómo se activa | Parámetro (`thinking` / budget) | Se la definís como tool disponible |

### Tabla "opción B" — Cómo cada uno expone el effort/thinking (verbatim)

| | claude.ai (web) | ChatGPT web | Gemini (web) | API (OpenAI) | API (Claude) |
|---|---|---|---|---|---|
| **Cómo se llama** | Extended thinking | Thinking / effort | Thinking | `reasoning_effort` | `thinking` + budget |
| **Cómo se expresa** | on/off (según modelo) | niveles con nombre | on/off | niveles: none/minimal/low/medium/high/xhigh | presupuesto de tokens |
| **Niveles visibles** | — | Instant / Medium / High / Extra High | — | none…xhigh | vos ponés el nº de tokens |
| **Granularidad** | baja (binario) | media (4 niveles) | baja (binario) | alta (6 niveles) | máxima (token exacto) |
| **Auto-router encima** | sí (decide el sistema) | sí (puede pisar tu elección) | sí | no | no |
| **Trace visible** | sí (bloque desplegable) | sí (al elegir manual) | sí | no (tokens ocultos) | resumen/parcial |
| **Quién lo setea** | la app | la app (+ vos, parcial) | la app | vos (request) | vos (request) |

### Generación normal vs Razonamiento (por qué se deprecó temperature) (verbatim)

| | Generación normal | Razonamiento |
|---|---|---|
| Cada token es | una palabra de la salida | un paso de cálculo que se relee |
| Un token "raro" | variación estilística inocua | posible error que contamina la cadena |
| La exploración | la inducís con temperature (afuera) | está en la política RL, escrita como texto (adentro) |
| Rol de temperature | perilla útil de creatividad | ruido que descarrila la trayectoria |

### Pre-entrenamiento / Fine-tuning supervisado vs RL (verbatim)

| | Pre-entrenamiento / Fine-tuning supervisado | RL |
|---|---|---|
| Cómo aprende | Imitando texto: "predecí la siguiente palabra de este ejemplo" | Por recompensa: "generá algo y te digo qué tan bueno fue" |
| La señal | La palabra correcta ya está en el dataset | Un puntaje sobre lo que el modelo produjo |
| Qué logra | Que suene bien, que sepa cosas | Que se comporte de cierta forma (útil, seguro, o que razone bien) |
| Analogía | Estudiar copiando de un libro | Practicar y recibir devolución de un entrenador |

### Cuándo temperature deja de estar disponible en Claude (verbatim)

| Modelo / Modo | Thinking | ¿Temperature disponible? |
|---|---|---|
| Claude 3.5 y anteriores | No existía thinking | Sí — temperature normal |
| Claude 3.7 Sonnet — sin thinking | Off | Sí |
| Claude 3.7 Sonnet — con extended thinking | On | No — debe quedar en 1 |
| Claude 4 (Opus 4 / Sonnet 4) — sin thinking | Off | Sí |
| Claude 4 — con thinking | On | No |
| Claude 4.5 / 4.6 (Sonnet 4.6, Opus 4.6) — sin thinking | Off | Sí |
| Claude 4.5 / 4.6 — con thinking | On | No |
| Claude Opus 4.7+ / Opus 4.8 (adaptive thinking por defecto) | On por defecto | No cuando piensa |

### Cita textual sobre restricciones de thinking en Claude (verbatim)
- El thinking no es compatible con modificar temperature ni top_k, ni con forzar el uso de tools. Con thinking activado, solo podés tocar top_p entre 0.95 y 1.
- El error de validación clásico lo confirma: la temperatura solo puede fijarse en 1 cuando el thinking está habilitado. Si mandás otro valor con thinking on, el request falla.
- La regla general de Claude (independiente del thinking): conviene alterar temperature *o* top_p, pero no los dos a la vez.

### Resumen encadenado — transformer, effort y tokens (verbatim)
1. Transformer = cómputo fijo por token, siempre next-token prediction.
2. Como el cómputo por token es fijo, más "esfuerzo" = obligatoriamente más tokens.
3. Los tokens de razonamiento se generan con el pipeline idéntico (incluida temperature/sampling).
4. El contexto funciona de scratchpad: el modelo escribe y se relee vía attention → cómputo en serie.
5. `effort` = señal aprendida por RL que sesga *cuándo* el modelo emite el token de "dejo de pensar".

Por eso lo de la doc de OpenAI cierra: "high" habilita multi-rama + backtracking + auto-verificación no porque haya un algoritmo nuevo, sino porque hay presupuesto de tokens para escribir esas ramas y esas verificaciones como texto, y el modelo aprendió a usarlos.
