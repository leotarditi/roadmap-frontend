# Introducción al Diseño Web Adaptable

## El Desafío del Diseño Web en la Web Moderna

### ¿Cómo llegó todo hasta aquí?

Desde el inicio de la World Wide Web, la accesibilidad fue un pilar fundamental. A lo largo de los años, la Web evolucionó y, con ella, los dispositivos desde los que la accedemos. En los primeros días, la mayoría de los usuarios accedían desde computadoras de escritorio, pero hoy, navegamos desde una multitud de dispositivos: teléfonos, tablets, laptops, incluso desde automóviles o refrigeradores. Entonces, ¿cómo aseguramos que una página web se vea bien en todos estos dispositivos?

La respuesta es el **diseño adaptable**. Este concepto ha sido clave para que las páginas web funcionen y se vean bien, sin importar el tamaño o tipo de dispositivo que se utilice.

### Analogía: Vestir a la Medida

Imagina que tienes que vestir a 100 personas que varían en forma y tamaño. No puedes crear un solo conjunto de ropa para todos porque no se adaptará bien. La solución es hacer prendas que cambien de forma para ajustarse a cada persona. Esto es exactamente lo que hace el diseño web adaptable: permite que una página web ajuste su diseño dependiendo del tamaño del dispositivo, tal como una prenda que se ajusta a la medida de quien la usa.

## La Evolución del Diseño Web

### Diseños de Ancho Fijo

En los inicios del diseño web, las pantallas de las computadoras eran pequeñas y tenían resoluciones muy específicas (640px x 480px). Los diseñadores creaban páginas que encajaban perfectamente en esas dimensiones. Esto es lo que llamamos **diseño de ancho fijo**.

#### Analogía: El Túnel Estrecho

Es como si diseñaras un túnel que solo tiene un ancho específico. Si intentas meter algo más grande por ese túnel, se atasca. Y si metes algo más pequeño, queda mucho espacio sin utilizar. En un diseño de ancho fijo, si el usuario tenía una pantalla más grande, sobraba espacio en los lados. Si era más pequeña, el contenido no cabía y aparecían barras de desplazamiento.

### Diseños Líquidos

A medida que las pantallas comenzaron a variar más en tamaño, los diseñadores empezaron a experimentar con **diseños líquidos**. Estos diseños ajustaban sus columnas según el ancho disponible de la pantalla, en lugar de usar valores fijos.

#### Analogía: La Goma Elástica

Un diseño líquido es como una goma elástica. Puede estirarse o encogerse según el espacio disponible. Pero al igual que una goma elástica, puede perder su forma si se estira demasiado o se encoge demasiado. En pantallas muy anchas, el diseño se sentía estirado, y en pantallas estrechas, se comprimía demasiado.

### Diseños Adaptables

Con la llegada de más dispositivos, los diseñadores comenzaron a usar **diseños adaptables**, que creaban varias versiones del mismo diseño, cada una adaptada a un ancho de pantalla específico.

#### Analogía: Ropa de Tallas

El diseño adaptable es como tener un conjunto de prendas en diferentes tallas (S, M, L). Si ves a alguien que necesita una talla específica, le das la más cercana que tienes. Funciona bien, pero no es perfecto. Si alguien necesita una talla intermedia, no encaja a la perfección y termina con ropa que es un poco demasiado grande o pequeña.

### El Nacimiento del Diseño Web Responsivo

En 2010, Ethan Marcotte introdujo el concepto de **diseño web responsivo**, que combina lo mejor de los diseños líquidos y las consultas de medios.

#### Analogía: La Prenda Inteligente

Imagina ahora una prenda que no solo se estira o encoge, sino que también ajusta su estilo y forma según el cuerpo de quien la lleva. No solo cambia su tamaño, también decide cómo redistribuir los botones, bolsillos, o ajusta su longitud. Esto es el diseño web responsivo. No solo cambia de tamaño según la pantalla, sino que redistribuye los elementos para ofrecer la mejor experiencia en cada dispositivo.

## Herramientas Claves en el Diseño Web Responsivo

### Consultas de Medios (Media Queries)

Las **consultas de medios** permiten aplicar reglas CSS dependiendo del tamaño de la pantalla del dispositivo.

#### Analogía: El Sastre Personal

Las consultas de medios son como un sastre que ajusta la prenda según las medidas exactas de la persona. Dependiendo del tamaño de la pantalla, el sastre (consulta de medios) ajusta los elementos del diseño para que todo encaje perfectamente.

### Cuadrículas Fluidas y Medios Fluidos

El uso de **cuadrículas fluidas** y **medios fluidos** garantiza que las imágenes y las secciones de un sitio web se ajusten automáticamente al tamaño de la pantalla.

#### Analogía: Un Edificio Flexible

Es como un edificio que puede cambiar su estructura interna según el número de personas que lo visiten. Si hay mucha gente, se expande. Si hay menos, se contrae. Pero siempre mantiene su solidez estructural, sin importar cuántas personas haya dentro.

### Meta Viewport

El **meta viewport** es un elemento crucial para decirle a los navegadores móviles que respeten el ancho de la pantalla y no hagan zoom automático en la página.

#### Analogía: Ajustar la Ventana

Es como ajustar el tamaño de una ventana en tu casa. Si es muy pequeña, tienes que acercarte para ver lo que hay afuera. El meta viewport asegura que la ventana se ajuste al tamaño adecuado para que puedas ver claramente sin necesidad de hacer zoom.

## Conclusión

El diseño web adaptable ha recorrido un largo camino desde los días de los diseños de ancho fijo. Hoy, gracias a técnicas como el diseño responsivo y las consultas de medios, podemos crear sitios web que se ven y funcionan bien en cualquier dispositivo. Tal como una prenda hecha a la medida o un edificio que se ajusta a las necesidades de sus ocupantes, los sitios web modernos están diseñados para ofrecer la mejor experiencia posible, sin importar el dispositivo desde el cual se accedan.

---

# Consultas de Medios

## Analogía: Ajustando la vestimenta según el clima

Imagina que sales de casa todos los días y que tu atuendo depende del clima. Si está soleado, usarías ropa ligera. Si llueve, te pones una campera impermeable. Si hace frío, sumas una bufanda y guantes. En diseño web, sucede algo similar: las consultas de medios actúan como esa lógica que te ayuda a decidir qué ponerte según las condiciones del día. Solo que, en lugar del clima, estamos ajustando cómo se ve un sitio web según el dispositivo o la pantalla del usuario.

---

## ¿Qué son las consultas de medios?

Las consultas de medios (`@media`) en CSS permiten que el diseño de una página web se adapte según las características del dispositivo del usuario. De la misma manera que te adaptarías al clima, el sitio web se "pone la ropa" adecuada según el dispositivo, ya sea un teléfono móvil, una tablet o una impresora. 

Un ejemplo claro es cómo se ajusta el diseño según el tamaño de la ventana o si el contenido será impreso.

### Ejemplo técnico:

```css
body {
  color: black;
  background-color: grey;
}

@media print {
  body {
    background-color: transparent;
  }
}
```

