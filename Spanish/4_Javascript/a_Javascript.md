# JavaScript puede cambiar el contenido HTML

En JavaScript, una de las muchas formas de interactuar con el HTML es usando el método `getElementById()`. Este método le permite a JavaScript "encontrar" un elemento en el DOM (Document Object Model) basado en su atributo `id`. Luego, podemos modificar el contenido de ese elemento.

### Analogía
Imaginá que el DOM es como un estante lleno de cajas (elementos HTML), y cada caja tiene una etiqueta (id). Si querés cambiar lo que hay dentro de una de esas cajas, primero necesitás identificarla por su etiqueta (usando `getElementById`), y después podés abrirla y cambiar lo que tiene adentro (modificar su `innerHTML`).

### Ejemplo
```javascript
document.getElementById("demo").innerHTML = "Hello JavaScript";
```

En este caso, estamos encontrando la caja con la etiqueta "demo" y cambiando su contenido a "Hello JavaScript".

### Dato técnico
- `innerHTML` es la propiedad que representa el contenido dentro de un elemento HTML. Podés asignarle cualquier texto o incluso código HTML para modificar el contenido del elemento.

Podés usar tanto comillas simples como dobles en JavaScript:

```javascript
document.getElementById('demo').innerHTML = 'Hello JavaScript';
```

---

## JavaScript Can Change HTML Attribute Values

Otra funcionalidad clave de JavaScript es la capacidad de cambiar atributos de elementos HTML, como la fuente de una imagen. Para ello, utilizamos nuevamente `getElementById()` para encontrar el elemento y luego modificamos el atributo específico.

### Analogía
Imaginá que los atributos HTML son como los detalles en la etiqueta de una caja, como "frágil" o "color blanco". Si necesitás cambiar algún detalle, como la fuente de una imagen, es como si cambiaras una etiqueta en esa caja. Podés quitar la etiqueta vieja y poner una nueva.

### Ejemplo
```javascript
document.getElementById("myImage").src = "lightbulb-on.png";
```

En este ejemplo, estamos cambiando la fuente de la imagen (el atributo `src`) para mostrar una imagen diferente.

---

## JavaScript Can Change HTML Styles (CSS)

También podés usar JavaScript para cambiar el estilo CSS de un elemento HTML. Es como cambiar su apariencia.

### Analogía
Imaginá que el estilo CSS es como la ropa que lleva puesta una persona. Si querés que esa persona use ropa más grande o más chica, simplemente le cambiás la ropa. En este caso, podés cambiar el tamaño de la fuente o cualquier otro estilo del elemento.

### Ejemplo
```javascript
document.getElementById("demo").style.fontSize = "35px";
```

Aquí, estamos aumentando el tamaño de la fuente del texto dentro del elemento "demo" a 35 píxeles.

### Dato técnico
- `style` es la propiedad que nos permite acceder y modificar las reglas CSS de un elemento HTML. Podés cambiar cualquier propiedad CSS de esta manera, como color, márgenes, o display.

---

## JavaScript Can Hide HTML Elements

Podés ocultar un elemento HTML modificando su estilo CSS con JavaScript. En particular, podés cambiar su propiedad `display`.

### Analogía
Imaginá que un elemento HTML es como un objeto en una habitación. Podés ponerle una sábana encima (cambiando su `display` a "none") para ocultarlo de la vista. Nadie lo verá, pero todavía está ahí, bajo la sábana.

### Ejemplo
```javascript
document.getElementById("demo").style.display = "none";
```

Con este código, estamos ocultando el elemento "demo".

---

## JavaScript Can Show HTML Elements

De la misma manera que podés ocultar un elemento, también podés mostrarlo nuevamente cambiando la propiedad `display` a "block" o cualquier otro valor visible.

### Analogía
Volviendo al ejemplo de la sábana, mostrar el elemento nuevamente es como quitar la sábana que lo cubría, y ahora todos pueden verlo de nuevo.

### Ejemplo
```javascript
document.getElementById("demo").style.display = "block";
```

En este caso, estamos mostrando nuevamente el elemento "demo" que habíamos ocultado antes.

---

## ¿Sabías que?

Aunque JavaScript y Java suenan parecido, son lenguajes completamente diferentes tanto en concepto como en diseño. JavaScript fue creado por Brendan Eich en 1995 y se convirtió en un estándar ECMAScript en 1997.

- **ECMA-262** es el nombre oficial del estándar que define JavaScript.
- **ECMAScript** es el nombre oficial del lenguaje JavaScript.

---

# La Etiqueta `<script>`

En HTML, el código JavaScript se inserta entre las etiquetas `<script>` y `</script>`.

### Analogía
Imagina que tu página web es como una obra de teatro. El HTML es el escenario y los actores (los elementos HTML) ya están allí, pero aún no saben qué hacer. El guion (JavaScript) está dentro de la etiqueta `<script>`, y les dice a los actores qué acciones tomar durante la obra.

### Ejemplo:
```html
<script>
  document.getElementById("demo").innerHTML = "Mi Primer JavaScript";
</script>
```
Este código le dice al "actor" con el `id="demo"` que cambie su diálogo a "Mi Primer JavaScript".

### Explicación Técnica
- **`<script>`**: Es la etiqueta que marca el inicio del código JavaScript en una página web. 
- **`document.getElementById()`**: Este método selecciona un elemento HTML por su `id`, lo que permite interactuar con él desde el código JavaScript.
- **`innerHTML`**: Propiedad que cambia el contenido de un elemento.

### Atributo `type`
En ejemplos antiguos, se usaba el atributo `type="text/javascript"` en la etiqueta `<script>`, pero ya no es necesario porque JavaScript es el lenguaje de scripting por defecto en HTML.

---

## Funciones y Eventos en JavaScript

Una **función** en JavaScript es un bloque de código que se ejecuta cuando se "invoca" o "llama". Por ejemplo, una función puede activarse cuando el usuario hace clic en un botón.

### Analogía
Piensa en una función como una receta de cocina. Sabes que cuando necesitas preparar un plato, sigues las instrucciones de esa receta. La receta (la función) no hace nada hasta que decides cocinar (llamar la función).

### Ejemplo:
```html
<script>
function miFuncion() {
  document.getElementById("demo").innerHTML = "El párrafo ha cambiado.";
}
</script>
```
Aquí, la "receta" es la función `miFuncion()`, y cuando alguien hace clic en un botón, se ejecuta y cambia el contenido del elemento con `id="demo"`.

---

## JavaScript en `<head>` o `<body>`

Puedes colocar cualquier número de scripts en un documento HTML. Estos scripts pueden estar en la sección `<head>`, en la sección `<body>`, o en ambas.

### JavaScript en `<head>`
Si colocas un script en la cabecera (`<head>`), normalmente lo haces para funciones que deseas cargar antes de que el contenido del cuerpo de la página se muestre. El script se ejecuta cuando se le llama, como en el siguiente ejemplo:

### Ejemplo:
```html
<!DOCTYPE html>
<html>
<head>
  <script>
    function miFuncion() {
      document.getElementById("demo").innerHTML = "El párrafo ha cambiado.";
    }
  </script>
</head>
<body>
  <h2>Demostración de JavaScript en Head</h2>
  <p id="demo">Un párrafo</p>
  <button type="button" onclick="miFuncion()">Prueba</button>
</body>
</html>
```

### JavaScript en `<body>`
Los scripts también pueden colocarse en el cuerpo (`<body>`), lo que hace que el código JavaScript se cargue junto con el contenido visible de la página. Colocar los scripts al final del cuerpo ayuda a mejorar la velocidad de carga de la página, ya que el navegador primero muestra el contenido y luego interpreta el script.

### Ejemplo:
```html
<!DOCTYPE html>
<html>
<body>
  <h2>Demostración de JavaScript en Body</h2>
  <p id="demo">Un párrafo</p>
  <button type="button" onclick="miFuncion()">Prueba</button>
  <script>
    function miFuncion() {
      document.getElementById("demo").innerHTML = "El párrafo ha cambiado.";
    }
  </script>
</body>
</html>
```

### Colocar Scripts al Final del `<body>`
Poner los scripts al final del cuerpo (`<body>`) mejora la velocidad de visualización, ya que la interpretación del script puede ralentizar la carga del contenido visible.

---

## JavaScript Externo

Los scripts también pueden colocarse en archivos externos. Esto es útil cuando el mismo código JavaScript se usa en múltiples páginas web.

### Analogía
Piensa en un archivo JavaScript externo como una biblioteca que todos pueden consultar cuando lo necesiten. En lugar de repetir el mismo libro (código) en cada sala de la casa (página web), lo guardas en un estante (archivo `.js`), y todos pueden tomarlo cuando lo necesiten.

### Ejemplo:
- Archivo externo: **miScript.js**
```javascript
function miFuncion() {
  document.getElementById("demo").innerHTML = "El párrafo ha cambiado.";
}
```
- HTML que lo utiliza:
```html
<script src="miScript.js"></script>
```

### Ventajas del JavaScript Externo
1. **Separación del HTML y el código**: Hace que el HTML y el JavaScript sean más fáciles de leer y mantener.
2. **Reutilización**: Puedes usar el mismo archivo JavaScript en varias páginas web.
3. **Archivos en caché**: Los navegadores pueden guardar en caché los archivos JavaScript externos, lo que acelera la carga de la página en visitas posteriores.

---

## Referencias Externas

Un script externo puede referenciarse de tres maneras:
1. **URL completa**:
   ```html
   <script src="https://www.ejemplo.com/js/miScript.js"></script>
   ```
2. **Ruta relativa** (ubicación del archivo en relación con el HTML):
   ```html
   <script src="/js/miScript.js"></script>
   ```
3. **Sin ruta** (cuando el archivo está en el mismo directorio que el HTML):
   ```html
   <script src="miScript.js"></script>
   ```

En cada caso, el script externo se comporta como si estuviera exactamente donde está colocada la etiqueta `<script>`.

---

# Posibilidades de visualización de JavaScript 🚀

JavaScript nos ofrece varias maneras de "mostrar" datos en la web. Para entender cómo funciona esto, podemos pensar en JavaScript como un mago con diferentes trucos bajo la manga para mostrar información. Cada truco tiene su propia manera de actuar. Vamos a ver estos "trucos" y cómo funcionan.

## 1. Usando `innerHTML` 🎩
Imagina que tienes una pizarra (el elemento HTML), y quieres escribir en ella. JavaScript puede tomar un marcador y escribir algo directamente en esa pizarra usando `innerHTML`.

### Ejemplo:
```html
<!DOCTYPE html>
<html>
<body>

<h1>Mi Primera Página Web</h1>
<p>Mi Primer Párrafo</p>

<p id="demo"></p> <!-- Aquí es donde escribiremos -->

<script>
document.getElementById("demo").innerHTML = 5 + 6;
</script>

</body>
</html>
```

**Analogia**: `document.getElementById("demo")` es como señalar la pizarra específica en la que quieres escribir, y `innerHTML` es el acto de escribir en esa pizarra. Este es el truco más común y usado para actualizar contenido en la página.

## 2. Usando `document.write()` 🖋️
Este truco es como tener una hoja de papel y escribir algo en ella antes de que esté completamente lista. JavaScript puede escribir directamente en el documento mientras se está cargando.

### Ejemplo:
```html
<!DOCTYPE html>
<html>
<body>

<h1>Mi Primera Página Web</h1>
<p>Mi primer párrafo.</p>

<script>
document.write(5 + 6);
</script>

</body>
</html>
```

**Analogia**: Piensa en `document.write()` como escribir en un papel mientras se está imprimiendo. Una vez que el papel ya está completo (la página cargada), cualquier intento de escribir más reemplazará todo el contenido existente, como si tiraras el papel viejo y empezaras de nuevo. Por eso, este truco solo se recomienda usar para pruebas rápidas.

## 3. Usando `window.alert()` 📢
Este truco es como un altavoz. Cuando quieres que algo sea muy obvio, puedes usar una alerta que llame la atención del usuario.

### Ejemplo:
```html
<!DOCTYPE html>
<html>
<body>

<h1>Mi Primera Página Web</h1>
<p>Mi primer párrafo.</p>

<script>
window.alert(5 + 6);
</script>

</body>
</html>
```

**Analogia**: `window.alert()` es como gritar: "¡Atención! Aquí tienes algo importante", porque interrumpe todo y muestra una ventana emergente con el mensaje. Usar `alert()` sin el `window` es igualmente válido, ya que JavaScript asume que te estás refiriendo a la ventana global.

## 4. Usando `console.log()` 🛠️
Este es el truco de "tras bambalinas". Si quieres ver lo que está pasando sin mostrarlo al público (al usuario), puedes usar `console.log()` para mostrar información en la consola de desarrollo del navegador.

