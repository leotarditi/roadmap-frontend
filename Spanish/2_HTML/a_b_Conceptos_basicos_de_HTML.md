# Descripción general de HTML

HTML, o **lenguaje de marcado de hipertexto**, es como el esqueleto de una página web. Imagina que estás construyendo una casa: necesitas una estructura que le dé forma y soporte a cada habitación, ventana y puerta. En el caso de una página web, HTML es esa estructura que define cómo se organizará y mostrará la información.

## ¿Qué es HTML?

HTML consiste en una serie de **elementos y atributos** que se utilizan para organizar el contenido de una página de manera estructurada. Piensa en los elementos HTML como las distintas habitaciones de una casa: tienes una sala, un baño, una cocina. Cada una tiene un propósito claro, y así es como funcionan los elementos en HTML.

En términos más técnicos, **HTML** describe la estructura de los documentos que se muestran en la web. Estos documentos están compuestos por un **árbol de nodos**, que incluye **elementos HTML** y **nodos de texto**.

## Elementos

Un **elemento HTML** es como una caja que encierra contenido y define cómo se verá o funcionará. Cada elemento está compuesto por **etiquetas**, que actúan como la tapa de esa caja. En HTML, las etiquetas se escriben entre corchetes angulares `< >`, y vienen en pares: una etiqueta de apertura y una de cierre. 

Por ejemplo:
```html
<h1>Bienvenidos a la página</h1>
```

La etiqueta `<h1>` es el encabezado más importante (como el título de una sección). Es como la puerta principal de una casa: todos la ven primero. Lo que está dentro de esas etiquetas es el contenido: en este caso, el texto "Bienvenidos a la página".

### Anidación de elementos

Los elementos también pueden estar **anidados** uno dentro de otro, como si una caja pequeña estuviera dentro de una caja más grande. Es importante cerrar las etiquetas en el orden correcto, para que el navegador (quien "lee" estas cajas) no se confunda. Por ejemplo:

```html
<p>Este es un <strong>texto importante</strong> dentro de un párrafo</p>
```

En este caso, `<p>` es el elemento de párrafo que contiene otro elemento `<strong>`, que hace que parte del texto esté en **negrita**. Es como tener una caja de joyas dentro de un cofre: ambas tienen que cerrarse en el orden correcto para que el contenido esté bien organizado.

## Atributos

Los **atributos** son como las características adicionales de una habitación. Por ejemplo, una ventana puede tener persianas, vidrio antirreflejo, o una cortina. De la misma manera, los atributos en HTML agregan información o comportamientos adicionales a los elementos.

```html
<img src="imagen.jpg" alt="Una imagen descriptiva">
```

En este ejemplo, el atributo `src` le dice al navegador dónde encontrar la imagen, mientras que el atributo `alt` describe la imagen, algo que es útil para motores de búsqueda o personas con discapacidades visuales.

## Elementos vacíos y reemplazados

Algunos elementos no necesitan contenido interno, como `<img>` o `<input>`. Estos se llaman **elementos vacíos** y son como una ventana en la casa: simplemente están ahí, sin contenido dentro, pero cumplen una función muy importante. Además, ciertos elementos se llaman **elementos reemplazados**, como una imagen o un botón de formulario, que son "reemplazados" por algo visible o interactivo en la página.

## Reglas de cierre

Es importante recordar que la mayoría de los elementos deben cerrarse adecuadamente, como cerrar una puerta para mantener la casa ordenada. Sin embargo, algunos elementos (como `<li>` en las listas) pueden funcionar sin ser cerrados explícitamente, pero es una buena práctica hacerlo siempre para evitar problemas de visualización.

# Estructura del Documento HTML

### Imagina que tu HTML es como una Casa

Piensa en una página web como una casa. Para construirla necesitas ciertos componentes básicos que, aunque a veces no sean visibles, son esenciales para que todo funcione correctamente.

1. **<!DOCTYPE html>**: Es como los planos oficiales de la casa. Le dice al navegador cómo debe interpretar el resto del "edificio". Sin estos planos, el navegador podría interpretar mal tu página.
   
   ```html
   <!DOCTYPE html>
   ```

2. **<html>**: Este es el cimiento de la casa. Dentro de esta etiqueta se construye todo lo demás. Aquí es donde se define el lenguaje de tu "edificio", por ejemplo, si está en español o inglés. Así como una casa puede estar en diferentes países, un documento HTML puede estar en diferentes idiomas.

   ```html
   <html lang="es">
   ```

### El techo de la casa: <head>

El `<head>` es como el techo de la casa, no lo ves por dentro, pero tiene funciones importantes. Aquí es donde colocas información sobre la página que no será visible directamente en la pantalla, pero que es crucial para su correcto funcionamiento.

1. **<meta charset="utf-8">**: Es como asegurar que todos los cables y conexiones eléctricas estén en el formato correcto. UTF-8 es el tipo de "cableado" que garantiza que puedas usar cualquier carácter o emoji en tu página.

   ```html
   <meta charset="utf-8">
   ```

2. **<title>**: Este es el nombre de la casa que aparece en la pestaña del navegador, como el cartel de bienvenida en la entrada.

   ```html
   <title>Mi Sitio Web</title>
   ```

3. **<meta name="viewport" content="width=device-width, initial-scale=1">**: Imagina que tienes una casa que puede cambiar de tamaño dependiendo del visitante (dispositivo). Esta etiqueta asegura que tu casa se ajuste correctamente ya sea que la visite alguien en un celular o en una computadora.

   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1">
   ```

### El cuerpo de la casa: <body>

El `<body>` es todo lo que los visitantes ven cuando entran a tu casa. Aquí es donde se encuentran las paredes, los muebles, y donde las personas interactúan con los elementos visibles de tu sitio web. 

   ```html
   <body>
     <!-- Aquí va el contenido visible de la página -->
   </body>
   ```

### Resumen de la estructura básica:

Hasta ahora, nuestra "casa" HTML básica se ve así:

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <title>Mi Sitio Web</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>
  <body>
    <!-- Contenido visible aquí -->
  </body>
</html>
```

### Agregando Estilos (CSS): La Pintura de la Casa

El CSS se encarga de la apariencia de la casa. Puedes elegir pintar las paredes de un color, cambiar el estilo de los muebles, o incluso agregar decoraciones. Hay tres maneras principales de agregar CSS:

1. **Usando un archivo externo**: Es como tener un decorador profesional que guarda todas sus herramientas en un solo lugar (un archivo externo).

   ```html
   <link rel="stylesheet" href="estilos.css">
   ```

2. **Estilos dentro del documento**: Si quieres hacer pequeños cambios sin contratar a alguien externo, puedes añadir estilos dentro del mismo archivo HTML.

   ```html
   <style>
     body {
       background-color: lightblue;
     }
   </style>
   ```

# Metadata en HTML: Entendiendo el Poder de las Etiquetas `<meta>`

## Introducción

Imagina que estás organizando un evento grande, como una fiesta. Para que todo salga bien, necesitas información clave sobre los invitados: sus preferencias, alergias, música favorita, etc. **La etiqueta `<meta>`** en HTML funciona de manera similar. Proporciona información importante sobre tu sitio web a los navegadores y motores de búsqueda para mejorar su funcionamiento y apariencia.

## ¿Qué son los Metadatos?

Los **metadatos** son datos sobre los datos. En el contexto de HTML, son información extra que no se muestra directamente en la página, pero que es vital para que los navegadores, motores de búsqueda y redes sociales sepan cómo interpretar y presentar tu contenido. La etiqueta `<meta>` es la que ayuda a definir estos metadatos.

## Tipos de Metaetiquetas Comunes

### 1. **Charset**: El Idioma del Sitio

Pensemos en **`<meta charset="utf-8">`** como un cartel en la puerta de la fiesta que dice en qué idioma se hablará. Si tus invitados no saben esto, podrían llegar y no entender nada. De igual forma, **`utf-8`** es el conjunto de caracteres más usado, lo que garantiza que el texto de tu página se muestre correctamente en la mayoría de los idiomas.

### 2. **Viewport**: Ajustando la Pantalla para Cada Dispositivo

El atributo **`<meta name="viewport" content="width=device-width, initial-scale=1.0">`** es como un acomodador en una fiesta que ajusta el espacio según el número de personas que lleguen. Este meta permite que la página se adapte correctamente al tamaño de la pantalla del dispositivo del usuario, ya sea un teléfono o una computadora. Así, todos tienen espacio para moverse cómodamente.

### 3. **Description**: El Anuncio de la Fiesta

La metaetiqueta **description** es como el texto que colocas en una invitación. En la web, es lo que los motores de búsqueda muestran debajo del título en los resultados. Es un resumen breve y atractivo de tu contenido, ayudando a los usuarios a saber si tu sitio es lo que buscan.

```html
<meta name="description" content="Aprende sobre HTML y etiquetas meta en este artículo fácil de seguir.">
```

### 4. **Robots**: Invitados con Restricciones

Al igual que podrías tener reglas sobre quién puede entrar a tu fiesta, con **`<meta name="robots" content="noindex, nofollow">`** puedes decirle a los motores de búsqueda que **no** indexen tu página ni sigan los enlaces. Esto es útil si tienes páginas que no quieres que aparezcan en los resultados de búsqueda.

### 5. **Theme-color**: Personalizando el Ambiente

Con **`<meta name="theme-color" content="#226DAA">`**, es como elegir la decoración de tu fiesta. Este meta define el color que aparecerá en las barras del navegador y en las apps móviles, dando una sensación de personalización y coherencia en tu branding.

## Metaetiquetas para Redes Sociales

### **Open Graph** y **Twitter Cards**: Compartiendo la Fiesta

Cuando alguien comparte un enlace a tu sitio en redes sociales, quieres que se vea bien, ¿verdad? Aquí es donde entran en juego **Open Graph** y **Twitter Cards**. Son como los flyers que alguien reparte para promocionar tu fiesta, asegurándose de que la imagen, el título y la descripción que se muestran sean atractivos.

```html
<meta property="og:title" content="Gran Fiesta de HTML" />
<meta property="og:description" content="Únete a nosotros para aprender sobre HTML y etiquetas meta." />
<meta property="og:image" content="https://example.com/imagen-fiesta.png" />
```

En Twitter:

```html
<meta name="twitter:title" content="Gran Fiesta de HTML" />
<meta name="twitter:description" content="Aprende HTML de manera divertida y fácil." />
<meta name="twitter:image" content="https://example.com/imagen-twitter.png" />
```

# HTML Semántico: Dando Sentido al Código

## Introducción

Imagina que estás construyendo una casa. Tienes dos opciones para organizarla: puedes usar cajas de cartón sin etiquetas para guardar todas tus cosas, o puedes usar muebles bien definidos, como armarios para ropa, estanterías para libros y cajones para cubiertos. ¿Cuál te parece más fácil de manejar y entender? Seguro que los muebles bien definidos.

Lo mismo sucede con HTML. Podemos usar elementos como `<div>` y `<span>`, que son como esas cajas de cartón sin etiquetas (sin valor semántico), o podemos usar etiquetas como `<header>`, `<nav>`, `<article>`, que son como los muebles específicos (elementos semánticos) que indican qué tipo de contenido albergan.

## ¿Qué es el HTML semántico?

Cuando hablamos de HTML semántico, nos referimos a utilizar las etiquetas HTML adecuadas para describir el propósito o significado del contenido que estamos marcando. Esto no solo ayuda a los desarrolladores a entender mejor la estructura de una página, sino que también hace que los motores de búsqueda, los navegadores y las herramientas de accesibilidad puedan procesar y presentar el contenido de manera más efectiva.

### Ejemplo de código sin semántica:

```html
<div>
  <span>Tres palabras</span>
  <div>
    <a>una palabra</a>
    <a>una palabra</a>
    <a>una palabra</a>
    <a>una palabra</a>
  </div>
</div>
<div>
  <div>
    <div>cinco palabras</div>
  </div>
  <div>
    <div>tres palabras</div>
    <div>cuarenta y seis palabras</div>
    <div>cuarenta y cuatro palabras</div>
  </div>
  <div>
    <div>siete palabras</div>
    <div>sesenta y ocho palabras</div>
    <div>cuarenta y cuatro palabras</div>
  </div>
</div>
<div>
   <span>cinco palabras</span>
</div>
```

En este caso, no podemos entender fácilmente la estructura de la página ni el propósito de cada elemento solo mirando el código.

### Ejemplo de código con semántica:

```html
<header>
  <h1>Tres palabras</h1>
  <nav>
    <a>una palabra</a>
    <a>una palabra</a>
    <a>una palabra</a>
    <a>una palabra</a>
  </nav>
</header>
<main>
  <header>
    <h1>Cinco palabras</h1>
  </header>
  <section>
    <h2>Tres palabras</h2>
    <p>Cuarenta y seis palabras</p>
    <p>Cuarenta y cuatro palabras</p>
  </section>
  <section>
    <h2>Siete palabras</h2>
    <p>Sesenta y ocho palabras</p>
    <p>Cuarenta y cuatro palabras</p>
  </section>
</main>
<footer>
  <p>Cinco palabras</p>
</footer>
```

Este código, por otro lado, nos da un contexto claro. Sabemos que `<header>` contiene el encabezado de la página, `<nav>` es el menú de navegación, `<main>` alberga el contenido principal y `<footer>` es el pie de página. Con solo mirar el código, podemos hacernos una idea de cómo está organizada la información.

## Importancia de la Semántica para la Accesibilidad

El HTML semántico no solo es útil para nosotros, los desarrolladores. También es vital para las personas que utilizan dispositivos de asistencia, como lectores de pantalla. Estos dispositivos dependen de la estructura semántica del HTML para ayudar a las personas con discapacidades visuales a navegar por una página web de manera eficiente.

### El AOM (Modelo de Objetos de Accesibilidad)

Cuando un navegador procesa una página web, no solo crea un DOM (Modelo de Objetos del Documento) que representa la estructura del HTML, sino que también genera un AOM (Modelo de Objetos de Accesibilidad), que es como una versión semántica del DOM.

Este modelo semántico ayuda a los lectores de pantalla a proporcionar información útil al usuario. Si el HTML no tiene elementos semánticos, estos dispositivos no pueden interpretar correctamente la estructura de la página, haciendo que la navegación sea mucho más difícil.

## El Atributo `role`

A veces, puede que necesites agregar significado a un elemento no semántico. En estos casos, puedes usar el atributo `role`. Este atributo describe el papel que tiene un elemento en la página, ayudando a las herramientas de accesibilidad a interpretar mejor el contenido.

Por ejemplo, si tienes un elemento `<div>` que actúa como un botón, puedes agregarle `role="button"` para darle ese significado.

```html
<div role="button">Haz clic aquí</div>
```

Esto indicará al lector de pantalla que el elemento se comporta como un botón, pero no añadirá las funcionalidades nativas de un botón verdadero. Por eso, siempre que sea posible, es mejor usar los elementos semánticos correctos, como `<button>` en lugar de añadir `role="button"` a un `<div>`.

## ¿Por qué es importante el HTML semántico?

Volviendo a nuestra analogía, cuando organizamos nuestra casa usando muebles bien definidos en lugar de cajas sin etiquetar, todo es más fácil de encontrar y usar. Lo mismo sucede con una página web. Al usar HTML semántico, estamos construyendo una estructura lógica que no solo ayuda a los desarrolladores y dispositivos de asistencia, sino que también mejora el SEO (optimización para motores de búsqueda) y hace que el sitio sea más fácil de mantener a largo plazo.

### Recapitulación:

- **Elementos semánticos** como `<header>`, `<main>`, `<article>`, y `<footer>` nos ayudan a organizar el contenido de manera clara.
- **El atributo `role`** es útil cuando no puedes usar un elemento semántico, pero debe usarse con moderación.
- **HTML semántico** mejora la accesibilidad y el SEO de tu página.
  
Organiza tu HTML como organizas tu casa: eligiendo los muebles correctos para cada cosa y asegurándote de que todo esté en su lugar adecuado.

# Encabezados y Secciones

## Introducción

Imagina que estás escribiendo un libro. Cada página tiene que estar organizada para que cualquier persona que lo lea (ya sea humano o máquina) pueda entender fácilmente qué secciones son importantes, dónde están los capítulos y cómo encontrar rápidamente la información. Esto es lo que hacemos cuando organizamos un documento HTML usando encabezados y secciones. ¡Es como darle una estructura clara a tu libro!

## Estructura Semántica

La semántica en HTML es como cuando usas el nombre correcto para las cosas. Por ejemplo, si tienes un perro, lo llamas "perro", no "animal". En HTML, en lugar de usar etiquetas genéricas como `<div>`, que no le dicen mucho al navegador sobre qué es, usamos etiquetas semánticas como `<header>`, `<nav>`, o `<footer>` para explicar qué hace cada parte del documento.

### Ejemplo de Código sin Semántica

```html
<!-- start header -->
<div id="pageHeader">
  <div id="title">Machine Learning Workshop</div>
  <div id="navigation">
    <a href="#reg">Register</a>
    <a href="#about">About</a>
    <a href="#teachers">Instructors</a>
    <a href="#feedback">Testimonials</a>
  </div>
</div>
<!-- end of header -->
```

En este ejemplo, estamos usando `<div>` para todo, lo cual es como llamar "animal" a todo sin especificar si es un perro, un gato o un pájaro. Funciona, pero no es muy claro.

### Mejora Semántica

Podemos hacer que este código sea más entendible y útil para los motores de búsqueda y los lectores de pantalla usando elementos semánticos.

```html
<header>
  <h1>Machine Learning Workshop</h1>
  <nav>
    <a href="#reg">Register</a>
    <a href="#about">About</a>
    <a href="#teachers">Instructors</a>
    <a href="#feedback">Testimonials</a>
  </nav>
</header>
```

Aquí, estamos diciendo claramente que esta parte del documento es un `header` y que dentro tenemos un título (`<h1>`) y un bloque de navegación (`<nav>`). Es como darle un título a cada capítulo de nuestro libro.

## Footer (Pie de Página)

Al igual que el encabezado, el pie de página (`<footer>`) también es una parte importante de la estructura de una página. Es como la sección de agradecimientos o información adicional en un libro.

```html
<footer>
  <p>&copy;2022 Machine Learning Workshop, LLC. All rights reserved.</p>
  <address>Instructors: <a href="/hal.html">Hal</a> and <a href="/eve.html">Eve</a></address>
</footer>
```

Aquí, usamos `<address>` para mostrar la información de contacto, que es como decirle al lector: "Si quieres más información, aquí están los datos de los autores."

## Elementos Semánticos en la Estructura

Cuando construimos una página web, usamos otros elementos semánticos para organizar el contenido, igual que organizamos capítulos en un libro.

### `<main>`

Este es el contenido principal de la página, como el cuerpo principal del libro.

### `<article>`

Cada `<article>` es como un artículo de revista o una entrada de blog. Es un bloque independiente de contenido que puede vivir por sí mismo o dentro de otras secciones.

### `<aside>`

Un `<aside>` es como una nota al margen o una caja de texto destacada en un libro. No es el contenido principal, pero está relacionado de alguna manera.

### `<section>`

Una `<section>` es una parte genérica de una página que agrupa contenido relacionado. Si no sabes qué etiqueta usar, probablemente puedas usar `<section>`.

# Atributos en HTML

## ¿Qué son los atributos?

Piensa en los atributos como las "instrucciones adicionales" que le das a un elemento HTML para que haga algo más específico. Es como cuando escribes una carta y en el sobre añades instrucciones: "Por favor, entregar antes del mediodía". El sobre sería el elemento HTML, y la instrucción extra sería el atributo.

Los atributos en HTML son esos detalles adicionales que ponemos en la **etiqueta de apertura** de un elemento para definir su comportamiento o funcionalidad. Estos atributos están formados por un **nombre** y un **valor** (por ejemplo, `type="text"` en un input).

## Ejemplo básico

```html
<input type="text">
```

Aquí, el `input` es el sobre (elemento) y `type="text"` es la instrucción (atributo) que le estamos dando. Le estamos diciendo al navegador que este `input` debe ser de texto.

## Tipos de atributos

### Atributos Globales

Algunos atributos son como reglas generales que aplican a cualquier elemento HTML, sin importar qué tipo de elemento sea. Un buen ejemplo es el atributo `id`, que sirve para darle un nombre único a un elemento en la página. Es como ponerle un nombre a un personaje en una obra de teatro: nadie más puede llamarse igual, o te confundirías.

```html
<div id="miElementoUnico"></div>
```

Este `div` tiene un `id` único llamado "miElementoUnico". Con este `id`, podemos identificarlo claramente en CSS o JavaScript y aplicarle estilos o comportamiento específicos.

### Atributos Específicos

Hay otros atributos que solo aplican a ciertos elementos. Por ejemplo, el atributo `src` en una etiqueta `img` indica la fuente de la imagen, como la dirección de una imagen en internet. No tendría sentido poner `src` en un `div`, sería como tratar de poner una dirección en un objeto que no es una carta.

```html
<img src="imagen.jpg" alt="Descripción de la imagen">
```

### Atributos Booleanos

Un atributo booleano es como un interruptor de luz: está encendido o apagado, no hay punto medio. Si el atributo está presente, es como decir "está encendido". Si no está, entonces está apagado. Un ejemplo de esto es el atributo `disabled` en un botón.

```html
<button disabled>Botón deshabilitado</button>
```

En este caso, el botón está "apagado" o deshabilitado porque hemos añadido el atributo `disabled`. No es necesario darle un valor, ya que su sola presencia indica que el botón está inhabilitado.

### Atributos Enumerados

Los atributos enumerados son aquellos que tienen un conjunto limitado de valores posibles. Es como si en un menú solo pudieras elegir entre tres opciones: pizza, pasta o ensalada. Un ejemplo es el atributo `contenteditable`, que le dice al navegador si un elemento es editable o no. Tiene solo dos valores: `true` o `false`.

```html
<div contenteditable="true">Este texto se puede editar.</div>
```

Si pones `contenteditable="true"`, el texto dentro del `div` puede ser modificado por el usuario. Si pones `contenteditable="false"`, no podrá hacerlo.

## Uso correcto de los atributos

Es importante seguir las reglas de los atributos, especialmente con las mayúsculas y minúsculas. Algunos atributos como `id` son **sensible a mayúsculas y minúsculas**. Esto significa que un `id="miID"` no es lo mismo que `id="MiID"`. Por otro lado, algunos atributos, como `type` en un `input`, no son sensibles a esto.

```html
<!-- Esto es lo mismo -->
<input type="text">
<input type="TeXt">

<!-- Esto NO es lo mismo -->
<div id="miID"></div>
<div id="MiID"></div>
```

## Atributos en acción con JavaScript

Los atributos también pueden ser manipulados con JavaScript. Si quieres cambiar el estado de un atributo, como desmutear un video, puedes hacerlo con el siguiente código:

```javascript
const myMedia = document.getElementById("mediaFile");
myMedia.removeAttribute("muted"); // Quitar atributo muted
myMedia.setAttribute("muted", ""); // Agregar el atributo muted
```

## Uso del Atributo `class` en HTML

