# Parámetros configurables en LLMs

---

**Q: Qué parametros son relevantes hoy en un LLM que se puedan configurar**

Va un mapa de los parámetros que hoy importan de verdad, agrupados por qué controlan. Aclaro que no todos están en todas las APIs: dependen del modelo/provider.

**Aleatoriedad / sampling** (lo que define cuán "creativo" o determinista sale el texto)

- `temperature`: escala la distribución de probabilidad. 0 = casi determinista, valores altos (0.8–1.2) = más variedad. Es la palanca principal.
- `top_p` (nucleus sampling): en vez de mirar todos los tokens, se queda con el conjunto mínimo que suma esa probabilidad acumulada. 0.9 es típico. Se usa en lugar de temperature, no en conjunto (tocar los dos a la vez suele ser contraproducente).
- `top_k`: limita a los K tokens más probables. Más crudo que top_p.
- `min_p`: más nuevo, filtra tokens por debajo de un umbral relativo al token más probable. Da buen balance a temperaturas altas; lo soportan varios backends open source.

**Penalizaciones de repetición**

- `frequency_penalty`: penaliza tokens según cuántas veces ya aparecieron (baja repetición literal).
- `presence_penalty`: penaliza si el token ya apareció aunque sea una vez (empuja a introducir temas nuevos).
- `repetition_penalty`: variante multiplicativa en backends tipo vLLM/llama.cpp, no en la API de OpenAI.

**Longitud y corte**

- `max_tokens` / `max_output_tokens`: techo de la respuesta. Clave para costo y para no cortar generaciones largas.
- `stop` / `stop_sequences`: strings que cortan la generación. Útil para formatos estructurados o para que no siga de largo.

**Reproducibilidad**

- `seed`: fija el muestreo para (idealmente) obtener la misma salida. En la práctica es "best effort" — no garantiza determinismo total entre corridas o versiones de modelo.

**Razonamiento** (esto es lo más "de hoy", modelos 2024–2025 en adelante)

- `reasoning_effort` (serie o de OpenAI, GPT-5): low/medium/high, cuánto "piensa" antes de responder.
- Presupuesto de thinking (Anthropic extended thinking, Gemini): asignás tokens al razonamiento interno. Trade-off directo entre calidad, latencia y costo.

**Salida estructurada / tools**

- `response_format`: JSON mode o, mejor, structured outputs con JSON Schema (garantiza que la salida valide contra el esquema). Fundamental si estás armando agentes.
- `tools` + `tool_choice`: definís funciones disponibles y forzás o dejás libre el llamado.

**Menos frecuentes pero útiles**

- `logit_bias`: subís/bajás la probabilidad de tokens específicos por ID. Sirve para prohibir o forzar palabras.
- `logprobs` / `top_logprobs`: te devuelve las probabilidades, útil para evals, confidence scoring o detección de alucinaciones.
- `n`: cantidad de respuestas por request (útil para best-of-n).
- Control de caché de prompt (`cache_control` en Anthropic): no cambia la salida pero sí el costo/latencia.

---

**Q: Eg: Temperatura**

La temperatura es lo que reescala los *logits* antes del softmax, o sea antes de convertir los puntajes crudos del modelo en probabilidades.

**La mecánica**

El modelo, para cada token candidato, produce un logit (un número sin normalizar). El softmax los convierte en probabilidades:

```
P(token_i) = exp(logit_i / T) / Σ exp(logit_j / T)
```

Ese `T` es la temperatura. Fijate que divide al logit:

- **T → 0**: los logits se agrandan muchísimo, el más alto se lleva casi toda la probabilidad. Salida casi determinista (siempre el token top). Es *greedy*.
- **T = 1**: usás la distribución tal cual la produjo el modelo, sin deformar.
- **T alta (>1)**: aplanás la distribución, los tokens menos probables ganan chance. Más variedad, pero también más riesgo de incoherencia.

**Ejemplo numérico**

Con logits `[2.0, 1.0, 0.5]`, así quedan las probabilidades según T:

| Token | logit | T=0.5 | T=1.0 | T=2.0 |
|-------|-------|-------|-------|-------|
| A | 2.0 | ~0.84 | ~0.63 | ~0.48 |
| B | 1.0 | ~0.11 | ~0.23 | ~0.29 |
| C | 0.5 | ~0.05 | ~0.14 | ~0.23 |

Se ve el efecto: a T=0.5 el token A domina (84%), la respuesta va a ser predecible. A T=2.0 la distribución se aplana.

---

**Q: Que se expone de esto en el chat en Claude, GPT.**

Corta respuesta: prácticamente nada.

En claude.ai (web), no exponés temperatura ni ninguno de estos parámetros. El chat te deja elegir el **modelo** y punto. La temperatura y el resto vienen con defaults internos.

En **ChatGPT** (web) es más o menos lo mismo: elegís el modelo, en modo "Advanced" tenés algunos toggles tipo "reasoning effort" (solo en o1/o3), pero no temperature explícita. Con Custom GPTs ganás un poco más de control, pero sigue siendo limitado.

Lo que sí cambia indirectamente:

- En algunos productos Team/Enterprise, OpenAI expone "temperature" vía settings de admin.
- En Claude API (para devs), exponés todo: temperature, top_p, max_tokens, tools, structured output, etc.

