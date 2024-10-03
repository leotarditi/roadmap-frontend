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

