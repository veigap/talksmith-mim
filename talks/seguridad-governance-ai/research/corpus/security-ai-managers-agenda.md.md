---
source_file: security-ai-managers-agenda.md
source_type: chat-export
ingested_at: 2026-07-06
---

# Seguridad e IA para Managers — Agenda ampliada de 2 horas

## Provenance
- Original location: llm-chats/security-ai-managers-agenda.md
- Format: markdown (agenda + desarrollo de contenidos generados en sesión LLM)
- Author / source (if known): generado durante la sesión de trabajo LLM del proyecto (ver `registro-sesion-chat.md.md`); construido sobre un esquema de alto nivel del usuario, reorganizado y ampliado
- Date of original (if known): sesión del 6 de julio de 2026 (según el registro de sesión)

## Key claims
- **Público objetivo:** managers no técnicos que empezaron a usar herramientas de IA (Claude, ChatGPT, Copilot). Objetivo: **criterio práctico, no ingeniería profunda**.
- **Agenda de 120 min** (110 de contenido + 10 de pausa), 12 bloques (0–11), con dos bloques nuevos "imprescindibles": **Bloque 4 — Responsabilidades y el impacto real de una filtración de datos (el eje central, 14 min)** y **Bloque 5 — Shadow AI y quién es responsable (9 min)**. Detalle completo de tiempos preservado en excerpts. Si hay demo en vivo, restar ~5 min de rompemitos y buenas prácticas.
- **Encuadre (Bloque 0) — las dos caras de la seguridad:** Cara 1 = protección frente a terceros malintencionados; Cara 2 = **cumplir lo que le prometiste a tus clientes** sobre el manejo de sus datos (compliance). Punto clave: **"podés no tener ningún hacker y aun así fallar en seguridad."**
- **Los cuatro tipos de daño de una filtración:** financiero, legal/regulatorio, reputacional (el más duradero), operativo. Cifras IBM 2025: costo global promedio **USD 4,44 millones**; EE. UU. récord de **USD 10,22 millones**; incluso en una empresa chica trepa a seis cifras.
- **Datos 2025 sobre shadow AI:** filtraciones con shadow AI costaron en promedio **USD 4,63 millones — USD 670.000 más** que un incidente estándar; **1 de cada 5 organizaciones (20%)** sufrió una filtración vinculada a shadow AI; **97%** de las organizaciones con filtraciones relacionadas con IA no tenía controles de acceso adecuados; **63%** sin política de gobernanza de IA (o en desarrollo); **83%** sin controles básicos (solo 17% puede impedir técnicamente subir datos confidenciales a una IA pública); incidentes de shadow AI comprometieron más PII (**65%**) y más propiedad intelectual (**40%**) que el promedio.
- **Rendición de cuentas — el punto que reencuadra la charla:** *"Si esto sale mal, ¿quién es responsable?"* → **la organización (y muchas veces el manager que autorizó o toleró el uso), no el proveedor de IA.** Los términos del proveedor casi siempre se desligan de responsabilidad. **"La IA lo hizo" no es una defensa legal ni profesional.**
- **Caso Samsung (abril 2023):** en menos de 20 días de habilitar ChatGPT, tres incidentes: (1) ingeniero pegó código fuente de una base interna de semiconductores para corregir errores; (2) otro subió código de medición de rendimiento y defectos de equipos para optimizarlo; (3) un empleado pasó la grabación de una reunión interna a texto y la pegó para generar la minuta. Resultado: IP confidencial en servidores de un tercero **sin NDA, sin control de residencia de datos y sin posibilidad de borrarla**. Samsung prohibió ChatGPT y anunció una IA interna. Moraleja: **no hubo hackers — fueron empleados competentes tratando de trabajar más rápido**; prohibir no alcanza (hay que dar alternativa autorizada).
- **Nota de secuencia pedagógica:** presentar Samsung en el Bloque 4 con pura intuición ("el dato salió y no vuelve") y hacer el *callback* legal en GDPR (Bloque 8 + anexo); no definir NDA/DPA/residencia en el Bloque 4 — solo sembrarlos.
- **Clasificación de datos — 3 niveles:** Público (OK cualquier herramienta) / Interno (solo herramientas autorizadas con contrato) / Confidencial-Regulado (nunca en herramientas de consumo). Regla: **"Antes de pegar, preguntá de qué nivel es este dato."**
- **El perímetro de seguridad — evolución en tres etapas:** on-prem ("castillo y foso", perímetro físico/de red) → SaaS/nube (perímetro = **contrato + identidad**: DPA, SSO/MFA, logs; "la identidad es el nuevo perímetro"; control cedido de forma gobernada) → IA (el perímetro se corre hasta **la persona y su criterio**; decisión individual e invisible). Idea clave: **el salto peligroso de la IA no es ceder control, es hacerlo sin gobernanza** — individual, invisible e irreversible. En Samsung el perímetro no se rompió: fue **evitado**. Gobernar la IA = devolverle lo que la etapa SaaS ya tenía (DPA, accesos, logs, borrado).
- **Shadow AI:** empleados usando IA no autorizada con datos de la empresa, de forma invisible; "está pasando en tu organización ahora mismo". Diferencia clave consumo vs. enterprise: entrenamiento con tus datos, retención, DPA. **La jugada del manager: no prohibir** (la gente esquiva las prohibiciones) sino **proveer una herramienta autorizada** y hacer que el camino seguro sea el fácil.
- **Mínimo privilegio (agentes/MCP):** una herramienta o agente debe tener el acceso mínimo necesario; un chatbot que responde preguntas es bajo riesgo, un agente que lee todo el disco y manda mails es otra clase de riesgo. Básicos: MFA/SSO, no compartir cuentas, revisar accesos de conectores.
- **Riesgo de terceros:** tres preguntas al proveedor — *¿Entrenan con mis datos? ¿Cuánto tiempo los retienen? ¿Qué certificaciones (SOC 2) y contratos (DPA) ofrecen?*
- **Ingeniería social potenciada por IA:** phishing, clonación de voz y deepfakes baratos y convincentes; "se veía/sonaba real" ya no es verificación; aprobaciones de dinero/datos requieren confirmación out-of-band.
- **Alucinaciones como riesgo de decisión:** "seguro de sí mismo" ≠ "correcto"; regla: **la IA redacta, los humanos deciden; verificá todo lo que tenga consecuencias**.
- **Distinción estructural del Bloque 8:** **GDPR y HIPAA son leyes** (tu organización cumple); **SOC 2 es una auditoría** (el proveedor te la muestra). SOC 2 Type I (diseño en un momento dado) vs. **Type II** (efectividad en el tiempo, 6–12 meses — el más valioso). *"¿Tienen SOC 2 Type II?"* es la pregunta de compra.
- **EU AI Act — primera ley amplia de IA:** clasifica **usos** (no la tecnología) en riesgo inaceptable (prohibido: scoring social, ciertos usos biométricos), alto riesgo (contratación, crédito, educación, salud, infraestructura crítica — obligaciones fuertes), riesgo limitado (transparencia: avisar que es IA / contenido generado), riesgo mínimo (sin obligaciones nuevas). Fechas: obligaciones **GPAI desde el 2 de agosto de 2025**; grueso de las reglas (incl. transparencia) **2 de agosto de 2026**; alto riesgo escalonado **2027–2028**. Alcanza a organizaciones fuera de la UE si sus sistemas/resultados se usan en la UE. Regla práctica: **preguntá en qué nivel de riesgo cae tu caso de uso antes de desplegarlo.**
- **Anexo IA + GDPR (rol de data controller):** cuando un empleado pega datos personales en una herramienta no gobernada, el incumplimiento es estructural — se rompen a la vez Art. 28 (sin DPA), Arts. 15–17 (derechos inejecutables, sobre todo supresión), Arts. 44–49 (transferencia ilícita), Art. 5 (minimización, finalidad, accountability), Art. 30 (registro), Art. 32 (seguridad), Art. 22 (decisiones automatizadas), Arts. 33–34 (brecha notificable en 72 h que no podés detectar). Conclusión: la única forma de cumplir es **gobernar qué herramienta se usa** (DPA, accesos, logging, borrado) — mover shadow AI a IA gobernada.

