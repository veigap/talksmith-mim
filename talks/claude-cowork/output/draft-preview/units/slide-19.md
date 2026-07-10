## Schedule: que Cowork trabaje solo

- **Para qué sirve.** Todo lo anterior es reactivo (vos pedís, Claude hace). Schedule hace a Cowork **proactivo**: describís una tarea una vez, elegís una cadencia, y Claude la corre solo.
- **Cómo funciona.**
  - Describís la tarea una vez; Claude guarda el prompt como las instrucciones de la tarea.
  - Elegís cadencia: por hora · diaria · semanal · días de semana · o **a demanda** ("Run now").
  - Cada corrida abre su **propia sesión fresca de Cowork** y avisa al terminar.
  - Tiene los **mismos poderes** que una tarea normal: connectors, skills, plugins instalados.
  - Vive en la pestaña **Scheduled** de la barra lateral.
- **⚠️ LA trampa — corre LOCAL, no en la nube.** Las tareas programadas de Cowork corren **en tu computadora**, no en servidores de Anthropic. Solo se disparan **con la máquina encendida y la app de Claude Desktop abierta**. Si estaba dormida/cerrada a la hora prevista, la corrida se **saltea** — y se ejecuta automáticamente apenas la máquina despierta o reabrís la app (con aviso de "esto se saltó"). No esperes que tu laptop apagada genere el reporte del lunes.
  - *(Aparte, fuera de alcance:)* existen agentes programados **alojados en la nube**, pero son una funcionalidad separada — no es lo que hace el Schedule de Cowork.

![Pestaña Scheduled en Cowork](images/schedule.png)

- **Ejemplo (Atlas).** Cada lunes 8:00: `buscar-accion` → `reporte-semanal` → dejar el reporte como borrador en Gmail, listo antes de la reunión de las 9:00. Tip de demo: no esperar al lunes, usar "Run on demand".

### Notes

Acá Cowork pasa de herramienta a empleado: describís el trabajo una vez y corre solo. Es el momento en que Atlas "trabaja mientras vos dormís" — pero con un asterisco. El punto crítico — y un error clásico — es que el Schedule de Cowork corre LOCAL, en tu máquina, no en la nube de Anthropic: solo se dispara con la computadora despierta y la app abierta; si estaba dormida/cerrada, se saltea y corre apenas volvés (con aviso). Dejarlo bien claro para que nadie espere que su laptop apagada genere el reporte del lunes. (Si alguien pregunta por corridas en la nube: sí existen agentes programados hosteados, pero son otra cosa, fuera del alcance de esta charla.) Para la demo, usar "Run on demand" en lugar de esperar la cadencia real. Tiempo objetivo: ~10 min.
