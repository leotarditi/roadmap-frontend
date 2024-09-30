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

# Entendiendo las Unidades de Tamaño en CSS con Analogías Simples

### Unidades de Tallas en CSS

Imagina que estás diseñando una prenda de ropa. Necesitas saber las medidas para crear un buen ajuste. En CSS, el concepto es similar: necesitas especificar medidas para los elementos de tu página web. Las unidades de tamaño son como esas medidas, y te permiten controlar cómo se ajustan los elementos en diferentes situaciones.

---

### 🧵 **Analogía: Ajustando la Talla de la Ropa**  
Piensa en las unidades de CSS como tallas de ropa. Dependiendo del material (en este caso, el tamaño de la pantalla o el dispositivo), la talla puede cambiar, pero las reglas que usas para decidir la talla son las mismas.

---

### 1. **Unidades Relativas: Adaptándose al Entorno**

Las unidades relativas son como ropa elástica, ajustándose al cuerpo de quien la use. Estas unidades se adaptan en función del contexto. Un ejemplo es la unidad `em`, que cambia su tamaño en función del tamaño de la fuente de su elemento superior. Si la fuente principal es más grande, el valor de `em` también lo será. Lo mismo ocurre con `rem`, que usa como referencia el tamaño de la fuente del elemento raíz.

#### 👕 **Analogía**: 
Imagina que haces una camiseta para niños. Si haces la camiseta 1.5 veces más grande que la medida del niño (es decir, usas `1.5em`), la camiseta crecerá o se reducirá dependiendo del tamaño del niño (la fuente base del elemento).

#### Ejemplo técnico:
```css
p {
  font-size: 24px;
  line-height: 1.5; /* Esto es un 150% del tamaño de la fuente */
}
```
Aquí, `1.5` se refiere a la proporción de la altura de la línea en relación con el tamaño de la fuente. Si la fuente es de 24px, la altura de línea será 36px (150%).

---

### 2. **Unidades Absolutas: Tamaños Fijos, Sin Elasticidad**

Por otro lado, las unidades absolutas son como un traje formal hecho a medida. Una vez que lo has cortado, no puedes estirarlo ni encogerlo. Un `px` (píxel) es una unidad absoluta que siempre mide lo mismo sin importar dónde lo uses.

#### 👔 **Analogía**: 
Si decides que una chaqueta mida 50cm de ancho, ese tamaño será fijo. No importa quién la use, esa chaqueta siempre tendrá ese ancho. Lo mismo sucede con los `px`, `cm` o `in` en CSS.

#### Ejemplo técnico:
```css
div {
  width: 10cm;
  height: 5cm;
}
```
Este `div` tendrá siempre un tamaño de 10x5 centímetros, perfecto si estás diseñando algo para impresión, donde el tamaño debe ser preciso.

---

### 3. **Porcentajes: Elásticos y Proporcionales**

Los porcentajes en CSS funcionan como si ajustaras una prenda proporcionalmente al tamaño del cuerpo. Si dices que el ancho de un elemento debe ser el `50%`, estás diciendo que debe ocupar la mitad del espacio disponible en su contenedor superior.

#### 👗 **Analogía**: 
Es como si la prenda estuviera diseñada para ocupar el 50% del ancho de la persona que la viste. Si la persona (el contenedor) es más grande, la prenda (el elemento) también será más grande.

#### Ejemplo técnico:
```css
div {
  width: 50%; /* El div ocupará la mitad del ancho disponible */
}
```
En este ejemplo, el `div` siempre será la mitad del tamaño de su contenedor principal, sin importar cuánto cambie el tamaño de la ventana del navegador.

---

### 4. **Unidades del Viewport: Ajustes Basados en la Ventana**

Ahora, imagina que la prenda que estás creando puede cambiar dependiendo del lugar donde te encuentres. Las unidades de viewport (`vw`, `vh`) son como esa prenda mágica. Se adaptan al tamaño de la ventana del navegador.

#### 👕 **Analogía**: 
Si dices que tu camiseta mide `10vw` de ancho, significa que la camiseta siempre será el 10% del ancho de la ventana del navegador. A medida que el navegador se agranda o se achica, la camiseta cambiará su tamaño para mantenerse proporcional.

#### Ejemplo técnico:
```css
div {
  width: 10vw; /* El div será el 10% del ancho de la ventana */
}
```

---

### 5. **Unidades Especiales: Control Preciso para Casos Específicos**

Hay otras unidades especiales como `ch`, que mide el ancho de un caracter "0" en la fuente utilizada. Estas unidades son útiles para casos específicos donde necesitas un control muy detallado sobre el tamaño de los elementos.

#### 👕 **Analogía**: 
Imagina que ajustas el ancho de una prenda en función de la anchura de un botón específico. Cada botón en la prenda mide lo mismo, por lo que puedes usar ese botón como referencia para ajustar el resto de las medidas.

#### Ejemplo técnico:
```css
p {
  max-width: 60ch; /* El párrafo no podrá ser más ancho que 60 caracteres "0" */
}
```

---

### Resumen

Las unidades de tamaño en CSS son herramientas clave para diseñar interfaces web que sean funcionales y estéticamente agradables. Al entender cómo funcionan y cómo se adaptan a diferentes situaciones, puedes diseñar páginas que se vean bien sin importar el dispositivo en el que se vean.

**Unidades relativas**: Se adaptan al contexto (como em, rem, %).  
**Unidades absolutas**: Tienen un tamaño fijo (como px, cm).  
**Viewport units**: Se basan en el tamaño de la ventana del navegador (vw, vh).

```css
p {
  font-size: 1.2rem; /* relativo al tamaño de fuente raíz */
  width: 80vw;       /* 80% del ancho de la ventana */
}
```

---

# Diseño CSS: Estructurando el Camino

## Imagina que eres un arquitecto
Para entender el diseño en CSS, imagina que eres un arquitecto que está diseñando una casa. Tienes que decidir cómo distribuir cada habitación (elementos), si estarán alineadas una al lado de la otra (diseño horizontal), una encima de la otra (diseño vertical) o en ambas direcciones (diseño bidimensional). CSS es tu herramienta, como los planos que decides usar para organizar cada parte de la casa.

### Diseño: Una Breve Historia
Al principio, la web era como construir casas usando mesas plegables. Los desarrolladores usaban elementos `<table>` para organizar contenido, lo cual era como intentar usar mesas para construir paredes. Luego llegó CSS y fue como si hubiéramos descubierto cemento: ahora podíamos separar la estructura (HTML) del diseño (CSS). Esto permitió que los arquitectos (desarrolladores) diseñaran casas (sitios web) sin modificar las paredes originales (HTML).

#### Evolución del Diseño CSS
CSS ha ido evolucionando y mejorando sus herramientas. Es como si ahora tuvieras más opciones de materiales y técnicas de construcción para hacer tu casa más sólida y estética. Hoy en día, contamos con herramientas avanzadas como **Flexbox** y **Grid**.

### Propiedad `display`: Definiendo el Comportamiento de las Habitaciones

