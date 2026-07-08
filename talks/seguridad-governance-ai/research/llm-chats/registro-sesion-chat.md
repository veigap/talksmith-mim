# Registro de sesión — Seguridad e IA para Managers

*Bitácora de la conversación de trabajo: pedidos, decisiones y conceptos clave desarrollados. Fecha: 6 de julio de 2026.*

---

## Objetivo del proyecto

Preparar una charla de **2 horas sobre seguridad e IA para managers** que empezaron a usar LLMs (público no técnico). A lo largo de la sesión se construyó la agenda, se profundizaron conceptos y se generaron documentos de estudio de respaldo.

---

## Archivos generados

| Archivo | Contenido |
|---------|-----------|
| `security-ai-managers-agenda.md` | Agenda completa de 2 h + temas imprescindibles + rompemitos + anexos |
| `gdpr-explicado.md` | GDPR de cero: historia, conceptos, derechos, DPA, controller/processor |
| `hipaa-explicado.md` | HIPAA de cero: historia, PHI, BAA, sanciones, comparación con GDPR |
| `argentina-datos-explicado.md` | "El GDPR argentino": Ley 25.326 y la reforma en curso |
| `registro-sesion-chat.md` | Este documento |

---

## Cronología de decisiones

**1. Agenda inicial.** Se partió de un esquema de alto nivel del usuario y se lo reorganizó en una agenda de 2 h con tiempos, siguiendo un arco narrativo: conceptos → cómo funciona → riesgos → prácticas → cumplimiento → contexto local → amenazas avanzadas.

**2. Temas imprescindibles faltantes.** Se agregaron los bloques que una charla de seguridad para managers no puede omitir, con eje en **responsabilidades e impacto real de una filtración de datos**.

**3. Ampliación total de concerns.** Se sumó un mapa completo de preocupaciones (retención, IP, decisiones automatizadas, gobernanza, logging, secretos en prompts, etc.), etiquetadas `[IMPRESCINDIBLE]` vs `[SI HAY TIEMPO]`.

**4. Se quitó "Incident response".** Y se rebalancearon los tiempos para sumar 120 min reales.

**5. Rompemitos.** Se escribieron 5 preguntas tipo verdadero/falso, cada una sembrando un aprendizaje de un bloque posterior. Luego el mito #3 se reemplazó por uno más complejo ("on-prem/local es siempre más seguro").

**6. Traducción a español** de todo el material.

**7. EU AI Act** agregado como sección propia del Bloque 8.

**8. Profundización del eje central:** cifras de IBM 2025, caso real Samsung, y guion minuto a minuto.

**9. Anexo IA + GDPR** (rol de data controller) y el ejemplo del derecho al olvido imposible de cumplir.

**10. Documentos de estudio** de GDPR, HIPAA y Argentina.

---

## Conceptos clave desarrollados (lo más valioso de la sesión)

### Qué es "seguridad": las dos caras
La seguridad no es solo impedir que un atacante use tus datos (**Cara 1**), sino también **cumplir lo que le prometiste a tus clientes** sobre cómo los manejás (**Cara 2 — compliance**). *Podés no tener ningún hacker y aun así fallar en seguridad.* La IA golpea sobre todo la Cara 2.

### El perímetro de seguridad: de on-prem a SaaS a IA
El perímetro no desapareció de golpe, se erosionó en tres etapas:
- **On-prem** — castillo y foso; perímetro físico y de red.
- **SaaS/nube** — el perímetro se transforma en **contrato + identidad** (DPA, SSO/MFA, logs); cediste control pero *gobernado*.
- **IA** — el perímetro se corre hasta **la persona y su criterio**; a menudo *sin gobernanza*.

Idea central: el problema de la IA **no es ceder control** (eso ya lo hacíamos con SaaS), sino hacerlo **sin gobernanza**. Gobernar la IA = devolverle lo que SaaS ya tenía.

