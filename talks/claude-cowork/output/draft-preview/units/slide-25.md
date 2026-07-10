## Plugins en una cuenta Team: ciclo de vida

- **Quién lo maneja.** En cuentas **Team / Enterprise**, los **Owners** gestionan los plugins de la organización desde **Organization settings → Plugins**. El resto de los miembros los reciben listos.
- **El ciclo de vida, de punta a punta:**

```ascii
+-----------------+     +------------------------+     +----------------------+
| OWNER crea un   | --> | agrega plugins:        | --> | fija preferencia de  |
| marketplace     |     | · subir ZIP            |     | instalacion por      |
| privado (org)   |     | · sync repo GitHub     |     | plugin (opcional /   |
|                 |     |   (auto-actualiza)     |     | auto-install / prov.)|
+-----------------+     +------------------------+     +----------------------+
                                                                  |
                                                                  v
+---------------------------+     +-----------------------------------------+
| MIEMBROS instalan/        | <-- | se DISTRIBUYE a los miembros            |
| habilitan desde el        |     | (aparece en chat Y en Cowork)          |
| directorio de la org      |     |                                         |
| (updates se sincronizan)  |     |                                         |
+---------------------------+     +-----------------------------------------+
```

- **Qué se puede hacer.**
  - El Owner crea un **marketplace privado** de la organización y agrega plugins de dos formas: **subir un ZIP**, o **sincronizar desde un repo de GitHub** (privado) — esta segunda vía **auto-actualiza** cuando cambia el repo.
  - Por cada plugin se fija una **preferencia de instalación**: opcional (el miembro decide), **auto-install** o provisionado por usuario.
  - Los plugins distribuidos aparecen en **chat y en Cowork** para los miembros; cada uno **instala/habilita** desde el directorio de la org, y las **actualizaciones se sincronizan** solas.

### Notes

Slide de cierre del bloque avanzado, orientada a quien algún día administre una cuenta de equipo. La idea: los Plugins no son solo para instalar de a uno; en una cuenta Team, un Owner puede armar un marketplace privado de la organización y repartir workflows a todo el equipo. Recorrer el ciclo con el diagrama: el Owner crea el marketplace y sube plugins (ZIP o, mejor, sincronizando un repo de GitHub que auto-actualiza), fija cómo se instala cada uno (opcional / auto-install / provisionado), y desde ahí se distribuye —aparece tanto en chat como en Cowork— y los miembros lo habilitan desde su directorio, con las actualizaciones sincronizadas. Mantenerlo alto nivel: es el "para cuando esto escala a un equipo". Tiempo objetivo: ~4 min.
