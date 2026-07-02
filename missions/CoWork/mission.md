# 🛰️ Misión: "Atlas, el analista de mercado de tu equipo"

> **Tu desafío laboral:** tu jefe necesita que, todas las semanas, alguien entregue un reporte claro sobre las empresas que el equipo vigila. Ese alguien sos vos — y no sos analista ni técnico. En vez de quemarte cada lunes armando el reporte a mano, vas a construir a **Atlas**, un analista virtual que lo hace por vos. Cuatro milestones. Una misión. Sin escribir una sola línea de código. **Empezamos.**

---

## 🎬 La situación

Lunes, 8:55 de la mañana. Reunión de equipo a las 9:00.

Tu jefe te mira y dice: *"Necesito que sigas estas tres empresas: **Apple, Microsoft y Nvidia**. Un pulso semanal — qué se movió, qué noticias salieron, qué hay que vigilar. Y lo quiero **de dos formas**: un **email en mi inbox, una vez por semana**, y una **página web siempre actualizada** con un resumen, que yo pueda abrir cuando quiera. Algo así…"*

Y te garabatea en una servilleta cómo se imagina esa página:

![Boceto del jefe — así se imagina la página web (el tablero) con el resumen semanal](mockup-tablero.png)

*El boceto del jefe: una página con el resumen, una tarjeta por empresa y una tabla. Eso es lo que vas a construir como **página web** en el Milestone 4 (el **email semanal**, en el Milestone 3).*

Traducción: te acaban de asignar un reporte recurrente, manual y aburrido —sobre **3 acciones puntuales que tu jefe eligió**— que te va a comer la mañana de cada lunes para siempre.

Hasta ahora, ese trabajo lo venía haciendo a medias **un pasante del equipo**: cada semana entraba a un montón de portales (Yahoo Finance, Bloomberg, CNBC…) y pegaba lo que encontraba en **un archivo distinto por cada fuente**, una forma rústica de no olvidarse de nada. Te deja esa pila de archivos como herencia (están en la carpeta `reportes/`, una subcarpeta por semana con una carpeta `fuentes/` adentro): son notas en crudo, desordenadas, repartidas entre muchos archivos, con comentarios al margen. Ese es tu punto de partida. **A menos que…**

A menos que delegues. En esta misión vas a **contratar a Atlas**: un analista virtual que investiga las empresas del equipo, arma el reporte mientras vos dormís, lo deja en el correo del equipo y lo publica en un tablero que tu jefe puede abrir cuando quiera. Lo entrenás una vez. A partir de ahí, trabaja solo.

Pero el verdadero premio no es Atlas: **sos vos, dominando Claude Cowork.** Este encargo de oficina es la excusa perfecta para tocar, una por una y en el orden justo, todas las piezas que hacen de Cowork una bestia. Cuando termines, no vas a haber "leído sobre" Cowork. Vas a haber resuelto un problema real de trabajo con él.

---

## 🎯 Qué vas a construir (y qué desbloqueás en cada etapa)

Un **Proyecto** en Cowork que vas a hacer crecer por **milestones**, como en un videojuego: cada uno es un **incremento funcional** que ya sirve por sí solo, te da un **superpoder nuevo de Cowork** encima del anterior, y deja a Atlas más cerca de hacer tu trabajo por vos.

| Milestone | Lo que logra Atlas | Superpoder de Cowork que desbloqueás |
|-------|--------------------|--------------------------------------|
| **1 · 🥚 Atlas nace** | **Reporte a pedido:** convierte las notas sueltas del pasante en un pulso semanal prolijo, con formato fijo | **Projects** + **Instructions** + **Skills** |
| **2 · 🔎 Atlas aprende a investigar** | **Reporte autónomo:** consigue noticias y precios por su cuenta — chau copy-paste manual | **Tools** (búsqueda web) + **Connectors** (datos de acciones) |
| **3 · 🐣 Atlas trabaja solo** | **Reporte listo para enviar:** cada lunes deja el reporte como borrador en Gmail, listo para revisarlo y mandarlo | **Connectors** (Gmail) + **Schedule** |
| **4 · 📣 Atlas llega al equipo** | **Página pública:** el tablero `pulso-semanal` se publica en una URL accesible para todo el equipo y se refresca sola cada semana | **Artifacts** (Live Artifacts) · **Connectors** (ShareDuo) · **Skills** |