## Definitions and terminology
- **Shadow AI** — uso invisible de herramientas de IA no autorizadas con datos de la empresa.
- **Clasificación de datos (3 niveles)** — Público / Interno / Confidencial-Regulado.
- **Perímetro de seguridad** — evolución on-prem → SaaS → IA; "la identidad es el nuevo perímetro" (etapa SaaS).
- **Mínimo privilegio** — acceso mínimo necesario para la tarea, aplicado a agentes/conectores/MCP.
- **GPAI** — modelos de propósito general bajo el EU AI Act.
- **SOC 2 Type I vs. Type II** — diseño puntual vs. efectividad operativa a lo largo de 6–12 meses.
- **PII vs. datos personales** — PII identifica directamente; los datos personales del GDPR incluyen todo lo vinculable/reidentificable (PII es solo un subconjunto).
- **Out-of-band** — confirmación por canal alternativo para aprobaciones sensibles.
- Etiquetas de priorización: `[IMPRESCINDIBLE]` (va en la charla) vs `[SI HAY TIEMPO / PÚBLICO]` (solo si la sala es regulada/técnica o el formato es más largo).

## Evidence and examples
- **Cifras IBM 2025 (con fuentes):** USD 4,44M global / USD 10,22M EE. UU.; shadow AI +USD 670.000 (promedio USD 4,63M); 20% de organizaciones con filtración vinculada a shadow AI; 97% sin controles de acceso adecuados; 63% sin política de gobernanza; 83% sin controles básicos (17% con bloqueo técnico); 65% más PII y 40% más IP comprometida.
- **Caso Samsung 2023** con los tres incidentes detallados (fuente: Forbes, mayo 2023).
- **Cuatro modos de falla concretos:** (1) datos sensibles pegados en herramienta de consumo que entrena con lo ingresado; (2) documento generado por IA que filtra datos de otro cliente que el modelo vio antes (o que el usuario pegó antes en una cuenta compartida); (3) agente/conector con permisos amplios ejecutando acción no deseada (mail, borrado, carpeta expuesta); (4) credenciales o claves de API pegadas en un prompt y guardadas en el historial.
- **Guion minuto a minuto del Bloque 4 (14 min):** 0–2 gancho Samsung ("Tres fugas en veinte días, sin un solo hacker" + mano levantada "¿a cuántos les pasó pegar algo del trabajo en una IA esta semana?"); 2–5 los cuatro daños con cifras; 5–8 por qué la IA cambia el juego (2–3 estadísticas, no todas); 8–11 modos de falla (uno o dos según la sala); 11–13 la pregunta incómoda con silencio; 13–14 puente a Bloques 5 y 6. Tono: serio pero no catastrofista; cerrar con agencia ("esto se puede manejar").
- **Tip de facilitación (escenario de 2 min):** "Un miembro de tu equipo pega la lista completa de clientes en un chatbot gratuito para 'ordenarla'. Contame qué acaba de pasar — legal, financiera y reputacionalmente."
- **Rompemitos — 5 preguntas V/F** (íntegras en excerpts), ordenadas para que cada una siembre un bloque posterior: (1) "todo lo que escribo entrena al modelo" — en parte cierto, depende de herramienta y plan; (2) "proveedor grande = automáticamente seguro y en cumplimiento" — falso, vos seguís siendo responsable; (3) "on-prem/local es siempre más seguro" — parcialmente cierto para *un* riesgo y engañoso en general: **"seguro" no es una propiedad del lugar, es una propiedad de la gobernanza**; un SaaS gobernado puede ser más seguro que un on-prem descuidado; (4) "borrar los nombres alcanza" — mayormente falso: PII ⊂ datos personales; reidentificación; "borrar" en la interfaz ≠ borrado del proveedor; (5) "si responde con seguridad y cita fuentes, es correcto" — falso: alucinaciones y citas fabricadas.
- **Parte 3 — mapa completo de preocupaciones etiquetadas** (detalle en excerpts): retención/historial/borrado; opt-out de entrenamiento y revisión humana; minimización y redacción/seudonimización antes de pegar; transferencia internacional; titularidad de la salida (PI/copyright); confidencialidad y obligaciones contractuales (NDAs, secreto profesional); consentimiento hacia clientes; decisiones automatizadas/sesgo/equidad; jailbreaking vs. inyección de prompts; procedencia del modelo; Política de Uso Aceptable de IA ("el artefacto más útil que un manager puede impulsar: una página"); logging/auditabilidad; capacitación y cultura ("las herramientas no causan filtraciones — los hábitos sí"); riesgo insider; lock-in/continuidad; secretos en prompts (advertencia dedicada de 60 segundos); higiene de dispositivo/cuenta; ISO/IEC 42001 y NIST AI RMF.
- **Hoja de una página para llevar (6 reglas):** 1. Clasificá antes de pegar; 2. Usá herramientas autorizadas y con contrato; 3. Mínimo privilegio para cada conector y agente; 4. **Vos sos responsable, no el proveedor**; 5. Verificá la salida de la IA que tenga consecuencias; 6. Reportá los incidentes rápido — "la velocidad es el control más barato que tenés".

