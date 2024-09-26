# Formularios para obtener datos de los usuarios

Los formularios son la manera más común de recoger información de los usuarios en una página web. Si alguna vez has llenado un formulario en línea, entonces ya conoces cómo funciona desde el lado del usuario. Ahora veremos cómo implementarlo del lado del desarrollador.

## Analogía: Recoger opiniones en una fiesta

Imagina que estás en una fiesta y decides preguntarle a cada invitado cuál es su animal favorito. Quieres que te den la respuesta de manera organizada, por lo que entregas a cada persona una tarjeta con un espacio en blanco para que escriban su respuesta y un buzón donde pueden depositar la tarjeta cuando hayan terminado. ¡Eso es, básicamente, lo que hace un formulario en HTML! El formulario es la tarjeta y el buzón es el botón de envío que recopila todas las respuestas.

---

## ¿Cómo lo haces con HTML?

Con HTML, podemos crear un formulario para obtener datos de los usuarios usando etiquetas especiales como `<form>`, `<input>`, `<label>`, y un botón de envío `<button>`.

### Ejemplo básico de un formulario:

```html
<form>
  <label for="animal">¿Cuál es tu animal favorito?</label>
  <input type="text" id="animal" name="animal">
  <button>Guardar</button>
</form>
```

En este código, hemos creado un pequeño formulario que pide al usuario que escriba su animal favorito. Aquí lo que sucede:

- `<form>`: Es el contenedor que agrupa todos los elementos de entrada de datos.
- `<label>`: Una etiqueta que describe lo que queremos que el usuario responda. En este caso, pregunta por el animal favorito.
- `<input type="text">`: El campo donde el usuario escribe su respuesta.
- `<button>`: Un botón que envía la información del formulario.

### Concepto técnico

Cuando usas un formulario en una página web, esencialmente estás creando una interfaz donde los usuarios pueden introducir datos. Luego, esos datos se envían a un servidor o a otro lugar para ser procesados, como un buzón recoge todas las respuestas de tus invitados en la fiesta.

---

## ¿Dónde se procesan los datos?

Una vez que el usuario hace clic en "Guardar", los datos introducidos en el formulario son enviados a una URL para ser procesados. Este proceso funciona de la siguiente manera:

1. El navegador envía los datos del formulario al servidor, como si tomaras las tarjetas de la fiesta y las llevaras a alguien que las analice.
2. El servidor recibe esos datos y los procesa. Puede guardarlos en una base de datos, realizar cálculos o mostrarte una respuesta basada en esos datos.

Por ejemplo, si quieres que los datos del formulario sean procesados por una página en `https://example.com/animals`, puedes hacerlo así:

```html
<form action="https://example.com/animals">
  <label for="animal">¿Cuál es tu animal favorito?</label>
  <input type="text" id="animal" name="animal">
  <button>Guardar</button>
</form>
```

---

## ¿Cómo se transfieren los datos?

### Método GET (Datos visibles en la URL)

Por defecto, los formularios envían los datos como una solicitud GET, lo que significa que los datos se adjuntan a la URL. Por ejemplo, si alguien escribe "rana" como su animal favorito, el navegador hace una solicitud a esta URL:

`https://example.com/animals?animal=rana`

En la URL puedes ver directamente la respuesta del usuario, ya que se ha enviado como parte de la dirección.

### Método POST (Datos no visibles en la URL)

Si no quieres que los datos sean visibles en la URL (por ejemplo, cuando envías información sensible como contraseñas), puedes usar el método POST. Con este método, los datos se envían en el cuerpo de la solicitud y no son visibles en la URL.

```html
<form action="https://example.com/animals" method="post">
  <label for="animal">¿Cuál es tu animal favorito?</label>
  <input type="text" id="animal" name="animal">
  <button>Guardar</button>
</form>
```

---

## ¿Qué método usar?

- **GET**: Usa este método si los datos que estás enviando no son sensibles y podrían ser visibles sin problemas en la URL. Un buen ejemplo es un formulario de búsqueda.
- **POST**: Usa este método si estás manejando datos sensibles o que no deberían ser visibles en la URL, como una contraseña o datos personales.

En resumen, el formulario en HTML es como una tarjeta que les das a los invitados de tu fiesta para que escriban sus respuestas. El botón de envío es el buzón donde colocan las tarjetas. Al final, alguien (tu servidor) recoge esas tarjetas, las procesa y hace algo útil con la información que le diste.

# Formularios en HTML - Recopilando Datos de los Usuarios

### Imagina que eres un mesero en un restaurante...
Cada vez que atiendes a un cliente, necesitas anotar su pedido para llevarlo a la cocina. Para hacer esto de manera eficiente, usas un formulario en papel donde el cliente escribe lo que quiere comer. En el mundo web, cuando necesitas que los usuarios ingresen información en tu sitio (como su nombre, email, o su color favorito), usas formularios en HTML. Aquí te explicamos cómo.

---

## ¿Cómo se estructura un formulario?

Para crear un formulario en HTML, necesitas usar el elemento `<form>`, que actúa como ese papel en blanco donde los usuarios escriben su "pedido".