### 🚗 Analogía: "Las Etiquetas de los Autos"
Imagina que cada elemento HTML es como un auto en una gran cochera. Algunos autos necesitan una etiqueta especial que los distinga de otros, tal vez por el color, el modelo, o el tipo de combustible que usan. La **etiqueta** en este caso es el atributo `class`, que le permite a los desarrolladores etiquetar ciertos autos (o elementos HTML) para que después puedan agruparlos y aplicarles mejoras (como un trabajo de pintura o nuevas llantas, que serían los estilos CSS).

En HTML, el atributo `class` actúa como esa etiqueta. Te permite agrupar elementos en categorías y aplicarles un estilo especial o comportamiento, al igual que podrías poner etiquetas en los autos de tu cochera para identificarlos y hacerles cambios más fácilmente.

### 🔍 Explicación Técnica

El atributo `class` en HTML sirve para agrupar elementos y aplicarles estilos mediante **CSS** o comportamientos mediante **JavaScript**. Este atributo toma como valor una lista separada por espacios de nombres de clases (case-sensitive), es decir, sensibles a mayúsculas y minúsculas. 

Un ejemplo básico de su uso sería:

```html
<div class="coche deportivo rojo"></div>
```

Aquí, el `<div>` tiene tres clases: `coche`, `deportivo` y `rojo`. Esto nos permite aplicar estilos o comportamientos a todos los elementos con la clase `coche`, a todos los `deportivo`, o a aquellos con la clase `rojo`.

### 🛠️ Seleccionando Elementos con `class`

Podemos utilizar las clases de dos maneras principales:

1. **CSS**: Para aplicar estilos a todos los elementos que tengan una clase particular.
   ```css
   .rojo {
     background-color: red;
   }
   ```

2. **JavaScript**: Para manipular elementos que compartan la misma clase.
   ```javascript
   const cochesRojos = document.getElementsByClassName('rojo');
   for (let coche of cochesRojos) {
     coche.style.border = '2px solid black';
   }
   ```

### 📚 ¿Siempre es Necesario Usar `class`?

No siempre es necesario agregar una clase a cada elemento. En muchos casos, la estructura semántica del HTML es suficiente para aplicar estilos y comportamientos. Por ejemplo, podríamos seleccionar elementos basados en su posición o tipo sin necesidad de usar `class`:

- **Sin `class`**: Seleccionamos todos los párrafos (`<p>`) o todos los elementos dentro de una lista (`<li>`).
- **Con `class`**: Nos permite ser más específicos, por ejemplo, seleccionar solo los párrafos que pertenecen a una clase especial.

```html
<p class="importante">Este es un párrafo importante.</p>
<p>Este es un párrafo normal.</p>
```

En este caso, podríamos aplicar estilos solo al párrafo con la clase `importante` usando `.importante` en CSS.

# Conceptos básicos de texto en HTML

## Introducción

Imagina que estás construyendo una casa. Los **encabezados** serían como los títulos que le pones a cada sección de tu plano: "Sala de estar", "Cocina", "Baño", etc. Cada título tiene un nivel de importancia, y eso también ocurre en HTML. Con estos **encabezados**, le damos estructura al contenido de una página web.

HTML es el lenguaje de marcado que usamos para construir la estructura de una página web, como si fuera el plano de una casa. Permite a los navegadores entender cómo organizar el contenido. En esta sección, te voy a guiar por los conceptos básicos de texto y cómo marcarlos en HTML.

---

## Encabezados en HTML

En HTML, existen seis niveles de encabezados, representados por las etiquetas `<h1>` a `<h6>`. Son como los títulos y subtítulos de un documento, donde `<h1>` es el título más importante (equivalente a "Sala de estar" en el plano de la casa), y `<h6>` es el menos importante.

```html
<h1>Este es un Encabezado Nivel 1</h1>
<h2>Este es un Encabezado Nivel 2</h2>
<h3>Este es un Encabezado Nivel 3</h3>
```

### Analogía: La estructura de un libro
Piensa en un libro: 
- El título principal del libro es el **h1**.
- Los capítulos son **h2**.
- Las secciones dentro de los capítulos son **h3**, y así sucesivamente.

Estos encabezados no solo organizan el contenido visualmente, sino que también permiten a los usuarios de lectores de pantalla navegar fácilmente por una página. Los lectores de pantalla permiten saltar entre encabezados con la tecla "h", lo que hace que sea crucial que el contenido esté bien estructurado.

---

## Párrafos en HTML

Cuando tienes varios párrafos en un libro, cada uno está claramente separado por un espacio. En HTML, esto se hace con la etiqueta `<p>`, que representa un párrafo.

```html
<p>Este es un párrafo de ejemplo en HTML.</p>
```

Es importante cerrar correctamente las etiquetas para que el contenido se muestre como esperas. Aunque en algunos casos la etiqueta de cierre puede ser opcional, siempre es mejor ser claro y cerrar todas las etiquetas.

### Analogía: Un bloque de texto
Los párrafos en HTML son como bloques de texto dentro de un artículo. Separan ideas y hacen que el contenido sea más fácil de leer.

---

## Citas y referencias

Para citar texto de otra fuente o para agregar énfasis en una frase, HTML tiene dos etiquetas clave: `<blockquote>` y `<q>`. 
- La etiqueta `<blockquote>` es para citas más largas, que normalmente se muestran en un bloque separado del resto del texto.
- La etiqueta `<q>` es para citas cortas, que se integran en el flujo del texto.

```html
<blockquote cite="https://ejemplo.com">
    Este es un bloque de cita de una fuente externa.
</blockquote>

<p>Como dijo alguien famoso: <q>El conocimiento es poder.</q></p>
```

### Analogía: Un recuadro de cita en un artículo
Imagina que estás leyendo una revista, y ves una cita de un experto en un cuadro destacado. Ese cuadro sería un `<blockquote>`. Las citas cortas dentro del texto serían como las frases entrecomilladas, representadas por `<q>`.

---

## Entidades HTML

En HTML, algunos caracteres tienen un significado especial, como `<`, `>`, `&`, y `"`.

Para que estos caracteres se muestren en pantalla y no se interpreten como código, usamos **entidades HTML**. Por ejemplo:
- `<` se escribe como `&lt;`
- `>` se escribe como `&gt;`
- `&` se escribe como `&amp;`

```html
<p>Para mostrar un menor que: &lt; </p>
```

### Analogía: Instrucciones en una receta
Imagina que en una receta te dicen que "no uses este ingrediente". Si lo pones, no vas a obtener el resultado esperado. Lo mismo ocurre con estos caracteres en HTML. Si los usas sin escapar, el navegador podría malinterpretarlos.

# Vínculos en HTML: Analogías y Conceptos

## Introducción

En el mundo de la web, los vínculos son como los caminos en un mapa que conectan diferentes lugares. Imagina que estás explorando una ciudad desconocida y cada vez que quieres ir a una nueva atracción, sigues un camino que te lleva allí. En HTML, los vínculos hacen algo similar, pero en lugar de conectar lugares físicos, conectan documentos y recursos en la web.

## La Etiqueta `<a>`

La etiqueta `<a>` en HTML es como un señalizador en la ciudad. Es el que te dice adónde ir cuando haces clic en él. Por ejemplo, si ves un cartel que dice "Museo de Historia", es como hacer clic en un vínculo que te lleva a la página de ese museo.

### El Atributo `href`

El atributo `href` es el "mapa" que indica la dirección a la que el vínculo te llevará. Sin `href`, el vínculo sería como un cartel sin dirección, simplemente una pieza decorativa sin funcionalidad. 

**Ejemplos de vínculos:**

- `<a href="https://machinelearningworkshop.com">Machine Learning Workshop</a>`  
  Este es un vínculo con una dirección completa, como una dirección postal exacta que te lleva al sitio web del taller de aprendizaje automático.

- `<a href="#teachers">Our teachers</a>`  
  Este vínculo te lleva a una parte específica de la misma página, como si fuera una señal en un edificio grande que te guía a un departamento particular.

- `<a href="mailto:hal9000@machinelearningworkshop.com">Email Hal</a>`  
  Este vínculo abre tu cliente de correo electrónico para enviar un mensaje a Hal, como si tuvieras un teléfono en el cartel que te permite llamar directamente.

- `<a href="tel:8005551212">Call Hal</a>`  
  Similar al anterior, pero para hacer una llamada telefónica en lugar de enviar un correo.

## URL Absolutas vs. Relativas

- **URL Absoluta:** Es como una dirección completa que incluye el nombre de la calle y la ciudad. Ejemplo: `https://machinelearningworkshop.com`. Puedes ir a cualquier lugar del mundo con esta dirección.

- **URL Relativa:** Es como una dirección dentro de una misma ciudad. No necesitas la dirección completa, solo la ruta desde tu ubicación actual. Ejemplo: `<a href="../attributes/">Attributes</a>`. Esto te lleva a una página en el mismo sitio web, pero en una ubicación diferente.

## Vínculos Internos y Externos

- **Vínculo Interno:** Te lleva a una parte diferente del mismo documento o sitio web, como si te movieras dentro del mismo edificio. Ejemplo: `<a href="#top">Go to top.</a>`

- **Vínculo Externo:** Te lleva a un sitio web completamente diferente, como salir del edificio y caminar a otro. Ejemplo: `<a href="https://machinelearningworkshop.com">Machine Learning Workshop</a>`

## Atributo `download`

Cuando un vínculo apunta a un archivo descargable, el atributo `download` sugiere un nombre de archivo para guardarlo, como poner una etiqueta en una caja de entrega para que sepas qué hay dentro. Ejemplo:

```html
<a href="blob:https://example.com/file" download="example-file.svg">Download SVG</a>
```

## Atributo `target`

El atributo `target` indica dónde se abrirá el vínculo. Es como elegir si quieres abrir una puerta en la misma habitación (pestaña actual) o en una sala nueva (nueva pestaña). 

- **`_self`:** Abre el vínculo en la misma ventana o pestaña.
- **`_blank`:** Abre el vínculo en una nueva ventana o pestaña.
- **`_parent`:** Abre el vínculo en el marco superior si está anidado en un iframe.
- **`_top`:** Abre el vínculo en el marco superior más alto.

Ejemplo:

```html
<a href="registration.html" target="_blank">Register Now</a>
```

Esto abrirá la página en una nueva pestaña.

## Atributo `rel`

El atributo `rel` define la relación entre el documento actual y el recurso del vínculo. Es como colocar una etiqueta en una caja para describir su contenido. 

- **`nofollow`:** Indica que los motores de búsqueda no deben seguir este vínculo.
- **`external`:** Indica que el vínculo lleva a un sitio web externo.
- **`help`:** Sugiere que el vínculo ofrece ayuda.

Ejemplo:

```html
<a href="https://external-site.com" rel="external">Visit External Site</a>
```

## Seguimiento de Clics

El atributo `ping` permite rastrear los clics en un vínculo. Es como tener una cámara en la entrada de un edificio que te notifica cada vez que alguien entra. 

```html
<a href="https://example.com" ping="https://tracking-site.com/ping">Track Me</a>
```

## Sugerencias sobre la Experiencia del Usuario

- **Información Claramente Visibles:** Los vínculos deben ser fáciles de identificar. No uses solo color para diferenciar los vínculos; considera subrayar o cambiar el estilo.
- **Descripciones Claras:** El texto del vínculo debe indicar claramente adónde lleva el vínculo. Evita textos genéricos como "haz clic aquí".
- **No Anidar Elementos Interactivos:** No pongas botones dentro de vínculos o viceversa. Esto puede causar problemas en la navegación.

## Vínculos y JavaScript

Puedes usar JavaScript para manipular vínculos, como cambiar su destino o el protocolo que usan. Es como cambiar la dirección en una señal de tráfico mientras estás en la carretera.

```javascript
let a = document.links[0];
a.href = 'newpage.html'; // Cambia la URL del vínculo
a.protocol = 'ftp'; // Cambia solo el protocolo
```