## Inconsistencies / open questions
- El documento reconoce explícitamente que **"no todo esto entra en 120 minutos"** — la Parte 3 es un mapa completo a recortar con el presentador ("después vos y yo podemos recortar para que entre"). El recorte quedó pendiente.
- Las estadísticas de shadow AI mezclan fuentes (IBM Cost of a Data Breach 2025 vía IBM, Help Net Security y Kiteworks); el "83% sin controles básicos" proviene de la síntesis de Kiteworks — verificar contra el informe primario de IBM antes de citar en lámina.
- El guion del Bloque 4 dice "mostrá 2–3 estadísticas, no todas" y "uno o dos [modos de falla], no los cuatro" — la selección concreta queda a criterio del presentador.
- Tensión menor de tiempos: la agenda asigna 14 min al Bloque 4, mientras el storyboard de apertura (`apertura-samsung-storyboard.md`) propone una apertura de ~12–14 min que "reemplaza/enriquece" slides de un `esquema-slides.md` — la relación exacta entre ambos cortes de la charla no está resuelta en las fuentes.
- Referencia a un archivo `esquema-slides.md` que **no existe** entre las fuentes entregadas (mencionado en el storyboard; la agenda tampoco lo incluye).

## Images / diagrams
Sin imágenes. La fuente es Markdown puro (tablas y emojis inline, sin archivos de imagen). Carpeta companion `security-ai-managers-agenda.md/images/` creada y vacía (válido según esquema).