Por qué no lo exponen en el chat web: porque la mayoría de usuarios no sabe qué es, y los que saben usan la API. El chat web apunta a mantener la interfaz limpia y los defaults son "razonables".

---

**Q: Dame una tabla con la lista de parametros y si esta expuesto.**

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

---

**Q: Solo los que se puedan tocar. Agregar en la tabla Gemini**

| Parámetro / Modo | claude.ai (web) | ChatGPT web | Gemini (web) |
|-----------|-----------------|------------|------------|
| **temperature** | — | — | — |
| **response_format** (JSON) | — | X | X |
| **tools / function_calling** | — | X | X |
| **reasoning_effort** | — | X (o1/o3) | — |
| **model selection** | X | X | X |

Lo único que tocás en los tres es el modelo. ChatGPT suma JSON mode y reasoning; Gemini suma JSON mode. Nada de temperature en ninguno del lado web.

---

**Q: Que es "Thinking" que se ve en la UI**

"Thinking" es el razonamiento interno que hace el modelo antes de darte la respuesta.

El modelo dedica tokens a "pensar" (razonar, desglosar el problema, explorar caminos) sin mostrarte ese proceso. Luego te da la respuesta final limpia.

Dónde lo ves:

- **Claude.ai**: en algunos modelos (Extended Thinking), ves un toggle o la palabra "Thinking" aparece en la UI mientras procesa. Los tokens de thinking se cuentan aparte (más caro).
- **ChatGPT**: en o1 y o3, ves "Reasoning" o "Thinking" — el modelo razona internamente antes de responder.
- **Gemini**: también lo tiene, aparece como "Thinking" en la interfaz.

Por qué importa:

- **Problemas complejos**: matemática, lógica, coding — el thinking mejora mucho la calidad porque el modelo se "toma tiempo" para razonar.
- **Costo**: cada token de thinking cuenta en la factura (a menudo el doble que tokens normales).
- **Latencia**: tarda más porque está pensando.

---

**Q: Que es "thinking"?**

"Thinking" es el razonamiento interno que el modelo hace antes de darte la respuesta final.

En vez de responder de una, el modelo primero "piensa": desglosa el problema, explora enfoques, chequea su propio razonamiento. Ese proceso consume tokens pero mejora la calidad, sobre todo en tareas complejas (matemática, lógica, código, análisis de varios pasos).

Dónde lo ves en la UI:

- **Claude.ai**: en modelos con Extended Thinking, aparece la palabra "Thinking" o un bloque plegable mientras el modelo procesa. Podés expandirlo para ver el razonamiento.
- **ChatGPT**: en los modelos de razonamiento (serie o), muestra "Thinking" / "Reasoning" antes de la respuesta.
- **Gemini**: igual, aparece un indicador de "Thinking".

Los trade-offs:

- **Calidad**: sube bastante en problemas difíciles. Para preguntas simples no aporta mucho.
- **Costo**: los tokens de razonamiento se facturan aparte (y suelen ser caros).
- **Latencia**: tarda más porque literalmente está pensando antes de escribir.

El detalle clave: el thinking que ves en la UI es una versión mostrada del proceso, no necesariamente el razonamiento crudo completo — cada empresa decide cuánto exponer.

---

**Q: Thinking vs Effort**

Son dos cosas de nivel distinto: una es **qué** hace el modelo, la otra es **cuánto** de eso hace.

**Thinking** = el mecanismo. Es el razonamiento interno en sí: el modelo genera tokens de "pensamiento" antes de la respuesta final. Es la capacidad. O está activo o no.

**Effort (reasoning_effort)** = la perilla que regula ese mecanismo. Es un parámetro que le dice al modelo *cuánto* esfuerzo/razonamiento meterle. Típicamente `low` / `medium` / `high`. Más effort = más tokens de thinking = más calidad en problemas difíciles, pero más costo y latencia.

La analogía: Thinking es "el modelo puede pensar antes de hablar". Effort es "¿que piense 5 segundos o 5 minutos?".

| | Thinking | Effort |
|---|---|---|
| Qué es | El proceso de razonar | El nivel de intensidad de ese proceso |
| Tipo | Capacidad on/off | Perilla graduable (low/med/high) |
| Quién lo usa | Claude (extended thinking), Gemini | OpenAI serie o (o1/o3), GPT-5 |
| Equivalente | "pensar" | "cuánto pensar" |

Distintas empresas lo empaquetan distinto: OpenAI usa el término `reasoning_effort` explícito; Anthropic lo maneja como presupuesto de tokens para thinking; Gemini tiene su propio control de presupuesto. Effort y thinking-budget son la misma familia de idea (regular la cantidad de razonamiento), solo que una lo expresa en niveles y la otra en tokens.

---

**Q: effort es en el agente, no el modelo**

Sí y no — hay dos capas.

**Dónde se setea**: `reasoning_effort` es un parámetro de configuración, no algo intrínseco del modelo. Lo fija quien hace la llamada — el agente, la app, el config. No viene "horneado" en los pesos del modelo. En un setup agéntico, sí, lo definís a nivel del agente.

**Qué controla**: pero lo que ese parámetro regula es el comportamiento del *modelo* — cuánto razona internamente. El agente no "hace" el effort; le dice al modelo cuánto esfuerzo aplicar. El razonamiento ocurre dentro del modelo.

