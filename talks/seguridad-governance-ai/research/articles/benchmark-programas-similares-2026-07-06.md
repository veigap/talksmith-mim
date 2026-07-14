# Benchmark — programas similares de AI Security & Governance para managers (julio 2026)

Investigación web hecha el 2026-07-06 a pedido del presenter ("Busca en internet sobre programas similares si hay algo que podemos incluir"). Objetivo: comparar el outline de la charla contra lo que cubren programas ejecutivos, cursos MBA y certificaciones equivalentes, y detectar temas no cubiertos.

## 1. Programas y certificaciones relevadas

### Executive education (universidades)
- **Carnegie Mellon — "Future of Secure AI" Executive Certificate** (Information Networking Institute, lanzado 2026). Para líderes senior: AI risk, governance, cyber-resiliencia, foresight estratégico. 4 días intensivos. Fuente: https://www.cmu.edu/ini/executive-education/future-of-secure-ai-certificate.html
- **Johns Hopkins — AI for Senior Leaders**: aplicación inmediata a governance, risk management y decisiones de adopción de AI. Fuente: https://engineering.jhu.edu/ExecEd/course/ai-for-senior-leaders-online/
- **Wharton — AI Strategy and Governance** (Coursera / Penn): accountability y marcos de AI ética, análisis de stakeholders, modelos de governance de AI y datos, evaluación de impacto regulatorio. Fuente: https://www.coursera.org/learn/wharton-ai-strategy-governance
- **MBAs con concentración AI** (JHU Carey, UNT, USI, Eastern, NDNU): sesgo algorítmico, límites de exactitud y responsabilidades derivadas, privacidad de datos, propiedad intelectual, cumplimiento regulatorio, transparencia y accountability, casos reales. Fuentes: https://carey.jhu.edu/programs/flexible-mba/artificial-intelligence-business ; https://online.usi.edu/degrees/business/mba/artificial-intelligence/ai-ethics-and-governance/

### Certificaciones profesionales
- **IAPP AIGP (AI Governance Professional)**, Body of Knowledge v2.1 (2026), 4 dominios: (I) fundamentos de AI governance, (II) leyes/estándares/frameworks aplicados a AI, (III) gobernar el desarrollo de AI, (IV) gobernar el deployment y uso. Fuente: https://iapp.org/certify/aigp
- **Securiti — AI Security & Governance Certification**: GenAI core, leyes globales de AI, obligaciones de compliance, AI risk management, frameworks de governance. ~2–2,5 h (mismo formato de duración que nuestra charla). Fuente: https://education.securiti.ai/certifications/ai-governance/

### Training corporativo de awareness (lo que las empresas dan a sus empleados)
- Temas típicos (SentinelOne, Onspring, Adaptive Security, Brightside): ingeniería social generada por AI (deepfakes de voz/video, phishing escrito por AI, BEC asistido por AI), políticas de uso seguro de GenAI, prompt injection, fuga de datos por plataformas AI, reconocimiento y verificación de deepfakes (con foco en roles de alto riesgo: ejecutivos, finanzas, legales), plan de respuesta a incidentes específico de AI (alucinaciones, errores de decisión automatizada), y NIST AI RMF como marco estructurante. Fuentes: https://www.sentinelone.com/cybersecurity-101/data-and-ai/ai-security-awareness-training/ ; https://onspring.com/resources/blog/ai-grc-employee-training/
- Entrenamiento shadow-AI recomendado: mostrar qué pasa con el dato al entrar a un LLM público, diferencia consumo vs enterprise, recorrer incidentes reales (Samsung), enseñar el uso de la herramienta aprobada. Coincide fuerte con nuestros Bloques 2/5/6. Fuente: https://www.wiz.io/academy/ai-security/chatgpt-security

## 2. Verificación de cifras (pedido del corpus: "verificar antes de slide")

- **IBM Cost of a Data Breach 2025 — CONFIRMADO**: promedio global USD 4,44 M (bajó 9% desde 4,88 M en 2024); EE. UU. USD 10,22 M; shadow AI alto suma +USD 670.000 al costo promedio; **97%** de las brechas relacionadas con AI ocurrieron en organizaciones sin controles de acceso de AI adecuados. Fuente: https://www.ibm.com/reports/data-breach
- **DISCREPANCIA**: el outline dice "83% sin controles básicos"; lo verificable en IBM 2025 es "**63%** sin políticas de AI governance" (Ponemon, n=600). Corregir o re-sourcing del 83%.
- Dato adicional utilizable: ~18% de empleados enterprise pega datos en herramientas GenAI y >50% de esos pegados incluye información corporativa (LayerX vía eSecurityPlanet). Fuente: https://www.esecurityplanet.com/news/shadow-ai-chatgpt-dlp/

## 3. Gaps del outline vs. programas relevados (candidatos a incluir)

1. **Deepfakes e ingeniería social potenciada por AI** — presente en prácticamente todo training corporativo 2026 (voice cloning al CFO, BEC, phishing hiperpersonalizado). El outline trata a la AI solo como canal de fuga, no como arma del atacante — la "Cara 1" de la S2 queda sin desarrollo. Candidato fuerte: 1–2 slides en el bloque de amenazas.
2. **Respuesta a incidentes** — el cierre dice "reportá incidentes rápido" pero ningún slide desarrolla qué hacer cuando algo sale mal (a quién avisar, por qué la velocidad importa — enlaza con las 72 h de GDPR). Los programas incluyen incident response como tema propio.
3. **Checklist de evaluación de proveedores/vendors** — la pregunta de compra del S41 ("¿tenés SOC 2 Type II?") podría ampliarse a la mini-checklist del manager que contrata una herramienta AI: ¿entrena con mis datos? ¿retención? ¿DPA? ¿residencia? ¿subprocesadores? Tema recurrente en vendor management de los cursos enterprise.
4. **Sesgo algorítmico y decisiones automatizadas** — núcleo de todo curso MBA de responsible AI (bias, transparencia, accountability); en el outline solo aparece de refilón en el slide de Argentina. Para managers que deciden con AI (contratación, crédito, evaluación) es un riesgo legal directo (GDPR art. 22, EU AI Act alto riesgo).
5. **Propiedad intelectual** — quién es dueño del output, riesgo de ingreso de IP propia y de infracción con IP ajena. En el outline quedó relegado al backup B5; los MBAs lo tratan como tema principal.
6. **NIST AI RMF** — mención de 1 línea como marco de referencia (govern/map/measure/manage) daría respaldo al mensaje "seguro = gobernado" del S9/S35 sin costo de tiempo.
7. **Política de uso de AI del equipo (AUP)** — la "jugada del manager" (S26) da la herramienta; los programas suman el paso siguiente: una política simple de uso aceptable para el equipo (qué está permitido, con qué datos, qué requiere revisión humana).

## 4. Validaciones del enfoque actual (lo que el outline ya hace bien vs. mercado)

- Duración 2 h alineada con formatos certificados equivalentes (Securiti ~2–2,5 h).
- La secuencia vocabulario → cómo funciona → impacto → prácticas → compliance cubre los 4 dominios del AIGP a nivel introductorio.
- Rompemitos con votación = práctica pedagógica destacada en cursos ejecutivos (engagement).
- Uso de Samsung como caso ancla: recomendado explícitamente por la literatura de training corporativo.
- Consumo vs. enterprise tiers: confirmado como "la diferencia que más importa" también en fuentes 2026.
