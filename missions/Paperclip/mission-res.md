# 🏛️ Solución paso a paso — "El vigía regulatorio de Atlas"

> Guía de resolución de `mission.md`. **Verificada contra la documentación oficial de Paperclip** (conceptos: Goals, Projects, Tasks/Issues, Agents, Heartbeats, Hiring, Org Structure). Los textos para copiar van *en cursiva/comillas* o en bloque; lo que hay que **hacer**, como acción.

---

## 📖 Glosario Paperclip (para no perderse)

- **Company** — Atlas. Tiene **un** goal raíz de compañía.
- **Goal** — objetivo con nivel **company / team / agent / task**; tiene *owner* y *parent* (todo cuelga del goal de compañía). Debe medir **resultados**, no actividad.
- **Project** — agrupa tasks y se liga a un goal (ej. «Aumentar el reconocimiento de marca»).
- **Task (Issue)** — la unidad de trabajo. Identificador `ACMA-###`. Estados: `backlog → todo → in_progress → in_review → done`. **Un solo asignado**. Puede tener `parent` (subtarea) y siempre traza a un goal.
- **Agent** — un empleado de IA (rol, `reportsTo`, `capabilities`, presupuesto, adapter).
- **Heartbeat** — ciclo de ejecución del agente. Se agenda por **`intervalSec`** (mínimo 30s). Se puede disparar a mano.
- **Board** — vos. Aprobás contrataciones pedidas por agentes y hacés de compuerta humana (las tasks paran en `in_review`).

> La **compuerta humana** del pipeline = la task queda en **`in_review`** hasta que vos (o el Content Reviewer) la pasás a `done`.

---

## 🧰 Antes de empezar (estado inicial)

- La org de `atlas-org-setup.md` cargada en Paperclip (prefijo de issues **ACMA**), **sin el Director de Relaciones Institucionales**.
- El **goal de compañía** (posicionamiento de marca) y el **proyecto «Aumentar el reconocimiento de marca»** existen.
- Vos entrás como **board** (creás agentes y hacés de compuerta humana).

> ✅ **Verificación:** ves el CEO, CMO, contenido y legales; el proyecto de marca abierto; **ningún** Director de Relaciones Institucionales.

---

## Paso 1 — La forma manual (una task para el agente de marketing)

**El objetivo:** sentir el límite reaccionando como hoy — le tirás la task directo al CMO.

**Hacé esto:** en **Tasks → Create Task**, dentro del proyecto **«Aumentar el reconocimiento de marca»**:

```
Título:      Blog: reforma de integridad en la cadena de suministro (Ley 27.401)
Descripción: Impacto en proveedores de Vaca Muerta. Enfoque técnico, para ingenieros
             de perforación y compras. Que salga esta semana.
Asignado a:  CMO (agente de marketing)
Goal/Proyecto: «Aumentar el reconocimiento de marca»
Estado:      todo
```

El CMO lo toma en su heartbeat (**checkout** `todo → in_progress`), lo baja a su equipo de contenido, y la task termina en **`in_review`** esperando tu visto bueno.

**Qué vas a notar:** el CMO **improvisa el encuadre** de un tema sensible, **sin evaluación de riesgo ni chequeo legal previo**. En corrupción/transparencia, así nació el blog que hubo que bajar.

> 🏁 **Éxito:** la task llega a `in_review`, y podés explicar por qué a mano no escala (reactivo, sin dueño, riesgoso).

---

## Paso 2 — Sumar al Director (goal → proyecto → agente → instrucciones)

### 2.1 · Crear el goal (nivel *team*, por resultado)

En **Goals → Create Goal**:

```
Título:     Anticipación regulatoria
Descripción: Que ningún cambio normativo material sorprenda a Atlas: detectarlos a tiempo
            —los que afecten a Atlas o a sus clientes de Vaca Muerta— y convertirlos en
            posicionamiento técnico de marca.
Nivel:      team
Parent:     <goal de compañía: posicionamiento orgánico de marca>
Owner:      Director de Relaciones Institucionales   (lo asignás al crearlo en 2.3)
```

> 📌 Es un **goal de team** que cuelga del goal de compañía — así el trabajo del Director traza hasta la misión. La **descripción** mide por **resultado** ("que ningún cambio material sorprenda"), no por actividad ("vigilar cada semana"), como pide la doc.

### 2.2 · Crear el proyecto «Radar Regulatorio»