- **Bloque (`block`)**: Piensa en los elementos de bloque como si fueran paredes de una casa. Ocupan todo el espacio horizontal disponible y no pueden estar al lado de otros elementos. Son grandes y sólidos.
  
  ```css
  .my-element {
      display: block;
  }
  ```

- **Intercalado (`inline`)**: Los elementos intercalados son como los muebles en una habitación. No ocupan todo el ancho y pueden estar alineados uno al lado del otro, como sillas alineadas en un salón.

  ```css
  .my-element {
      display: inline;
  }
  ```

### Flexbox: Un Eje para Organizar
**Flexbox** es como una cinta transportadora en una fábrica: alinea todo en una sola fila (eje) o columna. Te permite ajustar el espacio entre los elementos, estirarlos o contraerlos según el espacio disponible. Ideal para cuando quieres que todo esté alineado de manera organizada en una sola dirección, como en un estante.

```css
.my-element {
    display: flex;
}
```

- **`align-items`**: Es como decidir si los objetos estarán alineados al centro o distribuidos en los extremos.
  
  ```css
  .my-element {
      display: flex;
      align-items: center;
  }
  ```

### Grid: Diseños en Dos Dimensiones
Si Flexbox es una cinta transportadora que organiza en una fila, **Grid** es como tener un plano cuadriculado para organizar todo en dos dimensiones: filas y columnas. Imagina que estás organizando los muebles en tu salón y quieres que algunos ocupen más espacio que otros. Grid te da ese control.

```css
.my-element {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 1rem;
}
```

- **`grid-template-columns`**: Con esta propiedad defines el número de columnas y su tamaño, como si estuvieras decidiendo cuántas paredes poner en cada parte de la casa.

### Conclusión

CSS es como tu herramienta de diseño y construcción. Flexbox es ideal para organizar elementos en una sola fila o columna, mientras que Grid te permite organizar en varias filas y columnas. ¡Tu sitio web es como una casa y tú eres el arquitecto que decide cómo todo encaja perfectamente!

---

# 📦 Caja Flexible (Flexbox)

### ¿Qué es Flexbox?

Imagina que tienes una caja llena de objetos de diferentes tamaños y formas. Quieres organizarlos dentro de la caja de la mejor manera posible. A veces tienes mucho espacio, a veces no tanto, pero quieres que los objetos se adapten al espacio disponible sin hacerte pasar un mal rato.

Así funciona **Flexbox**, un modelo de diseño CSS que te permite organizar elementos en una "caja flexible" que se adapta al tamaño del contenedor y los elementos que contiene. Esto es ideal para crear interfaces que cambian de tamaño de acuerdo con el tamaño de la pantalla (o **viewport**).

---

## 🚀 Conceptos Básicos de Flexbox

### Eje Principal y Eje Cruzado

Imagina que el eje principal es una cinta transportadora donde vas colocando tus objetos. Este eje lo decides tú. Puede ser una **fila** (los objetos se colocan uno al lado del otro) o una **columna** (los objetos se apilan uno encima del otro).

El **eje cruzado** es el eje que cruza al principal. Si tu cinta transportadora es una fila, el eje cruzado será vertical, y si es una columna, el eje cruzado será horizontal.

```css
/* El eje principal es una fila */
.container {
  display: flex;
  flex-direction: row; /* También puede ser 'column' */
}
```

### 💡 Ejemplo Visual:
Imagina una estantería (contenedor) donde pones libros (elementos flexibles). Si los libros no caben todos en una fila (eje principal), algunos caerán en la siguiente fila (eje cruzado). Flexbox te ayuda a decidir cómo se organizan.

### Flexibilidad en el Espacio

En una fila normal, los objetos se alinean rígidamente. Si no caben, simplemente se desbordan o se ven mal. Con Flexbox, los objetos **crecen o se encogen** dependiendo del espacio disponible. Piensa en ellos como globos que pueden expandirse o reducirse según el espacio que tengan.

```css
/* Hacemos que los elementos se adapten */
.container {
  display: flex;
  flex-wrap: wrap; /* Los elementos se pueden mover a una nueva línea si no caben */
}
```

### 🛠️ Propiedades Técnicas

1. **flex-direction**: Define la dirección del eje principal.
   - `row`: Los elementos se organizan en una fila.
   - `column`: Los elementos se organizan en una columna.

2. **flex-wrap**: Permite que los elementos "salten" a una nueva línea si no hay suficiente espacio.
   - `wrap`: Los elementos se ajustan en varias filas o columnas.

3. **justify-content**: Controla cómo se distribuyen los elementos en el eje principal.
   - `flex-start`: Los elementos se alinean al inicio.
   - `center`: Los elementos se centran en el contenedor.

4. **align-items**: Controla cómo se alinean los elementos en el eje cruzado.
   - `flex-start`: Los elementos se alinean al inicio del eje cruzado.
   - `center`: Los elementos se centran a lo largo del eje cruzado.

---

### 🌱 Un Ejemplo Práctico

```html
<div class="container">
  <div>Elemento 1</div>
  <div>Elemento 2</div>
  <div>Elemento 3</div>
</div>
```

```css
.container {
  display: flex;
  flex-direction: row; /* Organiza los elementos en una fila */
  justify-content: space-between; /* Espacio igual entre los elementos */
  align-items: center; /* Alinea los elementos verticalmente al centro */
}
```

En este caso, **los tres elementos se organizarán horizontalmente** en una fila. Tendrán espacio igual entre ellos y estarán centrados verticalmente.

### ⚠️ Cuidado con el Reordenamiento

Si cambias el orden visual con propiedades como `row-reverse`, los elementos parecerán moverse visualmente, pero **el orden lógico en el DOM no cambia**. Esto puede causar problemas de accesibilidad, especialmente para lectores de pantalla.

```css
/* Los elementos se muestran en orden inverso */
.container {
  display: flex;
  flex-direction: row-reverse;
}
```

---

## 🎯 Analogía Final

Piensa en Flexbox como un grupo de amigos que entran en una foto grupal. Si hay espacio, se acomodan tranquilamente, pero si hay menos espacio, algunos se acercan o hacen espacio para otros, y si es necesario, se forman varias filas. ¡Así de flexible es Flexbox!

---

## 🎓 Conceptos Clave:

- **Eje Principal**: La dirección en la que los elementos se organizan (puede ser horizontal o vertical).
- **Eje Cruzado**: El eje perpendicular al principal, donde también puedes alinear elementos.
- **flex-wrap**: Permite que los elementos se ajusten a una nueva fila o columna si no caben en una sola línea.

---

# CSS Grid: Organizando Elementos en una Cuadrícula

## Introducción
El diseño de **encabezado, barra lateral, cuerpo y pie de página** es uno de los más comunes en el diseño web. Imagina una página con un encabezado que contiene un logo y el menú de navegación, una barra lateral con enlaces o información adicional, y un área principal que muestra el contenido de un artículo. A lo largo del tiempo, se han utilizado diferentes enfoques para lograr este diseño, pero **CSS Grid** ha simplificado considerablemente la creación de este tipo de estructuras. 

