# Feedback backlog

## Tagging vocabulary

Reuse existing tags before inventing new ones. In use: restructure, add-slide, add-visual, slide-content, sources, roadmap, positioning, compact, accuracy.

## Entries

<!-- Editor appends entries below this line. -->
- talk: claude-cowork
  date: 2026-07-08
  location: Whole draft (Agenda + all Sections)
  origin: presenter-chat
  feedback: "Reestructura mayor: aprovechar que los alumnos ya usan IAs en modo chat para introducir extensiones ANTES de Cowork. Nuevo arco: (1) el chat y sus limites (responde de memoria de entrenamiento); (2) Conectores como concepto transversal — chat solo vs con conectores, busqueda web como primer conector, directorio oficial + no oficiales + mencion de custom, ejemplos mail/calendar, capacidad ejecutiva (mandar mails, tickets, mensajes, agendar); (3) tareas programadas desde el chat (ej. resumidor de mails); (4) Cowork — mas que 'Claude en tu computadora', cambia por completo la forma de trabajar — con intro/Instrucciones/Projects/Live Artifacts adentro (A1, B1), slide corta de Schedule (C2), y archivos .md expandido (que es, como se lee, trabajar en .md y exportar al final); (5) Skills se muda al final junto a Subagentes y Plugins."
  resolution: Draft reestructurado de 6+Conclusions a 5+Conclusions secciones con el arco chat-primero. 6 slides nuevas (1.1 limites del chat; 2.1 chat solo vs conectores; 2.2 busqueda web / memoria vs info viva; 2.5 conectores que actuan; 3.1 tareas programadas desde el chat; 4.10 trabaja en .md exporta al final). Intro trio + Instrucciones + Projects + selector + .md + Schedule corto + Live Artifacts consolidados en la seccion 4 (Cowork); Skills/anatomia SKILL.md movidas a la seccion 5 con Subagentes y Plugins. Roadmap 2.2 reescrito al arco nuevo como 4.4 con marcadores (visto)/estamos-aca. Thesis y Agenda reescritas. Todo renumerado; recortes documentados en Cut material; claims nuevos con fuentes oficiales citadas y verificacion online pendiente registrada en Open questions (outage de herramientas web).
  tags: [restructure, add-slide, add-visual, slide-content, sources, roadmap]
- talk: claude-cowork
  date: 2026-07-09
  location: Slide "1. Tareas programadas desde el chat" (seccion 3)
  origin: presenter-chat
  feedback: "hay tareas programadas en claude.ai en el navegador, lo estoy usando ahora"
  resolution: Slide 3.1 reescrita con Claude como ejemplo de primera clase junto a ChatGPT; tareas programadas en claude.ai desde el navegador, corren en la nube (sin compu prendida), beta con rollout desde julio 2026 empezando por Max. Removido el hedge que remitia "la forma Claude" a Cowork. Atribucion triple per L002: observacion firsthand del presentador + release notes oficiales (12138966, verificadas 2026-07-09) + TechCrunch 2026-07-07 (encuadre de terceros). Slug de ChatGPT tasks corregido al canonico 10291617-tasks-in-chatgpt.
  tags: [accuracy, sources, slide-content]
- talk: claude-cowork
  date: 2026-07-09
  location: Slide "11. Schedule en Cowork" (seccion 4)
  origin: presenter-chat
  feedback: "El hecho round-3 'Schedule corre LOCAL (compu despierta + app abierta), NO en la nube' quedo desactualizado: desde 2026-07-07 las tareas programadas corren remoto/en la nube, sin dispositivo online (beta, Max primero)."
  resolution: ACCURACY FIX en 4.11: Content reescrito ("Corren en la nube desde julio 2026"; laptop apagada SI genera el reporte; planes pagos; beta rollout Max-first; nota de que la limitacion vieja ya no aplica); Speaker notes y Sources actualizadas (13854387 re-fetcheada 2026-07-09: "Scheduled tasks run remotely... even when your computer is asleep or the Claude Desktop app is closed"; + release notes 12138966 + TechCrunch; caveats del corpus marcadas desactualizadas). Grep por otros claims "corre local": solo quedan el [closed] historico (audit trail, intacto) y la locality de Live Artifacts en 4.12, claim distinto RE-VERIFICADO vigente contra 14729249 el 2026-07-09 (vigilancia anotada en Open questions).
  tags: [accuracy, sources, slide-content]
- talk: claude-cowork
  date: 2026-07-09
  location: Slide "5. Los conectores tambien actuan" (seccion 2)
  origin: presenter-chat
  feedback: "ya esta chequeado lo del calendario"
  resolution: Accion de Calendar (agendar/crear eventos) marcada como verificada de primera mano por el presentador (2026-07-09) en Sources y Speaker notes de 2.5; sumadas dos fuentes oficiales verificadas que respaldan la capacidad ejecutiva general (11175166 "access and take action in these services"; modelcontextprotocol.io "take actions on your behalf"). Hedge conservado SOLO para tickets y mensajes (sin verificacion por conector). Open question actualizada al estado por-accion.
  tags: [accuracy, sources]
- talk: claude-cowork
  date: 2026-07-09
  location: Open questions (URLs round 4)
  origin: presenter-chat
  feedback: "Re-verificar las 6 URLs pendientes de round 4 ahora que volvio el acceso web; si alguna 404ea o contradice la slide, corregir y reemplazar la fuente."
  resolution: Las 6 verificadas el 2026-07-09: 4 OK sin cambios (web search 10684626; custom connectors 11175166; modelcontextprotocol.io; ChatGPT search 9237897 — corroborado via busqueda por 403 anti-bot del fetch directo); 2 corregidas/reemplazadas (claude.com/directory -> claude.com/blog/connectors-directory + support 11176164, por login-gate; slug de ChatGPT tasks -> 10291617-tasks-in-chatgpt). Citas de slides 2.1/2.2/2.4 actualizadas con quotes y fecha de verificacion; entradas de Open questions marcadas resueltas en draft y memory.
  tags: [sources, accuracy]