**¿Qué hace este código?** 
El sitio se ve con un fondo gris en pantalla, pero al imprimirlo, el fondo se vuelve transparente. De esta manera, ahorras tinta, como si te quitaras una capa de ropa innecesaria cuando entras a un lugar cerrado.

---

## Tipos de medios y cómo usarlos

Así como te pones diferentes tipos de ropa dependiendo del clima (chomba en verano, campera en invierno), en CSS podemos definir tipos de medios como `print` (para impresión) o `screen` (para pantallas), usando la regla `@media`.

```html
<link rel="stylesheet" href="global.css">
<link rel="stylesheet" href="print.css" media="print">
```

Si no especificas un medio, el navegador asume que el diseño es para **todos** los medios (`all`), que es como vestirte para cualquier ocasión sin tener en cuenta el clima.

---

## Condiciones en las consultas de medios

Las consultas de medios también permiten agregar **condiciones**, como si dijéramos: "Si hace frío **y** está lloviendo, entonces me pongo la campera **y** el paraguas".

En diseño, esto se traduce a aplicar diferentes estilos dependiendo del **tamaño de la pantalla** o la **orientación del dispositivo**. Un ejemplo es ajustar el diseño si el usuario está usando su dispositivo en modo horizontal (landscape) o vertical (portrait).

### Ejemplo técnico:

```css
@media (orientation: landscape) {
  /* Estilos para modo horizontal */
}

@media (orientation: portrait) {
  /* Estilos para modo vertical */
}
```

---

## Puntos de interrupción (breakpoints)

Volviendo a nuestra analogía del clima, un **punto de interrupción** sería el momento exacto en que decides cambiar tu ropa. Si hace 15°C, quizás te pongas un abrigo ligero. Si baja a 5°C, es hora de algo más grueso. En diseño web, usamos puntos de interrupción para decidir cuándo aplicar diferentes estilos dependiendo del **ancho** o **alto** de la pantalla.

### Ejemplo técnico:

```css
@media (min-width: 50em) {
  article {
    column-count: 2;
  }
}
```

Aquí, si el ancho de la pantalla es mayor a 50em (unas 800px aproximadamente), el texto del artículo se divide en dos columnas. Es como si decidieras que, cuando hace suficiente frío, te pones dos capas de ropa en lugar de una.

---

## Combinaciones de condiciones

Puedes combinar varias condiciones, como si dijeras: "Si está soleado **y** hace calor, entonces uso gafas de sol y una remera". En CSS, esto se hace usando `and`.

### Ejemplo técnico:

```css
@media (min-width: 50em) and (min-height: 60em) {
  article {
    column-count: 2;
  }
}
```

Aquí, los estilos de dos columnas solo se aplican si la pantalla es lo suficientemente ancha **y** alta. De esta manera, aseguras que el diseño sea cómodo para leer, sin importar cómo el usuario sostenga su dispositivo.

---

## Conclusión

Las consultas de medios son como un armario bien organizado. Permiten que los diseñadores cambien la apariencia de un sitio web dependiendo del "clima" (el dispositivo o las preferencias del usuario). Y como buen diseñador, tienes que asegurarte de que tu sitio siempre esté bien "vestido" para cada ocasión.

---

# Internacionalización (i18n)

La World Wide Web está disponible para todas las personas en todo el mundo, ¡lo dice su nombre! Eso significa que tu sitio web puede ser visitado por cualquier persona que tenga acceso a Internet, sin importar en qué parte del planeta estén, qué dispositivo usen o qué idioma hablen.

Imagina que tienes un puesto de comidas en un parque. Al principio, solo ofreces menús en español porque es el idioma que hablas. Pero un día llegan turistas de diferentes partes del mundo: algunos hablan inglés, otros francés, otros japonés. Si solo tienes menús en español, esas personas no podrán entender qué ofreces, ¡y probablemente se vayan a otro lugar! Aquí es donde entra la **internacionalización (i18n)**. Lo que hace es asegurarse de que tus menús (tu contenido y diseño) estén preparados para ser fácilmente traducidos y adaptados a diferentes públicos, sin importar su idioma o cultura.

## Propiedades lógicas: Flexibilidad para todo tipo de escritura

Pensemos ahora en cómo escribimos: en español o inglés escribimos de izquierda a derecha (como cuando lees un libro o navegas por internet). Pero no todas las lenguas funcionan así. En árabe o hebreo, por ejemplo, se escribe de derecha a izquierda, y en algunos casos, como en el japonés, se puede escribir incluso de arriba hacia abajo. ¡Todo esto afecta el diseño de tu página web!

### Analogía: Redecorar una casa según el invitado
Imagina que tu sitio web es una casa y que estás recibiendo invitados de diferentes culturas. Si vienen invitados que leen de derecha a izquierda, sería como reorganizar los muebles y cuadros para que todo tenga sentido para ellos. Aquí es donde entran las **propiedades lógicas** de CSS. Estas propiedades son como un rediseño automático que se adapta según la forma en la que tus invitados (los usuarios) leen.

En CSS, probablemente ya usaste propiedades direccionales como `left` (izquierda), `right` (derecha), `top` (arriba) e `bottom` (abajo). Esas propiedades son como señalar físicamente dónde colocar un mueble en tu casa. Sin embargo, las **propiedades lógicas** no dependen de la dirección, sino del flujo de contenido. Es decir, el mueble (o el contenido en tu sitio) se coloca en un lugar lógico que cambia dependiendo del idioma que esté usando el visitante.

#### Ejemplo de propiedades lógicas
En lugar de decir "pon un margen a la izquierda" (`margin-left`), podrías decir "pon un margen al inicio de la línea" (`margin-inline-start`). Este margen estará en el lado izquierdo si el idioma va de izquierda a derecha, y en el lado derecho si el idioma va de derecha a izquierda.

```css
/* Antes */
label {
  margin-right: 0.5em;
}

/* Ahora, usando propiedades lógicas */
label {
  margin-inline-end: 0.5em;
}
```

### El uso de estas propiedades te ahorra mucho trabajo
Si preparas tu sitio con propiedades lógicas, no necesitarás rediseñar tu página cada vez que la traduzcas a un idioma nuevo. Por ejemplo, no tendrás que ajustar manualmente los márgenes o la alineación del texto para idiomas como el árabe o el hebreo.

#### Ejemplo de "mover los muebles" automáticamente

```html
<html dir="rtl">
<!-- El contenido de esta página se mostrará de derecha a izquierda -->
</html>
```

### Consejos prácticos
- **No uses imágenes con texto.** Si lo haces, tendrás que crear imágenes diferentes para cada idioma. Mejor coloca el texto por separado usando CSS.
- **Cuidado con las palabras largas.** Algunos idiomas, como el alemán, tienen palabras muy largas, y tu diseño debe tener espacio suficiente para ellas.
- **Usa fuentes adecuadas.** Asegúrate de que la fuente que eliges para tu web soporte caracteres de varios idiomas, incluyendo acentos y otros signos diacríticos.

