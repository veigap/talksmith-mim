# HIPAA explicado — historia, evolución y puntos clave

*Documento de estudio para entender HIPAA desde cero. Pensado para un lector no jurídico. Complementa a [`gdpr-explicado.md`](gdpr-explicado.md).*

---

## En una frase

**HIPAA** (*Health Insurance Portability and Accountability Act*) es la ley federal de **Estados Unidos**, de **1996**, que —entre otras cosas— protege la **información de salud** de las personas: regula quién puede ver, usar y compartir tus datos médicos, y obliga a las organizaciones de salud a mantenerlos privados y seguros.

A diferencia del GDPR (que cubre *todos* los datos personales de *todas* las personas en la UE), HIPAA es **sectorial y nacional**: cubre **solo datos de salud** y **solo en EE. UU.**

---

## Por qué existe

HIPAA nació en 1996 con un objetivo que hoy sorprende: **no** era principalmente una ley de privacidad. Sus dos metas originales fueron:

1. **Portabilidad** (la "P" de *Portability*): que un trabajador **no perdiera su seguro de salud** al cambiar de empleo.
2. **Simplificación administrativa**: estandarizar las transacciones electrónicas del sistema de salud (facturación, reclamos) para reducir el caos de formatos.

El problema: para digitalizar y estandarizar todo ese flujo de información médica hacía falta, sí o sí, **reglas sobre cómo proteger esos datos**. Así, la privacidad y la seguridad de la información de salud —lo que hoy asociamos con HIPAA— surgieron como consecuencia necesaria de esa modernización. Con los años, esa parte se volvió el corazón de la ley.

---

## Historia y evolución

HIPAA no fue un evento único: se construyó por capas a lo largo de casi 20 años.

**1996 — se promulga HIPAA.** Firmada por Bill Clinton. Establece la portabilidad del seguro y la simplificación administrativa, y ordena crear reglas de privacidad y seguridad.

**2003 — entra en vigor la Privacy Rule (Regla de Privacidad).** Define qué es la información de salud protegida (**PHI**) y establece quién puede usarla o divulgarla, además de los derechos de los pacientes sobre sus datos.

**2005 — entra en vigor la Security Rule (Regla de Seguridad).** Se enfoca en la PHI en formato **electrónico** (ePHI) y exige salvaguardas administrativas, físicas y técnicas (control de acceso, cifrado, auditoría).

**2009 — HITECH Act.** Una reforma clave, impulsada por la digitalización de las historias clínicas. Endureció el *enforcement*, subió las multas, creó la **obligación de notificar brechas** y —muy importante— extendió las obligaciones a los **business associates** (los proveedores externos que manejan PHI).

**2013 — Omnibus Rule.** Terminó de implementar HITECH: hizo a los business associates **directamente responsables** ante la ley y reforzó los derechos de los pacientes. Es, más o menos, la forma en que conocemos HIPAA hoy.

---

## Conceptos clave (el vocabulario)

**PHI — Protected Health Information (Información de Salud Protegida).** Cualquier información sobre la salud de una persona que pueda identificarla, cuando la maneja una entidad cubierta. Incluye diagnósticos, tratamientos, resultados de laboratorio, datos de facturación médica, y también identificadores como nombre, fecha de nacimiento o número de historia clínica cuando van asociados a lo anterior. En formato electrónico se la llama **ePHI**.

**Entidades cubiertas (*covered entities*).** Las organizaciones a las que HIPAA aplica **directamente**:
- **Prestadores de salud** (médicos, hospitales, clínicas, farmacias) que transmiten datos de salud electrónicamente.
- **Planes de salud** (aseguradoras, obras sociales).
- **Cámaras de compensación** de salud (*healthcare clearinghouses*).

**Business associates (asociados de negocio).** Terceros que **manejan PHI en nombre** de una entidad cubierta: proveedores de nube, empresas de facturación, IT, servicios de transcripción… **y herramientas de IA**. Desde HITECH/Omnibus, son directamente responsables y **deben firmar un BAA** (ver abajo).

**La "regla de oro" — *minimum necessary*.** Solo se debe acceder, usar o compartir el **mínimo** de PHI necesario para la tarea. (El eco del principio de minimización del GDPR.)

---

## Las reglas de HIPAA

HIPAA no es un texto único, sino un conjunto de reglas:

- **Privacy Rule (Privacidad):** quién puede usar o divulgar PHI, con qué límites, y qué derechos tiene el paciente.
- **Security Rule (Seguridad):** cómo proteger la ePHI, con tres tipos de salvaguardas: **administrativas** (políticas, capacitación), **físicas** (acceso a instalaciones y dispositivos) y **técnicas** (control de acceso, cifrado, registros de auditoría).
- **Breach Notification Rule (Notificación de brechas):** obliga a avisar de una filtración de PHI —a los afectados, al gobierno (OCR) y, en casos grandes, a la prensa— **dentro de los 60 días**.
- **Enforcement Rule (Cumplimiento):** define cómo se investigan las violaciones y cómo se calculan las multas.

---

## Derechos del paciente

Como persona, HIPAA te da derechos sobre tu información de salud:

- **Acceso** — pedir y obtener una copia de tu historia clínica.
- **Rectificación** — solicitar que corrijan datos erróneos.
- **Registro de divulgaciones** — saber a quién se le compartió tu PHI.
- **Solicitar restricciones** — pedir límites sobre cómo se usa o comparte tu información.
- **Notificación** — que te avisen si tus datos sufrieron una brecha.

---