```html
<form>
  <label for="color">¿Cuál es tu color favorito?</label>
  <input type="text" id="color" name="color">
  <button type="submit">Enviar</button>
</form>
```

### ¿Qué pasa dentro del `<form>`?
Dentro del formulario incluimos:
- **Un `<label>`**: Es como una etiqueta en tu formulario de papel, donde explicas lo que el cliente debe escribir. Aquí está el mensaje "¿Cuál es tu color favorito?".
- **Un `<input>`**: Este es el campo donde el usuario puede escribir. Como el espacio en blanco donde el cliente anotará su respuesta.
- **Un `<button>`**: Este es el botón que envía el formulario, como cuando le entregas el pedido al cocinero. Al hacer clic, se envían los datos ingresados.

### Detalles técnicos:
- El atributo `for` en la etiqueta `<label>` se conecta con el atributo `id` en el campo `<input>`. Esto mejora la accesibilidad y permite que, al hacer clic en el texto de la etiqueta, el cursor se posicione directamente en el campo de entrada.
- El atributo `name` en el `<input>` es fundamental, ya que es la clave que usaremos para identificar los datos que el usuario ingresa cuando enviemos el formulario.

---

## ¿Qué tipo de datos puedes pedir?

El tipo de datos que puedes pedir depende del atributo `type` del `<input>`. Por ejemplo:

- **type="text"**: Un campo de texto normal.
- **type="checkbox"**: Una casilla de verificación.
- **type="file"**: Permite a los usuarios subir archivos.

### Analogía:
Imagina que en lugar de solo pedir el pedido de comida, también preguntas si el cliente quiere agregar salsa (casilla de verificación) o subir una foto de cómo quiere que quede el plato (subida de archivos). Dependiendo de lo que preguntes, usas un tipo diferente de campo.

```html
<label for="extras">¿Quieres agregar salsa?</label>
<input type="checkbox" id="extras" name="extras" value="salsa">
```

---

## ¿Y si necesitas varias líneas de texto?

A veces, los clientes necesitan escribir más que una palabra. En HTML, para eso usamos `<textarea>`, que es como un cuaderno más grande donde pueden escribir varias líneas.

```html
<label for="comentarios">Comentarios:</label>
<textarea id="comentarios" name="comentarios"></textarea>
```

---

## Agrupar controles de formulario

Si tienes varias preguntas relacionadas, como pedir el plato principal y las bebidas, es útil agrupar esos campos. Para eso, usamos `<fieldset>` y `<legend>`, que son como un subtítulo en tu formulario.

```html
<fieldset>
  <legend>Elige tus comidas favoritas</legend>
  
  <label for="pizza">Pizza</label>
  <input type="checkbox" id="pizza" name="comida" value="pizza">
  
  <label for="pasta">Pasta</label>
  <input type="checkbox" id="pasta" name="comida" value="pasta">
</fieldset>
```

---

## Enviar el formulario

Cuando ya tienes toda la información, es hora de "enviar el pedido a la cocina", o en nuestro caso, procesar los datos del formulario. Esto se hace con un botón de envío, usando `<button>` o `<input type="submit">`.

```html
<button type="submit">Enviar</button>
```

Al hacer clic en este botón, el formulario se envía a la URL que indicas en el atributo `action` del `<form>`. De forma predeterminada, los datos se envían a la misma página en la que estás, pero puedes cambiar esto especificando una URL diferente.

---

## ¿GET o POST?

Dependiendo de qué tan "importante" sea el pedido (los datos del formulario), puedes usar dos métodos para enviarlo:
- **GET**: Envía los datos en la URL, como si le pidieras al cliente que dijera su pedido en voz alta. Ideal para formularios simples, como búsquedas.
- **POST**: Envía los datos de manera más "privada", como si el cliente te pasara una nota con su pedido. Es lo que se usa cuando los datos son sensibles, como una contraseña o información personal.

```html
<form method="post">
  ...
</form>
```

### Resumen de analogías:
- Un formulario es como una hoja de pedidos donde los usuarios escriben su "orden".
- Los distintos campos `<input>` son como espacios en blanco en esa hoja donde pueden escribir su respuesta.
- El botón de envío es como el momento en el que llevas el pedido a la cocina.
- Y dependiendo del tipo de pedido, puedes usar un método más público (GET) o privado (POST) para enviar la información.

# Evitar que los usuarios vuelvan a ingresar datos en los formularios

Después de aprender sobre los elementos de formulario y cómo crear formularios interactivos, ahora veremos cómo facilitar la vida de los usuarios ayudándolos a evitar el reingreso de datos.

## Aprovecha Autocompletar al máximo

Imagina que estás comprando online y, cada vez que lo haces, tienes que volver a ingresar tu dirección. ¡Qué molesto sería! Aquí es donde la función de **Autocompletar** viene al rescate. Al ingresar tu dirección una sola vez, tu navegador la recordará y la ofrecerá para futuros formularios similares.

### ¿Cómo funciona Autocompletar?

