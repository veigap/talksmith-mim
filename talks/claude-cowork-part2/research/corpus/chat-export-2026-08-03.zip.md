---
source_file: chat-export-2026-08-03.zip
source_type: chat-export
ingested_at: 2026-08-03
---

# Exploración para Cowork — continuación y Claude Code

## Provenance
- Original location: research/llm-chats/chat-export-2026-08-03.zip
- Format: zip-chat (Markdown export)
- Author / source (if known): conversación de planificación del presentador con un asistente
- Date of original (if known): 2026-08-03

## Key claims
- La nueva clase debe empezar con un review/quiz de lo aprendido sobre chat, Cowork, Connectors, Projects, archivos `.md` y Skills.
- La profundización propuesta para Cowork se organiza en Artifacts, conocimiento/contexto y plugins, antes de una introducción breve a Claude Code.
- Un Artifact de chat y un Live Artifact de Cowork se distinguen por persistencia, fuentes de datos, disponibilidad, posibilidades de compartir y permisos.
- El conocimiento verificable debe vivir en archivos; las Instructions definen cómo debe trabajar Claude; Memory aporta continuidad; un Project delimita el ámbito donde ese contexto tiene sentido.
- Claude Code puede presentarse a un público no técnico como una forma de delegar la construcción o modificación de software: entiende un proyecto, propone un plan, modifica archivos, prueba y deja cambios revisables.

## Definitions and terminology
- **Artifact de chat:** pieza autosuficiente de contenido o una herramienta creada dentro de una conversación.
- **Live Artifact de Cowork:** vista HTML interactiva y persistente de un trabajo, que puede volver a consultar conectores y archivos locales autorizados.
- **Instructions:** reglas explícitas del Project sobre idioma, formato, fuentes prioritarias, límites y momentos de consulta.
- **Memory:** continuidad aprendida o recuperada para un trabajo; no reemplaza documentación ni evidencia.
- **Project:** espacio que agrupa contexto de un tema y delimita dónde aplica.
- **Archivos:** fuente de verdad auditable para hechos, políticas, fuentes, plantillas y decisiones.
- **Claude Code:** agente que trabaja sobre una base de software y permite planificar, modificar, probar y revisar cambios.

## Evidence and examples
- Quiz de cinco preguntas con tres opciones sobre delegación, Connectors, Cowork, Skills y archivos `.md`.
- Caso de Artifact: tracker de competidores de sólo lectura con precio, lanzamientos, fuentes y relevancia.
- Caso de conocimiento: Project de Faro con `competidores.md`, Instructions de formato, una preferencia en Memory y una Skill para el informe semanal.
- Caso de Claude Code: herramienta de seguimiento de competidores con tabla ordenable y marcas para datos vencidos.
- La fuente conserva enlaces a documentación oficial de Anthropic sobre Cowork, Artifacts, Live Artifacts, Memory, Projects y Claude Code.

## Inconsistencies / open questions
- La conversación primero caracterizó Dispatch como un orquestador de tareas hijas. Luego se corrigió: para los alumnos debe explicarse ante todo como la posibilidad de enviar una tarea o sesión de código a una computadora host; no usar la primera explicación como fuente docente.
- Se identificó una corrección potencial al material anterior sobre Schedule y carpetas locales. Verificarla contra documentación oficial si Schedule aparece en la nueva clase.
- La propuesta inicial de módulos omitió Artifacts y luego fue corregida; la decisión vigente del presentador es incluir Artifacts.
- Falta confirmar el alcance concreto de plugins y si se reutilizarán diapositivas o fuentes de las dos presentaciones previas.

## Images / diagrams
- Ninguna imagen incluida en el archivo exportado.

## Raw / preserved excerpts

