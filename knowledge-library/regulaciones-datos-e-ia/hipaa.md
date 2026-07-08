---
topic: HIPAA — la ley de datos de salud de EE. UU., explicada para no juristas
language: Español
sources:
  - talk: seguridad-governance-ai
    date: 2026-07-06
    contributed: Documento de estudio completo (PHI, BAA, reglas, multas, enforcement) más el punto central para IA (PHI sin BAA = incumplimiento inmediato) y la comparación con GDPR.
last_updated: 2026-07-06
---

# HIPAA — explicado para managers

## Qué es

- **HIPAA** (*Health Insurance Portability and Accountability Act*): ley federal de **EE. UU., de 1996**, que protege la **información de salud** — regula quién puede ver, usar y compartir datos médicos.
- A diferencia del GDPR (todos los datos personales, extraterritorial), HIPAA es **sectorial y nacional**: solo datos de salud, solo EE. UU. Relevante únicamente si tocás datos de salud.
- Dato histórico útil: HIPAA **no nació como ley de privacidad** — sus metas originales fueron la *portabilidad* del seguro al cambiar de empleo y la simplificación administrativa; la privacidad se volvió el corazón de la ley por capas: Privacy Rule (2003), Security Rule (2005), HITECH (2009, endureció enforcement y extendió obligaciones a los business associates), Omnibus Rule (2013).

## Conceptos mínimos

- **PHI — Protected Health Information**: información de salud identificable manejada por una entidad cubierta (diagnósticos, tratamientos, laboratorio, facturación médica, identificadores asociados). En formato electrónico: **ePHI**.
- **Entidades cubiertas**: prestadores que transmiten datos electrónicamente, planes de salud, cámaras de compensación.
- **Business associates**: terceros que manejan PHI en nombre de una entidad cubierta — nube, facturación, IT… **y herramientas de IA**. Directamente responsables desde HITECH/Omnibus.
- **BAA — Business Associate Agreement**: el contrato obligatorio con un business associate — **el "primo del DPA"** del GDPR.
- **Minimum necessary**: usar solo el mínimo de PHI necesario para la tarea (eco de la minimización del GDPR).
- Las cuatro reglas: Privacy Rule, Security Rule (salvaguardas administrativas/físicas/técnicas), Breach Notification Rule (**60 días** para notificar), Enforcement Rule.

## El punto central para IA

**Pegar PHI en una herramienta de IA sin BAA = incumplimiento inmediato, aunque nada se filtre.** La mayoría de las herramientas de IA de consumo **no firman BAAs**; solo planes específicos de salud o ciertos enterprise ("HIPAA-eligible") lo hacen.

> *"Sin BAA firmado, ninguna herramienta — por buena que sea — puede tocar PHI legalmente. '¿Firmás un BAA?' es la pregunta que separa una herramienta usable en salud de una que no lo es."*

Riesgos adicionales de la IA de consumo en salud: retención y entrenamiento con lo ingresado (pérdida de control sobre PHI irrecuperable); sin logs ni control de acceso no se puede cumplir la Security Rule ni responder a una auditoría de la OCR.

## Multas y enforcement

- Multas **por violación**, en cuatro niveles según grado de culpa, ajustadas por inflación. ⚠️ **Verificar antes de citar**: el rango "US$ 145 – 2.190.294 por violación (2025–2026)" y el caso **Warby Parker (US$ 1,5M, feb 2025)** provienen del documento de estudio y requieren confirmación de cifras/contexto.
- Enforcement por la **OCR** (Office for Civil Rights, HHS); 2024–2025 con totales anuales de acuerdos de los más altos de su historia (22 en 2024, 21 en 2025 según el documento fuente).
- A diferencia del GDPR (porcentaje de facturación global), HIPAA multa por violación — pero una brecha con miles de registros escala rápido.

## GDPR vs. HIPAA — "son primos con la misma lógica"

| | **HIPAA** | **GDPR** |
|---|---|---|
| Origen | EE. UU., 1996 | UE, 2018 |
| Alcance | Sectorial: solo salud | Todos los datos personales |
| A quién aplica | Entidades de salud + business associates | Extraterritorial |
| Contrato con terceros | **BAA** | **DPA** |
| Multas | Por violación, con topes anuales | Hasta €20M o 4% global |
| Autoridad | OCR / HHS | Autoridades de cada país |

Misma lógica en ambos: rendición de cuentas + contrato obligatorio con proveedores (BAA↔DPA) + derechos de las personas + notificación de brechas. La conclusión también es la misma: el cumplimiento no depende de "tener cuidado" sino de **usar solo herramientas gobernadas**.

## References

- [`../../talks/seguridad-governance-ai/research/corpus/hipaa-explicado.md.md`](../../talks/seguridad-governance-ai/research/corpus/hipaa-explicado.md.md) — documento de estudio fuente (historia por capas, reglas, glosario, enforcement).
- HHS.gov — HIPAA for Professionals: https://www.hhs.gov/hipaa/for-professionals/index.html
- HIPAA Journal — Penalties for HIPAA Violations: https://www.hipaajournal.com/what-are-the-penalties-for-hipaa-violations-7096/
