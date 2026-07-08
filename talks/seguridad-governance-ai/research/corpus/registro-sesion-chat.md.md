---
source_file: registro-sesion-chat.md
source_type: chat-export
ingested_at: 2026-07-06
---

# Registro de sesión — Seguridad e IA para Managers

## Provenance
- Original location: llm-chats/registro-sesion-chat.md
- Format: markdown (bitácora de la conversación de trabajo con el LLM: pedidos, decisiones y conceptos clave)
- Author / source (if known): registro de la sesión de trabajo presentador ↔ LLM
- Date of original (if known): 6 de julio de 2026 (declarada en el propio documento)

## Key claims
- **Objetivo del proyecto:** preparar una charla de **2 horas sobre seguridad e IA para managers** que empezaron a usar LLMs (público no técnico). En la sesión se construyó la agenda, se profundizaron conceptos y se generaron documentos de estudio de respaldo.
- Archivos generados en la sesión: `security-ai-managers-agenda.md` (agenda 2 h + imprescindibles + rompemitos + anexos), `gdpr-explicado.md`, `hipaa-explicado.md`, `argentina-datos-explicado.md`, y el propio `registro-sesion-chat.md`.
- **Concepto rector — las dos caras de la seguridad:** la seguridad no es solo impedir que un atacante use tus datos (Cara 1), sino también **cumplir lo que le prometiste a tus clientes** sobre cómo los manejás (Cara 2 — compliance). *"Podés no tener ningún hacker y aun así fallar en seguridad."* La IA golpea sobre todo la Cara 2.
- **El perímetro de seguridad se erosionó en tres etapas:** on-prem (castillo y foso; perímetro físico y de red) → SaaS/nube (perímetro = **contrato + identidad**: DPA, SSO/MFA, logs; control cedido pero *gobernado*) → IA (perímetro corrido hasta **la persona y su criterio**, a menudo *sin gobernanza*). Idea central: el problema de la IA **no es ceder control** (ya se hacía con SaaS) sino hacerlo **sin gobernanza**. **Gobernar la IA = devolverle lo que SaaS ya tenía.**
- **Caso Samsung (2023), "sin exagerar":** tres fugas en menos de 20 días (código fuente ×2 + minuta de reunión), sin hackers. **El impacto real no fue un robo probado, sino la pérdida irreversible de control** sobre IP confidencial (en servidores de un tercero, sin NDA, sin residencia, sin poder borrar), más la respuesta costosa (prohibición + IA interna) y el golpe reputacional. Lección precisa: el daño es *perder el control del dato*, no necesariamente que alguien lo explote.
- **Secuencia pedagógica Samsung ↔ GDPR:** plantar el gancho en el Bloque 4 (intuición: "el dato salió y no vuelve") y hacer el *callback* en GDPR traduciendo cada frase a su artículo: "sin NDA" → DPA (Art. 28); "sin residencia" → transferencia (Arts. 44–49); "sin borrado" → derecho de supresión (Art. 17).
- **PI vs PII:** PII (identifica *directamente*: nombre, DNI, email) es solo un **subconjunto** de los **datos personales** del GDPR (todo lo *vinculable*: IP, ubicación, comportamiento, inferencias). Error típico: *"le saqué el nombre, ya no es dato personal"* → falso si se puede reidentificar. Integrado como mito #4 del rompemitos.
- **Controller vs. processor y el DPA:** responsable decide el *por qué* y el *cómo* (responsabilidad principal); encargado solo trata siguiendo instrucciones. Prueba: ¿quién decide para qué se usan los datos? El DPA (Art. 28) es el contrato obligatorio de la relación. En IA: la empresa es responsable, el proveedor encargado; **sin DPA la relación es ilícita**. *"¿Tiene DPA?"* separa una IA gobernada de una shadow AI.
- **GDPR como data controller — por qué shadow AI rompe el cumplimiento estructuralmente** (no por descuido): sin DPA (Art. 28), sin poder ejecutar la supresión (Art. 17), transferencia ilícita (Arts. 44–49), sin registro (Art. 30), sin poder demostrar accountability (Art. 5). Ejemplo más contundente: *un cliente pide borrar sus datos y no sabés dónde quedaron ni podés borrarlos.*
- **Leyes vs. auditorías:** GDPR y HIPAA son **leyes** que la organización debe cumplir; **SOC 2 es una auditoría** que el proveedor muestra. Frase acuñada: *"GDPR y HIPAA te dicen qué cumplir; SOC 2 es cómo un proveedor te prueba que puede ayudarte a cumplirlo."*
- **BAA (HIPAA) ≈ DPA (GDPR):** contrato obligatorio para que un tercero toque PHI; sin BAA ninguna herramienta puede tocar PHI legalmente; la mayoría de las IA de consumo no firman BAAs.
- **Argentina:** Ley 25.326 (2000), pionera, "país adecuado" para la UE (2003), pero desactualizada; reforma en curso (2025–2026) para alinearla con GDPR (accountability, privacy by design, portabilidad, oposición a decisiones automatizadas). Atajo: *entender GDPR es entender hacia dónde va Argentina.*

