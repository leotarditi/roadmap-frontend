# 📦 Modelo de Caja en CSS

El **modelo de caja** es uno de los conceptos más importantes en CSS. Entender cómo funciona te ayudará a escribir un CSS más predecible y fácil de controlar.

### 📜 Ejemplo inicial

Supongamos que tienes este HTML:

```html
<p>Soy un párrafo de texto y tengo algunas palabras.</p>
```

Luego aplicamos este CSS:

```css
p {
  width: 100px;
  height: 50px;
  padding: 20px;
  border: 1px solid;
}
```

A simple vista, esperarías que la caja del párrafo tuviera 100px de ancho y 50px de alto, pero en realidad, el ancho total sería **142px**. ¡Espera! ¿Por qué pasa esto? 🌟

Aquí es donde entra el **modelo de caja**. Cada elemento en la web es una "caja", y esas cajas tienen varias capas:

1. **Contenido**: el texto o cualquier otro contenido dentro del elemento.
2. **Padding**: espacio entre el contenido y el borde del elemento.
3. **Borde (border)**: la línea que rodea la caja.
4. **Margen (margin)**: el espacio entre la caja y otros elementos.

### 📏 Tamaños de la Caja: Intrínseco vs. Extrínseco

Las cajas pueden tener dos tipos de tamaño:

- **Tamaño extrínseco**: Cuando tú defines el tamaño, por ejemplo, con `width` o `height`. Si el contenido excede el espacio, puede desbordarse.
- **Tamaño intrínseco**: El navegador decide el tamaño según el contenido. Esto permite que la caja se ajuste dinámicamente.

🔍 **Ejemplo sencillo**: Tienes una caja con texto "CSS is awesome" y le das un `width` de 100px. Si el texto es más largo que 100px, se desbordará. Usar `min-content` como ancho permitirá que la caja se ajuste al tamaño mínimo que necesita el texto.

### 📚 Analogía: Una Foto en la Pared

Imagina que tienes tres fotos en la pared, cada una con un marco.

- **La caja de contenido** es la **obra de arte**.
- **El padding** es el **espacio en blanco** entre el marco y la obra.
- **El borde** es el **marco**.
- **El margen** es el **espacio entre las fotos** en la pared.

Con esta analogía, puedes entender cómo el contenido, el padding, el borde y el margen interactúan en una caja en CSS.

### 🔧 Controlando el Modelo de Caja

Por defecto, el modelo de caja en CSS usa `box-sizing: content-box;`, lo que significa que el `width` y el `height` se aplican solo al contenido. El padding y el borde se suman a esos tamaños.

Por ejemplo:

```css
.my-box {
  width: 200px;
  border: 10px solid;
  padding: 20px;
}
```

El **ancho real** de `.my-box` será **260px** (200px de contenido + 40px de padding + 20px de borde).

Para hacer el tamaño más predecible, puedes usar `box-sizing: border-box;`, que incluye el padding y el borde dentro del `width`:

```css
.my-box {
  box-sizing: border-box;
  width: 200px;
  border: 10px solid;
  padding: 20px;
}
```

De esta forma, el ancho de la caja será exactamente **200px**.

### 🔍 Visualizando el Modelo de Caja

Puedes ver cómo se comporta el modelo de caja usando las **DevTools** de tu navegador:

1. Abre DevTools (clic derecho > Inspeccionar).
2. Selecciona un elemento.
3. Ve a la sección de "Box Model" para ver el desglose de `content`, `padding`, `border` y `margin`.

### 🎨 Resumen

El **modelo de caja** es la base para comprender cómo se calculan las dimensiones de los elementos en CSS. Recordar que todo en CSS es una caja te permitirá escribir estilos más consistentes y flexibles. No olvides que:

- `box-sizing: content-box` solo aplica `width` al contenido.
- `box-sizing: border-box` incluye `padding` y `border` dentro del tamaño total de la caja.

---

# Selectores CSS: Comprendiendo y Aplicando Estilos a Elementos HTML

## Introducción

