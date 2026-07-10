## Skills: enseñarle a Claude algo una sola vez

- **Concepto.** Una Skill es una instrucción reutilizable (+ scripts opcionales) que el agente carga cuando tu pedido coincide con su descripción. Un trabajo por Skill: "si escribís 'y además', dividila en dos". La frase clave: *"Todo lo que le explicás a Claude dos veces es una Skill que deberías escribir una vez."*
- **Cómo se crea una Skill en Cowork.** Dos caminos reales (Cowork es GUI: **no hay slash commands**):
  1. **Pedísela en lenguaje natural** — "armame una Skill que haga X". Claude **escribe el archivo `SKILL.md`**, pero Cowork **NO la registra/habilita** solo. Tenés que **habilitarla** en **Customize → Skills** (el botón **Save skill / Save to enable**). Recién ahí queda activa.
  2. **Subís un ZIP** — empaquetás la carpeta de la Skill como `.zip` y la cargás en **Customize → Skills → "+" → Create skill → Upload a skill**, y la activás con el toggle.
- **Requisito.** Las Skills necesitan **Code execution** habilitado (Settings → Capabilities).
- **OJO — la trampa del Save (camino 1).** Es el error más común: pedís la Skill, Claude escribe el archivo… pero si no le das **Save / enable** en Customize, no queda habilitada y parece que "no funciona".
- **Ejemplo (Atlas).** La Skill `reporte-semanal`: lee TODOS los archivos crudos de una carpeta `fuentes/` (uno por portal), consolida por empresa y genera un reporte con formato fijo. La empresa más relevante va primera (⭐). Guarda con sufijo `-new` para no pisar el ejemplo.

### Notes

La Skill es la materialización directa del paradigma "enseñá una vez, reutilizá siempre". Mostrar los dos caminos reales en Cowork: (1) pedírsela en lenguaje natural — Claude escribe el `SKILL.md`, y vos la habilitás en Customize → Skills; (2) subir un ZIP de la carpeta de la Skill por Customize → Skills. Aclarar de entrada que Cowork es GUI: no hay slash commands. El punto que NO hay que saltear es la trampa del Save: es un error real y muy común — pedís la Skill, Claude escribe el archivo, pero si no le das Save / enable no queda habilitada y parece que "no funciona". Mencionar que las Skills requieren Code execution (Settings → Capabilities). Usar `reporte-semanal` como ejemplo concreto: convierte varios archivos desordenados en un reporte prolijo. Tiempo objetivo: ~8 min.
