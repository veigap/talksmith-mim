# Seguridad e IA para Managers — Agenda ampliada de 2 horas

*Público: managers que empezaron a usar herramientas de IA (Claude, ChatGPT, Copilot, etc.). No técnicos. Objetivo: criterio práctico, no ingeniería profunda.*

---

## Cómo leer este documento

La primera parte es la **agenda revisada de 2 horas** con tiempos. La segunda, **"Temas imprescindibles que no estaban en el esquema original"**, amplía el contenido que una charla de seguridad para managers no puede omitir con responsabilidad — con el tratamiento más profundo reservado para las **responsabilidades legales y el impacto de una filtración de datos**, porque es lo que convierte "interesante" en "tengo que actuar sobre esto".

Tu esquema original era un buen esqueleto *de alto nivel*. Los faltantes de abajo no son estilísticos: son los temas que, si se omiten, dejan a los managers expuestos justamente a los riesgos que la charla busca prevenir.

---

## Parte 1 — Agenda revisada de 2 horas

| # | Bloque | Tiempo |
|---|--------|--------|
| 0 | Apertura: por qué esto importa ahora | 7 min |
| 1 | Conceptos fundamentales (PII, residencia de datos, cifrado, **+ clasificación de datos, + perímetro de seguridad**) | 13 min |
| 2 | Detrás de escena: qué pasa realmente (camino API → LLM) | 14 min |
| 3 | MCP como un tipo especial de API | 7 min |
| 4 | **Responsabilidades y el impacto real de una filtración de datos (el eje central)** *(nuevo)* | 14 min |
| — | ☕ Pausa | 10 min |
| 5 | **Shadow AI y quién es responsable** *(nuevo)* | 9 min |
| 6 | Buenas prácticas con herramientas como Claude | 12 min |
| 7 | Rompemitos: qué es real y qué no | 7 min |
| 8 | Estándares y cumplimiento (HIPAA, GDPR, SOC 2, **EU AI Act**) | 8 min |
| 9 | ¿Y en Argentina? | 6 min |
| 10 | Inyección de prompts y la era de los agentes | 9 min |
| 11 | Cierre + hoja de una página para llevar | 4 min |

**Total: 120 min** (110 de contenido + 10 de pausa). Si hacés una demo en vivo, restá ~5 min de rompemitos y buenas prácticas.

Los dos bloques nuevos (4 y 5) son las incorporaciones "imprescindibles". El resto es tu esquema, reordenado para que cada amenaza aterrice solo después de que la audiencia tenga el modelo mental para entenderla.

---

## Parte 2 — Temas imprescindibles que no estaban en el esquema original

### Encuadre: qué es "seguridad" en este contexto *(Bloque 0)*

Antes de las amenazas, alineá la definición. Para un manager, "seguridad" tiene **dos caras**, y la IA golpea sobre todo la segunda:

- **Cara 1 — protección frente a terceros malintencionados.** Que un atacante no robe, altere o use tus datos. Es lo que la mayoría imagina cuando escucha "seguridad": hackers, malware, phishing.
- **Cara 2 — cumplir lo que le prometiste a tus clientes sobre cómo manejás sus datos.** Tu política de privacidad, tu contrato, tu NDA, tus obligaciones regulatorias. Esto es *compliance*, y es tan parte de la seguridad como la primera cara.

El punto clave para la sala: **podés no tener ningún hacker y aun así fallar en seguridad.** Si un empleado manda datos de un cliente a una herramienta que vos le dijiste al cliente que no usarías —o que simplemente no podés controlar ni auditar— ya incumpliste el compromiso. Nada se "filtró" en el sentido clásico (nadie los robó), y sin embargo hay una falla de seguridad y de cumplimiento. El caso Samsung y el anexo de GDPR son exactamente esto: no hubo atacante, hubo una promesa rota.

> **Frase para la lámina:** *"Una falla de seguridad no siempre tiene un atacante. A veces sos vos incumpliendo lo que prometiste sobre cómo cuidás los datos."*

---

### A. Responsabilidades y el impacto real de una filtración de datos *(el eje central)*

Esta es la sección que cambia comportamientos. Los managers rara vez actúan ante "es inseguro"; actúan ante "esto es lo que cuesta, y este es quién queda con su nombre en el caso". Cubrí cuatro dimensiones de impacto y después la rendición de cuentas.

**1. Los cuatro tipos de daño.** Una filtración nunca es solo un problema de IT:

- **Financiero** — remediación, forense, honorarios legales, multas regulatorias, notificación a clientes, monitoreo de crédito y pérdida de negocio. El costo global promedio de una filtración de datos en 2025 fue de **USD 4,44 millones**; en Estados Unidos alcanzó un récord de **USD 10,22 millones**. Incluso una filtración en una empresa chica trepa fácil a seis cifras.
- **Legal y regulatorio** — multas bajo la ley de protección de datos, reclamos por incumplimiento de contrato de clientes cuyos datos manejaste mal, y en sectores regulados, riesgo de licencia o certificación. Bajo GDPR, las sanciones llegan hasta el 4% de la facturación anual global.
- **Reputacional** — clientes perdidos, alianzas dañadas, cobertura de prensa. Es el más duradero y el más difícil de cuantificar.
- **Operativo** — caída de servicio, respuesta al incidente consumiendo a tu equipo, y el "impuesto de confianza" de controles más estrictos después.

