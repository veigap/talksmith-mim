# Requerimiento — `content-image` emite su columna de texto aunque esté vacía

## El problema, en una frase

En `content-image`, el contenedor de texto se emite **incondicionalmente**. Si la lámina no
tiene `lead` ni `facts`, sale un `<div class="citext"></div>` vacío — que en el layout
`image-top` está estilado como una **caja con fondo y borde de acento**, así que se proyecta
un cajón vacío debajo de la imagen.

## Dónde está, exactamente

`skills/md-to-deck/templates/html/content-image.j2`, macro `citext`:

```jinja
{% macro citext(s) %}
<div class="citext">
{{ m.lead(s) -}}
{% if s.facts %}<ul class="cifacts">…</ul>{% endif %}
</div>
{% endmacro %}
```

`m.lead(s)` ya está guardado por dentro (`{% if s.lead %}`) y la lista de `facts` también.
**El wrapper no.** Sin `lead` y sin `facts`, el macro devuelve un div vacío, y los tres
layouts lo insertan igual.

El estilo que lo vuelve visible está en `theme.css` línea 204:

```css
.ci.ci-top .citext{ … background:var(--card); border-left:.6cqw solid var(--red);
                    border-radius:.8cqw; padding:1.5cqw 2cqw; … }
```

Un div sin contenido pero con `background`, `border-left` y `padding` **se ve**.

## Los tres síntomas

| layout | qué se proyecta |
|---|---|
| `image-top` | una **caja de nota vacía** debajo de la imagen: fondo, borde rojo a la izquierda, padding, sin una letra adentro |
| `text-left` (default) | media lámina en blanco a la izquierda; la imagen se queda en su mitad derecha, a la mitad del ancho que podría usar |
| `image-left` | lo mismo, espejado |

Los tres son la misma causa. El de `image-top` es el que salta primero porque el cajón vacío
es literalmente visible; los otros dos pasan por "la imagen quedó chica".

## Los dos casos reales que lo destaparon

Repo `talksmith-mim`, Talk `claude-cowork`, render `html-strict` del 2026-07-31:

1. **Slide 1.4 «Dónde se empieza en Cowork».** Es una lámina de **imagen sola**: el autor pidió
   explícitamente *"solo dejá la imagen, no pongas el texto"* y bajó los cuatro bullets a las
   Speaker notes. El modelo quedó con `image` y nada más → caja vacía.

2. **Slide 1.3 «El mapa: piezas que se apilan».** Acá el `final.md` **sí** tiene una línea de
   lead (`**Idea clave:** cada bloque resuelve un problema conocido…`), pero el FILL la ruteó a
   `highlights` en vez de a `lead`. Resultado: el texto aparece en la banda de abajo y la caja
   de arriba queda vacía. Misma caja vacía, causa de origen distinta.

El segundo caso es útil porque muestra que esto **no** requiere una lámina rara: alcanza con
que el modelo mande el texto a otro campo.

## Qué pido

### 1. El arreglo mínimo, que es el bug

Guardar el wrapper: **no emitir `.citext` si no hay ni `lead` ni `facts`.**

```jinja
{% macro citext(s) %}{% if s.lead or s.facts %}
<div class="citext">…</div>
{% endif %}{% endmacro %}
```

Con eso, `image-top` sin texto renderiza solo la imagen, y los layouts lado a lado dejan de
reservar media lámina para nada.

**Cuidado con el grid.** `.ci` es `grid-template-columns:1fr 1fr` (theme.css 178) y `.ci-top`
es un flex column. Si el `citext` desaparece, la imagen tiene que **ocupar el ancho completo**,
no quedarse en su mitad con la otra en blanco. Probablemente haga falta una regla del tipo
`.ci:not(:has(.citext)){grid-template-columns:1fr}` o una clase que el `.j2` agregue cuando no
hay texto — lo que el mantenedor prefiera, pero **el ancho es parte del arreglo**, no un
detalle aparte. Un arreglo que solo saca la caja y deja la imagen a media lámina no sirve.

### 2. Lo que el bug destapa: falta el caso "una imagen sola"

`content-image` está definido en el catálogo como *"columna de texto (lead + algunos facts o
un callout) en una mitad; 1-3 imágenes en la otra"*. Una lámina de **imagen sola** no encaja
en esa descripción, y **ningún template del catálogo la cubre**: `image-grid` pide ≥4 imágenes
donde "la variedad es el mensaje", `figures` pide una imagen por ítem. Hoy la única salida es
usar `content-image` sin texto, que es justo lo que dispara el bug.