En **Projects → Create Project**:

```
Nombre:      Radar Regulatorio
Goal:        Ningún cambio regulatorio material sorprende a Atlas
Descripción: Vigilancia semanal del panorama regulatorio de Vaca Muerta y del sector
            de petróleo y gas. Casa de las notas de riesgo del Director.
```

Es donde el heartbeat corre y quedan las **notas de riesgo** (cada una, una task en este proyecto).

### 2.3 · Contratar al agente (Board Direct Hire)

En **Agents → Create Agent**. Como sos el **board**, es contratación directa — **no genera approval** (el approval es solo cuando *otro agente* pide contratar). Configuración:

```
name:        Director de Relaciones Institucionales
role:        institutional_relations
title:       Director de Relaciones Institucionales
reportsTo:   CEO
budgetMonthlyCents: 20000            # $200/mes; escalás sin volar el presupuesto
adapterType: process
adapterConfig:
  adapter: claude_local             # o el runtime que uses
  heartbeatSchedule: { enabled: true, intervalSec: 604800 }   # ~semanal (V1 = por intervalo)
capabilities: <lo del 2.4>
```

> ⚠️ **Heartbeat "semanal" ≠ "lunes 8am".** V1 agenda por **`intervalSec`** (≈ 604800s = 7 días), no por día de la semana. Mínimo 30s.

### 2.4 · Escribir sus `capabilities` / instrucciones (la rutina del heartbeat)

Paperclip **no tiene un "charter"**: el comportamiento del agente vive en su campo **`capabilities` / instrucciones**. Pegá esto (es la definición de rol existente **+** el detalle nuevo):

> **Rol.** Director de Relaciones Institucionales de Atlas. Asuntos gubernamentales en petróleo y gas de Argentina: monitoreo regulatorio, vínculo con stakeholders y posicionamiento institucional. Reportás al CEO.
>
> **Qué hacés en cada heartbeat (semanal):**
> 1. **Investigá** cambios regulatorios/legislativos —vigentes y en trámite— relevantes para Atlas: Vaca Muerta, régimen de hidrocarburos y RIGI, normativa provincial (Neuquén/Río Negro), ambiental/emisiones, certificación (IRAM/API/ISO) e **integridad/transparencia en la cadena de suministro**.
> 2. **Evaluá materialidad** (bajo/medio/alto, con una línea): ¿impacta los intereses de Atlas o la actividad de sus clientes, como riesgo u oportunidad?
> 3. **Si hay algo material:** creá una **task "nota de riesgo" en el proyecto Radar Regulatorio** (asignada a vos). Y **creá una task de blog en el proyecto «Aumentar el reconocimiento de marca», asignada al CMO**, con el brief de abajo. En temas de **alta sensibilidad** (corrupción/transparencia), la revisión del **CLO es obligatoria** antes de que el blog avance.
> 4. **Si no hay nada material:** dejá una task/comentario de "sin acción" y cerrá la corrida.
>
> **Barreras:** contenido **técnico y factual**, nunca militancia ni lobby, **sin acusar a personas ni empresas**. Vos **proponés y armás el brief**; no escribís ni publicás el blog. La compuerta final es humana (la task queda en `in_review`).

**Brief del blog** (en la descripción de la task para el CMO):

```
- Título tentativo
- Por qué ahora (el cambio regulatorio y su estado)
- Impacto en Atlas (interés comercial / clientes / Vaca Muerta)
- Ángulo editorial (técnico, no partidario)
- Puntos clave a cubrir
- Audiencia (ingenieros de perforación, compras, operadores)
- Sensibilidad / urgencia + si requiere revisión del CLO
```

> 🏁 **Éxito:** existen el **goal** (team) y el **proyecto** Radar Regulatorio; el **Director** está creado, reporta al CEO, con `heartbeatSchedule` semanal y las `capabilities` de arriba.

---

## Paso 3 — Correr un heartbeat y observar

**El objetivo:** ver el handoff dispararse solo, sin pedido manual.

**Hacé esto:**
1. Dispará un heartbeat del Director a mano: **Agents → Director → "Run heartbeat now"** (equivale a `POST /api/agents/{id}/heartbeat/invoke`, o CLI `paperclipai heartbeat run --agent-id {id}`).
2. Mirá la **heartbeat run**: crea la **task "nota de riesgo"** en *Radar Regulatorio* y la **task de blog** en el proyecto de marca, **asignada al CMO** (`todo`).
3. El **CMO**, en su heartbeat, hace **checkout** de esa task (`todo → in_progress`), la trabaja y la deja en **`in_review`** para tu visto bueno.

