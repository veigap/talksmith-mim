# 🛰️ Misión: "Faro, la mesa de inteligencia de mercado de Atlas"

*Paulo Veiga · Marco Sánchez Sorondo · Claudio Righetti · Juan Pablo Cosentino*

> **Tu desafío laboral:** trabajás en **Atlas**, una empresa que vende insumos de perforación para Vaca Muerta. Tu jefe quiere, todas las semanas, un reporte claro sobre las empresas que marcan el pulso de nuestro mercado. Ese trabajo cae en vos, y no sos analista ni técnico. En vez de armarlo a mano cada lunes, vas a construir **Faro**, un analista de mercado virtual que lo hace por vos, con el **chat de Claude** que ya usás. Sin escribir una sola línea de código. **Empezamos.**

---

## 🎬 La situación

Trabajás en **Atlas**, una empresa de insumos de perforación para los pozos de **Vaca Muerta**. Lunes, 8:55 de la mañana. Reunión de equipo a las 9:00.

Tu jefe te mira y dice: *"La inversión en IA está disparando la demanda de energía en todo el mundo: los centros de datos consumen electricidad sin freno, y eso empuja la demanda de petróleo y gas. Vaca Muerta está en el centro de esa historia, y nuestro negocio depende de cuánto se perfore. Necesito seguir de cerca a los tres jugadores que mueven nuestro mercado: **YPF, Vista y Tenaris**. Un pulso semanal: qué se movió, qué noticias salieron, qué hay que vigilar. Lo quiero como un **email en mi inbox** cada lunes, antes de la reunión de las 9."*

Traducción: te acaban de asignar un reporte recurrente y manual, sobre **3 empresas que tu jefe eligió**, que te va a comer la mañana de cada lunes.

Hasta ahora lo hacía a medias **un pasante**: cada semana entraba a un montón de portales (Yahoo Finance, Bloomberg, Reuters…) y pegaba lo que encontraba en un archivo por fuente. Ya no está, y el trabajo cae en vos. **A menos que…**

A menos que delegues. Vas a construir **Faro**: un analista de mercado virtual que investiga esas tres empresas, arma el pulso mientras dormís y deja el email listo en el correo. Lo configurás una vez. Después, trabaja solo.

El premio no es Faro: es que al terminar vas a dominar el chat extendido resolviendo un encargo real de trabajo, no leyendo sobre él.

---

## 👥 Para quién es esta misión

Para cualquiera que tenga que **entregar trabajo recurrente**, aunque nunca haya programado. Acá no se programa: se **guía a Claude con lenguaje natural** y se **combinan las piezas que viste en clase**. Si sabés mandar un email, ya tenés lo que hace falta.

---

## ✅ Antes de despegar (checklist de la Parte 1)

Revisá estas condiciones de base **antes** del workshop. Si algo falta, avisá al facilitador.

- [ ] Una cuenta de Claude con **plan pago** y acceso a **claude.ai** en el navegador.
- [ ] Una cuenta de **Gmail** a mano.

---

# 🧩 PARTE 1 — Faro en el chat

*Sin instalar nada: el chat de Claude que ya usás, extendido con conectores y tareas programadas.*

### 🔎 Milestone 1 — Faro se conecta
**Desbloqueás: Conectores (búsqueda web · noticias · Gmail)**

**El objetivo:** que el chat responda con información **real y de esta semana** sobre YPF, Vista y Tenaris, en vez de responder de memoria de entrenamiento.

**Tu misión:**

1. Activar la **búsqueda web** (un toggle en la configuración del chat), pedirle el pulso de la semana de las 3 empresas y verificar que **cite fuentes** (el "buscando…" y las citas son tu punto de control).
2. Conectar **Massive** (el proveedor de noticias al que tenemos suscripción) desde la **biblioteca de conectores**: buscarlo, darle Connect y autorizar.
3. Conectar **Gmail** de la misma forma y verificar que funciona: pedirle en un chat un resumen de los mails de ayer.
4. Pedir el pulso de nuevo, ahora con las dos fuentes conectadas, y comparar la diferencia de calidad.