Imagina que estás en un supermercado lleno de productos (elementos HTML). Los `selectores` de CSS son como las etiquetas de precios que te ayudan a encontrar exactamente lo que necesitas y aplicarle cambios, ya sea cambiando su color, tamaño o cualquier otro atributo visual.

### Ejemplo práctico: Primer párrafo de un artículo

Supón que tienes un artículo con varios párrafos, pero deseas que el **primer párrafo** sea rojo y un poco más grande que los demás. Podrías hacer algo así:

```html
<article>
  <p>I want to be red and larger than the other text.</p>
  <p>I want to be normal sized and the default color.</p>
</article>
```

Para lograr que solo el primer párrafo cambie, puedes usar el siguiente CSS:

```css
article p:first-of-type {
  color: red;
  font-size: 1.5em;
}
```

Con esta simple regla, seleccionas el primer párrafo dentro de cada artículo y aplicas un color y un tamaño de fuente específicos.

### Descomponiendo una Regla CSS

Una regla CSS está compuesta por dos partes principales:

1. **Selector**: Indica qué elementos HTML serán afectados. Ejemplo: `article p:first-of-type`.
2. **Declaraciones**: Las reglas que se aplicarán a los elementos seleccionados. Cada declaración tiene una **propiedad** (como `color`) y un **valor** (como `red`).

```css
article p:first-of-type {
  color: red;
  font-size: 1.5em;
}
```

### Tipos de Selectores

CSS ofrece varios tipos de selectores, desde los más simples hasta los más complejos, permitiéndote aplicar estilos específicos a diferentes elementos HTML. Veamos algunos de ellos:

---

### Selector Universal

Este es el "comodín" de CSS, ya que selecciona **todos los elementos** en una página:

```css
* {
  color: hotpink;
}
```

En este ejemplo, **todos los textos de la página** se vuelven rosa fuerte. Es como si en el supermercado todas las etiquetas de precio cambiaran de color.

---

### Selector de Tipo

Un selector de tipo selecciona elementos HTML específicos, como `<section>`, `<div>`, `<p>`, etc.

```css
section {
  padding: 2em;
}
```

Este código añade un **espaciado** a todos los elementos `<section>` de la página. Es similar a aplicar un diseño específico a todas las estanterías de una tienda.

---

### Selector de Clase

Un selector de clase te permite seleccionar elementos por su atributo `class`. Es muy flexible porque puedes aplicar la misma clase a varios elementos.

```html
<div class="my-class"></div>
<button class="my-class"></button>
<p class="my-class"></p>
```

```css
.my-class {
  color: red;
}
```

En este caso, todos los elementos con la clase `my-class` tendrán texto rojo. Es como si aplicáramos un mismo descuento a productos de diferentes estanterías, solo por tener la misma etiqueta.

---

### Selector de ID

A diferencia de las clases, un `ID` debe ser **único** para cada elemento en una página.

```html
<div id="rad"></div>
```

```css
#rad {
  border: 1px solid blue;
}
```

Este CSS aplicará un borde azul solo al elemento que tenga el ID `rad`. Es como asignar un código de barras exclusivo a un producto en particular.

---

### Selector de Atributos

Puedes seleccionar elementos en función de los atributos que tengan. Por ejemplo, si un `div` tiene un atributo `data-type="primary"`, puedes aplicarle estilos específicos:

```html
<div data-type="primary"></div>
<div data-type="secondary"></div>
```

```css
[data-type='primary'] {
  color: red;
}
```

Este CSS solo selecciona los elementos con `data-type="primary"`, dándoles un texto rojo. Es como aplicar un descuento solo a productos con una etiqueta de oferta específica.

---

### Pseudoclases y Pseudoelementos

Los pseudoselectores permiten aplicar estilos en función de estados especiales o partes específicas de un elemento.

#### Pseudoclase: `:hover`

```css
a:hover {
  outline: 1px dotted green;
}
```

Este CSS aplica un borde verde punteado a los enlaces cuando el usuario pasa el ratón por encima. Es como iluminar un producto cuando alguien lo toma en sus manos.