CSS Grid permite crear diseños bidimensionales, organizando elementos en **filas y columnas** de manera flexible y precisa. 

## Concepto General
CSS Grid es ideal porque combina lo mejor de los diseños con tamaños intrínsecos y extrínsecos. Esto significa que puedes definir el tamaño de las columnas y filas según el contenido o según el espacio disponible. La cuadrícula organiza los elementos en un contenedor dividiendo el espacio en celdas, lo que facilita posicionar elementos de forma controlada o dejar que el navegador los posicione automáticamente.

## ¿Qué es una cuadrícula?
Una **cuadrícula** en CSS se define al crear filas y columnas. Los elementos hijos del contenedor de la cuadrícula (o **grid container**) se colocan automáticamente en las celdas generadas o pueden ser posicionados manualmente.

### Terminología de CSS Grid
Para entender CSS Grid, es importante familiarizarse con algunos términos clave:

- **Líneas de cuadrícula**: Son las líneas invisibles que delimitan las filas y columnas. Por ejemplo, si tienes una cuadrícula con 4 columnas, tendrás 5 líneas de columna.
  
  - *Analogía*: Piensa en las líneas de cuadrícula como las líneas de un cuaderno cuadriculado. Las líneas te ayudan a ubicar elementos de manera precisa.

- **Pistas de cuadrícula (Grid Tracks)**: El espacio entre dos líneas de cuadrícula se denomina "pista". Puedes tener pistas de columna o de fila.

  - *Analogía*: Imagina una estantería con repisas (las pistas) entre cada soporte vertical (las líneas de cuadrícula). Los objetos (elementos) se colocan en las repisas.

- **Celda de cuadrícula**: Es el área más pequeña en una cuadrícula, formada por la intersección de una fila y una columna.

  - *Analogía*: Una celda en CSS Grid es como una celda en una hoja de cálculo, donde cada celda puede contener datos (elementos).

- **Área de la cuadrícula**: Se refiere a un grupo de celdas que abarcan varias filas y columnas.

  - *Analogía*: Piensa en un edificio de oficinas, donde una "área" es un espacio abierto que ocupa varias oficinas (celdas).

- **Brechas (Gaps)**: Son los espacios vacíos entre las pistas de la cuadrícula. Aunque no puedes colocar elementos directamente en ellos, ayudan a distribuir los elementos de manera ordenada.

  - *Analogía*: Son como los pasillos entre las repisas de una estantería. No colocas cosas ahí, pero permiten que los objetos estén organizados y accesibles.

## Implementando CSS Grid

```css
.container {
  display: grid;
  grid-template-columns: 5em 100px 30%;
  grid-template-rows: 200px auto;
  gap: 10px;
}
```

En este ejemplo, hemos creado una cuadrícula con tres columnas, cada una con un tamaño diferente (em, px, y %), y dos filas. La propiedad `gap` define el espacio entre las filas y columnas.

### Explorando en el Navegador
Puedes usar las **Herramientas para Desarrolladores** en Chrome para visualizar y depurar las cuadrículas. Selecciona un contenedor con `display: grid`, y verás las líneas y celdas resaltadas, lo que te permite entender mejor cómo se organizan los elementos.

## Palabras Clave de Tamaño Intrínseco
CSS Grid incluye palabras clave para ajustar el tamaño de las pistas según el contenido:

- **min-content**: Define la pista tan pequeña como sea posible, sin cortar el contenido.
- **max-content**: La pista se expande para mostrar todo el contenido en una sola línea.
- **fit-content()**: Similar a `max-content`, pero puedes limitar el tamaño máximo.

### Ejemplo de Palabras Clave de Tamaño Intrínseco:

```css
.container {
  display: grid;
  grid-template-columns: min-content max-content fit-content(10em);
}
```

En este ejemplo, las tres columnas usan diferentes métodos de ajuste de tamaño.

## La Unidad `fr`
La unidad **fracción** (`fr`) en CSS Grid permite distribuir el espacio disponible entre las columnas o filas de manera proporcional.

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
}
```

En este caso, la segunda columna ocupa el doble de espacio que las otras dos.

### Analogía:
La unidad `fr` es como dividir una pizza. Si asignas `1fr` a una persona y `2fr` a otra, la segunda recibirá el doble de porciones.

## Función `minmax()`
La función **`minmax()`** te permite definir un tamaño mínimo y máximo para las pistas de la cuadrícula.

```css
.container {
  display: grid;
  grid-template-columns: minmax(100px, 1fr);
}
```

Aquí, la columna tendrá un tamaño mínimo de 100px y ocupará el espacio restante (1fr) si es posible.

### Analogía:
Imagina una goma elástica que tiene un tamaño mínimo de 100px, pero puede estirarse hasta llenar el espacio disponible.

## Función `repeat()`
Si necesitas crear varias columnas o filas repetidas, puedes usar la función **`repeat()`**.

```css
.container {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
}
```

Esto creará 12 columnas con tamaños iguales.

### Analogía:
Es como pedir una docena de facturas; todas tienen el mismo tamaño y se acomodan perfectamente en la bandeja.

## Auto-fill y Auto-fit
Con **auto-fill** y **auto-fit**, puedes crear tantas columnas como quepan en el contenedor sin especificar un número fijo de columnas.

```css
.container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
}
```

Esto crea tantas columnas como quepan, con un tamaño mínimo de 200px.

### Analogía:
Piensa en llenar una caja con pelotas de tenis. Pones tantas como caben, pero cada una mantiene un tamaño mínimo.

---

## Conclusión
CSS Grid te ofrece un control total sobre la disposición de los elementos en filas y columnas. Con herramientas como `fr`, `minmax()`, y `repeat()`, puedes crear diseños complejos y flexibles con un código limpio y fácil de mantener. Aprovecha la visualización de cuadrículas en las herramientas de desarrollo para comprender mejor cómo se distribuyen los elementos.

# Números de Línea Negativos en CSS Grid

### Introducción

Imagina que estás jugando con un tablero de ajedrez. Ese tablero representa una **cuadrícula explícita**, la cual has definido y tiene un tamaño específico. Cada pieza que colocas es un **elemento** en esa cuadrícula. Ahora, ¿qué sucede si necesitas mover una pieza fuera del tablero? El tablero no desaparecerá; en cambio, se **expandirá** para dar espacio a la pieza, creando una **cuadrícula implícita**.

Así es como funciona CSS Grid: cuando defines las **filas** y **columnas** de tu diseño (grid-template-rows y grid-template-columns), estás estableciendo tu **cuadrícula explícita**. Pero si necesitas colocar un elemento fuera de esos límites, CSS creará una cuadrícula adicional (cuadrícula implícita) para acomodar ese elemento.

### Números de Línea Negativos: ¿Qué son?

Cuando defines una cuadrícula, las **líneas** que la componen tienen números. Generalmente, empiezan desde el 1 y continúan en el sentido de lectura. Pero, ¿qué pasaría si quisieras hacer algo más flexible, como extender un elemento desde la primera línea hasta la última, sin importar cuántas filas o columnas haya? Aquí entran los **números de línea negativos**.

Piensa en las líneas de la cuadrícula como si fueran las **páginas de un libro**. Normalmente, contarías desde la primera página (1) hasta la última (digamos 100). Sin embargo, podrías empezar a contar desde la última página hacia atrás, usando números negativos. Si quieres estirar un elemento desde la primera hasta la última línea de una cuadrícula, podrías usar `grid-column: 1 / -1`. El número -1 siempre representa la **última línea** de la cuadrícula.

```css
.grid-container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}

