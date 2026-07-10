## Subagentes: delegar sub-tareas en paralelo

- **Concepto.** Un Subagente es un asistente aislado, con su propio contexto, instrucciones y acceso a herramientas, al que el agente principal le delega un trabajo y del que recibe **un resumen** (no la transcripción completa).
- **Skill vs Subagente (la regla de una línea).** Chico, y debe quedar frente a vos → **Skill** (corre *dentro* de tu conversación). Grande o ruidoso, y debe correr en un proceso aparte → **Subagente** (corre *al lado*, en su propio contexto).
- **En Cowork.** Los Subagentes se coordinan "por debajo" (under the hood): el agente principal los lanza cuando le conviene, y pueden correr **varios en paralelo**.
- **Cómo se agrega un subagente.** Se define igual que una Skill — una **descripción de cuándo usarlo** + sus **instrucciones**. Dos caminos: **pedile a Claude que lo arme** (escribe el archivo del agente, como con las Skills, y lo gestionás en el directorio **Customize**), o viene **empaquetado dentro de un Plugin**. No hace falta tocar archivos a mano.

```ascii
                +------------------+
                | agente principal |
                +------------------+
                  /      |       \
                 v       v        v
          +--------+ +--------+ +--------+
          | sub A  | | sub B  | | sub C  |
          |contexto| |contexto| |contexto|
          |propio  | |propio  | |propio  |
          +--------+ +--------+ +--------+
                 \       |       /
                  v      v      v
                +------------------+
                | resumen combinado|
                +------------------+
```

### Notes

Nivel avanzado — presentarlo como "para cuando crezcas". La distinción mental útil: si la sub-tarea es chica y querés verla, es una Skill; si es grande o ruidosa y querés que corra aparte sin ensuciar tu conversación, es un Subagente. El ejemplo del deck (8 propuestas de proveedores revisadas en paralelo por tres especialistas → tabla combinada) ilustra el fan-out. Cómo se agrega: explicarlo en paralelo a las Skills — un subagente se define con una descripción (cuándo usarlo) + instrucciones; le pedís a Claude que lo arme (igual que una Skill, se gestiona en Customize) o viene dentro de un Plugin. Mantenerlo alto nivel: no entrar en rutas de archivos ni internals de persistencia. Tiempo objetivo: ~7 min.