#### Pseudoelemento: `::before` y `::after`

```css
.my-element::before {
  content: 'Prefix - ';
}
```

El pseudoelemento `::before` añade contenido antes de un elemento, sin necesidad de modificar el HTML original. Imagina que añades una etiqueta antes de un producto para resaltar información adicional.

---

### Selectores Complejos: Combinadores

En ocasiones, querrás aplicar estilos a un elemento **dentro de otro**. Aquí es donde entran los combinadores, que especifican relaciones entre elementos.

#### Combinador Descendente

```css
p strong {
  color: blue;
}
```

Este CSS selecciona todos los elementos `<strong>` que están dentro de un `<p>` y les aplica color azul. Es como decir: "Cambia de color solo a los productos que están dentro de una caja específica."

---

## Conclusión

CSS nos brinda un conjunto poderoso de herramientas para aplicar estilos a nuestros elementos HTML. Desde selectores simples como clases e IDs, hasta combinadores y pseudoselectores, podemos tener un control detallado del diseño visual de nuestras páginas web. ¡Sigue explorando más selectores para dominar el arte del CSS!

---

# La Cascada en CSS

## ¿Qué es la Cascada?

CSS significa "Hojas de Estilo en Cascada", y la cascada es el algoritmo que el navegador usa para resolver conflictos cuando se aplican múltiples reglas CSS a un mismo elemento. El resultado de este proceso es lo que vemos finalmente en la pantalla. Imagina que cada regla CSS es como una gota de agua cayendo, y la última gota en caer es la que gana. Vamos a ver cómo funciona esto con un ejemplo:

```css
button {
  color: red;
}

button {
  color: blue;
}
```

En este caso, el color del botón será **azul** porque la última regla CSS es la que se aplica. Este es el primer concepto clave de la cascada: **el orden importa**.

## ¿Cómo funciona la cascada?

La cascada se basa en cuatro principios fundamentales:

1. **Posición y Orden de Aparición**  
2. **Especificidad**  
3. **Origen del CSS**  
4. **Importancia**

Vamos a explicar cada uno de estos conceptos con una analogía sencilla y luego entraremos en los detalles técnicos.

---

### 1. Posición y Orden de Aparición

**Analogía:** Imagina que estás construyendo una torre de bloques de colores. Si pones primero un bloque rojo y luego un bloque azul, lo que verás será el bloque azul porque es el que está arriba. En CSS, el navegador aplica la última regla que encuentra cuando las reglas son iguales en especificidad.

**Ejemplo técnico:**

```css
.my-element {
  background: green;
  background: purple;
}
```

En este caso, el fondo será púrpura, ya que es la última declaración.

Este principio también se aplica cuando el CSS viene de diferentes lugares: puede haber reglas en una etiqueta `<link>`, en una etiqueta `<style>` o incluso directamente en el HTML como un atributo `style`.

Si tienes múltiples hojas de estilo vinculadas en tu página, el navegador aplicará las reglas de la última hoja de estilo. Por ejemplo, si tienes una hoja de estilo cargada en el `<head>` y otra cargada al final del `<body>`, las reglas del `<body>` se aplicarán por encima de las del `<head>`.

---

### 2. Especificidad

**Analogía:** Imagina que estás en un restaurante y hay varias personas pidiendo comida. Si el chef recibe un pedido genérico como "quiero un sándwich", y luego recibe otro que dice "quiero un sándwich de pollo con mostaza", va a preparar el más específico porque tiene más detalles.

En CSS, la **especificidad** funciona de manera similar. Las reglas más específicas ganan sobre las más generales. Hay un sistema de puntos para determinar qué selector es más fuerte:

- Selectores de **elemento** (como `button`, `div`, etc.) son los menos específicos.
- Selectores de **clase** (como `.my-class`) son más específicos.
- Selectores de **ID** (como `#my-id`) son aún más específicos.

**Ejemplo técnico:**

```html
<h1 class="my-element">Título</h1>
```