## Identificación del idioma de la página

Al igual que cuando organizas una fiesta y preparas comida para tus invitados según sus gustos y preferencias, es útil que le indiques al navegador qué idioma usas en tu sitio web para que se ajuste de manera adecuada.

```html
<html lang="en">
<!-- Declaramos que esta página está en inglés -->
</html>
```

Incluso puedes ser más específico, como declarar que es inglés de Estados Unidos:

```html
<html lang="en-us">
<!-- Especificamos inglés de EE.UU. -->
</html>
```

## Publicaciones en diferentes idiomas

Si tienes versiones de tu sitio en diferentes idiomas, como si ofrecieras menús en varios idiomas en tu restaurante, usa el atributo `hreflang` para asegurarte de que los motores de búsqueda y los navegadores entiendan cuál es la versión correcta de la página.

```html
<a href="/path/to/german/version" hreflang="de">German version</a>
```

También puedes agregar este atributo en el `head` de tu documento para vincular traducciones:

```html
<link href="/path/to/german/version" rel="alternate" hreflang="de">
```

## Conclusión: Piensa globalmente, diseña inteligentemente

Al pensar en la internacionalización desde el principio, no solo haces que tu sitio sea más accesible, sino que también te ahorras tiempo a largo plazo. Al usar **propiedades lógicas** en CSS y definir el idioma de tu página correctamente, preparas tu contenido para un público global sin tener que hacer rediseños importantes. ¡Es como tener una casa lista para recibir a cualquier invitado sin importar de qué parte del mundo venga!

---

# Diseños Macro en Frontend

En este artículo, vamos a desglosar uno de los conceptos esenciales en el desarrollo frontend: los **diseños macro**. Los diseños macro se refieren a la organización de los grandes bloques de una página, es decir, cómo se distribuyen los principales componentes de la interfaz a nivel general. Vamos a utilizar una analogía simple para hacerlo más entendible:

## Analogía: El Puzzle Gigante
Imagina que tienes un rompecabezas gigante, donde las piezas son muy grandes y debes colocarlas en un marco. Lo primero que haces es poner las piezas más grandes en su lugar para definir la estructura general. Este es tu **diseño macro**: cómo colocas los bloques principales de contenido en tu página. 

Por ejemplo, en un sitio web típico, tendrías secciones como la cabecera, el contenido principal, la barra lateral (si hay) y el pie de página. Organizar estas secciones de manera clara y lógica es como armar las esquinas y bordes de tu rompecabezas. Una vez que tienes esto resuelto, puedes enfocarte en los detalles más pequeños.

```html
<body>
  <header>…</header>
  <main>
    <article>…</article>
    <aside>…</aside>
  </main>
  <footer>…</footer>
</body>
```

Este esquema básico es la estructura de cualquier página web. Como las pantallas tienen diferentes tamaños (móviles, tabletas, ordenadores), el reto es hacer que este "puzzle" se vea bien sin importar el tamaño de la pantalla. Ahí es donde entra en juego el diseño responsive.

### Consultas de medios: Adaptando el diseño

La clave para lograr un diseño que se vea bien en todos los dispositivos es hacer que el rompecabezas se ajuste automáticamente al tamaño del marco (pantalla). Para eso, usamos las **consultas de medios** en CSS. Estas nos permiten aplicar diferentes estilos en función del tamaño del dispositivo.

Ejemplo: Supongamos que queremos que en pantallas grandes el contenido se muestre en dos columnas, mientras que en pantallas pequeñas se muestre en una sola columna.

```css
@media (min-width: 45em) {
  main {
    display: grid;
    grid-template-columns: 2fr 1fr;
  }
}
```

### Cuadrícula CSS: Organizándolo todo

**Cuadrícula CSS** es una herramienta poderosa que actúa como un tablero donde colocamos las piezas del puzzle. Al definir una cuadrícula, estamos diciendo al navegador cómo organizar los bloques principales de la página. Siguiendo con la analogía del puzzle, es como dividir el tablero en secciones más claras para saber exactamente dónde encaja cada pieza.

```css
@media (min-width: 45em) {
  main {
    display: grid;
    grid-template-columns: 2fr 1fr;
  }
}
```

En este ejemplo, definimos que cuando el ancho de la pantalla sea de al menos 45em, el contenido se organizará en dos columnas: una que ocupe dos tercios del espacio (2fr) y otra que ocupe el tercio restante (1fr).

### Flexbox: Alternativa flexible

Otra herramienta útil es **Flexbox**, que se asemeja a una cuerda elástica. Imagina que tienes varias piezas del puzzle que necesitan acomodarse en una línea, pero algunas pueden estirarse o encogerse según el espacio disponible. Flexbox permite hacer esto de manera sencilla.

```css
@media (min-width: 45em) {
  main {
    display: flex;
    flex-direction: row;
  }

  main article {
    flex: 2;
  }

  main aside {
    flex: 1;
  }
}
```

En este caso, el contenido también se divide en dos partes, pero con Flexbox, tenemos más control sobre cómo se distribuyen y adaptan los elementos según el espacio disponible.

### ¿Siempre necesitas consultas de medios?

No siempre es necesario usar consultas de medios para ajustar el diseño. En lugar de especificar puntos de interrupción (como 30em, 45em, etc.), podemos hacer que el navegador se encargue de calcular automáticamente cuántos elementos caben en cada línea. 

Por ejemplo, supongamos que tienes un grupo de tarjetas que siempre deben tener un tamaño máximo de 15em. Puedes usar la propiedad **grid-template-columns** con **auto-fill** para hacer que el diseño se ajuste automáticamente según el espacio disponible.

```css
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(15em, 1fr));
  grid-gap: 1em;
}
```

Con esta regla, el navegador coloca tantas tarjetas como sea posible en una fila, sin que tengas que preocuparte por definir exactamente cuándo deben cambiar de tamaño.

### Flexbox también puede ayudar

También puedes hacer esto con Flexbox. La diferencia es que Flexbox estirará las tarjetas si no hay suficientes para llenar una fila completa.

```css
.cards {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  gap: 1em;
}
.cards .card {
  flex-basis: 15em;
  flex-grow: 1;
}
```

### Conclusión

El diseño macro es como armar las piezas grandes de un rompecabezas en una página web. Puedes usar herramientas como Cuadrícula CSS o Flexbox para asegurarte de que estos bloques se organicen bien en cualquier tamaño de pantalla. Recuerda que, al planificar el diseño general, es importante pensar en cómo el contenido fluye en diferentes tamaños de pantalla y dispositivos, de modo que tu rompecabezas siempre se vea completo sin importar el tamaño del marco.