**🏁 Lo lográs cuando:** el chat arma un pulso de la semana con precios y noticias **citadas de fuentes reales**, sin que pegues una sola noticia a mano.

---

### ⚙️ Milestone 2 — Faro trabaja solo
**Desbloqueás: Tareas programadas · Conectores que actúan (borrador en Gmail)**

**El objetivo:** que el pulso deje el chat y aparezca **solo, todas las semanas**, como borrador de email listo para mandar antes de la reunión de los lunes.

**Tu misión:**

1. Pedirle al chat que **deje el pulso de esta semana como borrador en Gmail**, dirigido a `admin@intuitiv-ai.com` (la prueba de fuego de la capacidad ejecutiva; el borrador **no se envía solo**, y eso es a propósito).
2. Crear una **tarea programada** en claude.ai: cada **lunes a las 8:00**, armar el pulso de las 3 empresas con los conectores y dejarlo como borrador en Gmail dirigido a `admin@intuitiv-ai.com`, listo antes de la reunión de las 9:00.
3. Ejecutarla a demanda una vez para verificarla sin esperar al lunes.

**🏁 Lo lográs cuando:** el borrador aparece en tu Gmail **y** la tarea queda visible en tu lista de tareas programadas, lista para disparar cada lunes. **El jefe ya tiene su email semanal.**

---

# 🧩 PARTE 2 — Faro en Cowork

*Faro baja a tu computadora: carpetas y archivos reales, reporte con formato fijo, el tablero del jefe, y todo empaquetado para reutilizar.*

El email del lunes ya llega solo, y el jefe quedó **muy contento**. Tanto, que ahora quiere más: el mismo pulso, además del email, en un **PDF con mejor capacidad visual** — una página que pueda abrir y leer de un vistazo. Y te garabatea en una servilleta cómo se lo imagina:

![Boceto del jefe: así se imagina el tablero con el resumen semanal](mockup-tablero.png)

*El boceto: una página con el resumen, una tarjeta por empresa y una tabla.*

Para armar eso cada semana, Faro necesita algo que el chat no tiene: trabajar sobre las **carpetas y archivos reales** del equipo — la herencia del pasante incluida. Acá entra **Claude Cowork**.

---

## 📁 Materiales incluidos

La misión viene con material de ejemplo en `reportes/`. Hay **una subcarpeta por semana**. Dentro de cada una, la carpeta `fuentes/` (las notas en crudo del pasante, **un archivo por portal**: la *entrada*) **lado a lado** con el **reporte final** ya ordenado (`.md`, la *salida*). Sirve para ver de dónde se parte y a dónde se llega:

```
reportes/
├── semana-2026-05-18/
│   ├── fuentes/                          ← entrada: notas del pasante, un archivo por fuente
│   │   ├── yahoo-finance.txt    (cotizaciones)
│   │   ├── bloomberg.txt        (Vista Energy)
│   │   ├── reuters.txt          (YPF)
│   │   └── stocktitan.txt       (Tenaris)
│   └── reporte-semana-2026-05-18.md      ← salida: el reporte que arma Faro
├── semana-2026-05-25/   (varios archivos en fuentes/  +  reporte-…md)
└── semana-2026-06-01/   (varios archivos en fuentes/  +  reporte-…md)
```

> 💡 Las **noticias y los enlaces** de los ejemplos son **reales** (mayo 2026); los **precios y porcentajes** son **aproximados**, con fines ilustrativos.

---

## ✅ Antes de despegar (checklist de la Parte 2)