# Listas en HTML

## Listas

Las listas son como las cajas de herramientas en las que organizas diferentes elementos. Imagina que tienes una caja de herramientas que quieres mantener ordenada. Puedes clasificar tus herramientas en diferentes compartimentos. De la misma manera, en HTML, usamos listas para organizar y presentar información de manera estructurada. Aquí exploraremos cómo crear y manejar listas en HTML usando analogías para hacerlo más claro.

### Listas sin Ordenar (`<ul>`)

Piensa en una lista sin ordenar (`<ul>`) como una caja de herramientas donde no necesitas seguir un orden específico para colocar tus herramientas. Solo necesitas asegurarte de que todas las herramientas estén en su lugar. Las listas sin ordenar se usan cuando el orden de los elementos no importa. Por ejemplo, si estás enumerando los tipos de herramientas que tienes, como martillos, destornilladores y llaves, el orden en que los mencionas no afecta.

En HTML, una lista sin ordenar se define así:

```html
<ul>
  <li>Martillo</li>
  <li>Destornillador</li>
  <li>Llave</li>
</ul>
```

Cada elemento de la lista está precedido por una viñeta por defecto, que actúa como una pequeña marca para cada herramienta.

### Listas Ordenadas (`<ol>`)

Ahora, si tu caja de herramientas tiene compartimentos numerados, como los que podrías tener en un organizador de herramientas, estás trabajando con una lista ordenada (`<ol>`). Aquí, el orden sí importa. Por ejemplo, si estás enumerando los pasos para ensamblar un mueble, el orden en que sigues las instrucciones es crucial.

En HTML, una lista ordenada se define así:

```html
<ol>
  <li>Desembalar las piezas</li>
  <li>Armar las partes del mueble</li>
  <li>Colocar el mueble en su lugar</li>
</ol>
```

Las listas ordenadas usan números o letras para mostrar el orden de los elementos. Puedes controlar el tipo de numeración mediante CSS o el atributo `type`.

### Listas de Descripciones (`<dl>`)

Imagina que tienes un catálogo de productos, donde cada producto tiene una descripción detallada. Una lista de descripciones (`<dl>`) funciona como este catálogo. Cada producto (término) tiene una descripción asociada.

En HTML, una lista de descripciones se define así:

```html
<dl>
  <dt>Martillo</dt>
  <dd>Herramienta para clavar clavos.</dd>
  
  <dt>Destornillador</dt>
  <dd>Herramienta para atornillar tornillos.</dd>
</dl>
```

Aquí, `<dt>` es el término (por ejemplo, el nombre del producto), y `<dd>` es la descripción de ese término.

### Anidación de Listas

Las listas también pueden estar anidadas, como una caja de herramientas dentro de una caja de herramientas más grande. Esto es útil para mostrar jerarquías o subcategorías. Por ejemplo, en un manual de instrucciones, podrías tener una lista de tareas principales y dentro de cada tarea, una lista de pasos específicos:

```html
<ol>
  <li>Preparar los ingredientes
    <ul>
      <li>Reunir todos los ingredientes</li>
      <li>Medir las cantidades necesarias</li>
    </ul>
  </li>
  <li>Cocinar el plato</li>
</ol>
```

En este caso, la lista de pasos está anidada dentro de la tarea principal.

### Atributos de Listas

- **`type`**: En listas ordenadas, puedes cambiar el tipo de numeración (números, letras, números romanos).
- **`reversed`**: Este atributo invierte el orden de los números en una lista ordenada.
- **`start`**: Establece el número de inicio en una lista ordenada.

Por ejemplo, si quieres que una lista ordenada comience en el número 5 y se muestre en números romanos, podrías hacer lo siguiente:

```html
<ol type="I" start="5">
  <li>Primer paso</li>
  <li>Segundo paso</li>
</ol>
```

### Elementos de Lista (`<li>`)

Cada elemento en una lista, ya sea ordenada o sin ordenar, se define usando el elemento `<li>`. Es como cada compartimento en tu caja de herramientas que tiene un propósito específico.

```html
<ul>
  <li>Martillo</li>
  <li>Destornillador</li>
</ul>
```

Los elementos de lista se pueden cerrar implícitamente cuando se encuentra el siguiente `<li>` o la etiqueta de cierre de lista (`</ul>`, `</ol>`), pero es una buena práctica cerrarlos explícitamente para mantener el código limpio.

### Listas y Accesibilidad

Cuando usas listas, asegúrate de que sean accesibles. Por ejemplo, si usas CSS para cambiar el estilo de la lista y eliminar las viñetas, considera usar `role="list"` para asegurar que los lectores de pantalla reconozcan la lista como tal.

```html
<ul role="list">
  <li>Elemento 1</li>
  <li>Elemento 2</li>
</ul>
```

Este atributo asegura que la semántica de la lista se mantenga incluso si el estilo visual se cambia.

# Navegación en Sitios Web: Un Viaje Guiado

En la web, la navegación es como un mapa que ayuda a los usuarios a encontrar su camino. En esta sección, exploraremos los diferentes tipos de navegación que pueden facilitar la experiencia del usuario en un sitio web.

## ¿Qué es la Navegación?

Imagina que estás en una gran librería. Para encontrar un libro específico, usas diferentes herramientas:

1. **Carteles de Pasillo**: Te dicen en qué sección están los libros sobre ciencia ficción, cocina, etc. Esto es como la **navegación global**, que te ayuda a encontrar las secciones principales de un sitio web.
2. **Ruta de Tablones**: Muestra cómo llegar desde la entrada de la librería hasta el libro que quieres. Esto es como la **ruta de navegación**, que muestra cómo llegaste a la página actual.
3. **Mapa de la Librería**: Te da una visión general de todas las secciones y te permite encontrar rápidamente el área que te interesa. Esto es como un **mapa del sitio**, que ofrece una visión general de todo el sitio web.

### Navegación Global

La navegación global es como los carteles de pasillo en la librería. Es una lista de enlaces que te llevan a las principales secciones de tu sitio web, como "Inicio", "Sobre Nosotros", "Servicios", etc. Esta navegación suele estar visible en todas las páginas y puede aparecer en diferentes formatos, como barras de navegación, menús desplegables, o menús flotantes, dependiendo del tamaño de la pantalla del usuario.

**Ejemplo en Código**:

```html
<nav aria-label="Global Navigation">
  <ul>
    <li><a href="/">Inicio</a></li>
    <li><a href="/about">Sobre Nosotros</a></li>
    <li><a href="/services">Servicios</a></li>
    <li><a href="/contact">Contacto</a></li>
  </ul>
</nav>
```

### Ruta de Navegación

La ruta de navegación es como el tablón de anuncios que te muestra el camino desde la entrada hasta el libro en particular. En la web, esto muestra la jerarquía de páginas desde la página de inicio hasta la página actual.

**Ejemplo en Código**:

```html
<nav aria-label="Breadcrumbs">
  <ul>
    <li><a href="/">Inicio</a></li>
    <li><a href="/category">Categoría</a></li>
    <li><a href="/category/item">Elemento</a></li>
    <li aria-current="page">Página Actual</li>
  </ul>
</nav>
```

### Mapa del Sitio

Un mapa del sitio es como un plano de la librería que muestra todas las secciones y estantes. En la web, esto es una página que enlaza a todas las secciones importantes del sitio, proporcionando una vista general para que los usuarios encuentren lo que buscan rápidamente.

**Ejemplo en Código**:

```html
<nav aria-label="Site Map">
  <ul>
    <li><a href="/">Inicio</a></li>
    <li><a href="/about">Sobre Nosotros</a></li>
    <li><a href="/services">Servicios</a></li>
    <li><a href="/contact">Contacto</a></li>
  </ul>
</nav>
```

### Navegación Local

La navegación local es como los indicadores en cada pasillo de la librería que te ayudan a encontrar el libro específico que buscas en esa sección. En la web, esto se refiere a los enlaces que llevan a las subsecciones dentro de una página o área específica del sitio.

**Ejemplo en Código**:

```html
<nav aria-label="Local Navigation">
  <ul>
    <li><a href="#section1">Sección 1</a></li>
    <li><a href="#section2">Sección 2</a></li>
    <li><a href="#section3">Sección 3</a></li>
  </ul>
</nav>
```

### Índice de Página

El índice de una página es como el índice de un libro que te permite ver las secciones y temas cubiertos en el documento. En la web, esto puede ser una lista de enlaces a diferentes partes del contenido de la página actual, que se puede mostrar o ocultar según el tamaño de la pantalla.

**Ejemplo en Código**:

```html
<nav aria-label="Table of Contents">
  <ul>
    <li><a href="#section1">Introducción</a></li>
    <li><a href="#section2">Contenido Principal</a></li>
    <li><a href="#section3">Conclusión</a></li>
  </ul>
</nav>
```

## Accesibilidad y Usabilidad

Para mejorar la accesibilidad, asegúrate de que los usuarios puedan saltar fácilmente a la parte principal del contenido. Esto se hace usando un enlace como "Ir al contenido" al principio de la página.

**Ejemplo en Código**:

```html
<a href="#main" class="skip-link">Skip to main content</a>
<main id="main">
  <!-- Contenido principal aquí -->
</main>
```

La usabilidad es clave. Asegúrate de que la navegación sea intuitiva y que los usuarios puedan encontrar lo que buscan sin confusión. La navegación debe ser coherente y predecible en todo el sitio.

# Tablas en HTML: Una Guía Paso a Paso

Las tablas en HTML se utilizan para mostrar datos organizados en filas y columnas, de manera similar a cómo se muestran las filas de asientos en un cine. Sin embargo, es importante usarlas correctamente para asegurarse de que la información sea accesible y clara para todos. En esta guía, vamos a desglosar cómo funcionan las tablas en HTML, utilizando analogías simples para entender mejor cada concepto técnico.

## ¿Qué es una tabla HTML?

Imagina una tabla como una hoja de papel con una cuadrícula dibujada. Cada casilla en la cuadrícula puede contener información específica. En HTML, usamos la etiqueta `<table>` para crear esta cuadrícula de datos.

**Analogía:** Piensa en `<table>` como un "cuaderno de registro" donde cada página tiene una cuadrícula para registrar información de manera ordenada.

### Elementos de la tabla

1. **`<table>`**: Es como la portada de tu cuaderno de registro. Une todos los elementos de la tabla.

2. **`<caption>`**: Este es el título de la tabla, como el encabezado de una página en tu cuaderno que dice de qué se trata. Debe ser el primer elemento dentro de `<table>` para que todos entiendan de inmediato el propósito de la tabla.

3. **`<thead>`**: Representa el encabezado de la tabla. Es como los títulos de las columnas en una hoja de cálculo.

4. **`<tbody>`**: Aquí van los datos principales de la tabla, como el contenido de las filas en tu hoja de cálculo.

5. **`<tfoot>`**: Se usa para el pie de la tabla, que puede contener resúmenes o totales, como los totales de una columna en tu hoja de cálculo.

   **Analogía:** Imagina que `<thead>` es la primera fila de tu cuaderno de registro con los nombres de las categorías, `<tbody>` es el resto de las filas donde escribes los datos, y `<tfoot>` es una sección al final para resúmenes.

### Filas y Celdas

- **`<tr>`**: Es una fila en la tabla, como una línea en una hoja de cálculo.
- **`<th>`**: Es una celda de encabezado, que está en negrita y centrada por defecto. Es como el título de una columna en tu hoja de cálculo.
- **`<td>`**: Es una celda de datos que contiene la información real, como los valores en una hoja de cálculo.

   **Analogía:** Piensa en `<tr>` como una fila de datos en tu hoja de cálculo. `<th>` es como el encabezado de esa fila, y `<td>` es donde pones los datos.

### Combinando Celdas

Puedes combinar celdas para que ocupen más espacio usando:

- **colspan**: Combina celdas en una fila. Es como unir dos columnas en tu hoja de cálculo para hacer una celda más ancha.
- **rowspan**: Combina celdas en varias filas. Es como unir dos filas en tu hoja de cálculo para hacer una celda más alta.

**Analogía:** Imagina que en tu hoja de cálculo necesitas una celda que abarque varias columnas o filas. Usas `colspan` o `rowspan` para combinar esas celdas, igual que en una tabla HTML.

### Agrupando Columnas

- **<colgroup>** y **<col>**: Permiten agrupar columnas y aplicar estilos a ellas. Es como usar un marcador en tu hoja de cálculo para cambiar el color de varias columnas a la vez.

**Analogía:** Si necesitas aplicar un color a varias columnas en tu hoja de cálculo, usarías una función para seleccionar todas ellas. En HTML, usas `<colgroup>` y `<col>` para hacer lo mismo.

### Estilizando Tablas

Las tablas no son responsivas por defecto. Para hacerlas adaptables a diferentes tamaños de pantalla, es necesario usar CSS:

- **border-collapse** y **border-spacing**: Controlan el espacio entre las celdas y los bordes de la tabla. 

**Analogía:** Si en tu hoja de cálculo quieres ajustar el espacio entre las celdas, usas herramientas de formato. En HTML, usas CSS para hacer lo mismo.

### Accesibilidad

Es crucial que las tablas sean accesibles para todos, incluidos los usuarios con discapacidades. Usa atributos ARIA y asegura que los encabezados y celdas estén bien definidos.

**Analogía:** Si necesitas que tu cuaderno de registro sea accesible para todos, asegúrate de etiquetar claramente las secciones y usar colores que sean visibles para todos. En HTML, haces esto con atributos ARIA y una estructura clara.

### No Usar Tablas para Diseño

No uses tablas para organizar contenido no tabular, como imágenes o diseño de página. Para eso, usa listas o CSS Grid.

**Analogía:** No uses una hoja de cálculo para diseñar una presentación de diapositivas. Usa una herramienta de presentación para eso. En HTML, usa listas y CSS para diseño en lugar de tablas.

## Ejemplo Completo

Aquí tienes un ejemplo de cómo se ve una tabla HTML bien estructurada:

```html
<table>
  <caption>MLW Students</caption>
  <thead>
    <tr>
      <th>Año</th>
      <th>Estudiante</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1956</th>
      <td>Lou Minious</td>
    </tr>
    <!-- Más filas aquí -->
  </tbody>
  <tfoot>
    <tr>
      <td colspan="2">Total de estudiantes: 1</td>
    </tr>
  </tfoot>
</table>
```

# Formularios

## ¿Qué es un formulario?

Los formularios son una parte esencial de casi todos los sitios y aplicaciones web. Imagina que un formulario es como una hoja de papel donde los usuarios pueden escribir información que luego se envía a algún lugar, como una carta que llevas al buzón. En el mundo web, esta "hoja de papel" es representada por el elemento `<form>` en HTML.

### El Elemento `<form>`

El `<form>` es el contenedor de todos los controles interactivos que permiten a los usuarios ingresar y enviar datos. Es como una caja de herramientas donde guardas todos los utensilios que necesitas para completar una tarea. Dentro del `<form>`, colocas todos los elementos que forman el formulario, como los campos de texto, botones y listas desplegables.

```html
<form action="/enviar-datos" method="POST">
  <!-- Aquí van los controles del formulario -->
</form>
```

## Enviar Formularios

Cuando un usuario termina de llenar un formulario, lo envía mediante un botón. Puedes usar dos tipos principales de botones para enviar datos:

```html
<input type="submit" value="Enviar Formulario">
<button type="submit">Enviar Formulario</button>
```

El atributo `action` del `<form>` define la URL a la que se envían los datos, mientras que `method` especifica el protocolo HTTP que se utiliza, como `GET` o `POST`. 

### `action` y `method`

- **`action`**: Es la dirección a donde van los datos del formulario. Si no se especifica, los datos se envían a la misma página.
- **`method`**: Define cómo se envían los datos. `GET` añade los datos a la URL, mientras que `POST` los envía en el cuerpo de la solicitud. Usa `POST` para datos sensibles como contraseñas.

## Botones de Envío y Tipos de Entrada

Los botones de envío y los tipos de entrada son como los controles en un juego. Cada uno tiene una función específica:

```html
<input type="submit" value="Enviar">
<button type="submit">Enviar</button>
```

- **`<input type="submit">`**: Muestra un botón con la etiqueta definida en el atributo `value`.
- **`<button type="submit">`**: Muestra un botón con la etiqueta que esté entre las etiquetas de apertura y cierre.

## Atributos Importantes

- **`name`**: Define el nombre de cada campo del formulario. Es como el título de una columna en una hoja de cálculo; ayuda a identificar qué datos se están enviando.
- **`value`**: Es el contenido o la selección del campo, como el texto en una celda de una hoja de cálculo.

## Casillas de Verificación y Botones de Selección

### Casillas de Verificación

Las casillas de verificación permiten seleccionar múltiples opciones, similar a marcar varias casillas en una lista de tareas. Solo se envían las casillas marcadas.

```html
<input type="checkbox" name="intereses" value="deportes"> Deportes
<input type="checkbox" name="intereses" value="lectura"> Lectura
```

### Botones de Selección

Los botones de selección permiten elegir solo una opción de un grupo, como seleccionar una sola respuesta en una encuesta. Todos los botones en un grupo deben tener el mismo `name` para que se comporten como un solo conjunto.

```html
<input type="radio" name="genero" value="masculino"> Masculino
<input type="radio" name="genero" value="femenino"> Femenino
```

## Etiquetas y Grupos de Controles

Las etiquetas son como los nombres en un formulario. Ayudan a los usuarios a entender qué información se requiere. Utiliza `<label>` para etiquetar controles individuales y `<legend>` con `<fieldset>` para agrupar controles relacionados.

### Ejemplo de Etiquetas

```html
<label for="nombre">Tu nombre:</label>
<input type="text" id="nombre" name="nombre">
```

### Ejemplo de Grupo de Controles

```html
<fieldset>
  <legend>Información de Contacto</legend>
  <label for="email">Correo Electrónico:</label>
  <input type="email" id="email" name="email">
</fieldset>
```

## Tipos de Entrada y Teclados Dinámicos

Los tipos de entrada determinan qué teclado aparece en dispositivos móviles. Por ejemplo, un campo de entrada de tipo `tel` muestra un teclado numérico, mientras que `email` muestra un teclado con `@`.

```html
<input type="tel" name="telefono">
<input type="email" name="correo">
```

## Cómo Acceder al Micrófono y a la Cámara

Para subir archivos, usar el tipo de entrada `file` permite a los usuarios seleccionar archivos desde su dispositivo.

```html
<input type="file" name="archivo">
```

## Validación Integrada en Formularios HTML

En la web, los formularios son como los exámenes en los que nos aseguramos de que la información que ingresamos es correcta antes de enviarla. Sin necesidad de JavaScript, HTML puede ayudar a evitar que se envíen formularios con datos inválidos. Imagina que estás armando un formulario para inscripciones y necesitas asegurarte de que cada campo se complete correctamente. Aquí es donde entra la validación integrada.

### Selectores CSS y Atributos HTML

#### Analogía del Semáforo

Piensa en los selectores CSS como un semáforo para los controles de formularios. Cada tipo de luz (roja, amarilla, verde) representa un estado del formulario:
- **:required** y **:optional** son como las luces de advertencia. Te indican si un campo es obligatorio o no.
- **:default** es como una luz verde fija. Muestra si un campo tiene un valor predeterminado.
- **:enabled** y **:disabled** son los indicadores de tráfico que te dicen si un campo es interactivo o no.
- **:read-write** y **:read-only** son como la señal de "se puede escribir" o "solo lectura".

#### Ejemplos de CSS

Aquí tienes un ejemplo para deshabilitar el botón de envío si el formulario no es válido:

```css
form:invalid [type="submit"] {
  opacity: 50%;
  pointer-events: none;
}
```

Este código puede parecer intuitivo, pero en realidad, deshabilitar el botón de envío de esta manera puede confundir a los usuarios. Es mejor proporcionar mensajes de error claros en lugar de simplemente deshabilitar el botón.

### Validación del Formulario

#### Analogía del Inspector de Seguridad

La validación integrada funciona como un inspector de seguridad que revisa cada campo del formulario antes de enviarlo:
- **:valid** y **:invalid** son como los permisos de seguridad. Si todo está en orden, el campo es verde; si no, es rojo.
- **:in-range** y **:out-of-range** revisan si los valores numéricos están dentro del rango permitido, como un medidor de temperatura que asegura que el termostato esté en un rango seguro.

#### Mensajes de Error

Si un campo es obligatorio y está vacío, el navegador mostrará un mensaje de error diciendo que el campo es necesario. Si un valor numérico está fuera del rango permitido, aparecerá un mensaje de error relacionado con ese problema.

### Atributos de Validación

#### Analogía del Libro de Reglas

Cada atributo HTML para validación actúa como una regla en un libro de instrucciones:
- **required**: El campo es obligatorio. Si no se completa, el formulario no se envía.
- **minlength** y **maxlength**: Establecen el número mínimo y máximo de caracteres permitidos. Imagínalos como las páginas mínimas y máximas de un libro.
- **pattern**: Define un patrón que el valor debe seguir. Piensa en ello como las reglas para escribir una contraseña segura.

#### Ejemplo de Código HTML

Aquí tienes un formulario de ejemplo con validación integrada:

```html
<dialog open>
  <form method="post" action="thankyou.php">
    <label for="name">Nombre:</label>
    <input type="text" id="name" name="name" required>
    
    <label for="email">Correo electrónico:</label>
    <input type="email" id="email" name="email" required>
    
    <label for="age">Edad:</label>
    <input type="number" id="age" name="age" min="1" max="100" step="1" required>
    
    <button type="submit">Enviar</button>
    <button type="button" formmethod="dialog" formnovalidate aria-label="close">Cerrar</button>
  </form>
</dialog>
```

En este formulario, el primer botón cierra el diálogo sin enviar datos, mientras que el segundo botón envía los datos del formulario si todo es válido.

### Consideraciones Adicionales

#### Analogía del Asesor de Formulario

Al diseñar formularios, imagina que estás actuando como un asesor que ayuda a los usuarios a completar el formulario correctamente. Asegúrate de:
- Incluir instrucciones claras y útiles.
- Proporcionar retroalimentación precisa sobre errores.
- Considerar las diferentes formas en que los usuarios pueden ingresar datos.

Recuerda, HTML puede hacer mucho por sí solo en términos de validación y accesibilidad. Utilizar JavaScript para personalizar mensajes de error o agregar funcionalidades adicionales puede mejorar aún más la experiencia del usuario.

# Imágenes en HTML: Una Guía Sencilla

## Objetivo