### Ejemplo:
```html
<!DOCTYPE html>
<html>
<body>

<script>
console.log(5 + 6);
</script>

</body>
</html>
```

**Analogia**: Piensa en `console.log()` como un cuaderno de notas que tienes en tu bolsillo. No lo compartes con todos, pero lo usas para tomar apuntes y asegurarte de que todo va bien "detrás del escenario". Esto es muy útil cuando quieres depurar tu código y verificar que todo funcione como esperas.

## 5. El caso del "imprimidor fantasma" 👻: `window.print()`
JavaScript no tiene una manera directa de imprimir algo en una impresora real. Sin embargo, si quieres que el usuario imprima la página web actual, puedes usar `window.print()`.

### Ejemplo:
```html
<!DOCTYPE html>
<html>
<body>

<button onclick="window.print()">Imprimir esta página</button>

</body>
</html>
```

**Analogia**: `window.print()` es como darle al usuario un botón para que saque una copia física de lo que está viendo. Pero ojo, JavaScript no puede controlar la impresora directamente, solo puede decirle al navegador: "Oye, imprime esto".

---

## Resumen 📜
En resumen, JavaScript tiene varios trucos para mostrar o registrar información:
- **`innerHTML`**: Es como escribir en una pizarra visible para todos.
- **`document.write()`**: Es como escribir en un papel mientras se imprime (con riesgo de sobrescribir todo).
- **`window.alert()`**: Es como gritar algo importante con un altavoz.
- **`console.log()`**: Es como llevar un cuaderno de notas privado.
- **`window.print()`**: Es como darle a alguien un botón para que imprima la página actual.

---

# Sentencias de JavaScript 📜

Los **statements** (sentencias) en JavaScript son como instrucciones que un chef sigue para preparar un plato. Cada paso es esencial y se ejecuta en el orden en que se presentan. Vamos a explorar cómo funcionan las sentencias en JavaScript y los elementos que las componen.

## Ejemplo de Sentencias

```javascript
let x, y, z;    // Sentencia 1
x = 5;          // Sentencia 2
y = 6;          // Sentencia 3
z = x + y;      // Sentencia 4
```

### Analogía:
Imagina que tienes tres ingredientes (x, y, z) en tu cocina. Primero, declaras tus ingredientes (sentencia 1), luego decides cuánto tienes de cada uno (sentencias 2 y 3), y al final, mezclas esos ingredientes para obtener un resultado (sentencia 4).

## Programas JavaScript

Un **programa informático** es una lista de "instrucciones" que debe ser "ejecutada" por una computadora. En JavaScript, estas instrucciones se llaman **statements**.

### Ejemplo de una Sentencia:
Esta sentencia le dice al navegador que escriba "Hello Dolly." dentro de un elemento HTML con id="demo":

```javascript
document.getElementById("demo").innerHTML = "Hello Dolly.";
```

### Analogía:
Piensa en el programa JavaScript como una receta de cocina. Cada instrucción (sentencia) debe seguirse para que el plato final se prepare correctamente.

## Componentes de las Sentencias JavaScript

Las sentencias de JavaScript están compuestas por:

- **Valores**: Los ingredientes de tu receta.
- **Operadores**: Las herramientas que utilizas para mezclar o cambiar tus ingredientes.
- **Expresiones**: Las combinaciones de valores y operadores.
- **Palabras clave (keywords)**: Las instrucciones especiales que indican al navegador qué hacer.
- **Comentarios**: Notas que puedes dejar para ti mismo o para otros chefs (programadores).

## Uso de Punto y Coma `;`

Los puntos y comas separan las sentencias en JavaScript. Es como colocar un punto al final de cada oración.

### Ejemplo:
```javascript
let a, b, c;  // Declara 3 variables
a = 5;        // Asigna el valor 5 a a
b = 6;        // Asigna el valor 6 a b
c = a + b;    // Asigna la suma de a y b a c
```

### Analogía:
Si no pones un punto al final de una oración, puede que la gente no sepa dónde termina tu idea. Lo mismo sucede en JavaScript con el uso del punto y coma.

## Espacios en Blanco

JavaScript ignora los espacios adicionales. Puedes agregar espacios para hacer tu script más legible.

### Ejemplo:
```javascript
let person = "Hege";  // Con espacios
let person="Hege";    // Sin espacios
```

### Analogía:
Los espacios son como las pausas en una conversación; ayudan a que tu mensaje sea más claro.

## Longitud de Línea y Saltos de Línea

Para mejorar la legibilidad, es recomendable evitar líneas de código más largas de 80 caracteres. Si una sentencia no cabe en una línea, es mejor dividirla después de un operador.

### Ejemplo:
```javascript
document.getElementById("demo").innerHTML =
"Hello Dolly!";
```

### Analogía:
Es como dividir un párrafo en frases más cortas para que sea más fácil de leer.

## Bloques de Código

Las sentencias de JavaScript pueden agruparse en **bloques de código** dentro de llaves `{...}`. Esto se usa para definir sentencias que se ejecutan juntas.

### Ejemplo:
```javascript
function myFunction() {
  document.getElementById("demo1").innerHTML = "Hello Dolly!";
  document.getElementById("demo2").innerHTML = "How are you?";
}
```

### Analogía:
Un bloque de código es como un grupo de ingredientes que se mezclan para hacer un plato específico. Se necesita todo el bloque para que el resultado final tenga sentido.

## Palabras Clave en JavaScript

Las sentencias de JavaScript a menudo comienzan con una **palabra clave** que identifica la acción a realizar. Aquí hay una lista de algunas palabras clave comunes:

| Palabra clave | Descripción |
|---------------|-------------|
| `var`         | Declara una variable |
| `let`         | Declara una variable de bloque |
| `const`       | Declara una constante de bloque |
| `if`          | Marca un bloque de sentencias a ejecutar bajo una condición |
| `switch`      | Marca un bloque de sentencias a ejecutar en diferentes casos |
| `for`         | Marca un bloque de sentencias a ejecutar en un bucle |
| `function`    | Declara una función |
| `return`      | Sale de una función |
| `try`         | Implementa el manejo de errores para un bloque de sentencias |

### Analogía:
Las palabras clave son como los signos de puntuación en un libro; ayudan a estructurar y dar sentido a la información.

## Conclusión

Las sentencias en JavaScript son esenciales para crear programas que el navegador pueda ejecutar. Cada instrucción debe seguirse cuidadosamente, y la estructura y claridad en la escritura del código son fundamentales para el éxito. ¡Ahora estás listo para seguir aprendiendo más sobre el emocionante mundo de JavaScript! 🎉

---

# Sintaxis de JavaScript

La sintaxis de JavaScript es el conjunto de reglas que define cómo se construyen los programas de JavaScript. Podemos imaginarlo como el conjunto de instrucciones en una receta de cocina; si no seguimos las reglas, no obtendremos el platillo deseado.

## Cómo crear variables

Las variables son como cajas en las que almacenamos información. Para crear estas cajas, usamos las palabras clave `var`, `let` o `const`:

```javascript
// Cómo crear variables:
var x; 
let y;
```

## Cómo usar variables

Una vez que tenemos nuestras cajas, podemos llenarlas con información. Aquí hay un ejemplo de cómo asignar valores a nuestras variables:

```javascript
x = 5;  // Llenamos la caja x con el número 5
y = 6;  // Llenamos la caja y con el número 6
let z = x + y; // Creamos otra caja z que es la suma de x e y
```

### Valores en JavaScript

En JavaScript, hay dos tipos de valores:

1. **Valores fijos** (también llamados literales)
2. **Valores variables** (también llamados variables)

### Literales en JavaScript

Los literales son valores fijos que no cambian. Los dos tipos más importantes son:

1. **Números**: Se escriben con o sin decimales. Ejemplo: `10.50`, `1001`.
2. **Cadenas**: Son textos encerrados entre comillas simples o dobles. Ejemplo: `"John Doe"`, `'John Doe'`.

### Variables en JavaScript

Las variables son utilizadas para almacenar datos. Utilizamos `var`, `let` y `const` para declararlas. El signo igual (`=`) se usa para asignar valores a estas variables. Por ejemplo:

```javascript
let x;  // Definimos x como una variable
x = 6;  // Asignamos el valor 6 a x
```

### Operadores en JavaScript

JavaScript utiliza operadores aritméticos (`+`, `-`, `*`, `/`) para realizar cálculos. Por ejemplo:

```javascript
(5 + 6) * 10  // Calcula la suma de 5 y 6, luego la multiplica por 10
```

### Expresiones en JavaScript

Una **expresión** es una combinación de valores, variables y operadores que evalúa un resultado. El proceso de cálculo se llama **evaluación**. Por ejemplo, `5 * 10` se evalúa como `50`:

```javascript
5 * 10
```

Las expresiones también pueden contener valores variables, como en el caso de:

```javascript
x * 10
```

### Palabras clave en JavaScript

Las palabras clave son comandos que le indican al navegador qué acciones realizar. Por ejemplo, la palabra clave `let` le dice al navegador que debe crear variables:

```javascript
let x, y;
x = 5 + 6;  // Suma 5 y 6 y asigna el resultado a x
y = x * 10; // Multiplica x por 10 y asigna el resultado a y
```

### Comentarios en JavaScript

No todas las declaraciones de JavaScript se "ejecutan". El código que se encuentra después de dos barras (`//`) o entre `/*` y `*/` es tratado como un comentario y se ignora:

```javascript
let x = 5;   // Esta línea se ejecutará
// x = 6;   Esta línea NO se ejecutará
```

### Identificadores / Nombres

Los **identificadores** son nombres en JavaScript utilizados para nombrar variables, funciones y otros elementos. Las reglas para los nombres legales son las mismas en la mayoría de los lenguajes de programación. Un nombre debe comenzar con:

- Una letra (A-Z o a-z)
- Un signo de dólar ($)
- O un guion bajo (_)

Los caracteres posteriores pueden ser letras, dígitos, guiones bajos o signos de dólar.

**Nota:** No se permiten números como primer carácter en los nombres, para que JavaScript pueda distinguir fácilmente entre identificadores y números.

### JavaScript es sensible a mayúsculas y minúsculas

Todos los identificadores en JavaScript son sensibles a mayúsculas. Por ejemplo, `lastName` y `lastname` son dos variables diferentes:

```javascript
let lastname, lastName;
lastName = "Doe";
lastname = "Peterson";
```

### JavaScript y el uso de Camel Case

Los programadores han utilizado diferentes maneras de unir varias palabras en un nombre de variable. En JavaScript, se prefiere el **Camel Case** que comienza con una letra minúscula:

- **Camel Case** (minúscula al principio): `firstName`, `lastName`
- **Pascal Case** (mayúscula al principio): `FirstName`, `LastName`

### Conjunto de caracteres en JavaScript