`````markdown
# Exportación de conversación

- Tarea: 019fc79f-bbc6-7452-971b-5aa0577051cd
- Exportado: 2026-08-03
- Incluye mensajes del usuario y respuestas visibles del asistente. No incluye razonamientos ni salidas de herramientas.

## Usuario

Hola

## Asistente

¡Hola! ¿En qué te gustaría que trabajemos?

## Usuario

Quiero emplezar a explorar temas adicionales relacionado a Claude CoWork para una presentacion. Se presento la introduccion y Chat Destkop y CoWork. En la clase voy a empezar repasando temas que se hablaron. Para eso, empiezo con un quick multiple choise de 5 preguntas. Cuales serian buenas preguntas para saber si los conceptos estan fijados

## Asistente

Estas 5 preguntas apuntan a distinguir conceptos, no sólo recordar nombres:

1. ¿Cuál describe mejor la diferencia entre Claude Desktop y Claude Cowork?

   - A. Desktop sirve para conversar; Cowork para delegar trabajo sobre archivos y tareas. ✅  
   - B. Cowork sólo funciona en el navegador.  
   - C. Desktop no puede trabajar con documentos.  
   - D. Son exactamente el mismo producto con distinto diseño.

2. Antes de que Claude Cowork modifique archivos o ejecute una acción relevante, ¿qué conviene hacer?

   - A. Darle acceso total para que sea más rápido.  
   - B. Revisar qué acción propone, qué archivos afecta y confirmar sólo si corresponde. ✅  
   - C. Cerrar la aplicación.  
   - D. Pedirle que repita la respuesta en otro chat.

3. ¿Qué tipo de pedido aprovecha mejor Cowork?

   - A. “¿Cuál es la capital de Japón?”  
   - B. “Revisa estos documentos, identifica inconsistencias y prepara un borrador de resumen.” ✅  
   - C. “Dime un chiste.”  
   - D. “Define inteligencia artificial en una palabra.”

4. ¿Por qué es útil dar contexto y criterios de éxito al iniciar una tarea?

   - A. Porque hace que Claude responda con más texto.  
   - B. Porque reduce ambigüedades y permite evaluar si el resultado cumple el objetivo. ✅  
   - C. Porque elimina la necesidad de revisar el resultado.  
   - D. Porque impide que Claude haga preguntas.

5. ¿Cuál es la mejor forma de trabajar con resultados producidos por Claude?

   - A. Copiarlos y usarlos sin revisar.  
   - B. Considerarlos un primer borrador: verificar datos, criterio y cambios antes de usarlos. ✅  
   - C. Pedir siempre una única respuesta muy larga.  
   - D. Evitar dar retroalimentación.

Podés abrir con una consigna breve: “Respondan individualmente; después discutimos por qué las alternativas incorrectas son tentadoras.” Eso convierte el quiz en repaso conceptual, no sólo en evaluación.

## Usuario

No revisaste las presentaaciones en el disco. ?

## Asistente — avance

Tenés razón: respondí con supuestos generales y no revisé el material local. Voy a usar el flujo de presentaciones para ubicar y leer las diapositivas antes de reformular el quiz.

## Asistente — avance

El entorno de archivos rechazó el acceso al directorio del proyecto incluso para listar su contenido. Voy a reintentar la inspección con acceso al directorio compartido, sin modificar nada.

## Usuario

Lee final.md como documentos

## Usuario

Por que "EPERM: operation not permitted, scandir '/Users/pveiga/Documents/Austral/talksmith-mim'"

## Usuario

Volvamos a procesas. Ahora parece que tenes accesso

## Asistente — avance

Sí, ahora el directorio ya aparece accesible. Voy a revisar los `final.md` para reconstruir los conceptos que ya se presentaron y ajustar las preguntas a ese material.

## Asistente

Sí. Ahora revisé los tres materiales: [introducción](/Users/pveiga/Documents/Austral/talksmith-mim/talks/intro-curso-mim/final.md), [Claude Desktop–Chat](/Users/pveiga/Documents/Austral/talksmith-mim/talks/claude-desktop-chat/final.md) y [Claude Cowork](/Users/pveiga/Documents/Austral/talksmith-mim/talks/claude-cowork/final.md).

Para abrir la clase, usaría estas cinco preguntas, centradas en los conceptos ancla que ya vieron:

1. ¿Qué cambia principalmente al pasar de chatear con IA a delegar a un agente?

   - A. El agente responde más rápido.
   - B. Se describe un resultado; el agente planifica y ejecuta, mientras la persona revisa y guía. ✅
   - C. Ya no hace falta dar contexto.
   - D. La salida deja de requerir revisión humana.

2. Un chat de IA “de fábrica” responde principalmente a partir de:

   - A. Los archivos, mails y calendario del usuario.
   - B. Información actualizada automáticamente en tiempo real.
   - C. Su memoria de entrenamiento y lo que recibe en el prompt. ✅
   - D. Las decisiones tomadas en conversaciones anteriores.

3. ¿Qué diferencia mejor a la búsqueda web de un Connector?

   - A. La búsqueda web consulta información actual; un Connector conecta el chat con sistemas del usuario y puede también ejecutar acciones. ✅
   - B. Los Connectors sólo sirven para buscar en internet.
   - C. La búsqueda web permite editar archivos locales.
   - D. No hay diferencia: son dos nombres para lo mismo.

4. En Cowork, ¿sobre qué trabaja el agente cuando se le delega una tarea?

   - A. Sólo sobre el texto visible en la ventana de chat.
   - B. Sobre una carpeta o Project: lee el material disponible y deja allí archivos, entregables y notas. ✅
   - C. Sobre todos los archivos de la computadora sin necesidad de permisos.
   - D. Únicamente sobre documentos PDF.

5. ¿Cuál es el mejor criterio para decidir si una tarea merece una Skill?

   - A. Si se la explicás a Claude más de una vez y querés repetirla con el mismo proceso y formato. ✅
   - B. Si requiere una respuesta creativa cada vez.
   - C. Si tiene varias tareas no relacionadas en un mismo pedido.
   - D. Si contiene información sensible de clientes.

La última abre muy bien la transición: “Entonces, si una tarea se repite, ¿cómo la convertimos en una instrucción reutilizable y gobernable?”

## Usuario

Que sean 3 opciones.

## Asistente

Claro. Las mismas cinco, con tres opciones:

1. ¿Qué cambia al pasar de chatear con IA a delegar a un agente?

   - A. Se describe un resultado; el agente planifica y ejecuta, mientras la persona revisa y guía. ✅
   - B. Ya no hace falta dar contexto.
   - C. La salida no requiere revisión humana.

2. Un chat de IA “de fábrica” responde principalmente a partir de:

   - A. Los archivos, mails y calendario del usuario.
   - B. Su memoria de entrenamiento y lo que recibe en el prompt. ✅
   - C. Información actualizada automáticamente en tiempo real.

3. ¿Qué diferencia mejor a la búsqueda web de un Connector?

   - A. La búsqueda web consulta información actual; un Connector conecta sistemas del usuario y puede ejecutar acciones. ✅
   - B. Los Connectors sólo sirven para buscar en internet.
   - C. No hay diferencia: son dos nombres para lo mismo.

4. En Cowork, ¿sobre qué trabaja el agente cuando se le delega una tarea?

   - A. Sólo sobre el texto visible en la ventana de chat.
   - B. Sobre una carpeta o Project: lee material y deja allí entregables y notas. ✅
   - C. Sobre todos los archivos de la computadora, sin permisos.

5. ¿Cuándo conviene crear una Skill?

   - A. Cuando explicás la misma tarea más de una vez y querés repetir proceso y formato. ✅
   - B. Cuando la tarea incluye varias cosas no relacionadas.
   - C. Cuando contiene datos sensibles de clientes.

## Usuario

Y la respuesta a cada uno y por que

## Asistente

1. ¿Qué cambia al pasar de chatear con IA a delegar a un agente?

   - A. Se describe un resultado; el agente planifica y ejecuta, mientras la persona revisa y guía. ✅
   - B. Ya no hace falta dar contexto.
   - C. La salida no requiere revisión humana.

   Respuesta: A. La diferencia central es el rol humano: se deja de pedir pasos uno por uno y se delega un resultado. Pero la persona conserva el criterio, supervisa el plan y verifica la entrega.

2. Un chat de IA “de fábrica” responde principalmente a partir de:

   - A. Los archivos, mails y calendario del usuario.
   - B. Su memoria de entrenamiento y lo que recibe en el prompt. ✅
   - C. Información actualizada automáticamente en tiempo real.

   Respuesta: B. Sin extensiones, el modelo no ve información nueva ni sistemas personales. Su comportamiento se modifica con el contexto que recibe en el prompt.

3. ¿Qué diferencia mejor a la búsqueda web de un Connector?

   - A. La búsqueda web consulta información actual; un Connector conecta sistemas del usuario y puede ejecutar acciones. ✅
   - B. Los Connectors sólo sirven para buscar en internet.
   - C. No hay diferencia: son dos nombres para lo mismo.

   Respuesta: A. La web resuelve el acceso a información actual y fuentes; los Connectors conectan el chat con herramientas como mail, calendario o documentos, permitiendo consultar información y, según el permiso, actuar sobre esos sistemas.

4. En Cowork, ¿sobre qué trabaja el agente cuando se le delega una tarea?

   - A. Sólo sobre el texto visible en la ventana de chat.
   - B. Sobre una carpeta o Project: lee material y deja allí entregables y notas. ✅
   - C. Sobre todos los archivos de la computadora, sin permisos.

   Respuesta: B. La carpeta es el espacio de trabajo: allí está el conocimiento e instrucciones que el agente necesita, y allí produce archivos, borradores y entregables. El acceso es deliberado, no automático a toda la computadora.

5. ¿Cuándo conviene crear una Skill?

   - A. Cuando explicás la misma tarea más de una vez y querés repetir proceso y formato. ✅
   - B. Cuando la tarea incluye varias cosas no relacionadas.
   - C. Cuando contiene datos sensibles de clientes.

   Respuesta: A. Una Skill convierte una tarea recurrente en un instructivo reutilizable. Debe tener un trabajo claro; si incluye un “y además”, probablemente convenga separarla en dos Skills. Los datos sensibles no deberían usarse como disparador para automatizar.

## Usuario

Cambiemos esta por "Un chat de IA “de fábrica” responde principalmente a partir de" uso de archivos.md

## Asistente

2. ¿Por qué conviene usar archivos `.md` para el conocimiento e instrucciones de una tarea?

- A. Porque son texto estructurado que el agente puede leer y usar directamente como contexto. ✅
- B. Porque impiden que el agente modifique archivos.
- C. Porque sólo pueden abrirse desde Claude Cowork.

Respuesta: A. Los archivos `.md` permiten guardar notas, referencias e instrucciones en un formato simple, portable y fácil de estructurar. Cowork puede leerlos dentro de la carpeta de trabajo y usarlos para entender qué tiene que hacer.

## Usuario

Ahora, dado esto. Que temas de cowork seria convenientes en cubrir. Busca si hay cursos y la documentacion.

## Asistente — avance

Voy a contrastar el contenido ya cubierto con la documentación oficial de Claude Cowork y con cursos o guías públicas actuales, para proponer un bloque siguiente que complemente —sin repetir— la presentación.

## Asistente — avance

Encontré un punto importante para actualizar: la documentación vigente distingue entre tareas programadas remotas —que no pueden usar una carpeta local— y trabajo local vía Desktop/Dispatch. Lo incorporaré como tema y como corrección del material ya presentado.

## Asistente

Sí. El material que ya presentaste cubre muy bien las piezas: chat vs. delegación, Connectors, Schedule, carpetas y `.md`, Projects, Instructions, Skills, subagentes y cuidados. Yo evitaría sumar otra “lista de funcionalidades”; el próximo paso debería ser enseñar a convertir esas piezas en un flujo de trabajo confiable.

Mi prioridad sería:

| Tema siguiente | Por qué conviene | Actividad sugerida |
|---|---|---|
| 1. Cómo delegar bien una tarea | Es el hueco más importante: objetivo, fuentes, formato de salida, restricciones, criterio de calidad y puntos de aprobación. | Dar tres pedidos ambiguos y hacer que los grupos los conviertan en un brief delegable. |
| 2. Supervisar y verificar el trabajo | Cowork planifica, ejecuta y entrega; el manager debe revisar el plan, pedir correcciones y verificar la fuente antes de usar el resultado. | Un agente prepara un brief de mercado con citas; los alumnos detectan qué afirmación deben verificar antes de recomendar una decisión. |
| 3. El flujo reutilizable: Project → Skill → Schedule | No enseñar estas piezas aisladas, sino como una escalera: ordenar el contexto, codificar una tarea repetida y automatizarla. | Construir un “informe semanal” a partir de notas, una plantilla y una Skill. |
| 4. Automatización: Schedule vs. Dispatch | Son dos modos distintos de trabajo autónomo: Schedule repite una instrucción con cadencia; Dispatch toma un resultado amplio y lo ejecuta en segundo plano mediante tareas hijas. | Clasificar casos: “reporte semanal”, “analizar 20 competidores”, “ordenar una carpeta”, “preparar una reunión”. |
| 5. Plugins y conectores como paquete de trabajo | Ya mostraron Skills y subagentes. Falta enseñar cuándo conviene instalar/evaluar un plugin, personalizarlo y distribuir una práctica de equipo. | Auditar un plugin: qué conectores instala, qué permisos pide, qué datos puede leer/escribir y qué tarea resuelve. |
| 6. Computer use y seguridad | Es una capacidad potente y una excelente conversación de management: cuándo usar Connector, navegador o interacción directa con pantalla; y cuándo no usar ninguno. | Demo de bajo riesgo y matriz de decisión: “permitir / aprobar manualmente / no delegar”. |

Hay una corrección importante para el material de `Schedule`: la documentación actual indica que las tareas programadas corren remotamente y pueden usar conectores, Skills y archivos guardados en la cuenta, pero no pueden vincularse a carpetas locales de la computadora. Para tareas largas sobre el entorno local, Anthropic presenta **Dispatch** como la alternativa: trabaja en segundo plano usando un Project de Cowork, con sus carpetas, instrucciones y memoria. [Tareas programadas](https://support.claude.com/en/articles/13854387-schedule-recurring-tasks-in-claude-cowork), [Dispatch](https://claude.com/docs/cowork/guide/dispatch).

Mi propuesta de secuencia sería:

1. **Delegar y verificar:** del pedido ambiguo al entregable confiable.  
2. **Diseñar un flujo repetible:** Project, instrucciones, Skill y control de calidad.  
3. **Automatizar con criterio:** Schedule, Dispatch, plugins, permisos y gobernanza.  
4. **Laboratorio aplicado:** cada alumno lleva una tarea real y construye su primera versión.

La documentación y los cursos oficiales apuntan exactamente a esa progresión: el curso gratuito *Introduction to Claude Cowork* cubre loop de tarea, plugins/Skills, trabajo con archivos e investigación, y cómo guiar trabajos de varios pasos; el material de Anthropic después profundiza en personalización, automatización y escalamiento organizacional. [Curso oficial](https://anthropic.skilljar.com/introduction-to-claude-cowork), [guía de personalización](https://claude.com/resources/tutorials/customize-claude-cowork), [guía de producto](https://claude.com/blog/the-claude-cowork-product-guide).

Dejaría **subagentes propios y packaging técnico de plugins** como contenido optativo o avanzado. Para alumnos de MiM, el mayor retorno está en aprender a formular, supervisar, verificar y estandarizar una delegación real.

## Usuario

Noo es dispatch realmente ejecutar algo desde un dispositivo ?

## Asistente

Sí, tenés razón. Lo simplifiqué mal.

**Dispatch ejecuta trabajo desde un dispositivo/host**, normalmente Claude Desktop: recibe un resultado amplio, lo divide en tareas y las corre en segundo plano. Si lo iniciás desde el teléfono, el trabajo puede ejecutarse en tu computadora, pero esta debe estar encendida, conectada y con Claude Desktop abierto. [Documentación de Dispatch](https://claude.com/docs/cowork/guide/dispatch), [uso desde cualquier dispositivo](https://support.claude.com/en/articles/13947068-assign-tasks-from-anywhere-in-claude-cowork).

La distinción útil para clase sería:

- **Schedule:** “todos los lunes a las 8, hacé este briefing”. Es una repetición por calendario y corre remotamente; no usa una carpeta local.
- **Dispatch:** “investigá estas 20 empresas y prepará una recomendación”. Es una delegación amplia y de varias tareas, que se ejecuta desde el host/Desktop y puede trabajar con el Project, sus carpetas locales, instrucciones y conectores.
- **Cowork normal:** una tarea puntual que seguís y guiás en la conversación.

Entonces, sí: Dispatch es precisamente el tema adecuado para cubrir después de Cowork, porque completa el salto de “delegar una tarea” a “delegar trabajo mientras yo sigo con otra cosa”.

## Usuario

O Dispatch es subprocess ?

## Asistente

Conceptualmente, sí: **Dispatch es un orquestador que genera tareas hijas**.

No es un “subprocess” del sistema operativo, pero la analogía sirve:

```text
Vos definís un resultado
        ↓