Puedes explorar más diseños fluidos sin consultas de medios en [1linelayouts.com](https://1linelayouts.com).

---

# Microdiseños

Cuando pensamos en diseños, a menudo los imaginamos a nivel de página, como un cuadro grande donde se organizan los elementos. Sin embargo, los componentes más pequeños dentro de la página también pueden tener sus propios diseños independientes, como pequeñas piezas de un rompecabezas que deben encajar de manera eficiente en diferentes configuraciones.

## Diseño Adaptable

Lo ideal es que estos microdiseños se ajusten automáticamente, independientemente de su posición en la página. Imagina que tienes un componente que puede ser como una caja de juguetes: no importa si lo pones en la sala de estar, en la habitación o en el jardín; la caja debe ser capaz de ajustarse y acomodar todos los juguetes sin importar el lugar donde esté.

Si no se sabe con seguridad dónde terminará un componente, se debe asegurar que el componente pueda adaptarse a su contenedor. Por ejemplo, un diseño de dos columnas, una ancha y otra angosta, presenta objetos multimedia de forma diferente según su ubicación.

### Cuadrícula

La cuadrícula de CSS no se usa solo para los diseños a nivel de página, también es eficaz para los componentes que residen en ellos. 

```css
h1 {
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  gap: 1em;
}

h1::before,
h1::after {
  content: "";
  border-top: 0.1em double black;
  align-self: center;
}
```

En este ejemplo, los seudoelementos `::before` y `::after` crean líneas decorativas al lado de un encabezado. El encabezado es un contenedor de cuadrícula, y los elementos individuales se organizan de manera que las líneas siempre ocupen el espacio disponible.

### Flexbox

Como su nombre indica, puedes usar **flexbox** para hacer que tus componentes sean flexibles. Puedes declarar qué elementos de tu componente deben tener un tamaño mínimo o máximo y dejar que los demás elementos se flexionen para ajustarse.

```css
.media {
  display: flex;
  align-items: center;
  gap: 1em;
}
.media-illustration {
  flex: 1;
  max-inline-size: 200px;
}
.media-content {
  flex: 3;
}
```

En este ejemplo, la imagen ocupa un cuarto del espacio disponible y el texto ocupa los otros tres cuartos. Sin embargo, la imagen nunca supera los 200 píxeles. Esto permite que el componente se ajuste sin importar el tamaño del contenedor.

### Consultas de Contenedores

**Flexbox** te permite diseñar desde el contenido. Puedes especificar los parámetros de tus elementos (qué tan estrechos deben ser, qué tan anchos deben ser) y dejar que el navegador averigüe la implementación final.

Sin embargo, el componente en sí no tiene conocimiento de su contexto. Imagina que tu componente es como un artista que no sabe si actuará en un pequeño café o en un gran estadio. Esto puede hacer que los diseños de componentes sean más complicados que los diseños de página. Para poder aplicar estilos contextualmente relevantes, los componentes deben tener más información que el tamaño del viewport.

Para informar sobre las dimensiones de cualquier contenedor, puedes usar consultas de contenedores:

```css
main,
aside {
  container-type: inline-size;
}
```

Esto significa que quieres consultar la dimensión intercalada, que en inglés es el eje horizontal. Cambiarás los estilos según el ancho del contenedor.

```css
.media-illustration {
  max-width: 200px;
  margin: auto;
}

@container (min-width: 25em) {
  .media {
    display: flex;
    align-items: center;
    gap: 1em;
  }

  .media-illustration {
    flex: 1;
  }

  .media-content {
    flex: 3;
  }
}
```

Si un objeto multimedia está dentro de un contenedor más angosto que 25em, los estilos de flexbox no se aplican, y la imagen y el texto aparecen ordenados verticalmente. Pero si el elemento que lo contiene es más ancho que 25em, la imagen y el texto se mostrarán en paralelo. Con las consultas de contenedores, puedes definir el diseño de los componentes de forma independiente; el ancho del viewport ya no importa.

### Combinar Consultas

Puedes usar consultas de medios para el diseño de la página y consultas de contenedor para los componentes dentro de la página. Por ejemplo:

```html
<body>
  <main>
     <div class="media">…</div>
     <div class="media">…</div>
  </main>
  <aside>
     <div class="media">…</div>
  </aside>
</body>
```

Una consulta de medios aplica un diseño de cuadrícula a los elementos `main` y `aside` cuando el viewport es más ancho que 45em:

```css
@media (min-width: 45em) {
  body {
    display: grid;
    grid-template-columns: 3fr 1fr;
  }
}
```

La regla de consulta de contenedor para los objetos multimedia sigue siendo la misma; solo aplica un diseño de flexbox horizontal si el elemento contenedor es más ancho que 25em.

### Conclusión

Las consultas a contenedores cambian las reglas del juego para los microdiseños. Los componentes pueden ser autónomos, independientemente del viewport del navegador. Esto te permite crear interfaces más flexibles y responsivas, facilitando la tarea del desarrollador y mejorando la experiencia del usuario.

---

# Typography

## Understanding Typography through a Simple Analogy

Imagine your web page is like a billboard. If the letters are too small, people driving by won’t be able to read them. If the letters are too big, it might get overwhelming, and no one will know what to focus on. Typography is about making your text not only readable but also pleasant to look at, just like balancing the size and style of the letters on your billboard.

When you're building a webpage, if you don’t set a font style, the browser will automatically choose one for you. This is similar to letting someone else decide the font for your billboard—they’ll make it readable, but it might not be what you wanted. To control this, you have to specify the text size, font, and line spacing yourself.

### Browser Defaults (User-Agent Stylesheets)
Each browser comes with its own set of "default" styles. If you don't specify your own, the browser uses its default font size, color, and spacing, just like if you rented a billboard and didn't specify any size or design—someone else would decide for you.

But here's the key: **users can also change these styles**. Some people prefer bigger fonts, while others might use a smaller one. It’s important to respect user preferences.

### Line Length & Readability
If a billboard stretches across an entire highway, it would be impossible to read if the letters go all the way from one side to the other. In web typography, we call this "line length." Ideally, text lines should not be too long or too short—somewhere between 45 to 75 characters per line is considered ideal for readability.

```css
article {
  max-inline-size: 66ch; /* Limits line length to 66 characters */
}
```
This code ensures that the text stays within a comfortable width for reading.

### Text Size and Screen Size
Just like you would make the letters bigger on a billboard that's far away, text on bigger screens should be larger. On smaller screens, like mobile devices, the text should be smaller so it fits well.

Here's how you can use **media queries** to adjust the size of text based on the screen width:

```css
@media (min-width: 30em) {
  html {
    font-size: 125%; /* Text gets bigger as screen width increases */
  }
}

@media (min-width: 60em) {
  html {
    font-size: 200%; /* Even larger for very wide screens */
  }
}
```

### Responsive Text Sizing
Sometimes, you want the text size to automatically adjust as the screen size changes, like making your billboard text bigger when viewed from far away and smaller when up close. For this, CSS provides the `vw` unit, which stands for viewport width (the size of the screen). However, using `vw` alone isn’t ideal, because it might make text too small or too large.

```css
html {
  font-size: calc(0.75rem + 1.5vw); /* Responsive font size */
}
```

### Controlling the Extremes with `clamp()`
To ensure your text doesn’t shrink too much on small screens or grow too large on big ones, you can use the `clamp()` function. This lets you define a minimum, a preferred size, and a maximum for your text size.

```css
html {
  font-size: clamp(1rem, 0.75rem + 1.5vw, 2rem);
}
```
Here, the text size will always be between 1rem (a comfortable default size) and 2rem, scaling based on the screen width.

### Line Height for Readability
Just as the spacing between billboards matters to avoid crowding, so does the space between lines of text. The **line-height** property controls this. For long lines, too much space can make the text harder to read. For short lines, you might want more spacing.

```css
article {
  line-height: 1.65; /* Sets comfortable spacing between lines */
}
```

### Web Fonts
Using custom web fonts is like choosing a specific font for your billboard instead of sticking with what’s available by default. Web fonts can add character to your website, but they come with a cost—slower load times, like waiting for the perfect paint to dry on your billboard.

```css
@font-face {
  font-family: 'Roboto';
  src: url('/fonts/roboto-regular.woff2') format('woff2');
}
```

To avoid slowing down the user’s experience, you can **preload** fonts and **swap** to them only after they're ready to ensure your text doesn’t remain invisible while waiting.

```html
<link href="/fonts/roboto-regular.woff2" rel="preload" as="font" crossorigin>
```

And to handle text switching smoothly, use:
```css
body {
  font-family: 'Roboto', sans-serif;
  font-display: swap;
}
```

### Variable Fonts: The All-in-One Solution
Variable fonts allow you to pack all styles (bold, italic, etc.) into a single file. This is like having multiple billboards (different styles) all in one—saving space while offering flexibility.

---

# Imágenes Responsivas

### ¿Qué pasa cuando agrandamos una imagen?
Imagina que tienes una foto y decides pegarla en la pared de tu cuarto. Si la pared es más pequeña que la foto, tendrás que doblarla para que encaje, lo que no es ideal porque te perderás parte de la imagen, ¿verdad? Bueno, en la web pasa algo similar.

El texto de una página web se ajusta automáticamente al tamaño de la pantalla, como si las letras supieran cómo acomodarse en el espacio disponible. Las imágenes, por otro lado, son un poco más rebeldes y, si no las controlamos, podrían salirse de los límites y hacer que tengas que "deslizarte" para verlas por completo, como si estuvieras moviendo la foto en tu pared con una lupa. 

#### ¿Cómo evitamos esto?
Afortunadamente, con CSS podemos "decirles" a las imágenes que se ajusten al tamaño del contenedor donde las colocamos, igual que si recortaras la foto para que siempre encaje en la pared de tu cuarto.

### Código básico para imágenes responsivas
```css
img {
  max-inline-size: 100%;
  block-size: auto;
}
```

### Analogía técnica:
- **max-inline-size**: Es como decirle a la imagen "Nunca seas más ancha que la pantalla o el espacio donde te coloqué".
- **block-size**: Mantiene el "tamaño de bloque", es decir, que la imagen conserve su altura original en relación con su ancho, evitando que se deforme.

### Navegadores compatibles:
- Chrome: 57+
- Edge: 79+
- Firefox: 41+
- Safari: 12.1+

---

## ¿Y qué pasa si la imagen se deforma?

A veces, cuando cargamos una imagen, podría aplastarse o estirarse para que encaje en un espacio. ¿Te ha pasado que ves una foto en tu celular y parece que a las personas las aplastaron o alargaron? Eso sucede porque no se mantiene la relación de aspecto de la imagen.

### Solución con `aspect-ratio`
Podemos usar una propiedad llamada `aspect-ratio` para asegurarnos de que la imagen mantenga su proporción original, como si dijéramos "Mantén la relación entre tu ancho y tu alto, ¡sin deformarte!"

```css
img {
  max-inline-size: 100%;
  block-size: auto;
  aspect-ratio: 2/1; /* Esto indica que el ancho siempre será el doble que el alto */
}
```

### Object-fit: Evita la compresión y estiramiento

En vez de forzar que la imagen encaje de cualquier forma, podemos usar `object-fit` para darle al navegador instrucciones sobre cómo encajar la imagen. Si alguna vez has recortado una foto para que solo quepa la parte más importante, esto es lo que hacemos con `object-fit`.

- **contain**: La imagen se ajusta al espacio disponible pero puede dejar áreas vacías.
- **cover**: La imagen llena todo el espacio, aunque tenga que cortar partes de la imagen.

```css
img {
  max-inline-size: 100%;
  block-size: auto;
  aspect-ratio: 2/1;
  object-fit: contain; /* O prueba con cover */
}
```

---

## Recortar una imagen con estilo

Si una parte específica de la imagen es la más importante (como la cara de una persona o un objeto), podemos usar `object-position` para asegurarnos de que esa parte quede visible. Imagina que tienes una foto grupal y quieres asegurarte de que siempre se vea la persona en el centro.

```css
img {
  max-inline-size: 100%;
  block-size: auto;
  aspect-ratio: 2/1;
  object-fit: cover;
  object-position: top center; /* Asegura que la parte superior de la imagen esté centrada */
}
```

---

## Optimizando la carga de imágenes

Ahora bien, cuando tenemos muchas imágenes en una página web, puede ser un problema que todas se carguen al mismo tiempo. ¡Es como si intentaras abrir todos tus regalos de cumpleaños a la vez! 😅 Para evitar esto, podemos usar el atributo `loading="lazy"` que le dice al navegador que no cargue la imagen hasta que sea realmente necesario (como cuando el usuario se desplaza hasta ese lugar en la página).

```html
<img src="image.png" alt="Descripción de la imagen" width="300" height="200" loading="lazy">
```

---

## Sugerencias para la precarga

Si tienes imágenes muy importantes en la parte superior de la página, como un banner principal, puedes decirle al navegador que las cargue con prioridad usando `fetchpriority="high"`. Esto es como decirle al navegador "¡Esta imagen es importante, tráela primero!"

```html
<img src="hero.jpg" alt="Imagen principal" width="1200" height="800" loading="eager" fetchpriority="high">
```

---

## ¿Por qué es importante todo esto?

La idea detrás de las imágenes responsivas es que tus usuarios no tengan que esperar más de lo necesario ni gastar datos innecesarios, especialmente si están usando un dispositivo móvil o una conexión lenta. Recuerda, ¡cada kilobyte cuenta!

Por lo tanto, es esencial no solo ajustar las imágenes a los diferentes tamaños de pantalla, sino también asegurarse de que se carguen de manera eficiente.

---

# El elemento de imagen

En el módulo anterior, aprendimos cómo el atributo `srcset` te permite proporcionar versiones de la misma imagen en diferentes tamaños, dándole al navegador la posibilidad de elegir la versión más adecuada. Sin embargo, si quieres cambiar la imagen por completo dependiendo del dispositivo o las condiciones, necesitarás el elemento `picture`.

## ¿Cómo funciona el elemento `picture`?

Imagina que estás organizando una cena y, según el número de invitados, decides cambiar el tipo de comida. Si hay pocas personas, sirves algo simple como pizza, pero si llegan más, decides hacer un asado. Aquí, el elemento `picture` es como tú, tomando decisiones más grandes, y el elemento `img` es la comida que sirve la cena.

El `picture` se basa en el `img`, igual que en la cena dependes de la comida disponible. Si no tienes comida (no hay elemento `img`), ¡no puedes servir nada!

Ejemplo básico:
```html
<picture>
  <img src="image.jpg" alt="Descripción de la imagen.">
</picture>
```

## Control total con `picture`

Cuando usas `srcset`, le das sugerencias al navegador, como cuando le dices a un amigo que podría ser una buena idea traer algo a la cena. Pero con `picture`, no das sugerencias, ¡das órdenes! Tú tienes el control y decides qué imagen usar.

```html
<picture>
  <source srcset="image.avif" type="image/avif">
  <source srcset="image.webp" type="image/webp">
  <img src="image.jpg" alt="Descripción de la imagen." width="300" height="200" loading="lazy" decoding="async">
</picture>
```

### Analizando el código
Aquí el navegador primero intentará usar el formato `AVIF` (el asado), luego `WebP` (la pizza), y si no puede con ninguno, usará la imagen en formato `JPEG` (un sándwich simple). Es como tener opciones para tu cena según las condiciones.

## Cambiando tamaños de imagen

Otra ventaja del `picture` es que puedes cambiar la imagen dependiendo del tamaño de la pantalla, como cambiar la decoración de tu casa según la cantidad de gente que venga. Si tienes muchos invitados, pones más sillas; si son pocos, usas menos espacio.

Ejemplo:
```html
<picture>
  <source srcset="large.png" media="(min-width: 75em)">
  <source srcset="medium.png" media="(min-width: 40em)">
  <img src="small.png" alt="Descripción de la imagen." width="300" height="200" loading="lazy" decoding="async">
</picture>
```

En este caso, el navegador usará una imagen más grande si la pantalla es muy amplia (75em o más), una imagen mediana si la pantalla es intermedia (entre 40em y 75em) y una pequeña si la pantalla es pequeña.

## Controlando la densidad de píxeles

Piensa en esto como si tus invitados trajeran diferentes tipos de vasos a la cena. Si hay invitados con vasos grandes y resistentes (dispositivos con mayor densidad de píxeles), les sirves en esos. Si tienen vasos pequeños (menor densidad), les sirves en esos.

```html
<picture>
  <source srcset="large.png 1x" media="(min-width: 75em)">
  <source srcset="medium.png 1x, large.png 2x" media="(min-width: 40em)">
  <img src="small.png" alt="Descripción de la imagen." width="300" height="200" loading="lazy" decoding="async" srcset="small.png 1x, medium.png 2x, large.png 3x">
</picture>
```

Aquí, el navegador seleccionará la imagen adecuada no solo según el tamaño de la pantalla, sino también según la densidad de píxeles del dispositivo.

## Recortando imágenes

Si necesitas ajustar una imagen para que luzca mejor en diferentes dispositivos, puedes recortarla para que se vea bien tanto en pantallas pequeñas como grandes. Es como cortar un pastel: puedes servirlo en porciones pequeñas para los niños, pero cuando llegan los adultos, sirves una porción más grande.

```html
<picture>
  <source srcset="full.jpg" media="(min-width: 75em)" width="1200" height="500">
  <source srcset="regular.jpg" media="(min-width: 50em)" width="800" height="400">
  <img src="cropped.jpg" alt="Descripción de la imagen." width="400" height="400" loading="eager" decoding="sync">
</picture>
```

Aquí le estás diciendo al navegador que si la pantalla es grande (más de 75em), use una imagen completa, pero si la pantalla es mediana, use una imagen más pequeña. Y si la pantalla es muy pequeña, usa un recorte más estrecho.

## Conclusión

El elemento `picture` te da un control mucho más detallado sobre qué imágenes mostrar y cómo deben cambiar según el contexto, como el tamaño de la pantalla o el formato de imagen que soporte el navegador. Pero para la mayoría de los casos, `srcset` y `sizes` del `img` son suficientes, así que no siempre es necesario complicarse.

---

# Íconos y Gráficos en la Web

## Introducción a los Íconos
Piensa en los íconos como señales de tránsito en la web. Así como las señales te indican qué hacer en una carretera (frenar, girar, etc.), los íconos ayudan a los usuarios a navegar por una página web de forma intuitiva. Los íconos no son el contenido principal de la web, pero sí son fundamentales para que la interfaz de usuario sea clara y funcional.

Al igual que el texto en la interfaz de usuario, los íconos deben adaptarse y escalarse para verse bien en diferentes dispositivos y tamaños de pantalla. Un ícono mal dimensionado sería como una señal de tránsito que es tan pequeña que no la ves, o tan grande que te distrae. ¡Nadie quiere eso en la web!

## Gráficos Vectoriales Escalables (SVG)
Imagina que quieres hacer un cartel para un evento. Si lo diseñas usando una imagen tradicional (como un JPG o PNG), podrías necesitar crear diferentes versiones de tu cartel para que se vea bien en un afiche grande, en una invitación de bolsillo, o en una página web. Pero si usas un formato como SVG, es como tener una plantilla que puedes ampliar o reducir sin perder calidad.

- **PNG y JPG**: Son como un mosaico hecho de píxeles; si lo amplías demasiado, los píxeles se ven borrosos.
- **SVG**: Funciona como un diagrama técnico. No importa cuánto lo amplíes, siempre se verá nítido porque se basa en instrucciones de dibujo.

En lugar de usar múltiples versiones de un mismo ícono en diferentes tamaños, con un solo archivo SVG puedes tener un ícono que se ve perfecto en cualquier tamaño. ¡Menos trabajo, más claridad!

### Código de Ejemplo de un SVG:
```xml
<svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="-21 -21 42 42" width="100" height="100">
  <title>Carita sonriente</title>
  <circle r="20" fill="yellow" stroke="black"/>
  <ellipse rx="2.5" ry="4" cx="-6" cy="-7" fill="black"/>
  <ellipse rx="2.5" ry="4" cx="6" cy="-7" fill="black"/>
  <path stroke="black" d="M -12,5 A 13.5,13.5,0 0,0 12,5 A 13,13 0 0,1 -12,5"/>
</svg>
```

En este ejemplo, cada forma (círculo, elipses y líneas) tiene instrucciones claras para ser dibujada por el navegador, y no importa cuánto escales esta carita, siempre se verá bien.

## Íconos en la Interfaz de Usuario

### Íconos Presentacionales
Un ícono es como el "fondo" de la interfaz. Si tienes un botón con un texto que dice "Menú", el texto es lo más importante, y el ícono de las tres rayitas solo lo acompaña. Esto significa que el ícono es presentacional, su rol es estético, no informativo.

Ejemplo de código para íconos presentacionales:
```html
<button>
  <img src="hamburger.svg" alt="" width="16" height="16"> Menú
</button>
```
Nota: El atributo `alt=""` indica que la imagen es decorativa y no es necesario que un lector de pantalla lo lea.

### Íconos Independientes
Si decides usar un ícono sin texto, como el ícono de "hamburguesa" para un menú sin acompañarlo de la palabra "Menú", entonces el ícono ya no es solo decorativo, tiene un propósito funcional. Necesitamos asegurarnos de que las tecnologías de accesibilidad (como los lectores de pantalla) entiendan que este ícono tiene un significado.

Ejemplo de código con ícono accesible:
```html
<button aria-label="Menú">
  <img src="hamburger.svg" alt="">
</button>
```

### SVG y Accesibilidad
Si usas SVG directamente en el HTML, puedes tener control total sobre cómo se ve y cómo se comporta. Pero recuerda, si el ícono no es decorativo, debes hacerlo accesible. En este caso, podrías usar `aria-label` para darle un nombre accesible al ícono.

Ejemplo:
```html
<button aria-label="Menú">
  <svg aria-hidden="true" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 80" width="16" height="16">
    <rect width="100" height="20" />
    <rect y="30" width="100" height="20"/>
    <rect y="60" width="100" height="20"/>
  </svg>
</button>
```

## Estilos para Íconos SVG
Una gran ventaja de los SVG es que puedes cambiar su apariencia directamente con CSS, como si fuera cualquier otro elemento de tu página. Esto significa que puedes cambiar el color del ícono cuando el usuario pasa el mouse sobre él, o cuando recibe foco.

Ejemplo:
```css
button {
  color: blue;
}
button rect {
  fill: blue;
}

button:hover rect,
button:focus rect {
  fill: red;
}
```

En este ejemplo, el ícono cambia de color cuando el usuario interactúa con el botón.

## Conclusión
Usar íconos en la web es como usar señales para guiar a los usuarios, y con formatos como SVG, puedes asegurarte de que esas señales se vean claras y profesionales sin importar el tamaño. Además, el uso adecuado de íconos en la interfaz de usuario mejora la accesibilidad y la experiencia de todos los usuarios.

---

# Personalización del Navegador

## Temas

**Imagina que tu sitio web es como elegir la vestimenta adecuada para diferentes ocasiones.** Dependiendo de dónde estés (en la playa, una reunión o en casa), vas a elegir algo que se ajuste mejor a la situación. Lo mismo sucede con los sitios web: podemos adaptar su apariencia para que se ajusten al entorno y a las preferencias del usuario. En este artículo te explico cómo puedes hacer que tu sitio web se vea genial en cualquier contexto, incluso en el navegador que el usuario esté utilizando.

---

### Personaliza la Interfaz del Navegador

Así como puedes elegir un color que combine con tu vestimenta para cada ocasión, también puedes hacer que el navegador combine con los colores de tu sitio web. Algunos navegadores permiten cambiar su interfaz según el color que elijas para tu página. Para lograr esto, solo debes agregar un meta tag en tu archivo HTML.

```html
<meta name="theme-color" content="#00D494">
```

> **Concepto técnico:** Este código le dice al navegador qué color utilizar en su barra de navegación cuando cargue tu sitio. Aunque parezca raro poner un color directamente en HTML en lugar de CSS, esta técnica permite que el navegador adapte su color inmediatamente, sin esperar a que la CSS esté lista.

**¿Cuándo usar esto?** Es como si le dijeras al usuario: "Te doy la opción de personalizar un poco tu experiencia mientras navegas mi sitio". Esto puede ser genial, pero usa esta funcionalidad con moderación, ¡no querrás distraer al usuario con muchos cambios de color!

### Manifiesto de Aplicación Web

Si quieres llevar la experiencia al siguiente nivel, puedes hacer que tu sitio funcione como una app cuando el usuario lo guarde en su pantalla de inicio, al igual que si guardas un acceso directo a tu página favorita en el escritorio de tu computadora.

Para esto, necesitas un archivo especial llamado `manifest.json`, que contiene información básica sobre tu sitio:

```json
{
  "short_name": "Clearleft",
  "name": "Clearleft design agency",
  "start_url": "/",
  "background_color": "#00D494",
  "theme_color": "#00D494",
  "display": "standalone"
}
```

> **Concepto técnico:** El archivo de manifiesto le dice al navegador cómo debe presentarse tu sitio si lo agregan a la pantalla de inicio, mostrando el ícono y los colores que definiste. 

### Cómo Proporcionar un Modo Oscuro

Pensemos en esto como si tu sitio web fuera una sala que puede cambiar de luces brillantes a luces tenues, según las preferencias del usuario. Hoy en día, muchos sistemas operativos permiten elegir entre temas claros u oscuros, y tu sitio web debería adaptarse también. ¡No querrás que los ojos de tu visitante sufran si tienen activado el modo oscuro!

Puedes detectar la preferencia del usuario usando una consulta de medios llamada `prefers-color-scheme`.

```css
@media (prefers-color-scheme: dark) {
  /* Estilos para el tema oscuro */
  body {
    background-color: black;
    color: white;
  }
}
```

> **Concepto técnico:** `@media` es una herramienta poderosa que nos permite definir estilos específicos para diferentes situaciones, como el modo oscuro. Así, cuando el usuario tenga el modo oscuro activado, tu sitio se ajustará automáticamente para hacer su experiencia más cómoda.

### Propiedades Personalizadas en CSS

Piensa en las propiedades personalizadas de CSS como etiquetas adhesivas. En lugar de escribir el mismo color una y otra vez en diferentes lugares, colocamos estas etiquetas para reutilizar colores y otros valores.

```css
html {
  --page-color: white;
  --ink-color: black;
}

@media (prefers-color-scheme: dark) {
  html {
    --page-color: black;
    --ink-color: white;
  }
}

body {
  background-color: var(--page-color);
  color: var(--ink-color);
}
```

> **Concepto técnico:** Las propiedades personalizadas en CSS (también conocidas como variables CSS) son muy útiles para reducir la repetición de código. Al actualizar solo una variable, puedes cambiar el color en toda tu página.

### Imágenes y Modo Oscuro

Así como cambias la decoración de tu sala dependiendo de la hora del día, las imágenes de tu sitio también pueden cambiar en modo oscuro para mejorar la experiencia visual.

```html
<picture>
  <source srcset="darkimage.png" media="(prefers-color-scheme: dark)">
  <img src="lightimage.png" alt="Descripción de la imagen.">
</picture>
```

> **Concepto técnico:** El elemento `<picture>` permite cargar imágenes diferentes según las condiciones del navegador. Con `prefers-color-scheme`, puedes cambiar automáticamente entre imágenes claras y oscuras.

### Formularios y Estilos

Finalmente, es importante que todos los elementos, como los formularios, también se adapten al modo oscuro o claro. Imagina que los botones y campos de texto de un formulario son como el toque final en la decoración de tu sala; deben estar en armonía con el resto del entorno.

```css
html {
  color-scheme: light;
}

@media (prefers-color-scheme: dark) {
  html {
    color-scheme: dark;
  }
}
```

> **Concepto técnico:** La propiedad `color-scheme` en CSS le dice al navegador cómo estilizar los elementos de formulario predeterminados según el tema que prefiera el usuario.

---

### Conclusión

Adaptar tu sitio web a las preferencias del usuario es como asegurarse de que la decoración de tu sala esté lista para cualquier ocasión. Usando herramientas como `theme-color`, `prefers-color-scheme`, y variables CSS, puedes crear una experiencia más personalizada y cómoda para tus visitantes. ¡Recuerda usar estas técnicas de manera sutil y bien pensada para que el usuario siempre se sienta bienvenido!

---

# Accesibilidad

Permitir que tus páginas respondan a diferentes tamaños de pantalla es solo una forma de asegurarte de que la mayor cantidad posible de personas pueda acceder a tu sitio web. Considera algunos de estos otros factores que debes tener en cuenta.

## Deficiencia de la visión del color

Cada persona percibe el color de manera diferente, como si estuvieran viendo el mundo a través de diferentes lentes. Por ejemplo, una persona con **protanopia** no percibe el rojo como un color distintivo. Imagina que el rojo es un semáforo; para esta persona, parece que siempre está en verde. Con la **deuteranopia**, falta el verde, y para las personas con **tritanopia**, es el azul el que no pueden distinguir.

### Herramientas útiles:

- **Firefox**: La pestaña de accesibilidad incluye un menú desplegable que simula diferentes tipos de visión de color.
- **Chrome**: Las herramientas para desarrolladores permiten emular estas deficiencias.

### Consejos de diseño:

No debes confiar únicamente en el color para diferenciar elementos. Por ejemplo, al igual que un semáforo también emite sonidos, los vínculos deben tener un estilo adicional, como estar subrayados o en negrita, para que sean fácilmente identificables.

#### Qué no debes hacer:

```css
a {
  color: red;
}
```

#### Qué debes hacer:

```css
a {
  color: red;
  font-weight: bold;
}
```

## Contraste de color

Algunas combinaciones de colores pueden causar problemas. Si el texto y el fondo son similares, es como intentar leer un libro en la oscuridad: te cansas la vista y no puedes concentrarte. Afortunadamente, puedes detectar problemas de contraste desde el principio del proceso de diseño.

### Herramientas para probar el contraste:

- **tota11y**: Un bookmarklet que puedes añadir a tu barra de herramientas.
- **VisBug**: Extensión de navegador que facilita la edición visual.

### Mejores prácticas:

Siempre declara `color` y `background-color` juntos en tu CSS. No asumas que el color de fondo será el predeterminado del navegador, ya que los usuarios pueden personalizar sus colores.

#### Qué no debes hacer:

```css
body {
  color: black;
}
```

#### Qué debes hacer:

```css
body {
  color: black;
  background-color: white;
}
```

## Contraste alto

Algunas personas configuran sus sistemas operativos para usar un modo de contraste alto. Para estas personas, es como si estuvieran mirando un letrero iluminado en medio de la oscuridad; necesitan que el contraste sea fuerte para distinguir el texto.

### Configuración en Mac:

1. Preferencias del sistema
2. Accesibilidad
3. Display
4. Selecciona la opción para aumentar el contraste.

### CSS y contraste alto:

Puedes usar la función multimedia `prefers-contrast` para ajustar tu paleta de colores:

```css
@media (prefers-contrast: more) {
  /* Cambios de color para alto contraste */
}
```

## Tamaño de fuente

El tamaño de fuente también es esencial. Imagina que cada usuario es un lector con diferentes niveles de visión; algunos necesitan una lupa y otros pueden leer sin problemas. Puedes responder a esta necesidad usando tamaños de fuente relativos, como `rem` o `em`.

### Prueba la escalabilidad:

Intenta aumentar el tamaño de texto en tu navegador. ¿Tu sitio web sigue siendo funcional si el tamaño de fuente se duplica? Asegúrate de que la experiencia sea la misma tanto en computadoras de escritorio como en dispositivos móviles.

## Navegación con el teclado

No todos usan un mouse para navegar. Algunos se mueven por la página usando el teclado, similar a cómo un viajero podría seguir un mapa sin GPS. Asegúrate de que los elementos sean accesibles con el teclado.

### Mejores prácticas:

Utiliza las pseudoclases `:hover` y `:focus` para resaltar los enlaces, garantizando que sean visibles tanto con mouse como con teclado.

```css
a:focus,
a:hover {
  outline: 1px dotted;
}
```

## Movimiento reducido

Las animaciones pueden ser deslumbrantes, pero para algunas personas pueden causar mareos, como un viaje en un barco en aguas turbulentas. Usa la consulta de función `prefers-reduced-motion` para evitar que esos usuarios se sientan incómodos.

### Ejemplo de CSS:

```css
@media (prefers-reduced-motion: no-preference) {
  a {
    transition-duration: 0.4s;
    transition-property: transform;
  }
}
```

## Voz

Algunas personas no ven tu sitio web en una pantalla. Utilizan tecnologías de asistencia, como lectores de pantalla, que convierten el texto en voz. Es crucial que tu HTML sea semántico y esté bien estructurado para que estas herramientas funcionen eficazmente.

### Importancia de la estructura:

Usa encabezados de manera correcta, como `<h1>`, `<h2>`, etc. Los lectores de pantalla dependen de estos encabezados para navegar por tu contenido.

#### Qué no debes hacer:

```html
<div class="heading-main">Welcome to my page</div>
```

#### Qué debes hacer:

```html
<h1>Welcome to my page</h1>
```

## Estructura

Emplea elementos de referencia como `<main>`, `<nav>`, `<aside>`, `<header>`, y `<footer>` para estructurar tu contenido. Esto ayuda a los usuarios de lectores de pantalla a navegar rápidamente.

#### Ejemplo de estructura correcta:

```html
<header>...</header>
<nav>...</nav>
<main>...</main>
<aside>...</aside>
<footer>...</footer>
```

## Formularios

Todos los campos de formulario deben tener un elemento `<label>` asociado. Esto es como poner una etiqueta clara en una caja; asegura que los usuarios sepan qué contiene.

#### Ejemplo correcto:

```html
<label for="name">Your name</label>
<input id="name" type="text">
```

## Imágenes

Proporciona siempre una descripción de texto de las imágenes con el atributo `alt`. Esto es como contarle a alguien lo que hay en una foto si no puede verla.

#### Ejemplo:

```html
<img src="dog.jpg" alt="A golden retriever sitting on the grass looking happy.">
```

## Vínculos

Incluye texto descriptivo en los vínculos. Evita frases genéricas como "haz clic aquí", que son como indicaciones vagamente útiles.

#### Ejemplo:

```html
<p>Find out more about <a href="/offers.html">our latest offers</a>.</p>
```

## ARIA

El uso de HTML semántico hará que tus páginas sean más accesibles. Sin embargo, si creas widgets de interfaz que no tienen un elemento HTML correspondiente, necesitarás usar **ARIA** (Accessible Rich Internet Applications) para añadir semántica a esos elementos.

---