**2. Por qué las herramientas de IA cambian la exposición.** Los datos de 2025 muestran el nuevo frente con números difíciles de ignorar:

- Las filtraciones que involucraron **shadow AI** costaron en promedio **USD 4,63 millones — USD 670.000 más** que un incidente estándar.
- **1 de cada 5 organizaciones (20%)** sufrió una filtración vinculada a shadow AI.
- De las organizaciones con filtraciones relacionadas con IA, el **97% no tenía controles de acceso adecuados**.
- El **63%** de las organizaciones filtradas **no tenía política de gobernanza de IA** o todavía la estaba desarrollando.
- El **83%** opera **sin controles básicos** para prevenir la exposición de datos a herramientas de IA (solo el 17% puede impedir técnicamente que un empleado suba datos confidenciales a una IA pública).
- Los incidentes de shadow AI comprometieron **más PII (65%)** y **más propiedad intelectual (40%)** que el promedio.

El mecanismo es simple: un empleado pega un contrato de un cliente, una historia clínica o código fuente en un chatbot de consumo, y ese dato ahora vive fuera de tu perímetro de control. Muchas veces no hay registro, ni contrato, ni forma de recuperarlo.

**3. Modos de falla concretos para nombrar en voz alta** (los managers recuerdan historias, no abstracciones):

- Datos sensibles pegados en una herramienta de consumo que entrena con lo que ingresás.
- Un documento generado por IA que filtra datos de otro cliente que el modelo vio antes (o que el *usuario* pegó antes en una cuenta compartida).
- Un agente/conector con permisos amplios ejecutando una acción no deseada (enviar un mail, borrar un archivo, exponer una carpeta).
- Credenciales o claves de API pegadas en un prompt y guardadas en el historial.

**4. Rendición de cuentas — la pregunta que todo manager se hace en secreto.** Hacela explícita: *"Si esto sale mal, ¿quién es responsable?"* La respuesta es incómoda y vale decirla sin vueltas: **la organización (y muchas veces el manager que autorizó o toleró el uso) es responsable, no el proveedor de IA.** Los términos del proveedor casi siempre se desligan de responsabilidad por lo que ingresás. "La IA lo hizo" no es una defensa legal ni profesional. Este único punto reencuadra toda la charla: de curiosidad a responsabilidad.

**5. Caso real: Samsung y ChatGPT (2023).** Nada aterriza el riesgo como una historia verdadera. En abril de 2023, **en menos de 20 días** de habilitar ChatGPT, Samsung tuvo **tres incidentes separados**: un ingeniero pegó código fuente de una base interna de semiconductores para que lo ayudara a corregir errores; otro subió código de medición de rendimiento y defectos de equipos para optimizarlo; y un empleado pasó la grabación de una reunión interna a texto y la pegó para generar la minuta. Resultado: propiedad intelectual confidencial —especificaciones de hardware, procesos de control de calidad, notas de reunión— quedó en servidores de un tercero **sin NDA, sin control de residencia de datos y sin posibilidad de borrarla**. Samsung terminó **prohibiendo** ChatGPT y anunciando el desarrollo de su propia IA interna.

La moraleja para la sala: no hubo hackers, ni malware, ni brecha en el perímetro. Fueron **empleados competentes tratando de trabajar más rápido**. Ese es exactamente el riesgo que este bloque busca prevenir — y por qué prohibir no alcanza (Bloque 5: hay que dar una alternativa autorizada).

> **Nota de secuencia (importante para presentar).** En el Bloque 4 el caso funciona con pura intuición: *el dato salió y no vuelve*. Los tres términos —"sin NDA", "sin control de residencia", "sin poder borrar"— recién cobran **peso legal** cuando explicás GDPR (Bloque 8 + anexo). Por eso conviene **plantar el gancho acá y hacer el *callback* después**: presentá Samsung ahora en lenguaje llano, y cuando llegues a GDPR volvé a él para traducir cada frase a su artículo. No definas NDA/DPA ni residencia en el Bloque 4 — solo sembralos.

> **Tip de facilitación:** corré esto como un escenario de 2 minutos. "Un miembro de tu equipo pega la lista completa de clientes en un chatbot gratuito para 'ordenarla'. Contame qué acaba de pasar — legal, financiera y reputacionalmente." Dejá que la sala se incomode antes de dar el marco.

---

### Guion sugerido para el Bloque 4 (14 min)

Un hilo posible para presentar el eje central, minuto a minuto:

- **(0–2 min) Gancho con el caso Samsung.** Contá la historia antes que cualquier número. "Tres fugas en veinte días, sin un solo hacker." Preguntá a la sala: *"¿A cuántos les pasó pegar algo del trabajo en una IA esta semana?"* — que levanten la mano. Esa es la puerta de entrada.
- **(2–5 min) Los cuatro tipos de daño.** Recorré financiero → legal → reputacional → operativo. Anclá con la cifra: **USD 4,44 M** promedio global, **USD 10,22 M** en EE. UU. El mensaje: "esto no es un problema de IT, es un problema de negocio".
- **(5–8 min) Por qué la IA cambia el juego.** Mostrá 2–3 estadísticas, no todas: **shadow AI +USD 670.000**, **97% sin controles de acceso**, **83% sin controles básicos**. La idea: la mayoría de las organizaciones están expuestas *hoy*.
- **(8–11 min) Modos de falla concretos.** Nombrá los cuatro escenarios (datos pegados, fuga cruzada, agente con permisos, credenciales en el prompt). Uno o dos, no los cuatro, según la sala.
- **(11–13 min) La pregunta incómoda.** *"Si esto sale mal, ¿quién es responsable?"* Dejá el silencio. Después: **la organización y el manager, no el proveedor.** "La IA lo hizo" no es defensa.
- **(13–14 min) Puente.** "La buena noticia: casi todo esto se previene con hábitos simples — a eso vamos ahora." Enlazá con Shadow AI (Bloque 5) y Buenas prácticas (Bloque 6).

**Tono:** serio pero no catastrofista. El objetivo no es asustar sino generar responsabilidad. Cerrá siempre con agencia: "esto se puede manejar".

---

### B. Clasificación de datos — el concepto fundamental que faltaba

Tu Bloque 1 cubre PII, residencia y cifrado, pero se saltea el concepto que los hace *accionables*: **no todos los datos son iguales.** Dales a los managers un modelo mental simple de 3 niveles que puedan aplicar esa misma tarde:

- **Público** — ya compartible (material de marketing, docs públicos). OK para cualquier herramienta.
- **Interno** — no secreto pero tampoco público (procesos internos, borradores de planes). OK solo en herramientas autorizadas y con contrato.
- **Confidencial / Regulado** — PII, datos de clientes, salud, financieros, credenciales, secretos comerciales. Nunca en herramientas de consumo; solo en herramientas empresariales con el contrato y los controles correctos.

La única regla para que se lleven: **"Antes de pegar, preguntá de qué nivel es este dato."**

---

### B-bis. El perímetro de seguridad — de on-prem a SaaS a IA *(concepto fundamental)*

Este es el concepto que hace que el caso Samsung (y toda la charla) tenga sentido. Contalo como una **evolución en tres etapas**: el perímetro no desapareció de golpe, se fue erosionando — y entender el arco explica por qué la IA *se siente* distinta.

**1. On-premise — "el castillo y el foso".** Durante décadas todo vivía adentro: servidores en tu edificio, datos en tu red. El perímetro era **físico y de red** (firewall, VPN). "Adentro seguro, afuera peligroso." Una **brecha de perímetro** era alguien rompiendo el muro desde afuera — un hackeo, malware, un phishing que da acceso a la red. Control total, pero también toda la responsabilidad sobre vos.

**2. SaaS / nube — el perímetro se vuelve contrato e identidad.** Los datos se mudaron a servidores de terceros (Google Workspace, Salesforce, Microsoft 365). El muro físico dejó de alcanzar, pero el perímetro **no desapareció: se transformó**. Pasó a ser **contratos e identidad** — DPAs, controles de acceso, SSO/MFA, logs de administración. "La identidad es el nuevo perímetro." Cediste control, sí, pero de forma **gobernada**: sabés qué proveedor, con qué contrato, con qué certificación (SOC 2), y quién accedió a qué.

**3. IA — el perímetro se corre hasta la persona.** Ahora el dato sale por una vía nueva: un empleado lo **pega en un chatbot**. Muchas veces sin contrato, sin control de acceso, sin log, y posiblemente usado para entrenar el modelo. No es una integración que TI aprobó — es una **decisión individual e invisible**. El perímetro se corrió hasta **la persona y su criterio**: qué pega y en qué herramienta.

| Etapa | Dónde viven los datos | Qué era el "perímetro" | ¿Gobernado? |
|-------|----------------------|------------------------|-------------|
| On-prem | Tu edificio / tu red | Muro físico y de red (firewall, VPN) | Sí — vos controlás todo |
| SaaS / nube | Servidores del proveedor | Contrato + identidad (DPA, SSO/MFA, logs) | Sí — de forma delegada |
| IA | Servidores del modelo | La persona y su criterio | **A menudo, no** |

**La idea clave para el manager.** Cada etapa cedió más control a cambio de más capacidad — eso no es nuevo ni malo. El salto peligroso de la IA **no es ceder control, es hacerlo sin gobernanza**: de forma individual, invisible e irreversible. Por eso en Samsung "no hubo hackers": no fue una brecha de perímetro, fue el perímetro simplemente **evitado**. Y por eso *gobernar* la IA es, en el fondo, **devolverle lo que la etapa SaaS ya tenía**: contrato (DPA), controles de acceso, logs y opción de borrado. Ese es el puente hacia todo lo que sigue — clasificación, herramientas autorizadas, mínimo privilegio.

> **Frase para la lámina:** *"El firewall no te protege de un dato que sale voluntariamente por la puerta de adelante. On-prem y SaaS movieron el perímetro; la IA lo puso en manos de cada empleado."*

---

### C. Shadow AI y la distinción consumo vs. empresa

Posiblemente el riesgo práctico #1 para los managers, y ausente del esquema. Cubrí:

- **Qué es shadow AI** — empleados usando herramientas de IA no autorizadas con datos de la empresa, de forma invisible. Está pasando en tu organización ahora mismo, esté o no autorizado.
- **Consumo vs. empresa/enterprise** — la diferencia que más importa: si tus datos se usan para entrenar el modelo, cuánto tiempo se retienen, y si hay un contrato (DPA) que te proteja. Las cuentas gratuitas/personales normalmente no ofrecen nada de esto; los planes business/enterprise en general sí.
- **La jugada del manager** — no prohibir (la gente esquiva las prohibiciones); *proveer una herramienta autorizada* y hacer que el camino seguro sea el camino fácil.

---

### D. Accesos, permisos y mínimo privilegio (especialmente para agentes/MCP)

Cuando introduzcas MCP y agentes (Bloque 3), tenés que acompañarlo con el control que los mantiene seguros. Los managers deben entender el **mínimo privilegio**: una herramienta o agente debe tener el acceso mínimo necesario para la tarea, y nada más. Un chatbot que solo responde preguntas es de bajo riesgo; un agente que puede leer todo tu disco y enviar mails en tu nombre es otra clase de riesgo. Conectá esto directo con el Bloque A: los permisos amplios son la forma en que un error chico se transforma en una filtración grande.

Nombrá también lo básico que previene la mayoría de los incidentes: **MFA / SSO, no compartir cuentas, y revisar a qué pueden acceder los conectores.**

---

### E. Riesgo de terceros / proveedores (la cadena de suministro de datos)

Cuando usás una herramienta de IA, no confiás solo en el proveedor sino en sus subprocesadores e infraestructura. Los managers deberían aprender a hacer tres preguntas al proveedor: *¿Entrenan con mis datos? ¿Cuánto tiempo los retienen? ¿Qué certificaciones (SOC 2, etc.) y contratos (DPA) ofrecen?* Esto conecta el bloque de estándares (SOC 2, GDPR) con una decisión de compra concreta.

---

### F. Factor humano: ingeniería social potenciada por IA

Una adición breve pero esencial: la amenaza no es solo que *tus* datos salgan; es que entren datos *fabricados*. La IA abarató y volvió convincentes el phishing, la clonación de voz y los deepfakes. Los managers deben saber que "se veía/sonaba real" ya no es verificación, y que las aprobaciones de movimiento de dinero o datos necesitan confirmación por un canal alternativo (out-of-band).

---

### G. La confiabilidad como tema de seguridad: alucinaciones y exceso de confianza

Los managers confunden "seguro de sí mismo" con "correcto". Encuadrá la alucinación no como una rareza sino como un *riesgo de decisión*: actuar sobre hechos fabricados, citas falsas o números equivocados es su propia clase de filtración — de confianza, de cumplimiento, de calidad. La regla: **la IA redacta, los humanos deciden; verificá todo lo que tenga consecuencias.**

---

### H. Estándares y cumplimiento, explicados uno por uno (Bloque 8)

Antes de entrar en cada uno, la distinción que evita la confusión más común: **GDPR y HIPAA son *leyes* — obligaciones que tu organización debe cumplir. SOC 2 es una *auditoría* — algo que un proveedor te muestra para probar que tiene controles.** No mezclarlos es la mitad del bloque.

**GDPR — Reglamento General de Protección de Datos (UE, 2018).** *Es una ley.*
- **Qué es:** el reglamento europeo de datos personales, hoy el estándar de referencia global.
- **A quién aplica:** a cualquier organización que trate datos de personas en la UE, esté o no radicada en la UE (alcance extraterritorial). Por eso te alcanza aunque estés en Argentina.
- **Qué exige:** base legal para tratar datos; derechos del titular (acceso, rectificación, **supresión / "olvido"**, portabilidad); principios de minimización, limitación de finalidad y responsabilidad proactiva (*accountability*); notificación de brechas en **72 horas**; contrato (DPA) con cada procesador; y reglas para transferir datos fuera de la UE.
- **Sanciones:** hasta **€20 millones o el 4% de la facturación global anual**, lo que sea mayor.
- **Ángulo IA:** es el estándar que la IA no gobernada rompe más fácil (ver el anexo de GDPR). Tu rol es el de *responsable del tratamiento*.

**HIPAA — Health Insurance Portability and Accountability Act (EE. UU., 1996).** *Es una ley (sectorial).*
- **Qué es:** la ley estadounidense que protege la información de salud (**PHI — Protected Health Information**).
- **A quién aplica:** a prestadores de salud, aseguradoras y a sus *business associates* (proveedores que manejan PHI en su nombre). Solo relevante si tu audiencia toca datos de salud.
- **Qué exige:** privacidad y seguridad de la PHI, controles de acceso, cifrado, notificación de brechas, y un contrato específico (**BAA — Business Associate Agreement**) con cualquier tercero que toque la PHI.
- **Ángulo IA:** si un empleado pega datos de salud en una herramienta que **no firmó un BAA**, ya hay incumplimiento. La mayoría de las IA de consumo **no** firman BAAs; los planes de salud dedicados o enterprise sí.

