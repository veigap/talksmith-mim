---
source_file: apertura-samsung-storyboard.md
source_type: chat-export
ingested_at: 2026-07-06
---

# Apertura con Samsung — el impacto de la IA, revelado de a capas

## Provenance
- Original location: llm-chats/apertura-samsung-storyboard.md
- Format: markdown (storyboard slide a slide de la secuencia de apertura, generado en sesión LLM)
- Author / source (if known): generado durante la sesión de trabajo LLM del proyecto; **no figura** en la tabla de "Archivos generados" de `registro-sesion-chat.md`, probablemente posterior a ese registro
- Date of original (if known): ca. 6 de julio de 2026 (contexto de la misma sesión de trabajo)

## Key claims
- **Concepto de apertura:** la sala no entiende "el problema" al principio, así que se usa el caso Samsung como una **historia que se revela de a capas**; cada slide agrega una capa de impacto. Título de la sección: *"El día que Samsung perdió el control (sin que nadie lo hackeara)."*
- **Objetivo declarado:** que la audiencia entienda, "en la piel", que **el mayor riesgo de la IA no es que te ataquen, sino perder el control de tus datos y romper lo que le prometiste a tus clientes** — y que eso pasa por decisiones cotidianas y bienintencionadas, no por negligencia.
- **Formato:** 10 slides, ~12–14 min. Cada slide se documenta con ficha (Título / Qué contiene / Objetivo) + puesta en escena (En pantalla / Guion / Interacción / Reacción esperada / Transición).
- Declara que **"reemplaza/enriquece los slides S1–S3 y S16–S22 del `esquema-slides.md`"** (archivo no presente en las fuentes).
- **Arco de los 10 slides:** (1) Portada — promesa de una historia real; (2) La escena, sin alarma — "Abril 2023 — Samsung habilita ChatGPT a sus ingenieros" (división de semiconductores); (3) Qué hicieron, totalmente razonable — los tres usos cotidianos; (4) La pregunta que nadie se hizo — "¿A dónde fue ese texto?"; (5) Capa 1: perdieron el control — "Ya no lo podían recuperar"; (6) Capa 2: sin red de protección legal — "Sin contrato, sin residencia, sin borrado" (tres palabras que se tachan en pantalla: NDA, Control de residencia, Derecho a borrar); (7) La revelación — "No hubo hackers / No hubo malware / No hubo intrusión. El dato salió por la puerta de adelante"; (8) Qué le costó a Samsung — el daño real, sin exagerar; (9) Las dos caras de la seguridad — la tesis de la charla; (10) El mapa de lo que sigue — cuatro partes: cómo funciona / cómo se rompe / qué te obliga / qué hacer.
- **Slide 7 es el "clic" de la charla:** el perímetro de seguridad no se rompió, **se esquivó**; las defensas clásicas (firewall, VPN, antivirus) no fueron diseñadas para un dato que sale voluntariamente de la mano de un empleado con permiso.
- **Slide 8 — honestidad sobre el daño:** no hay evidencia pública de robo por un competidor ni de desastre financiero medible; el daño real fue la **pérdida irreversible de control** + frenar una herramienta útil + quedar como el caso de estudio mundial. Frase ancla: *"El daño no fue que alguien lo usara. El daño fue que ya no podían controlarlo."* Respuesta de Samsung: prohibió la IA generativa, empezó a construir IA interna con límites estrictos.
- **Slide 9 — la tesis:** dos columnas — lo que imaginamos ("que me hackeen", candado roto) vs. lo que pasa de verdad ("perder el control de mis datos y romper lo que le prometí a mis clientes", puerta abierta). La seguridad tiene dos caras: protegerte de los que atacan **y** cumplir lo que prometiste; **la IA golpea sobre todo la segunda** — "y esa es la que casi nadie está mirando". Indicación explícita: "si se llevan un solo slide, es este".
- **Callback planificado (Bloque 8 / GDPR):** retomar las tres palabras tachadas del slide 6 y traducirlas — "sin NDA" → DPA / Art. 28; "sin control de residencia" → transferencia internacional / Arts. 44–49; "sin derecho a borrar" → derecho de supresión / Art. 17.
- **Principios de facilitación:** el motor de la apertura es **la pregunta, no la respuesta** (dejar que la sala piense y se equivoque en slides 3–5); **no definir términos técnicos todavía** (NDA, DPA, residencia, perímetro, API) — sembrarlos y prometer el callback; **tono cálido, sin catástrofe** — los protagonistas son excelentes profesionales, eso genera identificación ("me podría pasar a mí"); ritmo liviano en slides 2–4, lento desde el 5, **slide 7 el punto más lento** de la sección; sin imágenes de stock de "hacker con capucha" (contradice el mensaje).
- Adaptación por público: si la sala es de salud o finanzas, mencionar en el slide 8 que el mismo caso implicaría además **incumplimiento regulatorio directo** (HIPAA / datos financieros), no solo pérdida de control.

