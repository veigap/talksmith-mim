# Requerimiento — soportar `layout: image-left` en `content+cards+image`

## El problema, en una frase

Hoy una lámina que tiene **tarjetas Y una imagen** no puede pedir que la imagen vaya a la
izquierda. `content-image` soporta `layout` (`text-left` / `image-left` / `image-top`) pero
sus ítems son `facts`, que renderizan como lista con negrita y **sin ícono**.
`content+cards+image` sí da tarjetas con ícono por concepto, pero **no tiene campo `layout`**:
las tarjetas van siempre a la izquierda y la imagen siempre a la derecha.

Eso deja al autor eligiendo entre dos cosas que no deberían competir: **íconos** o
**imagen-izquierda**.

## Caso que lo disparó

Repo `talksmith-mim`, Talk `claude-cowork`, slide **1.2 «De chatear a delegar»**. Es una
lámina de cuatro pares paralelos (chatear vs. delegar: la forma de trabajo, los pasos, la
salida, el rol humano) más un diagrama que la prosa recorre. El autor pinó
`<!-- layout: image-left -->` porque quiere que el diagrama entre primero por el ojo y el
texto lo siga.

Para honrar ese hint, el FILL la clasificó `content-image` y los cuatro pares bajaron a
`facts` — y perdieron el ícono. Si en cambio se clasifica `content+cards+image`, recupera
los íconos y pierde la posición de la imagen. Las dos salidas son peores que la lámina que
el autor quiso.

## Qué pido

Que **`content+cards+image` acepte el campo `layout`**, con la misma semántica y los mismos
valores que ya tiene `content-image`:

| valor | efecto |
|---|---|
| `text-left` | **default**, comportamiento actual: tarjetas a la izquierda, imagen a la derecha |
| `image-left` | espejado: imagen a la izquierda, tarjetas a la derecha |

`image-top` **no** se pide para este template. Una pila de tarjetas debajo de una imagen a
ancho completo es otra lámina, no una variante de layout; si alguna vez hace falta, que sea
una decisión aparte. Rechazar el valor de forma explícita es preferible a soportarlo a medias.

## Restricciones que no se pueden romper

1. **Compatibilidad hacia atrás.** `layout` es opcional. Un modelo sin el campo tiene que
   renderizar exactamente como hoy. Ningún deck existente puede cambiar un píxel.

2. **El orden del markup no se toca.** `content-image` ya resolvió esto bien y hay un
   comentario en `theme.css` (líneas ~192-194) que explica por qué: el espejado es
   **solo visual**, vía `order:` en el grid. El HTML mantiene el orden tarjetas-después-imagen,
   así que el orden de lectura para PDF y lector de pantalla no cambia. Copiar ese enfoque,
   no reordenar los nodos en el `.j2`.

3. **La enumeración no se espeja.** Igual que en `content-image`: las tarjetas conservan su
   orden, su alineación a la izquierda y su ícono. Lo único que cambia de lado son las dos
   columnas del grid.

4. **El asimétrico del grid.** `.cci` hoy es `grid-template-columns:1.1fr 1fr` — la columna
   de tarjetas es un poco más ancha que la de la imagen. En `image-left` ese `1.1fr` tiene que
   seguir siendo **la columna de las tarjetas**, no la de la imagen. Con `order:` esto sale
   solo (las columnas del grid no se mueven, se mueve el contenido), así que verificar que
   la imagen no herede la columna ancha.

5. **El hint de autor sigue mandando.** `<!-- layout: image-left -->` debajo del `##` de la
   slide ya *pinea* el campo en `content-image` (el FILL lo copia en vez de juzgar). Tiene que
   comportarse igual acá: el hint gana sobre el criterio del modelo.

## Archivos que toca (según el plugin de hoy)

- **`schemas/slide-model.md`** — la fila de `content+cards+image` en la tabla de campos
  (~línea 119-126) pasa a listar `layout` (`text-left`|`image-left`) entre los opcionales,
  como ya lo hace la fila de `content-image`. Y la guía de FILL (~línea 207-212), que hoy
  explica cuándo poner `image-left` **solo** para `content-image`, tiene que decir que la
  misma decisión aplica a `content+cards+image`.

- **`config/pptx-styles/slide-templates.md`** — la entrada `#### content+cards+image`
  (~línea 442) hoy describe un "~50/50 split: cards en una mitad + imagen en la otra" sin
  mencionar layouts. Sumar las dos variantes, con el mismo criterio de elección que ya está
  escrito en la entrada de `content-image`: *"pick the layout from the content … image to be
  read first → `image-left`; an author hint pins it"*.

- **`skills/md-to-deck/templates/html/content-cards-image.j2`** — hoy emite
  `<div class="cci">` fijo. Pasa a emitir la clase condicional, exactamente con la forma que
  ya usa `content-image.j2` en su línea 14:
  `<div class="cci{{ ' cci-imgleft' if s.layout == 'image-left' else '' }}">`

- **`skills/md-to-deck/templates/html/theme.css`** — junto al bloque `.cci` (~línea 207),
  agregar el par de reglas espejo, calcadas de `.ci.ci-imgleft`:
  `.cci.cci-imgleft .ccicards{order:2}` y `.cci.cci-imgleft .imgph{order:1}`.
  Conservar el comentario que explica **por qué** el espejado es solo visual; es la clase de
  cosa que alguien "arregla" reordenando el markup si no está dicho.

- **La ruta PPTX.** El mismo `slide-model.json` alimenta el render `.pptx`, así que revisar
  qué hace su spec (`config/pptx-styles/*/pptx-prompt.md`, receta §13
  content+cards+image) con un `layout` que hoy ignora. Dos salidas aceptables: implementarlo,
  o **ignorarlo de forma documentada**. Lo que no sirve es que HTML y PPTX difieran en
  silencio, porque el objetivo declarado del modelo compartido es que una lámina se vea igual
  en los dos renders.

## Cómo se verifica que quedó bien

1. Render `html-strict` de un deck existente **sin** ningún `layout` en un
   `content+cards+image`: el HTML tiene que salir byte-idéntico al de antes del cambio.
2. La misma lámina con `"layout":"image-left"`: imagen a la izquierda, tarjetas a la derecha,
   **con sus íconos**, tarjetas en el mismo orden y alineadas a la izquierda.
3. `?print-pdf` sobre esa lámina: el orden de lectura del PDF sigue siendo tarjetas → imagen.
4. Un `"layout":"image-top"` en `content+cards+image`: falla o avisa, no rompe callado.
5. La lámina 1.2 de `claude-cowork` reclasificada a `content+cards+image` con su hint
   `image-left` intacto: es el caso real, y tiene que dar la lámina que el autor pidió desde
   el principio.

## Lo que NO estoy pidiendo

- No pido un template nuevo. `content+cards+image` ya es el correcto para "tarjetas + una
  imagen de apoyo"; le falta un solo campo.
- No pido cambiar `content-image` ni sus `facts`. Sigue siendo el template correcto para
  texto de apoyo que no es un set etiquetado.
- No pido íconos en `facts`. Las viñetas sin ícono son una decisión de diseño válida para
  ese template; el problema es no poder elegir tarjetas cuando la lámina las pide.