- **El modelo** es el que tiene la capacidad de thinking y el que ejecuta el razonamiento.
- **El effort** es un dial de configuración que vive en la capa de quien invoca (agente/app/request), y que le instruye al modelo cuánto razonar.

Es la misma lógica que temperature: la seteás vos afuera, pero lo que modifica es cómo samplea el modelo.

---

**Q: Que es el parametro "deep research" que ve en Gemini.**

Deep Research no es un "parámetro" tipo temperature. Es un **modo/feature** que activás con un toggle en la barra de prompt de Gemini. Cambia todo el comportamiento, no un valor puntual.

Qué es: una feature agéntica. En vez de responderte de una, navega automáticamente decenas o cientos de sitios web (y opcionalmente tu Gmail, Drive y Chat), razona sobre lo que encuentra, y arma un reporte de varias páginas en minutos.

Cómo funciona el loop:

1. Le das una pregunta, y primero construye un plan de investigación — un outline estructurado de lo que va a investigar.
2. Podés aceptar el plan tal cual o modificarlo antes de que arranque.
3. Una vez aprobado, navega la web como lo harías vos: busca, encuentra info, y arranca una búsqueda nueva basada en lo que aprendió. Repite el proceso varias veces.
4. Te entrega un reporte con citas a las fuentes.

Tiempos: suele tardar 5-10 minutos porque analiza muchas fuentes; los reportes más complejos tardan más.

La diferencia conceptual:

- **temperature / effort** = perillas que ajustan *cómo* genera un texto.
- **Deep Research** = un modo que cambia *qué hace* el sistema: en vez de una respuesta, dispara un flujo agéntico de planear → buscar → leer → sintetizar.

Disponibilidad: es feature de pago. Requiere Gemini Advanced (suscripción Google One AI Premium); el tier gratuito no lo incluye. El equivalente lo tenés en ChatGPT ("Deep Research", sobre o3) y en Claude también hay un modo Research.

---

**Q: Perfecto. Agregalo a la lista.**

| Parámetro / Modo | claude.ai (web) | ChatGPT web | Gemini (web) |
|-----------|-----------------|------------|------------|
| **temperature** | — | — | — |
| **response_format** (JSON) | — | X | X |
| **tools / function_calling** | — | X | X |
| **reasoning_effort** | — | X (o1/o3) | — |
| **deep research** (modo) | X (Research) | X | X |
| **model selection** | X | X | X |

Deep Research no es un parámetro de sampling como los otros, es un modo agéntico que cambia todo el comportamiento. Lo tenés en los tres (Claude lo llama "Research", ChatGPT y Gemini "Deep Research"), en general detrás de plan pago.

---

**Q: Hay un parametro seed, si pongo este siempre igual la respuesta seria siempre el mismo.**

En teoría sí, en la práctica no del todo. Es la trampa clásica del `seed`.

La idea del parámetro: `seed` fija el punto de partida del muestreo aleatorio. Si el sampling es el único componente aleatorio, mismo seed + mismos inputs (prompt, temperature, top_p, modelo, todos los demás params) debería darte la misma salida. Sirve para reproducibilidad — debuggear, testear, evals.

Por qué en la práctica no garantiza determinismo total:

1. **Hardware / paralelización**: las operaciones en GPU con floating point no son perfectamente asociativas. El orden en que se acumulan las sumas puede variar según cómo se paraleliza, y eso cambia mínimamente los logits. Un logit que cambia en el sexto decimal puede, en un empate cerrado, elegir otro token — y a partir de ahí la respuesta diverge.

2. **Batching**: si tu request se procesa junto a otros (como pasa en servidores compartidos), el batch afecta el cálculo. No controlás con quién te toca compartir batch.

3. **Cambios del lado del provider**: si actualizan el modelo, cambian la infra, o reenrutan a otra versión, el seed deja de mapear a lo mismo. Por eso OpenAI acompaña el seed con un `system_fingerprint` — si ese fingerprint cambia, te avisan que la reproducibilidad no está garantizada.

4. **Temperature = 0 no es lo mismo que seed**: T=0 te da *greedy* (siempre el token más probable), que tiende a ser más estable, pero por el punto 1 tampoco es 100% determinista. Y con T>0, el seed es lo que fija el "azar".

El resumen honesto: mismo seed → respuestas muy parecidas o idénticas la mayoría de las veces. Pero es "best effort", no una garantía. Si necesitás determinismo real y duro, no lo vas a conseguir vía API pública — lo lográs solo corriendo el modelo vos mismo, con hardware fijo, batch de tamaño 1, y kernels deterministas.

---

**Q: La temperara aplana los valores. Ahora, cual es el criterio de seleccion de esa palabras.**

La temperatura **arma** la distribución, pero la selección en sí la hace otro mecanismo: el **sampling**.

Los dos pasos separados:

1. **Temperature** deforma la distribución de probabilidades (la aplana o la afila).
2. **El sampler** es el que efectivamente *elige* un token de esa distribución.

La temperatura no selecciona nada. Solo cambia las probabilidades con las que después se juega la selección.

Cuál es el criterio de selección: una vez que tenés las probabilidades finales (ej: A=0.48, B=0.29, C=0.23), se hace un **muestreo aleatorio ponderado**. Imaginá una ruleta donde cada token ocupa una porción proporcional a su probabilidad:

- A ocupa el 48% de la ruleta
- B el 29%
- C el 23%

Se tira un número aleatorio entre 0 y 1 (acá entra el `seed`), y cae en la porción que corresponda. No es "el más probable gana siempre" — es "cada uno gana proporcional a su tajada".

Técnicamente se hace con la CDF (suma acumulada):

```
A: 0.00 – 0.48
B: 0.48 – 0.77
C: 0.77 – 1.00
```

Sale el random (ej: 0.63) → cae en el rango de B → se elige B.

Los otros parámetros *recortan* la ruleta antes de tirar:

- **top_k**: dejá solo los K tokens más probables, el resto probabilidad 0.
- **top_p (nucleus)**: dejá solo los tokens que sumen p de probabilidad acumulada. Descarta la cola larga.
- **min_p**: descartá todo lo que esté por debajo de un umbral relativo al token top.

El pipeline completo:

```
logits → [temperature deforma] → [top_k/top_p/min_p recortan] →
         → normalizar → muestreo aleatorio ponderado (con seed) → token elegido
```

El caso límite: con **temperature = 0**, la distribución se afila tanto que un token se lleva ~toda la probabilidad. Ahí el muestreo deja de ser aleatorio de hecho y siempre cae en el más probable — eso es *greedy decoding* / *argmax*.

---

**Q: Agrega top_k en la lista.**

`top_k` no se puede tocar en ninguno de los tres chats web. Igual queda explícito que no está expuesto:

| Parámetro / Modo | claude.ai (web) | ChatGPT web | Gemini (web) |
|-----------|-----------------|------------|------------|
| **temperature** | — | — | — |
| **top_k** | — | — | — |
| **response_format** (JSON) | — | X | X |
| **tools / function_calling** | — | X | X |
| **reasoning_effort** | — | X (o1/o3) | — |
| **deep research** (modo) | X (Research) | X | X |
| **model selection** | X | X | X |

`top_k` (como `temperature`, `top_p`, `min_p` y las penalties) es puro territorio de API. En el chat web ninguna de las tres lo expone.

---

**Q: Vamos a "reasoning_effort". Explicamelo en detalle**

`reasoning_effort` es el parámetro con el que le decís al modelo cuánto razonar internamente antes de responder. Es la perilla que gradúa el "thinking".

Qué controla en concreto: los modelos de razonamiento generan *tokens de razonamiento* ocultos antes de la respuesta final. `reasoning_effort` regula cuántos de esos tokens está dispuesto a gastar el modelo pensando.

Los niveles típicos:

- `minimal` — casi no razona, responde rápido (se agregó con GPT-5).
- `low` — razonamiento breve.
- `medium` — el default en general.
- `high` — razona a fondo, explora más caminos, chequea su propio trabajo.

El mecanismo por dentro: no cambia qué modelo usás. Es el mismo modelo, pero le das más o menos "cancha" para pensar. Con `high`, el modelo puede desarmar el problema en subpasos, considerar varios enfoques, descartar los que no cierran, y recién ahí responder.

| Effort | Calidad (en tareas difíciles) | Latencia | Costo |
|--------|------------------------------|----------|-------|
| minimal | baja | mínima | mínimo |
| low | media | baja | bajo |
| medium | buena | media | medio |
| high | máxima | alta | alto |

Los tokens de razonamiento se facturan (como tokens de salida) aunque no los veas.

Cuándo conviene:

- `minimal` / `low`: tareas simples, formato, extracción, clasificación, respuestas directas.
- `medium`: la mayoría de los casos, buen balance.
- `high`: matemática seria, lógica, código complejo, análisis multi-paso.

El detalle contra-intuitivo: más razonamiento no siempre es mejor. En tareas fáciles, un effort alto puede llevar al modelo a "pensar de más" (overthinking) y a veces empeorar la respuesta.

- **thinking** = la capacidad de razonar (el mecanismo).
- **reasoning_effort** = cuánto de esa capacidad activás (la perilla).

Diferencia con temperature: `temperature` toca *cómo samplea* cada token; `reasoning_effort` toca *cuánto piensa antes* de empezar a producir la respuesta. Son ejes independientes.

Nota sobre Anthropic: Claude expresa la misma idea distinto — en vez de niveles `low/medium/high`, le das un presupuesto de tokens para thinking (`thinking_budget`).

---

**Q: reasoning_effort vs effort en la UI?**

Son la misma idea, pero en dos capas distintas — uno es el nombre técnico en la API, el otro es cómo te lo presentan (renombrado y empaquetado) en la UI.

**`reasoning_effort` (API)**: es el parámetro crudo. En la API de OpenAI seteás reasoning_effort con varios niveles, que controla cuánto "pensamiento" interno hace el modelo. Valores tipo `minimal/low/medium/high`. Es el nombre "de máquina".

**"Effort" en la UI (ChatGPT)**: en el chat no ves el parámetro como tal. Ves un selector de nivel de esfuerzo en el model picker, con etiquetas en lenguaje humano. OpenAI lo renombró: antes eran Standard/Extended/Heavy; ahora el picker usa Instant, Medium (razonamiento estándar), High (razonamiento extendido), Extra High (el máximo), más Pro Standard y Pro Extended.

