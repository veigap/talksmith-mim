---
topic: Regulaciones de datos e IA — el mapa para managers (leyes, auditorías y el EU AI Act)
language: Español
sources:
  - talk: seguridad-governance-ai
    date: 2026-07-06
    contributed: Mapa leyes vs. auditorías, SOC 2, EU AI Act, checklist del comprador; documentos de estudio de GDPR, HIPAA y Argentina curados en archivos temáticos.
last_updated: 2026-07-06
---

# Regulaciones de datos e IA — el mapa para managers

Marco regulatorio del uso de datos (y de IA) explicado para una audiencia de negocios no técnica. Este es el archivo de entrada; el detalle de cada régimen vive en los archivos temáticos:

- [`gdpr.md`](gdpr.md) — GDPR: historia, conceptos, DPA, derechos del titular, GDPR + IA.
- [`hipaa.md`](hipaa.md) — HIPAA: PHI, BAA, comparación con GDPR.
- [`argentina.md`](argentina.md) — Ley 25.326 y la reforma en curso.

## La distinción que evita la confusión: leyes vs. auditorías

| Estándar | ¿Qué es? | ¿Quién cumple? | Foco |
|---|---|---|---|
| **GDPR** | Ley (UE, extraterritorial) | Tu organización | Datos personales, derechos del titular |
| **HIPAA** | Ley (EE. UU., salud) | Tu organización + sus proveedores | Datos de salud (PHI) |
| **SOC 2** | Auditoría (AICPA) | El proveedor te la muestra | Controles de seguridad del proveedor |

Frase síntesis: *"GDPR y HIPAA te dicen qué cumplir; SOC 2 es cómo un proveedor te prueba que puede ayudarte a cumplirlo."* GDPR y HIPAA son obligaciones tuyas; SOC 2 es **evidencia** que el proveedor exhibe — no una obligación legal.

## SOC 2 en dos líneas

- **Type I** = foto del diseño de controles en un momento dado. **Type II** = efectividad sostenida en el tiempo (6–12 meses) — **el valioso**.
- La pregunta de compra cabe en un mail: **"¿Tenés SOC 2 Type II?"**

> Nota de cobertura: SOC 2 no tiene documento de estudio propio en el corpus del Talk de origen (pendiente declarado de la sesión original); el contenido proviene de la agenda de la charla. Candidato a profundizar en una futura promoción.

## EU AI Act — la primera ley amplia de IA

- Clasifica **usos**, no la tecnología: 🚫 riesgo inaceptable (prohibido: scoring social, ciertos usos biométricos) · 🔴 alto riesgo (contratación, crédito, educación, salud, infraestructura crítica — obligaciones fuertes) · 🟡 limitado (transparencia: avisar que es IA) · 🟢 mínimo (sin obligaciones nuevas).
- Fechas de entrada en vigor: obligaciones **GPAI desde el 2 de agosto de 2025**; grueso de las reglas **2 de agosto de 2026**; alto riesgo escalonado **2027–2028**.
- **Alcanza a organizaciones fuera de la UE** si sus sistemas o resultados se usan en la UE.
- Punto clave para managers: los usos de **alto riesgo son exactamente los gerenciales** (contratación, crédito, evaluación de personas). Regla práctica: *preguntá en qué nivel de riesgo cae tu caso de uso antes de desplegarlo.*

## La mini-checklist del comprador

Las 5 preguntas del manager que contrata una herramienta de IA (extensión de la pregunta de compra de SOC 2, validada contra prácticas de vendor management de programas enterprise):

1. ¿Entrenan con mis datos?
2. ¿Cuánto retienen y puedo pedir borrado?
3. ¿Firman DPA (o BAA si hay salud)?
4. ¿Dónde residen los datos? ¿Quiénes son los subprocesadores?
5. ¿SOC 2 Type II?

## Marcos de gestión complementarios

- **NIST AI RMF** — marco de gestión de riesgo de IA con cuatro funciones: gobernar / mapear / medir / gestionar. Formaliza el mensaje "seguro = gobernado". Usado como marco estructurante en training corporativo.
- **ISO/IEC 42001** — sistema de gestión de IA (mencionado como referencia de profundización).

## References

- [`../../talks/seguridad-governance-ai/research/corpus/security-ai-managers-agenda.md.md`](../../talks/seguridad-governance-ai/research/corpus/security-ai-managers-agenda.md.md) — tabla de estándares, SOC 2, EU AI Act con fechas, frase leyes vs. auditorías.
- [`../../talks/seguridad-governance-ai/research/corpus/benchmark-programas-similares-2026-07-06.md.md`](../../talks/seguridad-governance-ai/research/corpus/benchmark-programas-similares-2026-07-06.md.md) — checklist de vendors (gap 3), NIST AI RMF (gap 6).
- [`../../talks/seguridad-governance-ai/research/corpus/registro-sesion-chat.md.md`](../../talks/seguridad-governance-ai/research/corpus/registro-sesion-chat.md.md) — origen de la frase "leyes vs. auditorías".
- European Commission — AI Act: regulatory framework: https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai
- EU AI Act — Implementation timeline: https://artificialintelligenceact.eu/implementation-timeline/