## Raw / preserved excerpts

Agenda completa (íntegra):

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

> **Frase para la lámina:** *"Una falla de seguridad no siempre tiene un atacante. A veces sos vos incumpliendo lo que prometiste sobre cómo cuidás los datos."*

> **4. Rendición de cuentas — la pregunta que todo manager se hace en secreto.** Hacela explícita: *"Si esto sale mal, ¿quién es responsable?"* La respuesta es incómoda y vale decirla sin vueltas: **la organización (y muchas veces el manager que autorizó o toleró el uso) es responsable, no el proveedor de IA.** Los términos del proveedor casi siempre se desligan de responsabilidad por lo que ingresás. "La IA lo hizo" no es una defensa legal ni profesional. Este único punto reencuadra toda la charla: de curiosidad a responsabilidad.

> **5. Caso real: Samsung y ChatGPT (2023).** [...] En abril de 2023, **en menos de 20 días** de habilitar ChatGPT, Samsung tuvo **tres incidentes separados**: un ingeniero pegó código fuente de una base interna de semiconductores para que lo ayudara a corregir errores; otro subió código de medición de rendimiento y defectos de equipos para optimizarlo; y un empleado pasó la grabación de una reunión interna a texto y la pegó para generar la minuta. Resultado: propiedad intelectual confidencial —especificaciones de hardware, procesos de control de calidad, notas de reunión— quedó en servidores de un tercero **sin NDA, sin control de residencia de datos y sin posibilidad de borrarla**. Samsung terminó **prohibiendo** ChatGPT y anunciando el desarrollo de su propia IA interna.