**SOC 2 — System and Organization Controls 2 (EE. UU., AICPA).** *No es una ley: es un reporte de auditoría.*
- **Qué es:** un informe de un auditor independiente sobre los controles de un proveedor, evaluados contra cinco criterios de confianza: **seguridad, disponibilidad, integridad de procesamiento, confidencialidad y privacidad**.
- **A quién aplica:** a proveedores de software/tecnología que quieren *demostrarle* a sus clientes que su postura de seguridad es seria. No es algo que *vos* cumplís; es algo que *ellos* te presentan.
- **Tipos:** **Type I** (los controles están bien diseñados en un momento dado) vs. **Type II** (los controles funcionaron de forma efectiva a lo largo del tiempo, típicamente 6–12 meses — el más valioso).
- **Ángulo IA:** es la pregunta de compra. *"¿Tienen SOC 2 Type II?"* es cómo un manager evalúa a un proveedor de IA. No garantiza que **tu** uso sea seguro, pero valida que el proveedor tiene los controles.

| Estándar | ¿Qué es? | ¿Quién cumple? | Foco |
|----------|----------|----------------|------|
| **GDPR** | Ley (UE, extraterritorial) | Tu organización | Datos personales, derechos del titular |
| **HIPAA** | Ley (EE. UU., salud) | Tu organización + sus proveedores | Datos de salud (PHI) |
| **SOC 2** | Auditoría (AICPA) | El proveedor te la muestra | Controles de seguridad del proveedor |

> **Frase para la lámina:** *"GDPR y HIPAA te dicen qué tenés que cumplir. SOC 2 es cómo un proveedor te prueba que puede ayudarte a cumplirlo."*

---

### I. EU AI Act — la primera ley amplia de IA (ampliación del Bloque 8)

Es el marco regulatorio de IA que más rápido se mueve y el que más conviene que los managers entiendan, aunque estén en Argentina: alcanza a cualquier organización cuyos sistemas de IA se usen o cuyos resultados se consuman en la UE. Presentalo en tres ideas simples.

**1. El modelo de niveles de riesgo (lo que hay que recordar).** La ley clasifica los usos de IA, no la tecnología en sí:

- **Riesgo inaceptable (prohibido)** — p. ej. scoring social, ciertos usos de reconocimiento biométrico. Simplemente no se permiten.
- **Alto riesgo** — IA en contratación, crédito, educación, salud, infraestructura crítica. Permitida pero con obligaciones fuertes (gestión de riesgo, calidad de datos, supervisión humana, documentación).
- **Riesgo limitado** — obligaciones de transparencia: avisarle a la gente que interactúa con IA o que un contenido es generado por IA (chatbots, deepfakes).
- **Riesgo mínimo** — la mayoría de los usos cotidianos; sin obligaciones nuevas.

**2. Fechas clave.** Las obligaciones para modelos de propósito general (**GPAI**) rigen desde el **2 de agosto de 2025**; el grueso de las reglas, incluida la transparencia, se vuelve aplicable el **2 de agosto de 2026**; las obligaciones de alto riesgo están escalonadas hacia **2027–2028**.

**3. Por qué le importa a un manager que "solo usa" herramientas.** Aunque no construyas IA, si tu organización *aplica* IA a decisiones sobre personas (Bloque G / decisiones automatizadas), podés caer en la categoría de "alto riesgo" y heredar obligaciones de transparencia y supervisión humana. Y como alcanza a proveedores fuera de la UE, condiciona qué herramientas y planes vas a poder usar. La regla práctica: **preguntá en qué nivel de riesgo cae tu caso de uso antes de desplegarlo.**

> **Puente con la Parte 3:** el EU AI Act empuja hacia los mismos controles que ya venís nombrando — política de uso aceptable, logging/auditabilidad, supervisión humana y derechos frente a decisiones automatizadas. No es un tema aparte: es el respaldo regulatorio de las buenas prácticas.

---

## Parte 3 — Preocupaciones restantes para incorporar

Una nota franca primero: **no todo esto entra en 120 minutos.** Cada punto está etiquetado como `[IMPRESCINDIBLE]` (va en la charla — integrar a un bloque existente) o `[SI HAY TIEMPO / PÚBLICO]` (cubrir solo si la sala es regulada, técnica, o si tenés un formato más largo). Tratá esto como el mapa completo de preocupaciones; después vos y yo podemos recortar para que entre.

### Ciclo de vida del dato y mecánica de privacidad

- **`[IMPRESCINDIBLE]` Retención, historial y borrado.** Los chats persisten. Los managers deben saber: dónde vive el historial, cuánto lo retiene el proveedor, si pueden borrarlo, y que "borrar" en la interfaz ≠ borrado de los sistemas del proveedor. Se conecta con el derecho de supresión del GDPR.
- **`[IMPRESCINDIBLE]` Opt-out de entrenamiento y revisión humana.** Más allá de consumo vs. empresa: algunos proveedores usan las entradas para entrenar modelos *y* tienen humanos que revisan conversaciones marcadas. Los managers deben saber dónde está el interruptor de opt-out y no asumir que viene "apagado por defecto".
- **`[IMPRESCINDIBLE]` Minimización de datos y redacción.** El control más barato de todos: compartir el *mínimo* dato necesario, y redactar/seudonimizar (quitar nombres, IDs, números de cuenta) *antes* de pegar. Un hábito práctico, no una política.
- **`[SI HAY TIEMPO]` Mecánica de transferencia internacional.** Conecta "residencia de datos" con los instrumentos legales que hacen lícita la transferencia (decisiones de adecuación, cláusulas contractuales tipo). Relevante para datos de la UE/Argentina que salen de la región.

