# Learnings

> Format spec, loading semantics, and promotion rules live in [`${CLAUDE_PLUGIN_ROOT}/schemas/learnings.md`](${CLAUDE_PLUGIN_ROOT}/schemas/learnings.md).

## Entries

<!-- Editor role appends promoted learnings below this line during the Step 7 Promote pass. -->

### Fuente visible en lámina para toda estadística

**Rule:** Toda estadística que aparece en una lámina lleva su referencia de fuente visible en la lámina, en forma corta (p. ej. "IBM 2025", "LayerX 2025").

**Why:** Pedido explícito del presenter ("Cada una de estas tiene que tener referencia a las fuentas"), adoptado como requisito permanente y aplicado deck-wide en este Talk: al agregar el slide de números de la apertura (1.9) se auditó el deck completo y se atribuyeron las cifras que faltaban (el 10,22M de 5.3 y el dato LayerX de 6.1).

**Where it applies:** Slide content — todo slide con cifras o estadísticas (los datos legales fijos, como plazos o topes de multa de una norma, no requieren atribución en lámina).

**Evidence:** seguridad-governance-ai:2026-07-06 (backlog: grupo Samsung/números — Slide "3. Qué hicieron: tres usos cotidianos", tags [slide-content, missing-evidence, add-source, split]; la auditoría deck-wide quedó registrada en la resolution de esa fila, movida a feedback-processed.md)

**Added:** 2026-07-06