.grid-item {
    grid-column: 1 / -1;
}
```

### Analogía: La Mesa de Noche
Imagina que tienes una mesa de noche con tres cajones. Cada cajón representa una fila de la cuadrícula. Si quisieras que un objeto (como una lámpara) se extienda a través de toda la mesa de noche, ocuparía todos los cajones. En términos de CSS Grid, esto se traduciría como `grid-row: 1 / -1`, es decir, desde el **primer** hasta el **último** cajón.

### Controlando la Cuadrícula Implícita

Cuando trabajas con CSS Grid, puedes encontrarte con elementos que "se salen" de la cuadrícula explícita. En estos casos, el navegador automáticamente ajusta el tamaño de las filas o columnas nuevas que crea. Esto puede controlarse usando propiedades como `grid-auto-rows` y `grid-auto-columns`.

Por ejemplo, puedes especificar que las filas implícitas tengan un tamaño mínimo de `10em` y que crezcan automáticamente según el contenido.

```css
.container {
    display: grid;
    grid-auto-rows: minmax(10em, auto);
}
```

### Analogía: El Estante que Crece

Piensa en un estante donde guardas libros. Si compras más libros de los que caben en los estantes que ya tienes, puedes agregar más estantes automáticamente. Eso es lo que hace `grid-auto-rows`: define el **tamaño mínimo** de estos nuevos "estantes" (o filas implícitas) y les permite crecer si es necesario.

### Nombres para las Líneas

En lugar de usar números para las líneas de la cuadrícula, puedes **nombrarlas** para hacer tu código más legible y fácil de mantener. Esto es como etiquetar tus cajones con nombres: "Documentos", "Libros", "Ropa", en lugar de llamarlos "Cajón 1", "Cajón 2", etc.

```css
.container {
    display: grid;
    grid-template-columns:
      [main-start aside-start] 1fr
      [aside-end content-start] 2fr
      [content-end main-end]; /* diseño de dos columnas */
}

.sidebar {
    grid-column: aside-start / aside-end;
}

footer {
    grid-column: main-start / main-end;
}
```

### Áreas de la Cuadrícula

CSS Grid también permite nombrar **áreas** completas de la cuadrícula, lo que hace más fácil visualizar cómo se verá el diseño. Piensa en esto como si estuvieras organizando tu casa: podrías etiquetar áreas como "Cocina", "Sala", "Dormitorio", etc., y cada una ocupará un espacio claramente definido.

```css
.container {
    display: grid;
    grid-template-areas:
        "header header header header"
        "sidebar content content content"
        "sidebar footer footer footer";
}
```

Cada área tiene un nombre específico, y cuando los defines, puedes colocar fácilmente los elementos en esas áreas. 

```css
header {
    grid-area: header;
}

.sidebar {
    grid-area: sidebar;
}

.content {
    grid-area: content;
}

footer {
    grid-area: footer;
}
```

### Propiedades Abreviadas

Finalmente, CSS Grid incluye **propiedades abreviadas** como `grid-template` y `grid`. Estas te permiten escribir menos código al establecer filas, columnas y áreas al mismo tiempo.

```css
.container {
    display: grid;
    grid-template:
      "header header header" minmax(150px, auto)
      "sidebar content content" auto
      "sidebar footer footer" auto / 1fr 1fr 1fr;
}
```

Esta propiedad es muy útil cuando quieres ahorrar tiempo y simplificar la estructura de tu código.

---

# Propiedades Lógicas en CSS

## Podcast de CSS - 012: Propiedades lógicas 

Imagina que estás organizando una fiesta de cumpleaños. Tienes una mesa decorada con globos y un pastel, y en un rincón, hay una caja de sorpresas con regalos. En este escenario, la forma en que organizas y distribuyes los elementos es crucial para que la fiesta sea un éxito.

De manera similar, en el mundo del desarrollo web, la manera en que organizamos y posicionamos los elementos en una página web puede afectar su usabilidad y apariencia. Aquí es donde entran las **propiedades lógicas** en CSS.

### Un Problema Común

Un patrón de interfaz de usuario muy común es tener una etiqueta de texto con un ícono complementario. Piensa en un letrero que dice "¡Bienvenido!" y tiene un ícono de mano levantada a su izquierda. Sin embargo, este diseño solo funciona si el texto se lee de izquierda a derecha. Si decides cambiar el idioma a árabe, el ícono se posicionará en el lugar incorrecto, justo contra el texto.

Aquí es donde las **propiedades lógicas** vienen al rescate, proporcionando una solución que se adapta automáticamente según el idioma y la dirección del texto. Son como una brújula que siempre te indica la dirección correcta, sin importar cómo gire el mapa.

### Terminología

Las propiedades físicas (superior, derecha, inferior, izquierda) son como una rosa de los vientos que nos dice dónde está cada punto de referencia en nuestro mapa. Por otro lado, las propiedades lógicas se refieren a los bordes de un elemento en relación con el flujo de contenido. Así, si cambiamos la dirección del texto, estas propiedades también cambian. Esto nos brinda mayor flexibilidad al definir estilos para nuestras interfaces.

### Flujo de Bloques y Flujo Intercalado

- **Flujo de Bloques**: Imagina que estás leyendo un libro en inglés. La historia avanza de arriba hacia abajo, como si los párrafos fueran bloques apilados uno sobre otro. Este es el **flujo de bloques**.

- **Flujo Intercalado**: Ahora, piensa en cómo escribes una frase en inglés. El flujo es de izquierda a derecha. Si cambias a árabe, este flujo se convierte en derecha a izquierda. Esto es el **flujo intercalado**. 

Puedes controlar cómo se presenta el texto usando la propiedad `writing-mode`. Así, puedes crear documentos que se adapten a diferentes direcciones de lectura, al igual que tu mesa de fiesta se puede reorganizar según la cantidad de invitados.

### Relación de Flujo

Históricamente, en CSS, aplicábamos propiedades como `margin-top` para referirnos a la parte superior de un elemento. Pero con las propiedades lógicas, `margin-top` se convierte en `margin-block-start`. Esto significa que, independientemente del idioma y la dirección del texto, las reglas de margen se aplican correctamente.

### Tamaño de Elementos

Para evitar que un elemento se extienda demasiado, puedes definir un tamaño máximo:

```css
.my-element {
  max-width: 150px;
  max-height: 100px;
}
```

Usando propiedades lógicas, la regla se vería así:

```css
.my-element {
  max-inline-size: 150px;
  max-block-size: 100px;
}
```

### Inicio y Finalización

En lugar de usar direcciones (arriba, derecha, abajo, izquierda), utilizamos `inicio` y `fin`. Por ejemplo, para alinear texto a la derecha, en lugar de:

```css
p {
  text-align: right;
}
```

Podemos usar:

```css
p {
  text-align: end;
}
```

Esto se adapta automáticamente a la dirección de lectura.

### Espaciado y Posicionamiento

Las propiedades lógicas para `margin`, `padding` e `inset` facilitan el posicionamiento de elementos en diferentes modos de escritura. Por ejemplo, en lugar de usar:

```css
.my-element {
  padding-top: 2em;
  padding-bottom: 2em;
  margin-left: 2em;
  position: relative;
  top: 0.2em;
}
```

Usamos:

```css
.my-element {
  padding-block-start: 2em;
  padding-block-end: 2em;
  margin-inline-start: 2em;
  position: relative;
  inset-block-start: 0.2em;
}
```

Esto hace que el espaciado se adapte según la dirección del texto.

### Bordes

También puedes usar propiedades lógicas para bordes. Por ejemplo, en lugar de:

```css
.my-element {
  border-bottom: 1px solid red;
  border-right: 1px solid red;
}
```

Podemos usar:

```css
.my-element {
  border-block-end: 1px solid red;
  border-inline-end: 1px solid red;
}
```

### Nuevas Unidades

Las propiedades lógicas introducen dos nuevas unidades: `vi` y `vb`. Estas se basan en el tamaño del viewport y se adaptan a la dirección de lectura.

### Uso Pragmático de Propiedades Lógicas

Las propiedades lógicas no son solo para internacionalización. También producen interfaces de usuario más versátiles. Por ejemplo, si tienes un gráfico con etiquetas en los ejes, puedes usar propiedades lógicas para aplicar márgenes de manera consistente, sin importar la dirección del texto.

### Resolviendo el Problema del Ícono

Regresando a nuestro ejemplo del ícono y el texto, para que el espaciado entre ellos sea adecuado en todas las direcciones de lectura, usamos:

```css
p {
  display: inline-flex;
  align-items: center;
}