### Legal, propiedad intelectual y titularidad

- **`[IMPRESCINDIBLE]` ¿De quién es la salida? PI y derechos de autor.** ¿Podés usar comercialmente el texto/código/imagen generado por IA? ¿El proveedor reclama derechos? ¿La salida podría infringir el copyright de otro? Un riesgo comercial vivo que los managers aprueban sin saberlo.
- **`[IMPRESCINDIBLE]` Confidencialidad y obligaciones contractuales.** Pegar datos de un cliente/empleador en una herramienta no autorizada puede violar NDAs, contratos con clientes o deberes de secreto profesional (legal, médico, contable) — independientemente de cualquier "filtración".
- **`[SI HAY TIEMPO]` Consentimiento y transparencia hacia los clientes.** En muchos regímenes tenés que avisarle a la gente cuando la IA procesa sus datos o toma decisiones sobre ellos.

### Riesgos específicos de IA más allá de la inyección de prompts

- **`[IMPRESCINDIBLE]` Decisiones automatizadas, sesgo y equidad.** Si la IA influye en decisiones sobre personas (contratación, crédito, precios, beneficios), puede discriminar y generar exposición legal. Tanto el GDPR como la reforma propuesta en Argentina otorgan derechos frente a decisiones exclusivamente automatizadas — nombralo explícitamente.
- **`[SI HAY TIEMPO]` Jailbreaking vs. inyección de prompts.** Distinto de la inyección: usuarios que a propósito empujan al modelo más allá de sus salvaguardas. Importa si tu organización *construye* una función de IA, menos si solo *usa* herramientas.
- **`[SI HAY TIEMPO]` Procedencia del modelo / cadena de suministro.** De dónde viene el modelo, open-source vs. alojado, correr modelos locales — para el público más técnico.

### Gobernanza y controles organizacionales

- **`[IMPRESCINDIBLE]` Política de Uso Aceptable de IA.** El artefacto más útil que un manager puede impulsar: una página de "qué está permitido, qué no, qué herramientas, qué datos". Sin ella, todo lo anterior es solo concientización.
- **`[IMPRESCINDIBLE]` Registro (logging), auditabilidad y monitoreo.** ¿Podés probar *qué* se compartió, *quién* y *cuándo*? Las herramientas empresariales dan logs de administración; las de consumo no. Esto es lo que hace posible siquiera la respuesta a incidentes y el cumplimiento.
- **`[IMPRESCINDIBLE]` Capacitación y cultura.** Las herramientas no causan filtraciones — los hábitos sí. El camino seguro tiene que ser el fácil, y la gente tiene que sentirse segura para *reportar* errores en lugar de esconderlos.
- **`[SI HAY TIEMPO]` Riesgo interno (insider).** Empleados descuidados o maliciosos moviendo datos a través de herramientas de IA; la razón por la que existen el mínimo privilegio y el logging.
- **`[SI HAY TIEMPO]` Disponibilidad, continuidad y dependencia del proveedor (lock-in).** Qué pasa si la herramienta se cae, cambia los términos, o necesitás irte — continuidad del negocio, no solo confidencialidad.

### Higiene del endpoint y de la cuenta (el asiento del humano)

- **`[IMPRESCINDIBLE]` Secretos en los prompts.** Nunca pegar contraseñas, claves de API ni tokens — quedan en el historial y en los logs. Merece una advertencia dedicada de 60 segundos.
- **`[SI HAY TIEMPO]` Básicos de dispositivo y cuenta.** MFA/SSO (ya en el Bloque D), más dispositivos bloqueados, sin logins compartidos, y cuidado con extensiones/plugins de navegador que leen las sesiones de IA.

### Estándares para sumar al Bloque 8

Tu bloque de estándares lista HIPAA, GDPR, SOC 2 — **sumá la capa específica de IA**, porque es el área que más rápido se mueve:

- **`[IMPRESCINDIBLE]` EU AI Act.** La primera ley amplia de IA. Las obligaciones de GPAI (modelos de propósito general) rigen desde el **2 de agosto de 2025**; el grueso de las reglas, incluida la transparencia, se vuelve aplicable el **2 de agosto de 2026**, con las obligaciones de alto riesgo escalonadas hacia **2027–2028**. Incluso organizaciones fuera de la UE se ven afectadas si atienden usuarios de la UE. Presentá la idea de *niveles de riesgo* (prohibido / alto riesgo / limitado / mínimo) — los managers la captan al instante.
- **`[SI HAY TIEMPO]` ISO/IEC 42001 y NIST AI RMF.** Los marcos de "cómo gobernamos la IA de forma responsable" que adopta una organización que madura; se combinan con ISO 27001 y SOC 2 del lado de seguridad.

---

## Parte 4 — Rompemitos: 5 preguntas para correr (Bloque 7)

Corré cada una como un rápido "levanten la mano: ¿verdadero o falso?" antes de revelar la respuesta. Están ordenadas para que cada una *siembre un aprendizaje* que un bloque posterior después paga — el rompemitos se vuelve el anzuelo, no un desvío.