- [ ] La **app de escritorio de Claude** (macOS o Windows) en su **última versión**, con la pestaña **"Cowork"** visible, con la sesión del plan pago iniciada (el plan gratis no incluye Cowork). Cowork también está llegando a web y mobile (beta, despliegue gradual), pero esta misión trabaja sobre carpetas locales, así que usamos la app de escritorio.
- [ ] Saber **dónde corren tus tareas programadas** (lo viste en clase): en la nube si tu cuenta ya tiene la beta (despliegue gradual, primero Max); si no, corren **local**, con la computadora prendida y la app abierta. Las tareas que usan **archivos de tu disco corren local siempre**.

### 🛠️ Milestone 3 — Faro toma forma
**Desbloqueás: Projects · Instrucciones · archivos .md**

**El objetivo:** montar la base de Faro: un Project con carpeta propia, un contrato de trabajo escrito una sola vez, y toda la información de trabajo en `.md`.

**Tu misión:**

1. Crear una **carpeta dedicada** para Faro (ej.: `Documentos/Faro-Mercado`) y copiar adentro la carpeta `reportes/` de los materiales. Que no contenga datos confidenciales: la carpeta que concedés es el control de privacidad.
2. Crear un **Project** llamado *"Inteligencia de Mercado Semanal"*, apuntado a esa carpeta con el explorador de archivos.
3. Escribir las **Instrucciones del proyecto**: qué es Faro, qué empresas sigue, para qué audiencia escribe (tu equipo en Atlas), con qué tono, y la regla de oro: **nunca da consejos de inversión**.
4. Poner la información de trabajo en orden y **en `.md`**: pedirle a Faro que convierta las notas en crudo de una semana de `fuentes/` a archivos `.md` prolijos. El trabajo iterativo pasa sobre un formato de archivo eficiente para que la IA trabaje sobre él; el formato final se genera al último.
5. Pedirle **en la conversación** el reporte de esa semana con el formato del reporte de ejemplo (primero comprobás que Faro sabe hacerlo).
6. Cerrar la sesión pidiéndole a Faro que escriba un **`CLAUDE.md`** en la raíz de la carpeta: el contexto del proyecto en texto plano (qué es Faro, cómo está organizada la carpeta, decisiones y pendientes), para que la próxima conversación no arranque de cero.

**🏁 Lo lográs cuando:** el Project existe con sus Instrucciones, Faro produce un `reporte-semana-AAAA-MM-DD.md` **igual al reporte de ejemplo de esa semana** (mismo formato, todas las empresas, la tabla resumen, las fuentes y la aclaración legal), y el **`CLAUDE.md`** quedó en la raíz de la carpeta de Faro con el contexto del proyecto.

> 📎 **¿Cómo debería verse?** En `reportes/` hay una subcarpeta por semana, y dentro la carpeta `fuentes/` lado a lado con el reporte final (`.md`). Mirá un par antes de empezar.

---

### ⏰ Milestone 4 — El lunes se arma solo
**Desbloqueás: Schedule en Cowork · Conectores dentro del Project**

**El objetivo:** la tarea programada que armaste en el chat, ahora sobre tu carpeta: cada lunes Faro consigue la información, arma el reporte en el Project y deja el borrador en Gmail.


**Tu misión:**

1. Pedirle a Faro que, dado un **ticker y una semana**, busque precios y noticias (web + Massive) y **guarde las fuentes en disco**, un archivo por fuente, dentro de `fuentes/` de la semana.
2. Verificarlo para las 3 empresas: la carpeta `fuentes/` se reconstruye **partiendo de cero**, sin pasante.

Programar desde la pestaña **Scheduled** la tarea del **lunes 8:00**: conseguir fuentes → armar el reporte `.md` en el Project → dejar el borrador en Gmail dirigido a `admin@intuitiv-ai.com`. Usar **"Run now"** para probarla sin esperar al lunes.

**🏁 Lo lográs cuando:** una corrida de la tarea, completa y sin tocar nada, deja las fuentes en disco, el reporte en la carpeta de Faro y el borrador en Gmail.