### El caso Samsung (2023), sin exagerar
Tres fugas en menos de 20 días (código fuente x2 + minuta de reunión), sin hackers. **El impacto real no fue un robo probado, sino la pérdida irreversible de control** sobre IP confidencial (en servidores de un tercero, sin NDA, sin residencia, sin poder borrar), más la respuesta costosa (prohibición + IA interna) y el golpe reputacional. La lección precisa: el daño es *perder el control del dato*, no necesariamente que alguien lo explote.

### Secuencia pedagógica Samsung ↔ GDPR
Plantar el gancho en el Bloque 4 (intuición: "el dato salió y no vuelve") y hacer el *callback* en GDPR, traduciendo cada frase a su artículo: "sin NDA" → DPA (Art. 28), "sin residencia" → transferencia (Arts. 44–49), "sin borrado" → derecho de supresión (Art. 17).

### PI vs PII
**PII** (identifica *directamente*: nombre, DNI, email) es solo un **subconjunto** de los **datos personales** del GDPR (todo lo *vinculable*: IP, ubicación, comportamiento, inferencias). Error típico: *"le saqué el nombre, ya no es dato personal"* → falso si se puede reidentificar. (Quedó integrado como el mito #4.)

### Controller vs. processor y su conexión con el DPA
- **Responsable (controller):** decide el *por qué* y el *cómo*; carga con la responsabilidad principal.
- **Encargado (processor):** solo trata datos siguiendo instrucciones.
- **Prueba:** ¿quién decide para qué se usan los datos? Ese es el responsable.
- **DPA (Art. 28):** el contrato obligatorio que regula la relación responsable→encargado. En IA: vos sos el responsable, el proveedor es el encargado; sin DPA la relación es ilícita. *"¿Tiene DPA?"* separa una IA gobernada de una shadow AI.

### GDPR como data controller: por qué shadow AI rompe el cumplimiento
Como responsable del tratamiento, si un empleado usa una herramienta no gobernada **no podés cumplir** — y no por descuido, sino estructuralmente: sin DPA (Art. 28), sin poder ejecutar el derecho de supresión (Art. 17), transferencia ilícita (Arts. 44–49), sin registro (Art. 30), sin poder demostrar accountability (Art. 5). El ejemplo más contundente: *un cliente pide borrar sus datos y no sabés dónde quedaron ni podés borrarlos.*

### Estándares: leyes vs. auditorías
**GDPR y HIPAA son leyes** que *vos* tenés que cumplir. **SOC 2 es una auditoría** que *el proveedor* te muestra. No mezclarlos es media batalla. Frase: *"GDPR y HIPAA te dicen qué cumplir; SOC 2 es cómo un proveedor te prueba que puede ayudarte a cumplirlo."*

### BAA (HIPAA) ≈ DPA (GDPR)
El BAA es el contrato obligatorio para que un tercero toque PHI (datos de salud). Sin BAA firmado, ninguna herramienta puede tocar PHI legalmente. La mayoría de las IA de consumo no firman BAAs.

### Argentina: "el GDPR argentino"
Ley 25.326 (2000), pionera y reconocida como "país adecuado" por la UE (2003), pero desactualizada. Reforma en curso (2025–2026) para alinearla con GDPR: accountability, privacy by design, portabilidad, oposición a decisiones automatizadas. Atajo: *entender GDPR es entender hacia dónde va Argentina.*

---

## Pendientes

- **Diapositivas del eje central** (Responsabilidades e impacto de una filtración) — solicitadas, aún no generadas.
- **SOC 2** como documento de estudio propio (opcional, en el formato de los otros tres).

---

## Nota operativa

Durante la sesión, varios conectores (Slack, GitHub, Notion, Gmail, ms365, etc.) aparecieron como pendientes de autorización. No fueron necesarios para este trabajo; si en el futuro se quieren usar, hay que autorizarlos desde la configuración de conectores.