```css
.my-element {
  color: red;
}

h1 {
  color: blue;
}
```

El texto del `h1` será **rojo** porque el selector `.my-element` es más específico que el selector `h1`.

---

### 3. Origen del CSS

**Analogía:** Piensa en la jerarquía de una empresa. Primero está el jefe, luego los gerentes y finalmente los empleados. Cada nivel tiene un poder diferente para tomar decisiones. En CSS, hay tres orígenes principales que afectan qué estilos se aplican:

1. **Estilos del navegador** (lo que el navegador aplica por defecto).
2. **Estilos del autor** (lo que tú escribes en tu CSS).
3. **Estilos del usuario** (si el usuario tiene preferencias especiales en su navegador, como cambiar el tamaño de la letra o el contraste).

Cuando el navegador decide qué estilo aplicar, sigue un orden de jerarquía. Los estilos del autor generalmente ganan sobre los estilos del navegador.

---

### 4. Importancia

**Analogía:** Imagina que tienes una regla en casa que dice "todos deben apagar las luces cuando salgan de una habitación". Pero alguien dice "¡Importante! No apagues la luz del baño". Este "¡Importante!" tiene más peso que la regla general. En CSS, cuando usas `!important`, estás diciendo que esa regla es más importante y debe aplicarse sin importar qué.

**Ejemplo técnico:**

```css
.my-element {
  background: yellow !important;
}

.my-element {
  background: red;
}
```

En este caso, el fondo será **amarillo** porque tiene `!important`.

---

## Recapitulación

La cascada es el algoritmo que decide qué estilos se aplican en un elemento HTML cuando hay varias reglas en conflicto. Los cuatro factores principales que intervienen en este proceso son el orden de aparición, la especificidad, el origen del CSS y la importancia de las reglas.

- **Posición y Orden de Aparición:** La última regla en aparecer gana.
- **Especificidad:** Las reglas más específicas (ID > Clase > Elemento) ganan.
- **Origen:** El CSS creado por el autor suele tener prioridad sobre los estilos predeterminados del navegador.
- **Importancia:** Las reglas con `!important` anulan casi cualquier otra regla.

---

## Verifica tus conocimientos

Pon a prueba lo que has aprendido:

Si tienes el siguiente código:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <link rel="stylesheet" href="/styles.css" />
  </head>
  <body>
    <button>I am a button</button>
    <style>
      button {
        background: pink;
      }
    </style>
  </body>
</html>
```

Y en `styles.css` tienes esta regla:

```css
button {
  background: yellow;
}
```

**¿De qué color será el fondo del botón?**

---

Aquí tienes un archivo `README.md` que explica el concepto de especificidad en CSS usando analogías claras, con sus respectivos conceptos técnicos.

```markdown
# 📚 Especificidad en CSS

## ¿Qué es la especificidad? 🧠

Imagina que estás en un torneo de videojuegos donde cada jugador tiene una puntuación. Cuanto mayor sea la puntuación, más ventaja tiene sobre sus competidores. En CSS, las reglas funcionan de manera similar: cada selector tiene una puntuación que determina cuál regla se aplicará al elemento.

### Ejemplo:

```html
<button class="branding">Hello, Specificity!</button>
```

```css
button {
  color: red;
}

.branding {
  color: blue;
}
```

Aquí tenemos dos reglas compitiendo: una quiere que el botón sea rojo y la otra, azul. La pregunta es: **¿cuál se aplicará?**

La respuesta está en **la especificidad**, que es como el puntaje de cada selector. La regla con la mayor puntuación de especificidad será la que "gane" y se aplique.

## Puntuación de especificidad 🏆

Cada tipo de selector en CSS tiene una puntuación específica. Piensa en esto como un juego de cartas donde algunas tienen más valor que otras:

- **Selector de ID**: 100 puntos (¡es como un comodín súper poderoso!)
- **Selector de clase, atributo o seudoclase**: 10 puntos
- **Selector de tipo o seudoelemento**: 1 punto
- **Selector universal** (`*`): 0 puntos (sin valor)