## Definitions and terminology
- **Revelado por capas** — estructura narrativa de la apertura: escena neutra → giro ("¿a dónde fue ese texto?") → capa 1 (pérdida de control) → capa 2 (sin red legal) → revelación (no hubo brecha) → costo → tesis → mapa.
- **"El dato salió por la puerta de adelante"** — metáfora central: perímetro esquivado, no roto.
- **Las tres palabras tachadas** — NDA · Control de residencia · Derecho a borrar; se siembran sin definir y "vuelven con nombre y apellido" (artículos GDPR) en el Bloque 8.
- **Las dos caras de la seguridad** — ataque externo vs. promesas incumplidas (compliance); tesis de la charla.
- Términos deliberadamente **no definidos** en la apertura: NDA, DPA, residencia de datos, perímetro, API.

## Evidence and examples
- Los tres usos de Samsung tal como se presentan al público (slide 3): (1) pegaron código fuente para encontrar un error; (2) pegaron código de un equipo de medición para optimizar su rendimiento; (3) subieron la grabación de una reunión interna para generar la minuta. Guion: "Nadie quería hacer nada malo. Nadie fue negligente. Es gente muy capaz tratando de ahorrarse tiempo. Todos hicimos algo parecido."
- Interacciones diseñadas: slide 2 — "pónganse en los zapatos de esos ingenieros… ¿qué harían?"; slide 3 — "levanten la mano los que ven acá un problema de seguridad" (contar las manos en voz alta; se espera que muy pocas se levanten); slide 5 — "hasta acá, ¿apareció algún hacker en esta historia?" (bajar el tono); slide 7 — silencio deliberado de 3–4 segundos, opcional "el antivirus más caro del mundo no lo hubiera frenado"; slide 6 — "guarden estas tres palabras; en un rato vuelven".
- Detalles de puesta en escena: slide 4 con fondo casi vacío y una sola frase grande centrada ("¿A dónde fue ese texto?"); slide 5 con tres líneas que aparecen de a una (no podían borrarlo / no sabían en qué servidor quedó / podía usarse para entrenar el modelo); slide 6 con las tres palabras tachadas con línea roja al nombrarlas; slide 7 con tres frases apiladas apareciendo de a una.
- Manejo de reacciones previsto: si alguien dice "¡yo no le pego nada!" en el slide 2 → "guardá esa respuesta, la retomamos en 10 minutos"; si hay caras de "¿qué es un NDA?" en el slide 6 → "si alguna no les suena, perfecto, es la idea; hoy salen sabiendo qué son".
- Slide 10 — mapa de la charla en 4 partes: (1) **Cómo funciona** — qué pasa cuando uso una IA (API, LLM como servicio); (2) **Cómo se rompe** — el perímetro, shadow AI, la inyección de prompts; (3) **Qué te obliga** — GDPR, HIPAA, estándares, Argentina; (4) **Qué hacer** — buenas prácticas para el lunes a la mañana. Cierre con agencia: *"Esto se puede manejar. Vamos a ver cómo."*

## Inconsistencies / open questions
- Referencia a `esquema-slides.md` (slides S1–S3 y S16–S22) — **ese archivo no está entre las fuentes entregadas**; la numeración de slides que este storyboard reemplaza no es verificable desde el corpus.
- Solapamiento de tiempos con la agenda: la apertura ocupa ~12–14 min con el caso Samsung completo, mientras `security-ai-managers-agenda.md` ubica el caso Samsung dentro del **Bloque 4** (14 min, con guion propio minuto a minuto) y asigna solo 7 min al Bloque 0 de apertura. Ambas fuentes usan la misma historia en posiciones distintas de la charla; cuál versión prevalece (o cómo se reparten) queda sin resolver.
- El storyboard no figura en la lista de archivos generados del registro de sesión — cronología de creación incierta.
- El slide 5 afirma "según los términos de la herramienta en ese momento, lo que pegabas podía usarse para seguir entrenando al modelo" — coherente con las demás fuentes, pero sin cita directa a los términos de OpenAI de 2023.

## Images / diagrams
Sin imágenes. La fuente es Markdown puro; describe elementos visuales de slides (íconos, tarjetas, tachados) pero no incluye archivos de imagen. Carpeta companion `apertura-samsung-storyboard.md/images/` creada y vacía (válido según esquema).

## Raw / preserved excerpts