> La moraleja para la sala: no hubo hackers, ni malware, ni brecha en el perímetro. Fueron **empleados competentes tratando de trabajar más rápido**. Ese es exactamente el riesgo que este bloque busca prevenir — y por qué prohibir no alcanza (Bloque 5: hay que dar una alternativa autorizada).

Tabla del perímetro (íntegra):

| Etapa | Dónde viven los datos | Qué era el "perímetro" | ¿Gobernado? |
|-------|----------------------|------------------------|-------------|
| On-prem | Tu edificio / tu red | Muro físico y de red (firewall, VPN) | Sí — vos controlás todo |
| SaaS / nube | Servidores del proveedor | Contrato + identidad (DPA, SSO/MFA, logs) | Sí — de forma delegada |
| IA | Servidores del modelo | La persona y su criterio | **A menudo, no** |

> **Frase para la lámina:** *"El firewall no te protege de un dato que sale voluntariamente por la puerta de adelante. On-prem y SaaS movieron el perímetro; la IA lo puso en manos de cada empleado."*

Rompemitos #3 (el reemplazado, íntegro por su valor):

> **3. "Si corro el modelo de IA en mis propios servidores (on-prem / local), mis datos están seguros."**
> *Realidad:* Parcialmente cierto para *un* riesgo, y engañoso como afirmación general. Sí, correrlo local evita que el dato salga a un tercero — ese punto es real. **Pero "seguro" no es una propiedad del lugar, es una propiedad de la gobernanza:**
> - On-prem te **devuelve toda la carga**: parches, controles de acceso, hardening, monitoreo, backups — sin el equipo de seguridad ni las certificaciones (SOC 2) que trae un buen proveedor SaaS.
> - **Procedencia del modelo (cadena de suministro):** un modelo open-source que descargaste puede venir con sesgos, configuraciones inseguras o incluso manipulado. "Local" no significa "confiable".
> - No te protege de inyección de prompts, de accesos mal configurados, ni de un empleado que filtra por otra vía.
> El "clic" para la sala: **un SaaS gobernado (con DPA, accesos y logs) puede ser más seguro que un on-prem descuidado.**

Tabla de estándares (íntegra):

| Estándar | ¿Qué es? | ¿Quién cumple? | Foco |
|----------|----------|----------------|------|
| **GDPR** | Ley (UE, extraterritorial) | Tu organización | Datos personales, derechos del titular |
| **HIPAA** | Ley (EE. UU., salud) | Tu organización + sus proveedores | Datos de salud (PHI) |
| **SOC 2** | Auditoría (AICPA) | El proveedor te la muestra | Controles de seguridad del proveedor |

> **Frase para la lámina:** *"GDPR y HIPAA te dicen qué tenés que cumplir. SOC 2 es cómo un proveedor te prueba que puede ayudarte a cumplirlo."*

Anexo GDPR — callback Samsung (íntegro):