### Analogía

Imagina que estás en una competencia de cocina. Tienes tres jueces: un juez famoso (ID), un juez con experiencia (clase), y un juez común (tipo). Aunque los tres pueden evaluar el plato, la puntuación del juez famoso siempre tiene más peso.

### Ejemplo práctico

```html
<button class="branding" id="special-button">Hello, Specificity!</button>
```

```css
button {
  color: red; /* 1 punto */
}

.branding {
  color: blue; /* 10 puntos */
}

#special-button {
  color: green; /* 100 puntos */
}
```

Aquí, el botón será verde, porque el selector con el ID (`#special-button`) tiene 100 puntos, superando a los otros dos selectores. **El juez famoso (ID) ha hablado, y su palabra es la ley.**

## Puntuación de los selectores 🌟

Cada tipo de selector suma puntos según sus reglas:

- **Selector universal (`*`)**: 0 puntos
- **Selector de tipo (`div`, `button`)**: 1 punto
- **Selector de clase (`.my-class`)**: 10 puntos
- **Selector de ID (`#myID`)**: 100 puntos
- **Atributo de estilo intercalado (`style="color: red"`)**: 1000 puntos
- **Regla `!important`**: 10,000 puntos (la más poderosa)

### Ejemplo: puntuaciones de especificidad

```html
<a class="my-class another-class" href="#">A link</a>
```

```css
a {
  color: red; /* 1 punto */
}

a.my-class {
  color: green; /* 11 puntos (1 del `a` + 10 de `.my-class`) */
}

a.my-class.another-class {
  color: rebeccapurple; /* 21 puntos (1 + 10 + 10) */
}

a.my-class.another-class[href] {
  color: goldenrod; /* 31 puntos (1 + 10 + 10 + 10 del atributo) */
}

a.my-class.another-class[href]:hover {
  color: lightgrey; /* 41 puntos (1 + 10 + 10 + 10 + 10 de `:hover`) */
}
```

## Visualizando la especificidad 👀

Podemos visualizar la especificidad como un marcador de puntajes. Imagina que estás jugando un juego de mesa y debes sumar puntos de cada jugada.

- **ID**: 100 puntos
- **Clase, atributo, seudoclase**: 10 puntos cada uno
- **Tipo o seudoelemento**: 1 punto cada uno

Ejemplo visual:

```css
a.my-class.another-class[href]:hover {
  color: lightgrey; /* 0-4-1: 4 en el segundo grupo y 1 en el tercero */
}
```

### Ejercicio de especificidad

¿Cuál es la puntuación de `#specialty:hover li.dark`?

- `#specialty`: 100 puntos
- `:hover`: 10 puntos
- `li`: 1 punto
- `.dark`: 10 puntos

**Total**: 1-2-1

## Especificidad pragmática 🛠️

En ocasiones, puedes necesitar aumentar la especificidad para que una regla CSS específica se aplique. Si un selector de clase no es suficiente, podrías repetirlo, pero ten cuidado de no complicar demasiado tu CSS.

### Ejemplo:

```css
.my-button {
  background: blue;
}

button[onclick] {
  background: grey;
}
```

El botón será gris porque el segundo selector tiene más puntos de especificidad (11 puntos contra 10 puntos de la clase). Si quieres asegurarte de que el fondo sea azul, puedes duplicar el selector de clase:

```css
.my-button.my-button {
  background: blue; /* 20 puntos */
}

button[onclick] {
  background: grey; /* 11 puntos */
}
```

## Regla de oro: El último selector gana 🎯

Si dos selectores tienen la misma puntuación, el CSS aplicado más recientemente (el que está más abajo en la hoja de estilo) será el que se use. 

### Ejemplo:

```css
.my-button {
  background: blue;
}

[onclick] {
  background: grey;
}
```

El botón será gris, pero si cambiamos el orden:

```css
[onclick] {
  background: grey;
}

.my-button {
  background: blue;
}
```

