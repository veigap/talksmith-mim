---
source_type: presenter-outline
captured_at: 2026-07-06
topic: Esquema de slides — Seguridad e IA para Managers (brain-dump Modo C, Step 4)
author: Paulo Veiga (presenter)
---

# Esquema de slides — Seguridad e IA para Managers

> Outline verbatim entregado por el presenter en el chat como brain-dump del Modo C (Presenter Outline), Step 4. Incluye al final sus directivas de mejora.

Storyboard slide por slide para la charla de 2 h. Cada entrada indica el título del slide y qué cubrir. Basado en security-ai-managers-agenda.md y los documentos de estudio (GDPR, HIPAA, Argentina).

Total estimado: ~49 slides para 110 min de contenido + 10 de pausa. Los slides marcados 〔divisor〕 son separadores de sección (sin contenido denso). Al final hay slides de respaldo (backup) para preguntas.

---

## Apertura — Bloque 0 (7 min)

**S1 — Portada**
Título de la charla, tu nombre, fecha. Una imagen sobria. Subtítulo que fije el tono: "Criterio práctico para quienes ya usan IA en el trabajo."

**S2 — Qué es "seguridad": las dos caras**
Cara 1: protección frente a atacantes (hackers, malware). Cara 2: cumplir lo que le prometiste a tus clientes sobre cómo manejás sus datos (compliance). Mensaje: podés no tener ningún hacker y aun así fallar en seguridad. La IA golpea sobre todo la Cara 2. Frase de lámina: "Una falla de seguridad no siempre tiene un atacante. A veces sos vos incumpliendo lo que prometiste."

**S3 — Por qué esto importa ahora**
Gancho: "ya estás pegando datos de la empresa en estas herramientas". 1–2 titulares reales de fugas. Qué se va a llevar la audiencia al final. Pregunta a la sala para levantar la mano: "¿quién usó una IA para algo del trabajo esta semana?"

---

## Fundamentos — Bloque 1 (13 min)

**S4 — 〔divisor〕 Fundamentos: el vocabulario mínimo**

**S5 — PII vs. datos personales**
PII = identifica directamente (nombre, DNI, email). Datos personales (GDPR) = todo lo vinculable (IP, ubicación, comportamiento, inferencias). PII es un subconjunto. Error típico: "le saqué el nombre, ya no es personal" → falso si se puede reidentificar.

**S6 — Residencia de datos**
Dónde viven físicamente los datos y por qué importa la jurisdicción. Ejemplo simple: un dato en servidores de EE. UU. está bajo leyes de EE. UU.

**S7 — Cifrado**
En tránsito vs. en reposo, explicado sin matemática. La idea: el cifrado protege el dato aunque alguien lo intercepte o robe el disco.

**S8 — Clasificación de datos (3 niveles)**
Público / Interno / Confidencial-Regulado. Aclarar que es una convención (respaldo en ISO 27001 / NIST), no un estándar único. Regla para llevar: "Antes de pegar, preguntá de qué nivel es este dato."

**S9 — El perímetro: de on-prem a SaaS a IA**
La tabla de tres etapas (dónde viven los datos / qué era el perímetro / ¿gobernado?). Idea central: el problema de la IA no es ceder control, es hacerlo sin gobernanza. Frase: "El firewall no te protege de un dato que sale voluntariamente por la puerta de adelante."

---

## Detrás de escena — Bloque 2 (14 min)

**S10 — 〔divisor〕 ¿Qué pasa realmente cuando uso una IA?**

**S11 — Qué es una API**
Analogía del mesero/restaurante: pedís algo por un canal estándar y te traen la respuesta. Es cómo dos sistemas se hablan.

**S12 — El camino del dato: de tu teclado al modelo**
Diagrama: tu máquina/navegador → proveedor → modelo → respuesta. Marcar en qué puntos el dato queda expuesto o se guarda.

**S13 — LLM como servicio**
El modelo no corre en tu compu: es un servicio de un tercero al que le mandás tu texto. Implicancia: lo que pegás viaja y puede quedar. Conecta con residencia y retención.

---

## MCP — Bloque 3 (7 min)

**S14 — MCP: una API que actúa**
No solo responde: conecta la IA con tus archivos, mail, calendario. La IA pasa de "contestar" a "hacer".

**S15 — Por qué eleva el riesgo**
Un chatbot que responde es bajo riesgo; un agente que puede leer tu disco y enviar mails es otra clase de riesgo. Introduce mínimo privilegio (se paga en el Bloque 6).

---