Los navegadores utilizan un conjunto de reglas (llamadas **heurísticas**) para identificar campos de formularios donde podrían ofrecer opciones de autocompletar. Estas heurísticas incluyen:

- El valor de los atributos `name`, `type` e `id` del formulario.
- Si hay presente un atributo `autocomplete` en el control del formulario.

Por ejemplo, si tienes un campo de dirección, el navegador identifica automáticamente que estás ingresando una dirección basándose en cómo está configurado el formulario. Así, la próxima vez que te pidan una dirección, el navegador te sugerirá completar el campo automáticamente con la que ya ingresaste previamente.

#### Ejemplo de campo de dirección:
```html
<label for="address">Dirección</label>
<input type="text" id="address" name="address" autocomplete="address-line1">
```

### Nota:

Los navegadores también ayudan a recordar contraseñas. Al registrarte en un sitio, el navegador te ofrecerá generar y almacenar una contraseña segura. La próxima vez que quieras iniciar sesión en ese sitio, el navegador te ofrecerá autocompletar la contraseña almacenada.

## Ayuda a los navegadores con la función Autocompletar

Aunque los navegadores son muy inteligentes, hay formas en que podemos **mejorar** la experiencia de autocompletar utilizando correctamente los atributos en los formularios.

### Usa valores de atributos adecuados

Es importante que los valores de los atributos `name`, `type` e `id` sean descriptivos y claros. Por ejemplo, si tienes un campo de correo electrónico, usa el valor **`email`** en los tres atributos.

```html
<label for="email">Email</label>
<input type="email" name="email" id="email">
```

Al usar `email` como valor en estos atributos, le estamos dando tres señales al navegador de que este es un campo donde debe ofrecer la opción de autocompletar con una dirección de correo electrónico.

### El atributo de Autocompletar

El atributo `autocomplete` es un superhéroe oculto cuando hablamos de autocompletar. Ayuda a los navegadores a identificar exactamente qué tipo de dato esperar en un campo.

Por ejemplo, si tienes un campo de nombre en tu formulario, puedes asegurarte de que el navegador lo reconozca y ofrezca opciones de autocompletar adecuadas usando el atributo `autocomplete="name"`:

```html
<label for="name">Nombre</label>
<input type="text" id="name" name="name" autocomplete="name">
```

### ¿Qué pasa si los atributos `name`, `type` e `id` no son suficientes?

A veces, los atributos estándar no son suficientes para que el navegador entienda de qué tipo de datos se trata. Aquí es donde el atributo `autocomplete` se vuelve esencial.

#### Ejemplo con nombre y dirección:
```html
<label for="name">Nombre</label>
<input type="text" id="name" name="name" autocomplete="name">

<label for="street-address">Dirección</label>
<input type="text" id="street-address" name="address" autocomplete="street-address">
```

En este caso, estamos indicando de forma clara al navegador qué tipo de información esperamos que autocomplete.

### Mantén tus datos de Autocompletar actualizados

Si te mudas o cambias tu información de contacto, no te preocupes, puedes actualizar los datos que el navegador guarda. Los navegadores permiten a los usuarios editar la información que tienen almacenada, lo que garantiza que siempre se utilicen datos correctos.

En resumen, la función **Autocompletar** no solo ahorra tiempo a los usuarios, sino que también mejora la experiencia de uso en tu sitio. Al utilizar atributos adecuados y aprovechar `autocomplete`, estarás ayudando a los navegadores a identificar correctamente los campos del formulario y a proporcionar una experiencia más fluida a tus usuarios.

# Ayuda a los usuarios a ingresar los datos correctos en los formularios

### Introducción

Imagina que estás construyendo una casa (el formulario) y quieres asegurarte de que las puertas, ventanas y escaleras (los datos) tengan el tamaño y la forma correctos antes de instalarlos. No querrías una puerta demasiado pequeña ni una escalera con peldaños irregulares, ¿verdad? La validación de formularios en HTML funciona de manera similar: nos ayuda a asegurarnos de que los datos que los usuarios ingresan son del tamaño y formato correctos antes de enviarlos al servidor.

Los navegadores ya cuentan con funciones integradas para la validación, pero nosotros, como desarrolladores, podemos ayudar a guiar al usuario y asegurarnos de que los datos que ingresan sean válidos usando atributos HTML, CSS e incluso JavaScript.

---

### ¿Por qué deberías validar tus formularios?

Es frustrante llenar un formulario sin saber qué campos son obligatorios o las limitaciones de esos campos. Imagina que te piden ingresar tu número de teléfono, pero cuando lo haces, el sistema te dice que no es válido porque olvidaste agregar el código de área. ¡Qué frustrante! La validación de formularios te ayuda a prevenir estos problemas desde el principio.

**Por qué es útil:**
- Evita errores comunes antes de que ocurran.
- Hace la experiencia de usuario más fluida.
- Reduce la probabilidad de recibir datos incorrectos en el servidor.

---

### Ayuda a los usuarios a no perder por accidente campos obligatorios

Para comenzar, puedes usar HTML para marcar los campos que son obligatorios con el atributo `required`. Esto es como poner una señal en una puerta que dice "No puedes salir sin esta llave" (el dato necesario).