Ficha de la sección (íntegra):

> - **Título:** *"El día que Samsung perdió el control (sin que nadie lo hackeara)."*
> - **Propuesta de alto nivel:** abrir la charla con un caso real contado como una historia que se pela de a capas; usar la sorpresa ("no hubo hackers") para redefinir qué significa la seguridad en la era de la IA y montar el mapa del resto de la charla.
> - **Objetivo (qué queremos que se lleven):** que entiendan, en la piel, que **el mayor riesgo de la IA no es que te ataquen, sino perder el control de tus datos y romper lo que le prometiste a tus clientes** — y que eso pasa por decisiones cotidianas y bienintencionadas, no por negligencia.
> - **Cantidad de slides:** 10. **Duración:** ~12–14 min. Reemplaza/enriquece los slides S1–S3 y S16–S22 del `esquema-slides.md`.

Slide 4 — guion (íntegro):

> "Cuando vos pegás algo en una herramienta de IA, sentís que se lo estás diciendo a un programa en tu compu. Pero no. Ese texto sale de tu máquina, viaja por internet y llega a los servidores de otra empresa —en este caso, los de OpenAI, en otro país. En el momento en que apretaron 'enviar', el código secreto de Samsung y la reunión interna **dejaron de estar dentro de Samsung**."

Slide 7 — guion (íntegro; el "clic" de la charla):

> "Acá está el corazón de toda la charla. Cuando pensamos en 'seguridad', imaginamos a alguien de afuera rompiendo un muro: un hacker, un virus, una intrusión. En el caso Samsung, el muro quedó perfectamente intacto. Nadie entró. El dato no fue robado: **salió caminando por la puerta de adelante, de la mano de un empleado con permiso.** El perímetro de seguridad no se rompió. Se esquivó. Y eso es algo para lo que la seguridad tradicional —el firewall, la VPN, el antivirus— no fue diseñada."

Slide 8 — guion (íntegro; el matiz honesto):

> "Seamos honestos y precisos, porque esto importa: no hay evidencia pública de que un competidor haya robado ese código, ni de un desastre financiero medible. Si les cuento que fue una catástrofe, les estaría mintiendo. Pero el daño real fue otro, más silencioso: perdieron el control de información confidencial de forma **irreversible**; tuvieron que frenar en seco una herramienta útil y salir a construir la suya; y quedaron como el ejemplo que todos citamos. El punto no es el tamaño de la multa. Es que el riesgo se materializó y no hay botón de 'deshacer'."

> **Interacción:** Frase para dejar grabada: *"El daño no fue que alguien lo usara. El daño fue que ya no podían controlarlo."*

Slide 9 — guion (íntegro; la tesis):

> "Casi todos, cuando escuchan 'seguridad', piensan en la izquierda: que alguien nos ataque. Pero lo que vimos con Samsung —y lo que va a pasar en sus empresas— vive en la derecha: datos que se escapan de nuestro control por decisiones cotidianas y bienintencionadas, y promesas de confidencialidad que le hicimos a nuestros clientes y que se rompen sin que nadie 'entre' a robar nada. La seguridad tiene dos caras: protegerte de los que atacan, **y** cumplir lo que prometiste. La IA golpea sobre todo la segunda. Y esa es la que casi nadie está mirando."

Notas para presentar (íntegras):

> - **El motor de la apertura es la pregunta, no la respuesta.** En los slides 3, 4 y 5, dejá que la sala piense y se equivoque antes de revelar. La pequeña incomodidad de "no vi el problema" fija el aprendizaje mejor que cualquier bullet.
> - **No definas términos técnicos todavía** (NDA, DPA, residencia, perímetro, API). Sembralos con lenguaje llano y prometé el *callback*. Sobre-explicar acá mata el ritmo.
> - **Tono: cálido, sin catástrofe.** Los protagonistas no son tontos: son excelentes profesionales. Eso es lo inquietante y lo que genera identificación ("me podría pasar a mí"). Si la sala siente que los estás retando, perdiste.
> - **Ritmo:** los slides 2–4 van livianos y rápidos; a partir del slide 5 bajás la velocidad. El slide 7 es el punto más lento de toda la sección.
> - **Callback planificado (anotalo para el Bloque 8 / GDPR):** retomá las tres palabras tachadas del slide 6 y traducilas: "sin NDA" → DPA / Art. 28; "sin control de residencia" → transferencia internacional / Arts. 44–49; "sin derecho a borrar" → derecho de supresión / Art. 17.
> - **Si el público es de salud o finanzas:** en el slide 8 mencioná que el mismo caso implicaría además incumplimiento regulatorio directo (HIPAA / datos financieros), no solo pérdida de control.