## Eje central: responsabilidades e impacto — Bloque 4 (14 min)

**S16 — 〔divisor〕 Qué pasa cuando algo sale mal**

**S17 — Caso real: Samsung (2023)**
Tres fugas en <20 días (código fuente x2 + minuta), sin hackers. El dato quedó en servidores de un tercero sin NDA, sin residencia, sin poder borrarlo. Contar la historia antes de los números. Aclarar el matiz: el daño no fue un robo probado, sino la pérdida irreversible de control.

**S18 — Los 4 tipos de daño**
Financiero / legal-regulatorio / reputacional / operativo. Mensaje: no es un problema de IT, es de negocio.

**S19 — El costo, en números**
USD 4,44 M promedio global; USD 10,22 M en EE. UU. (IBM 2025). Anclar la magnitud.

**S20 — Por qué la IA cambia la exposición**
2–3 stats de shadow AI: +USD 670.000 por brecha, 97% sin controles de acceso, 83% sin controles básicos. Idea: la mayoría de las organizaciones ya está expuesta.

**S21 — Modos de falla concretos**
Datos pegados en herramienta de consumo; fuga cruzada entre clientes; agente con permisos amplios; credenciales en el prompt. Elegir 1–2 según la sala.

**S22 — La pregunta incómoda: ¿quién es responsable?**
Dejar el silencio. Respuesta: la organización y el manager, no el proveedor. "La IA lo hizo" no es defensa. Puente hacia las buenas prácticas: "la buena noticia: casi todo esto se previene."

---

## ☕ Pausa (10 min) — S23 slide de pausa con la hora de regreso

---

## Shadow AI — Bloque 5 (9 min)

**S24 — 〔divisor〕 Shadow AI: el riesgo invisible**
Qué es: empleados usando herramientas no autorizadas con datos de la empresa. Está pasando ahora, esté o no autorizado.

**S25 — Consumo vs. enterprise**
La diferencia que más importa: ¿entrenan con tus datos? ¿cuánto los retienen? ¿hay contrato (DPA)? Gratis/personal: normalmente no. Business/enterprise: normalmente sí.

**S26 — La jugada del manager**
No prohibir (la gente esquiva las prohibiciones): proveer una herramienta autorizada y hacer que el camino seguro sea el fácil.

---

## Buenas prácticas — Bloque 6 (12 min)

**S27 — 〔divisor〕 Qué hacer el lunes a la mañana**

**S28 — Clasificá antes de pegar**
Aplicar los 3 niveles del S8. Qué nunca va a una herramienta de consumo.

**S29 — Mínimo privilegio**
Cada conector/agente con el acceso mínimo necesario. Revisar qué pueden ver los conectores.

**S30 — Higiene de cuenta y secretos**
MFA/SSO, no compartir cuentas. Nunca pegar contraseñas, claves ni tokens (quedan en el historial).

**S31 — Verificá la salida**
La IA redacta, los humanos deciden. Verificar todo lo que tenga consecuencias (la alucinación como riesgo de decisión).

---

## Rompemitos — Bloque 7 (7 min)

**S32 — 〔divisor〕 Rompemitos: ¿verdadero o falso?**
Explicar la dinámica: votan primero, revelo después.

**S33 — Mito 1: "Todo lo que escribo entrena la IA y puede reaparecer"**
Realidad: depende del plan; consumo suele entrenar, enterprise no. Siembra el tema de tiers.

**S34 — Mito 2: "Proveedor grande = automáticamente seguro y compliant"**
Realidad: falso; su seguridad no es tu cumplimiento; vos seguís siendo responsable.

**S35 — Mito 3: "On-prem/local es siempre más seguro"**
Realidad: reduce un riesgo pero te pasa toda la carga (parches, accesos, procedencia del modelo). "Seguro" es propiedad de la gobernanza, no del lugar. Callback al S9.

**S36 — Mito 4: "Borrar los nombres alcanza"**
Realidad: confunde PII con datos personales; si se puede reidentificar, sigue protegido. Callback al S5.

**S37 — Mito 5: "Si responde con seguridad y cita fuentes, es correcto"**
Realidad: alucina y fabrica citas; verificar lo consecuente.

---

## Estándares y cumplimiento — Bloque 8 (8 min)

**S38 — 〔divisor〕 El mapa de estándares**
El marco que evita la confusión: GDPR y HIPAA son leyes (vos cumplís); SOC 2 es una auditoría (el proveedor te la muestra).

