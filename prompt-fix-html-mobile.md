# Prompt — arreglar la vista mobile del render `html-strict` (talksmith)

> Pegar esto en una sesión de Claude Code abierta sobre el repo del plugin
> (`https://github.com/veigap/talksmith`, v0.69.0). Todas las rutas son relativas a la raíz del repo.

---

En el render `html-strict` de `talksmith:md-to-deck`, el deck es ilegible en un teléfono en
vertical: la slide queda como una franja fina en el medio de la pantalla, con la tipografía a
menos de un tercio de su tamaño y bandas vacías arriba y abajo. Quiero que lo arregles.

## Diagnóstico (ya verificado sobre un deck generado, no hace falta re-investigarlo)

**Causa raíz.** `skills/md-to-deck/html_style.py`, `_REVEAL_INIT` (empieza en la línea 587),
inicializa Reveal con un lienzo fijo:

```js
Reveal.initialize({
  width:1280, height:720, margin:0, minScale:0.2, maxScale:2.0,
  ...
});
```

Reveal calcula `scale = min(anchoDisponible/1280, altoDisponible/720)`. En un teléfono en
vertical (por ejemplo 390×844 px CSS) eso da `min(0.305, 1.17) = 0.305`: la slide se dibuja de
390×220 px, centrada verticalmente, y el resto de la pantalla queda vacío. No es un problema de
contenido ni de una slide puntual: le pasa a las 42.

**Factores que lo confirman y que hay que tener en cuenta al arreglarlo:**

1. **No hay ningún manejo de viewport propio.** `skills/md-to-deck/templates/html/theme.css` no
   tiene una sola `@media` ni ninguna consulta de `orientation`. Las únicas media queries del
   HTML de salida vienen del `reveal.css` vendorizado y del popup de speaker notes. El tema nunca
   contempló una pantalla angosta.
2. **`minScale:0.2` no ayuda.** Es un piso, no un remedio: la restricción que manda es el ancho,
   y 0.305 está por encima del piso. Subir `minScale` no cambia nada.
3. **El `<meta name="viewport">` está bien** (`width=device-width, initial-scale=1`). Ese no es
   el problema; descartarlo de entrada.
4. **`fitContent()` (mismo bloque `_REVEAL_INIT`) mide en píxeles del lienzo, no del dispositivo.**
   Lee `cb.clientWidth` / `cb.clientHeight`, que siempre son relativos a los 1280×720 lógicos. O
   sea que ajusta el contenido igual en cualquier pantalla y después Reveal escala todo por 0.305.
   No sabe que existe el teléfono.
5. **A favor nuestro: el tema ya es responsive por dentro.** `theme.css:16` declara
   `.reveal .slides>section{height:100%;padding:0;container-type:inline-size}` y **todas** las
   medidas tipográficas y de espaciado están en `cqw` (container query units) — ver `.stage`,
   `.stitle`, `.lead`, `.cfit`, etc. Si una slide pasa a ser un bloque de ancho completo que
   conserve `container-type:inline-size`, todo el sistema de tamaños se re-escala solo. **Esta es
   la palanca: no hay que re-tipografiar nada.**

## Lo que quiero

Un **modo lectura vertical**: en pantallas angostas y verticales, el deck deja de ser un lienzo
fijo con navegación por slides y se reflowea como documento — una slide abajo de la otra, a todo
el ancho, con tipografía de tamaño normal y scroll vertical. Es el modo en el que uno revisa un
borrador desde el teléfono.

Alcance del breakpoint: `@media (max-width: 820px) and (orientation: portrait)`. Fuera de ahí,
**cero cambios**.

### Requisitos

- **Desktop y proyección intactos.** El comportamiento actual (lienzo 1280×720, navegación de
  Reveal, fragments, transiciones, overview con `Esc`, pantalla completa con `F`) no se toca.
- **Export a PDF intacto.** `?print-pdf` tiene que seguir produciendo el mismo PDF apaisado. Ojo:
  el modo lectura no puede filtrarse dentro de `@media print`.
- **Speaker notes intactas.** La vista `s` y los `<aside class="notes">` siguen igual; en modo
  lectura las notas siguen sin mostrarse en la cara de la slide.
- **Aprovechar los container queries.** En modo lectura cada `section` debería quedar como bloque
  de ancho completo con su `container-type:inline-size` intacto y una relación de aspecto libre
  (que crezca según el contenido, sin `height:100%` ni `overflow:hidden`). Los `cqw` hacen el
  resto.
- **Neutralizar el fit por slide.** En modo lectura hay que desactivar `fitContent()` y
  `fitCover()` (o hacer que salgan temprano): sus `transform: scale()` y sus `width` calculados en
  píxeles del lienzo pelean con el reflow. Lo mismo con el `transform` de `.reveal .slides` que
  aplica Reveal.
- **Los fragments no pueden esconder contenido.** Con `reveal` por defecto los ítems entran de a
  uno por click. En un documento scrolleable eso deja la mitad de cada slide invisible: en modo
  lectura todos los fragments tienen que estar visibles.
- **Autodetección, sin toggle nuevo.** Que entre solo por media query. Si querés dejar un escape
  manual, que sea un parámetro de URL al estilo del `?deck-theme=` que ya existe
  (`_THEME_EARLY`, línea 658), no un botón más en la interfaz.
- **Sin dependencias nuevas.** El deck se entrega autocontenido (`build_html.py` inlinea Reveal,
  las fuentes y las imágenes como data-URI). Nada de CDN.

### Dónde tocar

- `skills/md-to-deck/templates/html/theme.css` — el bloque de modo lectura. El archivo es CSS
  estático sin interpolación (se lee en `html_style.py:582`), así que es el lugar natural.
- `skills/md-to-deck/html_style.py` — `_REVEAL_INIT` (línea 587) para la salida temprana de
  `fitContent`/`fitCover` y para cualquier `Reveal.configure` que haga falta al entrar y salir del
  modo (rotar el teléfono tiene que funcionar en vivo, en las dos direcciones).

Antes de escribir código, revisá si Reveal 4 no resuelve parte de esto de fábrica: mirá si el
`reveal.js` vendorizado ya trae la vista de scroll / `view: 'scroll'` (Reveal 5) o
`disableLayout`. Si está disponible, usarlo es mejor que hacer el reflow a mano. Decime qué
encontraste y qué camino tomás **antes** de implementar.

### Cómo verificar

1. Generá un deck de prueba con el test de estilo que ya existe (`build_html.py --model`) o con
   `tests/`, y revisalo en tres viewports: 1440×900, 390×844 (vertical) y 844×390 (horizontal).
2. En 390×844 tiene que verse: una slide por bloque a todo el ancho, tipografía legible sin zoom,
   scroll continuo, todos los ítems visibles (nada escondido detrás de un fragment), imágenes
   dentro del ancho.
3. En 1440×900 y en 844×390 el resultado tiene que ser **byte-idéntico** al de antes del cambio,
   salvo el CSS/JS nuevo. Verificalo con un diff.
4. `?print-pdf` sigue exportando apaisado.
5. Actualizá `CHANGELOG.md` y, si corresponde, la sección *Presentation* de
   `skills/md-to-deck/SKILL.md` (hoy describe navegación, escalado y export, y no menciona el
   comportamiento en mobile).

### Fuera de alcance

No cambiar la clasificación de slides, el contrato de `slide-model.json`, las plantillas Jinja de
cada tipo, ni el render `.pptx`. Esto es exclusivamente la capa de presentación HTML.