```html
<label for="name">Nombre (obligatorio)</label>
<input required type="text" id="name" name="name">
```

Cuando un usuario intenta enviar el formulario sin llenar este campo, el navegador automáticamente mostrará un mensaje diciendo que el campo es obligatorio.

---

### Atributo `type`: Indicando el tipo de dato

Además del atributo `required`, HTML también nos permite especificar el tipo de datos que esperamos. Por ejemplo, si pedimos un correo electrónico, usamos `type="email"` para asegurarnos de que el dato ingresado tenga el formato adecuado.

```html
<label for="email">Correo electrónico (obligatorio)</label>
<input required type="email" id="email" name="email">
```

Si el usuario ingresa algo que no tiene formato de correo electrónico (por ejemplo, solo letras sin el símbolo "@" y el dominio), el navegador mostrará un mensaje de error.

---

### Cómo restringir la cantidad de caracteres con `minlength` y `maxlength`

A veces, necesitas que los datos tengan una longitud específica. Por ejemplo, si estás creando una contraseña, podrías querer que tenga al menos 8 caracteres. Esto es como decirle al constructor de la casa: "Esta puerta necesita ser de al menos 2 metros de altura para que pase alguien por ella".

```html
<label for="password">Contraseña (obligatoria)</label>
<input required minlength="8" type="password" id="password" name="password" aria-describedby="password-minlength">
<div id="password-minlength">Ingrese al menos ocho caracteres</div>
```

---

### Atributo `pattern`: Definiendo reglas avanzadas

Imagina que le pides a alguien que escriba su animal favorito, pero solo quieres aceptar respuestas que contengan entre 2 y 20 letras en minúsculas. Puedes usar el atributo `pattern` para definir una "fórmula" o expresión regular que verifique que el texto cumpla con esas reglas.

```html
<label for="animal">¿Cuál es tu animal favorito? (obligatorio)</label>
<input required pattern="[a-z]{2,20}" type="text" id="animal" name="animal">
```

Esta regla solo permitirá letras minúsculas y rechazará entradas como "Perro" o "Elefante123".

---

### Estilos con CSS: Mejora la experiencia del usuario

Puedes usar CSS para mostrar visualmente cuáles son los campos obligatorios o cuáles son inválidos. Por ejemplo, podrías agregar un borde rojo a los campos que están mal llenados.

```css
input:required {
  border: 2px solid red;
}
input:invalid {
  border: 2px solid red;
}
input:valid {
  border: 2px solid green;
}
```

Esto es como poner una cinta roja en una puerta defectuosa o una cinta verde en una puerta que está lista para ser instalada.

---

### Validación con JavaScript: Mensajes personalizados

A veces, los mensajes predeterminados del navegador no son suficientes o no son consistentes entre navegadores. En este caso, puedes usar JavaScript para personalizar los mensajes de error que se muestran cuando el usuario ingresa datos incorrectos.

```javascript
const nameInput = document.querySelector('[name="name"]');

nameInput.addEventListener('invalid', () => {
    nameInput.setCustomValidity('Por favor, ingresa tu nombre.');
});
```

Con esto, en lugar de recibir un mensaje genérico, los usuarios verán algo más claro y útil.

---

### Validación en tiempo real con `onblur`

Si quieres hacer la experiencia del usuario aún más fluida, puedes validar los campos a medida que los van llenando, en lugar de esperar hasta que intenten enviar el formulario. Puedes hacerlo escuchando el evento `onblur`, que se activa cuando el usuario deja de interactuar con un campo.

```javascript
const inputField = document.querySelector('input');

inputField.addEventListener('blur', function() {
    if (!inputField.checkValidity()) {
        alert('Este campo no es válido');
    }
});
```

En resumen, la validación de formularios es esencial para ofrecer una experiencia de usuario agradable y asegurarte de que los datos que recibes sean válidos y estén en el formato correcto. Al combinar HTML, CSS y JavaScript, puedes crear formularios robustos que guíen al usuario y reduzcan errores.

# Prueba tus Formularios

En módulos anteriores, aprendiste a construir formularios, ayudando a los usuarios a evitar reingresar datos y validarlos correctamente. Ahora la pregunta es: ¿cómo asegurarte de que el formulario sea realmente útil y funcional para los usuarios? Para esto, necesitas **probar y analizar tu formulario**.

## ¿Tu formulario funciona en otros dispositivos?

Imagina que construyes una bicicleta perfecta en tu taller, y funciona excelente en tus pruebas. Pero... ¿qué pasa si esa bicicleta es usada en una calle empinada, o en un terreno lleno de barro? Lo mismo ocurre con los formularios: aunque funcionen en tu computadora, debes probarlos en otros "terrenos" o dispositivos.

### Pasos clave para probar:
1. **Prueba en tu computadora** (tu terreno conocido).
2. **Usa solo el teclado**: Como si estuvieras manejando un auto sin usar las manos.
3. **Prueba en un teléfono móvil**: Esto es como llevar tu bicicleta a un terreno desconocido.
4. **Diferentes métodos de entrada**: Prueba usando el teclado, panel táctil o mouse.
5. **Diferentes navegadores y sistemas operativos**: Es como probar tu bicicleta en asfalto, tierra o arena.