p svg {
  width: 1.2em;
  height: 1.2em;
  margin-inline-end: 0.5em;
  flex: none;
}
```

---

# Espaciado en CSS

Supongamos que tienes una colección de tres cajas, apiladas una encima de la otra, y queremos que haya espacio entre ellas. ¿Cómo podrías lograr eso en CSS?

![Tres cuadros apilados con una flecha hacia abajo](url_de_la_imagen)

La propiedad `margin` podría ofrecerte lo que necesitas, pero también puede agregar espacios adicionales que no deseas. Por ejemplo, ¿cómo te orientas solo al espacio entre cada uno de esos elementos? Algo como `gap` podría ser más apropiado en este caso. Hay muchas maneras de ajustar el espaciado dentro de una IU, cada uno con sus propias fortalezas y advertencias.

## Espacio HTML

El HTML proporciona algunos métodos para espaciar los elementos. Los elementos `<br>` y `<hr>` te permiten espaciar elementos en la dirección del bloque, que, si usas un idioma de origen latino, es de arriba a abajo.

- Si usas un elemento `<br>`, se creará un salto de línea como si presionaras la tecla **Intro** en un procesador de texto.
  
- `<hr>` crea una línea horizontal con espacio a ambos lados, conocida como **margin**.

Además de usar elementos HTML, las entidades HTML pueden crear espacio. Una entidad HTML es una cadena reservada de caracteres que el navegador reemplaza por entidades de caracteres. Por ejemplo, si escribieras `&copy;` en tu archivo HTML, se convertiría en un carácter ©. La entidad `&nbsp;` se convierte en un carácter de espacio de no separación, que proporciona un espacio intercalado. Sin embargo, ten cuidado, porque el aspecto de no ruptura de este carácter une los dos elementos, lo que puede provocar comportamientos extraños.

**Nota:** Usa elementos HTML para agregar espacio solo cuando estos ayuden a comprender el documento. Por ejemplo, un elemento `<hr>` no solo agrega espacio, sino que crea una separación lógica de dos fragmentos de contenido. Si solo deseas una línea con espacio a su alrededor, puede ser más adecuado agregar un borde con CSS.

## Margen

Si deseas agregar espacio al exterior de un elemento, usas la propiedad `margin`. El margen es como agregar un cojín alrededor del elemento. La propiedad `margin` es la abreviatura de `margin-top`, `margin-right`, `margin-bottom` y `margin-left`.

![Diagrama de las cuatro áreas principales del modelo de caja](url_de_la_imagen)

La abreviatura `margin` aplica propiedades en un orden particular: arriba, derecha, abajo e izquierda. Puedes recordar estos errores: **TROUBLe**.

- La palabra "Problemas" corriendo hacia abajo con T, R, B y L que se extiende a la parte superior, a la derecha, a la parte inferior y a la izquierda.

La abreviatura `margin` también se puede usar con uno, dos o tres valores. Agregar un cuarto valor te permite configurar cada lado individual. Se aplican de la siguiente manera:

- Un valor se aplicará a todos los lados. (`margin: 20px`)
- Dos valores: el primer valor se aplicará a la parte superior e inferior, y el segundo valor se aplica a la izquierda y a la derecha. (`margin: 20px 40px`)
- Tres valores: el primero es top, el segundo valor es left y right, y el tercer valor es bottom. (`margin: 20px 40px 30px`).

El margen puede definirse con una longitud, porcentaje o valor automático, como `1em` o `20%`. Si usas un porcentaje, el valor se calculará en función del ancho del bloque contenedor de tu elemento. Esto significa que, si el bloque contenedor de tu elemento tiene un ancho de 250px y tu elemento tiene un valor `margin` de 20%: cada lado de tu elemento tendrá un margen calculado de 50px.

También puedes usar un valor de `auto` para el margen. Para los elementos de nivel de bloque con un tamaño restringido, un margen de `auto` ocupará espacio disponible en la dirección en la que se aplique. Un buen ejemplo es el módulo **Flexbox**, donde los elementos se alejan entre sí.

```css
.wrapper {
    max-width: 400px;
    margin: 0 auto;
}
```

Aquí, el margen se quita de los lados superior e inferior (bloqueo), y `auto` comparte el espacio entre los lados izquierdo y derecho (intercalados).

**Nota:** En el módulo anterior sobre propiedades lógicas, aprendiste que, en lugar de especificar `margin-top`, `margin-right`, `margin-bottom` y `margin-left`, puedes usar `margin-block-start`, `margin-inline-end`, `margin-block-end` y `margin-inline-start`.

## Margen Negativo

Los valores negativos también se pueden usar para el margen. En lugar de agregar espacio entre elementos del mismo nivel, reducirá el espacio entre ellos. Esto puede dar como resultado la superposición de elementos si declaras un valor negativo superior al espacio disponible.

## Contracción de Margen

La contracción del margen es un concepto engañoso, pero es algo con lo que te encontrarás muy comúnmente cuando compiles interfaces. Supongamos que tienes dos elementos, un encabezado y un párrafo, ambos tienen un margen vertical:

```html
<article>
  <h1>My heading with teal margin</h1>
  <p>A paragraph of text that has blue margin on it, following the heading with margin.</p>