Dispatch (agente principal)
        ↓
divide y asigna tareas hijas
        ↓
cada una corre como sesión de Cowork o Claude Code
        ↓
Dispatch reúne el resultado
```

La diferencia con los **subagentes** es el nivel:

- **Subagentes:** paralelizan partes de una tarea dentro de una sesión de Cowork; Claude los coordina “por debajo”.
- **Dispatch:** es un agente de más alto nivel y persistente: recibe un objetivo amplio, crea y monitorea tareas hijas visibles en la barra lateral, y puede derivarlas a Cowork o Claude Code según corresponda.

Así que para explicarlo en clase usaría: *“Dispatch es el jefe de proyecto: no hace todo él; descompone el trabajo y coordina sesiones de ejecución.”*

## Usuario

Dame un link a la documenencaion sbore el mismo.

## Asistente

[Documentación oficial de Claude Dispatch](https://claude.com/docs/cowork/guide/dispatch)

## Usuario

Lo que encuentro es "Claude can work with your files, browse in Chrome, and use connectors. Dispatch a task or a code session from the mobile app, and Claude will keep working as long as your computer stays awake." que no parece ser lo que estas diciendo.

## Asistente — avance

Tenés razón en cuestionarlo: esa frase describe Dispatch como la forma de enviar una tarea o sesión de código al equipo que actúa como host, no necesariamente como un orquestador de subprocesos. Voy a verificar la página vigente y separar ambos conceptos.

## Asistente

Tenés razón: para explicar **qué es Dispatch al usuario**, tu cita es mucho mejor que mi analogía de “jefe de proyecto”.

La definición correcta y más útil es:

> **Dispatch permite enviar tareas a Claude desde el móvil o Desktop para que se ejecuten en tu computadora, usando los archivos, aplicaciones, conectores y plugins configurados allí.**

Por eso la computadora debe permanecer despierta y Claude Desktop abierto. Es una forma de trabajo remoto sobre tu propio Desktop, no una función de “subprocess” que haya que enseñar como concepto principal. [Documentación de uso desde cualquier dispositivo](https://support.claude.com/en/articles/13947068-assign-tasks-from-anywhere-in-claude-cowork).

La confusión viene de que la documentación técnica agrega que, ante un pedido amplio, Dispatch puede dividirlo en una o más sesiones hijas de Cowork o Claude Code. Eso describe cómo organiza el trabajo internamente, pero no es el framing pedagógico principal. [Documentación técnica de Dispatch](https://claude.com/docs/cowork/guide/dispatch).

Para tu presentación, lo diría así:

> **“Dispatch es la forma de encargar trabajo a tu Claude Desktop desde donde estés. Le mandás una tarea desde el teléfono, Claude trabaja con los recursos de tu computadora y vos volvés a buscar el resultado.”**

Y dejaría la idea de las sesiones hijas sólo como nota avanzada, si alguien pregunta qué ocurre internamente.

## Usuario

No veo que mencionas nada sobre Artifacts. Por que no lo encontraste. No se menciona en los cursos ?

## Asistente — avance

Sí aparece, y debí incluirlo. La búsqueda encontró menciones, pero prioricé los módulos que el curso oficial listaba como núcleo y no seguí la rama de Artifacts. Voy a verificar su documentación específica y qué lugar ocupa en los cursos para corregir la propuesta.

## Asistente

Tenés razón: omití un tema importante. Fue un error de síntesis mío, no de disponibilidad de fuentes.

Sí aparece en la documentación y en los recursos oficiales:

- La guía de personalización de Cowork nombra explícitamente Artifacts como dashboards, trackers y comparadores persistentes que se actualizan con datos de conectores. [Customize Claude Cowork](https://claude.com/resources/tutorials/customize-claude-cowork)
- Anthropic Academy lo incluye como línea de aprendizaje propia (“create, manage, and collaborate on files and other content with Claude”). [Claude for work](https://www.anthropic.com/learn/claude-for-work)
- Existe además documentación específica y reciente sobre **Live Artifacts en Cowork**. [Use live artifacts in Claude Cowork](https://support.claude.com/en/articles/14729249-use-live-artifacts-in-claude-cowork)

No pude confirmar que el curso *Introduction to Claude Cowork* tenga una unidad explícita de Artifacts: su página pública enumera el enfoque general, pero no publica el detalle completo de cada módulo. Así que no afirmaría que sea un módulo central de ese curso sin entrar a él.

Sí lo incorporaría a tu secuencia, incluso antes de Dispatch:

1. **De archivo entregable a vista viva:** qué diferencia hay entre un Excel/PDF/deck que Claude genera y un *Live Artifact*.
2. **Caso de negocio:** crear un dashboard de competidores, un tracker de proyectos o un briefing matinal.
3. **Actualización:** el Artifact queda en la barra lateral, puede consultar datos actuales de conectores y archivos locales al abrirse, y conserva versiones.
4. **Gobernanza:** qué conectores puede usar, qué datos muestra y qué significa compartirlo.

La distinción ancla sería:

> Una **Skill** enseña a Claude a repetir un proceso.  
> Un **Artifact** conserva una interfaz para consultar el resultado de ese proceso.

Ejemplo para clase: una Skill semanal investiga competidores y un Live Artifact muestra, en una sola vista, lanzamientos, cambios de precio y novedades. Al abrirlo de nuevo, se refresca con datos actuales.

Hay un cuidado relevante para enseñar: los Live Artifacts usan los conectores aprobados durante su creación o actualización **sin volver a pedir permiso al abrirse o refrescarse**. Por eso conviene construirlos inicialmente con fuentes de bajo riesgo y privilegios mínimos. [Documentación de seguridad y funcionamiento](https://support.claude.com/en/articles/14729249-use-live-artifacts-in-claude-cowork).

## Usuario

Ok. Si, creo que es importante distincciones entre live artifacts y artifacts. Hay restrucciones clara.

## Asistente

Sí: merece una lámina propia porque son objetos parecidos en apariencia, pero con un modelo de datos, disponibilidad y riesgo distinto.

| | Artifact de Chat | Live Artifact de Cowork |
|---|---|---|
| Qué es | Contenido o app creada dentro de una conversación. | Página HTML interactiva y persistente para un trabajo concreto. |
| Datos | Parte del contexto de la conversación. | Puede refrescar datos de conectores y archivos locales. |
| Dónde vive | Chat y vista de Artifacts. | Sidebar de Cowork, etiquetado como “Cowork”. |
| Dispositivos | Puede compartirse/publicarse según el plan. | Sólo Claude Desktop; es local, no viaja a web o móvil. |
| Compartir | Pro/Max pueden publicar; Team/Enterprise comparten dentro de la organización. | Sólo Team/Enterprise, dentro de la organización; no hay enlace público. |
| Permisos | Dependen de la conversación y las funciones usadas. | Usa los conectores autorizados para crearlo o actualizarlo sin volver a pedir permiso al refrescar. |

La restricción que más vale subrayar es la última: un Live Artifact no es sólo una visualización bonita; puede volver a consultar fuentes conectadas cada vez que se abre. Por eso no conviene conectarlo a herramientas con permisos de escritura o datos sensibles durante un primer ejercicio. [Live Artifacts en Cowork](https://support.claude.com/en/articles/14729249-use-live-artifacts-in-claude-cowork), [publicar y compartir Artifacts](https://support.claude.com/en/articles/9547008-publish-and-share-artifacts).

Yo lo enseñaría con esta frase:

> **El Artifact de Chat es una pieza creada en una conversación; el Live Artifact es una vista persistente que puede mantenerse viva con datos de tu trabajo.**

El caso didáctico ideal es un tracker de competidores de sólo lectura: fuentes web o Drive, cambios de precio, lanzamientos y fechas; luego mostrar refresco, historial de versiones y qué ocurriría si alguien intentara compartirlo.

## Usuario

Proponemos cual seria decks y talk track sobre artifacts

## Asistente — avance

Sí. Para proponer la presentación con una narrativa y un guion hablable, voy a usar la guía de presentaciones y la de edición de prosa del proyecto; no crearé archivos todavía, sólo definiré el deck y el talk track.

## Asistente

Propongo un deck breve, de 35 minutos más 15 de demo o ejercicio. Su función no es enseñar a “hacer una app”, sino que los alumnos entiendan cuándo una respuesta debe transformarse en una interfaz que pueden volver a usar.

**Título del deck:**  
**Artifacts: cuando el resultado deja de ser un chat**

**Idea central:** un Artifact de Chat conserva una pieza de contenido o una herramienta creada en una conversación; un Live Artifact de Cowork mantiene una vista de trabajo que consulta datos actuales dentro de límites definidos.

| # | Lámina | Mensaje visible | Talk track |
|---|---|---|---|
| 1 | Apertura | **¿Qué hacés con una buena respuesta cuando la necesitás otra vez mañana?** | “Hasta ahora, Cowork nos ayudó a delegar trabajo y producir archivos. Pero hay resultados que no queremos volver a buscar dentro de un chat: queremos abrirlos, consultarlos y actualizarlos.” |
| 2 | El problema | Un chat tiene historial. El trabajo recurrente necesita una vista. | Mostrar un ejemplo: una respuesta sobre cinco competidores queda enterrada en el chat; un tracker permite volver a mirar precios, lanzamientos y fuentes. |
| 3 | Qué es un Artifact | **Una pieza de contenido autosuficiente que Claude muestra fuera del hilo de conversación.** | “Puede ser un documento, una visualización, un diagrama, un sitio simple o una herramienta interactiva. Lo importante es que se puede editar, reutilizar, descargar o compartir.” |
| 4 | La distinción central | **Dos tipos, dos comportamientos.** | Comparar Artifact de Chat y Live Artifact de Cowork. Esta es la lámina ancla. |
| 5 | Artifact de Chat | Se crea para editar, reutilizar o compartir una pieza de contenido. | “Acá el caso típico es una calculadora, un canvas, un documento o una mini app. Puede quedar asociado a la conversación; si se publica, aparece en la vista de Artifacts.” |
| 6 | Live Artifact | **Un tablero persistente para mirar el estado actual del trabajo.** | “Cowork crea una página HTML interactiva que queda en su sidebar. Puede ser un tracker, dashboard, comparador o briefing. Al abrirlo, consulta de nuevo las fuentes conectadas y muestra una vista actualizada.” |
| 7 | Caso MiM | Tracker de competidores: precio, lanzamientos, noticias y fuente. | Mostrar el recorrido: fuentes autorizadas → Cowork investiga → construye el tracker → el alumno abre la vista la semana siguiente y refresca. |
| 8 | Los límites importan | Desktop, permisos, compartir y datos. | Explicar las cuatro restricciones sin tecnicismos: vive localmente en Desktop; no aparece en web o móvil; compartir sólo en Team/Enterprise y dentro de la organización; usa conectores autorizados sin pedir aprobación en cada refresh. |
| 9 | No es automatización ciega | El tablero muestra evidencia. La decisión sigue siendo humana. | “El Artifact puede resumir y organizar; ustedes deben abrir la fuente detrás de una afirmación relevante, decidir qué dato importa y actuar.” |
| 10 | Cierre | **Una Skill repite un proceso. Un Live Artifact hace visible su resultado.** | Cerrar conectando el módulo anterior: “Una Skill puede producir el briefing; el Artifact permite consumirlo sin volver al chat. El próximo paso es pensar qué proceso conviene hacer repetible y qué vista conviene mantener viva.” |

La lámina 4 podría verse así:

| | Artifact de Chat | Live Artifact de Cowork |
|---|---|---|
| Uso principal | Crear y trabajar una pieza de contenido | Consultar una vista de trabajo persistente |
| Datos | Contexto de la conversación o app | Conectores aprobados y archivos locales |
| Actualización | Se edita en el chat | Puede refrescar datos al abrirse |
| Disponibilidad | Claude web y Desktop | Sólo Claude Desktop |
| Compartir | Publicación o uso interno, según plan | Sólo Team/Enterprise dentro de la organización |

Para la demo, usaría este prompt:

> “Creá un Live Artifact de sólo lectura para seguir cinco competidores del sector [X]. Mostrá empresa, lanzamiento reciente, cambio de precio, fecha, fuente y nivel de relevancia. Usá únicamente estas fuentes autorizadas: [fuentes]. No ejecutes acciones ni escribas en ninguna aplicación.”

El momento pedagógico más importante viene después de crearlo: abrirlo y preguntar:

- ¿Qué fuente alimenta cada dato?
- ¿Qué ocurriría si uno de los conectores tuviera permiso de escritura?
- ¿Este tablero se puede abrir desde el celular?
- ¿Quién podría compartirlo y con quién?

No pondría Dispatch en este deck. Dejaría Artifacts como módulo autónomo, porque responde una pregunta distinta: **cómo convertir un resultado en una vista viva y reutilizable**.

La base documental para el deck sería [Artifacts generales](https://support.claude.com/en/articles/9487310-what-are-artifacts-and-how-do-i-use-them), [Live Artifacts en Cowork](https://support.claude.com/en/articles/14729249-use-live-artifacts-in-claude-cowork) y [reglas de publicación y compartición](https://support.claude.com/en/articles/9547008-publish-and-share-artifacts).

## Usuario

Listo, este es un tema. Ahora vamos a "**Delegar y verificar:** del pedido ambiguo al entregable confiable."

## Asistente — avance

Perfecto. Este módulo tiene que convertir la idea de “delegar” en una práctica de management: definir el trabajo, revisar el plan, verificar la evidencia y asumir la decisión. Voy a basarlo en la guía de presentaciones y contrastarlo con la orientación oficial sobre trabajo y seguridad en Cowork.

## Asistente

Este debería ser un deck de 35 minutos, más 20 minutos de trabajo en equipos. Continúa naturalmente lo ya visto: Cowork puede ejecutar, pero el alumno debe aprender a formular un encargo y asumir la validación del resultado.

**Título:**  
**Delegar y verificar: del pedido ambiguo al entregable confiable**

**Resultado de aprendizaje:** al terminar, cada alumno puede redactar un brief delegable, revisar el plan de Cowork y verificar las afirmaciones que sostienen una decisión.

| # | Lámina | Contenido visible | Talk track |
|---|---|---|---|
| 1 | **Una delegación no empieza con un prompt** | “Analizá estos archivos y recomendame qué hacer.” | “Esto parece un pedido razonable. Pero no define una decisión, ni evidencia, ni formato, ni quién decide. Si Cowork entrega algo flojo, el problema suele estar acá.” |
| 2 | **Una tarea ambigua produce trabajo difícil de evaluar** | Pedido ambiguo → resultados posibles: resumen, presentación, tabla, recomendación. | “El agente puede trabajar mucho y entregar algo inútil porque nadie fijó qué significa ‘bien’. Antes de delegar, necesitamos acordar el trabajo.” |
| 3 | **El brief define el trabajo antes de que el agente lo ejecute** | Cuatro campos: **resultado**, **material**, **criterio**, **límites**. | “Resultado: qué debe entregar. Material: qué fuentes puede usar. Criterio: cómo reconocemos un buen resultado. Límites: qué no debe hacer y cuándo tiene que consultar.” |
| 4 | **El mismo pedido, convertido en una delegación** | Antes: “Analizá los competidores.” Después: brief completo. | Mostrar una versión concreta: “Compará cinco competidores usando estas fuentes; entregá una tabla con precio, lanzamiento y fuente; marcá incertidumbres; no recomiendes una inversión; consultame antes de usar una fuente externa.” |
| 5 | **Revisá el plan antes de esperar el archivo final** | Objetivo → plan → ejecución → entrega. Marcar el punto de revisión en el plan. | “Cowork puede descomponer la tarea y mostrar el plan. En ese momento revisás alcance, fuentes, pasos y acciones. Corregir el rumbo al comienzo cuesta poco; corregir un deck terminado cuesta más.” |
| 6 | **Guiar no es microgestionar** | Tres intervenciones útiles: corregir alcance, cambiar evidencia, pedir un control. | “No hace falta indicar cada clic. Intervenís cuando aparece una suposición incorrecta, falta una fuente clave o cambia el criterio de decisión.” |
| 7 | **Verificar tiene cuatro capas** | 1. Entregable. 2. Evidencia. 3. Supuestos. 4. Consecuencia. | “Primero, ¿entregó lo pedido? Segundo, ¿la afirmación importante tiene fuente? Tercero, ¿qué asumió o dejó afuera? Cuarto, ¿qué ocurre si esto está equivocado? La intensidad de la revisión depende de esa última pregunta.” |
| 8 | **Una cita no reemplaza tu criterio** | “Citación” ≠ “afirmación correcta”. | “La fuente puede ser vieja, irrelevante, secundaria o estar mal interpretada. Antes de usar una recomendación, abrís la fuente de la afirmación que sostiene tu decisión.” |
| 9 | **La firma sigue siendo tuya** | Cowork prepara → vos verificás → vos decidís → Cowork ejecuta acciones aprobadas. | “El agente puede investigar, ordenar, redactar y proponer. Ustedes deciden qué creer, qué firmar y qué acción permitir.” |
| 10 | **Práctica: una recomendación que resista preguntas** | Consigna del ejercicio. | “Tomen un pedido ambiguo. Conviértanlo en brief. Después reciban un informe con una cifra dudosa y definan qué tres afirmaciones verificarían antes de recomendar una acción.” |

La lámina 4 debería usar un ejemplo de gestión cercano:

```text
Pedido ambiguo
“Analizá nuestros competidores y recomendame una estrategia.”