> 🏁 **Éxito:** una sola corrida del Director produjo (a) una nota de riesgo (task en Radar) y (b) una task de blog asignada al CMO en el proyecto de marca — **sin que pidieras nada**. Lo reactivo del Paso 1 ahora es proactivo y con dueño.

> 🛠️ **Si algo sale mal:**
> - *El heartbeat no crea nada* → revisá que las `capabilities` incluyan el paso 3; forzá una corrida con el tema de ejemplo; mirá el log de la run.
> - *La task no le llega al CMO* → confirmá `assigneeAgentId = CMO` y que la task esté ligada al goal/proyecto de marca (si no, Paperclip rechaza la task por falta de goal).
> - *Sale con tono de denuncia* → reforzá las barreras en las `capabilities` (técnico, sin acusar; pedir CLO).

---

## 🔄 El círculo completo (con estados reales)

![Cómo se conecta la historia](img/diagrama-conexion.png)

`Heartbeat (intervalSec ~semanal)` → el **Director** detecta un riesgo → **task "nota de riesgo"** (proyecto *Radar Regulatorio*) **+** **task de blog** (`todo`, asignada al **CMO**, proyecto de marca) → el **CMO** hace **checkout** (`in_progress`) → **`in_review`** (compuerta humana: vos/Content Reviewer) → **`done`** → cumple el **goal de compañía**. Escalaste la automatización: ahora la IA también **vigila**, no solo escribe.

---

## 🎤 Guía rápida para el facilitador

| Momento | Qué mostrar en vivo | Concepto que "cae" |
|---|---|---|
| Paso 1 · task al CMO | El blog improvisado llegando a `in_review` | "Reaccionar a mano no escala y es riesgoso" |
| Paso 2.1–2.2 · goal + proyecto | Crear el goal *team* y el proyecto Radar | "Un agente necesita un para qué (goal) y un dónde (proyecto)" |
| Paso 2.3 · Board hire | Crear el Director (reportsTo CEO, heartbeat semanal) | "Escalar = sumar un agente, no una persona" |
| Paso 2.4 · capabilities | Pegar la rutina del heartbeat | "El comportamiento del agente se escribe en texto" |
| Paso 3 · run | El heartbeat creando la task para el CMO solo | "Handoff automático entre agentes, con estados y compuerta humana" |

---

## 🧭 Decisiones de diseño (cerradas)

1. **Ruta del handoff (Director → CMO):** **asignación directa** — el Director crea la task y la asigna al CMO (la doc permite asignación manual a cualquier agente, con visibilidad total en la company). *Alternativa, si querés delegación estricta por el árbol: rutearla por el CEO (un hop extra).*
2. **Proyecto vs. task:** «Aumentar el reconocimiento de marca» es un **proyecto**; el blog es una **task nueva en ese proyecto** asignada al CMO. Si querés jerarquía visible, colgala como **child task** (`parent`) de una task madre del proyecto.
3. **Cadencia / CLO:** heartbeat **semanal** (una semana sin riesgo deja una task de "sin acción" visible); en temas de **alta sensibilidad**, revisión del **CLO obligatoria** antes de pasar al CMO.
4. **Approval:** contratar al Director **por el board no requiere approval** (el approval es solo para hires pedidos por un agente).

---

## 📚 Fuentes (documentación oficial de Paperclip)

- [What is Paperclip?](https://paperclipai-paperclip.mintlify.app/introduction)
- [Concepts — Goals](https://paperclipai-paperclip.mintlify.app/concepts/goals) · [Tasks](https://paperclipai-paperclip.mintlify.app/concepts/tasks) · [Heartbeats](https://paperclipai-paperclip.mintlify.app/concepts/heartbeats) · [Org Structure](https://paperclipai-paperclip.mintlify.app/concepts/org-structure)
- [Guides — Hiring Agents](https://paperclipai-paperclip.mintlify.app/guides/hiring-agents) · [Task Management](https://paperclipai-paperclip.mintlify.app/guides/task-management) · [Governance & Approvals](https://paperclipai-paperclip.mintlify.app/guides/governance-approvals)
- [GitHub — paperclipai/paperclip](https://github.com/paperclipai/paperclip)