## Definitions and terminology
- **Cara 1 / Cara 2 de la seguridad** — protección frente a atacantes vs. cumplimiento de promesas sobre el manejo de datos (compliance).
- **Shadow AI** — uso de herramientas de IA no gobernadas por empleados; rompe el cumplimiento GDPR de manera estructural.
- **PI vs PII** — datos personales (GDPR, todo lo vinculable) vs. subset que identifica directamente.
- **Rompemitos** — dinámica de 5 preguntas verdadero/falso, cada una sembrando un aprendizaje de un bloque posterior.
- Etiquetas de priorización usadas en la agenda: `[IMPRESCINDIBLE]` vs `[SI HAY TIEMPO]`.

## Evidence and examples
- Cronología de decisiones de la sesión (10 pasos): (1) agenda inicial reorganizada desde un esquema de alto nivel del usuario, con arco narrativo conceptos → cómo funciona → riesgos → prácticas → cumplimiento → contexto local → amenazas avanzadas; (2) agregado de temas imprescindibles con eje en **responsabilidades e impacto real de una filtración**; (3) mapa completo de concerns (retención, IP, decisiones automatizadas, gobernanza, logging, secretos en prompts, etc.) etiquetado por prioridad; (4) **se quitó "Incident response"** y se rebalancearon tiempos para sumar 120 min reales; (5) rompemitos de 5 preguntas V/F; **el mito #3 se reemplazó** por uno más complejo ("on-prem/local es siempre más seguro"); (6) traducción a español de todo el material; (7) **EU AI Act** agregado como sección propia del Bloque 8; (8) profundización del eje central: cifras de IBM 2025, caso real Samsung, guion minuto a minuto; (9) anexo IA + GDPR (rol de data controller) y el ejemplo del derecho al olvido imposible de cumplir; (10) documentos de estudio de GDPR, HIPAA y Argentina.
- Ejemplo insignia del incumplimiento estructural: el cliente que ejerce el derecho de supresión y la empresa no puede cumplir porque el dato quedó en un chatbot no gobernado.

## Inconsistencies / open questions
- **Pendientes declarados al cierre de la sesión:** (1) **diapositivas del eje central** (Responsabilidades e impacto de una filtración) — solicitadas, aún no generadas; (2) **SOC 2 como documento de estudio propio** (opcional, en el formato de los otros tres). Ninguno de los dos existe en el corpus.
- **Hilos corregidos / decisiones revertidas durante la sesión:** se eliminó el bloque "Incident response" de la agenda; se reemplazó el mito #3 original por la versión "on-prem/local es siempre más seguro". Las versiones descartadas no se preservaron.
- El registro menciona un storyboard de apertura solo indirectamente: `apertura-samsung-storyboard.md` **no figura** en la tabla de "Archivos generados", lo que sugiere que fue creado en otra sesión o después de escribir este registro.
- Nota operativa: durante la sesión varios conectores (Slack, GitHub, Notion, Gmail, ms365, etc.) aparecieron como pendientes de autorización; no fueron necesarios.