| UI (ChatGPT hoy) | Equivale a | Concepto API |
|---|---|---|
| Instant | sin thinking | (modelo Instant) |
| Medium | ex-"Thinking Standard" | reasoning_effort medio |
| High | ex-"Thinking Extended" | reasoning_effort alto |
| Extra High | ex-"Thinking Heavy" | reasoning_effort máximo |

Las diferencias clave:

1. **Granularidad**: en la API tenés el valor directo y limpio. En la UI te dan niveles pre-empaquetados con nombres que cambian seguido.
2. **Auto-routing**: en la API, si pedís `high`, es `high`. En el chat no necesariamente — hay una capa de ruteo automático encima que puede pisar tu elección ("elijo High pero a veces igual recibo una respuesta básica").
3. **Trace visible**: la UI te muestra el "Thinking" desplegable. En la API los tokens de razonamiento normalmente no te los devuelve.
4. **Acoplado al modelo, en la UI**: en el chat, el "effort" viene mezclado con la selección de modelo. En la API son ejes más separados.

El resumen: `reasoning_effort` = la perilla real, cruda, sin intermediarios (API). "effort" en la UI = esa misma perilla, pero renombrada, discretizada en niveles con nombre comercial, y con un auto-router encima.

---

**Q: Uno es el Agente vs el Modelo?**

No exactamente — son dos distinciones diferentes que se están cruzando.

La distinción API vs UI no es agente vs modelo. Es quién configura y cómo se presenta:

- API = seteás `reasoning_effort` crudo vos, en el request.
- UI = el mismo parámetro, pero renombrado en niveles y con un router encima.

En ambos casos, quien *ejecuta* el razonamiento es el modelo.

La distinción agente vs modelo es otra cosa:

- **Modelo** = la cosa que razona. Tiene la capacidad de thinking y la ejecuta.
- **Agente / capa que llama** = quien *setea* el parámetro. No razona; le instruye al modelo cuánto razonar.

`reasoning_effort` siempre lo fija la capa que llama (sea un agente, la app de ChatGPT, o tu código con la API). Lo que cambia entre "API" y "UI" es *cómo* esa capa te deja tocarlo:

| | Quién setea el effort | Cómo te lo presenta |
|---|---|---|
| **API directa** | vos, en el request | valor crudo (`low/medium/high`) |
| **Tu agente** | el config del agente | como vos lo definas |
| **UI de ChatGPT** | la app de ChatGPT por vos | niveles con nombre + auto-router |

Dos ejes:

- Eje 1 (quién razona): capa que llama (agente/app/request) → configura; modelo → ejecuta.
- Eje 2 (cómo accedés a la config): API cruda vs UI empaquetada.

La UI de ChatGPT es solo un caso particular de "capa que llama" — una app que setea el effort por vos y te lo disfraza con nombres lindos.

---

**Q: En Claude, no es esto el agente cuanto itera la respuesta?**

No. El "thinking" de Claude no es un agente iterando la respuesta. Son mecanismos de niveles diferentes.

**Extended thinking en Claude = una sola pasada del modelo**: cuando Claude "piensa", genera tokens de razonamiento *antes* de la respuesta final, todo dentro de una única llamada al modelo. Es un monólogo interno lineal. No hay iteración, no hay loop, no hay múltiples llamadas.

**Un agente iterando = otra cosa, capa de arriba**: un agente es un loop *alrededor* del modelo: llama al modelo → mira el resultado → decide si vuelve a llamar → llama de nuevo. Eso son múltiples pasadas, orquestadas por código externo al modelo.

| | Extended thinking | Agente iterando |
|---|---|---|
| Qué es | Razonamiento interno del modelo | Loop de orquestación |
| Cuántas llamadas al modelo | Una | Varias |
| Quién controla | El modelo, adentro | Código/orquestador, afuera |
| Qué produce | Tokens de thinking + respuesta, en un tiro | Secuencia de acciones/llamadas |

Un agente puede, además, usar un modelo que tenga thinking activado. Se combinan: un agente que en cada iteración llama a un Claude con extended thinking. Son ejes independientes.

- `thinking_budget` → cuántos tokens de razonamiento usa el modelo en una llamada.
- Iteraciones del agente → cuántas llamadas hace el orquestador.

---

**Q: Pero tambien hay un Think**

Sí. El nombre "think" se usa para cosas distintas.

**1. Extended thinking**: el razonamiento interno del modelo, en una sola pasada, antes de responder. Regulado por `thinking_budget`.

**2. La "think tool" (herramienta)**: Anthropic definió una tool que se llama literalmente `think`. Es conceptualmente distinta:

- Es una herramienta que le das al modelo (como cualquier tool: search, calculator, etc.), no un modo de razonamiento interno.
- Cuando el modelo la "llama", lo que hace es parar a anotar/estructurar su pensamiento en un espacio dedicado, en medio de un flujo de trabajo con tools.
- No busca nada afuera, no cambia estado. Es un scratchpad.

| | Extended thinking | `think` tool |
|---|---|---|
| Qué es | Razonamiento interno del modelo | Una tool que el modelo invoca |
| Cuándo ocurre | Antes de empezar a responder | Durante un flujo con tools, entre pasos |
| Para qué sirve | Pensar el problema de entrada | Frenar a reflexionar *después* de recibir resultados de otras tools |
| Cómo se activa | Parámetro (`thinking` / budget) | Se la definís como tool disponible |

