---
source_file: gdpr-explicado.md
source_type: chat-export
ingested_at: 2026-07-06
---

# GDPR explicado — historia, evolución y puntos clave

## Provenance
- Original location: llm-chats/gdpr-explicado.md
- Format: markdown (documento de estudio generado en sesión LLM)
- Author / source (if known): generado durante la sesión de trabajo LLM del proyecto (ver `registro-sesion-chat.md.md`); documento de estudio para lector no jurídico
- Date of original (if known): sesión del 6 de julio de 2026 (según el registro de sesión)

## Key claims
- El **GDPR** (Reglamento General de Protección de Datos, formalmente Reglamento (UE) 2016/679) regula cómo cualquier organización puede recolectar, usar, guardar y compartir datos personales. Entró en aplicación el **25 de mayo de 2018** y es el estándar de referencia global de privacidad.
- Idea central — cambio de dueño: **"tus datos personales son tuyos, no de la empresa que los recolecta."** La empresa los "toma prestados" bajo condiciones estrictas.
- Razón de ser: a medida que la computación hizo trivial almacenar y cruzar información a escala masiva, el desbalance de poder se volvió peligroso (vigilancia, discriminación, manipulación, robo de identidad). Respuesta del GDPR: **quien trata datos personales tiene que rendir cuentas.**
- Evolución de ~50 años: 1970 primera ley del mundo (estado alemán de **Hesse**); 1973 primera ley nacional (**Suecia**); 1980 Directrices de la **OCDE** (fijan principios y vocabulario, no vinculantes); 1981 **Convenio 108** (primer tratado internacional vinculante, Consejo de Europa); 1995 **Directiva 95/46/CE** (antecesora directa); 2012–2016 reforma; adopción **14 de abril de 2016**; aplicación 25 de mayo de 2018; luego la era del *enforcement*.
- Debilidades de la Directiva 95/46/CE que el GDPR corrigió: era **directiva** (28 implementaciones nacionales distintas) y fue escrita **antes de Google, redes sociales, smartphones, nube y big data**. El GDPR, al ser **reglamento**, aplica directo e igual en toda la UE.
- **Sanciones en dos niveles:** hasta €10M o 2% de facturación global anual (incumplimientos "administrativos"); hasta **€20M o 4%** (violaciones de principios, bases legales o derechos). El cálculo sobre facturación global es lo que hace que las multinacionales lo tomen en serio.
- Enforcement real: **Meta €1.200 millones (mayo 2023)** — la mayor multa individual, por transferir datos de usuarios europeos a EE. UU. sin garantías; **Amazon €746 millones (2021)** — publicidad sin base válida; **Meta €390 millones (enero 2023)** — cambio de base legal sin transparencia; **2023–2024 acumularon ~€5.880 millones** en multas (Meta, Amazon, TikTok, LinkedIn, Clearview AI entre los principales).
- **"Efecto Bruselas":** por su alcance extraterritorial, el GDPR marcó el estándar de facto mundial e inspiró CCPA/CPRA (California), LGPD (Brasil) y los proyectos de reforma argentinos.
- **GDPR e IA:** como responsable del tratamiento, la organización sigue obligada aunque use herramientas de terceros. Sin DPA → encargado sin marco legal; datos a servidores fuera de la UE sin garantías → transferencia ilícita; derecho al olvido inejecutable si el dato quedó en una IA no gobernada; shadow AI sin registro → incumplimiento por diseño.
- Conclusión práctica: cumplir el GDPR con IA no depende de "tener cuidado" al escribir, sino de **gobernar qué herramienta se usa** (autorizada, con DPA, controles de acceso, logs y opción de borrado).
- **"¿Tiene DPA?" es la línea que separa una herramienta de IA gobernada de una shadow AI** — una de las primeras preguntas que un manager debería hacer antes de habilitar cualquier herramienta.