Delegación
Objetivo: preparar una recomendación para la reunión comercial del lunes.
Entregable: tabla comparativa + memo de una página.
Fuentes: estos cinco sitios y los archivos de la carpeta /mercado.
Criterio: cada afirmación relevante debe indicar su fuente y fecha.
Límites: no contactar competidores; consultarme antes de usar otras fuentes.
Cierre: listar incertidumbres y tres puntos que yo deba verificar.
```

El ejercicio puede usar un caso único durante toda la sesión:

> “La empresa evalúa lanzar un producto en un mercado nuevo. Cowork recibe una carpeta con informes, una planilla de precios y tres enlaces. Uno de los informes tiene datos de 2024, una fuente contradice a otra y falta información sobre un competidor.”

Cada grupo debe:

1. Reescribir el pedido como brief.
2. Señalar qué revisarían en el plan de Cowork.
3. Elegir tres afirmaciones que no aceptarían sin abrir la fuente.
4. Decidir qué acción, si alguna, permitirían al agente al final.

El mensaje de cierre para decir, no necesariamente proyectar:

> “Delegar no es transferir responsabilidad. Es definir el trabajo para que el agente ejecute bien y reservar el juicio para la decisión.”

La estructura sigue la orientación actual de Anthropic: Cowork trabaja con un ciclo de entender, planificar, ejecutar, verificar y entregar; la persona debe definir qué significa éxito y revisar las fuentes antes de actuar. [Ciclo de trabajo de Cowork](https://claude.com/resources/tutorials/choosing-between-claude-cowork-or-chat), [verificar antes de firmar](https://claude.com/resources/tutorials/using-claude-cowork-for-legal-question-briefing), [currículum de discernimiento](https://claude.com/resources/tutorials/getting-good-at-claude-a-research-backed-curriculum).

## Usuario

Ok,. No veo valor en esto. Vamos a por ejemplo Memory.

## Asistente — avance

De acuerdo; no lo forzaría como módulo independiente. **Memory** sí puede dar una clase más concreta porque responde una pregunta operativa: qué debería conservar Claude, dónde vive y cómo se controla. Voy a contrastarlo con la documentación actual y con lo que ya aparece en el deck de Cowork.

## Asistente — avance

Para darle forma de módulo y no de listado de producto, voy a usar la guía de presentaciones para definir la narrativa y el talk track. La documentación revela además una distinción importante: memoria de Chat, memoria de Project y el historial de archivos/instrucciones no son lo mismo.

## Asistente

**Memory** tiene valor si el módulo se llama **“Arquitectura de contexto: qué debe recordar Claude y dónde debe vivir”**. Una clase sobre el botón de Memory quedaría corta; una clase sobre evitar que el conocimiento del equipo quede atrapado en chats sí aporta.

Además, detecté una corrección necesaria en el deck actual: la lámina de Projects dice que los chats no comparten contexto. Hoy conviene decir algo más preciso:

> Los chats no comparten su transcripción completa, pero un Project puede aportar instrucciones, archivos y memoria de contexto entre tareas del mismo Project.

La documentación de Cowork dice que esa memoria está delimitada por Project; la de Memory de Chat advierte que el despliegue cambia según cuenta y superficie. Lo enseñaría como comportamiento visible en la app, con demo, sin prometer una arquitectura interna fija. [Projects en Cowork](https://support.claude.com/en/articles/14116274-organize-your-tasks-with-projects-in-claude-cowork), [Memory y búsqueda de chats](https://support.claude.com/en/articles/11817273-use-claude-s-chat-search-and-memory-to-build-on-previous-context).

## Deck propuesto

**Título:**  
**Memoria: el contexto que Claude conserva y el que vos tenés que documentar**

**Idea central:** Claude puede retener contexto, pero el equipo debe decidir qué queda en archivos, qué se fija como instrucción y qué puede quedar como memoria.

| # | Lámina | Mensaje visible | Talk track |
|---|---|---|---|
| 1 | **El chat no debería ser la memoria de tu equipo** | “¿Dónde quedó la regla que definimos hace dos semanas?” | “Si la respuesta es ‘en algún chat’, la regla no forma parte del proceso. Cowork ayuda a conservar contexto, pero no reemplaza una forma de trabajo ordenada.” |
| 2 | **Cuatro lugares para conservar contexto** | Archivos · Instrucciones · Memory · Historial de tareas. | “No son sinónimos. Cada uno resuelve un problema distinto. El error es usar Memory como reemplazo de los demás.” |
| 3 | **Cada tipo de información tiene un lugar** | Tabla: hecho verificable → archivo; regla estable → Instructions; preferencia o continuidad → Memory; trazabilidad → historial y entregables. | “Los datos que alguien debe poder auditar van a un archivo. Las reglas que no se negocian van a Instrucciones. La memoria sirve para continuidad, por ejemplo preferencias de formato o contexto de una tarea que sigue.” |
| 4 | **Un Project delimita qué contexto puede reaparecer** | Un Project = carpetas + instrucciones + links + memoria. | “La memoria del Project debe ayudar al trabajo de ese Project. No queremos que una preferencia de análisis de mercado aparezca en un trabajo de finanzas.” |
| 5 | **Memory ayuda; los archivos siguen siendo la fuente de verdad** | “Recordar que preferís un memo ejecutivo” vs. “Conservar la política comercial aprobada”. | “La primera puede quedar en memoria. La segunda debe vivir en un documento versionado. Si una omisión genera riesgo, conflicto o trabajo repetido, hay que documentarla.” |
| 6 | **Promover conocimiento evita depender de una memoria implícita** | Memoria útil → Instrucción del Project → archivo `.md` → Skill, si el proceso se repite. | “Cuando una preferencia se vuelve una regla, la promovemos. Cuando la regla describe una tarea recurrente, la convertimos en Skill.” |
| 7 | **La memoria necesita control humano** | Ver, editar, borrar; revisar alcance; no tratarla como caja fuerte. | “Claude permite revisar y modificar lo que recuerda. Datos como contraseñas, salud y finanzas se excluyen de Memory, pero igual no corresponde usarla como repositorio de información sensible.” |
| 8 | **Ejercicio: diseñar la memoria de Faro** | Cuatro tarjetas: “guardar en archivo / Instrucciones / Memory / no guardar”. | “Les doy ocho piezas de contexto de Faro. En grupos, decidan dónde debería vivir cada una y expliquen qué error evita esa elección.” |
| 9 | **Un buen Project reduce explicaciones sin perder control** | Archivos para evidencia. Instrucciones para reglas. Memory para continuidad. | “El objetivo no es que Claude recuerde más. Es que el equipo tenga que repetir menos, sin perder claridad ni trazabilidad.” |

El ejercicio de Faro puede usar estas tarjetas:

- “Los informes se escriben en español y llevan resumen ejecutivo.” → **Instructions**
- “El pricing de Atlas se actualizó el 12 de agosto.” → **archivo fuente**
- “Para Paulo, una tabla comparativa es más útil que cinco páginas de prosa.” → **Memory**
- “No usar datos de clientes ni información bajo NDA.” → **Instructions**
- “El archivo `competidores-2026.md` es la fuente aprobada para el análisis.” → **archivo / Instructions que lo prioriza**
- “Contraseña del CRM.” → **no guardar**
- “La revisión de julio quedó inconclusa por falta de datos de Brasil.” → **Memory al inicio; archivo si afecta decisiones posteriores**
- “El informe semanal sigue estos siete pasos.” → **Skill**

La demo ideal dura cinco minutos:

1. Crear un Project de Faro.  
2. Agregar una Instruction y un archivo `.md`.  
3. Pedir una tarea y corregir una preferencia.  
4. Mostrar qué puede recordar el Project.  
5. Abrir una nueva tarea y comprobar qué contexto reaparece.  
6. Convertir una preferencia importante en una Instruction o archivo.

El punto que hace interesante el tema es ese último paso: **Memory reduce fricción; la documentación crea un proceso confiable.**

## Usuario

Eso esta bien pero memory como concepto es importante en el contexto de explicar los 3 tipos de memoria. Intrucciones/Memory y Project. Me falta algo ?

## Asistente

Sí. La corrección conceptual es que **Project no es un tercer tipo de memoria**: es el contenedor que delimita el contexto.

La estructura más clara para clase sería:

```text
PROJECT: el espacio de trabajo de un tema
│
├── INSTRUCCIONES: reglas explícitas sobre cómo trabajar
├── MEMORY: contexto aprendido que puede reaparecer
└── ARCHIVOS / LINKS: evidencia y fuente de verdad
```

Entonces los tres conceptos a enseñar son:

| Concepto | Pregunta que responde | Ejemplo |
|---|---|---|
| **Instructions** | “¿Cómo tiene que trabajar Claude?” | “Escribí en español, usá este formato y citá las fuentes.” |
| **Memory** | “¿Qué aprendió Claude de este trabajo?” | “El equipo prefiere una tabla ejecutiva y usa USD.” |
| **Project** | “¿En qué espacio vale ese contexto?” | “Todo esto corresponde al análisis de Faro, no a Finanzas.” |

Te falta nombrar explícitamente un cuarto elemento: **los archivos como fuente de verdad**. Sin eso, podría quedar la idea equivocada de que Memory conserva conocimiento institucional de forma confiable.

La frase ancla sería:

> **Las Instrucciones dicen cómo trabajar. Memory conserva continuidad. El Project define dónde vale ese contexto. Los archivos guardan lo que hay que poder comprobar.**

También conviene diferenciar **historial de chat** de Memory:

- El historial conserva la conversación.
- Memory condensa o recupera contexto útil.
- Ninguno debería reemplazar un archivo o una Instruction cuando una regla importa.

Eso te da una clase más fuerte: no “cómo configurar Memory”, sino **cómo diseñar el contexto de un agente para que aprenda sin convertirse en una caja negra**.

## Usuario

Ok. Creo que todo el talk track seria Conocimiento y Memoria. Cual seria el talk track ...

## Asistente

Sí. Lo plantearía como una charla de **25–30 minutos**, no como un módulo entero de una hora.

**Título:**  
**Conocimiento y memoria: cómo hacer que un agente entienda el trabajo**

**Tesis:** Claude no trabaja mejor porque “recuerda más”, sino porque el equipo pone cada cosa en el lugar correcto: conocimiento verificable en archivos, reglas en Instructions, continuidad en Memory y límites claros en un Project.

| Lámina | Mensaje | Talk track |
|---|---|---|
| 1. Apertura | **Un agente no empieza de cero: empieza con el contexto que le damos.** | “En la clase anterior vimos que Cowork trabaja sobre una carpeta. Hoy vamos un paso más allá: qué debería encontrar allí, qué puede recordar entre tareas y qué no conviene dejar librado a su memoria.” |
| 2. El problema | **El conocimiento del equipo suele quedar repartido entre archivos, chats y personas.** | “Una regla puede estar en un mail, una decisión en una reunión y una plantilla en la carpeta de alguien. Cuando el contexto está disperso, cada nueva tarea empieza con explicaciones repetidas y resultados inconsistentes.” |
| 3. Conocimiento | **Lo que debe poder comprobarse vive en archivos.** | “Políticas, datos, definiciones, fuentes, plantillas y decisiones aprobadas deben estar en archivos claros, idealmente en `.md` cuando el objetivo es que un agente los lea y use. El archivo es la fuente de verdad: otra persona puede revisarlo, corregirlo y reutilizarlo.” |
| 4. Instructions | **Las Instructions fijan cómo trabaja Claude.** | “No guardan la evidencia; fijan las reglas. Idioma, formato, fuentes prioritarias, tono, qué nunca debe hacer y cuándo tiene que consultar. Son el contrato de trabajo del Project.” |
| 5. Memory | **Memory conserva continuidad, no reemplaza documentación.** | “Memory puede retener preferencias y contexto de tareas anteriores: cómo trabaja el equipo, qué formato prefiere o qué tema quedó abierto. Reduce explicaciones repetidas. Pero si una regla importa para una decisión, no alcanza con que Claude la recuerde: hay que escribirla.” |
| 6. Project | **El Project define dónde vale ese contexto.** | “El Project agrupa una carpeta, Instructions, links y Memory para un tema concreto. Así, el contexto de Faro no se mezcla con el de Finanzas o Marketing. El Project no es memoria: es el límite dentro del cual ese contexto tiene sentido.” |
| 7. La arquitectura | **Cada cosa tiene un lugar.** | Mostrar el diagrama: `Project → archivos / Instructions / Memory`. “Archivos responden qué sabemos. Instructions responden cómo trabajamos. Memory responde qué continuidad conviene conservar. El Project delimita el conjunto.” |
| 8. Promover conocimiento | **Cuando algo deja de ser una preferencia, hay que sacarlo de Memory.** | “Si Claude aprendió que el informe debe llevar una tabla ejecutiva, puede quedar en Memory. Si esa tabla pasa a ser obligatoria para todos los informes, la promovemos a Instructions. Si además el proceso se repite, lo convertimos en una Skill.” |
| 9. Caso Faro | **Faro mejora cuando su contexto deja de depender de una conversación.** | “La fuente de precios queda en `competidores.md`. La regla de formato queda en Instructions. La preferencia de priorizar empresas argentinas puede quedar en Memory. El flujo para construir el informe semanal se vuelve una Skill.” |
| 10. Cierre | **Menos reexplicación. Más contexto auditable.** | “El objetivo no es que Claude guarde todo. El objetivo es que el equipo decida qué debe recordar, qué debe documentar y qué debe volver a verificar.” |

La lámina 7 es la pieza visual central:

```text
                    PROJECT: Faro

       ┌──────────────┼───────────────┐
       │              │               │
   ARCHIVOS      INSTRUCTIONS       MEMORY
   qué sabemos   cómo trabajar      continuidad
   evidencia     reglas             preferencias
   fuentes       límites            contexto reciente