Por qué existe si ya hay extended thinking: extended thinking es bueno para razonar *antes* de arrancar. La think tool es para cuando el modelo, en medio de un flujo agéntico, ya llamó a otras tools, recibió resultados, y necesita detenerse a procesar esa info nueva antes de decidir el próximo paso.

Los tres "think" ordenados:

1. **Extended thinking** = razonamiento interno, una pasada, antes de responder (modo/param).
2. **`think` tool** = herramienta de scratchpad para reflexionar entre pasos de un flujo con tools.
3. **"Thinking" en la UI** = simplemente lo que te muestran del #1 (el bloque desplegable).

---

**Q: Vamos segun la documentacion como trabaja el effort.**

Según la documentación oficial de OpenAI:

Qué es, formalmente: un control a nivel de request que le indica al modelo cuánta profundidad de razonamiento asignar. Le decís al modelo cuántos tokens ocultos gastar en el chain-of-thought interno antes de escribir la respuesta final. No toca tu prompt ni el formato de salida.

Los valores: dependen del modelo y pueden incluir none, minimal, low, medium, high y xhigh. Menos effort favorece velocidad y menor uso de tokens; con más effort el modelo piensa de forma más completa para dar respuestas de mayor calidad.

Lo que pasa mecánicamente en cada nivel: en low, el modelo puede podar caminos de razonamiento temprano, devolviendo la primera solución razonable; en high, explora múltiples ramas de razonamiento, hace backtrack si es necesario, y verifica su propio trabajo antes de responder.

El detalle adaptativo: no es un presupuesto fijo y ciego. Los modelos razonan de forma adaptativa dentro de cada nivel de effort, usando menos tokens para tareas simples y pensando más para tareas complejas. El effort pone el techo/intensidad, pero el modelo modula dentro de eso según la dificultad real.

Defaults (dependen del modelo):

- gpt-5.5 usa medium por defecto.
- gpt-5.1 tiene reasoning_effort en none por defecto; al migrar desde modelos de razonamiento previos, puede que necesites pasar explícitamente un nivel si querés que ocurra razonamiento.
- gpt-5-pro solo soporta effort high (es su default aunque no lo pases), y gpt-5.1-codex-max agrega el nivel xhigh.

Cómo se pasa en la API:

```json
reasoning: {
  "effort": "low",     // "low", "medium", "high"...
  "summary": "auto"    // resumen del razonamiento
}
```

Gotchas de la doc:

- Con reasoning models, varios parámetros clásicos quedan deshabilitados: temperature, top_p, presence_penalty, frequency_penalty, logprobs, top_logprobs, logit_bias y max_tokens no están soportados. Usás `max_completion_tokens` / `max_output_tokens` en su lugar.
- Las llamadas a tools en paralelo no se soportan cuando reasoning_effort está en minimal.

El resumen conceptual: `effort` = asignación de cómputo, no prompt engineering. A mayor nivel, no solo piensa más tiempo sino que habilita estrategias de razonamiento más caras (multi-rama, backtracking, auto-verificación), y modula adaptativamente según la dificultad.

---

**Q: Ok. Creo que esto hay que agregarlo a la tabla. (opción B: tabla nueva sobre cómo cada uno expone el effort/thinking)**

| | claude.ai (web) | ChatGPT web | Gemini (web) | API (OpenAI) | API (Claude) |
|---|---|---|---|---|---|
| **Cómo se llama** | Extended thinking | Thinking / effort | Thinking | `reasoning_effort` | `thinking` + budget |
| **Cómo se expresa** | on/off (según modelo) | niveles con nombre | on/off | niveles: none/minimal/low/medium/high/xhigh | presupuesto de tokens |
| **Niveles visibles** | — | Instant / Medium / High / Extra High | — | none…xhigh | vos ponés el nº de tokens |
| **Granularidad** | baja (binario) | media (4 niveles) | baja (binario) | alta (6 niveles) | máxima (token exacto) |
| **Auto-router encima** | sí (decide el sistema) | sí (puede pisar tu elección) | sí | no | no |
| **Trace visible** | sí (bloque desplegable) | sí (al elegir manual) | sí | no (tokens ocultos) | resumen/parcial |
| **Quién lo setea** | la app | la app (+ vos, parcial) | la app | vos (request) | vos (request) |

Tres ideas clave:

1. UI = niveles empaquetados con nombre + auto-router; API = control crudo (niveles finos en OpenAI, tokens exactos en Claude).
2. El comportamiento por nivel (según doc OpenAI): a effort bajo poda temprano y agarra la primera solución razonable; a effort alto explora varias ramas, hace backtracking y verifica su trabajo.
3. OpenAI usa niveles, Claude usa presupuesto de tokens — misma familia conceptual, uno discretiza y el otro te da el dial continuo.

---

**Q: Vamos mas in depth como funciona. El modelo en un transformer genera la siguiente palabra. Como se conecta esto?**

La clave es una restricción del transformer que lo explica todo:

**Un transformer hace una cantidad FIJA de cómputo por token**: cada token que genera el modelo pasa por el mismo forward pass: la misma cantidad de capas, la misma cantidad de operaciones. Un token "fácil" y un token "difícil" consumen exactamente el mismo cómputo. El modelo no puede pensar más fuerte en un solo token — la profundidad del cálculo está fija por la arquitectura.