Es una forma de lámina totalmente común — una captura de pantalla que el presentador recorre
hablando, con todo el detalle en las notes. Dos salidas posibles, a elección del mantenedor:

- **(a)** Documentar que `content-image` sin `lead` ni `facts` **es** el caso de imagen sola,
  y que renderiza a ancho completo. Es lo más barato y probablemente lo correcto.
- **(b)** Un template propio (`image-full` o similar) y una regla de *Match* en el catálogo.

Cualquiera de las dos sirve; lo que no sirve es que quede sin decidir, porque entonces cada
FILL la clasifica distinto.

### 3. Una línea de criterio para el FILL (el caso 1.3)

En `schemas/slide-model.md`, la guía de FILL: **si la lámina tiene una línea de lead antes de
su enumeración o su imagen, va a `lead`.** Solo se manda a `highlights` una línea que
*comenta* el cuerpo (un `takeaway` que cierra), no la que lo *introduce*.

En el `final.md` de 1.3 la línea está escrita como `**Idea clave:** …` al principio del
`### Content`, arriba del diagrama — es un lead, no un cierre. Sin este criterio explícito el
formato `**Etiqueta:** texto` se lee como highlight y el lead queda vacío.

## Restricciones

1. **Compatibilidad hacia atrás.** Toda lámina con `lead` o `facts` renderiza exactamente como
   hoy. El cambio solo afecta al caso que hoy sale roto, así que no hay deck que regrese.
2. **No tocar `highlights`.** Si la lámina tiene highlights, la banda de abajo sigue igual.
   Una lámina puede quedar perfectamente como imagen + banda de highlights y sin `citext` —
   ese es 1.3 tal como está hoy en el modelo.
3. **El mismo guard, si aplica, en los otros templates.** Vale revisar si algún otro `.j2`
   emite un contenedor sin guardar (mismo patrón: wrapper afuera del `{% if %}`). Si aparece,
   arreglarlo en la misma pasada; si no, dejar constancia de que se revisó.
4. **La ruta PPTX.** Comprobar qué hace la receta §13 content+image con un modelo sin texto:
   si deja un marco de texto vacío en el `.pptx`, es el mismo bug en el otro render.

## Archivos que toca

- `skills/md-to-deck/templates/html/content-image.j2` — el guard del wrapper (macro `citext`).
- `skills/md-to-deck/templates/html/theme.css` — la regla de ancho completo cuando no hay
  columna de texto (junto a `.ci` línea 178 y `.ci-top` línea 197).
- `config/pptx-styles/slide-templates.md` — la entrada `#### content-image` (~línea 424), para
  decir qué pasa sin texto (punto 2).
- `schemas/slide-model.md` — la guía de FILL, criterio lead vs. highlights (punto 3), cerca de
  la línea 207 donde ya se explica cuándo usar cada `layout`.

## Cómo se verifica que quedó bien

1. Un modelo `content-image` con `layout:"image-top"`, `image` y **nada** de texto: se proyecta
   la imagen sola. **Ninguna caja, ningún borde de acento, ningún padding fantasma.**
2. El mismo modelo en `text-left` y en `image-left`: la imagen ocupa el **ancho completo** de
   la lámina, no media.
3. El mismo modelo pero con `highlights`: la imagen a ancho completo **y** la banda de
   highlights debajo, como hoy.
4. Cualquier lámina existente con `lead` y/o `facts`: HTML byte-idéntico al de antes.
5. Los dos casos reales: **1.4** de `claude-cowork` sale como imagen sola limpia, y **1.3** con
   su "Idea clave" arriba de la imagen como lead.

## Nota sobre el estado actual del deck

Para no dejar el deck roto mientras esto se arregla, ya apliqué dos parches **en el modelo**,
que hay que **revertir** cuando el plugin esté:

- **1.4** está forzada a `image-grid` con una sola imagen. Es un abuso del template (el catálogo
  pide ≥4) y lo único que lo justifica es que es el único que renderiza una imagen sin chrome
  de texto. Vuelve a `content-image` apenas exista el guard.
- **1.3** tiene la "Idea clave" movida de `highlights` a `lead`. Este cambio **no** es un
  parche: es la clasificación correcta según el `final.md` y se queda así.