Desde el primer milestone ya tenés algo útil; al final, el jefe **recibe el email y abre la web** — las dos cosas que pidió, sin que vos toques nada. Y la web es una **URL pública**, compartible con todo el equipo sin que nadie necesite tener Cowork.

---

## 👥 Para quién es esta misión

Para cualquiera que tenga que **entregar trabajo recurrente**, aunque jamás haya programado nada. Acá no se programa: se **guía a Claude con técnicas de prompting** y se **combinan las piezas de Cowork** (Projects, Skills, Connectors, Schedule, Artifacts). Si sabés mandar un email y mover una carpeta, ya tenés todo lo que hace falta. La barrera de entrada es cero. El techo es altísimo.

---

## 📁 Materiales incluidos

La misión viene con material de ejemplo en la carpeta `reportes/`. Hay **una subcarpeta por semana**. Dentro de cada una está la carpeta `fuentes/` —las notas en crudo del pasante, **un archivo por cada portal** (la *entrada*)— **lado a lado** con el **reporte final** ya ordenado (`.md`, la *salida*). Sirve para ver de dónde se parte y a dónde se llega:

```
reportes/
├── semana-2026-05-18/
│   ├── fuentes/                          ← entrada: notas del pasante, un archivo por fuente
│   │   ├── yahoo-finance.txt    (cotizaciones)
│   │   ├── bloomberg.txt        (Nvidia)
│   │   ├── the-next-platform.txt (Microsoft)
│   │   └── coincentral.txt      (Apple)
│   └── reporte-semana-2026-05-18.md      ← salida: el reporte que arma Atlas
├── semana-2026-05-25/   (varios archivos en fuentes/  +  reporte-…md)
└── semana-2026-06-01/   (varios archivos en fuentes/  +  reporte-…md)
```

> 💡 Las **noticias y los enlaces** de los ejemplos son **reales** (mayo 2026); los **precios y porcentajes** son **aproximados**, con fines ilustrativos.

---

## ✅ Antes de despegar (checklist de setup)

Estas son las **condiciones de base** — revisalas **antes** del workshop. Si algo falta, avisá al facilitador. Lo que hace falta para cada etapa puntual (búsqueda web, Gmail, etc.) te lo recuerda **cada milestone justo cuando lo vas a usar**, así no cargás con todo de entrada.

- [ ] **App de escritorio de Claude** instalada (macOS o Windows) y en su **última versión**. Cowork **no** corre en la web ni en el celular para *crear* las cosas; sí vas a poder dispararlo desde el celular una vez armado.
- [ ] **Plan pago de Claude** (Pro, Max, Team o Enterprise). El plan gratis no incluye Cowork.
- [ ] La pestaña **"Cowork"** visible (junto a "Chat" y "Code"). ¿No la ves? Actualizá la app.

---

## 🪜 La misión, milestone por milestone

### 🥚 Milestone 1 — Atlas nace
**Desbloqueás: Projects · Instructions · Skills**

**El objetivo:** levantar el cuartel de Atlas y enseñarle, con precisión de relojero, cómo se ve el reporte que tu jefe quiere recibir.

> ✅ **Necesitás para este milestone:** una **carpeta vacía** para el cuartel de Atlas (ej.: `Documentos/Atlas-Mercado`) y las **3 acciones a seguir** — caso base **AAPL (Apple), MSFT (Microsoft), NVDA (Nvidia)**. *(Podés cambiarlas por el sector o los competidores de tu empresa; tres alcanzan para aprender todo y el ejercicio corre más rápido.)*

**Tu misión:**

1. Crear un **Proyecto** llamado *"Inteligencia de Mercado Semanal"*, apuntado a tu carpeta.
2. Escribir las **Instrucciones del proyecto**: quién es Atlas, qué empresas sigue, para qué audiencia escribe (tu equipo), con qué tono, qué formato usa y la regla de oro — **nunca da consejos de inversión**.
3. Crear tu propia **Skill** (`reporte-semanal`): recibe **qué semana** querés procesar (la carpeta `semana-AAAA-MM-DD/`), toma **todos los archivos de su carpeta `fuentes/`** y los consolida en un reporte con plantilla fija — precio, movimiento, noticias clave, "ánimo" del mercado y qué vigilar.
4. Darle de comer las **fuentes de una semana** y ver nacer **el primer reporte** ordenado en tu carpeta.