</article>
```

```css
h1 {
    margin-bottom: 2rem;
}

p {
    margin-top: 3rem;
}
```

A primera vista, se te perdona pensar que el párrafo estará separado del encabezado 5em porque la combinación de 2rem y 3rem se calcula como 5rem. Sin embargo, debido a que el margen vertical se contrae, el espacio en realidad es 3rem.

La contracción de márgenes funciona seleccionando el valor más grande de dos elementos contiguos con un margen vertical en los lados contiguos. La parte inferior de `h1` se une con la parte superior de `p`, para que se seleccione el valor más alto del margen inferior de `h1` y el margen superior de `p`. Si `h1` tuviera un 3.5rem de margen inferior, el espacio entre ambos sería 3.5rem porque es mayor que 3rem. Solo los márgenes de bloqueo se contraen, no los márgenes intercalados (horizontales).

**Nota:** Este comportamiento se remonta a cuando la Web solo consistía en documentos. Los márgenes que se contraen ayudan a establecer un espaciado constante entre los elementos sin crear accidentalmente grandes espacios entre los elementos que también tienen un margen definido. La contracción de márgenes también ayuda con los elementos vacíos. Si tienes un párrafo con un margen inferior y superior de 20px, solo creará 20px de espacio, no 40px. Sin embargo, si se agrega algo dentro de este elemento, incluido padding, su margen ya no se contraerá y se tratará como cualquier cuadro con contenido.

## Verifica tus conocimientos

Pon a prueba tus conocimientos sobre la contracción de los márgenes:

Si dos elementos apilados uno encima del otro tienen 20 px de margen superior y 30 px de margen inferior, ¿cuánto espacio habrá entre ellos?

- 40 px
- 30 px
- 20 px
- 10 px

### Cómo evitar la contracción del margen

Si haces que un elemento esté absolutamente posicionado (usando `position: absolute`), el margen ya no se contraerá. El margen tampoco se contraerá si también usas la propiedad **float**.

Si tienes un elemento sin margen entre dos elementos con margen de bloque, el margen tampoco se contraerá, porque los dos elementos con margen de bloque ya no son hermanos adyacentes: solo son elementos del mismo nivel.

En la lección de diseño, aprendiste que los contenedores de **flexbox** y **grid** son muy similares a los contenedores de bloques pero manejan sus elementos secundarios de forma muy diferente. Este también es el caso de la contracción de los márgenes.

Si tomamos el ejemplo original de la lección y aplicamos **flexbox** con dirección de columna, los márgenes se combinan, en lugar de contraerse. Esto puede proporcionar previsibilidad con el trabajo de diseño, para los que se diseñaron los contenedores **flexbox** y **grid**.

## Relleno

En lugar de crear espacio en el exterior de la caja, como lo hace `margin`, la propiedad `padding` crea espacio en el interior del cuadro: como el aislamiento.

![Una caja con flechas que apuntan hacia adentro para mostrar que el relleno se encuentra dentro de una caja](url_de_la_imagen)

Según el modelo de caja que uses, como ya lo vimos en la lección sobre el modelo de caja, el `padding` también puede afectar las dimensiones generales del elemento.

La propiedad `padding` es la abreviatura de `padding-top`, `padding-right`, `padding-bottom` y `padding-left`. Al igual que `margin`, `padding` también tiene propiedades lógicas: `padding-block-start`, `padding-inline-end`, `padding-block-end` y `padding-inline-start`.

### Posicionamiento

También se aborda en el módulo sobre diseño. Si estableces un valor para `position` distinto de **static**, puedes espaciar elementos con

 márgenes y relleno y hacer que su comportamiento sea diferente, como hemos mencionado.

Si usas `absolute` o `fixed`, puedes dejar que las propiedades `margin` y `padding` se acumulen entre sí, permitiéndote controlar el espacio total en tu interfaz.

## Espaciado dentro de un contenedor flexible

Por último, cuando se utilizan contenedores flexibles y de cuadrícula, existen propiedades adicionales disponibles para controlar el espaciado, como `gap`, que permite un espaciado más efectivo entre elementos, sin tener en cuenta márgenes o rellenos individuales.

---

## Resumen

1. **HTML**: Utiliza elementos HTML con cuidado para espaciar contenido.
2. **Margen**: `margin` agrega espacio exterior alrededor de los elementos.
3. **Relleno**: `padding` agrega espacio interior dentro de un elemento.
4. **Contracción de márgenes**: Los márgenes verticales de los elementos se combinan para evitar espacios innecesarios.
5. **Contenedores flexibles**: Utiliza `gap` para espaciado entre elementos sin modificar los márgenes.

---

# Seudoelementos en CSS

## Introducción

Si tienes un artículo de contenido y quieres que la primera letra sea mucho más grande, ¿cómo lo logras?

> **Ejemplo:**
> Unos párrafos de texto con una gorra azul.

En CSS, puedes usar el seudoelemento `::first-letter` para lograr este tipo de detalle de diseño.

```css
p::first-letter {
  color: blue;
  float: left;
  font-size: 2.6em;
  font-weight: bold;
  line-height: 1;
  margin-inline-end: 0.2rem;
}
```

Un seudoelemento es como agregar o orientar un elemento adicional sin tener que agregar más HTML. En esta solución de ejemplo, con `::first-letter`, es uno de muchos seudoelementos. Tienen una variedad de roles. En esta lección, aprenderás qué seudoelementos están disponibles y cómo puedes usarlos.

---

## `::before` y `::after`

Tanto el `::before` como el `::after` crean un elemento secundario dentro de un elemento solo si defines una propiedad `content`. 

> **Analogía:** Imagina que estás colocando un cartel en la puerta de una tienda que dice "Abierto". No necesitas construir un nuevo marco, solo colocas una hoja de papel que dice "Abierto" encima de la puerta. Eso es lo que hacen `::before` y `::after`.

```css
.my-element::before {
    content: "";
}