### Herramientas:
- Puedes usar servicios como **BrowserStack**, que te permite probar tu formulario en diferentes dispositivos y navegadores sin tener que comprarlos todos.

## ¿Funciona para otras personas?

Tu formulario puede ser "tu bicicleta favorita", pero ¿qué pasa cuando otros intentan usarla? Aquí es donde entran en juego las **pruebas con otros usuarios**.

### ¿Cómo hacerlo?
- Pide a amigos o colegas que prueben el formulario.
- Siéntate a su lado o comparte pantalla para observar cómo lo usan. 
- Pregúntales si algo no quedó claro, si tuvieron problemas, o si alguna parte del formulario les resultó confusa.

### Ejemplo:
Imagina que en tu formulario tienes un campo de "dirección". No todos los usuarios escriben la dirección de la misma manera. Prueba ingresando una dirección de otro país. Es como preguntar: "¿Esta bicicleta se maneja igual en otra ciudad?"

## ¿Cómo medir el rendimiento de tu formulario?

Probar si funciona está bien, pero también necesitas asegurarte de que sea **rápido y eficiente**. Piensa en esto como probar cuán ligera y rápida es tu bicicleta en diferentes condiciones.

### Herramientas para medir el rendimiento:
1. **PageSpeed Insights (PSI)**: Es como un cronómetro que mide cuán rápido carga tu sitio.
   - PSI te da un informe de rendimiento con datos del "laboratorio" y del "mundo real". El primero es como probar tu bicicleta en un circuito controlado, y el segundo es como probarla en calles normales.
   
2. **Lighthouse**: Además de medir el rendimiento, también te dice si tu sitio tiene problemas de accesibilidad o SEO (como si un experto te diera consejos para mejorar tu bicicleta y hacerla más fácil de manejar para otros).

### Ejemplo:
Lighthouse te puede advertir si olvidaste conectar una etiqueta a un campo de formulario, lo que es como olvidarte de ajustar los frenos en tu bicicleta antes de salir a rodar.

## ¿Cómo supervisar la experiencia en un formulario?

Ya probaste tu formulario con algunas personas, pero quieres saber cómo les va a **todos** los usuarios en el mundo real. Aquí es donde entran las **métricas de rendimiento en vivo**. Es como usar un GPS para ver cómo las personas están usando tu bicicleta en tiempo real y si encuentran problemas.

### Herramientas:
- **PageSpeed Insights (PSI)**: Usa la API para obtener datos de rendimiento en tiempo real de usuarios reales.
- **Lighthouse**: Puede integrarse con herramientas como **GitHub Actions** para que puedas medir y supervisar el rendimiento de tu formulario automáticamente cada vez que haces cambios.

## Análisis y estadísticas: Conoce a tus usuarios

Para realmente entender cómo los usuarios interactúan con tu formulario, es útil tener una herramienta de análisis. **Google Analytics** es como un radar que te dice cuántas personas usan tu formulario, cuántos lo completan, y dónde encuentran problemas.

### Ejemplo:
Supón que quieres saber cuántas personas hacen clic en el botón "Enviar" de tu formulario. Google Analytics te puede ayudar a rastrear este evento y entender cómo mejorar la experiencia.

En resumen, probar formularios no es solo algo que haces una vez y olvidas. Así como una bicicleta necesita ajustes constantes para mantenerla en forma, los formularios necesitan pruebas y mejoras constantes para asegurar que todos los usuarios puedan usarlos sin problemas, sin importar en qué "terreno" se encuentren.

# Conceptos Básicos del Diseño

## Introducción

En la primera sección, aprendiste a crear un formulario básico. Ahora es momento de dar un paso más allá y aprender las mejores prácticas. En este módulo, veremos conceptos sobre la **Experiencia de Usuario (UX)** y cómo una **Interfaz de Usuario (UI)** bien implementada puede marcar una gran diferencia en la interacción de los usuarios con tu sitio.

## Crea Interfaces Fáciles de Usar

Piensa en un formulario como un camino por el que transita un ciclista. Si el camino está bien pavimentado, con señales claras y sin obstáculos, el ciclista llegará a su destino sin problemas. Si el formulario está mal diseñado, será como un camino lleno de baches y curvas cerradas: frustrante y lento.

Para hacer la "bicicleta" del usuario más liviana, asegúrate de que la **UI** sea intuitiva, con un buen diseño gráfico (diseño, espaciado, tamaño de fuente, colores) y una estructura lógica (etiquetas bien escritas y tipos de entrada adecuados).

## Etiquetas: El GPS de los Formularios

Imagina que las **etiquetas** son las señales de tránsito en el camino del ciclista. Le indican qué dirección tomar. Una etiqueta bien colocada y clara hace que el usuario sepa qué se espera que complete en cada campo del formulario.

### Usa una etiqueta para cada control de formulario

