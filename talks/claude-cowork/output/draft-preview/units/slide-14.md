## (Sideway) Archivos MD y metadata: el lenguaje común del mundo LLM

- **Concepto.** Casi todo lo que configurás alrededor de un agente — Instrucciones, Skills (`SKILL.md`), archivos de agentes, docs de plugins, salidas — es texto plano en **Markdown** (`.md`). Markdown es la *lingua franca* del mundo LLM.
- **Qué es la metadata / los headers.** Muchos de esos archivos arrancan con un bloque de **metadata** (un "header" en YAML): por ejemplo, un `SKILL.md` declara `name` y `description`. Esa descripción es lo que dispara la Skill — de forma semántica, no por palabra clave.
- **Por qué esto es importante en el mundo LLM.**
  - El modelo lee texto: si la configuración es texto plano legible, el agente la entiende directamente, sin formato propietario.
  - La metadata le dice al sistema *qué es* cada archivo y *cuándo* usarlo (la `description` de una Skill decide cuándo se activa).
  - Es portable y versionable: el mismo estándar `SKILL.md` funciona entre herramientas (Cowork y Codex usan el mismo formato).
- *Nota de alcance:* esto es un sideway de alto nivel — qué es y por qué importa. No entramos en el detalle del formato de archivos.

### Notes

Sideway breve y de alto nivel — explícitamente NO un deep dive de formato de archivos. La idea a transmitir: en el mundo LLM, la configuración es texto plano (Markdown) porque el modelo lee texto, y la metadata (el header YAML) le dice al sistema qué es cada archivo y cuándo usarlo. El ejemplo más tangible es la `description` de una Skill: no es decoración, es lo que decide si la Skill se activa o no para un pedido dado. Cerrar con la portabilidad: el mismo `SKILL.md` sirve en distintas herramientas. Mantenerlo en ~5 min — es contexto, no el plato principal.