Ahora será azul. Esto ocurre porque ambas reglas tienen la misma especificidad, y el último en el orden "gana".

---

Aquí te dejo un archivo Markdown basado en tu artículo de **Inheritance**, con una analogía sencilla para explicar los conceptos, manteniendo los aspectos técnicos claros:

```markdown
# Inheritance en CSS

## 📜 Herencia CSS: ¿Qué es y cómo funciona?

### Imagina que estás jugando al *teléfono descompuesto*:
En este juego, un mensaje se pasa de una persona a otra. Si el primero dice "Hola", todos los demás repiten "Hola", **a menos que alguien cambie el mensaje en algún punto**. En CSS, sucede algo parecido con la herencia. Un elemento HTML puede "heredar" propiedades de su padre, **a menos que las cambies específicamente**.

Ahora veamos cómo se aplica esto en CSS.

### Ejemplo:

```html
<a href="http://example.com" class="my-button">I am a button link</a>
```

```css
.my-button {
  display: inline-block;
  padding: 1rem 2rem;
  text-decoration: none;
  background: pink;
  font: inherit;
  text-align: center;
}

article a {
  color: maroon;
}
```

Si aplicamos esta clase `.my-button`, los estilos del botón deberían mostrarse bien, **pero sucede algo inesperado**: el color del texto es *maroon* (marrón oscuro), en lugar del esperado. Esto sucede porque el enlace está dentro de un `article`, el cual tiene una regla CSS que cambia el color del texto.

Aquí, el color es heredado del `article`, ya que no se especificó un valor de `color` en la clase `.my-button`.

### 🚨 ¿Qué propiedades se heredan automáticamente?

No todas las propiedades de CSS se heredan. Aquí te dejo una lista de las que **sí se heredan** automáticamente:

- **color** (Color del texto)
- **font-family** (Fuente del texto)
- **font-size** (Tamaño de la fuente)
- **line-height** (Altura de línea)
- **text-align** (Alineación del texto)

⚠️ **Propiedades como `margin` o `padding` no se heredan**, por lo que si no las defines, no afectarán a los hijos.

## 🛠️ Herramientas para controlar la herencia

A veces, la herencia puede causar resultados inesperados en tu diseño, pero **CSS tiene herramientas para controlarla**:

### 1. **`inherit`**: Hereda explícitamente

```css
strong {
  font-weight: 900;
}

.my-component strong {
  font-weight: inherit;
}
```

En este ejemplo, cualquier `<strong>` dentro de `.my-component` **heredará el `font-weight`** del elemento padre en lugar de usar `900`. Si cambias `.my-component` en el futuro, los elementos `<strong>` seguirán la nueva regla automáticamente.

### 2. **`initial`**: Restablece al valor inicial

```css
aside strong {
  font-weight: initial;
}
```

Con `initial`, puedes restablecer una propiedad al valor por defecto del navegador. Aquí, el `<strong>` dentro de un `aside` vuelve al peso de fuente normal (sin negrita).

### 3. **`unset`**: Combina lo mejor de ambos mundos

```css
aside p {
  margin: unset;
  color: unset;
}
```

`unset` actúa como `inherit` si la propiedad se hereda, y como `initial` si no se hereda. En este ejemplo, el `margin` volverá a su valor inicial y `color` se heredará del padre.

## 🧠 Verifica tus conocimientos

**¿Cuáles de las siguientes propiedades son heredables?**

- `line-height` ✅
- `animation` ❌
- `font-size` ✅
- `text-align` ✅
- `color` ✅

**¿Qué valor se comporta como `inherit` a menos que no haya nada que heredar?**
- `unset` ✅

---

Aquí tienes un archivo markdown que describe el tema del color en CSS utilizando analogías y conceptos técnicos. Puedes usarlo como base para tu repositorio en GitHub.

```markdown
# Roadmap para Frontend: Color en CSS

## Color 

### Podcast de CSS - 006: Color Parte Uno 