Coloca una etiqueta **visible** para cada campo. Esto es como asegurarte de que todas las señales en el camino están bien visibles, para que el ciclista no se pierda. Por ejemplo:

```html
<label for="email">Correo Electrónico</label>
<input type="email" id="email" name="email">
```

Evita usar el atributo `placeholder` como etiqueta. Esto sería como pintar las señales de tránsito en el suelo: tal vez al principio se vean, pero con el uso se desgastan y el ciclista puede perderse. El `placeholder` solo debe ofrecer una **sugerencia** del tipo de datos a ingresar, no describir el campo.

### Texto de la etiqueta: Menos es más

A la hora de escribir la etiqueta, manténla corta y clara. Esto es como poner un cartel sencillo, pero efectivo. En lugar de decir "Por favor, ingresa tu dirección de correo electrónico para poder recibir notificaciones", es mejor simplemente "Correo electrónico". Las etiquetas cortas ayudan a los usuarios a identificar más rápidamente lo que necesitan.

### Posición de la etiqueta: Señales donde se ven

Las mejores señales de tránsito son las que están justo enfrente del ciclista. Lo mismo ocurre con las etiquetas: la investigación demuestra que la mejor práctica es colocar las etiquetas **arriba** del campo de entrada. Así, los usuarios pueden escanear el formulario de manera rápida y eficiente.

## Cómo diseñar Formularios

Un formulario mal diseñado es como un mapa lleno de caminos confusos que lleva a los ciclistas por rutas innecesarias, haciendo que muchos abandonen antes de llegar a su destino. 

### Elementos de formulario adecuados

Usa el elemento de formulario adecuado para cada caso. Si necesitas varias líneas de texto, usa `<textarea>`, y si los usuarios deben aceptar términos y condiciones, usa `<input type="checkbox">`. Asegúrate de usar el tipo de entrada correcto para facilitar el trabajo del usuario, como `type="tel"` para teléfonos y `type="email"` para correos electrónicos, optimizando incluso los teclados en dispositivos móviles.

### Diferencia los controles

Haz que cada elemento del formulario sea visualmente claro. Si un botón parece un botón, el ciclista (usuario) sabrá que tiene que presionarlo para continuar su viaje, mientras que un enlace debería abrir otra página, no enviar el formulario.

## Ayuda a los usuarios a navegar por los Formularios

Imagina que le das al ciclista un mapa con múltiples rutas para elegir; se perdería fácilmente. Los formularios de **una sola columna** funcionan mejor porque el usuario sigue una sola dirección de principio a fin. De esta manera, el usuario no se distrae buscando dónde está el siguiente campo.

Además, asegúrate de que los formularios sean accesibles. Esto significa que los usuarios puedan navegar por ellos utilizando solo el teclado. ¡Prueba tu formulario navegando solo con el tabulador para asegurarte de que el orden sea el correcto!

## Ayuda a los usuarios a interactuar con los Formularios

Los botones y campos deben ser lo suficientemente grandes para que los usuarios puedan interactuar sin frustración. El tamaño mínimo recomendado es de **48px**. Esto sería como asegurarte de que las señales de tránsito sean lo suficientemente grandes para que el ciclista las vea claramente mientras se mueve.

Usa `padding` y `font-size` para ajustar el tamaño de los campos, asegurándote de que el usuario pueda interactuar fácilmente.

### Diferencia entre dispositivos

Usa `@media` en CSS para ajustar los controles de formulario según el tipo de dispositivo que se esté usando. Por ejemplo:

```css
@media (pointer: fine) {
  input[type="checkbox"] {
    width: 15px;
    height: 15px;
  }
}

@media (pointer: coarse) {
  input[type="checkbox"] {
    width: 30px;
    height: 30px;
  }
}
```

Esto permite que el formulario funcione bien tanto en dispositivos táctiles como con mouse.

## Cómo Mostrar Errores Donde Ocurren

Cuando el ciclista se desvía del camino, necesita una señal que le indique que ha tomado una ruta equivocada. Lo mismo ocurre con los formularios. Los mensajes de error deben mostrarse **cerca del campo** donde ocurre el problema, para que el usuario sepa qué corregir rápidamente.

Por ejemplo, si un campo de contraseña requiere al menos 8 caracteres, muestra esa información junto al campo, de esta manera:

```html
<label for="password">Contraseña (requerida)</label>
<input required minlength="8" type="password" id="password" name="password" aria-describedby="password-minlength">
<span id="password-minlength">Ingresa al menos ocho caracteres</span>
```

Haz que los mensajes de error sean claros y conecta esos mensajes con los campos correspondientes para que los lectores de pantalla puedan comunicarlos de manera efectiva.

# Accesibilidad

## Imagina que construyes un parque para todos

Cuando creas un formulario, piensa que estás construyendo un parque donde diferentes personas pueden venir a jugar. Algunas personas usarán bicicletas, otras vendrán caminando, algunas en sillas de ruedas, y otras, con sus mascotas. Al igual que en ese parque, no todos usarán tu formulario de la misma manera. Algunas personas usan mouse, otras usan pantallas táctiles, otras solo un teclado, y algunas hasta usan un lector de pantalla que les lee lo que hay en la página. **Tu tarea es asegurarte de que todos puedan disfrutar del parque**, es decir, que todos puedan interactuar con tu formulario sin importar cómo accedan a él.