## El BAA (Business Associate Agreement) — el "primo" del DPA

El **BAA — *Business Associate Agreement*** es el **contrato obligatorio** que una entidad cubierta debe firmar con cualquier business associate que vaya a tocar PHI. Es el equivalente en HIPAA del **DPA** del GDPR.

**Qué garantiza el BAA:**
- El business associate solo usa la PHI para los fines permitidos.
- Aplica las salvaguardas de la Security Rule (seguridad, cifrado, control de acceso).
- Reporta cualquier brecha a la entidad cubierta.
- Controla a sus propios subcontratistas.
- Devuelve o destruye la PHI al terminar el servicio.

**Por qué importa para la IA (el punto central):** si un empleado de una organización de salud pega PHI en una herramienta de IA que **no firmó un BAA**, la organización ya está en incumplimiento — aunque nada se filtre. Y la mayoría de las herramientas de IA **de consumo no firman BAAs**. Solo los planes específicos para salud o ciertos enterprise lo hacen (por ejemplo, ofertas "HIPAA-eligible" de algunos proveedores de nube/IA).

> **En una frase:** *sin BAA firmado, ninguna herramienta —por buena que sea— puede tocar PHI legalmente. "¿Firmás un BAA?" es la pregunta que separa una herramienta usable en salud de una que no lo es.*

---

## Sanciones: cuatro niveles

Las multas de HIPAA se calculan **por violación** y dependen del grado de culpa. Se ajustan por inflación cada año; para 2025–2026 el rango va desde **US$ 145 hasta US$ 2.190.294 por violación**, con topes anuales. Los cuatro niveles (*tiers*):

1. **Sin conocimiento** — la entidad no sabía ni podía saber razonablemente.
2. **Causa razonable** — hubo motivo, pero no negligencia deliberada.
3. **Negligencia deliberada, corregida** dentro de los 30 días.
4. **Negligencia deliberada, no corregida** — el nivel más caro.

A diferencia del GDPR (que calcula sobre la facturación global), HIPAA multa por violación — pero como una brecha puede implicar miles de registros, los montos escalan rápido.

---

## El enforcement en la práctica

Quien aplica HIPAA es la **OCR** (*Office for Civil Rights*), dentro del Departamento de Salud (HHS). No es letra muerta:

- **Solara Medical Supplies — US$ 3.000.000 (enero 2025).**
- **Warby Parker — US$ 1.500.000 (febrero 2025).**
- La OCR cerró **21 acuerdos y sanciones en 2025** y 22 en 2024 — de los totales anuales más altos de su historia.

---

## HIPAA vs. GDPR — la comparación rápida

| | **HIPAA** | **GDPR** |
|---|---|---|
| **Origen** | EE. UU., 1996 | UE, 2018 |
| **Alcance** | Sectorial: solo **datos de salud** | Amplio: **todos** los datos personales |
| **A quién aplica** | Entidades de salud + sus business associates | Cualquiera que trate datos de personas en la UE (extraterritorial) |
| **El contrato con terceros** | **BAA** | **DPA** |
| **Multas** | Por violación (US$ 145 – 2,19M) | Hasta €20M o 4% de facturación global |
| **Autoridad** | OCR / HHS | Autoridades de datos de cada país |

La idea para recordar: **son primos con la misma lógica** (rendición de cuentas, contratos con proveedores, derechos de las personas, notificación de brechas), pero HIPAA es angosto y estadounidense, y GDPR es amplio y global.

---

## HIPAA y la IA (por qué importa hoy)

Si tu organización toca datos de salud, el riesgo es directo:

- Pegar PHI en un chatbot **sin BAA** = incumplimiento inmediato, aunque nada se filtre.
- La IA de consumo suele **retener** lo que ingresás y usarlo para entrenar → pérdida de control sobre PHI, imposible de recuperar.
- Sin logs ni control de acceso, tampoco podés cumplir la Security Rule ni responder a una auditoría de la OCR.

La conclusión es la misma que con GDPR: el cumplimiento no depende de "tener cuidado", sino de **usar solo herramientas gobernadas** — en el caso de salud, herramientas que **firmen un BAA** y ofrezcan las salvaguardas de la Security Rule.

---

## Glosario rápido

| Término | Qué significa |
|---------|---------------|
| **HIPAA** | Ley de salud de EE. UU. (1996) que protege la información médica |
| **PHI** | Información de salud protegida (identificable) |
| **ePHI** | PHI en formato electrónico |
| **Entidad cubierta** | Prestador, plan de salud o cámara de compensación |
| **Business associate** | Tercero que maneja PHI en nombre de una entidad cubierta |
| **BAA** | Contrato obligatorio con un business associate (equivale al DPA de GDPR) |
| **Minimum necessary** | Usar solo el mínimo de PHI necesario |
| **OCR** | La oficina (HHS) que hace cumplir HIPAA |
| **HITECH (2009)** | Reforma que endureció HIPAA y extendió las reglas a los business associates |

---

## Fuentes

- [HHS.gov — HIPAA for Professionals](https://www.hhs.gov/hipaa/for-professionals/index.html)
- [HIPAA Journal — What are the Penalties for HIPAA Violations?](https://www.hipaajournal.com/what-are-the-penalties-for-hipaa-violations-7096/)
- [The HIPAA Guide — HHS Increases Civil Monetary Penalty Amounts for 2025](https://www.hipaaguide.net/hhs-increased-civil-monetary-penalty-hipaa-violations/)
- [Secureframe — HIPAA Violation Examples 2025](https://secureframe.com/hub/hipaa/violations)