**1. "Todo lo que escribo en un chatbot de IA se usa para entrenarlo y podría aparecer en la respuesta de otra persona."**
*Realidad:* En parte cierto, y depende enteramente de la herramienta y el plan. Muchas cuentas **de consumo/gratuitas** sí entrenan con lo que ingresás; la mayoría de los planes **business/enterprise** contractualmente no. Que "reaparezca" textual es raro, pero la retención y la revisión humana son reales. → *Introduce:* consumo vs. planes empresariales, opt-out de entrenamiento **(siembra el Bloque 6, Buenas prácticas).**

**2. "Si es un proveedor grande y confiable (Microsoft, Google, OpenAI), mis datos están automáticamente seguros y en cumplimiento."**
*Realidad:* Falso. La buena seguridad de un proveedor no es *tu* cumplimiento, y sus términos casi siempre se desligan de responsabilidad por lo que ingresás. Igual necesitás el plan correcto, un acuerdo de tratamiento de datos (DPA) y tus propios controles. **Vos seguís siendo responsable.** → *Introduce:* rendición de cuentas + riesgo de terceros **(siembra los Bloques 4 y 8).**

**3. "Si corro el modelo de IA en mis propios servidores (on-prem / local), mis datos están seguros."**
*Realidad:* Parcialmente cierto para *un* riesgo, y engañoso como afirmación general. Sí, correrlo local evita que el dato salga a un tercero — ese punto es real. **Pero "seguro" no es una propiedad del lugar, es una propiedad de la gobernanza:**

- On-prem te **devuelve toda la carga**: parches, controles de acceso, hardening, monitoreo, backups — sin el equipo de seguridad ni las certificaciones (SOC 2) que trae un buen proveedor SaaS.
- **Procedencia del modelo (cadena de suministro):** un modelo open-source que descargaste puede venir con sesgos, configuraciones inseguras o incluso manipulado. "Local" no significa "confiable".
- No te protege de inyección de prompts, de accesos mal configurados, ni de un empleado que filtra por otra vía.

El "clic" para la sala: **un SaaS gobernado (con DPA, accesos y logs) puede ser más seguro que un on-prem descuidado.** La seguridad no depende de *dónde* corre, sino de *cómo lo gobernás*. → *Introduce:* seguridad = gobernanza (no ubicación) + procedencia del modelo / cadena de suministro **(hace callback a B-bis on-prem→SaaS→IA y siembra la Parte 3).**

**4. "Borrar los nombres alcanza para que sea seguro pegar los datos."**
*Realidad:* Mayormente falso, y acá está el error más común de todos. Quitar el nombre parece hacer que el dato "deje de ser personal" — pero eso confunde **PII** (información que identifica *directamente*: nombre, DNI, email) con **datos personales** en el sentido de GDPR (cualquier dato *vinculable* a una persona identificable: IP, ubicación, comportamiento, incluso combinaciones). **PII es solo un subconjunto de los datos personales.** Si lo que queda permite reidentificar a la persona —solo o combinado con otra fuente— sigue siendo dato personal y sigue protegido. Además, los datos sensibles son más que nombres, y "borrar" en la interfaz no significa borrado del proveedor. Clasificá primero, minimizá siempre. → *Introduce:* **la distinción PI vs PII**, clasificación de datos, minimización y retención **(siembra el Bloque 1 y la Parte 3).**

**5. "Si la IA responde con seguridad y cita fuentes, es correcto."**
*Realidad:* Falso. Los modelos alucinan y pueden fabricar citas; la seguridad no es exactitud. Todo lo que tenga consecuencias tiene que ser verificado por un humano. → *Introduce:* la confiabilidad de la IA como riesgo de decisión — *la IA redacta, los humanos deciden* **(siembra el cierre).**

> **Facilitación:** primero la votación, después la revelación. La brecha entre las manos levantadas y la respuesta real es el momento de aprendizaje — y cada revelación es un tráiler de una línea de un bloque que todavía está por venir.

---

## Anexo auxiliar — IA y cumplimiento del GDPR (el rol de *data controller*)

**Sí, tu intuición es correcta.** Bajo el GDPR, tu organización es el **responsable del tratamiento (*data controller*)**: sos quien decide *qué* datos personales se procesan y *para qué*. Cuando un empleado pega datos personales en una herramienta de IA no gobernada, **no podés cumplir** — y no por un descuido, sino porque se rompen varias obligaciones a la vez. Es un buen tema para presentar justo después del eje central o dentro del Bloque 8.

**Callback al caso Samsung (usalo para abrir el anexo).** "¿Se acuerdan de las tres frases del caso? Ahora tienen nombre legal":

- *"Sin NDA"* → sin contrato de tratamiento (**DPA, Art. 28**): el proveedor procesa datos sin marco legal.
- *"Sin control de residencia de datos"* → **transferencia internacional ilícita (Arts. 44–49)**: el dato salió de la región sin garantías.
- *"Sin posibilidad de borrarla"* → **derecho de supresión (Art. 17) incumplible**: no podés ejecutar un pedido de borrado.

Lo que en el Bloque 4 era intuición, acá es incumplimiento con artículo y número. Ese es el "clic" que buscás en la sala.

Qué se rompe, en concreto:

- **Sin contrato con el procesador (Art. 28).** El proveedor de IA se convierte en un *procesador* de datos. El GDPR exige un contrato de tratamiento (DPA) con cláusulas específicas. Con una cuenta de consumo no hay DPA → tratamiento sin base contractual.
- **Derechos del titular imposibles de garantizar (Arts. 15–17).** Acceso, rectificación y, sobre todo, **supresión ("derecho al olvido")**. Este es el ejemplo más contundente para la sala: *un cliente ejerce su derecho y te pide que borres sus datos. Estás legalmente obligado a hacerlo. Pero el dato lo pegó un empleado en un chatbot no gobernado: no sabés en qué servidor quedó, si se usó para entrenar el modelo, ni cuántas copias existen — y no tenés forma de borrarlo.* En ese instante ya estás en incumplimiento, y no hay nada que puedas hacer *después*. El único momento para evitarlo era **antes**, gobernando qué herramienta se usa.
- **Transferencia internacional ilícita (Arts. 44–49).** El dato suele terminar en servidores fuera de la UE/región sin decisión de adecuación ni cláusulas contractuales tipo (SCCs). Residencia de datos rota.
- **Principios del Art. 5 violados.** Minimización (se comparte de más), limitación de la finalidad (el dato puede usarse para entrenar), y **responsabilidad proactiva (*accountability*)**: tenés que poder *demostrar* cumplimiento — y no podés demostrar algo que no ves.
- **Registro de actividades de tratamiento (Art. 30).** El shadow AI es invisible: si no sabés que está pasando, no está en tu registro. Incumplimiento por diseño.
- **Seguridad del tratamiento (Art. 32).** No hay garantía técnica ni organizativa sobre un canal que no controlás.
- **Decisiones automatizadas (Art. 22).** Si la IA influye en decisiones sobre personas, aparecen obligaciones adicionales de transparencia y supervisión humana.
- **Notificación de brecha (Arts. 33–34).** Una exposición de datos personales puede ser una brecha notificable **en 72 horas** — pero no podés notificar lo que no detectaste.

**La conclusión para el manager:** el cumplimiento del GDPR no depende de "tener cuidado" al usar la IA, sino de **gobernar qué herramienta se usa**. La única forma de seguir siendo un *data controller* que cumple es proveer una herramienta autorizada, con DPA, controles de acceso, logging y opción de borrado — es decir, mover el uso de shadow AI a IA gobernada. Esto conecta directo con el Bloque 5 (Shadow AI) y con la Política de Uso Aceptable de la Parte 3.

> **Frase para la lámina:** *"Como responsable del tratamiento, no podés delegar el cumplimiento en el buen criterio del empleado. Si la herramienta no está gobernada, el incumplimiento ya ocurrió — aunque nada se filtre."*

---

## Hoja de una página para llevar (para repartir)

1. **Clasificá antes de pegar** — público / interno / confidencial.
2. **Usá herramientas autorizadas y con contrato** para todo lo que no sea público.
3. **Mínimo privilegio** para cada conector y agente.
4. **Vos sos responsable, no el proveedor** — "la IA lo hizo" no es una defensa.
5. **Verificá la salida de la IA** que tenga consecuencias.
6. **Reportá los incidentes rápido** — la velocidad es el control más barato que tenés.

---

## Fuentes

- [IBM — Cost of a Data Breach Report 2025](https://www.ibm.com/reports/data-breach)
- [IBM Think — 2025 Cost of a Data Breach: Navigating the AI rush without sidelining security](https://www.ibm.com/think/x-force/2025-cost-of-a-data-breach-navigating-ai)
- [Help Net Security — Average global data breach cost now $4.44 million](https://www.helpnetsecurity.com/2025/08/04/ibm-cost-data-breach-report-2025/)
- [IBM Newsroom — 13% of organizations reported breaches of AI models/apps, 97% lacking proper AI access controls](https://newsroom.ibm.com/2025-07-30-ibm-report-13-of-organizations-reported-breaches-of-ai-models-or-applications,-97-of-which-reported-lacking-proper-ai-access-controls)
- [Kiteworks — How Shadow AI Costs Companies $670K Extra: IBM's 2025 Breach Report](https://www.kiteworks.com/cybersecurity-risk-management/ibm-2025-data-breach-report-ai-risks/)
- [Forbes — Samsung Bans ChatGPT Among Employees After Sensitive Code Leak (2023)](https://www.forbes.com/sites/siladityaray/2023/05/02/samsung-bans-chatgpt-and-other-chatbots-for-employees-after-sensitive-code-leak/)
- [European Commission — AI Act: regulatory framework](https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai)
- [EU AI Act — Implementation timeline](https://artificialintelligenceact.eu/implementation-timeline/)
- [IAPP — Novedades legislativas en Argentina sobre protección de datos personales e inteligencia artificial](https://iapp.org/news/a/novedades-legislativas-en-argentina-sobre-protecci-n-de-datos-personales-e-inteligencia-artificial)
- [Diario Judicial — ¿Sigue siendo suficiente la Ley 25.326 en 2026?](https://www.diariojudicial.com/news-103126-proteccion-de-datos-personales-sigue-siendo-suficiente-la-ley-25326-en-2026)