## Etiquetas: Las señales del parque

Al igual que en un parque, donde colocas carteles para que las personas sepan qué es cada cosa ("Zona de Juegos", "Baños", "Área de Picnic"), en los formularios también necesitas describir el propósito de cada campo. ¿Cómo haces eso? Con el **elemento `<label>`**.

El **`<label>`** es como el cartel que le dice a los usuarios qué es lo que deben poner en cada parte del formulario. Además, si alguien usa un lector de pantalla, este leerá el contenido del **`<label>`** para que esa persona sepa qué debe hacer. Por ejemplo, cuando tengas un campo para el nombre, asegúrate de que el **`<label>`** le diga al usuario: "Este es el lugar donde escribes tu nombre".

```html
<label for="nombre">Nombre</label>
<input type="text" id="nombre" name="nombre" />
```

Este pequeño detalle hace que tu formulario sea más claro y accesible para todos. ¡Es como poner el cartel adecuado en cada zona del parque!

## Usa las herramientas correctas para crear tu parque

Imagina que estás construyendo un parque y decides usar materiales que no son los adecuados: como poner bancos hechos de cartón en vez de metal o madera. Podrían parecer buenos al principio, pero no resistirán el uso diario. Lo mismo pasa si creas un formulario usando etiquetas como **`<div>`** para todo. Aunque puede que se vea bien, no funcionará correctamente para todos los usuarios.

Por ejemplo, un **`<input>`** le dice al navegador (y a los usuarios) que es un lugar donde deben escribir algo. Un **`<div>`**, aunque visualmente pueda parecer lo mismo, no tiene esa función. Esto es especialmente importante para las personas que usan lectores de pantalla, ya que no reconocerán el **`<div>`** como un campo donde se puede escribir. Es como si en tu parque pusieras un cartel que diga "Baños" pero al llegar, no hay ningún baño. ¡Confuso y frustrante!

### Ejemplo:

```html
<label for="nombre">Nombre</label>
<input type="text" id="nombre" name="nombre" required />
```

Este código le dice a todos los dispositivos y navegadores que este es un campo donde el usuario debe escribir su nombre, haciéndolo accesible y fácil de entender.

## Reglas claras: Señales de tránsito del parque

En un parque, es importante tener reglas claras, como "Prohibido nadar en la fuente" o "Zona para picnic solamente". De la misma manera, en los formularios necesitas indicar qué reglas deben seguir los usuarios. Si tienes un campo donde el usuario debe ingresar al menos 8 caracteres, debes indicárselo. Una forma de hacerlo es usar el atributo **`minlength`**, que le dice al navegador cuál es la longitud mínima permitida.

Pero también es importante que le expliques estas reglas al usuario de forma visible. Puedes agregar un pequeño texto debajo del campo que diga algo como "Debe tener al menos 8 caracteres", y asegurarte de que ese texto sea accesible usando **`aria-describedby`**.

```html
<label for="password">Contraseña</label>
<input type="password" id="password" name="password" minlength="8" aria-describedby="passwordHelp" />
<small id="passwordHelp">Debe tener al menos 8 caracteres</small>
```

Así, todos sabrán exactamente qué hacer.

## Mensajes de error: Semáforos del parque

Si en tu parque alguien intenta ir en bici por donde no debe, necesitas una señal que les avise del error. Lo mismo ocurre en un formulario. Si alguien comete un error al llenarlo, es fundamental que el mensaje de error sea claro y accesible. No te limites solo a usar el color rojo (ya que algunas personas no pueden distinguir entre rojo y verde), agrega un texto que explique el error, como: **"Error: Usa al menos 8 caracteres."**

```html
<span class="error">
  <strong>Error:</strong> Usa al menos 8 caracteres.
</span>
```

Esto garantiza que todos los usuarios puedan entender fácilmente qué ha salido mal.

## Navegación: Asegura que todos puedan recorrer el parque

En un parque bien diseñado, todos deberían poder moverse de un lugar a otro sin problemas. En un formulario, eso se traduce en asegurarte de que los usuarios puedan navegar por los diferentes campos de manera intuitiva. El orden en el que colocas los campos es importante. Aunque puedes cambiar la disposición visual de los campos con **CSS**, el **orden en el DOM** (el código HTML) debe seguir siendo coherente para que los usuarios que usan teclados o lectores de pantalla no se pierdan.

Asegúrate de probar tu formulario usando solo el teclado, para ver si la navegación es fluida y lógica.

## Tu parque, accesible para todos

Crear un formulario accesible es como construir un parque donde todos puedan disfrutar, sin importar cómo lleguen o qué herramientas usen. Asegúrate de usar los elementos correctos, proporcionar etiquetas claras, indicar las reglas de manera accesible y permitir que todos naveguen sin problemas. Al final del día, tu formulario no solo debe funcionar, sino también ser inclusivo y amigable para todos.

