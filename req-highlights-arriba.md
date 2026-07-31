# Requerimiento — poder poner un `highlight` **arriba** del cuerpo de la lámina

## El problema, en una frase

`highlights` sale **siempre debajo** del cuerpo, en todos los templates, sin forma de
cambiarlo. Está hardcodeado en el macro compartido `stage()`
(`skills/md-to-deck/templates/html/_macros.j2`, línea 14), que envuelve a todas las láminas
de contenido. Un highlight que **abre** la lámina hoy no se puede expresar.

## Por qué no es un descuido, y por qué igual falta

El diseño actual asume que un highlight es un **cierre**. La lógica de reveal lo dice
explícitamente en `schemas/slide-model.md` (~línea 96): los ítems enumerados aparecen uno a
uno y después *"`highlights` como un bloque final, para que el texto de conclusión aterrice
**después** de aquello que comenta, en vez de ser legible desde el arranque"*.

Para un `takeaway` eso es exactamente correcto y no hay que tocarlo. El problema es que
`highlights` no es solo `takeaway`: el schema define seis `kind` y varios **no son
conclusiones**. Una `quote` que encuadra el tema, una `definition` que hay que tener antes de
leer los ítems y un `important` que es una advertencia previa **quieren ir arriba**. Están
usando un contenedor cuya única posición asume lo contrario.

## Caso que lo disparó

Repo `talksmith-mim`, Talk `claude-cowork`, slide **1.2 «De chatear a delegar»**. Lleva un
highlight `kind: quote`:

> **Anthropic:** Menos una sesión de chat, más asignarle tareas a un colega.

Es el encuadre de la lámina: la frase con la que el presentador **abre** antes de recorrer los
cuatro pares chatear/delegar. Hoy sale al pie, después de la enumeración, donde se lee como
un resumen de algo que ya se dijo. Cambia el sentido de la lámina.

## Los rodeos que existen hoy, y por qué no alcanzan