.my-element::after {
    content: "";
}
```

`content` puede ser cualquier cadena (incluso una vacía), pero ten en cuenta que es probable que el lector de pantalla anuncie cualquier cosa que no sea una cadena vacía. Puedes agregar una imagen URL para insertar una imagen con sus dimensiones originales, por lo que no podrás cambiar su tamaño. También puedes insertar un contador.

> **Término clave:** Puedes crear un contador con nombre y, luego, incrementarlo según su posición en el flujo del documento. Hay todo tipo de contextos en los que pueden ser muy útiles, como la numeración automática de un esquema.

Una vez que se crea un elemento `::before` o `::after`, puedes personalizarlo como quieras, sin límites. Solo puedes insertar un elemento `::before` o `::after` en un elemento que acepte elementos secundarios (elementos con un árbol de documentos), por lo que elementos como `<img />`, `<video>` y `<input>` no funcionarán. Sin embargo, `input[type="checkbox"]` es una excepción, y se permite tener pseudoelementos secundarios.

---

## `::first-letter`

Conocimos este seudoelemento al principio de la lección. Ten en cuenta que no todas las propiedades de CSS se pueden utilizar al orientar los anuncios. `::first-letter` permite las siguientes propiedades:

- `color`
- Propiedades de `background` (como `background-image`)
- Propiedades de `border` (como `border-color`)
- `float`
- Propiedades de `font` (como `font-size` y `font-weight`)
- Propiedades de `text` (como `text-decoration` y `word-spacing`)

```css
p::first-letter {
  color: goldenrod;
  font-weight: bold;
}
```

**Nota:** Solo puedes usar `::first-letter` en contenedores de bloques. Por lo tanto, no funcionará si intentas agregarlo a un elemento que tenga `display: inline`.

---

## `::first-line`

El seudoelemento `::first-line` te permitirá dar estilo a la primera línea de texto solo si el elemento con `::first-line` aplicado tiene un valor `display` de block, inline-block, list-item, table-caption o table-cell.

```css
p::first-line {
  color: goldenrod;
  font-weight: bold;
}
```

Como el seudoelemento `::first-letter`, solo puedes usar un subconjunto de propiedades de CSS:

- `color`
- Propiedades de `background`
- Propiedades de `font`
- Propiedades de `text`

---

## `::backdrop`

Si tienes un elemento que se presenta en modo de pantalla completa, como `<dialog>` o `<video>`, puedes darle estilo al fondo (el espacio entre el elemento y el resto de la página) con el pseudoelemento `::backdrop`.

```css
video::backdrop {
  background-color: goldenrod;
}
```

---

## `::marker`

La `::marker` te permite aplicar diseño a la viñeta o al número de un elemento de la lista o a la flecha de un elemento `<summary>`.

```css
::marker {
  color: hotpink;
}

ul::marker {
  font-size: 1.5em;
}

ol::marker {
  font-size: 1.1em;
}

summary::marker {
  content: '\002B'; /* Plus symbol */
}

details[open] summary::marker {
  content: '\2212'; /* Minus symbol */
}
```

Solo se admite un pequeño subconjunto de propiedades de CSS para `::marker`:

- `color`
- `content`
- `white-space`
- Propiedades de `font`
- Propiedades de `animation` y `transition`

---

## `::selection`

El seudoelemento `::selection` te permite darle estilo al texto seleccionado.

```css
::selection {
  background: green;
  color: white;
}
```

Este seudoelemento se puede usar para aplicar estilo a todo el texto seleccionado. También se puede combinar con otros selectores para lograr un estilo de selección más específico.

```css
p:nth-of-type(2)::selection {
  background: darkblue;
  color: yellow;
}
```

Al igual que con otros seudoelementos, solo se permite un subconjunto de propiedades de CSS:

- `color`
- `background-color`, pero no `background-image`
- Propiedades de `text`

---

## `::placeholder`

La `::placeholder` te permite darle estilo al texto que aparece como sugerencia en un campo de entrada de formulario, como `<input>` con un atributo `placeholder`.

```css
input::placeholder {
  color: darkcyan;
}
```

`::placeholder` solo admite un subconjunto de reglas de CSS:

- `color`
- Propiedades de `background`
- Propiedades de `font`
- Propiedades de `text`

**Nota:** Un `placeholder` no es `<label>` y no se debe usar en lugar de un `<label>`. Los elementos del formulario deben estar etiquetados. De lo contrario, no se podrá acceder a ellos.

---

## `::cue`

Finalmente, en este recorrido por los seudoelementos, llegamos al pseudoelemento `::cue`. Esto te permite diseñar las indicaciones WebVTT, que son las leyendas de un elemento `<video>`.

También puedes pasar un selector a un `::cue`, lo que te permite aplicar ajustes de estilo a elementos específicos dentro de un subtítulo.

```css
video::cue {
  color: yellow;
}

video::cue(b) {
  color: red;
}

video::cue(i) {
  color: lightpink;
}
```

---

## Conclusión

Los seudoelementos son herramientas poderosas en CSS que te permiten agregar estilo y funcionalidad a tus elementos HTML sin necesidad de alterar la estructura del documento. Usar seudoelementos de manera efectiva puede ayudarte a lograr un diseño más atractivo y accesible en tus proyectos de frontend.

---

# Seudoclases en CSS

Supongamos que tienes un formulario de registro por correo electrónico, y quieres que el campo del formulario de correo electrónico tenga un borde rojo si contiene una dirección de correo electrónico no válida. ¿Cómo puedes hacerlo? Puedes usar una seudoclase `:invalid` de CSS, que es una de las muchas seudoclases proporcionadas por el navegador.

Una **seudoclase** te permite aplicar estilos en función de cambios de estado y factores externos. Esto significa que tu diseño puede reaccionar a las entradas del usuario, como una dirección de correo electrónico no válida. Estos se abordan en el módulo de selectores, y en este módulo las analizaremos en mayor detalle.

A diferencia de los seudoelementos, que se utilizan para dar estilo a partes específicas de un elemento, las seudoclases se conectan a **estados específicos** en los que puede estar un elemento.

## Estados Interactivos

Las siguientes seudoclases se aplican debido a una interacción que un usuario tiene con tu página.

### `:hover`

**Navegadores compatibles**

- Chrome: 1. (1)
- Edge: 12. (12)
- Firefox: 1. (1)
- Safari: 2. (2)

**Origen**: Si un usuario tiene un dispositivo apuntador, como un mouse o un panel táctil, y lo coloca sobre un elemento, puedes conectarte a ese estado con `:hover` para aplicar estilos. Esta es una manera útil de sugerir que se puede interactuar con un elemento.

### `:active`

**Navegadores compatibles**

- Chrome: 1. (1)
- Edge: 12. (12)
- Firefox: 1. (1)
- Safari: 1. (1)

**Origen**: Este estado se activa cuando un elemento está en interacción activa, como un clic, antes de que se libere. Si se utiliza un dispositivo apuntador, este estado se da cuando comienza el clic y aún no se ha liberado.

### `:focus`, `:focus-within` y `:focus-visible`

**Navegadores compatibles**

- Chrome: 1. (1)
- Edge: 12. (12)
- Firefox: 1. (1)
- Safari: 1. (1)

**Origen**: Si un elemento puede recibir el foco, como un `<button>`, puedes reaccionar a ese estado con la seudoclase `:focus`. También puedes reaccionar si un elemento secundario de tu elemento recibe el foco con `:focus-within`. 

Los elementos enfocables, como los botones, mostrarán un anillo de enfoque cuando estén en foco. Esto puede presentar un problema de accesibilidad si se elimina el anillo de enfoque por completo. Puedes usar `:focus-visible` para mostrar un estilo de foco cuando un elemento recibe el foco a través del teclado.

```css
button:focus {
    outline: none;
}