Consecuencia: la única forma de gastar más cómputo en un problema es generar más tokens. No hay otra palanca.

**Los "reasoning tokens" son tokens comunes**: cuando el modelo "razona", no activa un módulo especial. Genera tokens de pensamiento con exactamente el mismo mecanismo de next-token prediction que usa para todo lo demás. Logits → temperature → sampler → token elegido. Un "token de thinking" y un "token de respuesta" son indistinguibles a nivel de máquina. El chain-of-thought es literalmente el modelo prediciendo la siguiente palabra, solo que esas palabras van a un scratchpad interno en vez de a la respuesta final.

**El truco: el contexto es una memoria de trabajo**: cada token que el modelo genera se appendea al contexto, y los tokens siguientes lo pueden leer vía self-attention.

```
Problema → [genera paso 1] → paso 1 ahora está en el contexto →
         → [genera paso 2, atendiendo al paso 1] → paso 2 en contexto →
         → [genera paso 3, leyendo 1 y 2] → ... → [respuesta final]
```

El modelo escribe resultados intermedios y después se los lee a sí mismo. Convierte un problema difícil que no entra en un solo forward pass en una secuencia de muchos forward passes, cada uno resolviendo un pedacito, con los parciales guardados en el contexto. Esto es *test-time compute*: cómputo en serie. El contexto es la cinta de una máquina de Turing improvisada.

**Dónde entra el `effort`**: si el razonamiento es "generar más tokens antes de responder", controlar el effort es controlar cuántos tokens de pensamiento genera antes de cortar y pasar a la respuesta.

¿Cómo se decide ese "cortar"? El modelo tiene, entre todos los tokens posibles, uno especial que significa *"listo, dejo de pensar y empiezo a responder"* (un token de fin-de-thinking). En cada paso, ese token compite con los demás en la distribución de probabilidad.

- El modelo fue entrenado con RL para generar cadenas de razonamiento y para aprender *cuándo* emitir ese token de corte según la dificultad.
- El `effort` es una señal de condicionamiento que se mete en el contexto. Como el modelo se entrenó con esa señal correlacionada a la longitud del razonamiento, condicionar en "high" reshape la distribución del próximo token: baja la probabilidad de emitir el token de "ya terminé" temprano, y sube la de seguir generando pasos.

`effort` no es un mecanismo aparte. Es un sesgo sobre la decisión next-token de "sigo pensando vs. respondo ya".

El resumen de la cadena completa:

1. Transformer = cómputo fijo por token, siempre next-token prediction.
2. Como el cómputo por token es fijo, más "esfuerzo" = obligatoriamente más tokens.
3. Los tokens de razonamiento se generan con el pipeline idéntico (incluida temperature/sampling).
4. El contexto funciona de scratchpad: el modelo escribe y se relee vía attention → cómputo en serie.
5. `effort` = señal aprendida por RL que sesga *cuándo* el modelo emite el token de "dejo de pensar".

Por eso lo de la doc de OpenAI cierra: "high" habilita multi-rama + backtracking + auto-verificación no porque haya un algoritmo nuevo, sino porque hay presupuesto de tokens para escribir esas ramas y esas verificaciones como texto, y el modelo aprendió a usarlos.

---

**Q: Y por que temperatura se depreco en funcion de esto?**

Temperature se deshabilita en los reasoning models por una razón concreta: choca con lo que el RL entrenó.

**El razonamiento es una trayectoria aprendida, no texto libre**: cuando el modelo razona, está ejecutando una cadena de pasos donde cada token condiciona el siguiente. El RL entrenó esa trayectoria para que sea *correcta*.

Temperature mete ruido justo ahí. Y en una cadena larga de razonamiento, el ruido se acumula y se propaga:

- Un token de razonamiento medio raro (elegido por azar a temperature alta) no es como una palabra rara en prosa.
- Es un paso de cálculo equivocado que queda escrito en el contexto. Y como los pasos siguientes *leen* ese paso, arrastran el error. Un desvío temprano descarrila toda la cadena.

En prosa, temperature alta = "más creativo". En una cadena de razonamiento, temperature alta = "más chance de un paso lógico incorrecto que envenena el resto". No es creatividad, es error compuesto.

**El modelo ya tiene su propia gestión de aleatoriedad**: el reasoning model fue entrenado (vía RL) para manejar internamente cuándo explorar y cuándo consolidar. La exploración de ramas alternativas ya está codificada en la política aprendida, expresada como texto. La exploración que antes le pedías al modelo desde afuera subiendo temperature, ahora el modelo la hace desde adentro, escribiéndola como pasos de razonamiento.

Por qué directamente lo bloquean en vez de dejarlo en 1.0:

1. Esos parámetros se calibraron durante el entrenamiento RL a un régimen de sampling específico. Cambiarla en inference lo saca de la zona donde fue optimizado.
2. Las penalties son directamente dañinas acá: `frequency_penalty` / `presence_penalty` penalizan repetir tokens. Pero el razonamiento repite a propósito — reformula, vuelve sobre un valor, re-chequea un número.
3. Evitan que te pegues un tiro en el pie sin saber. La mayoría subiría temperature esperando "más creatividad" y en realidad estaría degradando la precisión del razonamiento.