## Images / diagrams
Sin imágenes. La fuente es Markdown puro; no hay archivos de imagen asociados. Carpeta companion `registro-sesion-chat.md/images/` creada y vacía (válido según esquema).

## Raw / preserved excerpts

> ### Qué es "seguridad": las dos caras
> La seguridad no es solo impedir que un atacante use tus datos (**Cara 1**), sino también **cumplir lo que le prometiste a tus clientes** sobre cómo los manejás (**Cara 2 — compliance**). *Podés no tener ningún hacker y aun así fallar en seguridad.* La IA golpea sobre todo la Cara 2.

> Idea central: el problema de la IA **no es ceder control** (eso ya lo hacíamos con SaaS), sino hacerlo **sin gobernanza**. Gobernar la IA = devolverle lo que SaaS ya tenía.

> ### El caso Samsung (2023), sin exagerar
> Tres fugas en menos de 20 días (código fuente x2 + minuta de reunión), sin hackers. **El impacto real no fue un robo probado, sino la pérdida irreversible de control** sobre IP confidencial (en servidores de un tercero, sin NDA, sin residencia, sin poder borrar), más la respuesta costosa (prohibición + IA interna) y el golpe reputacional. La lección precisa: el daño es *perder el control del dato*, no necesariamente que alguien lo explote.

> ### Secuencia pedagógica Samsung ↔ GDPR
> Plantar el gancho en el Bloque 4 (intuición: "el dato salió y no vuelve") y hacer el *callback* en GDPR, traduciendo cada frase a su artículo: "sin NDA" → DPA (Art. 28), "sin residencia" → transferencia (Arts. 44–49), "sin borrado" → derecho de supresión (Art. 17).

> ### GDPR como data controller: por qué shadow AI rompe el cumplimiento
> Como responsable del tratamiento, si un empleado usa una herramienta no gobernada **no podés cumplir** — y no por descuido, sino estructuralmente: sin DPA (Art. 28), sin poder ejecutar el derecho de supresión (Art. 17), transferencia ilícita (Arts. 44–49), sin registro (Art. 30), sin poder demostrar accountability (Art. 5). El ejemplo más contundente: *un cliente pide borrar sus datos y no sabés dónde quedaron ni podés borrarlos.*

> ### Estándares: leyes vs. auditorías
> **GDPR y HIPAA son leyes** que *vos* tenés que cumplir. **SOC 2 es una auditoría** que *el proveedor* te muestra. No mezclarlos es media batalla. Frase: *"GDPR y HIPAA te dicen qué cumplir; SOC 2 es cómo un proveedor te prueba que puede ayudarte a cumplirlo."*

> ## Pendientes
> - **Diapositivas del eje central** (Responsabilidades e impacto de una filtración) — solicitadas, aún no generadas.
> - **SOC 2** como documento de estudio propio (opcional, en el formato de los otros tres).

Tabla de archivos generados (íntegra):

| Archivo | Contenido |
|---------|-----------|
| `security-ai-managers-agenda.md` | Agenda completa de 2 h + temas imprescindibles + rompemitos + anexos |
| `gdpr-explicado.md` | GDPR de cero: historia, conceptos, derechos, DPA, controller/processor |
| `hipaa-explicado.md` | HIPAA de cero: historia, PHI, BAA, sanciones, comparación con GDPR |
| `argentina-datos-explicado.md` | "El GDPR argentino": Ley 25.326 y la reforma en curso |
| `registro-sesion-chat.md` | Este documento |