> **Callback al caso Samsung (usalo para abrir el anexo).** "¿Se acuerdan de las tres frases del caso? Ahora tienen nombre legal":
> - *"Sin NDA"* → sin contrato de tratamiento (**DPA, Art. 28**): el proveedor procesa datos sin marco legal.
> - *"Sin control de residencia de datos"* → **transferencia internacional ilícita (Arts. 44–49)**: el dato salió de la región sin garantías.
> - *"Sin posibilidad de borrarla"* → **derecho de supresión (Art. 17) incumplible**: no podés ejecutar un pedido de borrado.
> Lo que en el Bloque 4 era intuición, acá es incumplimiento con artículo y número. Ese es el "clic" que buscás en la sala.

> **Derechos del titular imposibles de garantizar (Arts. 15–17).** [...] *un cliente ejerce su derecho y te pide que borres sus datos. Estás legalmente obligado a hacerlo. Pero el dato lo pegó un empleado en un chatbot no gobernado: no sabés en qué servidor quedó, si se usó para entrenar el modelo, ni cuántas copias existen — y no tenés forma de borrarlo.* En ese instante ya estás en incumplimiento, y no hay nada que puedas hacer *después*. El único momento para evitarlo era **antes**, gobernando qué herramienta se usa.

> **Frase para la lámina:** *"Como responsable del tratamiento, no podés delegar el cumplimiento en el buen criterio del empleado. Si la herramienta no está gobernada, el incumplimiento ya ocurrió — aunque nada se filtre."*

Hoja de una página (íntegra):

> 1. **Clasificá antes de pegar** — público / interno / confidencial.
> 2. **Usá herramientas autorizadas y con contrato** para todo lo que no sea público.
> 3. **Mínimo privilegio** para cada conector y agente.
> 4. **Vos sos responsable, no el proveedor** — "la IA lo hizo" no es una defensa.
> 5. **Verificá la salida de la IA** que tenga consecuencias.
> 6. **Reportá los incidentes rápido** — la velocidad es el control más barato que tenés.

Fuentes citadas por el documento original:
- IBM — Cost of a Data Breach Report 2025: https://www.ibm.com/reports/data-breach
- IBM Think — 2025 Cost of a Data Breach: Navigating the AI rush without sidelining security: https://www.ibm.com/think/x-force/2025-cost-of-a-data-breach-navigating-ai
- Help Net Security — Average global data breach cost now $4.44 million: https://www.helpnetsecurity.com/2025/08/04/ibm-cost-data-breach-report-2025/
- IBM Newsroom — 13% of organizations reported breaches of AI models/apps, 97% lacking proper AI access controls: https://newsroom.ibm.com/2025-07-30-ibm-report-13-of-organizations-reported-breaches-of-ai-models-or-applications,-97-of-which-reported-lacking-proper-ai-access-controls
- Kiteworks — How Shadow AI Costs Companies $670K Extra: IBM's 2025 Breach Report: https://www.kiteworks.com/cybersecurity-risk-management/ibm-2025-data-breach-report-ai-risks/
- Forbes — Samsung Bans ChatGPT Among Employees After Sensitive Code Leak (2023): https://www.forbes.com/sites/siladityaray/2023/05/02/samsung-bans-chatgpt-and-other-chatbots-for-employees-after-sensitive-code-leak/
- European Commission — AI Act: regulatory framework: https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai
- EU AI Act — Implementation timeline: https://artificialintelligenceact.eu/implementation-timeline/
- IAPP — Novedades legislativas en Argentina sobre protección de datos personales e inteligencia artificial: https://iapp.org/news/a/novedades-legislativas-en-argentina-sobre-protecci-n-de-datos-personales-e-inteligencia-artificial
- Diario Judicial — ¿Sigue siendo suficiente la Ley 25.326 en 2026?: https://www.diariojudicial.com/news-103126-proteccion-de-datos-personales-sigue-siendo-suficiente-la-ley-25326-en-2026