**S39 — GDPR**
Ley UE, extraterritorial (te alcanza en Argentina). Derechos del titular, brechas 72 h, multas hasta €20M / 4%. El DPA como contrato con el proveedor.

**S40 — HIPAA**
Ley sectorial de salud (EE. UU.). PHI y el BAA (primo del DPA). Relevante solo si tocás datos de salud.

**S41 — SOC 2**
No es ley: auditoría del proveedor (5 criterios; Type I vs II). La pregunta de compra: "¿tenés SOC 2 Type II?"

**S42 — EU AI Act**
La primera ley amplia de IA. Niveles de riesgo (prohibido/alto/limitado/mínimo). Fechas: GPAI desde ago-2025, grueso ago-2026, alto riesgo 2027–2028. Alcanza a quien sirva a usuarios de la UE.

---

## Argentina — Bloque 9 (6 min)

**S43 — El "GDPR argentino"**
Ley 25.326 (2000), pionera y "país adecuado" para la UE (2003), pero desactualizada. Reforma en curso (2025–2026) para alinearla con GDPR: accountability, privacy by design, portabilidad, oposición a decisiones automatizadas. Atajo: entender GDPR es entender hacia dónde va Argentina.

---

## Inyección de prompts y agentes — Bloque 10 (9 min)

**S44 — 〔divisor〕 La amenaza de la era de los agentes**

**S45 — Qué es la inyección de prompts**
Directa (el usuario empuja al modelo) vs. indirecta (instrucciones ocultas en un documento o web que la IA lee y obedece). El riesgo no es solo lo que le das, sino lo que consume.

**S46 — Por qué los agentes amplifican el riesgo**
Si un agente con permisos lee contenido malicioso, puede ejecutar acciones (enviar, borrar, exponer). Conecta con mínimo privilegio.

**S47 — Guardrails concretos**
Permisos mínimos, revisar qué consume el agente, confirmación humana para acciones sensibles (dinero/datos), desconfiar de contenido externo.

---

## Cierre — Bloque 11 (4 min)

**S48 — Hoja de una página (los 6 para llevar)**
1. Clasificá antes de pegar. 2) Usá herramientas autorizadas y con contrato. 3) Mínimo privilegio. 4) Vos sos responsable, no el proveedor. 5) Verificá la salida. 6) Reportá incidentes rápido.

**S49 — Cierre + preguntas**
Tres takeaways en una línea. Ofrecer la hoja de una página impresa. Datos de contacto / Q&A.

---

## Slides de respaldo (backup, para preguntas)

* B1 — Samsung ↔ GDPR: traducción de "sin NDA / sin residencia / sin borrado" a los Arts. 28 / 44–49 / 17.
* B2 — Controller vs. processor + DPA: el diagrama y quién es responsable.
* B3 — Derechos del titular (GDPR): la tabla "qué podés pedir / qué te deben" + plazo de 1 mes, gratis.
* B4 — Comparación GDPR vs. HIPAA: la tabla de primos (BAA↔DPA).
* B5 — Mapa completo de concerns: retención, IP, decisiones automatizadas, logging, continuidad (de la Parte 3).

---

## Notas de diseño

* Un concepto por slide. Los managers recuerdan historias y frases, no bullets densos.
* Reservá las "frases para la lámina" ya escritas en la agenda como cierre visual de cada bloque clave.
* Los divisores dan respiro y ordenan el arco: Fundamentos → Cómo funciona → Impacto → Prácticas → Cumplimiento → Local → Amenazas → Cierre.
* Ritmo: ~2–2,5 min por slide de contenido; los divisores y la portada, segundos.

---

## Directivas del presenter (verbatim, al entregar el outline)

"No estoy buscando que mantengas estos slides o agenda. Dado que estoy usando el mejor modelo, me imagino que vas a poder hacer mejor trabajo. Creo que la historia de empezar son Samsung y llevar la charlar en temas core es importante. Tomate tu tiempo en crear un buen layout y si ves temas que parece que no estan siendo cubiertos, genera un reporte sobre esto. Busca en internet sobre programas similares si hay algo que podemos incluir."

Interpretación operativa:
1. El outline es punto de partida, no contrato — el Editor tiene libertad de reestructurar y mejorar.
2. **Samsung abre la charla** y el arco se construye desde esa historia hacia los temas core (esto resuelve la tensión storyboard-vs-agenda a favor del storyboard).
3. Invertir en un buen layout/arco narrativo.
4. Generar un reporte de gaps (temas no cubiertos).
5. Benchmark contra programas similares encontrados en internet e incorporar lo que valga la pena.