Este módulo es una descripción general de alto nivel sobre cómo manejar imágenes en HTML, con el objetivo de hacer estos conceptos más comprensibles mediante analogías y explicaciones técnicas. Si quieres profundizar en el tema, visita el curso [Aprende a usar imágenes](#).

## Imágenes Decorativas vs. Imágenes de Contenido

Imagina que estás decorando una habitación. Los **gradientes de fondo** en botones o las **imágenes de fondo** en una sección de tu habitación son como los adornos en las paredes: son decorativos y deben aplicarse con **CSS** (como colgar un cuadro en la pared). Pero cuando una **imagen** es parte fundamental de la decoración o del contenido, como una foto en un álbum, debe ser parte del **HTML** (como colocar una foto en un marco sobre la mesa).

## Usando la Etiqueta `<img>`

El método principal para incluir imágenes en HTML es usando la etiqueta `<img>`, que es como poner una foto en tu álbum. 

```html
<img src="images/eve.png" alt="Eve">
```

Aquí, `src` es la ruta donde está guardada la imagen (como la dirección de tu casa donde se encuentra la foto), y `alt` es una breve descripción de la imagen (como la nota que pones al pie de la foto para que sepas quién está en ella).

## Imágenes Responsivas

Supongamos que tienes un marco de fotos que puede cambiar de tamaño según el lugar donde lo pongas. De manera similar, en HTML, puedes usar el atributo `srcset` para proporcionar diferentes versiones de una imagen según la resolución de la pantalla y el tamaño del viewport.

```html
<img src="images/eve.png" alt="Eve"
  srcset="images/eve.png 400w, images/eve-xl.jpg 800w"
  sizes="(max-width: 800px) 400px, 800px" />
```

Aquí, `srcset` es como tener diferentes tamaños de fotos para diferentes marcos, y `sizes` es como decidir qué tamaño de foto va en qué marco según el tamaño de la pared.

## Usando `<picture>` para Más Opciones

El elemento `<picture>` es como tener un álbum de fotos con varias páginas. Puedes ofrecer varias versiones de la misma imagen para diferentes escenarios.

```html
<picture>
  <source src="images/eve.png" media="(max-width: 800px)" />
  <source src="images/eve-xl.jpg" />
  <img src="images/eve.png" alt="Eve" />
</picture>
```

En este caso, `<source>` es como las diferentes páginas del álbum que ofrecen diferentes fotos dependiendo del contexto (tamaño de pantalla, formato, etc.).

## Carga Diferida

Imagina que tienes un montón de fotos y solo quieres ver las que están frente a ti. La carga diferida (`loading="lazy"`) permite que las imágenes se carguen solo cuando están a punto de aparecer en la vista, como mirar un álbum de fotos solo cuando pasas la página.

```html
<img src="switch.svg" alt="light switch" loading="lazy" />
```

Esto ayuda a mejorar el rendimiento de la página, especialmente en dispositivos móviles con conexiones lentas.

## Relación de Aspecto

Es como si quisieras reservar espacio para una foto en un álbum. Los atributos `height` y `width` en `<img>` ayudan a reservar el espacio correcto para la imagen, evitando que la página "salte" mientras se carga la imagen.

```html
<img src="switch.svg" alt="light switch" role="img" width="70" height="112" />
```

Esto asegura que el diseño de la página se mantenga estable mientras la imagen se carga.

## Descripción de Imágenes Alt

Cuando escribas el texto alternativo (`alt`) para una imagen, piensa en qué información es útil para alguien que no puede ver la imagen. Por ejemplo, en lugar de decir "Esta es una imagen de un perro con un sombrero rojo", simplemente di "Perro con sombrero rojo" si eso es lo que importa en el contexto.

```html
<img src="switch.svg" alt="light switch" role="img" />
```

Para íconos y gráficos, el texto alternativo debe describir la función del ícono en lugar de su apariencia.

## Otras Características

Las imágenes en HTML también pueden usar atributos adicionales como `crossorigin`, `decoding`, y `referrerpolicy` para mejorar la compatibilidad y seguridad. Además, el atributo `ismap` se usa en imágenes de mapas para enviar coordenadas del clic.

# Audio y Video en HTML: Una Guía con Analogías

## Introducción

Como aprendiste en el módulo de imágenes, HTML permite incorporar contenido multimedia en una página web. En esta sección, analizaremos los archivos de audio y video, incluidos los conceptos básicos sobre cómo integrarlos en tus páginas web, cómo usar los controles del usuario, y cómo asegurarte de que tu contenido multimedia sea accesible para todos.

## Incorporación de Audio y Video

### ¿Cómo funciona?

Imagina que estás construyendo una casa. Las etiquetas `<audio>` y `<video>` en HTML son como las puertas de entrada y ventanas de tu casa, permitiendo que los visitantes vean y escuchen el interior. Estas etiquetas te permiten incorporar reproductores multimedia directamente en tu página web.

#### Ejemplo de `<video>`

```html
<video src="videos/machines.webm" poster="images/machine.jpg" controls>
  <p>Watch <a href="https://youtube.com/link">video on Youtube</a></p>
</video>
```

En este ejemplo, el `<video>` es como una ventana en tu casa que muestra un video. El atributo `src` es la dirección del video (como el cristal de la ventana), `poster` es la imagen que se muestra antes de que el video comience (como una cortina que cubre la ventana), y `controls` añade botones para pausar, reproducir y ajustar el volumen (como una persiana que puedes ajustar).

### Contenido Alternativo

Siempre incluye contenido alternativo dentro de las etiquetas `<video>` o `<audio>`. Esto es como dejar una nota en la ventana para las personas que no pueden ver el video, diciéndoles qué hacer si la ventana está rota.

#### Ejemplo con contenido alternativo

```html
<video controls poster="images/machine.jpg">
  <source src="videos/machines.webm" type="video/webm">
  <source src="videos/machines.mp4" type="video/mp4">
  <source src="videos/machines.ogv" type="video/ogg">
  <p>Watch <a href="https://youtube.com/link">video on Youtube</a></p>
</video>
```

Aquí, usamos varias fuentes de video (como tener diferentes tipos de ventanas en la misma casa) para asegurarnos de que el video se muestre en todos los navegadores.

### Atributos y Códecs

El atributo `type` en la etiqueta `<source>` indica al navegador qué tipo de video está viendo. Esto es como etiquetar los tipos de vidrio en tus ventanas, para que cada tipo de ventana se coloque en el lugar correcto.

```html
<source src="videos/machines.webm" type="video/webm;codecs=vp8,vorbis">
<source src="videos/machines.mp4" type="video/mp4; codecs=avc1.4d002a">
```

### Aspecto del Video

El atributo `poster` es la imagen que se muestra antes de que comience el video, como una carátula en un álbum. Asegúrate de que la relación de aspecto del video y del póster coincidan para evitar que el video se ajuste incorrectamente cuando se reproduce.

### Accesibilidad

Para las personas que no pueden oír, puedes agregar subtítulos y descripciones. Esto es como ofrecer un libro de instrucciones en Braille para los visitantes que no pueden ver bien.

#### Ejemplo de subtítulos y descripciones

```html
<video controls poster="images/machine.jpg">
  <source src="videos/machines.webm" type="video/webm">
  <source src="videos/machines.mp4" type="video/mp4">
  <source src="videos/machines.ogv" type="video/ogg">
  <track label="English" kind="subtitles" srclang="en" src="vtt/subtitles-en.vtt" default />
  <track label="Francais" kind="subtitles" srclang="fr" src="vtt/subtitles-fr.vtt" />
  <p>Watch <a href="https://youtube.com/link">video on Youtube</a></p>
</video>
```

Los archivos de pista deben estar en formato WebVTT (.vtt), y puedes agregar subtítulos, transcripciones, y descripciones para hacer que tu contenido sea accesible para todos.

### Videos de Fondo

A veces, los diseñadores quieren un video de fondo que no tenga controles visibles. Esto es como poner una pantalla de presentación en la oficina sin botones para cambiar el canal. Asegúrate de que estos videos no interfieran con la accesibilidad y considera ofrecer controles si es necesario.

#### Ejemplo de video de fondo

```html
<video autoplay loop muted poster="images/machine.jpg" role="none">
  <source src="videos/machines.webm" type="video/webm">
  <source src="videos/machines.mp4" type="video/mp4">
  <source src="videos/machines.ogv" type="video/ogg">
</video>
```

### Controles Multimedia Personalizados

Si quieres crear controles personalizados, es como diseñar tus propias herramientas para abrir y cerrar las ventanas. Puedes usar JavaScript para agregar botones que reproduzcan o pausen el audio.

#### Ejemplo de botón personalizado

```html
<button id="playPause" aria-controls="idOfAudio"
  data-pause-text="Pause audio"
  data-play-text="Play audio">Pause audio</button>
```

```javascript
const pauseButton = document.getElementById('playPause');

pauseButton.addEventListener("click", pauseAndPlay, false);

function pauseAndPlay() {
  const media = document.getElementById(this.getAttribute('aria-controls'));

  if (media.paused) {
    media.play();
    this.innerText = this.dataset.pauseText;
  } else {
    media.pause();
    this.innerText = this.dataset.playText;
  }
}
```

# Plantilla, Ranura y Sombra en Componentes Web

## Introducción

Los componentes web permiten crear elementos reutilizables que se pueden integrar fácilmente en aplicaciones existentes. Utilizando HTML, CSS y JavaScript, podemos crear componentes que encapsulan tanto la estructura como el estilo, y que se comportan de manera independiente del resto de la página. Vamos a explorar tres conceptos clave en este proceso: **plantillas**, **ranuras** y **Shadow DOM**.

## Componentes Web: Una Analogía

Imagina que estás construyendo un set de **bloques de LEGO**. Cada bloque tiene una forma y color específicos, y puedes combinarlos de diferentes maneras para crear estructuras únicas. Los componentes web funcionan de manera similar: puedes construir un componente (como un widget de calificación) y luego reutilizarlo en diferentes partes de tu aplicación, combinándolo con otros "bloques" para construir una interfaz completa.

## Plantilla

El **elemento `<template>`** en HTML es como una caja de herramientas en tu set de LEGO. Dentro de la caja (o plantilla), tienes todos los bloques que necesitas para construir una parte de tu estructura, pero la caja en sí no se muestra en tu construcción final. Solo cuando decides usar los bloques y construir algo nuevo, estos se hacen visibles.

```html
<template id="star-rating-template">
  <form>
    <fieldset>
      <legend>Rate your experience:</legend>
      <rating>
        <input type="radio" name="rating" value="1" aria-label="1 star" required />
        <input type="radio" name="rating" value="2" aria-label="2 stars" />
        <input type="radio" name="rating" value="3" aria-label="3 stars" />
        <input type="radio" name="rating" value="4" aria-label="4 stars" />
        <input type="radio" name="rating" value="5" aria-label="5 stars" />
      </rating>
    </fieldset>
    <button type="reset">Reset</button>
    <button type="submit">Submit</button>
  </form>
</template>
```

En este ejemplo, la plantilla define un formulario de calificación con estrellas, pero este formulario no se renderiza hasta que se use JavaScript para tomar el contenido de la plantilla y agregarlo al DOM.

## Ranura

El **elemento `<slot>`** actúa como una caja de almacenamiento donde puedes colocar diferentes tipos de piezas (o contenido). Piensa en las ranuras como los espacios específicos en los bloques de LEGO donde puedes insertar otras piezas para personalizar tu construcción.

```html
<template id="star-rating-template">
  <form>
    <fieldset>
      <slot name="star-rating-legend">
        <legend>Rate your experience:</legend>
      </slot>
      <rating>
        <input type="radio" name="rating" value="1" aria-label="1 star" required />
        <input type="radio" name="rating" value="2" aria-label="2 stars" />
        <input type="radio" name="rating" value="3" aria-label="3 stars" />
        <input type="radio" name="rating" value="4" aria-label="4 stars" />
        <input type="radio" name="rating" value="5" aria-label="5 stars" />
      </rating>
    </fieldset>
    <button type="reset">Reset</button>
    <button type="submit">Submit</button>
  </form>
</template>
```

Aquí, el `<slot>` permite insertar un elemento personalizado (como una leyenda diferente) en el lugar definido dentro del componente.

## Shadow DOM

El **Shadow DOM** es como una caja de LEGO que has sellado, asegurándote de que las piezas dentro de ella no puedan ser modificadas desde el exterior. Esto significa que el estilo y el comportamiento de los componentes dentro de esta caja son independientes del resto de la página.

```javascript
customElements.define('star-rating', class extends HTMLElement {
  constructor() {
    super();
    const starRating = document.getElementById('star-rating-template').content;
    const shadowRoot = this.attachShadow({ mode: 'open' });
    shadowRoot.appendChild(starRating.cloneNode(true));
  }
});
```

En este código, se define un nuevo elemento `<star-rating>` que usa el contenido de la plantilla dentro de un Shadow DOM. Esto asegura que los estilos y el contenido del componente no se vean afectados por el CSS externo.

### Estilos Encapsulados

Dentro del Shadow DOM, puedes definir estilos que solo afectan al contenido de ese componente, sin interferir con el resto del documento.

```html
<template id="star-rating-template">
  <style>
    rating {
      display: inline-flex;
    }
    input {
      appearance: none;
      margin: 0;
      box-shadow: none;
    }
    input::after {
      content: '\2605'; /* solid star */
      font-size: 32px;
    }
    input:invalid::after {
      color: #ddd;
    }
    input:valid {
      color: orange;
    }
    input:checked ~ input:not(:checked)::after {
      color: #ccc;
      content: '\2606'; /* hollow star */
    }
  </style>
  <!-- Form content -->
</template>
```

Aquí, los estilos definidos en el Shadow DOM no afectan al resto del documento, y viceversa.

# APIs de HTML

En esta guía, exploraremos las APIs de HTML utilizando analogías simples para entender cómo funcionan los elementos del DOM (Document Object Model) y sus respectivas interfaces. Estas analogías te ayudarán a visualizar conceptos técnicos de manera clara y accesible.

## El DOM y el AOM: El Mapa de Nuestra Página Web

### El DOM: El Árbol Familiar

Imagina que tu página web es como un gran árbol en un parque. Cada rama y hoja de este árbol representa un nodo en el DOM. El DOM es como un mapa que muestra la estructura de todos los elementos (nodos) en tu documento web. Cada nodo puede tener "ramas" (nodos hijos) o ser una hoja en sí misma (sin nodos hijos).

- **Ejemplo**: Piensa en una página web como un árbol de Navidad. Las ramas principales son los elementos más grandes como `<header>`, `<main>`, y `<footer>`. Dentro de cada rama, puedes tener decoraciones (nodos hijos) como `<h1>`, `<p>`, y `<img>`.

### El AOM: El Árbol de Accesibilidad

Ahora, imagina que hay una versión especial de este árbol que está diseñada para ser más accesible para todos, como una versión con etiquetas en braille para personas con discapacidad visual. Este árbol especial es el árbol de accesibilidad (AOM). Se basa en el DOM pero añade detalles adicionales para ayudar a la accesibilidad.

## API de Elementos HTML: Herramientas para Manipular el Árbol

### Objetos en el Árbol

En nuestro árbol, cada nodo es como un objeto en una tienda de juguetes. Puedes manipular estos objetos utilizando JavaScript, como si estuvieras cambiando las decoraciones de tu árbol de Navidad.

#### Accediendo a Atributos

Cada objeto (nodo) tiene propiedades específicas que puedes consultar o modificar. Por ejemplo, si quieres saber el `alt` (texto alternativo) de todas las imágenes en tu página, puedes hacer lo siguiente:

```javascript
let allImages = document.querySelectorAll('img');
allImages.forEach((imageInstance) => {
  console.log(imageInstance.alt);
});
```

Esto es como revisar el nombre de cada adorno en tu árbol de Navidad.

#### Consultando Propiedades de Diseño

También puedes obtener información sobre el tamaño de las secciones de tu página web, como medir la altura de cada sección:

```javascript
let allSections = document.querySelectorAll('section');
allSections.forEach((sectionInstance) => {
  console.log(sectionInstance.offsetHeight);
});
```

Es como medir la altura de cada rama del árbol para asegurarte de que todas encajen perfectamente.

### Interfaces de Elementos HTML: Tipos de Objetos

Cada tipo de nodo tiene una "identidad" específica, como si cada juguete en la tienda tuviera una etiqueta que dice qué tipo es. Algunas de las interfaces más comunes incluyen:

- **HTMLAnchorElement** para `<a>`
- **HTMLImageElement** para `<img>`
- **HTMLInputElement** para `<input>`

Estas interfaces son como las etiquetas de los juguetes que te dicen cómo usarlos.

### Métodos y Propiedades

Algunos métodos y propiedades se heredan de otros. Por ejemplo, la propiedad `length` en una colección de elementos puede tener diferentes significados según el contexto, como el tamaño de una caja de juguetes comparado con la cantidad de juguetes dentro.

### Otras Interfaces

Algunas interfaces adicionales te permiten manipular nodos específicos del DOM:

- **EventTarget**: Como un control remoto para manejar eventos.
- **Node**: Como una herramienta para recorrer y modificar el árbol, similar a usar una escalera para ajustar las decoraciones del árbol.

## Interfaces Document y Window: El Entorno de Trabajo

### Interfaz Document

La interfaz `Document` es como el plano general de tu página web, permitiéndote acceder a toda la información sobre los nodos en tu árbol y manipular colecciones de elementos específicos.

- **Ejemplo**: `document.body` te da acceso a la parte principal del cuerpo de la página, como si tuvieras el plano del árbol y pudieras ver cada parte del árbol claramente.

### Interfaz Window

La interfaz `Window` es como el entorno general donde se encuentra tu árbol. Permite manipular la ventana del navegador y acceder a información global, como el tamaño de la ventana o el dispositivo en uso.

- **Ejemplo**: `window.resizeTo()` es como ajustar el tamaño del árbol de Navidad para que encaje perfectamente en tu sala.

# Enfoque y Navegación en Frontend: Un Viaje a Través del Tabulador

## Introducción

Imagina que estás navegando por una página web como si fuera un laberinto. Los elementos interactivos (como botones, enlaces y formularios) son las puertas por las que puedes pasar, mientras que otros elementos están cerrados o bloqueados. Este laberinto tiene un orden específico en el que puedes moverte, y tu tarea es asegurarte de que todos puedan navegarlo fácilmente.

## La Navegación por Tabulador: ¿Cómo Funciona?

### Enfoque Predeterminado

Por defecto, los elementos interactivos en una página web son como puertas que puedes abrir con la tecla Tab. Estas puertas están en el mismo orden en que están dispuestas en el laberinto (el código fuente), y el tabulador te permite moverte de una a otra de manera secuencial.

**Analogía:** Imagina que el tabulador es una llave mágica que te permite abrir puertas en el orden en que están colocadas. Si cambias el orden de las puertas, pero usas la misma llave, te perderás en el laberinto.

### Atributos HTML para Controlar el Enfoque

1. **`tabindex`**: Este atributo es como una guía que te dice en qué orden debes abrir las puertas. Un valor de `0` te permite abrir la puerta en el orden normal, mientras que un valor positivo (`1`, `2`, etc.) te pone en una fila especial de puertas prioritarias. Un valor negativo (`-1`) hace que la puerta sea inaccesible con el tabulador, pero aún puedes abrirla con la tecla de acceso directo (si conoces la combinación).

2. **`contenteditable`**: Es como una etiqueta que le dice a la puerta que puede ser modificada. Si pones `contenteditable="true"`, ahora puedes escribir en esa puerta. Esto hace que la puerta sea accesible con la tecla Tab, pero solo si también tiene `tabindex="0"`.

3. **`autofocus`**: Imagina que cuando entras al laberinto, la primera puerta que ves es automáticamente la que se abre. `autofocus` hace que esto ocurra con el primer elemento enfocable en la página cuando se carga. Sin embargo, es un poco caprichoso, y a veces puede causar confusión si no se usa con cuidado.

### Cómo Evitar el Caos en la Navegación

Si cambias el orden de las puertas de manera confusa con CSS, podrías tener un laberinto desordenado. Por ejemplo, si usas CSS para cambiar la posición de una puerta sin ajustar el orden del tabulador, los usuarios podrían encontrarse perdidos, tratando de encontrar su camino en un laberinto que no sigue el orden visual.

**Ejemplo Visual de Problemas:**

- **Con `tabindex` Caótico:** Si colocas un valor alto en `tabindex`, los usuarios seguirán un orden inesperado que puede hacer que se confundan.
  
- **Con CSS Caótico:** Si usas propiedades de CSS como `flex-flow: row-reverse;` para cambiar el orden visual, pero no ajustas el `tabindex`, el orden de navegación por teclado se desincroniza con el orden visual, creando una experiencia frustrante.

### Cómo Hacer que las Puertas Inactivas sean Inertes

Si quieres que algunas puertas no se puedan abrir con la tecla Tab, usa `tabindex="-1"`. Estas puertas siguen allí, pero no se pueden abrir con la llave mágica. Para hacer que una puerta sea completamente inaccesible, puedes usar `disabled` o `inert`.

1. **`disabled`**: Es como poner un cartel de "cerrado" en la puerta. Los usuarios no pueden abrirla ni siquiera con clics.

2. **`inert`**: Es como cerrar con llave la puerta y también el cuarto entero. No solo la puerta está cerrada, sino que todo lo que está dentro también está inaccesible.

**Nota:** Aunque `inert` es poderoso, no da señales visuales de que la puerta está cerrada, lo que puede ser confuso. Siempre asegúrate de que sea obvio para los usuarios que una puerta está inactiva.

## Consejos Finales

- **Mantén el Orden:** Asegúrate de que el orden de tabulación siga el orden visual siempre que sea posible.
- **Hazlo Claro:** Usa estilos CSS como `:focus` para que los usuarios vean qué puerta está actualmente abierta.
- **Prueba:** Navega por tu página con el teclado y asegúrate de que todo esté en orden.

Siguiendo estos principios, podrás crear un laberinto de navegación que sea intuitivo y accesible para todos los usuarios.

# Elementos de Texto Intercalados en HTML

HTML es como el idioma en el que hablamos con los navegadores. Aunque fue creado para compartir documentos, tiene muchas herramientas para mostrar información de manera clara y organizada. En este artículo, exploraremos algunos elementos de texto intercalados que nos ayudan a hacer que nuestros documentos sean más significativos y entendibles.

## **Elementos Básicos de Texto Intercalado**

Imagina que HTML es como un cuaderno de notas. Algunos elementos son como herramientas específicas para hacer anotaciones importantes y diferenciarlas del resto del texto.

### **1. `<code>` y `<pre>`**

Cuando queremos mostrar un fragmento de código en nuestro cuaderno, utilizamos el elemento `<code>`. Es como usar una fuente de letra monoespaciada para que el código se vea claro y ordenado. Si tenemos varias líneas de código, las encerramos en `<pre>`, que es como un contenedor especial que mantiene el formato del código tal cual.

```html
<pre>
<code>
function sayHello() {
  console.log('Hello, World!');
}
</code>
</pre>
```

### **2. `<data>` y `<time>`**

Piensa en `<data>` como una etiqueta con una traducción automática. Si tienes una fecha o un número, puedes usar `<time>` para darle un formato que las computadoras puedan entender fácilmente, como un calendario o un motor de búsqueda.

```html
<time datetime="2024-09-25">25 de septiembre de 2024</time>
```

### **3. `<samp>`, `<kbd>`, y `<var>`**

- **`<samp>`** es como mostrar un resultado de una máquina o programa. Imagina que tienes una impresora que muestra un mensaje, `<samp>` lo representa.

- **`<kbd>`** se usa para mostrar entradas del teclado. Es como si escribieras en tu cuaderno qué teclas debes presionar.

- **`<var>`** se usa para variables en matemáticas o programación, como escribir un símbolo que puedes cambiar más adelante.

```html
<kbd>Ctrl + C</kbd>
<var>x</var>
```

## **Elementos para Mostrar Cambios y Anotaciones**

Al igual que en un cuaderno de notas, a veces necesitamos marcar cambios o hacer anotaciones.

### **4. `<del>` y `<ins>`**

- **`<del>`** es como usar una línea para tachar un texto que ya no es válido. Puedes añadir una nota sobre por qué se eliminó y cuándo.

- **`<ins>`** es el opuesto. Es como escribir una nota nueva en el margen, agregando texto que antes no estaba.

```html
<p>El texto anterior fue <del>eliminado</del> y reemplazado por <ins>nuevo texto</ins>.</p>
```

### **5. `<sup>` y `<sub>`**

- **`<sup>`** es para superíndices, como los números pequeños arriba en las fórmulas matemáticas.

- **`<sub>`** es para subíndices, como los números pequeños abajo en las fórmulas.

```html
<p>La fórmula del agua es H<sub>2</sub>O y la potencia de dos es 2<sup>2</sup>.</p>
```

### **6. `<s>`**

El elemento **`<s>`** se usa para marcar texto que ya no es relevante. Es como poner una línea a través de una nota antigua que ya no necesitamos.

```html
<p>Este texto es <s>obsoleto</s> y ya no se usa.</p>
```

## **Elementos de Texto Especial**

Algunas veces necesitamos anotar o enfatizar ciertas partes del texto para que se destaquen.

### **7. `<em>`, `<mark>`, `<strong>`, y `<cite>`**

- **`<em>`** es como usar un resaltador para enfatizar algo. Cuanto más anidado esté, más énfasis tiene.

- **`<mark>`** es para resaltar información relevante, como marcar términos importantes en un documento.

- **`<strong>`** es para resaltar algo muy importante. Los navegadores suelen hacerlo en negrita.

- **`<cite>`** es para citar títulos de libros, artículos u obras.

```html
<p>Este es un <em>texto enfatizado</em> y este es un <mark>texto resaltado</mark>. Además, el libro <cite>HTML para Todos</cite> es muy útil.</p>
```

## **Elementos para Definir Términos y Idiomas**

Cuando estamos aprendiendo o explicando algo nuevo, a veces necesitamos definir términos o mencionar diferentes idiomas.

### **8. `<abbr>`, `<dfn>`, `<bdi>`, `<bdo>`, `<ruby>`, `<rt>`, y `<rp>`**

- **`<abbr>`** se usa para definir abreviaturas y siglas.

- **`<dfn>`** es para definir un término nuevo.

- **`<bdi>`** y **`<bdo>`** ayudan a manejar textos en idiomas que se leen de derecha a izquierda.

- **`<ruby>`**, **`<rt>`**, y **`<rp>`** se usan para mostrar anotaciones sobre caracteres en idiomas como el japonés.

```html
<abbr title="Hypertext Markup Language">HTML</abbr>
<dfn>Frontend</dfn> es el diseño y desarrollo de la parte visible de una aplicación web.
```

## **Elementos de Espacio en Blanco**

Finalmente, para manejar el espacio en blanco en tu documento, puedes usar:

### **9. `<br>`, `<hr>`, y `<wbr>`**

- **`<br>`** es como agregar una línea nueva, ideal para direcciones o poesía.

- **`<hr>`** es como dibujar una línea horizontal para separar secciones.

- **`<wbr>`** sugiere dónde puede dividirse una palabra larga si es necesario.

```html
<address>
1234 Elm Street<br>
Springfield, IL 62704
</address>

<p>Este es un texto largo con <wbr>posibles puntos de ruptura.</p>
```

# Detalles y resumen

## Introducción a los Widgets de Divulgación

Imagina que estás organizando una fiesta en tu casa y tienes una caja llena de juegos. Decides usar una caja especial con tapa para que los invitados puedan ver rápidamente qué juegos están disponibles sin tener que abrir la caja cada vez. Este mecanismo de abrir y cerrar la tapa es similar a lo que hacen los widgets de divulgación en HTML.

### ¿Qué es un Widget de Divulgación?

Un widget de divulgación es como una caja con una tapa que puedes abrir y cerrar para mostrar o ocultar contenido. En la web, esto se logra utilizando los elementos `<details>` y `<summary>`. Estos elementos permiten que parte del contenido esté oculto hasta que el usuario decida verlo.

## Cómo Funcionan `<details>` y `<summary>`

1. **Elemento `<details>`**: Piensa en `<details>` como la caja que contiene el contenido oculto. Este elemento actúa como el contenedor principal que puede estar abierto o cerrado.
2. **Elemento `<summary>`**: Este es como el botón en la caja que, cuando se presiona, abre o cierra la tapa. El `<summary>` sirve como un resumen o título que permite al usuario expandir o contraer el contenido dentro del `<details>`.

Cuando haces clic en el `<summary>`, el `<details>` se expande para mostrar el contenido que estaba oculto.

## Ejemplo Práctico

```html
<details>
  <summary>¿Qué es HTML?</summary>
  <p>HTML (HyperText Markup Language) es el estándar para crear páginas web y aplicaciones. Es un lenguaje de marcado que estructura el contenido en la web.</p>
</details>
```

En el ejemplo anterior, "¿Qué es HTML?" es el título que los usuarios pueden hacer clic para ver más información sobre HTML.

## Activar o Desactivar la Visibilidad

### Atributo `open`

El atributo `open` en `<details>` funciona como un interruptor. Si está presente, la caja (contenedor) está abierta y el contenido es visible. Si no está presente, la caja está cerrada y el contenido está oculto.

```html
<details open>
  <summary>¿Qué es HTML?</summary>
  <p>HTML es el lenguaje estándar para crear páginas web.</p>
</details>
```

En este caso, la caja estará abierta cuando se cargue la página, mostrando el contenido por defecto.

## Estilización con CSS

Puedes estilizar el `<summary>` para que se vea como quieras. Por ejemplo, puedes cambiar la flecha que indica si el contenido está abierto o cerrado. Es como cambiar la apariencia del botón en la tapa de la caja para que se vea más atractivo.

```css
details summary::before {
  content: "▶"; /* Triángulo apuntando a la derecha */
  display: inline-block;
  margin-right: 5px;
}

details[open] summary::before {
  content: "▼"; /* Triángulo apuntando hacia abajo */
}
```

Aquí, el triángulo apunta hacia la derecha cuando el contenido está oculto y hacia abajo cuando está visible.

## Manejo de Errores y Compatibilidad

Si no usas `<summary>`, el navegador insertará uno por ti con el texto "details". Sin embargo, es mejor proporcionar tu propio `<summary>` para un control más preciso y para mantener la accesibilidad. Los navegadores pueden manejar de manera diferente el contenido interactivo dentro de `<summary>`, así que asegúrate de probar en varios navegadores.

## Interacción con JavaScript

Aunque los elementos `<details>` y `<summary>` funcionan bien con HTML y CSS, a veces querrás usar JavaScript para manejar comportamientos más complejos. Por ejemplo, puedes querer cerrar otros detalles abiertos cuando se abre uno nuevo:

```javascript
document.querySelectorAll('details').forEach(detail => {
  detail.addEventListener('toggle', () => {
    if (detail.open) {
      document.querySelectorAll('details').forEach(otherDetail => {
        if (otherDetail !== detail) {
          otherDetail.removeAttribute('open');
        }
      });
    }
  });
});
```

Este script asegura que solo un detalle esté abierto a la vez.

# Diálogo

## Resumen

Un diálogo modal es como una ventana emergente que interrumpe al usuario en una página web para que se enfoque en ella. Imagina que estás en una reunión y alguien te pide que prestes atención a un documento específico; eso es lo que hace un diálogo modal en el mundo digital. A diferencia de otras ventanas emergentes, los diálogos modales bloquean temporalmente el resto del contenido en la página hasta que el usuario interactúe con ellos.

## Diálogos Modales

### Concepto

Un diálogo modal es como un cartel en la oficina que cubre toda la pared. Mientras el cartel está allí, no puedes ver ni interactuar con nada más en la oficina. Para continuar trabajando, necesitas retirar el cartel. En términos de web, esto significa que el diálogo modal se superpone a todo el contenido de la página y desactiva la interacción con otros elementos.

### Implementación

En HTML, el elemento `<dialog>` se utiliza para crear estos diálogos. Aquí está el código básico para un diálogo modal:

```html
<dialog id="myDialog">
  <p>Este es un diálogo modal</p>
  <button id="closeDialog">Cerrar</button>
</dialog>
```

Puedes abrir un diálogo modal usando JavaScript:

```javascript
const dialog = document.getElementById('myDialog');
dialog.showModal(); // Abre el diálogo como modal
```

Y cerrarlo con:

```javascript
dialog.close(); // Cierra el diálogo
```

Cuando un diálogo modal se abre con el método `showModal()`, el enfoque se mueve automáticamente al contenido del diálogo. Esto es como si te pidieran que te enfoques completamente en el cartel sin distraerte con otros objetos en la oficina.

### Interacciones

- **Cerrar con la tecla Escape:** Al igual que cerrar un cartel cuando ya no lo necesitas, presionar la tecla Escape cierra el diálogo modal.
- **Formulario:** Si el diálogo contiene un formulario con `method="dialog"`, enviar el formulario también cierra el diálogo.
- **Método `.close()`:** Este método de JavaScript también puede usarse para cerrar el diálogo.

### Ejemplo de código

```html
<dialog open>
  <form method="dialog">
    <button type="submit" autofocus>close</button>
  </form>
</dialog>
```

El atributo `autofocus` en el botón asegura que se enfoque automáticamente cuando el diálogo se abre, igual que si el cartel se iluminara para llamar tu atención al entrar en la oficina.

## Diálogos No Modales

### Concepto

Un diálogo no modal es como una ventana en la oficina que puedes abrir y cerrar a voluntad, pero que no oculta ni desactiva el resto de la oficina. A diferencia del diálogo modal, puedes seguir interactuando con otros elementos en la página mientras el diálogo está abierto.

### Implementación

Para crear un diálogo no modal, usas el método `show()` en lugar de `showModal()`. Aquí está el código:

```html
<dialog id="nonModalDialog">
  <p>Este es un diálogo no modal</p>
  <button id="closeNonModalDialog">Cerrar</button>
</dialog>
```

```javascript
const nonModalDialog = document.getElementById('nonModalDialog');
nonModalDialog.show(); // Abre el diálogo sin modal
```

A diferencia del diálogo modal, el diálogo no modal no oscurece el fondo ni bloquea la interacción con otros elementos.

## Cómo Cerrar un Diálogo

### Sin JavaScript

Puedes cerrar un diálogo sin JavaScript usando un formulario:

```html
<dialog open>
  <form method="dialog">
    <button type="submit" autofocus>close</button>
  </form>
</dialog>
```

El formulario se envía con `method="dialog"`, lo que cierra el diálogo y mantiene el estado de los datos ingresados.

### Con JavaScript

```javascript
const dialog = document.querySelector('dialog');
dialog.close(); // Cierra el diálogo
```

### Atributo `autofocus`

El atributo `autofocus` asegura que el primer elemento enfocable dentro del diálogo reciba el enfoque automáticamente cuando el diálogo se abre. Es como si un cartel en la oficina tuviera una luz que indica dónde debes mirar primero.

## Consideraciones Adicionales

### No Usar `tabindex`

No añadas `tabindex` al `<dialog>` en sí, ya que el diálogo no debe recibir enfoque.

### Roles ARIA

- **`role="dialog"`**: Para diálogos estándar.
- **`role="alertdialog"`**: Para diálogos que requieren una confirmación o una respuesta importante.

### Configuración Predeterminada de CSS

Cada navegador puede tener estilos predeterminados para los diálogos. Por ejemplo, Firefox y Chrome establecen `color: CanvasText` y `background-color: Canvas`, mientras que Safari usa `color: black` y `background-color: white`.

```css
dialog {
  /* Estilos predeterminados */
}
```