| | Generación normal | Razonamiento |
|---|---|---|
| Cada token es | una palabra de la salida | un paso de cálculo que se relee |
| Un token "raro" | variación estilística inocua | posible error que contamina la cadena |
| La exploración | la inducís con temperature (afuera) | está en la política RL, escrita como texto (adentro) |
| Rol de temperature | perilla útil de creatividad | ruido que descarrila la trayectoria |

El cierre: en el modelo normal, *vos* gestionás el trade-off exploración/precisión con temperature. En el reasoning model, *el entrenamiento RL* ya se encargó de eso y lo hace de forma dirigida dentro del chain-of-thought. Se deprecó porque la aleatoriedad dejó de ser una perilla del usuario y pasó a ser parte de la política aprendida del modelo.

---

**Q: Que es RL?**

RL = Reinforcement Learning (aprendizaje por refuerzo).

La idea base: un paradigma de entrenamiento donde el modelo aprende por prueba y error a partir de recompensas, no copiando ejemplos.

1. El modelo produce algo (una respuesta, una cadena de razonamiento).
2. Se evalúa qué tan buena fue → se le da una recompensa (un puntaje: alto si estuvo bien, bajo si estuvo mal).
3. El modelo ajusta sus pesos para hacer más probable lo que dio recompensa alta y menos probable lo que dio baja.
4. Repetís millones de veces.

Con el tiempo, el modelo aprende una política (policy): una estrategia de qué token generar en cada situación para maximizar la recompensa esperada.

| | Pre-entrenamiento / Fine-tuning supervisado | RL |
|---|---|---|
| Cómo aprende | Imitando texto: "predecí la siguiente palabra de este ejemplo" | Por recompensa: "generá algo y te digo qué tan bueno fue" |
| La señal | La palabra correcta ya está en el dataset | Un puntaje sobre lo que el modelo produjo |
| Qué logra | Que suene bien, que sepa cosas | Que se comporte de cierta forma (útil, seguro, o que razone bien) |
| Analogía | Estudiar copiando de un libro | Practicar y recibir devolución de un entrenador |

El famoso RLHF (RL from Human Feedback): humanos rankeaban respuestas del modelo, con eso se entrenaba un "modelo de recompensa" que aprendía el gusto humano, y después RL optimizaba el LLM contra ese juez. Eso convirtió a los modelos crudos en asistentes útiles y educados.

Por qué RL es central para el razonamiento: los reasoning models se entrenan con RL pero con un giro clave: la recompensa muchas veces es automática y verificable, no humana.

Ejemplo: le das problemas de matemática con respuesta conocida. El modelo genera una cadena de razonamiento larga y llega a un resultado. Se chequea automáticamente: ¿el resultado es correcto? → recompensa alta. ¿Incorrecto? → baja. El modelo aprende qué cadenas de razonamiento llevan a respuestas correctas.

Lo potente: nadie le enseñó *cómo* razonar paso a paso. El modelo descubrió por sí mismo, a fuerza de recompensa, que le conviene desglosar, explorar ramas, hacer backtracking y verificar — porque esas estrategias correlacionan con llegar a la respuesta correcta y cobrar la recompensa.

El resumen de una línea: RL = entrenar por recompensa en vez de por imitación. En razonamiento, la recompensa es "¿llegaste a la respuesta correcta?", y de optimizar eso millones de veces sale, sola, la capacidad de pensar paso a paso.

---

**Q: En claude, hacer una tabla cuando temperature dejo de funcionar.**

Aclaración conceptual: en Claude, temperature nunca se "deprecó" de forma global. Lo que pasó es que se vuelve incompatible cuando activás extended thinking — y el thinking arrancó en Claude 3.7 Sonnet. En los modelos sin thinking, temperature sigue viva.

Cuándo temperature deja de estar disponible en Claude:

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

Lo que dice la doc textual:

- El thinking no es compatible con modificar temperature ni top_k, ni con forzar el uso de tools. Con thinking activado, solo podés tocar top_p entre 0.95 y 1.
- El error de validación clásico lo confirma: la temperatura solo puede fijarse en 1 cuando el thinking está habilitado. Si mandás otro valor con thinking on, el request falla.
- La regla general de Claude (independiente del thinking): conviene alterar temperature *o* top_p, pero no los dos a la vez.

El cambio de régimen:

- Claude 3.7 → Claude 4.x: usabas `thinking: {type: "enabled", budget_tokens: N}` — presupuesto de tokens explícito. Ahí ya temperature quedaba fija en 1 al activar thinking.
- Claude 4.7 / 4.8 en adelante: el default pasó a adaptive thinking (el modelo decide cuánto razonar por request) y aparecieron niveles de effort (incluido `xhigh`, entre `high` y `max`). Los modos por presupuesto de los modelos viejos ya no se usan en 4.7+.

El resumen: temperature en Claude no murió por decreto — murió condicionada al razonamiento. Cuando el modelo entra en modo de cadena de razonamiento (entrenada por RL), la aleatoriedad externa estorba, así que la API la clava en 1. En Opus 4.7/4.8, como el thinking es adaptativo y prendido por defecto, en la práctica el régimen normal ya es sin temperature configurable.