¡Recuerda siempre probar tu formulario con diferentes dispositivos y personas para asegurarte de que sea accesible para todos!

# Internacionalización y Localización

## ¿Qué es la Internacionalización y Localización?

Imagina que estás organizando una gran fiesta. Invitaste a amigos de diferentes partes del mundo. Cada uno habla su propio idioma y tiene sus costumbres, pero todos necesitan disfrutar de la fiesta. **Internacionalizar** tu sitio web es como asegurarte de que todos tengan un lugar cómodo en tu fiesta, sin importar de dónde vengan. **Localizar** es como personalizar la decoración y la música para cada uno de tus invitados, haciéndoles sentir como en casa. Esto es lo que logras con la internacionalización y localización en tus formularios web.

---

## Asegúrate de que el formulario funcione en diferentes idiomas

Cuando creas un formulario, debes pensar en que será usado por personas que hablan distintos idiomas. Es como escribir una tarjeta de invitación: quieres que todos la entiendan, sin importar su idioma nativo.

### Primer paso: Define el idioma del documento

Para comenzar, usa el atributo `lang` en tu archivo HTML. Esto le dice al navegador y a los lectores de pantalla en qué idioma está escrito tu formulario. Por ejemplo, si el formulario está en inglés estadounidense:

```html
<html lang="en-us">
```

Este atributo no solo es útil para los lectores de pantalla, sino también para que los navegadores puedan ofrecer traducciones automáticas correctas.

### Agrega versiones alternativas de tu formulario

Si traduces tu formulario a otros idiomas, puedes utilizar etiquetas `<link>` en la sección `<head>` para describir las versiones alternativas del formulario. Esto ayuda a los motores de búsqueda y navegadores a identificar las diferentes versiones lingüísticas:

```html
<link rel="alternate" title="Formulario en inglés"
  href="https://example.com/en/form" hreflang="en">
<link rel="alternate" title="Formulario en alemán"
  href="https://example.com/de/form" hreflang="de">
```

---

## Ayuda a que los usuarios de otros idiomas usen tu formulario

No siempre puedes traducir tu formulario a todos los idiomas posibles, pero al menos puedes hacer que sea fácilmente traducible con herramientas como Google Traductor.

### ¿Cómo lograrlo?

Asegúrate de que todo el texto importante esté en HTML, visible y accesible. Por ejemplo, el texto oculto en JavaScript o atributos como `aria-label` puede no ser traducido correctamente por algunas herramientas.

**Nota:** Evita usar `aria-label` para describir elementos importantes del formulario, ya que algunas herramientas no pueden traducir ese atributo.

---

## Asegúrate de que tu formulario funcione con diferentes sistemas de escritura

Distintas culturas tienen distintas formas de escribir. Algunos idiomas se leen de izquierda a derecha (como el español), mientras que otros lo hacen de derecha a izquierda (como el árabe). Esto es como decorar una fiesta: necesitas adaptar la disposición dependiendo de las costumbres de tus invitados.

### Usa propiedades lógicas de CSS

Las propiedades lógicas de CSS te permiten ajustar el diseño visual dependiendo de la dirección del texto. Por ejemplo, si estás creando un formulario que debe adaptarse a escrituras de derecha a izquierda (RTL), usa propiedades como `border-inline-start-width` en lugar de `border-left-width`. Así, el espaciado se ajustará automáticamente al sistema de escritura.

```css
input {
  border-inline-start-width: 4px;
}
```

Si el texto se lee de derecha a izquierda, este borde grueso aparecerá en el lado correcto sin necesidad de ajustes manuales.

---

## Asegúrate de que tu formulario acepte diferentes formatos de nombre

Los nombres pueden ser muy diferentes en distintas culturas. Algunos países tienen solo un nombre, otros dos apellidos, y algunos usan caracteres que no son latinos. Pedirle a un usuario que ingrese su "nombre" y "apellido" podría no tener sentido en su contexto cultural.

### ¿Cómo solucionarlo?

Una solución es usar un solo campo de nombre siempre que sea posible. De esta manera, permites que los usuarios ingresen su nombre completo sin problemas, sin importar el formato que usen.

---

## Permite diversos formatos de dirección

Así como las direcciones en papel son distintas en cada país, las direcciones electrónicas también lo son. Por ejemplo, en EE. UU., una dirección típica incluye calle, ciudad, estado, código postal y país. Pero en otros países, el formato puede ser completamente diferente.

### ¿Qué puedes hacer?

Una opción es usar entradas genéricas para que los usuarios ingresen su dirección de la manera que sea más familiar para ellos. No asumas que todas las direcciones siguen el mismo formato, y sé flexible con los campos de entrada.

En resumen, adaptar tu formulario para ser accesible a personas de diferentes idiomas, culturas y costumbres es clave para que todos puedan interactuar con tu sitio web de manera eficiente. No se trata solo de traducir palabras, sino de pensar en cómo las personas de diferentes partes del mundo usan sus nombres, direcciones y cómo navegan tu sitio. 

Con estos ajustes, estarás organizando la mejor fiesta posible para todos tus usuarios.