## Definitions and terminology
- **Datos personales** — *cualquier* información sobre una persona identificada o **identificable**: email, IP, ubicación, cookies, comportamiento de navegación, incluso inferencias. Definición mucho más amplia que la vieja noción estadounidense de "PII".
- **Categorías especiales (datos sensibles)** — salud, origen étnico/racial, opiniones políticas, religión, orientación sexual, datos biométricos y genéticos; protección reforzada.
- **Titular / interesado (*data subject*)** — la persona dueña de los datos.
- **Responsable del tratamiento (*data controller*)** — decide *qué* datos se tratan y *para qué*; carga con la responsabilidad principal. Prueba para distinguir: *¿quién decide para qué se usan los datos?*
- **Encargado del tratamiento (*data processor*)** — tercero que trata datos *en nombre* del responsable (nube, SaaS, liquidación de sueldos… y **una herramienta de IA**); solo ejecuta instrucciones.
- **DPA — Data Processing Agreement** — contrato obligatorio responsable↔encargado exigido por el **Art. 28**; sin DPA el tratamiento es directamente ilícito.
- **Bases legales (seis)** — consentimiento, ejecución de contrato, obligación legal, interés vital, interés público, interés legítimo. El consentimiento es la más conocida pero no la única.
- **Los 7 principios (Art. 5)** — (1) licitud, lealtad y transparencia; (2) limitación de la finalidad; (3) minimización; (4) exactitud; (5) limitación de la conservación; (6) integridad y confidencialidad; (7) **responsabilidad proactiva (accountability)**: poder **demostrar** que se cumple.
- **DPO** — Delegado de Protección de Datos; **DPIA** — evaluación de impacto para tratamientos de alto riesgo; **SCCs** — cláusulas contractuales tipo para transferencias internacionales.
- Matices controller/processor: una misma empresa puede ser responsable de unos datos y encargado de otros; existen **corresponsables**; desde el GDPR el encargado también tiene obligaciones directas y puede ser multado, pero el responsable sigue siendo el primer obligado.

## Evidence and examples
- **Derechos del titular:** información, acceso, rectificación, **supresión ("derecho al olvido")**, limitación del tratamiento, portabilidad, oposición, y no ser objeto de decisiones puramente automatizadas que afecten significativamente.
- **Tabla "desde tu lado"** (derecho de la persona ↔ obligación de la empresa), preservada íntegra en excerpts. Detalles "que valen oro para la charla": plazo general de respuesta **un mes** (extensible a tres si es complejo); ejercer los derechos es **gratis** (salvo pedidos abusivos o repetitivos).
- **El "clic" para el manager:** todo lo que te gustaría exigir como usuario es exactamente lo que tu empresa le debe a sus clientes. Si un empleado pegó datos de un cliente en un chatbot, **no podés cumplir ninguno de estos pedidos** — el derecho existe; tu capacidad de cumplirlo, no.
- **Obligaciones organizacionales:** DPA con cada encargado; registro de actividades de tratamiento; privacy by design / by default; DPIA para alto riesgo; DPO en ciertos casos; **notificación de brechas en 72 horas**; reglas de transferencia internacional (adecuación o SCCs).
- **Contenido esencial del DPA (Art. 28):** tratar solo según instrucciones documentadas (no para fines propios); confidencialidad del personal; medidas de seguridad (Art. 32); no usar sub-encargados sin autorización; asistir con pedidos de titulares y notificación de brechas; borrar o devolver los datos al terminar; permitir auditorías.
- **Consumo vs. enterprise:** la herramienta de IA de consumo/gratuita normalmente **no ofrece DPA** (y encima puede entrenar con tus datos — justo lo que el DPA prohibiría); el plan empresarial normalmente **sí** (no entrenar, controles de acceso, borrado, a veces elección de región / residencia de datos).
- Diagrama ASCII de la relación responsable→encargado con el DPA (preservado en excerpts).

## Inconsistencies / open questions
- Las cifras de multas acumuladas ("~€5.880 millones en 2023–2024") y el ranking de sancionados provienen de fuentes secundarias (Data Privacy Manager, Forbes); conviene verificar antes de fijarlas en una lámina.
- La multa de Amazon (€746M) se describe como "ratificada en instancias posteriores" sin detalle de la instancia — verificar estado procesal actual.
- El documento simplifica deliberadamente (declarado "para un lector no jurídico"); no cubre excepciones al derecho de supresión ni los matices de interés legítimo.

## Images / diagrams
Sin imágenes. La fuente es Markdown puro (incluye un diagrama ASCII inline, preservado abajo); no hay archivos de imagen asociados. Carpeta companion `gdpr-explicado.md/images/` creada y vacía (válido según esquema).

## Raw / preserved excerpts

> La idea central es un cambio de dueño: **tus datos personales son tuyos, no de la empresa que los recolecta.** La empresa solo los "toma prestados" bajo condiciones estrictas, y vos conservás derechos sobre ellos.

Tabla "desde tu lado" (íntegra):