El color es una parte fundamental de cualquier sitio web. En CSS, hay múltiples opciones de tipos de color, funciones y tratamientos. Pero, ¿cómo decides qué tipo de color usar? ¿Cómo puedes hacer que los colores sean semitransparentes? En esta lección, descubrirás qué opciones tienes para tomar decisiones adecuadas en tu proyecto.

### El Color como Concepto

Imagina que el color es como la paleta de un pintor. Cada color tiene su propio lugar y significado, y juntos crean una obra maestra. CSS tiene varios tipos de datos, como cadenas y números. El color es uno de estos tipos y utiliza números para definir sus características.

### Colores Numéricos

#### Colores Hexadecimales

Los colores hexadecimales son como una receta de cocina: cada ingrediente (rojo, verde, azul) tiene un valor específico. 

```css
h1 {
  color: #b71540;
}
```

La notación hexadecimal, abreviada como `hex`, representa valores para los colores primarios: rojo, verde y azul (RGB). Cada valor en `hex` va de 0-9 y A-F. Por ejemplo, el color negro se escribe como `#000000`, mientras que el negro con 50% de transparencia se representa como `#00000080`.

Para definir la transparencia, se añaden dos dígitos adicionales. Esto funciona como un código de barras, donde cada número tiene un significado específico.

**Ejemplos de transparencia:**

- Alfa del 0% (completamente transparente): `#00000000`
- Alfa del 50%: `#00000080`
- Alfa del 75%: `#000000BF`

#### RGB (Rojo, Verde, Azul)

Otra forma de definir colores es a través del modelo RGB, que se parece a un sistema de coordenadas.

```css
h1 {
  color: rgb(183, 21, 64);
}
```

En este modelo, cada componente (rojo, verde, azul) puede tener un valor entre 0 y 255. Al igual que en una mezcla de pintura, la combinación de estos colores produce un resultado final. Para definir un color negro, usarías `rgb(0, 0, 0)`.

Para añadir transparencia en RGB, puedes usar `rgb()` de dos maneras:

- `rgb(0 0 0 / 50%)`
- `rgba(0, 0, 0, 0.5)`

Ambas formas tienen su propio uso, pero el resultado es el mismo.

#### HSL (Matiz, Saturación, Luminosidad)

HSL es como la rueda de colores en una tienda de pintura. 

```css
h1 {
  color: hsl(344, 79%, 40%);
}
```

- **Matiz:** Describe el color (0-360 grados).
- **Saturación:** La intensidad del color (0% a 100%).
- **Luminosidad:** La cantidad de luz (0% a 100%).

Un color completamente negro en HSL sería `hsl(0, 0%, 0%)`.

Al igual que en RGB, puedes añadir un valor alfa:

- `hsl(0 0% 0% / 50%)`
- `hsla(0, 0%, 0%, 0.5)`

### Palabras Clave de Color

Hay 148 colores con nombres en CSS, como "púrpura" o "tomate". También puedes usar palabras clave especiales:

- **transparent:** Un color completamente transparente.
- **currentColor:** Se refiere al color actualmente aplicado al texto.

### Dónde Usar el Color en las Reglas de CSS

Cualquier propiedad que acepte `<color>` puede utilizar los métodos de color mencionados. Por ejemplo, para estilizar el texto, puedes usar propiedades como `color`, `text-shadow`, y `text-decoration-color`.

Para los fondos, puedes establecer el color usando `background` o `background-color`. Además, los colores también se pueden usar en gradientes, como `linear-gradient`, que mezcla varios colores en una sola imagen.

### Verifica Tus Conocimientos

**Pregunta 1:** ¿Cuáles de los siguientes son colores válidos?

- `#0f08` (✔️)
- `rbga(400 0 1)` (❌)
- `rgb(255, 0, 0)` (✔️)
- `hsl(180deg 50% 50%)` (✔️)
- `hotpink` (✔️)
- `#OOFZ2` (❌)

**Pregunta 2:** Localiza el color HSL no válido.

- `hsl(0 0% 0% / 20%)` (✔️)
- `hsl(0, 0, 0)` (❌)

---