---

### 📊 Milestone 5 — El tablero del jefe
**Desbloqueás: el formato final (del .md de trabajo al PDF de entrega)**

**El objetivo:** el encargo nuevo del jefe: el tablero con el diseño de su boceto, generado por Faro como **PDF** con los datos de cada semana. Es el principio de la clase en acción: se trabaja en `.md`; el formato final se genera una vez, al final.

**Tu misión:**

1. Pedirle a Faro que genere **`pulso-semanal-FECHA.pdf`** en la carpeta del Project, con el diseño del boceto del jefe (tarjetas por empresa, tabla resumen), alimentado por el reporte de la semana.
2. Verificar el **historial**: un PDF por semana queda en la carpeta, con la fecha en el nombre.
3. **Engancharlo a la tarea del lunes** (Milestone 4): después del reporte, Faro genera el PDF y lo **adjunta al borrador** de email para el jefe.

**🏁 Lo lográs cuando:** el tablero respeta el boceto, se genera con la corrida de cada lunes, y le llega al jefe adjunto al mail sin que lo armes a mano.

> 🎨 **Qué esperar:** el mismo diseño del boceto del jefe. Ese es el formato a respetar.

---

### 🧰 Milestone 6 — Faro se vuelve reutilizable
**Desbloqueás: Skills**

**El objetivo:** todo lo que le explicaste a Faro más de una vez, escribirlo una vez. Las rutinas de la misión se convierten en **Skills** con nombre, listas para reutilizar y compartir.

**Tu misión:**

1. Convertir en Skill el armado del reporte: **`reporte-semanal`** (toma la semana, lee `fuentes/`, consolida con el formato fijo). Un trabajo por Skill.
2. Convertir en Skill la investigación: **`buscar-accion`** (ticker + semana → fuentes en disco).
3. Convertir en Skill el tablero: **`publicar-tablero`** (genera el `pulso-semanal-FECHA.pdf` con el último reporte).
4. Abrir un `SKILL.md` y reconocer la anatomía que viste en clase: metadata arriba (la `description` decide cuándo se activa), instrucciones en Markdown abajo.

**🏁 Lo lográs cuando:** la tarea del lunes corre apoyada en las tres Skills, y cualquier compañero con tu Project puede disparar el mismo flujo sin que le expliques nada.

---

## 📏 Las reglas del juego

- **Conversá, no programes.** Todo se consigue describiéndole a Claude lo que querés. ¿No salió? Reformulá y volvé a tirar.
- **Respetá el orden.** Los milestones se apoyan entre sí: verificá uno antes de encarar el siguiente.
- **Verificá antes de avanzar.** Tocá el criterio de éxito con la mano antes de pasar de milestone.
- **Cuando te trabes, preguntale a Claude.** También sabe explicarse a sí mismo: usalo como copiloto.
- **Tomá nota mientras avanzás.** Qué te sorprendió, qué no salió y cómo lo resolviste. Esas notas son el verdadero aprendizaje, y el mejor recurso para repetir la misión con otro encargo.

---

## ⚠️ La letra chica (que importa)

Faro es un ejercicio **educativo** para dominar el chat extendido y Claude Cowork. Sus reportes **no son recomendaciones de inversión** ni asesoramiento financiero: son una síntesis de información pública para uso interno del equipo. Cada decisión de inversión es de quien la toma. Esta aclaración va escrita en las instrucciones del proyecto: la dejamos clavada en el Milestone 3.

---

> 🚀 **Cuando completes los seis milestones**, habrás recorrido las piezas de la clase en el mismo orden en que las aprendiste: **Conectores y Tareas programadas** en el chat, y **Projects, Instrucciones, archivos .md, Schedule y Skills** en Cowork, resolviendo un encargo real de trabajo. La guía de resolución, paso a paso, te espera en `mission-res.md`. **Que empiece la misión.**