- **Pasarla a `lead`.** El lead sí va arriba, pero 1.2 **ya tiene lead** ("Lo que cambia ahora
  es el rol: delegar. ¿Qué delegamos?") y el campo es uno solo. Además el lead es prosa
  plana: pierde la banda de acento, el ícono y la itálica que `.highlight.quote` le da a una
  cita — que es justo lo que la hace leer como cita y no como bajada del título.
- **Meterla como primer `fact` / primera `card`.** La mezcla con la enumeración, que es
  precisamente lo que no es, y le saca el tratamiento visual.

## Qué pido

Un campo **de posición por entrada de `highlights`**:

```json
"highlights": [
  { "kind": "quote", "label": "Anthropic",
    "body": "Menos una sesión de chat, más asignarle tareas a un colega.",
    "position": "top" }
]
```

| valor | efecto |
|---|---|
| `bottom` | **default**, comportamiento actual: banda debajo del cuerpo |
| `top` | banda entre el título y el cuerpo de la lámina |

**Por entrada, no por lámina** — a propósito. El caso real que va a aparecer enseguida es una
lámina con una `quote` que encuadra arriba **y** un `takeaway` que cierra abajo. Un flag a
nivel de slide obligaría a elegir. Con el campo por entrada, el render agrupa: todas las
`top` en una banda arriba (en su orden de aparición en el array) y todas las `bottom` en la
banda de abajo, tal como hoy.

## La decisión de diseño que hay que tomar en el pedido: **qué hace el reveal**

Hoy el bloque de highlights llama a `frag(s)` y aparece como **último paso** del clic. Si un
highlight sube, ¿sigue apareciendo último?

**Mi recomendación: no.** Un highlight en `top` debe estar **visible desde que abre la
lámina**, sin fragment. El razonamiento es simétrico al que ya está escrito para los de abajo:
si el de abajo aparece último *porque comenta lo que ya se vio*, el de arriba tiene que estar
primero *porque encuadra lo que todavía no se vio*. Un encuadre que aparece después de la
enumeración no encuadra nada — sería el mismo bug que el pedido intenta arreglar, movido de
lugar.

Concretamente: la banda `top` **no** lleva `frag(s)`; la banda `bottom` lo conserva tal cual.
`reveal: together` sigue anulando todo, sin cambio.

Si el mantenedor prefiere otra resolución, que sea explícita y quede documentada en el
schema — lo que no sirve es dejarlo librado a la implementación, porque es la diferencia
entre que la lámina funcione o no.

## Restricciones que no se pueden romper

1. **Compatibilidad hacia atrás.** `position` es opcional y su default es `bottom`. Una
   entrada sin el campo renderiza exactamente como hoy. Ningún deck existente puede cambiar
   un píxel, y ningún modelo existente necesita migración.

2. **Un solo tratamiento visual.** La banda de arriba usa **las mismas clases** `.highlights`
   / `.highlight` y los mismos colores e íconos por `kind` que la de abajo. Esto **no** es una
   variante de estilo, es la misma pieza en otro lado. Lo único que cambia es el espaciado:
   `.highlights` hoy tiene `margin-top:2.4cqw` (theme.css línea 184); arriba corresponde el
   espejo, `margin-bottom`, para no pegarla al cuerpo.

3. **Funciona en todos los templates.** El cambio va en `stage()`, que es compartido, así que
   sale gratis para los ~25 templates. No hacer una excepción por template.

4. **No se toca `lead`.** Siguen siendo cosas distintas: el lead es la bajada en prosa del
   título, el highlight es una línea acentuada con `kind`. Una lámina puede tener los dos, y
   en ese caso el orden es **título → lead → highlights(top) → cuerpo → highlights(bottom)**.

## Archivos que toca (según el plugin de hoy)

- **`skills/md-to-deck/templates/html/_macros.j2`** — `stage()` (líneas 10-16). Hoy emite un
  solo bloque de highlights después de `caller()`. Pasa a emitir dos bloques particionados por
  `position`, el de arriba antes de `caller()` y sin `frag(s)`, el de abajo donde está y como
  está. Conviene extraer el `for` a su propio macro y llamarlo dos veces, en vez de duplicar
  la línea.

- **`skills/md-to-deck/templates/html/theme.css`** — junto a `.highlights` (línea 184), la
  regla de la banda superior con `margin-bottom` en lugar de `margin-top`. Nada más: los
  colores por `kind` (líneas 189-191) se reusan sin cambio.

- **`schemas/slide-model.md`** — la definición de `highlights` (líneas 69-80) suma `position`
  a la forma de cada entrada (`{body, label?, kind?, position?}`) y la tabla de valores. Y la
  guía de reveal (~línea 96) tiene que decir qué pasa con los `top` — es donde vive hoy el
  razonamiento del "aterriza después", así que ahí mismo va el caso simétrico.

- **`schemas/slide-model.md`, guía de FILL** — una línea de criterio para que el modelo elija
  bien: **un `takeaway` va abajo por default; una `quote` de encuadre, una `definition` que
  hace falta antes de leer los ítems, o un `important` que es advertencia previa, van arriba.**
  Sin esto el campo existe pero nadie lo usa.

- **`config/pptx-styles/slide-templates.md`** — donde el catálogo describe la banda acentuada
  (~línea 227 menciona el ícono a la izquierda), aclarar que puede ir arriba o abajo.

- **La ruta PPTX.** El mismo `slide-model.json` alimenta el render `.pptx`. El render PPTX es
  estático (no tiene reveal), así que ahí **la posición es puramente de layout** y debería ser
  más fácil de implementar que en HTML. Igual que en el otro requerimiento: implementarlo o
  ignorarlo de forma documentada, pero que no difieran en silencio.

## Cómo se verifica que quedó bien

1. Render de un deck existente, sin ningún `position`: HTML byte-idéntico al de antes.
2. Una lámina con un highlight `position: top`: la banda sale entre el título (o el lead, si
   lo hay) y el cuerpo, con el mismo color, ícono y tipografía que tendría abajo.
3. **El caso mixto**, que es el que más fácil se rompe: una lámina con una `quote` en `top` y
   un `takeaway` en `bottom` tiene que dar **dos bandas separadas**, una arriba y otra abajo,
   no una sola con todo junto ni dos veces la misma.
4. Reveal: al abrir esa lámina, la banda de arriba **ya está visible** y la de abajo aparece
   en el último clic. Con `reveal: together`, todo visible de una.
5. La lámina 1.2 de `claude-cowork` con `"position":"top"` en su cita de Anthropic: es el caso
   real, y tiene que abrir con la cita.

## Lo que NO estoy pidiendo

- No pido un `kind` nuevo ni cambiar los seis que hay.
- No pido un segundo campo tipo `lead`. El lead ya existe y hace otra cosa.
- No pido posiciones más finas (entre la enumeración y la imagen, al costado, etc.).
  Arriba y abajo alcanzan; más granularidad es complejidad sin caso que la pida.