```

La demo debería seguir exactamente esa arquitectura:

1. Abrís el Project de Faro.
2. Mostrás un archivo `competidores.md`.
3. Mostrás una Instruction: “entregar un resumen ejecutivo y citar fuente + fecha”.
4. Pedís una tarea y agregás una preferencia de trabajo.
5. Abrís una nueva tarea del mismo Project.
6. Preguntás: “¿Qué debería seguir presente? ¿Qué no confiaríamos a Memory?”

El cierre deja servido el siguiente tema:

> “Ya sabemos cómo organizar el contexto. La próxima pregunta es cómo convertimos una forma de trabajar repetida en una Skill.”

## Usuario

Ok. Eso me parece perfecto. Vamos ahora a otro tema que seria Quick Intro a Clade Code. El grupo no es tecnico pero introducir muy por arriba como se usa y la conctruccion de lo que shace con el mismo

## Asistente — avance

Bien. Para un público no técnico, Claude Code no debería presentarse como “aprender a programar”, sino como el mismo patrón de delegación aplicado a software: contexto, plan, archivos, herramientas y verificación. Voy a contrastarlo con la documentación oficial para proponer un bloque breve y sin jerga.

## Asistente

Para este grupo haría un bloque de **15–20 minutos**, con una demo corta. El objetivo no es que aprendan a programar ni a usar una terminal; es que entiendan qué cambia cuando el agente trabaja sobre software.

**Título:**  
**Claude Code: delegar la construcción de software**

**Tesis:** Cowork trabaja sobre conocimiento, documentos y herramientas de oficina. Claude Code aplica el mismo patrón sobre un producto digital: lee el proyecto, propone cambios, edita archivos, prueba el resultado y deja cambios revisables.

| Lámina | Mensaje visible | Talk track |
|---|---|---|
| 1. Mismo patrón, otro material | **Cowork trabaja sobre el trabajo. Claude Code trabaja sobre el software.** | “No cambia la lógica que ya vimos. Definís un resultado, el agente entiende el contexto, ejecuta pasos y vos revisás. La diferencia es el material: en vez de informes y planillas, hay archivos que componen una aplicación.” |
| 2. Qué es una codebase | **Una aplicación es una carpeta de instrucciones, pantallas y reglas.** | “Un sitio web, una app o una automatización no es una caja negra. Está construido con archivos: los que definen qué ve el usuario, qué datos usa y qué ocurre cuando alguien hace clic.” |
| 3. Qué hace Claude Code | Lee → entiende → propone un plan → modifica archivos → prueba → muestra cambios. | “No le das una instrucción de programación. Le describís un resultado: ‘agregá una pantalla para comparar competidores’. Claude busca dónde tocar, propone el camino, hace los cambios y verifica que la aplicación funcione.” |
| 4. Qué tiene que decir un manager | Usuario · problema · comportamiento esperado · criterio de aceptación. | “No necesitan decirle qué archivo editar. Sí necesitan explicar para quién es la herramienta, qué problema resuelve, qué debería poder hacer la persona y cómo sabremos que quedó bien.” |
| 5. El control principal es el plan | **Plan Mode: Claude puede investigar y proponer sin modificar nada.** | “Para un cambio importante, primero le pedimos que lea el proyecto y proponga un plan. Recién después de entender alcance, riesgos y pantallas afectadas autorizamos los cambios.” |
| 6. El resultado se puede revisar | **Cada cambio deja una diferencia visible.** | “Claude Code muestra qué líneas cambió. Los programadores revisan el detalle; un manager puede revisar el comportamiento: qué nueva pantalla aparece, qué flujo cambia y qué pruebas corrió.” |
| 7. Demo: construir una herramienta mínima | Brief → prototipo → revisión → versión funcional. | “Vamos a pedir una herramienta simple: un tracker de competidores que permita cargar empresa, precio, fecha y fuente. No mostramos código salvo una línea. Mostramos el brief, el plan, la pantalla final y los cambios.” |
| 8. El límite | **Claude Code construye; el dueño del producto decide qué construir y qué publicar.** | “Que el agente pueda editar una app no habilita a publicar cambios sin control. La decisión de producto, seguridad, datos y lanzamiento sigue siendo humana.” |

El brief de demo podría ser:

> “Creá una herramienta web simple para el equipo de Faro. Debe permitir cargar cinco competidores con nombre, precio, fecha de actualización y fuente. Mostrá una tabla ordenable y marcá los datos con más de 30 días. No uses datos externos ni publiques nada. Antes de editar, proponé un plan. Al final, explicá cómo probar la herramienta.”

La demo sigue este orden:

1. Mostrar la carpeta del proyecto, sin explicar código.
2. Pegar el brief.
3. Elegir **Plan Mode**.
4. Revisar el plan como si fuera una propuesta de un proveedor.
5. Aprobar.
6. Mostrar la pantalla que construyó.
7. Mostrar que existe una lista de cambios y una forma de revertirlos.
8. Pedir una mejora simple: “destacá las fuentes faltantes”.

No incluiría terminal, Git, dependencias, comandos, APIs ni arquitectura. Esos temas hacen que una introducción para managers parezca un curso de ingeniería.

La frase de cierre sería:

> “Con Cowork delegamos trabajo de conocimiento. Con Claude Code podemos delegar parte de la construcción de las herramientas que ese trabajo necesita.”

Claude Code puede trabajar desde Desktop, web, IDE o terminal; para esta clase conviene mostrar la interfaz Desktop o web. Su documentación confirma el flujo de leer el proyecto, proponer cambios, editar, ejecutar comandos y revisar cambios; también recomienda Plan Mode para explorar antes de modificar. [Claude Code overview](https://code.claude.com/docs/en/overview), [Plan Mode y permisos](https://code.claude.com/docs/en/permission-modes), [guía Desktop](https://code.claude.com/docs/en/desktop).

## Usuario

Exporta todo este chat en  un zip.

## Asistente — avance

Voy a buscar la capacidad de exportar o leer el historial de esta tarea y crear un ZIP con la conversación completa, sin incluir archivos ajenos.


`````