button:focus-visible {
    outline: 1px solid black;
}
```

### `:target`

**Navegadores compatibles**

- Chrome: 1. (1)
- Edge: 12. (12)
- Firefox: 1. (1)
- Safari: 1.3

**Origen**: La `:target` selecciona un elemento que tiene un id que coincide con un fragmento de URL. Por ejemplo, si tienes el siguiente código HTML:

```html
<article id="content">
    …
</article>
```

Puedes adjuntar estilos a ese elemento si la URL contiene `#content`.

```css
#content:target {
    background: yellow;
}
```

Esto es útil para resaltar áreas que podrían haberse vinculado específicamente como el contenido principal de un sitio web.

## Estados Históricos

### `:link` y `:visited`

**Navegadores compatibles**

- Chrome: 1. (1)
- Edge: 12. (12)
- Firefox: 1. (1)
- Safari: 1. (1)

**Origen**: La `:link` seudoclase se puede aplicar a cualquier elemento `<a>` que tenga un valor `href` que aún no se haya visitado. Por otro lado, puedes definir el estilo de un vínculo que el usuario ya visitó mediante la seudoclase `:visited`. Sin embargo, tienes menos propiedades de CSS para usar con `:visited` por motivos de seguridad.

**Regla LVHA**: El orden es importante al definir estilos de vínculos. Te recomendamos que uses la regla LVHA para definir el estilo de los vínculos con seudoclases en el siguiente orden:

```css
a:link {}
a:visited {}
a:hover {}
a:active {}
```

### Estados del Formulario

Las siguientes seudoclases pueden seleccionar elementos de formulario en los diversos estados en los que pueden estar durante la interacción con ellos.

### `:disabled` y `:enabled`

**Navegadores compatibles**

- Chrome: 1. (1)
- Edge: 12. (12)
- Firefox: 1. (1)
- Safari: 3.1

**Origen**: Puedes usar `:disabled` para seleccionar un elemento de formulario, como `<button>`, si el navegador lo inhabilita. La seudoclase `:enabled` está disponible para el estado opuesto, aunque los elementos del formulario también son `:enabled` de forma predeterminada.

### `:checked` y `:indeterminate`

**Navegadores compatibles**

- Chrome: 1. (1)
- Edge: 12. (12)
- Firefox: 1. (1)
- Safari: 3.1

**Origen**: La `:checked` está disponible cuando un elemento de formulario complementario, como una casilla de verificación o un botón de selección, está marcado. El estado `:checked` es un estado binario (verdadero o falso). Sin embargo, las casillas de verificación tienen un estado intermedio, que se conoce como `:indeterminate`.

### `:placeholder-shown`

**Navegadores compatibles**

- Chrome: 47. (47)
- Edge: 79. (79)
- Firefox: 51. (51)
- Safari: 9. (9)

**Origen**: Si un campo del formulario tiene un atributo `placeholder` y no tiene valor, puedes usar `:placeholder-shown` para adjuntar estilos a ese estado.

## Estados de Validación

**Navegadores compatibles**

- Chrome: 10. (10)
- Edge: 12. (12)
- Firefox: 4. (4)
- Safari: 5. (5)

Puedes responder a la validación del formulario HTML con seudoclases como `:valid`, `:invalid` y `:in-range`. Estas seudoclases son útiles para mostrar a los usuarios si un campo, como un campo de correo electrónico, es válido o no. 

**Nota**: No es una buena idea confiar únicamente en el color para representar los cambios de estado, ya que los usuarios daltónicos y con visión reducida pueden tener dificultades para notar cambios de estado. Es recomendable combinar colores con cambios de texto e íconos para representar visualmente el cambio.

## Selección de Elementos por su Índice, Orden y Casos

Hay un grupo de seudoclases que seleccionan elementos en función de dónde se encuentran en el documento.

### `:first-child` y `:last-child`

**Navegadores compatibles**

- Chrome: 4. (4)
- Edge: 12. (12)
- Firefox: 3. (3)
- Safari: 3.1

**Origen**: Si quieres encontrar el primer o el último elemento, puedes usar `:first-child` y `:last-child`. Estas seudoclases devolverán el primer o el último elemento de un grupo de elementos del mismo nivel.

### `:only-child`

**Navegadores compatibles**

- Chrome: 2. (2)
- Edge: 12. (12)
- Firefox: 1.5
- Safari: 3.1

**Origen**: También puedes seleccionar elementos que no tengan hermanos con la seudoclase `:only-child`.

### `:first-of-type` y `:last-of-type`

**Navegadores compatibles**

- Chrome: 1. (1)
- Edge: 12. (12)
- Firefox: 3.5
- Safari: 3.1

**Origen**: Puedes seleccionar `:first-of-type` y `:last-of-type`, que parecen hacer lo mismo que `:first-child` y `:last-child`, pero con una diferencia clave. Considera el siguiente HTML:

```html
<div class="my-parent">
    <p>A paragraph</p>
    <div>A div</div>
    <div>Another div</div>
</div>
```

Si aplicas el siguiente CSS:

```css
.my-parent div:first-child {
    color: red;
}
```

Ningún elemento se mostrará en rojo porque el primer elemento secundario es un párrafo y no un div. La seudoclase `:first-of-type` es útil en este contexto.

```css
.my-parent div:first-of-type {
    color: red;
}
```

Aunque el primer elemento `<div>` es el segundo elemento secundario, sigue siendo el primero de su tipo dentro del elemento `.my-parent`, por lo que con esta regla, será de color rojo.

### `:nth-child` y `:nth-of-type`

**Navegadores compatibles**

- Chrome

: 4. (4)
- Edge: 12. (12)
- Firefox: 3. (3)
- Safari: 3.1

**Origen**: Las seudoclases `:nth-child` y `:nth-of-type` son útiles para seleccionar elementos en función de su posición dentro de su padre. La seudoclase `:nth-child` puede usar un argumento de tipo fórmula para seleccionar elementos.

**Ejemplo de código**:

```css
/* Selecciona el tercer hijo de cualquier tipo */
li:nth-child(3) {
    background-color: lightgreen;
}

/* Selecciona todos los hijos impares */
li:nth-child(odd) {
    background-color: lightblue;
}

/* Selecciona todos los hijos pares */
li:nth-child(even) {
    background-color: lightpink;
}
```

La seudoclase `:nth-of-type` se puede usar para seleccionar elementos de un tipo específico:

```css
/* Selecciona el segundo párrafo */
p:nth-of-type(2) {
    color: blue;
}
```

### `:not()`

**Navegadores compatibles**

- Chrome: 1. (1)
- Edge: 12. (12)
- Firefox: 1. (1)
- Safari: 1. (1)

**Origen**: La `:not()` seudoclase se puede usar para excluir un elemento específico. Ten en cuenta que solo puedes usar una regla dentro de `:not()`, no puedes incluir combinaciones o grupos de selectores dentro de ella. 

## Conclusión

Las seudoclases te permiten aplicar estilos basados en el estado de un elemento y en su relación con otros elementos. Estas son una excelente manera de hacer que tus diseños sean más interactivos y accesibles para los usuarios. Prueba a aplicar diferentes seudoclases en tus proyectos para explorar todo su potencial.

---