JavaScript utiliza el conjunto de caracteres Unicode, que abarca casi todos los caracteres, puntuaciones y símbolos del mundo. Para obtener más información, puedes estudiar nuestra [Referencia completa de Unicode](https://unicode.org/reports/tr51/).

---

Aquí tienes la traducción al español:

# Sintaxis de JavaScript

La sintaxis de JavaScript es el conjunto de reglas que dictan cómo se construyen los programas en JavaScript. Piensa en ella como la gramática de un idioma, proporcionando una estructura que nos permite comunicarnos de manera efectiva con la computadora.

### Cómo Crear Variables
```javascript
// Declarar variables
var x; // forma antigua de declarar variables
let y; // forma moderna de declarar variables
```

### Cómo Usar Variables
```javascript
x = 5; // Asignando un valor a x
y = 6; // Asignando un valor a y
let z = x + y; // Sumando x e y para crear z
```

---

## Valores de JavaScript

La sintaxis de JavaScript define dos tipos de valores:

- **Valores fijos**
- **Valores variables**

Los valores fijos se llaman **Literales**, mientras que los valores variables se refieren como **Variables**.

### Literales de JavaScript

Las dos reglas de sintaxis más importantes para los valores fijos son:

1. **Números** pueden escribirse con o sin decimales:
   - Ejemplo: `10.50`, `1001`
   
2. **Cadenas** son texto, escrito entre comillas dobles o simples:
   - Ejemplo: `"John Doe"` o `'John Doe'`

### Analogía
Piensa en los literales como los bloques de construcción de una estructura. Al igual que puedes usar ladrillos (números enteros) o azulejos (números decimales) para construir una casa, puedes usar ambos tipos de literales en tu código.

---

## Variables de JavaScript

En programación, las variables se utilizan para almacenar valores de datos. Son como cajas etiquetadas donde puedes mantener las cosas organizadas.

JavaScript utiliza las palabras clave `var`, `let` y `const` para declarar variables. Un signo igual (`=`) se utiliza para asignar valores a estas variables.

### Ejemplo
```javascript
let x; // Declarando una variable
x = 6; // Asignando el valor 6 a x
```

---

## Operadores de JavaScript

JavaScript utiliza **operadores aritméticos** (`+`, `-`, `*`, `/`) para calcular valores:

### Ejemplo
```javascript
(5 + 6) * 10 // Evalúa a 110
```

Además, JavaScript utiliza un **operador de asignación** (`=`) para asignar valores a las variables.

### Ejemplo
```javascript
let x, y;
x = 5; // x ahora tiene el valor 5
y = 6; // y ahora tiene el valor 6
```

### Analogía
Imagina que tienes una calculadora (JavaScript) y números (valores). Los operadores son como botones en la calculadora que te ayudan a realizar operaciones para obtener resultados.

---

## Expresiones de JavaScript

Una **expresión** es una combinación de valores, variables y operadores, que se calcula para obtener un valor. Este proceso se llama **evaluación**.

### Ejemplo
```javascript
5 * 10 // Evalúa a 50
x * 10 // Evalúa utilizando el valor de x
```

Los valores también pueden ser cadenas:
```javascript
"John" + " " + "Doe" // Evalúa a "John Doe"
```

### Analogía
Piensa en una expresión como una receta. Los ingredientes (valores) y los métodos de cocción (operadores) se combinan para crear un plato delicioso (resultado).

---

## Palabras Clave de JavaScript

Las palabras clave de JavaScript se utilizan para identificar acciones que se deben realizar. 

### Ejemplo
La palabra clave `let` le dice al navegador que cree variables:
```javascript
let x, y;
x = 5 + 6; // 11
y = x * 10; // 110
```

La palabra clave `var` también le dice al navegador que cree variables, pero generalmente se recomienda menos para la codificación moderna.

### Analogía
Las palabras clave en programación son como los verbos en una oración. Indican las acciones que se deben llevar a cabo.

---

## Comentarios de JavaScript

No todas las declaraciones de JavaScript se ejecutan. 

El código después de dobles barras `//` o entre `/*` y `*/` se trata como un comentario y se ignora:

### Ejemplo
```javascript
let x = 5;   // Esto se ejecutará
// x = 6;   // Esto NO se ejecutará
```

### Analogía
Los comentarios son como notas al pie en un libro. Proporcionan información adicional sin afectar el contenido principal.

---

## Identificadores / Nombres de JavaScript

Los identificadores son los nombres de JavaScript utilizados para nombrar variables, palabras clave y funciones. Las reglas para nombres legales son similares en la mayoría de los lenguajes de programación.

Un nombre de JavaScript debe comenzar con:

- Una letra (A-Z o a-z)
- Un signo de dólar (`$`)
- Un guion bajo (`_`)

Los caracteres posteriores pueden ser letras, dígitos, guiones bajos o signos de dólar. Es importante destacar que los números no pueden ser el primer carácter.

### Analogía
Piensa en los identificadores como etiquetas en cajas de almacenamiento. Te ayudan a identificar lo que hay dentro sin abrirlas.

---

## JavaScript es Sensible a Mayúsculas y Minúsculas

Todos los identificadores de JavaScript son sensibles a mayúsculas y minúsculas. 

### Ejemplo
Las variables `lastName` y `lastname` son dos variables diferentes:
```javascript
let lastname, lastName;
lastName = "Doe";
lastname = "Peterson";
```

JavaScript no interpreta `LET` o `Let` como la palabra clave `let`.

### Analogía
La sensibilidad a mayúsculas y minúsculas es como la diferencia entre letras mayúsculas y minúsculas en una contraseña. Ambas formas se reconocen como distintas.

---

## JavaScript y Camel Case

Históricamente, los programadores han utilizado diferentes formas de unir múltiples palabras en un solo nombre de variable:

- **Guiones** (no permitidos): `first-name`, `last-name`
- **Guion bajo**: `first_name`, `last_name`
- **Upper Camel Case (Pascal Case)**: `FirstName`, `LastName`
- **Lower Camel Case** (más común): `firstName`, `lastName`

### Analogía
Camel case es como crear una etiqueta con múltiples palabras. En lugar de espacios, capitalizas la primera letra de cada palabra para mantenerla ordenada y legible.

---

## Conjunto de Caracteres de JavaScript

JavaScript utiliza el conjunto de caracteres **Unicode**, que cubre (casi) todos los caracteres, puntuaciones y símbolos en el mundo.

### Analogía
Piensa en Unicode como una gigantesca biblioteca donde se almacenan todos los caracteres posibles. Puedes encontrar cualquier carácter que necesites, sin importar cuán único u obscuro sea.

---

## Conclusión

Entender la sintaxis de JavaScript es esencial para cualquier aspirante a desarrollador frontend. Proporciona la base sobre la cual puedes construir aplicaciones más complejas. Al usar analogías, podemos relacionar conceptos técnicos con experiencias cotidianas, haciendo que el aprendizaje sea más accesible y agradable.

---

# Comentarios en JavaScript

Los **comentarios en JavaScript** son como notas al pie de página en un libro. Ayudan a explicar el código, haciéndolo más legible y comprensible. También son útiles para evitar la ejecución de ciertas líneas de código cuando estamos probando alternativas. 

## Comentarios de Una Línea

Los comentarios de una línea comienzan con `//`. Cualquier texto que esté entre `//` y el final de la línea será ignorado por JavaScript (no será ejecutado).

### Ejemplo

```javascript
// Cambiar el encabezado:
document.getElementById("myH").innerHTML = "Mi Primera Página";

// Cambiar el párrafo:
document.getElementById("myP").innerHTML = "Mi primer párrafo.";
```

En este ejemplo, hemos utilizado un comentario de una línea antes de cada línea de código para explicar qué está haciendo.

### Comentarios de Una Línea al Final de Cada Línea

También puedes usar un comentario de una línea al final de cada línea para explicar el código:

```javascript
let x = 5;      // Declarar x, darle el valor de 5
let y = x + 2;  // Declarar y, darle el valor de x + 2
```

## Comentarios Multilínea

Los comentarios multilínea comienzan con `/*` y terminan con `*/`. Cualquier texto entre `/*` y `*/` será ignorado por JavaScript.

### Ejemplo

```javascript
/*
El código a continuación cambiará
el encabezado con id = "myH"
y el párrafo con id = "myP"
en mi página web:
*/
document.getElementById("myH").innerHTML = "Mi Primera Página";
document.getElementById("myP").innerHTML = "Mi primer párrafo.";
```

Es más común usar comentarios de una línea, mientras que los comentarios de bloque se utilizan a menudo para documentación formal.

## Usando Comentarios para Prevenir Ejecución

Usar comentarios para prevenir la ejecución del código es adecuado para probar código. Agregar `//` al inicio de una línea de código cambia esa línea de código ejecutable a un comentario.

### Ejemplo

```javascript
//document.getElementById("myH").innerHTML = "Mi Primera Página";
document.getElementById("myP").innerHTML = "Mi primer párrafo.";
```

En este ejemplo, hemos utilizado `//` para prevenir la ejecución de una de las líneas de código.

### Comentario de Bloque para Prevenir Ejecución de Múltiples Líneas

También puedes usar un comentario de bloque para prevenir la ejecución de múltiples líneas:

```javascript
/*
document.getElementById("myH").innerHTML = "Mi Primera Página";
document.getElementById("myP").innerHTML = "Mi primer párrafo.";
*/
```

## Resumen

Los comentarios son herramientas esenciales en JavaScript que permiten a los desarrolladores explicar y documentar su código, así como también controlar la ejecución de ciertas líneas de código durante la fase de prueba.

---

# Variables de JavaScript

## Variables: Contenedores de Datos

Una **variable** en JavaScript es como una caja en la que guardamos algo (un dato) para poder usarlo después. Igual que cuando guardamos algo importante en una caja y le ponemos una etiqueta para saber qué hay dentro, en JavaScript le damos un nombre a la variable para identificarla.

### Formas de declarar variables en JavaScript

Podemos declarar variables de 4 maneras:

1. Automáticamente
2. Usando `var`
3. Usando `let`
4. Usando `const`

**Ejemplo de declaración automática**:
```javascript
x = 5;
y = 6;
z = x + y;
```

Aquí, no hemos usado ninguna palabra clave (como `var` o `let`), pero las variables `x`, `y`, y `z` se han creado automáticamente cuando las usamos. Sin embargo, **no es recomendable** hacerlo así porque puede causar confusión en el código.

### El uso de `var`, `let` y `const`

#### `var`: El clásico pero desactualizado
```javascript
var x = 5;
var y = 6;
var z = x + y;
```
Antes de 2015, todas las variables en JavaScript se declaraban con `var`. Hoy en día, ya no se recomienda usar `var` a menos que estés trabajando con navegadores antiguos.

#### `let`: La mejor opción para variables que cambian
```javascript
let x = 5;
let y = 6;
let z = x + y;
```
La palabra clave `let` se introdujo en 2015 y es mejor utilizarla cuando la variable que estás creando podría cambiar en el futuro.

#### `const`: Para valores que no cambian
```javascript
const x = 5;
const y = 6;
const z = x + y;
```
Con `const`, declaramos una variable que no puede cambiar su valor. Es útil cuando sabes que un valor no debería modificarse, como el precio de algo o el valor de `pi` (3.14).

**Ejemplo mixto:**
```javascript
const price1 = 5;
const price2 = 6;
let total = price1 + price2;
```
En este ejemplo, `price1` y `price2` son constantes, pero `total` es una variable que puede cambiar. Esta es una buena práctica: usa `const` siempre que puedas y `let` cuando necesites que el valor cambie.

## ¿Cuándo usar `var`, `let`, o `const`?

1. **Siempre** declara las variables antes de usarlas.
2. Usa `const` si el valor no debe cambiar.
3. Usa `let` solo si el valor va a cambiar.
4. Usa `var` solo si necesitas compatibilidad con navegadores antiguos.

## Variables y Álgebra

Las variables en JavaScript son como las de álgebra. Por ejemplo:

```javascript
let x = 5;
let y = 6;
let z = x + y;
```

En este caso, las variables `x` y `y` almacenan los valores 5 y 6, respectivamente, y `z` almacena el resultado de sumarlos: 11.

## Identificadores en JavaScript

Todos los nombres de variables deben ser únicos. Estos nombres se llaman **identificadores** y deben seguir algunas reglas:

- Pueden contener letras, dígitos, guiones bajos (`_`) y signos de dólar (`$`).
- Deben comenzar con una letra, `$` o `_`.
- Son **sensibles a mayúsculas** (`x` y `X` son diferentes variables).
- No puedes usar palabras reservadas como nombres de variables (por ejemplo, `let`, `var`, `function`, etc.).

## Operador de Asignación

El operador `=` en JavaScript no significa "igual a", sino que **asigna** un valor a una variable. Por ejemplo:

```javascript
x = x + 5;
```

Esto no tendría sentido en álgebra, pero en JavaScript significa: toma el valor actual de `x`, súmale 5 y guarda el resultado de nuevo en `x`.

## Tipos de Datos

En JavaScript, las variables pueden contener diferentes tipos de datos:

- **Números**: como `100`.
- **Cadenas de texto (strings)**: como `"John Doe"`.

Las cadenas de texto deben ir entre comillas simples o dobles, mientras que los números no llevan comillas.

```javascript
const pi = 3.14;
let person = "John Doe";
let answer = 'Yes I am!';
```

## Declaración y Asignación

Declarar una variable es crearla. Puedes declarar una variable sin asignarle un valor, como en este ejemplo:

```javascript
let carName;
```

Más tarde puedes asignarle un valor:

```javascript
carName = "Volvo";
```

También puedes hacerlo todo en una línea:

```javascript
let carName = "Volvo";
```

## Múltiples Variables

Puedes declarar varias variables a la vez separándolas por comas:

```javascript
let person = "John Doe", carName = "Volvo", price = 200;
```

## Valores `undefined`

Si declaras una variable sin asignarle un valor, su valor será `undefined` hasta que le asignes uno.

```javascript
let carName;
```

## Re-declaración de Variables

Si usas `var`, puedes re-declarar una variable sin perder su valor, pero con `let` o `const`, no es posible:

```javascript
var carName = "Volvo";
var carName;
```

Esto es válido, pero el siguiente código no funcionará:

```javascript
let carName = "Volvo";
let carName; // Error
```

## Operaciones Matemáticas con Variables

Como en álgebra, puedes realizar operaciones matemáticas:

```javascript
let x = 5 + 2 + 3; // Resultado: 10
```

Si sumas cadenas de texto, se concatenarán:

```javascript
let x = "John" + " " + "Doe"; // Resultado: "John Doe"
```

## El Signo de Dólar `$` y el Guion Bajo `_`

JavaScript permite usar `$` y `_` en los nombres de las variables. Aunque no es común, algunos programadores lo usan, especialmente en bibliotecas como jQuery donde `$` es una función principal.

```javascript
let $ = "Hello World";
let _lastName = "Johnson";
```

Estas convenciones a veces se usan para marcar variables privadas o funciones específicas.

---

# JavaScript `let`

El concepto de las variables `let` en JavaScript puede parecer técnico, pero es como organizar tus herramientas en una caja según el trabajo que necesitas hacer. Imagina que `let` es una herramienta que solo puedes usar dentro de una habitación (bloque), y que si sales de esa habitación, no podrás llevarla contigo.

## Introducción

El keyword `let` fue introducido en **ES6 (2015)** y es como decirle a JavaScript: "Voy a usar esta variable solo en este espacio, no fuera de él". Es como si llevaras una linterna en una cueva; cuando sales de la cueva, ya no tienes acceso a esa luz.

### ¿Qué hace `let` especial?

- Las variables declaradas con `let` **tienen alcance de bloque**.
- Deben ser **declaradas antes de usarse**.
- No puedes **re-declararlas** en el mismo bloque.

## Alcance de Bloque (Block Scope)

Antes de ES6, JavaScript no tenía este concepto de límite dentro de un bloque. Pero ahora, con `let`, si declaras una variable dentro de un bloque `{}`, no puedes usarla afuera. Imagina que dentro de la cueva (bloque) tienes herramientas (`let` variables), pero cuando sales, ya no puedes usarlas más.

```javascript
{
  let x = 2;
}
// No puedes usar 'x' aquí, se queda dentro del bloque
```

## Alcance Global

Ahora, comparemos `let` con su primo más viejo, el keyword `var`. `var` es como una herramienta que puedes usar en cualquier parte del proyecto, ya sea que estés dentro o fuera de la cueva. Las variables declaradas con `var` tienen **alcance global**, y puedes usarlas incluso fuera del bloque donde fueron declaradas.

```javascript
{
  var x = 2;
}
// Puedes usar 'x' aquí
```

## No Se Puede Re-declarar

Otra ventaja de `let` es que evita que accidentalmente declares la misma variable dos veces en el mismo bloque. Es como si pusieras una etiqueta a tus herramientas en la cueva para que no traigas otra con el mismo nombre. Si lo intentas, JavaScript te dirá: "Ya tienes una herramienta llamada así".

```javascript
let x = "John Doe";
let x = 0; // Error: ya existe una variable 'x' en este bloque
```

Por otro lado, con `var`, puedes re-declarar variables sin que JavaScript te avise, lo que puede generar errores. Es como si tuvieras dos herramientas con el mismo nombre en tu caja y no supieras cuál usar.

```javascript
var x = "John Doe";
var x = 0; // No hay problema, pero puede ser confuso
```

## Hoisting

Una característica especial de JavaScript es el **hoisting**. Es como si tus herramientas estuvieran mágicamente disponibles desde el inicio, incluso antes de que las hayas declarado. Pero con `let`, aunque la herramienta "sube" al inicio del bloque, no puedes usarla hasta que realmente la hayas declarado. Si lo intentas, obtendrás un error.

```javascript
carName = "Saab";  // Error: no puedes usarla antes de declararla
let carName = "Volvo";
```

Con `var`, por otro lado, podrías usar la variable incluso antes de declararla, lo que a veces puede ser problemático.

```javascript
carName = "Volvo"; // Funciona, pero es peligroso
var carName;
```

## Cuándo Usar `let` y `var`

- **Usa `let`** cuando necesites una variable que solo se use en un área específica de tu código (como dentro de un bloque `{}`).
- **Usa `var`** solo si trabajas con navegadores muy viejos (aunque es mejor evitarlo cuando sea posible).

Recuerda, `let` te ayuda a mantener tus variables controladas dentro de espacios pequeños, como si guardas tus herramientas en una caja separada por trabajo. Mientras que `var` deja tus herramientas por todo el lugar, lo cual puede causar confusión si no tienes cuidado.

## Ejemplo Completo

```javascript
let x = 10;
// Aquí 'x' es 10

{
  let x = 2; // Dentro de este bloque, 'x' es 2
  console.log(x); // Imprime 2
}

console.log(x); // Aquí 'x' vuelve a ser 10, fuera del bloque
```

En este ejemplo, es como si usaras una herramienta dentro de la cueva (bloque) y luego volvieras a usar la misma herramienta, pero fuera de la cueva. La `x` dentro del bloque y fuera del bloque son diferentes.

---

¡Y eso es todo sobre `let`! Es una herramienta poderosa que te ayuda a controlar mejor el alcance de tus variables y evitar errores en tu código. Recuerda: `let` es como organizar tus herramientas por proyectos. Úsalo para evitar confusiones y mantener tu código limpio y claro.

---

# Constantes en JavaScript

El keyword `const` fue introducido en ES6 (2015).

## Conceptos Clave

- **Variables definidas con `const` no pueden ser redeclaradas.**
- **Variables definidas con `const` no pueden ser reasignadas.**
- **Las variables definidas con `const` tienen un scope de bloque.**

## No se Puede Reasignar

Una variable definida con el keyword `const` no puede ser reasignada. 

### Ejemplo
```javascript
const PI = 3.141592653589793;
PI = 3.14;      // Esto dará un error
PI = PI + 10;   // Esto también dará un error
```

## Debe Ser Asignada

Las variables `const` deben tener un valor asignado al momento de ser declaradas.

### Correcto
```javascript
const PI = 3.14159265359;
```

### Incorrecto
```javascript
const PI;
PI = 3.14159265359; // Esto dará un error
```

## ¿Cuándo usar `const` en JavaScript?

Siempre declara una variable con `const` cuando sepas que el valor no debería cambiar. Usa `const` al declarar:

- Un nuevo Array
- Un nuevo Object
- Una nueva Function
- Una nueva RegExp

## Objetos y Arreglos Constantes

El keyword `const` puede ser un poco engañoso. No define un valor constante, sino una referencia constante a un valor. Por lo tanto, **no puedes**:

- Reasignar un valor constante
- Reasignar un arreglo constante
- Reasignar un objeto constante

Pero **sí puedes**:

- Cambiar los elementos de un arreglo constante
- Cambiar las propiedades de un objeto constante

### Arreglos Constantes
Puedes cambiar los elementos de un arreglo constante:

#### Ejemplo
```javascript
// Puedes crear un arreglo constante:
const cars = ["Saab", "Volvo", "BMW"];

// Puedes cambiar un elemento:
cars[0] = "Toyota";

// Puedes agregar un elemento:
cars.push("Audi");
```

Pero **no puedes** reasignar el arreglo:

#### Ejemplo
```javascript
const cars = ["Saab", "Volvo", "BMW"];

cars = ["Toyota", "Volvo", "Audi"]; // ERROR
```

### Objetos Constantes
Puedes cambiar las propiedades de un objeto constante:

#### Ejemplo
```javascript
// Puedes crear un objeto const:
const car = {type: "Fiat", model: "500", color: "white"};

// Puedes cambiar una propiedad:
car.color = "red";

// Puedes agregar una propiedad:
car.owner = "Johnson";
```

Pero **no puedes** reasignar el objeto:

#### Ejemplo
```javascript
const car = {type: "Fiat", model: "500", color: "white"};

car = {type: "Volvo", model: "EX60", color: "red"}; // ERROR
```

## Diferencias entre `var`, `let` y `const`

| Scope | Redeclare | Reassign | Hoisted | Binds this |
|-------|-----------|----------|---------|------------|
| var   | No        | Sí       | Sí      | Sí         |
| let   | Sí        | No       | Sí      | No         |
| const | No        | No       | No      | No         |

## ¿Qué es Bueno?

- `let` y `const` tienen scope de bloque.
- `let` y `const` no pueden ser redeclarados.
- `let` y `const` deben ser declarados antes de usarse.
- `let` y `const` no se vinculan a `this`.
- `let` y `const` no son hoisted.

## ¿Qué No es Bueno?

- `var` no tiene que ser declarado.
- `var` es hoisted.
- `var` se vincula a `this`.

## Soporte en Navegadores

Los keywords `let` y `const` no son compatibles en Internet Explorer 11 o versiones anteriores. La siguiente tabla define las primeras versiones de navegador con soporte completo:

| Navegador | Versión |
|-----------|---------|
| Chrome    | 49      |
| Edge      | 12      |
| Firefox    | 36      |
| Safari    | 11      |
| Opera     | 36      |
| Fecha     | Mar, 2016 / Jul, 2015 / Jan, 2015 / Sep, 2017 / Mar, 2016 |

## Scope de Bloque

Declarar una variable con `const` es similar a `let` en cuanto a scope de bloque. La `x` declarada en el bloque no es la misma que la `x` declarada fuera del bloque:

### Ejemplo
```javascript
const x = 10;
// Aquí x es 10

{
  const x = 2;
  // Aquí x es 2
}

// Aquí x es 10
```

Puedes aprender más sobre el scope de bloque en el capítulo **JavaScript Scope**.

## Redeclaración

Redeclarar una variable `var` en JavaScript es permitido en cualquier parte de un programa:

### Ejemplo
```javascript
var x = 2;     // Permitido
var x = 3;     // Permitido
x = 4;         // Permitido
```

Redeclarar una variable existente `var` o `let` a `const`, en el mismo scope, no está permitido:

### Ejemplo
```javascript
var x = 2;     // Permitido
const x = 2;   // No permitido

{
  let x = 2;     // Permitido
  const x = 2;   // No permitido
}

{
  const x = 2;   // Permitido
  const x = 2;   // No permitido
}
```

Reasignar una variable existente `const`, en el mismo scope, no está permitido:

### Ejemplo
```javascript
const x = 2;     // Permitido
x = 2;           // No permitido
var x = 2;       // No permitido
let x = 2;       // No permitido
const x = 2;     // No permitido

{
  const x = 2;   // Permitido
  x = 2;         // No permitido
  var x = 2;     // No permitido
  let x = 2;     // No permitido
  const x = 2;   // No permitido
}
```

Redeclarar una variable con `const`, en otro scope o en otro bloque, es permitido:

### Ejemplo
```javascript
const x = 2;       // Permitido

{
  const x = 3;   // Permitido
}

{
  const x = 4;   // Permitido
}
```

## Hoisting

Las variables definidas con `var` son hoisted al inicio y pueden ser inicializadas en cualquier momento.

Significa: Puedes usar la variable antes de que sea declarada.

### Ejemplo
```javascript
// Esto está bien:
carName = "Volvo";
var carName;
```

Si quieres aprender más sobre hoisting, estudia el capítulo **JavaScript Hoisting**.

Las variables definidas con `const` también son hoisted al inicio, pero no inicializadas.

Significa: Usar una variable `const` antes de que sea declarada resultará en un `ReferenceError`:

### Ejemplo
```javascript
alert(carName); // ReferenceError
const carName = "Volvo";
```

### Notas
- Asegúrate de que el contenido sea claro y accesible para cualquier persona que lo lea.
- Puedes agregar más ejemplos y analogías en el futuro para otros conceptos de JavaScript, manteniendo el mismo formato.
- Este tipo de explicaciones puede ayudar a aquellos que están aprendiendo JavaScript a comprender mejor los conceptos técnicos mediante comparaciones simples.

---

# Operadores en JavaScript

Los **operadores de JavaScript** se utilizan para realizar diferentes tipos de cálculos matemáticos y lógicos.

## Ejemplos:
- El **Operador de Asignación** `=` asigna valores.
- El **Operador de Suma** `+` suma valores.
- El **Operador de Multiplicación** `*` multiplica valores.
- El **Operador de Comparación** `>` compara valores.

## JavaScript Assignment

El **Operador de Asignación** `=` asigna un valor a una variable:

### Ejemplos de Asignación
```javascript
let x = 10; // Asigna el valor 10 a x
let y = 2;  // Asigna el valor 2 a y
let z = x + y; // Asigna la suma de x e y a z
```
*Analogía:* Piensa en `=` como un mensajero que entrega el valor a la variable, que es como una caja que almacena ese valor.

## JavaScript Addition

El **Operador de Suma** `+` suma números:

### Suma
```javascript
let x = 5;
let y = 2;
let z = x + y; // z ahora es 7
```
*Analogía:* Imagina que `x` y `y` son dos montones de manzanas, y el operador `+` es alguien que las junta en un solo montón.

## JavaScript Multiplication

El **Operador de Multiplicación** `*` multiplica números:

### Multiplicación
```javascript
let x = 5;
let y = 2;
let z = x * y; // z ahora es 10
```
*Analogía:* Visualiza `x` como el número de cajas que tienes y `y` como cuántas manzanas hay en cada caja. `*` te da el total de manzanas.

## Tipos de Operadores en JavaScript

Hay diferentes tipos de operadores en JavaScript:

- **Operadores Aritméticos**
- **Operadores de Asignación**
- **Operadores de Comparación**
- **Operadores de Cadena**
- **Operadores Lógicos**
- **Operadores Bitwise**
- **Operadores Ternarios**
- **Operadores de Tipo**

## JavaScript Arithmetic Operators

Los **Operadores Aritméticos** se utilizan para realizar operaciones aritméticas en números:

### Ejemplo de Operadores Aritméticos
```javascript
let a = 3;
let x = (100 + 50) * a; // x ahora es 450
```
| Operador | Descripción                |
|----------|----------------------------|
| `+`      | Suma                       |
| `-`      | Resta                      |
| `*`      | Multiplicación             |
| `**`     | Exponenciación (ES2016)   |
| `/`      | División                   |
| `%`      | Módulo (Resto de División) |
| `++`     | Incremento                 |
| `--`     | Decremento                 |

## JavaScript Assignment Operators

Los **Operadores de Asignación** asignan valores a las variables de JavaScript.

El **Operador de Asignación de Suma** `+=` agrega un valor a una variable.

### Asignación
```javascript
let x = 10;
x += 5; // x ahora es 15
```
| Operador | Ejemplo  | Equivale a   |
|----------|----------|--------------|
| `=`      | `x = y`  | `x = y`      |
| `+=`     | `x += y` | `x = x + y`  |
| `-=`     | `x -= y` | `x = x - y`  |
| `*=`     | `x *= y` | `x = x * y`  |
| `/=`     | `x /= y` | `x = x / y`  |
| `%=`     | `x %= y` | `x = x % y`  |
| `**=`    | `x **= y`| `x = x ** y` |

## JavaScript Comparison Operators

Los **Operadores de Comparación** se utilizan para comparar valores:

| Operador | Descripción                       |
|----------|-----------------------------------|
| `==`     | igual a                           |
| `===`    | igual valor y tipo igual          |
| `!=`     | no igual                          |
| `!==`    | no igual valor o tipo             |
| `>`      | mayor que                         |
| `<`      | menor que                         |
| `>=`     | mayor o igual que                 |
| `<=`     | menor o igual que                 |
| `?`      | operador ternario                 |

*Analogía:* Imagina que los operadores de comparación son jueces que evalúan las evidencias (valores) y determinan si son iguales, mayores o menores.

## JavaScript String Comparison

Todos los operadores de comparación anteriores también se pueden usar en cadenas:

### Ejemplo
```javascript
let text1 = "A";
let text2 = "B";
let result = text1 < text2; // true, porque "A" es menor que "B"
```
*Nota:* Las cadenas se comparan alfabéticamente.

## JavaScript String Addition

El `+` también se utiliza para sumar (concatenar) cadenas:

### Ejemplo
```javascript
let text1 = "John";
let text2 = "Doe";
let text3 = text1 + " " + text2; // "John Doe"
```
*Analogía:* Piensa en la concatenación de cadenas como en la creación de una frase al unir palabras.

## JavaScript Logical Operators

Los **Operadores Lógicos** se utilizan para combinar expresiones booleanas:

| Operador | Descripción  |
|----------|--------------|
| `&&`     | y lógico     |
| `||`     | o lógico     |
| `!`      | no lógico    |

## JavaScript Type Operators

Los **Operadores de Tipo** se utilizan para verificar el tipo de una variable:

| Operador     | Descripción                            |
|--------------|----------------------------------------|
| `typeof`     | Devuelve el tipo de una variable      |
| `instanceof` | Devuelve verdadero si un objeto es de un tipo de objeto |

## JavaScript Bitwise Operators

Los operadores bit a bit trabajan con números de 32 bits. Cualquier operando numérico en la operación se convierte en un número de 32 bits. El resultado se convierte de nuevo en un número de JavaScript.

### Ejemplo de Operadores Bitwise
| Operador | Descripción              | Ejemplo   | Resultado |
|----------|--------------------------|-----------|-----------|
| `&`      | Y                        | `5 & 1`   | `1`       |
| `|`      | O                        | `5 | 1`   | `5`       |
| `~`      | NO                       | `~5`      | `-6`      |
| `^`      | XOR                      | `5 ^ 1`   | `4`       |
| `<<`     | desplazamiento a la izquierda | `5 << 1` | `10`      |
| `>>`     | desplazamiento a la derecha  | `5 >> 1` | `2`       |
| `>>>`    | desplazamiento a la derecha sin signo | `5 >>> 1` | `2` |

*Nota:* Los ejemplos anteriores usan ejemplos de 4 bits, pero JavaScript utiliza números de 32 bits con signo. Por lo tanto, en JavaScript, `~5` no devolverá `10`, sino `-6`.

---


# Aritmetica en JavaScript

## JavaScript Arithmetic Operators

Los operadores aritméticos realizan operaciones matemáticas en números (literales o variables). Imagina que los operadores son como herramientas en una caja de herramientas: cada uno tiene una función específica para ayudarte a resolver diferentes problemas numéricos.

| Operador | Descripción                     |
|----------|---------------------------------|
| `+`      | Suma                            |
| `-`      | Resta                           |
| `*`      | Multiplicación                  |
| `**`     | Exponenciación (ES2016)        |
| `/`      | División                        |
| `%`      | Módulo (Resto)                 |
| `++`     | Incremento                     |
| `--`     | Decremento                     |

## Operaciones Aritméticas

Una operación aritmética típica opera sobre dos números. Imagina que estos números son ingredientes que necesitas para una receta.

Los dos números pueden ser literales:

```javascript
let x = 100 + 50; // Aquí estamos usando literales
```

O variables:

```javascript
let a = 20;
let b = 30;
let x = a + b; // Aquí estamos usando variables
```

O expresiones:

```javascript
let x = (100 + 50) * a; // Aquí estamos usando una expresión
```

## Operadores y Operandos

Los números en una operación aritmética se llaman **operandos**. La operación que se realizará entre los dos operandos está definida por un **operador**. Piensa en los operandos como los ingredientes y el operador como la receta que indica cómo mezclar esos ingredientes.

```
Operand	Operador	Operand
100	    +	    50
```

### Sumar

El operador de suma (`+`) añade números:

```javascript
let x = 5;
let y = 2;
let z = x + y; // z ahora es 7
```

### Restar

El operador de resta (`-`) sustrae números:

```javascript
let x = 5;
let y = 2;
let z = x - y; // z ahora es 3
```

### Multiplicar

El operador de multiplicación (`*`) multiplica números:

```javascript
let x = 5;
let y = 2;
let z = x * y; // z ahora es 10
```

### Dividir

El operador de división (`/`) divide números:

```javascript
let x = 5;
let y = 2;
let z = x / y; // z ahora es 2.5
```

### Módulo

El operador de módulo (`%`) devuelve el resto de la división:

```javascript
let x = 5;
let y = 2;
let z = x % y; // z ahora es 1
```

En aritmética, la división de dos enteros produce un cociente y un resto. En matemáticas, el resultado de una operación de módulo es el resto de una división aritmética.

### Incrementar

El operador de incremento (`++`) incrementa números:

```javascript
let x = 5;
x++; // x ahora es 6
```

### Decrementar

El operador de decremento (`--`) decrementa números:

```javascript
let x = 5;
x--; // x ahora es 4
```

### Exponenciación

El operador de exponenciación (`**`) eleva el primer operando a la potencia del segundo operando:

```javascript
let x = 5;
let z = x ** 2; // z ahora es 25
```

La operación `x ** y` produce el mismo resultado que `Math.pow(x, y)`:

```javascript
let z = Math.pow(x, 2); // z ahora es 25
```

## Precedencia de Operadores

La precedencia de operadores describe el orden en que se realizan las operaciones en una expresión aritmética. Piensa en esto como las reglas de una competencia: algunas acciones deben realizarse antes que otras.

```javascript
let x = 100 + 50 * 3; // ¿Es el resultado igual a 150 * 3, o es el mismo que 100 + 150?
```

Como en las matemáticas escolares, la multiplicación se realiza primero. La multiplicación (`*`) y la división (`/`) tienen una precedencia más alta que la suma (`+`) y la resta (`-`). 

Y, al igual que en las matemáticas, la precedencia se puede cambiar utilizando paréntesis:

```javascript
let x = (100 + 50) * 3; // Aquí se suman primero 100 + 50 antes de multiplicar por 3
```

Cuando muchas operaciones tienen la misma precedencia (como suma y resta o multiplicación y división), se calculan de izquierda a derecha:

```javascript
let x = 100 + 50 - 3; // Se suma primero, luego se resta
let x = 100 / 50 * 3; // Se divide primero, luego se multiplica
```

## Notas

Para una lista completa de los valores de precedencia de operadores, visita [JavaScript Operator Precedence Values](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence).

---

# JavaScript Assignment

## JavaScript Assignment Operators

Los operadores de asignación asignan valores a variables en JavaScript. Imagina que una variable es una caja donde puedes guardar un valor. Cuando usas un operador de asignación, es como si estuvieras poniendo un nuevo objeto en la caja. Aquí hay una lista de operadores de asignación y cómo funcionan:

| Operador | Ejemplo      | Igual a          |
|----------|--------------|------------------|
| =        | `x = y`     | `x = y`          |
| +=       | `x += y`    | `x = x + y`      |
| -=       | `x -= y`    | `x = x - y`      |
| *=       | `x *= y`    | `x = x * y`      |
| /=       | `x /= y`    | `x = x / y`      |
| %=       | `x %= y`    | `x = x % y`      |
| **=      | `x **= y`   | `x = x ** y`     |

## Shift Assignment Operators

Los operadores de desplazamiento de asignación mueven los bits de un número a la izquierda o a la derecha. Piensa en ello como si estuvieras moviendo los muebles en una habitación.

| Operador | Ejemplo      | Igual a          |
|----------|--------------|------------------|
| <<=      | `x <<= y`    | `x = x << y`     |
| >>=      | `x >>= y`    | `x = x >> y`     |
| >>>=     | `x >>>= y`   | `x = x >>> y`    |

## Bitwise Assignment Operators

Los operadores de asignación de bit a bit realizan operaciones a nivel de bits. Imagina que los bits son pequeñas luces que pueden estar encendidas (1) o apagadas (0).

| Operador | Ejemplo      | Igual a          |
|----------|--------------|------------------|
| &=       | `x &= y`    | `x = x & y`      |
| ^=       | `x ^= y`    | `x = x ^ y`      |
| |=       | `x |= y`    | `x = x | y`      |

## Logical Assignment Operators

Los operadores de asignación lógica combinan operaciones lógicas con la asignación. Piensa en ellos como en una prueba de admisión: solo se asigna un valor si ciertas condiciones se cumplen.

| Operador | Ejemplo      | Igual a          |
|----------|--------------|------------------|
| &&=      | `x &&= y`    | `x = x && (x = y)` |
| ||=       | `x ||= y`    | `x = x || (x = y)` |
| ??=      | `x ??= y`   | `x = x ?? (x = y)` |

**Nota:** Los operadores de asignación lógica son una característica de ES2020.

## El Operador `=`

El operador de asignación simple asigna un valor a una variable. Piensa en ello como etiquetar una caja con un número.

**Ejemplos de Asignación Simple:**

```javascript
let x = 10; // Se asigna el valor 10 a la variable x
let x = 10 + y; // Se asigna el resultado de 10 + y a la variable x
```

## El Operador `+=`

El operador de asignación de suma suma un valor a una variable existente. Es como si agregas más cosas a la caja que ya tienes.

**Ejemplos de Asignación de Suma:**

```javascript
let x = 10;
x += 5; // Ahora x es 15
let text = "Hola"; 
text += " Mundo"; // text ahora es "Hola Mundo"
```

## El Operador `-=`

El operador de asignación de resta resta un valor de una variable. Imagina que sacas un objeto de la caja.

**Ejemplo de Asignación de Resta:**

```javascript
let x = 10;
x -= 5; // Ahora x es 5
```

## El Operador `*=`

El operador de asignación de multiplicación multiplica una variable por un valor.

**Ejemplo de Asignación de Multiplicación:**

```javascript
let x = 10;
x *= 5; // Ahora x es 50
```

## El Operador `**=`

El operador de asignación de exponenciación eleva una variable a la potencia del valor especificado. Es como multiplicar la caja por sí misma varias veces.

**Ejemplo de Asignación de Exponenciación:**

```javascript
let x = 10;
x **= 5; // Ahora x es 100000
```

## El Operador `/=`

El operador de asignación de división divide una variable por un valor.

**Ejemplo de Asignación de División:**

```javascript
let x = 10;
x /= 5; // Ahora x es 2
```

## El Operador `%=`

El operador de asignación de resto asigna el resto de una división a una variable.

**Ejemplo de Asignación de Resto:**

```javascript
let x = 10;
x %= 5; // Ahora x es 0
```

## El Operador `<<=`

El operador de desplazamiento a la izquierda asigna el valor desplazado a la variable. Es como mover todo hacia la izquierda en una fila.

**Ejemplo de Desplazamiento a la Izquierda:**

```javascript
let x = -100;
x <<= 5; // Mueve los bits de x 5 lugares a la izquierda
```

## El Operador `>>=`

El operador de desplazamiento a la derecha asigna el valor desplazado a la variable, manteniendo el signo.

**Ejemplo de Desplazamiento a la Derecha:**

```javascript
let x = -100;
x >>= 5; // Mueve los bits de x 5 lugares a la derecha
```

## El Operador `>>>=`

El operador de desplazamiento a la derecha sin signo asigna el valor desplazado a la variable sin mantener el signo.

**Ejemplo de Desplazamiento a la Derecha sin Signo:**

```javascript
let x = -100;
x >>>= 5; // Mueve los bits de x 5 lugares a la derecha sin mantener el signo
```

## El Operador `&=`

El operador de asignación de AND a nivel de bits realiza una operación AND bit a bit y asigna el resultado.

**Ejemplo de Asignación de AND:**

```javascript
let x = 10;
x &= 5; // Realiza AND bit a bit entre x y 5
```

## El Operador `|=`

El operador de asignación de OR a nivel de bits realiza una operación OR bit a bit y asigna el resultado.

**Ejemplo de Asignación de OR:**

```javascript
let x = 10;
x |= 5; // Realiza OR bit a bit entre x y 5
```

## El Operador `^=`

El operador de asignación de XOR a nivel de bits realiza una operación XOR bit a bit y asigna el resultado.

**Ejemplo de Asignación de XOR:**

```javascript
let x = 10;
x ^= 5; // Realiza XOR bit a bit entre x y 5
```

## El Operador `&&=`

El operador de asignación lógica AND se usa entre dos valores. Si el primer valor es verdadero, se asigna el segundo valor.

**Ejemplo de Asignación de AND Lógica:**

```javascript
let x = 10;
x &&= 5; // Si x es verdadero, se asigna 5
```

## El Operador `||=`

El operador de asignación lógica OR se usa entre dos valores. Si el primer valor es falso, se asigna el segundo valor.

**Ejemplo de Asignación de OR Lógica:**

```javascript
let x = 10;
x ||= 5; // Si x es falso, se asigna 5
```

## El Operador `??=`

El operador de asignación de coalescencia nula se usa entre dos valores. Si el primer valor es `undefined` o `null`, se asigna el segundo valor.

**Ejemplo de Asignación de Coalescencia Nula:**

```javascript
let x;
x ??= 5; // Si x es undefined, se asigna 5
```

**Nota:** El operador `??=` es una característica de ES2020.

---

# Tipos de Datos en JavaScript

JavaScript tiene **8 tipos de datos**:

1. **String** (Cadena de texto)
2. **Number** (Número)
3. **Bigint** (Número entero grande)
4. **Boolean** (Booleano)
5. **Undefined** (Indefinido)
6. **Null** (Nulo)
7. **Symbol** (Símbolo)
8. **Object** (Objeto)

## El Tipo de Dato Objeto

El tipo de dato objeto puede contener tanto objetos integrados como objetos definidos por el usuario:

### Tipos de objetos integrados pueden ser:

- Objetos
- Arreglos
- Fechas
- Mapas
- Conjuntos
- Arreglos de enteros
- Arreglos de flotantes
- Promesas
- Y más.

### Ejemplos:

```javascript
// Números:
let length = 16;
let weight = 7.5;

// Cadenas:
let color = "Amarillo";
let lastName = "Johnson";

// Booleanos
let x = true;
let y = false;

// Objeto:
const person = {firstName: "John", lastName: "Doe"};

// Objeto Array:
const cars = ["Saab", "Volvo", "BMW"];

// Objeto Fecha:
const date = new Date("2022-03-25");
```

**Nota**: Una variable en JavaScript puede contener cualquier tipo de dato.

## El Concepto de Tipos de Datos

En programación, los tipos de datos son un concepto importante. 

Para poder operar con variables, es esencial conocer su tipo. Sin tipos de datos, una computadora no puede resolver correctamente expresiones como:

```javascript
let x = 16 + "Volvo";
```

¿Tiene sentido sumar "Volvo" a dieciséis? ¿Producirá un error o un resultado?

JavaScript interpretará el ejemplo anterior como:

```javascript
let x = "16" + "Volvo";
```

**Nota**: Al sumar un número y una cadena, JavaScript tratará al número como una cadena.

### Ejemplo 1:

```javascript
let x = 16 + "Volvo"; // Resultado: "16Volvo"
```

### Ejemplo 2:

```javascript
let x = "Volvo" + 16; // Resultado: "Volvo16"
```

JavaScript evalúa las expresiones de izquierda a derecha. Diferentes secuencias pueden producir resultados distintos:

### Ejemplo 3:

```javascript
let x = 16 + 4 + "Volvo"; // Resultado: "20Volvo"
```

### Ejemplo 4:

```javascript
let x = "Volvo" + 16 + 4; // Resultado: "Volvo164"
```

En el primer ejemplo, JavaScript trata a `16` y `4` como números, hasta que encuentra "Volvo". En el segundo ejemplo, como el primer operando es una cadena, todos los operandos se tratarán como cadenas.

## Tipos Dinámicos en JavaScript

JavaScript tiene tipos dinámicos. Esto significa que la misma variable puede contener diferentes tipos de datos:

### Ejemplo:

```javascript
let x;       // Ahora x es indefinido
x = 5;       // Ahora x es un Número
x = "John";  // Ahora x es una Cadena
```

## Cadenas en JavaScript

Una cadena (o string) es una serie de caracteres como "John Doe". Las cadenas se escriben con comillas, ya sea simples o dobles:

### Ejemplo:

```javascript
// Usando comillas dobles:
let carName1 = "Volvo XC60";

// Usando comillas simples:
let carName2 = 'Volvo XC60';
```

Puedes usar comillas dentro de una cadena, siempre que no coincidan con las comillas que rodean la cadena:

### Ejemplo:

```javascript
// Comilla simple dentro de comillas dobles:
let answer1 = "Está bien";

// Comillas simples dentro de comillas dobles:
let answer2 = "Se le llama 'Johnny'";

// Comillas dobles dentro de comillas simples:
let answer3 = 'Se le llama "Johnny"';
```

Aprenderás más sobre cadenas más adelante en este tutorial.

## Números en JavaScript

Todos los números en JavaScript se almacenan como números decimales (punto flotante). Los números pueden escribirse con o sin decimales:

### Ejemplo:

```javascript
// Con decimales:
let x1 = 34.00;

// Sin decimales:
let x2 = 34;
```

### Notación Exponencial

Los números muy grandes o muy pequeños pueden escribirse en notación científica (exponencial):

### Ejemplo:

```javascript
let y = 123e5;    // 12300000
let z = 123e-5;   // 0.00123
```

**Nota**: La mayoría de los lenguajes de programación tienen muchos tipos numéricos:

- Números enteros (enteros):
  - byte (8 bits), short (16 bits), int (32 bits), long (64 bits)

- Números reales (punto flotante):
  - float (32 bits), double (64 bits).

Los números en JavaScript son siempre de un tipo: **double** (punto flotante de 64 bits).

Aprenderás más sobre números más adelante en este tutorial.

## BigInt en JavaScript

Todos los números en JavaScript se almacenan en un formato de punto flotante de 64 bits. BigInt es un nuevo tipo de dato (ES2020) que se puede utilizar para almacenar valores enteros que son demasiado grandes para ser representados por un número normal de JavaScript.

### Ejemplo:

```javascript
let x = BigInt("123456789012345678901234567890");
```

Aprenderás más sobre BigInt más adelante en este tutorial.

## Booleanos en JavaScript

Los booleanos solo pueden tener dos valores: **true** (verdadero) o **false** (falso).

### Ejemplo:

```javascript
let x = 5;
let y = 5;
let z = 6;

(x == y)       // Devuelve true
(x == z)       // Devuelve false
```

Los booleanos se utilizan a menudo en pruebas condicionales. Aprenderás más sobre booleanos más adelante en este tutorial.

## Arreglos en JavaScript

Los arreglos en JavaScript se escriben con corchetes cuadrados. Los elementos del arreglo se separan por comas.

El siguiente código declara (crea) un arreglo llamado **cars**, que contiene tres elementos (nombres de autos):

### Ejemplo:

```javascript
const cars = ["Saab", "Volvo", "BMW"];
```

Los índices de los arreglos comienzan desde cero, lo que significa que el primer elemento es [0], el segundo es [1], y así sucesivamente. Aprenderás más sobre arreglos más adelante en este tutorial.

## Objetos en JavaScript

Los objetos en JavaScript se escriben con llaves `{}`. Las propiedades del objeto se escriben como pares nombre:valor, separadas por comas.

### Ejemplo:

```javascript
const person = {firstName: "John", lastName: "Doe", age: 50, eyeColor: "blue"};
```

El objeto **person** en el ejemplo anterior tiene 4 propiedades: firstName, lastName, age y eyeColor. Aprenderás más sobre objetos más adelante en este tutorial.

## El Operador typeof

Puedes usar el operador **typeof** de JavaScript para encontrar el tipo de una variable.

El operador **typeof** devuelve el tipo de una variable o expresión:

### Ejemplo:

```javascript
typeof "";             // Devuelve "string"
typeof "John";         // Devuelve "string"
typeof "John Doe";     // Devuelve "string"
```

### Ejemplo:

```javascript
typeof 0;              // Devuelve "number"
typeof 314;            // Devuelve "number"
typeof 3.14;           // Devuelve "number"
typeof (3);            // Devuelve "number"
typeof (3 + 4);        // Devuelve "number"
```

Aprenderás más sobre **typeof** más adelante en este tutorial.

## Indefinido

En JavaScript, una variable sin valor tiene el valor **undefined**. El tipo también es **undefined**.

### Ejemplo:

```javascript
let car;    // Valor es indefinido, tipo es indefinido
```

Cualquier variable puede ser vaciada estableciendo su valor a **undefined**. El tipo también será **undefined**.

### Ejemplo:

```javascript
car = undefined;    // Valor es indefinido, tipo es indefinido
```

## Valores Vacíos

Un valor vacío no tiene nada que ver con **undefined**. 

Una cadena vacía tiene tanto un valor legal como un tipo.

### Ejemplo:

```javascript
let car = "";    // El valor es "", el typeof es "string"
```

---

# Funciones en JavaScript

## Funciones en JavaScript

Una función en JavaScript es un bloque de código diseñado para realizar una tarea particular. Imagina que una función es como un electrodoméstico en tu cocina. Cuando necesitas preparar un platillo específico, usas el electrodoméstico que mejor se adapta a esa tarea, ya sea una batidora para mezclar o una olla para cocinar.

### Ejecución de Funciones

Una función de JavaScript se ejecuta cuando "algo" la invoca (la llama). Es como cuando decides usar el electrodoméstico: abres la tapa y presionas el botón de inicio.

### Ejemplo

```javascript
// Función para calcular el producto de p1 y p2
function myFunction(p1, p2) {
  return p1 * p2;
}
```

## Sintaxis de Funciones en JavaScript

Una función de JavaScript se define con la palabra clave `function`, seguida de un nombre, y luego paréntesis `()`.

### Reglas de Nombres de Funciones

Los nombres de las funciones pueden contener letras, dígitos, guiones bajos y signos de dólar (mismas reglas que las variables). 

Los paréntesis pueden incluir nombres de parámetros separados por comas:
`(parametro1, parametro2, ...)`

El código que se ejecutará dentro de la función se coloca entre llaves `{}`.

```javascript
function nombre(parametro1, parametro2, parametro3) {
  // código a ejecutar
}
```

Los parámetros de la función se enumeran dentro de los paréntesis `()` en la definición de la función.

Los argumentos son los valores recibidos por la función cuando se invoca.

Dentro de la función, los argumentos (los parámetros) se comportan como variables locales.

## Invocación de Funciones

El código dentro de la función se ejecutará cuando "algo" invoque (llame) la función. Esto puede ocurrir en varias situaciones:

- **Cuando ocurre un evento** (cuando un usuario hace clic en un botón)
- **Cuando se invoca** (se llama) desde el código JavaScript
- **Automáticamente** (auto-invocada)

### Ejemplo de Invocación

```javascript
// La función se llama, el valor de retorno terminará en x
let x = myFunction(4, 3);
```

## Retorno de Funciones

Cuando JavaScript alcanza una declaración `return`, la función dejará de ejecutarse. 

Si la función fue invocada desde una declaración, JavaScript "regresará" para ejecutar el código después de la declaración que la invocó.

Las funciones a menudo calculan un valor de retorno. El valor de retorno se "devuelve" al "llamador".

### Ejemplo de Retorno

```javascript
function myFunction(a, b) {
  // La función devuelve el producto de a y b
  return a * b;
}
```

## ¿Por qué Usar Funciones?

Las funciones permiten reutilizar código, similar a tener una receta que puedes seguir múltiples veces para preparar el mismo platillo.

Puedes escribir un código que se pueda utilizar muchas veces, y puedes usar el mismo código con diferentes argumentos para producir resultados diferentes.

## Operador ()

El operador `()` invoca (llama) a la función.

### Ejemplo: Convertir Fahrenheit a Celsius

```javascript
function toCelsius(fahrenheit) {
  return (5/9) * (fahrenheit - 32);
}

let valor = toCelsius(77);
```

Acceder a una función con parámetros incorrectos puede devolver una respuesta incorrecta:

### Ejemplo de Error

```javascript
let valor = toCelsius();
```

Acceder a una función sin `()` devuelve la función y no el resultado de la función:

### Ejemplo de Referencia

```javascript
let valor = toCelsius; // Se refiere al objeto función, no al resultado
```

## Funciones Usadas como Valores de Variables

Las funciones pueden utilizarse de la misma manera que utilizas variables, en todo tipo de fórmulas, asignaciones y cálculos.

### Ejemplo de Uso Directo

En lugar de usar una variable para almacenar el valor de retorno de una función:

```javascript
let x = toCelsius(77);
let texto = "La temperatura es " + x + " Celsius";
```

Puedes usar la función directamente como valor de variable:

```javascript
let texto = "La temperatura es " + toCelsius(77) + " Celsius";
```

## Variables Locales

Las variables declaradas dentro de una función de JavaScript se convierten en locales a esa función. Es como tener un espacio de trabajo donde solo tú tienes acceso a tus herramientas.

### Ejemplo de Variable Local

```javascript
function myFunction() {
  let carName = "Volvo"; // Variable local
  // aquí se puede usar carName
}

// fuera de la función, no se puede usar carName
```

Dado que las variables locales solo se reconocen dentro de sus funciones, puedes usar variables con el mismo nombre en diferentes funciones.

Las variables locales se crean cuando una función comienza y se eliminan cuando la función termina.

---

# Objetos en JavaScript

## Objetos de la Vida Real

En la vida real, los objetos son cosas como casas, autos, personas, animales o cualquier otro sujeto.

Aquí hay un ejemplo de objeto auto:

| Car Object | Properties             | Methods                |
|------------|------------------------|------------------------|
| car.name   | Fiat                   | car.start()            |
| car.model  | 500                    | car.drive()            |
| car.weight | 850kg                  | car.brake()            |
| car.color  | blanco                 | car.stop()             |

### Propiedades de los Objetos

Un auto de la vida real tiene propiedades como peso y color:

- `car.name = Fiat`
- `car.model = 500`
- `car.weight = 850kg`
- `car.color = blanco`

Los objetos de auto tienen las mismas propiedades, pero los valores difieren de un auto a otro.

### Métodos de los Objetos

Un auto de la vida real tiene métodos como iniciar y detener:

- `car.start()`
- `car.drive()`
- `car.brake()`
- `car.stop()`

Los objetos de auto tienen los mismos métodos, pero se ejecutan en diferentes momentos.

## Variables en JavaScript

Las variables en JavaScript son contenedores para valores de datos.

Este código asigna un valor simple (Fiat) a una variable llamada `car`:

```javascript
let car = "Fiat";
```

## Objetos en JavaScript

Los objetos también son variables, pero pueden contener muchos valores.

Este código asigna muchos valores (Fiat, 500, blanco) a un objeto llamado `car`:

```javascript
const car = { type: "Fiat", model: "500", color: "blanco" };
```

**Nota:** Es una práctica común declarar objetos con la palabra clave `const`.

Aprende más sobre el uso de `const` con objetos en el capítulo: JS Const.

## Definición de Objetos en JavaScript

### Cómo Definir un Objeto en JavaScript

Existen diferentes maneras de definir un objeto en JavaScript:

1. **Usando una Notación de Objeto Literal**
2. **Usando la palabra clave new**
3. **Usando un Constructor de Objeto**

### Notación de Objeto Literal

Una notación de objeto literal es una lista de pares nombre: valor dentro de llaves `{}`.

```javascript
{ firstName: "John", lastName: "Doe", age: 50, eyeColor: "blue" }
```

**Nota:** Los pares nombre: valor también se llaman pares clave: valor. Los literales de objeto también se conocen como inicializadores de objeto.

### Creando un Objeto en JavaScript

Estos ejemplos crean un objeto en JavaScript con 4 propiedades:

#### Ejemplos

```javascript
// Crear un Objeto
const person = { firstName: "John", lastName: "Doe", age: 50, eyeColor: "blue" };
```

Los espacios y saltos de línea no son importantes. Un inicializador de objeto puede abarcar múltiples líneas:

```javascript
// Crear un Objeto
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};
```

Este ejemplo crea un objeto vacío y luego agrega 4 propiedades:

```javascript
// Crear un Objeto
const person = {};

// Agregar Propiedades
person.firstName = "John";
person.lastName = "Doe";
person.age = 50;
person.eyeColor = "blue";
```

### Usando la palabra clave new

Este ejemplo crea un nuevo objeto JavaScript usando `new Object()`, y luego agrega 4 propiedades:

```javascript
// Crear un Objeto
const person = new Object();

// Agregar Propiedades
person.firstName = "John";
person.lastName = "Doe";
person.age = 50;
person.eyeColor = "blue";
```

**Nota:** Los ejemplos anteriores hacen exactamente lo mismo, pero no es necesario usar `new Object()`. Por razones de legibilidad, simplicidad y velocidad de ejecución, usa el método de notación de objeto literal.

## Propiedades de los Objetos

Los valores nombrados, en los objetos JavaScript, se llaman propiedades.

| Propiedad     | Valor     |
|---------------|-----------|
| firstName     | John      |
| lastName      | Doe       |
| age           | 50        |
| eyeColor      | azul      |

Los objetos escritos como pares nombre-valor son similares a:

- Arreglos asociativos en PHP
- Diccionarios en Python
- Tablas hash en C
- Mapas hash en Java
- Hashes en Ruby y Perl

### Accediendo a las Propiedades de un Objeto

Puedes acceder a las propiedades del objeto de dos maneras:

- `objectName.propertyName`
- `objectName["propertyName"]`

#### Ejemplos

```javascript
person.lastName;
person["lastName"];
```

## Métodos de los Objetos en JavaScript

Los métodos son acciones que se pueden realizar sobre los objetos.

Los métodos son definiciones de función almacenadas como valores de propiedades.

| Propiedad      | Valor                           |
|----------------|---------------------------------|
| firstName      | John                            |
| lastName       | Doe                             |
| age            | 50                              |
| eyeColor       | azul                            |
| fullName       | function() { return this.firstName + " " + this.lastName; } |

### Ejemplo

```javascript
const person = {
  firstName: "John",
  lastName: "Doe",
  id: 5566,
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
};
```

En el ejemplo anterior, `this` se refiere al objeto `person`:

- `this.firstName` significa la propiedad `firstName` de `person`.
- `this.lastName` significa la propiedad `lastName` de `person`.

## En JavaScript, los Objetos son Rey

Si entiendes los objetos, entiendes JavaScript. Los objetos son contenedores para propiedades y métodos.

- **Propiedades** son valores nombrados.
- **Métodos** son funciones almacenadas como propiedades.

Las propiedades pueden ser valores primitivos, funciones o incluso otros objetos.

En JavaScript, casi "todo" es un objeto:

- Los objetos son objetos
- Las matemáticas son objetos
- Las funciones son objetos
- Las fechas son objetos
- Los arreglos son objetos
- Los mapas son objetos
- Los conjuntos son objetos

Todos los valores de JavaScript, excepto los primitivos, son objetos.

## Primitivos de JavaScript

Un valor primitivo es un valor que no tiene propiedades ni métodos.

Por ejemplo, `3.14` es un valor primitivo.

### Tipos de Datos Primitivos en JavaScript

JavaScript define 7 tipos de datos primitivos:

- string
- number
- boolean
- null
- undefined
- symbol
- bigint

### Inmutabilidad

Los valores primitivos son inmutables (están codificados y no pueden ser cambiados).

Si `x = 3.14`, puedes cambiar el valor de `x`, pero no puedes cambiar el valor de `3.14`.

| Valor       | Tipo     | Comentario                         |
|-------------|----------|-------------------------------------|
| "Hello"     | string   | "Hello" siempre es "Hello"         |
| 3.14        | number   | 3.14 siempre es 3.14               |
| true        | boolean  | true siempre es true                |
| false       | boolean  | false siempre es false              |
| null        | null     | null siempre es null                |
| undefined   | undefined| undefined siempre es undefined       |

## Los Objetos de JavaScript son Mutables

Los objetos son mutables: se dirigen por referencia, no por valor.

Si `person` es un objeto, la siguiente declaración no creará una copia de `person`:

```javascript
const x = person;
```

El objeto `x` no es una copia de `person`. El objeto `x` es `person`. Ambos comparten la misma dirección de memoria.

Cualquier cambio en `x` también cambiará a `person`:

### Ejemplo

```javascript
// Crear un Objeto
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "azul"
};

// Crear una copia
const x = person;

// Cambiar Edad en ambos
x.age = 10;
```

---

# Propiedades de los Objetos en JavaScript

## Un Objeto es una Colección Desordenada de Propiedades

Imagina que un objeto en JavaScript es como una caja de herramientas. Dentro de esta caja, tienes diferentes herramientas (propiedades) que puedes usar. Cada herramienta tiene un nombre (clave) y un propósito específico (valor). Las propiedades son la parte más importante de los objetos en JavaScript.

- **Propiedades:** Son como herramientas en la caja. Pueden cambiarse, añadirse, eliminarse, y algunas son de solo lectura.

## Accediendo a las Propiedades de JavaScript

La sintaxis para acceder a la propiedad de un objeto es la siguiente:

1. **Usando Notación de Punto:**

   ```javascript
   // objectName.property
   let age = person.age;
   ```

   Imagina que estás usando una herramienta de tu caja. Al mencionar el nombre de la caja (objeto) y luego el nombre de la herramienta (propiedad), obtienes la herramienta que necesitas.

2. **Usando Notación de Corchetes:**

   ```javascript
   // objectName["property"]
   let age = person["age"];
   ```

   Aquí, estás usando una etiqueta (nombre de la propiedad) para acceder a la herramienta dentro de la caja. Esto es útil si el nombre de la herramienta tiene espacios o caracteres especiales.

3. **Usando Expresiones:**

   ```javascript
   // objectName[expression]
   let age = person[x];
   ```

   En este caso, `x` es una variable que almacena el nombre de la herramienta, permitiéndote acceder a ella dinámicamente.

### Ejemplos

```javascript
person.firstname + " is " + person.age + " years old."; // Notación de punto
person["firstname"] + " is " + person["age"] + " years old."; // Notación de corchetes
let x = "firstname";
let y = "age";
person[x] + " is " + person[y] + " years old."; // Usando variables
```

## Añadiendo Nuevas Propiedades

Puedes agregar nuevas propiedades a un objeto existente simplemente dándole un valor:

### Ejemplo

```javascript
person.nationality = "English"; // Añadiendo una nueva propiedad
```

Piensa en esto como agregar una nueva herramienta a tu caja. Ahora tienes más opciones para trabajar.

## Eliminando Propiedades

La palabra clave `delete` se utiliza para eliminar una propiedad de un objeto:

### Ejemplo

```javascript
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};

delete person.age; // Eliminando una propiedad
```

También puedes usar la notación de corchetes:

```javascript
delete person["age"];
```

### Nota:

La palabra clave `delete` elimina tanto el valor de la propiedad como la propiedad en sí. Después de la eliminación, no puedes usar la propiedad hasta que la agregues de nuevo.

## Objetos Anidados

Los valores de las propiedades en un objeto pueden ser otros objetos. Esto es como tener herramientas dentro de herramientas en tu caja.

### Ejemplo

```javascript
myObj = {
  name: "John",
  age: 30,
  myCars: {
    car1: "Ford",
    car2: "BMW",
    car3: "Fiat"
  }
};
```

Puedes acceder a los objetos anidados utilizando notación de punto o notación de corchetes:

### Ejemplos

```javascript
myObj.myCars.car2;           // Notación de punto
myObj.myCars["car2"];       // Notación de corchetes
myObj["myCars"]["car2"];    // Acceso anidado
let p1 = "myCars";
let p2 = "car2";
myObj[p1][p2];              // Usando variables para acceder
```

## Referencia Completa de Objetos

Para una referencia completa, puedes consultar nuestra:

### [Referencia Completa de Objetos de JavaScript](#)

La referencia contiene descripciones y ejemplos de todas las propiedades y métodos de objetos.

## Conclusión

Comprender cómo funcionan las propiedades de los objetos en JavaScript es esencial para manejar datos y crear aplicaciones dinámicas. A medida que avances en tu aprendizaje, recuerda que los objetos son herramientas poderosas en tu caja de JavaScript, listas para ayudarte a construir lo que desees.

---

# Métodos de Objetos en JavaScript

## ¿Qué son los Métodos de Objetos?

Los métodos de objetos son como acciones que puedes realizar sobre objetos. Imagina un objeto como un teléfono inteligente, y los métodos son las aplicaciones (apps) que realizan tareas específicas en ese teléfono. Por ejemplo, puedes usar una app de mensajería para enviar mensajes o una app de fotos para tomar imágenes.

Un método es esencialmente una definición de función almacenada como un valor de propiedad dentro del objeto.

### Ejemplo de un Objeto con Métodos

```javascript
const persona = {
  nombre: "Juan",
  apellido: "Doe",
  id: 5566,
  nombreCompleto: function() {
    return this.nombre + " " + this.apellido; // Combina nombre y apellido
  }
};
```

En este ejemplo:
- `nombre`, `apellido` y `id` son propiedades del objeto `persona`.
- `nombreCompleto` es un método que combina las propiedades `nombre` y `apellido`.

### Entendiendo `this`

En el contexto de los métodos, `this` se refiere al objeto sobre el cual se está llamando al método. 

- `this.nombre` significa la propiedad `nombre` del objeto `persona`.
- `this.apellido` significa la propiedad `apellido` del objeto `persona`.

## Accediendo a los Métodos de Objetos

Puedes acceder a un método de objeto utilizando la siguiente sintaxis:

```javascript
nombreObjeto.nombreMetodo();
```

### Ejemplo

Cuando invocas la propiedad `nombreCompleto` con paréntesis, se ejecuta como una función:

```javascript
let nombre = persona.nombreCompleto(); // Ejecuta el método y retorna "Juan Doe"
```

Si accedes a la propiedad `nombreCompleto` sin paréntesis, devuelve la definición de la función:

```javascript
let nombre = persona.nombreCompleto; // Devuelve la definición de la función
```

## Agregando un Método a un Objeto

Puedes agregar fácilmente un nuevo método a un objeto existente:

### Ejemplo

```javascript
persona.nombreCompleto = function () {
  return this.nombre + " " + this.apellido; // Otra forma de obtener el nombre completo
};
```

Ahora, el objeto `persona` tiene un método adicional `nombreCompleto` que hace lo mismo que el método anterior.

## Usando Métodos de JavaScript

También puedes utilizar métodos incorporados de JavaScript dentro de tus métodos de objeto. Por ejemplo, puedes usar el método `toUpperCase()` para convertir texto a mayúsculas:

### Ejemplo

```javascript
persona.nombreCompleto = function () {
  return (this.nombre + " " + this.apellido).toUpperCase(); // Retorna "JUAN DOE"
};
```

En este caso, el método `nombreCompleto` ahora retorna el nombre completo en letras mayúsculas.

## Conclusión

Entender los métodos de objetos en JavaScript es esencial para construir aplicaciones interactivas y dinámicas. Los métodos te permiten realizar acciones sobre tus objetos, de manera similar a cómo funcionan las aplicaciones en un teléfono inteligente. A medida que continúas tu camino en JavaScript, recuerda que dominar los métodos es crucial para una codificación eficiente y para resolver problemas.

---

# Visualización de Objetos en JavaScript

## ¿Cómo Mostrar Objetos en JavaScript?

Cuando intentas mostrar un objeto de JavaScript directamente, el resultado será `[object Object]`, lo cual no es muy informativo. Es como intentar describir una caja sin abrirla: solo puedes ver su exterior.

### Ejemplo de Creación de un Objeto

```javascript
// Crear un Objeto
const persona = {
  nombre: "Juan",
  edad: 30,
  ciudad: "Nueva York"
};

// Intentar mostrar el objeto directamente
document.getElementById("demo").innerHTML = persona; // Resultado: [object Object]
```

Para mostrar un objeto de manera más informativa, existen varias soluciones:

1. **Mostrar las Propiedades del Objeto por Nombre**
2. **Mostrar las Propiedades del Objeto en un Bucle**
3. **Mostrar el Objeto usando `Object.values()`**
4. **Mostrar el Objeto usando `JSON.stringify()`**

## Mostrar Propiedades del Objeto

Puedes mostrar las propiedades de un objeto como una cadena de texto:

### Ejemplo

```javascript
// Crear un Objeto
const persona = {
  nombre: "Juan",
  edad: 30,
  ciudad: "Nueva York"
};

// Mostrar Propiedades
document.getElementById("demo").innerHTML =
  persona.nombre + ", " + persona.edad + ", " + persona.ciudad;
```

### Mostrar Propiedades en un Bucle

Las propiedades de un objeto se pueden recopilar utilizando un bucle:

### Ejemplo

```javascript
// Crear un Objeto
const persona = {
  nombre: "Juan",
  edad: 30,
  ciudad: "Nueva York"
};

// Construir un Texto
let texto = "";
for (let x in persona) {
  texto += persona[x] + " "; // Concatenar los valores
}

// Mostrar el Texto
document.getElementById("demo").innerHTML = texto;
```

**Nota:** Debes usar `persona[x]` dentro del bucle. Usar `persona.x` no funcionará porque `x` es la variable del bucle.

## Usando `Object.values()`

`Object.values()` crea un array a partir de los valores de las propiedades del objeto:

### Ejemplo

```javascript
// Crear un Objeto
const persona = {
  nombre: "Juan",
  edad: 30,
  ciudad: "Nueva York"
};

// Crear un Array
const miArray = Object.values(persona);

// Mostrar el Array
document.getElementById("demo").innerHTML = miArray; // Muestra: Juan, 30, Nueva York
```

## Usando `Object.entries()`

`Object.entries()` facilita el uso de objetos en bucles:

### Ejemplo

```javascript
const frutas = { Bananas: 300, Naranjas: 200, Manzanas: 500 };

let texto = "";
for (let [fruta, valor] of Object.entries(frutas)) {
  texto += fruta + ": " + valor + "<br>"; // Concatenar nombre y cantidad de frutas
}
```

## Usando `JSON.stringify()`

Los objetos de JavaScript se pueden convertir a una cadena utilizando el método JSON `JSON.stringify()`. Este método está incluido en JavaScript y es compatible con todos los navegadores principales.

### Ejemplo

```javascript
// Crear un Objeto
const persona = {
  nombre: "Juan",
  edad: 30,
  ciudad: "Nueva York"
};

// Convertir a Cadena
let miCadena = JSON.stringify(persona); // {"nombre":"Juan","edad":30,"ciudad":"Nueva York"}

// Mostrar la Cadena
document.getElementById("demo").innerHTML = miCadena;
```

**Nota:** El resultado será una cadena escrita en notación JSON.

## Conclusión

Entender cómo mostrar objetos en JavaScript es esencial para la depuración y para brindar información clara al usuario. Ya sea mediante propiedades específicas, bucles o métodos como `Object.values()` y `JSON.stringify()`, hay múltiples maneras de presentar los datos de manera efectiva.

---

# Constructores de Objetos en JavaScript

## Funciones Constructoras de Objetos

A veces necesitamos crear muchos objetos del mismo tipo. Para lograr esto, usamos una **función constructora de objetos**.

Se considera una buena práctica nombrar las funciones constructoras con una letra mayúscula al inicio, lo que ayuda a distinguirlas de las funciones regulares.

### Tipo de Objeto: Persona

```javascript
function Persona(primerNombre, apellido, edad, colorOjos) {
  this.primerNombre = primerNombre;
  this.apellido = apellido;
  this.edad = edad;
  this.colorOjos = colorOjos;
}
```

**Nota:** En la función constructora, `this` no tiene valor hasta que se crea un nuevo objeto. El valor de `this` se convertirá en el nuevo objeto.

### Creando Nuevos Objetos

Ahora podemos usar `new Persona()` para crear muchos nuevos objetos `Persona`:

```javascript
const miPadre = new Persona("Juan", "Pérez", 50, "azul");
const miMadre = new Persona("Sofía", "Rally", 48, "verde");
const miHermana = new Persona("Ana", "Rally", 18, "verde");
const yoMismo = new Persona("Juanito", "Rally", 22, "verde");
```

## Valores Predeterminados de Propiedad

Un valor asignado a una propiedad será un valor predeterminado para todos los objetos creados por el constructor:

### Ejemplo

```javascript
function Persona(primerNombre, apellido, edad, colorOjos) {
  this.primerNombre = primerNombre;
  this.apellido = apellido;
  this.edad = edad;
  this.colorOjos = colorOjos;
  this.nacionalidad = "Argentina"; // Valor predeterminado
}
```

### Agregando una Propiedad a un Objeto

Agregar una propiedad a un objeto creado por el constructor es sencillo:

```javascript
miPadre.nacionalidad = "Argentina"; // Asignar nacionalidad a miPadre
```

**Nota:** La nueva propiedad se agregará a `miPadre`, no a ningún otro objeto `Persona`.

## Agregando una Propiedad a un Constructor

No puedes agregar una nueva propiedad directamente a un constructor de objetos.

### Ejemplo

```javascript
Persona.nacionalidad = "Argentina"; // Esto no funcionará
```

Para agregar una nueva propiedad, debes agregarla al prototipo de la función constructora:

### Ejemplo

```javascript
Persona.prototype.nacionalidad = "Argentina"; // Agregar nacionalidad al prototipo
```

## Métodos de Función Constructora

Una función constructora también puede tener métodos definidos dentro de ella:

### Ejemplo

```javascript
function Persona(primerNombre, apellido, edad, colorOjos) {
  this.primerNombre = primerNombre;
  this.apellido = apellido;
  this.edad = edad;
  this.colorOjos = colorOjos;
  this.nombreCompleto = function() {
    return this.primerNombre + " " + this.apellido;
  };
}
```

### Agregando un Método a un Objeto

Puedes agregar fácilmente un método a un objeto creado:

```javascript
miMadre.cambiarNombre = function(nombre) {
  this.apellido = nombre; // Cambiar apellido
}
```

**Nota:** El nuevo método se agregará a `miMadre`, no a ningún otro objeto `Persona`.

## Agregando un Método a un Constructor

No puedes agregar un nuevo método a una función constructora de objetos directamente. El siguiente código producirá un `TypeError`:

### Ejemplo

```javascript
Persona.cambiarNombre = function(nombre) {
  this.apellido = nombre; // Esto no funcionará
}

// Intentar usar el método causará un error
miMadre.cambiarNombre("Pérez"); // TypeError: miMadre.cambiarNombre no es una función
```

Para agregar un nuevo método, debe hacerse en el prototipo de la función constructora:

### Ejemplo

```javascript
Persona.prototype.cambiarNombre = function(nombre) {
  this.apellido = nombre; // Cambiar apellido
}

miMadre.cambiarNombre("Pérez"); // Ahora funciona correctamente
```

**Nota:** La función `cambiarNombre()` asigna el valor de `nombre` a la propiedad `apellido` de la persona, con `this` refiriéndose a `miMadre`.

## Constructores de JavaScript Integrados

JavaScript tiene constructores integrados para todos los objetos nativos:

- `new Object()`   // Un nuevo objeto Object
- `new Array()`    // Un nuevo objeto Array
- `new Map()`      // Un nuevo objeto Map
- `new Set()`      // Un nuevo objeto Set
- `new Date()`     // Un nuevo objeto Date
- `new RegExp()`   // Un nuevo objeto RegExp
- `new Function()` // Un nuevo objeto Function

**Nota:** El objeto `Math` no está en la lista. `Math` es un objeto global y no se puede usar la palabra clave `new` con `Math`.

## ¿Sabías que?

- Usa literales de objeto `{}` en lugar de `new Object()`.
- Usa literales de arreglo `[]` en lugar de `new Array()`.
- Usa literales de expresión regular `/()/` en lugar de `new RegExp()`.
- Usa expresiones de función `() => {}` en lugar de `new Function()`.

### Ejemplo de Tipos Primitivos

```javascript
"";           // cadena primitiva
0;            // número primitivo
false;        // booleano primitivo

{};           // objeto
[];           // objeto array
/()/          // objeto regexp
function(){}; // función
```

---