**🏁 Lo lográs cuando:** tu **Skill `reporte-semanal`** toma **todos** los archivos de la carpeta `fuentes/` de una semana, consolida la info por empresa y genera un `reporte-semana-AAAA-MM-DD.md` **igual al reporte de ejemplo de esa misma semana** (la *salida* que ya está en la carpeta): mismo formato exacto, todas las empresas, la tabla resumen, las fuentes y la aclaración legal.

> 📎 **¿Cómo debería verse?** En la carpeta `reportes/` hay **una subcarpeta por semana**, y dentro de cada una la carpeta `fuentes/` (los archivos en crudo del pasante, uno por portal) **lado a lado** con el **reporte final** (`.md`). Mirá un par antes de empezar para ver de dónde se parte y a dónde se llega.

---

### 🔎 Milestone 2 — Atlas aprende a investigar
**Desbloqueás: Tools (búsqueda web) · Connectors (MCP)**

**El objetivo:** el salto más difícil de la misión. Que Atlas deje de depender de notas que alguien le deja servidas y **salga a conseguir la información él mismo** —la parte que parecía imposible sin saber programar—: dado un ticker y un día, que busque precios y noticias en la web y en un servicio de datos de acciones al que te conectás, y deje las fuentes en disco.

> ✅ **Necesitás para este milestone:** la **búsqueda web activada** en Cowork (Configuración → Capacidades) — es el oxígeno de Atlas para leer precios y noticias. *(La conexión a **MT Newswires** es el Paso 1 de abajo: ya tiene un connector listo en Cowork, no instalás nada de antemano.)*
>
> 🌐 **Claude in Chrome:** algunas páginas (como Yahoo Finance) renderizan el contenido con JavaScript y no son accesibles por búsqueda web sola. Para esos casos, Cowork puede usar **Claude in Chrome** como navegador real. Necesitás dos cosas: **Google Chrome instalado** en tu computadora, y la extensión **Claude in Chrome** instalada y habilitada. Podés seguir los pasos oficiales acá: [Cómo instalar Claude in Chrome](https://support.anthropic.com/en/articles/12012173-getting-started-with-claude-for-chrome). Si ya la tenés, asegurate de que esté activa antes de arrancar este milestone.

**Tu misión:**

1. **Conectarte a MT Newswires** (el proveedor de noticias de mercado al que tenemos suscripción) desde el directorio de Connectors, y dejarlo conectado. Lo bueno: **ya tiene un connector listo en Cowork**, así que no hay que crear ni configurar nada — solo buscarlo y conectarlo. → [MT Newswires](https://www.mtnewswires.com)
2. Crear una **segunda Skill** (`buscar-accion`): dado un **ticker + una semana**, busca en **[Yahoo Finance](https://finance.yahoo.com/news/)** (web) y en el **proveedor que conectaste**, y **guarda el resultado en disco** dentro de `fuentes/` (un archivo por fuente).
3. Correrla para las 3 acciones y comprobar que reconstruye la carpeta `fuentes/` de la semana — sin que vos pegues una sola noticia.

**🏁 Lo lográs cuando:** Atlas llena la carpeta `fuentes/` **partiendo de cero**, con precios y noticias que él mismo encontró, y con eso la Skill `reporte-semanal` arma el reporte. **Atlas dejó de ser un asistente que copia: ahora investiga solo.**

---

### 🐣 Milestone 3 — Atlas trabaja solo
**Desbloqueás: Connectors (Gmail) · Schedule**

**El objetivo:** que Atlas deje de esperar tus órdenes. Que escriba el reporte, lo **mande por email al equipo** y lo haga **todas las semanas, sin vos** — listo antes de la reunión de los lunes.

> ✅ **Necesitás para este milestone:** una **cuenta de Gmail** a mano (en el workshop el reporte queda como borrador en tu cuenta, ya dirigido a `superboss@gmail.com`, listo para enviarlo con un clic). Y grabate esto: **las tareas programadas solo corren con la compu encendida y la app de Claude abierta.**

**Tu misión:**

1. Conectar el **Connector de Gmail** — el brazo de Atlas hacia el correo.
2. Pedirle que **deje el reporte de esta semana como borrador en Gmail**, dirigido a `superboss@gmail.com` (la prueba de fuego).
3. Programar con `/schedule` una tarea que cada **lunes a las 8:00** genere el reporte, lo guarde y lo deje como borrador en Gmail dirigido a `superboss@gmail.com` — listo para revisarlo y enviarlo antes de la reunión de las 9:00.

**🏁 Lo lográs cuando:** el reporte de prueba aparece como borrador en tu Gmail **y** aparece tu tarea recurrente en la sección **"Scheduled"**, lista para disparar cada lunes.

---

### 📣 Milestone 4 — Atlas llega al equipo
**Desbloqueás: Artifacts (Live Artifacts) · Connectors (ShareDuo) · Skills**

**El objetivo:** que el tablero no quede guardado en tu computadora sino publicado en una **URL accesible para todo el equipo** — sin que nadie necesite tener Cowork. La Skill actualiza el Live Artifact `pulso-semanal` (cuyo formato ya está definido) y lo publica vía **ShareDuo**, todo solo cada lunes.

> ✅ **Necesitás para este milestone:** registrar **ShareDuo** como **MCP connector** en Cowork (Configuración → Connectors → Add MCP). Es el servicio que le da una URL pública al tablero. *(Lo hacés en el Paso 1 de abajo, no hace falta configurarlo antes del workshop.)*

**Tu misión:**

1. **Registrar y habilitar ShareDuo** como MCP connector en Cowork: buscalo en el directorio de Connectors, agregalo como MCP y verificá que quede activo.
2. Crear la **Skill `publicar-tablero`**: actualiza el Live Artifact `pulso-semanal` con los datos del último reporte (el diseño ya está definido — es el boceto del jefe que ves arriba — solo cambian los datos) y luego lo publica vía ShareDuo, devolviendo la URL pública que el equipo puede bookmarkear.
3. Correrla para publicar el tablero por primera vez y compartir la URL con el equipo.
4. **Engancharla a la tarea del lunes** (Milestone 3): cada semana, después del reporte y el email, Atlas refresca el tablero y la URL queda al día sola.

**🏁 Lo lográs cuando:** el equipo tiene una **URL pública con el tablero**, la tarea programada la refresca cada lunes, y vos no tocás nada. **Atlas llega al equipo.**

> 🎨 **Qué esperar:** el tablero tiene el mismo diseño que el **boceto del jefe** de la primera página — la imagen que garabateó en la servilleta. Ese es el formato a respetar.

---

## 📏 Las reglas del juego

- **Conversá, no programes.** Todo se consigue describiéndole a Claude lo que querés. ¿No salió? Reformulá y volvé a tirar.
- **Respetá el orden.** Cada milestone se para sobre el anterior. Saltearte uno es construir un piso sin cimientos.
- **Verificá antes de avanzar.** Tocá el criterio de éxito con la mano antes de pasar de milestone.
- **Cuando te trabes, preguntale a Atlas.** Cowork también sabe explicarse a sí mismo — usalo como copiloto.
- **Tomá nota mientras avanzás.** Anotá qué te sorprendió, qué no salió como esperabas y cómo lo resolviste. Esas notas son el verdadero aprendizaje de la misión — y el mejor recurso si querés repetirla con otro encargo.

---

## ⚠️ La letra chica (que importa)

Atlas es un ejercicio **educativo** para dominar Cowork. Sus reportes **no son recomendaciones de inversión** ni asesoramiento financiero: son una síntesis de información pública para uso interno del equipo. Cada decisión de inversión es de quien la toma. Esta aclaración va escrita en las instrucciones del proyecto — la dejamos clavada en el Milestone 1.

---

> 🚀 **Cuando completes los cuatro milestones**, habrás recorrido las seis piezas centrales de Claude Cowork — **Projects, Instructions, Skills, Connectors, Schedule y Artifacts** —, más las **herramientas de búsqueda, el navegador, la conexión a MT Newswires y la publicación vía ShareDuo** que las potencian, no en una diapositiva sino resolviendo un encargo real de trabajo. La guía de resolución, paso a paso, te espera en `mission-res.md`. **Que empiece la misión.**
