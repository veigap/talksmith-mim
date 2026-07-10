## Artifacts y Live Artifacts: del resultado a algo compartible

- **Qué es un Artifact.** Una salida viva y ejecutable que se renderiza en un panel lateral: componentes React, páginas HTML, gráficos SVG, diagramas, tablas, documentos descargables.
- **Distinción live vs no-live (breve).**
  - **Artifact estándar** (todos los planes): salida de un solo archivo, estática — lo que generás es lo que queda.
  - **Live Artifact** (Cowork, planes pagos): una **página HTML interactiva y persistente** que vive en la pestaña **"Live artifacts"** de Cowork. **Se actualiza con datos actuales** de tus apps conectadas cada vez que la abrís, y **guarda historial de versiones**.
- **Cómo se crea.** Dos formas: (1) **desde una tarea de Cowork** (le pedís que el resultado sea un Live Artifact), o (2) desde la pestaña **Live artifacts → New artifact → Chat with Claude**.
- **Estado actual del compartir — leer con cuidado.** Los Live Artifacts **todavía NO son compartibles**: en el lanzamiento son **para tu propio uso**; compartir está en el roadmap. Además son **locales, no en la nube**: viven en tu computadora y no te siguen entre dispositivos. Y **usan tus connectors sin volver a pedirte permiso** — solo los que aprobaste al crear/actualizar el artifact.
- **Ejemplo (Atlas).** El tablero `pulso-semanal-FECHA`: un Live Artifact nuevo por semana (queda un historial de versiones), con tarjetas por empresa, tabla resumen y un chip "LIVE", refrescado con los datos de la semana. Diseño basado en el boceto del jefe:

![Boceto del tablero "Pulso semanal de mercado" (wireframe del jefe)](research/corpus/mision%20-%20auto.zip/images/mockup-tablero.png)

### Notes

Cerramos el círculo de la misión: el jefe quería el reporte de dos formas — el email (que ya resolvimos con Gmail + Schedule) y una página siempre actualizada. El Live Artifact es esa página. Explicar la distinción clave: un Artifact estándar es estático; un Live Artifact persiste en la pestaña Live artifacts, se refresca con datos actuales al abrirlo y guarda versiones. Ser honesto con el estado actual del compartir, porque acá había una confusión que corregimos: hoy los Live Artifacts NO son compartibles (es del roadmap, no de hoy), son locales —no en la nube, no te siguen entre dispositivos— y usan los connectors que aprobaste sin volver a preguntar. (Nota: versiones previas de este material mencionaban un "ShareDuo" con URL pública — eso NO es una capacidad de Cowork; quitado.) Mostrar el boceto del tablero — el "napkin sketch" del jefe — como el spec de diseño que el artifact reproduce. Tiempo objetivo: ~10 min.
