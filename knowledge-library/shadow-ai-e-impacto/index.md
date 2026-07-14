---
topic: Shadow AI e impacto de filtraciones — estadísticas verificadas, tipos de daño y responsabilidad
language: Español
sources:
  - talk: seguridad-governance-ai
    date: 2026-07-06
    contributed: Cifras IBM 2025 y LayerX verificadas contra fuentes primarias (con la corrección del 83%→63%), tipología de daños, modos de falla, la respuesta gerencial al shadow AI y respuesta a incidentes.
last_updated: 2026-07-06
---

# Shadow AI e impacto de filtraciones

## Qué es el shadow AI

**Shadow AI**: empleados usando herramientas de IA **no autorizadas** con datos de la empresa. Es invisible — nadie lo reporta, no deja registro donde vos mirás. El nombre "shadow" no es por malicia: es porque no se ve. Está pasando en cualquier organización ahora mismo, esté o no autorizado el uso de IA.

## Estadísticas verificadas (estado a julio 2026)

Verificadas contra fuentes primarias en el benchmark del Talk de origen — reutilizables con confianza:

- ✅ Costo promedio global de una filtración de datos: **USD 4,44 millones** (bajó 9% desde 4,88M en 2024) — *IBM Cost of a Data Breach 2025*.
- ✅ En EE. UU.: **USD 10,22 millones** — récord histórico (IBM 2025).
- ✅ Una brecha con **shadow AI** cuesta **+USD 670.000** extra en promedio (promedio USD 4,63M) — IBM 2025.
- ✅ **97%** de las brechas relacionadas con IA ocurrieron en organizaciones **sin controles de acceso de IA adecuados** (IBM 2025).
- ✅ **63%** de las organizaciones estudiadas **sin política de gobernanza de IA** (o aún en desarrollo) — IBM/Ponemon 2025, n=600.
- ✅ ~**18%** de los empleados enterprise pega datos en herramientas GenAI; **más de la mitad** de esos pegados incluye información corporativa — LayerX (vía eSecurityPlanet).

⚠️ **Cifra corregida — no reutilizar**: "83% sin controles básicos" (síntesis de Kiteworks) **no pudo verificarse** contra el informe primario de IBM 2025; se reemplazó por el 63% verificado. Otras cifras de la agenda original sin verificación primaria: "20% de organizaciones con filtración vinculada a shadow AI", "65% más PII / 40% más IP comprometida" — verificar antes de fijar en lámina.

Regla editorial que dejó el Talk: **cada estadística en lámina lleva su fuente visible en forma corta.**

## Los 4 tipos de daño de una filtración

| Daño | Ejemplo |
|---|---|
| 💰 **Financiero** | Costo directo del incidente, multas |
| ⚖️ **Legal / regulatorio** | Incumplimiento GDPR/HIPAA, demandas |
| 📉 **Reputacional** | El más duradero: confianza de clientes |
| ⚙️ **Operativo** | Frenar herramientas, rehacer procesos |

**No es un problema de IT — es un problema de negocio.** El caso Samsung materializó el operativo y el reputacional sin multa ni robo probado: no hace falta que el daño financiero se materialice para que sea caro.

## Modos de falla concretos

1. Datos sensibles pegados en una **herramienta de consumo** que entrena con lo ingresado.
2. Un documento generado que **filtra datos de otro cliente** (que el modelo vio antes, o pegados antes en una cuenta compartida).
3. Un **agente con permisos amplios** ejecutando una acción no deseada (mail, borrado, carpeta expuesta).
4. **Credenciales o claves de API** pegadas en un prompt — quedan en el historial.

Escenario de facilitación (2 min): *"un miembro de tu equipo pega la lista completa de clientes en un chatbot gratuito para 'ordenarla'. Contame qué acaba de pasar — legal, financiera y reputacionalmente."*

## ¿Quién es responsable?

**La organización — y muchas veces el manager que autorizó o toleró el uso. No el proveedor.** Los términos del proveedor casi siempre se desligan de responsabilidad por lo que ingresás. ***"La IA lo hizo" no es una defensa legal ni profesional.*** Este único punto reencuadra cualquier charla sobre el tema: de curiosidad a responsabilidad.

## Consumo vs. enterprise — "la diferencia que más importa"

| Pregunta | Gratis / personal | Business / enterprise |
|---|---|---|
| ¿Entrenan con tus datos? | Normalmente **sí** | Normalmente **no** |
| ¿Cuánto retienen? | Indefinido / poco claro | Definido por contrato |
| ¿Hay contrato (DPA)? | **No** | **Sí** |

La misma marca puede ser gobernable o no según el plan — la pregunta no es "¿qué herramienta?" sino "¿qué plan y con qué contrato?". Confirmado como "la diferencia que más importa" también en fuentes 2026. Matiz importante (mito frecuente): el tier enterprise resuelve retención y entrenamiento, **no la gobernanza** — ni el shadow AI en cuentas personales, ni los conectores mal permisionados, ni la verificación de salidas. **La herramienta no reemplaza la gobernanza.**

## La jugada del manager

- ❌ **Prohibir no funciona**: la gente esquiva las prohibiciones y el uso se vuelve más invisible (Samsung prohibió — y tuvo que construir una IA interna).
- ✅ **Proveer una herramienta autorizada** — con contrato, con controles.
- 🎯 **Hacer que el camino seguro sea el fácil.** Es diseño de incentivos, no policía.

Paso siguiente natural: una **Política de Uso Aceptable de IA (AUP)** de una página — qué está permitido, con qué datos, qué requiere revisión humana. "El artefacto más útil que un manager puede impulsar."

## Cuando algo sale mal: respuesta a incidentes (versión mínima para managers)

- Pegaste lo que no debías / un agente hizo lo que no debía → **avisá ya** (manager / seguridad / IT).
- **La velocidad es el control más barato**: da opciones (cortar acceso, pedir borrado, notificar a tiempo). El plazo existe: GDPR exige notificar brechas en **72 horas** — no podés notificar lo que nadie reportó.
- El manager marca el tono: **quien reporta un error propio no se castiga.** Si reportar da miedo, los incidentes se entierran y se descubren tarde y mal.

## References

- [`../../talks/seguridad-governance-ai/research/corpus/benchmark-programas-similares-2026-07-06.md.md`](../../talks/seguridad-governance-ai/research/corpus/benchmark-programas-similares-2026-07-06.md.md) — verificación de cifras contra fuentes primarias (incl. corrección 83%→63%).
- [`../../talks/seguridad-governance-ai/research/corpus/security-ai-managers-agenda.md.md`](../../talks/seguridad-governance-ai/research/corpus/security-ai-managers-agenda.md.md) — tipología de daños, modos de falla, rendición de cuentas, jugada del manager, guion del bloque de impacto.
- IBM — Cost of a Data Breach Report 2025: https://www.ibm.com/reports/data-breach
- eSecurityPlanet — dato LayerX sobre pegado de datos en GenAI: https://www.esecurityplanet.com/news/shadow-ai-chatgpt-dlp/