| Como persona podés pedir… | En la práctica significa… | La empresa está obligada a… |
|---------------------------|---------------------------|-----------------------------|
| **Que me digan qué tienen** (información/acceso) | "¿Qué datos míos guardan y para qué?" | Darte una copia y explicarte los usos |
| **Que lo corrijan** (rectificación) | "Mi dato está mal, corregilo." | Corregirlo sin demora |
| **Que lo borren** (supresión / olvido) | "Eliminá mis datos." | Borrarlos si no hay razón legal para conservarlos |
| **Que frenen el uso** (limitación) | "No los uses hasta que resolvamos esto." | Congelar el tratamiento |
| **Que me los den para llevarlos** (portabilidad) | "Dame mis datos en un formato que pueda mudar a otro proveedor." | Entregarlos en formato reutilizable |
| **Que no los usen para X** (oposición) | "No me mandes marketing." | Dejar de usarlos para ese fin |
| **Que decida un humano** (decisiones automatizadas) | "No quiero que un algoritmo decida esto solo." | Ofrecer intervención humana |

> **El "clic" para el manager:** todo lo que te gustaría poder exigir como usuario es, exactamente, lo que **tu empresa le debe** a sus clientes. Y acá aparece el problema de la IA no gobernada: si un empleado pegó datos de un cliente en un chatbot, **no podés cumplir ninguno de estos pedidos** — no sabés qué se guardó, dónde está, ni podés borrarlo. El derecho existe; tu capacidad de cumplirlo, no.

Diagrama responsable/encargado/DPA (íntegro):

```
RESPONSABLE  ──(datos + instrucciones)──►  ENCARGADO
     │                                          │
     └──────────  DPA (Art. 28)  ───────────────┘
        el contrato obligatorio que regula la relación
```

> **En el caso de la IA:** cuando usás una herramienta de IA con datos personales, **vos (tu empresa) sos el responsable** y **el proveedor de IA es el encargado**. Esa relación *legalmente requiere un DPA*. Si no hay DPA — como pasa con la mayoría de las herramientas de consumo — la relación responsable-encargado existe de hecho pero **sin el marco legal que la vuelve lícita**. Ahí está el incumplimiento.

> Por eso, en la práctica, "¿tiene DPA?" es la línea que separa una herramienta de IA **gobernada** de una **shadow AI**. Es una de las primeras preguntas que un manager debería hacer antes de habilitar cualquier herramienta.

> **En una frase:** *el DPA es el contrato que convierte "confío en que el proveedor se porte bien" en "el proveedor está legalmente obligado a portarse bien — y puedo auditarlo".*

Enforcement (íntegro):

> - **Meta — €1.200 millones (mayo 2023):** la mayor multa individual hasta la fecha, por transferir datos de usuarios europeos a EE. UU. sin garantías adecuadas.
> - **Amazon — €746 millones (2021):** por tratamiento de datos con fines publicitarios sin base válida (ratificada en instancias posteriores).
> - **Meta — €390 millones (enero 2023):** por cambiar la base legal de consentimiento a "ejecución de contrato" sin transparencia suficiente.
> - En conjunto, **2023–2024 acumularon alrededor de €5.880 millones** en multas, con Meta, Amazon, TikTok, LinkedIn y Clearview AI entre los principales sancionados.

Glosario rápido (íntegro):

| Término | Qué significa |
|---------|---------------|
| **GDPR** | Reglamento General de Protección de Datos (UE, 2018) |
| **Dato personal** | Cualquier información sobre una persona identificable |
| **Categoría especial** | Dato sensible (salud, religión, etc.) con protección reforzada |
| **Titular (*data subject*)** | La persona dueña de los datos |
| **Responsable (*controller*)** | Quien decide qué datos se tratan y para qué |
| **Encargado (*processor*)** | Tercero que trata datos en nombre del responsable |
| **DPA** | Contrato entre responsable y encargado |
| **DPO** | Delegado de Protección de Datos |
| **DPIA** | Evaluación de impacto en la protección de datos |
| **SCCs** | Cláusulas contractuales tipo para transferencias internacionales |
| **Base legal** | La razón válida para tratar datos (consentimiento, contrato, etc.) |

Fuentes citadas por el documento original:
- European Commission — Data protection under GDPR: https://commission.europa.eu/law/law-topic/data-protection_en
- Data Privacy Manager — 20 biggest GDPR fines so far: https://dataprivacymanager.net/5-biggest-gdpr-fines-so-far-2020/
- Forbes — Lessons To Take Away From €4.5 Billion In GDPR Fines: https://www.forbes.com/councils/forbestechcouncil/2024/07/02/lessons-to-take-away-from-45-billion-in-gdpr-fines/
- IAPP — Novedades legislativas en Argentina sobre protección de datos personales e IA: https://iapp.org/news/a/novedades-legislativas-en-argentina-sobre-protecci-n-de-datos-personales-e-inteligencia-artificial
