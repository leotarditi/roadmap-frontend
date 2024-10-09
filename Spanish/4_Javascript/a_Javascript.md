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

# Eventos en JavaScript

Los eventos HTML son "cosas" que suceden en los elementos HTML. Cuando JavaScript se utiliza en páginas HTML, puede "reaccionar" a estos eventos.

## Eventos HTML

Un evento HTML puede ser algo que el navegador hace o algo que un usuario realiza. Aquí hay algunos ejemplos de eventos HTML:

- Una página web HTML ha terminado de cargarse
- Un campo de entrada HTML ha sido modificado
- Un botón HTML ha sido presionado

A menudo, cuando ocurren eventos, es posible que desees hacer algo. JavaScript te permite ejecutar código cuando se detectan eventos. HTML permite agregar atributos de manejadores de eventos, con código JavaScript, a los elementos HTML.

### Analogía: El Timón de un Barco

Imagina que tu página web es un barco en el mar. Los eventos son como olas que afectan el movimiento del barco. Cuando el barco se enfrenta a una ola (un evento), puedes girar el timón (ejecutar código) para reaccionar a esa ola y mantener el barco en la dirección correcta.

### Ejemplo de Atributos de Eventos

Con comillas simples:
```html
<element event='algún código JavaScript'>
```

Con comillas dobles:
```html
<element event="algún código JavaScript">
```

En el siguiente ejemplo, se añade un atributo `onclick` (con código) a un elemento `<button>`:

#### Ejemplo 1

```html
<button onclick="document.getElementById('demo').innerHTML = Date()">¿Qué hora es?</button>
```

En el ejemplo anterior, el código JavaScript cambia el contenido del elemento con `id="demo"`.

#### Ejemplo 2

En el siguiente ejemplo, el código cambia el contenido de su propio elemento (usando `this.innerHTML`):

```html
<button onclick="this.innerHTML = Date()">¿Qué hora es?</button>
```

El código JavaScript a menudo es más extenso. Es más común ver los atributos de eventos llamando a funciones:

#### Ejemplo 3

```html
<button onclick="displayDate()">¿Qué hora es?</button>
```

## Eventos HTML Comunes

Aquí hay una lista de algunos eventos HTML comunes:

| Evento       | Descripción                                    |
|--------------|------------------------------------------------|
| `onchange`   | Un elemento HTML ha sido cambiado              |
| `onclick`    | El usuario hace clic en un elemento HTML       |
| `onmouseover`| El usuario mueve el mouse sobre un elemento    |
| `onmouseout` | El usuario mueve el mouse fuera de un elemento  |
| `onkeydown`  | El usuario presiona una tecla                  |
| `onload`     | El navegador ha terminado de cargar la página  |

La lista es mucho más extensa: [Referencia de Eventos DOM en JavaScript de W3Schools](https://www.w3schools.com/jsref/dom_obj_event.asp).

### Analogía: Los Controladores de un Automóvil

Imagina que los eventos HTML son como las acciones que realizas al conducir un automóvil. Cuando presionas el acelerador (evento), el auto reacciona (ejecuta una función) aumentando la velocidad. De igual manera, cuando se produce un evento en tu página web, puedes hacer que tu código reaccione para realizar una acción específica.

## Manejadores de Eventos en JavaScript

Los manejadores de eventos pueden utilizarse para gestionar y verificar la entrada del usuario, acciones del usuario y acciones del navegador. Algunas de las cosas que se pueden hacer son:

- Acciones que deben realizarse cada vez que se carga una página
- Acciones que deben realizarse cuando se cierra la página
- Acciones que se deben ejecutar cuando un usuario hace clic en un botón
- Contenido que debe verificarse cuando un usuario ingresa datos
- Y más...

### Métodos Comunes para Usar Eventos en JavaScript:

- Los atributos de eventos HTML pueden ejecutar código JavaScript directamente.
- Los atributos de eventos HTML pueden llamar a funciones JavaScript.
- Puedes asignar tus propias funciones manejadoras de eventos a los elementos HTML.
- Puedes prevenir que los eventos se envíen o sean manejados.
- Y más...

Aprenderás mucho más sobre eventos y manejadores de eventos en los capítulos sobre DOM en HTML.

---

### Conclusión

Los eventos son fundamentales para la interacción en páginas web. Comprender cómo funcionan y cómo reaccionar a ellos te permitirá crear aplicaciones web más dinámicas y atractivas.

---

# String en JavaScript

Las cadenas son para almacenar texto. Se escriben con comillas.

## Uso de Comillas

Una cadena de JavaScript es cero o más caracteres escritos dentro de comillas.

### Ejemplo

```javascript
let texto = "John Doe";
```

Puedes usar comillas simples o dobles:

### Ejemplo

```javascript
let nombreAuto1 = "Volvo XC60";  // Comillas dobles
let nombreAuto2 = 'Volvo XC60';  // Comillas simples
```

**Nota:** Las cadenas creadas con comillas simples o dobles funcionan igual. No hay diferencia entre las dos.

### Analogía: Una Cubierta de Libro

Piensa en las cadenas como las cubiertas de los libros. Así como un libro puede tener una cubierta hecha de diferentes materiales (papel o tela), una cadena puede estar encerrada en comillas simples o dobles. El contenido dentro de la cubierta (el texto) sigue siendo el mismo, sin importar el tipo de cubierta que se use.

## Comillas Dentro de Comillas

Puedes usar comillas dentro de una cadena, siempre y cuando no coincidan con las comillas que rodean la cadena:

### Ejemplo

```javascript
let respuesta1 = "Está bien";
let respuesta2 = "Lo llaman 'Johnny'";
let respuesta3 = 'Lo llaman "Johnny"';
```

### Analogía: Cajas Anidadas

Imagina que tienes una caja (las comillas externas) que contiene otra caja más pequeña (las comillas internas). Siempre que no uses el mismo tipo de caja para ambas, todo encajará perfectamente sin confusiones.

## Cadenas de Plantilla

Las plantillas se introdujeron con ES6 (JavaScript 2016). Las plantillas son cadenas encerradas en comillas invertidas (`` `Esta es una cadena de plantilla` ``).

Las plantillas permiten comillas simples y dobles dentro de una cadena:

### Ejemplo

```javascript
let texto = `A menudo lo llaman "Johnny"`;
```

**Nota:** Las plantillas no son compatibles con Internet Explorer.

### Analogía: Un Sobre Flexible

Las plantillas son como un sobre flexible que puede contener cartas de varias formas y tamaños (comillas). Pueden acomodar todo tipo de contenido sin preocuparse por qué tipo de sobre (comillas) estás usando.

## Longitud de la Cadena

Para encontrar la longitud de una cadena, usa la propiedad `length` incorporada:

### Ejemplo

```javascript
let texto = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
let longitud = texto.length;
```

### Analogía: Midiendo una Cuerda

Piensa en una cadena como una cuerda. Así como puedes medir la longitud de una cuerda, puedes medir cuántos caracteres hay en una cadena.

## Caracteres de Escape

Debido a que las cadenas deben escribirse dentro de comillas, JavaScript malinterpretará esta cadena:

```javascript
let texto = "Somos los llamados "Vikingos" del norte.";
```

La cadena se cortará a `"Somos los llamados "`.

Para resolver este problema, puedes usar un carácter de escape con barra invertida. El carácter de escape con barra invertida (`\`) convierte los caracteres especiales en caracteres de cadena:

### Secuencias de Escape

| Código | Resultado    | Descripción         |
|--------|--------------|---------------------|
| `\'`   | `'`          | Comilla simple       |
| `\"`   | `"`          | Comilla doble        |
| `\\`   | `\`          | Barra invertida      |
| `\b`   | (Retroceso)  | Retroceso            |
| `\f`   | (Avance de formulario) | Avance de formulario |
| `\n`   | (Nueva línea) | Nueva línea          |
| `\r`   | (Retorno de carro) | Retorno de carro  |
| `\t`   | (Tabulador horizontal) | Tabulador horizontal |
| `\v`   | (Tabulador vertical) | Tabulador vertical   |

### Analogía: Personajes Especiales en un Guion

Imagina que estás escribiendo un guion de cine. La barra invertida es como una señal del director que le dice a los actores cómo entregar líneas especiales (como las comillas) sin interrumpir el flujo del guion (la cadena).

### Ejemplos

```javascript
let texto = "Somos los llamados \"Vikingos\" del norte.";  // Inserta una comilla doble
let texto = 'Está bien.';                                    // Inserta una comilla simple
let texto = "El carácter \\ se llama barra invertida.";     // Inserta una barra invertida
```

## Dividir Líneas Largas

Para mejorar la legibilidad, los programadores suelen evitar líneas de código largas. Una forma segura de dividir una declaración es después de un operador:

### Ejemplo

```javascript
document.getElementById("demo").innerHTML =
"¡Hola Dolly!";
```

Una forma segura de dividir una cadena es utilizando la adición de cadenas:

### Ejemplo

```javascript
document.getElementById("demo").innerHTML = "Hola " +
"Dolly!";
```

## Cadenas de JavaScript como Objetos

Normalmente, las cadenas de JavaScript son valores primitivos, creados a partir de literales:

```javascript
let x = "John";
```

Pero las cadenas también pueden definirse como objetos con la palabra clave `new`:

```javascript
let y = new String("John");
```

### **Precaución:** Evita los Objetos de Cadenas

**No crees objetos de cadenas.** La palabra clave `new` complica el código y ralentiza la velocidad de ejecución. Los objetos de cadena pueden producir resultados inesperados:

### Ejemplo de Comparación

```javascript
let x = "John";
let y = new String("John");

console.log(x == y);  // true
console.log(x === y); // false
```

### Analogía: Dos Maneras de Presentarte

Presentarte puede hacerse de dos maneras: diciendo informalmente, "Hola, soy John" (cadena primitiva) o presentando una tarjeta de identificación formal que dice, "Yo soy John" (objeto de cadena). Aunque ambos se refieren a la misma persona, la tarjeta de identificación (objeto de cadena) agrega una complejidad innecesaria.

---

# Metodos de String en JavaScript

## Métodos Básicos de Cadenas

Las cadenas en JavaScript son primitivas e inmutables: todos los métodos de cadenas producen una nueva cadena sin alterar la cadena original.

### Longitud de la Cadena

La propiedad `length` devuelve la longitud de una cadena:

```javascript
let text = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
let length = text.length; // Devuelve 26
```

### Extracción de Caracteres de la Cadena

Hay 4 métodos para extraer caracteres de una cadena:

- **El Método `at(position)`**
- **El Método `charAt(position)`**
- **El Método `charCodeAt(position)`**
- **Acceso a Propiedades `[]` como en Arreglos**

### Método `charAt()`

El método `charAt()` devuelve el carácter en un índice (posición) especificado en una cadena:

```javascript
let text = "HELLO WORLD";
let char = text.charAt(0); // Devuelve 'H'
```

### Método `charCodeAt()`

El método `charCodeAt()` devuelve el código del carácter en un índice especificado en una cadena. Este método devuelve un código UTF-16 (un número entero entre 0 y 65535).

```javascript
let text = "HELLO WORLD";
let char = text.charCodeAt(0); // Devuelve 72
```

### Método `at()`

ES2022 introdujo el método `at()` para cadenas. Permite el uso de índices negativos.

```javascript
const name = "W3Schools";
let letter = name.at(2); // Devuelve '3'
let letterNeg = name.at(-1); // Devuelve 's'
```

### Acceso a Propiedades `[]`

```javascript
let text = "HELLO WORLD";
let char = text[0]; // Devuelve 'H'
```

**Nota:** El acceso a propiedades puede ser algo impredecible, ya que las cadenas no son arreglos. Si no se encuentra ningún carácter, `[]` devuelve `undefined`, mientras que `charAt()` devuelve una cadena vacía.

### Extracción de Partes de la Cadena

Hay 3 métodos para extraer una parte de una cadena:

- `slice(start, end)`
- `substring(start, end)`
- `substr(start, length)`

#### Método `slice()`

`slice()` extrae una parte de una cadena y devuelve la parte extraída en una nueva cadena.

```javascript
let text = "Apple, Banana, Kiwi";
let part = text.slice(7, 13); // Devuelve 'Banana'
```

**Ejemplo con Índices Negativos:**

```javascript
let partNeg = text.slice(-12, -6); // Devuelve 'Banana'
```

#### Método `substring()`

`substring()` es similar a `slice()`. La diferencia es que los valores de inicio y fin menores que 0 se tratan como 0 en `substring()`.

```javascript
let str = "Apple, Banana, Kiwi";
let part = str.substring(7, 13); // Devuelve 'Banana'
```

#### Método `substr()`

`substr()` es similar a `slice()`, pero el segundo parámetro especifica la longitud de la parte extraída.

```javascript
let str = "Apple, Banana, Kiwi";
let part = str.substr(7, 6); // Devuelve 'Banana'
```

### Convertir a Mayúsculas y Minúsculas

Para convertir una cadena a mayúsculas, se utiliza `toUpperCase()`, y para convertir a minúsculas, se utiliza `toLowerCase()`.

#### Ejemplo `toUpperCase()`

```javascript
let text1 = "Hello World!";
let text2 = text1.toUpperCase(); // Devuelve 'HELLO WORLD!'
```

#### Ejemplo `toLowerCase()`

```javascript
let text1 = "Hello World!";
let text2 = text1.toLowerCase(); // Devuelve 'hello world!'
```

### Método `concat()`

`concat()` une dos o más cadenas:

```javascript
let text1 = "Hello";
let text2 = "World";
let text3 = text1.concat(" ", text2); // Devuelve 'Hello World!'
```

### Método `trim()`

El método `trim()` elimina los espacios en blanco de ambos lados de una cadena:

```javascript
let text1 = "      Hello World!      ";
let text2 = text1.trim(); // Devuelve 'Hello World!'
```

### Método `trimStart()` y `trimEnd()`

ECMAScript 2019 añadió los métodos `trimStart()` y `trimEnd()`, que eliminan espacios solo del inicio o del final de una cadena, respectivamente.

#### Ejemplo `trimStart()`

```javascript
let text1 = "     Hello World!     ";
let text2 = text1.trimStart(); // Devuelve 'Hello World!     '
```

#### Ejemplo `trimEnd()`

```javascript
let text1 = "     Hello World!     ";
let text2 = text1.trimEnd(); // Devuelve '     Hello World!'
```

### Métodos de Relleno

ECMAScript 2017 añadió `padStart()` y `padEnd()` para soportar el relleno al inicio y al final de una cadena.

#### Método `padStart()`

`padStart()` rellena una cadena desde el inicio hasta alcanzar una longitud dada.

```javascript
let text = "5";
let padded = text.padStart(4, "0"); // Devuelve '0005'
```

#### Método `padEnd()`

`padEnd()` rellena una cadena desde el final hasta alcanzar una longitud dada.

```javascript
let text = "5";
let padded = text.padEnd(4, "0"); // Devuelve '5000'
```

### Método `repeat()`

El método `repeat()` devuelve una cadena con un número de copias de una cadena.

```javascript
let text = "Hello world!";
let result = text.repeat(2); // Devuelve 'Hello world!Hello world!'
```

### Reemplazo de Contenido de Cadena

El método `replace()` reemplaza un valor especificado por otro en una cadena. Solo reemplaza la primera coincidencia.

```javascript
let text = "Please visit Microsoft!";
let newText = text.replace("Microsoft", "W3Schools"); // Devuelve 'Please visit W3Schools!'
```

Para reemplazar todas las coincidencias, utiliza una expresión regular con el flag `/g`.

```javascript
let text = "Please visit Microsoft and Microsoft!";
let newText = text.replace(/Microsoft/g, "W3Schools"); // Devuelve 'Please visit W3Schools and W3Schools!'
```

### Método `replaceAll()`

En 2021, JavaScript introdujo el método `replaceAll()`, que permite reemplazar todas las coincidencias sin necesidad de usar expresiones regulares.

```javascript
text = text.replaceAll("Cats", "Dogs");
```

## Resumen

Este documento ha cubierto los métodos básicos para manipular cadenas en JavaScript. Utilizando analogías simples y conceptos técnicos, ahora puedes entender cómo trabajar con cadenas de manera efectiva. Recuerda que todos los métodos devuelven una nueva cadena y no modifican la cadena original.

---

# JavaScript String Search

## Introducción
Buscar en cadenas de texto en JavaScript es como buscar un libro en una biblioteca. Usamos diferentes herramientas y métodos para encontrar lo que necesitamos. A continuación, exploraremos varios métodos que nos permiten localizar texto dentro de cadenas.

## Métodos de Búsqueda de Cadenas
- `String indexOf()`
- `String lastIndexOf()`
- `String search()`
- `String match()`
- `String matchAll()`
- `String includes()`
- `String startsWith()`
- `String endsWith()`

## JavaScript String indexOf()
El método `indexOf()` es como un bibliotecario que te dice en qué estante se encuentra un libro por primera vez. Devuelve el índice (posición) de la primera ocurrencia de una cadena en otra cadena o -1 si no se encuentra.

### Ejemplo
```javascript
let text = "Please locate where 'locate' occurs!";
let index = text.indexOf("locate"); // index será 7
```

**Nota:** JavaScript cuenta las posiciones desde cero. Por lo tanto, 0 es la primera posición en una cadena, 1 es la segunda, etc.

## JavaScript String lastIndexOf()
El método `lastIndexOf()` es como un bibliotecario que te dice en qué estante se encuentra un libro, pero buscando desde el final hacia el principio. Devuelve el índice de la última ocurrencia de un texto específico.

### Ejemplo
```javascript
let text = "Please locate where 'locate' occurs!";
let index = text.lastIndexOf("locate"); // index será 7
```

Ambos métodos (`indexOf()` y `lastIndexOf()`) devuelven -1 si el texto no se encuentra.

### Búsqueda desde una posición específica
Ambos métodos aceptan un segundo parámetro que indica la posición desde la cual iniciar la búsqueda.

### Ejemplo
```javascript
let index = text.indexOf("locate", 15); // index será -1
```

## JavaScript String search()
El método `search()` es como un detective que busca una palabra clave en un libro. Devuelve la posición de la coincidencia de una cadena o una expresión regular.

### Ejemplo
```javascript
let text = "Please locate where 'locate' occurs!";
let index = text.search("locate"); // index será 7
```

### Comparación con `indexOf()`
Ambos métodos aceptan argumentos similares y devuelven valores similares, pero hay diferencias:
- `search()` no acepta un segundo argumento.
- `indexOf()` no acepta expresiones regulares.

## JavaScript String match()
El método `match()` es como un examen que evalúa si hay coincidencias de un patrón en un texto. Devuelve un array con los resultados.

### Ejemplo
```javascript
let text = "The rain in SPAIN stays mainly in the plain";
let matches = text.match("ain"); // ["ain"]
```

### Búsqueda global
```javascript
let matches = text.match(/ain/g); // ["ain", "ain", "ain"]
```

## JavaScript String matchAll()
El método `matchAll()` es como un grupo de detectives que buscan todas las coincidencias en un libro. Devuelve un iterador con todos los resultados.

### Ejemplo
```javascript
const iterator = text.matchAll(/ain/g);
```

**Nota:** `matchAll()` es una característica de ES2020 y no es compatible con Internet Explorer.

## JavaScript String includes()
El método `includes()` es como preguntar si una tienda tiene un producto específico. Devuelve `true` si la cadena contiene un valor específico y `false` en caso contrario.

### Ejemplo
```javascript
let text = "Hello world, welcome to the universe.";
let hasWorld = text.includes("world"); // true
```

## JavaScript String startsWith()
El método `startsWith()` es como verificar si un libro comienza con una determinada frase. Devuelve `true` si la cadena comienza con un valor específico.

### Ejemplo
```javascript
let text = "Hello world, welcome to the universe.";
let startsWithHello = text.startsWith("Hello"); // true
```

## JavaScript String endsWith()
El método `endsWith()` es como verificar si un libro termina con una determinada frase. Devuelve `true` si la cadena termina con un valor específico.

### Ejemplo
```javascript
let text = "John Doe";
let endsWithDoe = text.endsWith("Doe"); // true
```

## Conclusión
Entender cómo buscar y manipular cadenas de texto en JavaScript es fundamental para trabajar con datos. Estos métodos son herramientas poderosas que te permitirán acceder y modificar información de manera eficiente. A medida que avances en tu camino como desarrollador frontend, dominar estas técnicas será esencial.

---

# Numbers en JavaScript

JavaScript tiene un solo tipo de número. Los números pueden escribirse con o sin decimales.

## Ejemplo
```javascript
let x = 3.14;    // Un número con decimales
let y = 3;       // Un número sin decimales
```

Los números extremadamente grandes o pequeños pueden escribirse en notación científica (exponencial):

## Ejemplo
```javascript
let x = 123e5;    // 12300000
let y = 123e-5;   // 0.00123
```

## Los Números en JavaScript Son Siempre de Punto Flotante de 64 bits
A diferencia de muchos otros lenguajes de programación, JavaScript no define diferentes tipos de números, como enteros, cortos, largos o de punto flotante.

Los números en JavaScript siempre se almacenan como números de punto flotante de doble precisión, siguiendo el estándar internacional IEEE 754.

Este formato almacena números en 64 bits, donde el número (la fracción) se almacena en los bits del 0 al 51, el exponente en los bits del 52 al 62, y el signo en el bit 63:

| Valor (también conocido como Fracción/Mantisa) | Exponente | Signo |
|------------------------------------------------|-----------|-------|
| 52 bits (0 - 51)                               | 11 bits (52 - 62) | 1 bit (63) |

### Precisión de Enteros
Los enteros (números sin un punto o notación de exponente) son precisos hasta 15 dígitos.

## Ejemplo
```javascript
let x = 999999999999999;   // x será 999999999999999
let y = 9999999999999999;  // y será 10000000000000000
```
El número máximo de decimales es 17.

### Precisión de Punto Flotante
Las operaciones de punto flotante no siempre son 100% precisas:

```javascript
let x = 0.2 + 0.1;
```

Para resolver el problema anterior, ayuda multiplicar y dividir:

```javascript
let x = (0.2 * 10 + 0.1 * 10) / 10;
```

### Sumar Números y Cadenas
**¡ADVERTENCIA!**

JavaScript utiliza el operador + tanto para la suma como para la concatenación.

- Los números se suman.
- Las cadenas se concatenan.

Si sumas dos números, el resultado será un número:

## Ejemplo
```javascript
let x = 10;
let y = 20;
let z = x + y; // z será 30
```

Si sumas dos cadenas, el resultado será una concatenación de cadenas:

## Ejemplo
```javascript
let x = "10";
let y = "20";
let z = x + y; // z será "1020"
```

Si sumas un número y una cadena, el resultado será una concatenación de cadenas:

## Ejemplo
```javascript
let x = 10;
let y = "20";
let z = x + y; // z será "1020"
```

Si sumas una cadena y un número, el resultado también será una concatenación de cadenas:

## Ejemplo
```javascript
let x = "10";
let y = 20;
let z = x + y; // z será "1020"
```

Un error común es esperar este resultado para la siguiente operación:

## Ejemplo
```javascript
let x = 10;
let y = 20;
let z = "The result is: " + x + y; // z será "The result is: 1020"
```

Otro error común es esperar que el siguiente resultado sea 102030:

## Ejemplo
```javascript
let x = 10;
let y = 20;
let z = "30";
let result = x + y + z; // result será "3030"
```

El intérprete de JavaScript trabaja de izquierda a derecha.

Primero, se suma 10 + 20 porque x e y son ambos números.

Luego, se concatena 30 + "30" porque z es una cadena.

### Cadenas Numéricas
Las cadenas en JavaScript pueden tener contenido numérico:

```javascript
let x = 100;         // x es un número
let y = "100";       // y es una cadena
```

JavaScript intentará convertir cadenas en números en todas las operaciones numéricas:

Esto funcionará:

```javascript
let x = "100";
let y = "10";
let z = x / y; // z será 10
```

Esto también funcionará:

```javascript
let x = "100";
let y = "10";
let z = x * y; // z será 1000
```

Y esto funcionará:

```javascript
let x = "100";
let y = "10";
let z = x - y; // z será 90
```

Pero esto no funcionará:

```javascript
let x = "100";
let y = "10";
let z = x + y; // z será "10010"
```

En el último ejemplo, JavaScript usa el operador + para concatenar las cadenas.

### NaN - No es un Número
NaN es una palabra reservada de JavaScript que indica que un número no es un número legal.

Intentar realizar una operación aritmética con una cadena no numérica resultará en NaN (Not a Number):

## Ejemplo
```javascript
let x = 100 / "Apple"; // x será NaN
```

Sin embargo, si la cadena es numérica, el resultado será un número:

## Ejemplo
```javascript
let x = 100 / "10"; // x será 10
```

Puedes usar la función global de JavaScript isNaN() para averiguar si un valor no es un número:

## Ejemplo
```javascript
let x = 100 / "Apple";
isNaN(x); // true
```

Ten cuidado con NaN. Si usas NaN en una operación matemática, el resultado también será NaN:

## Ejemplo
```javascript
let x = NaN;
let y = 5;
let z = x + y; // z será NaN
```

O el resultado podría ser una concatenación como NaN5:

## Ejemplo
```javascript
let x = NaN;
let y = "5";
let z = x + y; // z será "NaN5"
```

NaN es un número: typeof NaN devuelve number:

## Ejemplo
```javascript
typeof NaN; // "number"
```

### Infinito
Infinity (o -Infinity) es el valor que JavaScript devolverá si calculas un número fuera del mayor número posible.

## Ejemplo
```javascript
let myNumber = 2;
// Ejecuta hasta Infinity
while (myNumber != Infinity) {
  myNumber = myNumber * myNumber;
}
```

La división por 0 (cero) también genera Infinity:

## Ejemplo
```javascript
let x =  2 / 0; // x será Infinity
let y = -2 / 0; // y será -Infinity
```

Infinity es un número: typeof Infinity devuelve number.

## Ejemplo
```javascript
typeof Infinity; // "number"
```

### Hexadecimal
JavaScript interpreta constantes numéricas como hexadecimales si están precedidas por 0x.

## Ejemplo
```javascript
let x = 0xFF; // x será 255
```

Nunca escribas un número con un cero inicial (como 07). Algunas versiones de JavaScript interpretan números como octales si se escriben con un cero inicial.

Por defecto, JavaScript muestra números en base 10 decimal.

Pero puedes usar el método toString() para mostrar números desde la base 2 hasta la base 36.

- Hexadecimal es base 16.
- Decimal es base 10.
- Octal es base 8.
- Binario es base 2.

## Ejemplo
```javascript
let myNumber = 32;
myNumber.toString(32); // "10"
myNumber.toString(16); // "20"
myNumber.toString(12); // "28"
myNumber.toString(10); // "32"
myNumber.toString(8);  // "40"
myNumber.toString(2);  // "100000"
```

### Números en JavaScript como Objetos
Normalmente, los números en JavaScript son valores primitivos creados a partir de literales:

```javascript
let x = 123;
```

Pero los números también se pueden definir como objetos con la palabra clave new:

```javascript
let y = new Number(123);
```

## Ejemplo
```javascript
let x = 123;
let y = new Number(123);
```

No crees objetos Number.

La palabra clave new complica el código y ralentiza la velocidad de ejecución.

Los objetos Number pueden producir resultados inesperados:

Al usar el operador ==, x e y son iguales:

## Ejemplo
```javascript
let x = 500;
let y = new Number(500); // true
```

Al usar el operador ===, x e y no son iguales.

## Ejemplo
```javascript
let x = 500;
let y = new Number(500); // false
```

---

# JavaScript BigInt: Un Viajero en el Mundo de los Números Gigantes

## Introducción a BigInt
JavaScript BigInt es un tipo de dato especial que se utiliza para almacenar valores enteros muy grandes que no pueden ser representados por un número normal en JavaScript.

### Analogía
Imagina que tienes una caja de herramientas. Los números normales son como un destornillador común: sirven para la mayoría de las tareas, pero si necesitas un destornillador de gran tamaño (un número realmente grande), necesitas una herramienta especial, que es BigInt.

## Precisión de los Enteros en JavaScript
Los enteros en JavaScript solo son precisos hasta 15 dígitos:

```javascript
let x = 999999999999999; // Preciso
let y = 9999999999999999; // No preciso
```

En JavaScript, todos los números se almacenan en un formato de punto flotante de 64 bits (estándar IEEE 754). Esto significa que los números grandes no pueden ser representados con exactitud y se redondean.

### Analogía
Es como un reloj que solo puede mostrar hasta las 12 horas. Si intentas poner 15 horas, el reloj volverá a empezar desde 3. Así, los números grandes son "redondeados" para ajustarse a este formato.

### Rango de Enteros Seguros
JavaScript puede representar de manera segura enteros:

- Hasta **9007199254740991** ( \(2^{53} - 1\) )
- Y hasta **-9007199254740991** ( \(-2^{53} + 1\) )

Los valores fuera de este rango pierden precisión.

## Cómo Crear un BigInt
Para crear un BigInt, puedes añadir `n` al final de un número entero o llamar a `BigInt()`:

### Ejemplos
```javascript
let x = 9999999999999999; // Normal
let y = 9999999999999999n; // BigInt
let z = BigInt(1234567890123456789012345); // BigInt
```

## BigInt: Un Nuevo Tipo de Dato en JavaScript
El tipo de dato de un BigInt es `"bigint"`:

### Ejemplo
```javascript
let x = BigInt(999999999999999);
let type = typeof x; // "bigint"
```

BigInt es el segundo tipo de dato numérico en JavaScript (después de Number). Con BigInt, el total de tipos de datos soportados en JavaScript es **8**:

1. String
2. Number
3. Bigint
4. Boolean
5. Undefined
6. Null
7. Symbol
8. Object

### Analogía
Imagina que tienes una tienda que vende diferentes tipos de frutas. Cada tipo de fruta representa un tipo de dato en JavaScript. BigInt es una nueva fruta que han añadido a la tienda.

## Operadores de BigInt
Los operadores que se pueden usar en un número normal también se pueden usar en un BigInt.

### Ejemplo de Multiplicación de BigInt
```javascript
let x = 9007199254740995n;
let y = 9007199254740995n;
let z = x * y; // Multiplicación
```

### Notas
- No se permite realizar aritmética entre un BigInt y un número normal (la conversión de tipo puede perder información).
- El desplazamiento a la derecha sin signo (`>>>`) no se puede hacer en un BigInt (no tiene un ancho fijo).

## BigInt y Decimales
Un BigInt no puede tener decimales.

### Ejemplo de División de BigInt
```javascript
let x = 5n;
let y = x / 2; // Error: No se pueden mezclar BigInt y otros tipos
let z = Number(x) / 2; // Conversión explícita
```

## Notación Hexadecimal, Octal y Binaria para BigInt
Un BigInt también puede escribirse en notación hexadecimal, octal o binaria:

### Ejemplo en Hexadecimal
```javascript
let hex = 0x20000000000003n; // Hexadecimal
let oct = 0o400000000000000003n; // Octal
let bin = 0b100000000000000000000000000000000000000000000000000011n; // Binario
```

## Curiosidad sobre la Precisión
El redondeo puede comprometer la seguridad del programa.

### Ejemplo de MAX_SAFE_INTEGER
```javascript
9007199254740992 === 9007199254740993; // es verdadero !!!
```

## Soporte en Navegadores
BigInt es compatible en todos los navegadores desde septiembre de 2020:

- Chrome 67
- Edge 79
- Firefox 68
- Safari 14
- Opera 54

## Mínimos y Máximos Enteros Seguros
ES6 agregó propiedades máximas y mínimas al objeto Number:

- **MAX_SAFE_INTEGER**
- **MIN_SAFE_INTEGER**

### Ejemplo de MAX_SAFE_INTEGER
```javascript
let x = Number.MAX_SAFE_INTEGER; // 9007199254740991
```

### Ejemplo de MIN_SAFE_INTEGER
```javascript
let x = Number.MIN_SAFE_INTEGER; // -9007199254740991
```

## Nuevos Métodos para el Objeto Number
ES6 también agregó 2 nuevos métodos al objeto Number:

- **Number.isInteger()**
- **Number.isSafeInteger()**

### Método Number.isInteger()
El método `Number.isInteger()` devuelve `true` si el argumento es un entero.

#### Ejemplo de isInteger()
```javascript
Number.isInteger(10); // true
Number.isInteger(10.5); // false
```

### Método Number.isSafeInteger()
Un entero seguro es un entero que puede ser representado exactamente como un número de doble precisión.

El método `Number.isSafeInteger()` devuelve `true` si el argumento es un entero seguro.

#### Ejemplo de isSafeInteger()
```javascript
Number.isSafeInteger(10); // true
Number.isSafeInteger(12345678901234567890); // false
```

Los enteros seguros son todos los enteros desde \(-(2^{53} - 1)\) hasta \((2^{53} - 1)\). Este es seguro: **9007199254740991**. Este no es seguro: **9007199254740992**.

---

# Métodos Numéricos de JavaScript

Los métodos numéricos de JavaScript pueden ser utilizados en todos los números de JavaScript:

| Método           | Descripción                                           |
|------------------|------------------------------------------------------|
| `toString()`     | Devuelve un número como una cadena.                  |
| `toExponential()`| Devuelve un número escrito en notación exponencial.  |
| `toFixed()`      | Devuelve un número escrito con un número de decimales. |
| `toPrecision()`  | Devuelve un número escrito con una longitud especificada. |
| `valueOf()`      | Devuelve un número como un número.                   |

## El Método `toString()`

El método `toString()` devuelve un número como una cadena.

Puedes usarlo con cualquier tipo de número (literals, variables o expresiones):

**Ejemplo**
```javascript
let x = 123;
x.toString(); // "123"
(123).toString(); // "123"
(100 + 23).toString(); // "123"
```

**Analogía**: Imagina que `toString()` es como poner una etiqueta en un frasco de mermelada. El frasco sigue siendo el mismo, pero ahora tiene un nombre que lo identifica.

## El Método `toExponential()`

El método `toExponential()` devuelve una cadena, con un número redondeado y escrito usando notación exponencial.

Un parámetro define el número de caracteres detrás del punto decimal:

**Ejemplo**
```javascript
let x = 9.656;
x.toExponential(2); // "9.66e+0"
x.toExponential(4); // "9.6560e+0"
x.toExponential(6); // "9.656000e+0"
```

**Nota**: Si no especificas el parámetro, JavaScript no redondeará el número.

**Analogía**: Piensa en `toExponential()` como una forma de poner tus números en una caja compacta, donde se muestra el valor pero de manera más simplificada.

## El Método `toFixed()`

El método `toFixed()` devuelve una cadena, con el número escrito con un número especificado de decimales:

**Ejemplo**
```javascript
let x = 9.656;
x.toFixed(0); // "10"
x.toFixed(2); // "9.66"
x.toFixed(4); // "9.6560"
x.toFixed(6); // "9.656000"
```

**Analogía**: Imagina que `toFixed()` es como hacer un corte perfecto en una torta, asegurándote de que cada porción tenga el mismo tamaño, ya sea grande o pequeña.

## El Método `toPrecision()`

El método `toPrecision()` devuelve una cadena, con un número escrito con una longitud especificada:

**Ejemplo**
```javascript
let x = 9.656;
x.toPrecision(); // "9.656"
x.toPrecision(2); // "9.7"
x.toPrecision(4); // "9.656"
x.toPrecision(6); // "9.65600"
```

**Analogía**: Piensa en `toPrecision()` como elegir el tamaño de una caja para un regalo. Dependiendo de cuán grande quieras que sea, puedes ajustar el tamaño de la caja para que se vea perfecto.

## El Método `valueOf()`

El método `valueOf()` devuelve un número como un número.

**Ejemplo**
```javascript
let x = 123;
x.valueOf(); // 123
(123).valueOf(); // 123
(100 + 23).valueOf(); // 123
```

En JavaScript, un número puede ser un valor primitivo (`typeof = number`) o un objeto (`typeof = object`).

El método `valueOf()` se utiliza internamente en JavaScript para convertir objetos de tipo Número a valores primitivos.

**Nota**: No hay razón para usarlo en tu código.

**Analogía**: Imagina que `valueOf()` es como un cartero que te entrega la carta sin envoltura. Solo te da el contenido directo.

## Conversión de Variables a Números

Hay 3 métodos de JavaScript que se pueden usar para convertir una variable a un número:

| Método      | Descripción                                              |
|-------------|---------------------------------------------------------|
| `Number()`  | Devuelve un número convertido de su argumento.          |
| `parseFloat()` | Analiza su argumento y devuelve un número de punto flotante. |
| `parseInt()` | Analiza su argumento y devuelve un número entero.       |

### El Método `Number()`

El método `Number()` puede ser usado para convertir variables de JavaScript a números:

**Ejemplo**
```javascript
Number(true);          // 1
Number(false);         // 0
Number("10");          // 10
Number("  10");        // 10
Number("10  ");        // 10
Number(" 10  ");       // 10
Number("10.33");       // 10.33
Number("10,33");       // NaN
Number("10 33");       // NaN
Number("John");        // NaN
```

**Nota**: Si el número no puede ser convertido, se devuelve `NaN` (Not a Number).

**Analogía**: Considera `Number()` como un traductor que convierte palabras o expresiones a un número, pero si la traducción no es posible, devuelve un "no sé" (NaN).

### El Método `parseInt()`

El método `parseInt()` analiza una cadena y devuelve un número entero. Se permiten espacios. Solo se devuelve el primer número:

**Ejemplo**
```javascript
parseInt("-10");          // -10
parseInt("-10.33");       // -10
parseInt("10");           // 10
parseInt("10.33");        // 10
parseInt("10 20 30");     // 10
parseInt("10 años");      // 10
parseInt("años 10");      // NaN
```

**Analogía**: Piensa en `parseInt()` como un detector de precios en un supermercado, que solo puede leer el precio inicial y descarta cualquier información adicional.

### El Método `parseFloat()`

El método `parseFloat()` analiza una cadena y devuelve un número. Se permiten espacios. Solo se devuelve el primer número:

**Ejemplo**
```javascript
parseFloat("10");          // 10
parseFloat("10.33");       // 10.33
parseFloat("10 20 30");    // 10
parseFloat("10 años");      // 10
parseFloat("años 10");      // NaN
```

**Analogía**: `parseFloat()` es como un vaso medidor que mide el líquido hasta cierto nivel y no se preocupa por lo que hay más allá.

## Métodos del Objeto Number

Estos métodos pertenecen al objeto Number:

| Método                          | Descripción                                                    |
|---------------------------------|---------------------------------------------------------------|
| `Number.isInteger()`            | Devuelve verdadero si el argumento es un número entero.       |
| `Number.isSafeInteger()`        | Devuelve verdadero si el argumento es un número entero seguro.|
| `Number.parseFloat()`           | Convierte una cadena a un número.                             |
| `Number.parseInt()`             | Convierte una cadena a un número entero.                      |

### El Método `Number.isInteger()`

El método `Number.isInteger()` devuelve verdadero si el argumento es un número entero.

**Ejemplo**
```javascript
Number.isInteger(10);      // true
Number.isInteger(10.5);    // false
```

**Analogía**: Imagina que `Number.isInteger()` es como un guardia en una fiesta que solo deja entrar a aquellos con un "boleto entero".

### El Método `Number.isSafeInteger()`

Un número entero seguro es un número entero que puede ser representado exactamente como un número de precisión doble.

El método `Number.isSafeInteger()` devuelve verdadero si el argumento es un número entero seguro.

**Ejemplo**
```javascript
Number.isSafeInteger(10);                   // true
Number.isSafeInteger(12345678901234567890); // false
```

Los números enteros seguros son todos los enteros desde `-(2^53 - 1)` hasta `+(2^53 - 1)`.

**Analogía**: Piensa en `Number.isSafeInteger()` como un detector de metal que asegura que los números no son demasiado grandes para ser manejados.

### El Método `Number.parseFloat()`

El método `Number.parseFloat()` analiza una cadena y devuelve un número.

Se permiten espacios. Solo se devuelve el primer número:

**Ejemplo**
```javascript
Number.parseFloat("10");          // 10
Number.parseFloat("10.33");       // 10.33
Number.parseFloat("10 20 30");    // 10
Number.parseFloat("10 años");      // 10
Number.parseFloat("años 10");      // NaN
```

**Nota**: Los métodos `Number.parseInt()` y `Number.parseFloat()` son los mismos que los métodos globales `parseInt()` y `parseFloat()`. 

El propósito es la modularización de los globales (para facilitar el uso del mismo código de JavaScript fuera del navegador).

**Analogía**: `Number.parseFloat()` es como un filtro de café que extrae solo el líquido

 útil y deja la parte no deseada atrás.

### Resumen

Los métodos numéricos de JavaScript son herramientas poderosas para manipular y trabajar con números. Usando analogías simples, podemos entender su funcionamiento y aplicarlos de manera efectiva en nuestros programas.

¡Prueba estos métodos en tu código y observa cómo transforman tus números!

---

# Propiedades de Number en JavaScript

## Propiedades de Número

| Propiedad            | Descripción                                                  |
|----------------------|--------------------------------------------------------------|
| `EPSILON`            | La diferencia entre 1 y el número más pequeño > 1.          |
| `MAX_VALUE`          | El número más grande posible en JavaScript.                 |
| `MIN_VALUE`          | El número más pequeño posible en JavaScript.                |
| `MAX_SAFE_INTEGER`   | El máximo entero seguro (253 - 1).                          |
| `MIN_SAFE_INTEGER`   | El mínimo entero seguro -(253 - 1).                         |
| `POSITIVE_INFINITY`  | Infinito (devuelto en un desbordamiento).                  |
| `NEGATIVE_INFINITY`  | Infinito negativo (devuelto en un desbordamiento).         |
| `NaN`                | Un valor "No es un número".                                 |

## JavaScript EPSILON

La propiedad `Number.EPSILON` representa la diferencia entre el número de punto flotante más pequeño mayor que 1 y 1.

**Ejemplo**
```javascript
let x = Number.EPSILON;
console.log(x); // 2.220446049250313e-16
```

**Nota**: `Number.EPSILON` es una característica de ES6 y no funciona en Internet Explorer.

**Analogía**: Imagina que `EPSILON` es como una regla que mide el espacio más pequeño que puedes percibir entre dos objetos. Aunque parece un pequeño espacio, es importante para saber la precisión de los números.

## JavaScript MAX_VALUE

`Number.MAX_VALUE` es una constante que representa el número más grande posible en JavaScript.

**Ejemplo**
```javascript
let x = Number.MAX_VALUE;
console.log(x); // 1.7976931348623157e+308
```

**Analogía**: Piensa en `MAX_VALUE` como el límite de una montaña. A medida que subes, te acercas a la cima, pero hay un punto en el que no puedes ir más allá. Ese es el número más grande que JavaScript puede manejar.

## JavaScript MIN_VALUE

`Number.MIN_VALUE` es una constante que representa el número más pequeño posible en JavaScript.

**Ejemplo**
```javascript
let x = Number.MIN_VALUE;
console.log(x); // 5e-324
```

**Analogía**: Imagina que `MIN_VALUE` es el fondo de un océano. Es el punto más bajo que puedes alcanzar en el agua, pero aún hay un poco de agua, aunque sea muy poca.

## JavaScript MAX_SAFE_INTEGER

`Number.MAX_SAFE_INTEGER` representa el entero seguro máximo en JavaScript, que es (253 - 1).

**Ejemplo**
```javascript
let x = Number.MAX_SAFE_INTEGER;
console.log(x); // 9007199254740991
```

**Analogía**: Piensa en `MAX_SAFE_INTEGER` como una caja de seguridad. Puedes almacenar objetos hasta cierto límite; más allá de eso, los objetos podrían dañarse o perderse.

## JavaScript MIN_SAFE_INTEGER

`Number.MIN_SAFE_INTEGER` representa el entero seguro mínimo en JavaScript, que es -(253 - 1).

**Ejemplo**
```javascript
let x = Number.MIN_SAFE_INTEGER;
console.log(x); // -9007199254740991
```

**Nota**: `MAX_SAFE_INTEGER` y `MIN_SAFE_INTEGER` son características de ES6 y no funcionan en Internet Explorer.

**Analogía**: Considera `MIN_SAFE_INTEGER` como el fondo de una caja de seguridad. Es el punto más bajo que puedes llegar a almacenar sin que los objetos se pierdan.

## JavaScript POSITIVE_INFINITY

`Number.POSITIVE_INFINITY` representa infinito positivo.

**Ejemplo**
```javascript
let x = Number.POSITIVE_INFINITY;
console.log(x); // Infinity
```

**Infinito positivo** se devuelve en caso de un desbordamiento:

```javascript
let x = 1 / 0; // Devuelve Infinity
console.log(x);
```

**Analogía**: Imagina que `POSITIVE_INFINITY` es como el horizonte. No importa cuánto camines hacia él, siempre parece estar a la distancia, nunca lo alcanzas.

## JavaScript NEGATIVE_INFINITY

`Number.NEGATIVE_INFINITY` representa infinito negativo.

**Ejemplo**
```javascript
let x = Number.NEGATIVE_INFINITY;
console.log(x); // -Infinity
```

**Infinito negativo** se devuelve en caso de un desbordamiento:

```javascript
let x = -1 / 0; // Devuelve -Infinity
console.log(x);
```

**Analogía**: Piensa en `NEGATIVE_INFINITY` como el fondo de un pozo. Cuanto más profundo cavas, más lejos te alejas de la superficie, pero nunca llegas a un final.

## JavaScript NaN - Not a Number

`NaN` es una palabra reservada en JavaScript que indica un número que no es legal.

**Ejemplo**
```javascript
let x = Number.NaN;
console.log(x); // NaN
```

Intentar realizar una operación aritmética con una cadena no numérica resultará en `NaN` (No es un número):

```javascript
let x = 100 / "Apple"; // Devuelve NaN
console.log(x);
```

**Analogía**: Imagina que `NaN` es como un rompecabezas con piezas que no encajan. A pesar de que lo intentas, no puedes formar una imagen coherente con esas piezas.

## Propiedades de Números No Se Pueden Usar en Variables

Las propiedades de número pertenecen al objeto Number de JavaScript. Estas propiedades solo se pueden acceder como `Number.MAX_VALUE`. 

Usar `x.MAX_VALUE`, donde `x` es una variable o un valor, devolverá `undefined`:

**Ejemplo**
```javascript
let x = 6;
console.log(x.MAX_VALUE); // undefined
```

**Analogía**: Esto es como intentar usar una etiqueta que solo está en la caja, no en el objeto dentro de la caja. El objeto dentro de la caja no puede acceder a las propiedades de la caja.

---

# Arrays en JavaScript

Un **array** (o arreglo) es una variable especial que puede contener más de un valor:

```javascript
const autos = ["Saab", "Volvo", "BMW"];
```

## ¿Por qué usar arrays?

Si tienes una lista de elementos (por ejemplo, una lista de nombres de autos), almacenar los autos en variables individuales podría verse así:

```javascript
let auto1 = "Saab";
let auto2 = "Volvo";
let auto3 = "BMW";
```

Pero, ¿qué pasa si quieres recorrer los autos y encontrar uno específico? ¿Y si tuvieras no 3 autos, sino 300?

La solución es un **array**.

Un array puede contener muchos valores bajo un solo nombre, y puedes acceder a los valores al referirte a un número de índice.

## Crear un Array

Usar un literal de array es la forma más fácil de crear un array en JavaScript.

### Sintaxis

```javascript
const nombre_array = [elemento1, elemento2, ...];
```

Es común declarar arrays con la palabra clave `const`.

### Ejemplo

```javascript
const autos = ["Saab", "Volvo", "BMW"];
```

Los espacios y saltos de línea no son importantes. Una declaración puede ocupar varias líneas:

### Ejemplo

```javascript
const autos = [
  "Saab",
  "Volvo",
  "BMW"
];
```

También puedes crear un array y luego proporcionar los elementos:

### Ejemplo

```javascript
const autos = [];
autos[0] = "Saab";
autos[1] = "Volvo";
autos[2] = "BMW";
```

### Usando la palabra clave `new`

El siguiente ejemplo también crea un array y le asigna valores:

### Ejemplo

```javascript
const autos = new Array("Saab", "Volvo", "BMW");
```

Los dos ejemplos anteriores hacen exactamente lo mismo. No es necesario usar `new Array()`. 

Para simplicidad, legibilidad y velocidad de ejecución, usa el método de literal de array.

## Acceder a Elementos de un Array

Puedes acceder a un elemento de un array refiriéndote al número de índice:

```javascript
const autos = ["Saab", "Volvo", "BMW"];
let auto = autos[0];
```

**Nota:** Los índices de los arrays comienzan en 0. 

- `[0]` es el primer elemento.
- `[1]` es el segundo elemento.

## Cambiar un Elemento de un Array

Esta declaración cambia el valor del primer elemento en `autos`:

```javascript
autos[0] = "Opel";
```

### Ejemplo

```javascript
const autos = ["Saab", "Volvo", "BMW"];
autos[0] = "Opel";
```

## Convertir un Array a una Cadena

El método de JavaScript `toString()` convierte un array en una cadena de valores de array (separados por comas).

### Ejemplo

```javascript
const frutas = ["Banana", "Naranja", "Manzana", "Mango"];
document.getElementById("demo").innerHTML = frutas.toString();
```

**Resultado:**

```
Banana,Naranja,Manzana,Mango
```

## Acceder al Array Completo

Con JavaScript, el array completo se puede acceder refiriéndote al nombre del array:

### Ejemplo

```javascript
const autos = ["Saab", "Volvo", "BMW"];
document.getElementById("demo").innerHTML = autos;
```

## Los Arrays son Objetos

Los arrays son un tipo especial de objetos. El operador `typeof` en JavaScript devuelve "object" para los arrays.

Pero, los arrays en JavaScript se describen mejor como arrays.

Los arrays utilizan números para acceder a sus "elementos". En este ejemplo, `persona[0]` devuelve "Juan":

### Array:

```javascript
const persona = ["Juan", "Doe", 46];
```

Los objetos utilizan nombres para acceder a sus "miembros". En este ejemplo, `persona.firstName` devuelve "Juan":

### Objeto:

```javascript
const persona = {firstName: "Juan", lastName: "Doe", age: 46};
```

## Los Elementos de un Array Pueden Ser Objetos

Las variables en JavaScript pueden ser objetos. Los arrays son tipos especiales de objetos.

Debido a esto, puedes tener variables de diferentes tipos en el mismo array.

Puedes tener objetos en un array. Puedes tener funciones en un array. Puedes tener arrays en un array:

```javascript
miArray[0] = Date.now;
miArray[1] = miFuncion;
miArray[2] = misAutos;
```

## Propiedades y Métodos de Arrays

La verdadera fortaleza de los arrays en JavaScript son las propiedades y métodos de array integrados:

- `autos.length`   // Devuelve el número de elementos
- `autos.sort()`   // Ordena el array

Los métodos de array se cubrirán en los próximos capítulos.

## La Propiedad Length

La propiedad `length` de un array devuelve la longitud de un array (el número de elementos del array).

### Ejemplo

```javascript
const frutas = ["Banana", "Naranja", "Manzana", "Mango"];
let longitud = frutas.length;
```

La propiedad `length` siempre es una más que el índice más alto del array.

## Accediendo al Primer Elemento del Array

### Ejemplo

```javascript
const frutas = ["Banana", "Naranja", "Manzana", "Mango"];
let fruta = frutas[0];
```

## Accediendo al Último Elemento del Array

### Ejemplo

```javascript
const frutas = ["Banana", "Naranja", "Manzana", "Mango"];
let fruta = frutas[frutas.length - 1];
```

## Recorrer Elementos de un Array

Una forma de recorrer un array es utilizando un bucle `for`:

### Ejemplo

```javascript
const frutas = ["Banana", "Naranja", "Manzana", "Mango"];
let fLen = frutas.length;

let texto = "<ul>";
for (let i = 0; i < fLen; i++) {
  texto += "<li>" + frutas[i] + "</li>";
}
texto += "</ul>";
```

También puedes usar la función `Array.forEach()`:

### Ejemplo

```javascript
const frutas = ["Banana", "Naranja", "Manzana", "Mango"];

let texto = "<ul>";
frutas.forEach(miFuncion);
texto += "</ul>";

function miFuncion(valor) {
  texto += "<li>" + valor + "</li>";
}
```

## Agregar Elementos a un Array

La forma más fácil de agregar un nuevo elemento a un array es utilizando el método `push()`:

### Ejemplo

```javascript
const frutas = ["Banana", "Naranja", "Manzana"];
frutas.push("Limón");  // Agrega un nuevo elemento (Limón) a frutas
```

También se puede agregar un nuevo elemento a un array usando la propiedad `length`:

### Ejemplo

```javascript
const frutas = ["Banana", "Naranja", "Manzana"];
frutas[frutas.length] = "Limón";  // Agrega "Limón" a frutas
```

## ¡ADVERTENCIA!

Agregar elementos con índices altos puede crear "huecos" indefinidos en un array:

### Ejemplo

```javascript
const frutas = ["Banana", "Naranja", "Manzana"];
frutas[6] = "Limón";  // Crea huecos indefinidos en frutas
```

## Arrays Asociativos

Muchos lenguajes de programación admiten arrays con índices nombrados.

Los arrays con índices nombrados se llaman arrays asociativos (o hashes).

JavaScript no admite arrays con índices nombrados.

En JavaScript, los arrays siempre utilizan índices numerados.  

### Ejemplo

```javascript
const persona = [];
persona[0] = "Juan";
persona[1] = "Doe";
persona[2] = 46;
persona.length;    // Devolverá 3
persona[0];        // Devolverá "Juan"
```

## ¡ADVERTENCIA!

Si usas índices nombrados, JavaScript redefinirá el array como un objeto.

Después de eso, algunos métodos y propiedades del array producirán resultados incorrectos.

### Ejemplo:

```javascript
const persona = [];
persona["firstName"] = "Juan";
persona["lastName"] = "Doe";
persona["age"] = 46;
persona.length;     // Devolverá 0
persona[0];         // Devolverá indefinido
```

## La Diferencia Entre Arrays y Objetos

En JavaScript, los arrays utilizan índices numerados.  

En JavaScript, los objetos utilizan índices nombrados.

Los arrays son una especie especial de objetos, con índices numerados.

### Cuándo usar Arrays. Cuándo usar Objetos.

JavaScript no admite arrays asociativos. 

Debes usar objetos cuando quieras que los nombres de los elementos sean cadenas (texto).

Debes usar arrays cuando quieras que los nombres de los elementos sean números.

## JavaScript new Array()

JavaScript tiene un constructor de array incorporado `new Array()`.

Pero puedes usar `[]` de forma segura en su lugar.

Estas dos declaraciones diferentes crean un nuevo array vacío llamado `puntos`:

```javascript
const puntos = new Array();
const puntos = [];
```

Estas dos declaraciones diferentes crean

 un nuevo array llamado `puntos` que contiene tres elementos:

```javascript
const puntos = new Array(3);  // Crea un array de longitud 3
const puntos = [1, 2, 3];      // Crea un array que contiene 3 elementos
```

## Conclusión

Los arrays son estructuras de datos fundamentales en JavaScript que te permiten almacenar y gestionar múltiples valores de manera eficiente. 

Desde acceder y modificar elementos hasta recorrer sus valores y utilizar métodos incorporados, los arrays son una herramienta poderosa para el desarrollo web. Al comprender cómo funcionan y cuándo utilizarlos, puedes mejorar significativamente la calidad y la eficacia de tu código.

---

# Metodos de Array en JavaScript

## Basic Array Methods

### Array length

El **método `length`** es como contar cuántas manzanas hay en una canasta. Devuelve el número de elementos que hay en un arreglo.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let size = fruits.length; // size es 4
```

### Array toString()

El **método `toString()`** convierte un arreglo en una cadena de texto, similar a listar todos los ingredientes de una receta separados por comas.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.toString(); // "Banana,Orange,Apple,Mango"
```

### Array at()

El **método `at()`** te permite acceder a un elemento en un arreglo, como si estuvieras buscando un libro en una estantería, usando su posición.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let fruit = fruits.at(2); // fruit es "Apple"
```

### Array join()

El **método `join()`** une todos los elementos de un arreglo en una cadena, como juntar las piezas de un rompecabezas para formar una imagen.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.join(" * "); // "Banana * Orange * Apple * Mango"
```

## Popping and Pushing

Cuando trabajas con arreglos, puedes **sacar (pop)** o **meter (push)** elementos, como en una caja de juguetes.

### JavaScript Array pop()

El **método `pop()`** quita el último elemento de un arreglo.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.pop(); // El arreglo ahora es ["Banana", "Orange", "Apple"]
```

### JavaScript Array push()

El **método `push()`** agrega un nuevo elemento al final de un arreglo.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.push("Kiwi"); // El arreglo ahora es ["Banana", "Orange", "Apple", "Mango", "Kiwi"]
```

## Shifting Elements

**Shifting** es como **popping**, pero quita el primer elemento.

### JavaScript Array shift()

El **método `shift()`** quita el primer elemento de un arreglo y mueve todos los demás elementos hacia abajo.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.shift(); // El arreglo ahora es ["Orange", "Apple", "Mango"]
```

### JavaScript Array unshift()

El **método `unshift()`** agrega un nuevo elemento al principio del arreglo, como si estuvieras agregando una nueva caja a la parte superior de una torre de cajas.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.unshift("Lemon"); // El arreglo ahora es ["Lemon", "Banana", "Orange", "Apple", "Mango"]
```

## Changing Elements

Acceder a los elementos de un arreglo es como abrir una caja. Cada elemento tiene un número de índice, comenzando desde cero.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits[0] = "Kiwi"; // El arreglo ahora es ["Kiwi", "Orange", "Apple", "Mango"]
```

## JavaScript Array delete()

El **método `delete()`** elimina un elemento, pero deja un "hueco" en el arreglo. Es como sacar una manzana de una canasta y dejar el espacio vacío.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
delete fruits[0]; // El arreglo ahora es [undefined, "Orange", "Apple", "Mango"]
```

## Merging Arrays (Concatenating)

**Concatenar** arreglos es como juntar dos listas de compras en una sola.

### JavaScript Array concat()

El **método `concat()`** combina dos o más arreglos.

```javascript
const myGirls = ["Cecilie", "Lone"];
const myBoys = ["Emil", "Tobias", "Linus"];
const myChildren = myGirls.concat(myBoys); // ["Cecilie", "Lone", "Emil", "Tobias", "Linus"]
```

## Array copyWithin()

El **método `copyWithin()`** copia elementos de un arreglo a otra posición dentro del mismo arreglo.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.copyWithin(2, 0); // El arreglo ahora es ["Banana", "Orange", "Banana", "Orange"]
```

## Flattening an Array

**Flattening** un arreglo significa convertir un arreglo multidimensional en uno unidimensional.

### JavaScript Array flat()

El **método `flat()`** aplana un arreglo a una profundidad específica.

```javascript
const myArr = [[1,2],[3,4],[5,6]];
const newArr = myArr.flat(); // [1, 2, 3, 4, 5, 6]
```

## Splicing and Slicing Arrays

Los métodos **splice()** y **slice()** te permiten modificar un arreglo de diferentes maneras.

### JavaScript Array splice()

El **método `splice()`** puede agregar y eliminar elementos al mismo tiempo.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 0, "Lemon", "Kiwi"); // ["Banana", "Orange", "Lemon", "Kiwi", "Apple", "Mango"]
```

### JavaScript Array slice()

El **método `slice()`** extrae una sección de un arreglo y crea un nuevo arreglo.

```javascript
const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
const citrus = fruits.slice(1, 3); // ["Orange", "Lemon"]
```

---

Este documento proporciona una visión general de los métodos básicos de arreglos en JavaScript, ilustrando conceptos técnicos a través de analogías cotidianas. Con el tiempo, comprender estos métodos te ayudará a construir aplicaciones más complejas y efectivas.

### Notas
- Puedes personalizar aún más el contenido y las analogías para que se ajusten mejor a tu estilo.
- Asegúrate de probar el código y los ejemplos antes de publicarlos para garantizar su funcionamiento.
- Considera agregar secciones adicionales sobre métodos de búsqueda, ordenación e iteración según lo mencionado en la sección "See Also".

---

# Búsqueda en Arrays de JavaScript

En esta sección, exploraremos varios métodos para buscar en arrays en JavaScript. Piensa en un array como una fila de personas esperando para entrar a un concierto, y queremos encontrar individuos específicos (o valores) en esa fila. Cada persona tiene una posición, al igual que cada valor en el array tiene un índice.

## Métodos de Búsqueda y Encuentro de Arrays

### Array `indexOf()`

El método `indexOf()` es como preguntar por la posición de un amigo en la fila. Si tu amigo "Apple" está en la segunda posición, obtendrás `1` (recuerda, comenzamos a contar desde 0).

**Ejemplo:**

```javascript
const frutas = ["Apple", "Orange", "Apple", "Mango"];
let posicion = frutas.indexOf("Apple") + 1; // devuelve 1 (primer ocurrencia)
```

**Sintaxis:**

```javascript
array.indexOf(item, start)
```

- `item`: El ítem que estás buscando.
- `start`: Opcional. El índice desde el cual comenzar la búsqueda. Los valores negativos comenzarán a contar desde el final.

**Nota:** Si el ítem no se encuentra, devuelve `-1`. Si aparece múltiples veces, solo devuelve la posición de la primera ocurrencia.

---

### Array `lastIndexOf()`

El método `lastIndexOf()` funciona como una búsqueda inversa, buscando la última ocurrencia de un amigo en la fila. Si hay varios amigos "Apple", te dirá la posición del último.

**Ejemplo:**

```javascript
const frutas = ["Apple", "Orange", "Apple", "Mango"];
let posicion = frutas.lastIndexOf("Apple") + 1; // devuelve 3 (última ocurrencia)
```

**Sintaxis:**

```javascript
array.lastIndexOf(item, start)
```

- `item`: El ítem que se busca.
- `start`: Opcional. El índice desde el cual comenzar la búsqueda. Los valores negativos comenzarán a contar desde el final.

---

### Array `includes()`

Introducido en ECMAScript 2016, `includes()` comprueba si un amigo está presente en la fila sin dar su posición.

**Ejemplo:**

```javascript
const frutas = ["Banana", "Orange", "Apple", "Mango"];
console.log(frutas.includes("Mango")); // true
```

**Sintaxis:**

```javascript
array.includes(search-item)
```

**Nota:** Este método también puede comprobar valores `NaN`, a diferencia de `indexOf()`.

**Soporte en Navegadores:** Este método es compatible con todos los navegadores modernos, pero no con Internet Explorer.

---

### Método `find()` de JavaScript Array

El método `find()` es como buscar al primer amigo en la fila que sea más alto que 18. Devuelve el valor de la primera persona que satisface la condición.

**Ejemplo:**

```javascript
const numeros = [4, 9, 16, 25, 29];
let primero = numeros.find(valor => valor > 18); // devuelve 25
```

**Soporte en Navegadores:** Esta es una característica de ES6 y es compatible con todos los navegadores modernos desde junio de 2017.

---

### Método `findIndex()` de JavaScript Array

Similar a `find()`, el método `findIndex()` devuelve la posición (índice) de la primera persona en la fila que satisface la condición.

**Ejemplo:**

```javascript
const numeros = [4, 9, 16, 25, 29];
let primerIndice = numeros.findIndex(valor => valor > 18); // devuelve 3
```

**Soporte en Navegadores:** Este método también es una característica de ES6 y es compatible con todos los navegadores modernos.

---

### Método `findLast()` de JavaScript Array

Introducido en ES2023, `findLast()` comienza desde el final de la fila y devuelve el valor de la primera persona que satisface la condición.

**Ejemplo:**

```javascript
const temp = [27, 28, 30, 40, 42, 35, 30];
let alto = temp.findLast(x => x > 40); // devuelve 42
```

**Soporte en Navegadores:** Compatible en navegadores modernos desde julio de 2023.

---

### Método `findLastIndex()` de JavaScript Array

El método `findLastIndex()` encuentra el índice de la última persona que satisface una condición.

**Ejemplo:**

```javascript
const temp = [27, 28, 30, 40, 42, 35, 30];
let ultimoIndice = temp.findLastIndex(x => x > 40); // devuelve 4
```

**Soporte en Navegadores:** Compatible en navegadores modernos desde julio de 2023.

---

# JavaScript Sorting Arrays

En este artículo, exploraremos cómo ordenar arreglos en JavaScript y aprenderemos sobre métodos importantes como `sort()`, `reverse()`, `toSorted()`, y más, utilizando analogías para entender mejor cada concepto.

## Métodos de Ordenación de Arreglos

### Orden Alfabético

Imagina que tienes un grupo de amigos y decides organizarlos en orden alfabético por sus nombres. Así es como funciona el método `sort()`. Ordena los elementos de un arreglo como si estuvieras organizando nombres en una lista.

#### Ejemplo
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();
console.log(fruits); // ["Apple", "Banana", "Mango", "Orange"]
```

### Reversar un Arreglo

Si al final de la fiesta decides hacer una broma y poner a todos los amigos en orden inverso, usarías el método `reverse()`. Este método invierte el orden de los elementos en un arreglo.

#### Ejemplo
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.reverse();
console.log(fruits); // ["Mango", "Apple", "Orange", "Banana"]
```

Al combinar `sort()` y `reverse()`, puedes ordenar un arreglo en orden descendente, como poner a tus amigos en orden inverso después de haberlos organizado.

#### Ejemplo
```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort().reverse();
console.log(fruits); // ["Orange", "Mango", "Banana", "Apple"]
```

## Método `toSorted()`

Imagina que quieres ordenar la lista de amigos, pero no quieres perder el orden original. El método `toSorted()` es como hacer una copia de la lista y ordenarla, dejando la original intacta.

#### Ejemplo
```javascript
const months = ["Jan", "Feb", "Mar", "Apr"];
const sorted = months.toSorted();
console.log(sorted); // ["Apr", "Feb", "Jan", "Mar"]
console.log(months); // ["Jan", "Feb", "Mar", "Apr"]
```

## Método `toReversed()`

Al igual que `toSorted()`, el método `toReversed()` te permite invertir un arreglo sin alterar el original.

#### Ejemplo
```javascript
const months = ["Jan", "Feb", "Mar", "Apr"];
const reversed = months.toReversed();
console.log(reversed); // ["Apr", "Mar", "Feb", "Jan"]
console.log(months); // ["Jan", "Feb", "Mar", "Apr"]
```

## Ordenación Numérica

Por defecto, `sort()` ordena los elementos como si fueran cadenas. Si intentas ordenar números, puede que obtengas resultados inesperados. Es como si quisieras organizar tus amigos por edad, pero los ordenas como si fueran nombres, lo que puede causar confusión.

### Ejemplo
```javascript
const points = [40, 100, 1, 5, 25, 10];
points.sort();
console.log(points); // [1, 10, 100, 25, 40]
```

Para solucionar esto, puedes proporcionar una función de comparación que te ayude a ordenar los números correctamente.

### Ejemplo
```javascript
points.sort(function(a, b) { return a - b; });
console.log(points); // [1, 5, 10, 25, 40, 100]
```

### La Función de Comparación

La función de comparación define el orden de clasificación. Si devuelve un valor negativo, `a` se coloca antes que `b`. Si devuelve un valor positivo, `b` se coloca antes que `a`. Si devuelve 0, el orden se mantiene.

## Ordenación Aleatoria de un Arreglo

Si deseas mezclar los números, puedes hacerlo usando `sort()` con un truco, aunque no será muy preciso.

### Ejemplo
```javascript
const points = [40, 100, 1, 5, 25, 10];
points.sort(function() { return 0.5 - Math.random(); });
console.log(points); // Ejemplo: [25, 1, 100, 5, 10, 40]
```

### El Método Fisher-Yates

Para mezclar un arreglo de manera más efectiva, puedes usar el método Fisher-Yates, que es un método más confiable.

### Ejemplo
```javascript
const points = [40, 100, 1, 5, 25, 10];
for (let i = points.length - 1; i > 0; i--) {
  let j = Math.floor(Math.random() * (i + 1));
  [points[i], points[j]] = [points[j], points[i]];
}
console.log(points); // Ejemplo: [1, 40, 25, 10, 100, 5]
```

## Encontrar el Valor Más Bajo (o Más Alto) de un Arreglo

Para encontrar el valor más bajo o más alto en un arreglo, puedes utilizar varios métodos, como ordenar el arreglo y leer el primer o último elemento.

### Ejemplo (Encontrar el Mínimo)
```javascript
const points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b) { return a - b; });
// Ahora points[0] contiene el valor más bajo
console.log(points[0]); // 1
```

### Usando `Math.min()`

También puedes usar `Math.min()` para encontrar el número más bajo en un arreglo.

### Ejemplo
```javascript
function myArrayMin(arr) {
  return Math.min.apply(null, arr);
}
console.log(myArrayMin([1, 2, 3])); // 1
```

### Usando `Math.max()`

De manera similar, puedes usar `Math.max()` para encontrar el número más alto.

### Ejemplo
```javascript
function myArrayMax(arr) {
  return Math.max.apply(null, arr);
}
console.log(myArrayMax([1, 2, 3])); // 3
```

## Métodos Caseros para Mínimos y Máximos

Si no tienes acceso a `Math.min()` o `Math.max()`, puedes escribir tus propias funciones que recorran el arreglo y encuentren los valores.

### Ejemplo (Encontrar Mínimo)
```javascript
function myArrayMin(arr) {
  let min = Infinity;
  for (let value of arr) {
    if (value < min) {
      min = value;
    }
  }
  return min;
}
```

### Ejemplo (Encontrar Máximo)
```javascript
function myArrayMax(arr) {
  let max = -Infinity;
  for (let value of arr) {
    if (value > max) {
      max = value;
    }
  }
  return max;
}
```

## Ordenar Arreglos de Objetos

Cuando trabajas con arreglos de objetos, también puedes usar `sort()`. Es como tener un grupo de amigos, pero cada uno tiene su propia edad.

### Ejemplo
```javascript
const cars = [
  {type: "Volvo", year: 2016},
  {type: "Saab", year: 2001},
  {type: "BMW", year: 2010}
];
cars.sort(function(a, b) { return a.year - b.year; });
console.log(cars);
```

### Comparar Propiedades de Cadenas

Cuando comparas propiedades de cadena, el proceso es un poco más complejo, como decidir el orden de los nombres de tus amigos alfabéticamente.

### Ejemplo
```javascript
cars.sort(function(a, b) {
  let x = a.type.toLowerCase();
  let y = b.type.toLowerCase();
  return x < y ? -1 : x > y ? 1 : 0;
});
console.log(cars);
```

## Ordenación Estable de Arreglos

Desde ES2019, la especificación de `Array.sort()` permite algoritmos de ordenación estables. Esto significa que si dos elementos tienen el mismo valor, mantendrán su posición relativa.

### Ejemplo
```javascript
const myArr = [
  {name: "X00", price: 100},
  {name: "X01", price: 100},
  {name: "X02", price: 100},
  {name: "X03", price: 100},
  {name: "X04", price: 110},
  {name: "X05", price: 110},
  {name: "X06", price: 110},
  {name: "X07", price: 110}
];
myArr.sort(function(a, b) { return a.price - b.price; });
console.log(myArr);
```

---

# Iteración de Arreglos en JavaScript

## Métodos de Iteración de Arreglos

Los métodos de iteración de arreglos operan sobre cada elemento de un arreglo:

- `Array.forEach`
- `Array.map()`
- `Array.flatMap()`
- `Array.filter()`
- `Array.reduce()`
- `Array.reduceRight()`

### Véase también:
- Métodos Básicos de Arreglos
- Métodos de Búsqueda de Arreglos
- Métodos de Ordenamiento de Arreglos
- `Array.every()`
- `Array.some()`
- `Array.from()`
- `Array.keys()`
- `Array.entries()`
- `Array.with()`
- Expansión de Arreglos `(...)`

---

## JavaScript Array.forEach()

El método `forEach()` llama a una función (una función de callback) una vez para cada elemento del arreglo.

### Ejemplo
```javascript
const numeros = [45, 4, 9, 16, 25];
let txt = "";
numeros.forEach(miFuncion);

function miFuncion(valor, indice, arreglo) {
  txt += valor + "<br>";
}
```

**Nota:** La función toma 3 argumentos:

- El valor del elemento
- El índice del elemento
- El propio arreglo

El ejemplo anterior utiliza solo el parámetro `valor`. Se puede reescribir como:

### Ejemplo
```javascript
const numeros = [45, 4, 9, 16, 25];
let txt = "";
numeros.forEach(miFuncion);

function miFuncion(valor) {
  txt += valor + "<br>";
}
```

---

## JavaScript Array.map()

El método `map()` crea un nuevo arreglo realizando una función en cada elemento del arreglo.

Este método no ejecuta la función para los elementos del arreglo que no tienen valores y no cambia el arreglo original.

### Ejemplo
```javascript
const numeros1 = [45, 4, 9, 16, 25];
const numeros2 = numeros1.map(miFuncion);

function miFuncion(valor, indice, arreglo) {
  return valor * 2;
}
```

**Nota:** La función toma 3 argumentos:

- El valor del elemento
- El índice del elemento
- El propio arreglo

Cuando una función de callback usa solo el parámetro `valor`, los parámetros `índice` y `arreglo` pueden omitirse.

### Ejemplo
```javascript
const numeros1 = [45, 4, 9, 16, 25];
const numeros2 = numeros1.map(miFuncion);

function miFuncion(valor) {
  return valor * 2;
}
```

---

## JavaScript Array.flatMap()

ES2019 agregó el método `flatMap()` a JavaScript.

El método `flatMap()` primero mapea todos los elementos de un arreglo y luego crea un nuevo arreglo aplanando el arreglo.

### Ejemplo
```javascript
const miArr = [1, 2, 3, 4, 5, 6];
const nuevoArr = miArr.flatMap((x) => x * 2);
```

### Soporte en Navegadores
El método `flatMap()` es compatible con todos los navegadores modernos desde enero de 2020:

- Chrome 69
- Edge 79
- Firefox 62
- Safari 12
- Opera 56

---

## JavaScript Array.filter()

El método `filter()` crea un nuevo arreglo con los elementos del arreglo que pasan una prueba.

### Ejemplo
```javascript
const numeros = [45, 4, 9, 16, 25];
const mayoresDe18 = numeros.filter(miFuncion);

function miFuncion(valor) {
  return valor > 18;
}
```

**Nota:** La función toma 3 argumentos:

- El valor del elemento
- El índice del elemento
- El propio arreglo

---

## JavaScript Array.reduce()

El método `reduce()` ejecuta una función en cada elemento del arreglo para producir (reducirlo a) un único valor.

El método `reduce()` trabaja de izquierda a derecha en el arreglo. Ver también `reduceRight()`.

### Ejemplo
```javascript
const numeros = [45, 4, 9, 16, 25];
let suma = numeros.reduce(miFuncion);

function miFuncion(total, valor) {
  return total + valor;
}
```

**Nota:** La función toma 4 argumentos:

- El total (el valor inicial / valor previamente devuelto)
- El valor del elemento
- El índice del elemento
- El propio arreglo

---

## JavaScript Array.reduceRight()

El método `reduceRight()` ejecuta una función en cada elemento del arreglo para producir (reducirlo a) un único valor.

`reduceRight()` trabaja de derecha a izquierda en el arreglo. Ver también `reduce()`.

### Ejemplo
```javascript
const numeros = [45, 4, 9, 16, 25];
let suma = numeros.reduceRight(miFuncion);

function miFuncion(total, valor) {
  return total + valor;
}
```

---

## JavaScript Array.every()

El método `every()` verifica si todos los valores del arreglo pasan una prueba.

### Ejemplo
```javascript
const numeros = [45, 4, 9, 16, 25];
let todosMayoresDe18 = numeros.every(miFuncion);

function miFuncion(valor) {
  return valor > 18;
}
```

---

## JavaScript Array.some()

El método `some()` verifica si algunos valores del arreglo pasan una prueba.

### Ejemplo
```javascript
const numeros = [45, 4, 9, 16, 25];
let algunosMayoresDe18 = numeros.some(miFuncion);

function miFuncion(valor) {
  return valor > 18;
}
```

---

## JavaScript Array.from()

El método `Array.from()` devuelve un objeto Array de cualquier objeto con una propiedad de longitud o cualquier objeto iterable.

### Ejemplo
Crea un Array a partir de una cadena:

```javascript
Array.from("ABCDEFG");
```

### Soporte en Navegadores
`from()` es una característica de ES6 (JavaScript 2015). ES6 es completamente compatible en todos los navegadores modernos desde junio de 2017.

---

## JavaScript Array.keys()

El método `Array.keys()` devuelve un objeto Iterador de Arreglo con las claves de un arreglo.

### Ejemplo
Crea un objeto Iterador de Arreglo, conteniendo las claves del arreglo:

```javascript
const frutas = ["Banana", "Naranja", "Manzana", "Mango"];
const claves = frutas.keys();

for (let x of claves) {
  console.log(x);
}
```

### Soporte en Navegadores
`keys()` es una característica de ES6 (JavaScript 2015). ES6 es completamente compatible en todos los navegadores modernos desde junio de 2017.

---

## JavaScript Array.entries()

Crea un Iterador de Arreglo y luego itera sobre los pares clave/valor:

### Ejemplo
```javascript
const frutas = ["Banana", "Naranja", "Manzana", "Mango"];
const f = frutas.entries();

for (let x of f) {
  console.log(x);
}
```

El método `entries()` devuelve un objeto Iterador de Arreglo con pares clave/valor:

- [0, "Banana"]
- [1, "Naranja"]
- [2, "Manzana"]
- [3, "Mango"]

### Soporte en Navegadores
`entries()` es una característica de ES6 (JavaScript 2015). ES6 es completamente compatible en todos los navegadores modernos desde junio de 2017.

---

## JavaScript Array.with() Método

ES2023 agregó el método `Array.with()` como una forma segura de actualizar elementos en un arreglo sin alterar el arreglo original.

### Ejemplo
```javascript
const meses = ["Enero", "Febrero", "Marzo", "Abril"];
const misMeses = meses.with(2, "Marzo");
```

---

## JavaScript Array Spread (...)


El operador `...` expande un iterable (como un arreglo) en más elementos:

### Ejemplo
```javascript
const t1 = ["Ene", "Feb", "Mar"];
const t2 = ["Abr", "May", "Jun"];
const t3 = ["Jul", "Ago", "Sep"];
const t4 = ["Oct", "Nov", "Dic"];

const anio = [...t1, ...t2, ...t3, ...t4];
```

### Soporte en Navegadores
`...` es una característica de ES6 (JavaScript 2015). ES6 es completamente compatible en todos los navegadores modernos desde junio de 2017.

---

# JavaScript Array Const

## ECMAScript 2015 (ES6)

En 2015, JavaScript introdujo una nueva palabra clave importante: `const`.

Es una práctica común declarar arrays utilizando `const`:

### Ejemplo
```javascript
const cars = ["Saab", "Volvo", "BMW"];
```

## No se Puede Reasignar

Un array declarado con `const` no puede ser reasignado:

### Ejemplo
```javascript
const cars = ["Saab", "Volvo", "BMW"];
cars = ["Toyota", "Volvo", "Audi"]; // ERROR
```

### Analogía
Imagina que `const` es como un nombre en una etiqueta de una caja. Si etiquetas la caja con "Coches", no puedes cambiar la etiqueta a "Autos" (reasignar la variable). Sin embargo, puedes seguir cambiando los objetos dentro de la caja (modificar el contenido del array).

## Los Arrays No Son Constantes

La palabra clave `const` puede ser un poco engañosa. No define un array constante; define una referencia constante a un array.

Por eso, aún podemos cambiar los elementos de un array constante.

### Los Elementos Pueden Ser Reasignados
Puedes cambiar los elementos de un array constante:

### Ejemplo
```javascript
// Puedes crear un array constante:
const cars = ["Saab", "Volvo", "BMW"];

// Puedes cambiar un elemento:
cars[0] = "Toyota"; // Cambia "Saab" a "Toyota"

// Puedes agregar un elemento:
cars.push("Audi"); // Agrega "Audi"
```

### Analogía
Imagina que la caja etiquetada "Coches" contiene varios modelos de coches. Puedes cambiar "Saab" por "Toyota" o añadir un nuevo coche "Audi" a la colección, pero la caja siempre llevará la etiqueta "Coches".

## Soporte del Navegador

La palabra clave `const` no es compatible con Internet Explorer 10 o versiones anteriores.

La siguiente tabla define las primeras versiones de los navegadores con soporte completo para la palabra clave `const`:

| Navegador  | Versión       |
|------------|---------------|
| Chrome     | 49            |
| IE         | 11 / Edge     |
| Firefox    | 36            |
| Safari     | 10            |
| Opera      | 36            |
| Fecha      | Mar, 2016     |

## Asignado al Declarar

Las variables de JavaScript declaradas con `const` deben ser asignadas a un valor cuando se declaran. 

Esto significa que un array declarado con `const` debe ser inicializado cuando se declara.

### Ejemplo
Esto no funcionará:
```javascript
const cars; // ERROR
cars = ["Saab", "Volvo", "BMW"];
```

Los arrays declarados con `var` pueden ser inicializados en cualquier momento.

### Ejemplo
Esto está bien:
```javascript
cars = ["Saab", "Volvo", "BMW"]; // OK
var cars;
```

### Analogía
Piensa en `const` como una orden en un restaurante. Si pides un plato (declara el array), debes especificar lo que quieres (asignar un valor) al momento de hacer el pedido. Si solo haces el pedido sin especificar, el camarero (el compilador) no sabrá qué traer.

## Alcance del Bloque de Const

Un array declarado con `const` tiene **alcance de bloque**. 

Un array declarado en un bloque no es lo mismo que un array declarado fuera del bloque:

### Ejemplo
```javascript
const cars = ["Saab", "Volvo", "BMW"];
// Aquí cars[0] es "Saab"
{
  const cars = ["Toyota", "Volvo", "BMW"];
  // Aquí cars[0] es "Toyota"
}
// Aquí cars[0] es "Saab"
```

Un array declarado con `var` no tiene alcance de bloque:

### Ejemplo
```javascript
var cars = ["Saab", "Volvo", "BMW"];
// Aquí cars[0] es "Saab"
{
  var cars = ["Toyota", "Volvo", "BMW"];
  // Aquí cars[0] es "Toyota"
}
// Aquí cars[0] es "Toyota"
```

### Analogía
Imagina que tienes dos habitaciones (bloques) en una casa. En cada habitación, puedes tener una caja etiquetada "Coches", pero cada habitación puede contener diferentes modelos de coches sin interferir entre sí.

## Redeclarar Arrays

Re-declarar un array declarado con `var` se permite en cualquier lugar de un programa:

### Ejemplo
```javascript
var cars = ["Volvo", "BMW"];   // Permitido
var cars = ["Toyota", "BMW"];  // Permitido
cars = ["Volvo", "Saab"];      // Permitido
```

Re-declarar o reasignar un array a `const`, en el mismo ámbito o en el mismo bloque, no está permitido:

### Ejemplo
```javascript
var cars = ["Volvo", "BMW"];     // Permitido
const cars = ["Volvo", "BMW"];   // No permitido
{
  var cars = ["Volvo", "BMW"];   // Permitido
  const cars = ["Volvo", "BMW"]; // No permitido
}
```

Re-declarar o reasignar un array constante existente, en el mismo ámbito o en el mismo bloque, no está permitido:

### Ejemplo
```javascript
const cars = ["Volvo", "BMW"];   // Permitido
const cars = ["Volvo", "BMW"];   // No permitido
var cars = ["Volvo", "BMW"];     // No permitido
cars = ["Volvo", "BMW"];         // No permitido

{
  const cars = ["Volvo", "BMW"]; // Permitido
  const cars = ["Volvo", "BMW"]; // No permitido
  var cars = ["Volvo", "BMW"];   // No permitido
  cars = ["Volvo", "BMW"];       // No permitido
}
```

Re-declarar un array con `const`, en otro ámbito, o en otro bloque, está permitido:

### Ejemplo
```javascript
const cars = ["Volvo", "BMW"];   // Permitido
{
  const cars = ["Volvo", "BMW"]; // Permitido
}
{
  const cars = ["Volvo", "BMW"]; // Permitido
}
```

## Conclusión

La palabra clave `const` es una herramienta poderosa en JavaScript, especialmente para trabajar con arrays. Al comprender cómo funcionan los arrays constantes y sus límites, puedes escribir un código más limpio y efectivo. ¡Sigue explorando y aprendiendo!

---

# Objetos de Fecha en JavaScript

Los objetos de fecha en JavaScript nos permiten trabajar con fechas. Por ejemplo, un objeto de fecha puede lucir así:

```
Tue Oct 08 2024 15:01:51 GMT-0300 (hora estándar de Argentina)
```

## Ejemplos

```javascript
const d = new Date();
const d = new Date("2022-03-25");
```

**Nota:** Los objetos de fecha son estáticos. El "reloj" no está "corriendo". La hora del ordenador avanza, pero los objetos de fecha no.

## Salida de Fecha en JavaScript

Por defecto, JavaScript usará la zona horaria del navegador y mostrará una fecha como una cadena de texto completa:

```
Tue Oct 08 2024 15:01:51 GMT-0300 (hora estándar de Argentina)
```

Aprenderás mucho más sobre cómo mostrar fechas más adelante en este tutorial.

## Creando Objetos de Fecha

Los objetos de fecha se crean con el constructor `new Date()`. Hay 9 maneras de crear un nuevo objeto de fecha:

1. `new Date()`
2. `new Date(cadena de fecha)`
3. `new Date(año, mes)`
4. `new Date(año, mes, día)`
5. `new Date(año, mes, día, horas)`
6. `new Date(año, mes, día, horas, minutos)`
7. `new Date(año, mes, día, horas, minutos, segundos)`
8. `new Date(año, mes, día, horas, minutos, segundos, milisegundos)`
9. `new Date(milisegundos)`

### `new Date()`

`new Date()` crea un objeto de fecha con la fecha y hora actuales:

```javascript
const d = new Date();
```

### `new Date(cadena de fecha)`

`new Date(cadena de fecha)` crea un objeto de fecha a partir de una cadena de fecha:

```javascript
const d = new Date("13 de octubre de 2014 11:13:00");
const d = new Date("2022-03-25");
```

Los formatos de cadena de fecha se describen en el siguiente capítulo.

### `new Date(año, mes, ...)`

`new Date(año, mes, ...)` crea un objeto de fecha con una fecha y hora especificadas. Se especifican 7 números que representan año, mes, día, hora, minuto, segundo y milisegundo (en ese orden):

```javascript
const d = new Date(2018, 11, 24, 10, 33, 30, 0);
```

**Nota:** JavaScript cuenta los meses de 0 a 11:

- Enero = 0
- Diciembre = 11

Especificar un mes mayor a 11 no resultará en un error, sino que sumará el desbordamiento al año siguiente:

Especificar:

```javascript
const d = new Date(2018, 15, 24, 10, 33, 30);
```

Es lo mismo que:

```javascript
const d = new Date(2019, 3, 24, 10, 33, 30);
```

Especificar un día mayor al máximo no resultará en un error, sino que sumará el desbordamiento al mes siguiente:

Especificar:

```javascript
const d = new Date(2018, 5, 35, 10, 33, 30);
```

Es lo mismo que:

```javascript
const d = new Date(2018, 6, 5, 10, 33, 30);
```

### Usando 6, 4, 3 o 2 Números

- 6 números especifican año, mes, día, hora, minuto y segundo:

```javascript
const d = new Date(2018, 11, 24, 10, 33, 30);
```

- 5 números especifican año, mes, día, hora y minuto:

```javascript
const d = new Date(2018, 11, 24, 10, 33);
```

- 4 números especifican año, mes y día:

```javascript
const d = new Date(2018, 11, 24, 10);
```

- 3 números especifican año, mes y día:

```javascript
const d = new Date(2018, 11, 24);
```

- 2 números especifican año y mes:

```javascript
const d = new Date(2018, 11);
```

No puedes omitir el mes. Si proporcionas solo un parámetro, se interpretará como milisegundos.

```javascript
const d = new Date(2018);
```

### Siglo Anterior

Los años de uno y dos dígitos se interpretarán como 19xx:

```javascript
const d = new Date(99, 11, 24);
const d = new Date(9, 11, 24);
```

## JavaScript Almacena Fechas como Milisegundos

JavaScript almacena fechas como el número de milisegundos desde el 1 de enero de 1970. 

El tiempo cero es 1 de enero de 1970 00:00:00 UTC.

Un día (24 horas) son 86,400,000 milisegundos.

Ahora el tiempo es: `1728410511980` milisegundos desde el 1 de enero de 1970.

### `new Date(milisegundos)`

`new Date(milisegundos)` crea un nuevo objeto de fecha como milisegundos más el tiempo cero:

```javascript
// 1 de enero de 1970 más 100,000,000,000 milisegundos es:
const d = new Date(100000000000);

// 1 de enero de 1970 menos 100,000,000,000 milisegundos es:
const d = new Date(-100000000000);

// 1 de enero de 1970 más 24 horas es:
const d = new Date(24 * 60 * 60 * 1000);
// o
const d = new Date(86400000);

// 1 de enero de 1970 más 0 milisegundos es:
const d = new Date(0);
```

## Métodos de Fecha

Cuando se crea un objeto de fecha, varios métodos permiten operar sobre él. Los métodos de fecha permiten obtener y establecer el año, mes, día, hora, minuto, segundo y milisegundo de los objetos de fecha, utilizando la hora local o UTC (universal, o GMT).

Los métodos de fecha y las zonas horarias se cubren en los siguientes capítulos.

## Mostrando Fechas

JavaScript (por defecto) mostrará las fechas usando el método `toString()`. Esta es una representación en cadena de la fecha, que incluye la zona horaria. El formato está especificado en la especificación de ECMAScript:

```javascript
Tue Oct 08 2024 15:01:51 GMT-0300 (hora estándar de Argentina)
```

Cuando muestras un objeto de fecha en HTML, se convierte automáticamente a una cadena, utilizando el método `toString()`.

```javascript
const d = new Date();
d.toString();
```

El método `toDateString()` convierte una fecha a un formato más legible:

```javascript
const d = new Date();
d.toDateString();
```

El método `toUTCString()` convierte una fecha a una cadena usando el estándar UTC:

```javascript
const d = new Date();
d.toUTCString();
```

El método `toISOString()` convierte una fecha a una cadena usando el estándar ISO:

```javascript
const d = new Date();
d.toISOString();
```

---

# Formatos de Fecha en JavaScript

Cuando trabajamos con fechas en JavaScript, es fundamental entender cómo se representan y se manejan. Imagina que las fechas son como etiquetas de tiempo en una línea de producción: necesitan ser precisas y fáciles de interpretar. A continuación, exploraremos los diferentes formatos de entrada y salida de fechas en JavaScript.

## Entrada de Fechas en JavaScript

Existen tres tipos generales de formatos de entrada de fecha en JavaScript:

| Tipo         | Ejemplo               |
|--------------|----------------------|
| Fecha ISO    | "2015-03-25"         |
| Fecha Corta  | "03/25/2015"         |
| Fecha Larga  | "Mar 25 2015" o "25 Mar 2015" |

### Formato ISO

El formato ISO sigue un estándar estricto en JavaScript, como un manual de instrucciones que todos deben seguir. Es el formato recomendado y se presenta como `YYYY-MM-DD` (Año-Mes-Día). Por ejemplo:

```javascript
const d = new Date("2015-03-25");
```

### Fechas Cortas

Las fechas cortas suelen tener el formato "MM/DD/YYYY". Este formato puede ser más familiar para quienes están acostumbrados a escribir fechas de esta manera:

```javascript
const d = new Date("03/25/2015");
```

### Fechas Largas

Las fechas largas se escriben generalmente con el formato "MMM DD YYYY", donde "MMM" representa el mes en forma abreviada (por ejemplo, "Mar" para marzo):

```javascript
const d = new Date("Mar 25 2015");
```

## Salida de Fechas en JavaScript

Independientemente del formato de entrada, JavaScript por defecto mostrará las fechas en un formato de cadena de texto completo:

```
Tue Oct 08 2024 15:02:46 GMT-0300 (hora estándar de Argentina)
```

### Fechas ISO en JavaScript

ISO 8601 es el estándar internacional para la representación de fechas y horas. Utilizar este formato asegura que tus fechas sean interpretadas de manera consistente. 

#### Ejemplo (Fecha Completa)

```javascript
const d = new Date("2015-03-25");
```

Ten en cuenta que la fecha computada será relativa a tu zona horaria. Dependiendo de tu ubicación, el resultado podría variar entre el 24 y el 25 de marzo.

#### Fechas ISO (Año y Mes)

Puedes escribir fechas ISO sin especificar el día:

```javascript
const d = new Date("2015-03");
```

En este caso, el resultado podría variar entre el 28 de febrero y el 1 de marzo, dependiendo de la zona horaria.

#### Fechas ISO (Solo Año)

También es posible escribir fechas ISO solo con el año:

```javascript
const d = new Date("2015");
```

Esto puede resultar en fechas que oscilan entre el 31 de diciembre de 2014 y el 1 de enero de 2015.

#### Fechas ISO (Fecha-Hora)

Las fechas ISO pueden incluir horas, minutos y segundos:

```javascript
const d = new Date("2015-03-25T12:00:00Z");
```

En este formato, la "T" separa la fecha y la hora, y la "Z" indica que es hora UTC.

Si deseas ajustar el tiempo relativo a UTC, puedes eliminar la "Z" y agregar `+HH:MM` o `-HH:MM`:

```javascript
const d = new Date("2015-03-25T12:00:00-06:30");
```

### Zonas Horarias

Al establecer una fecha sin especificar la zona horaria, JavaScript utilizará la zona horaria del navegador. Por ejemplo, si un usuario navega desde los EE. UU. Central, una fecha/hora creada en GMT se convertirá a CDT.

## Fechas Cortas y Advertencias

Las fechas cortas se escriben con la sintaxis "MM/DD/YYYY":

```javascript
const d = new Date("03/25/2015");
```

**Advertencias:**
- En algunos navegadores, los meses o días sin ceros a la izquierda pueden causar errores:

```javascript
const d = new Date("2015-3-25"); // Puede fallar
```

- La interpretación de "YYYY/MM/DD" es indefinida, y algunos navegadores pueden adivinar el formato o devolver NaN:

```javascript
const d = new Date("2015/03/25"); // Indefinido
```

- La interpretación de "DD-MM-YYYY" también es indefinida:

```javascript
const d = new Date("25-03-2015"); // Indefinido
```

## Fechas Largas

Las fechas largas se suelen escribir con la sintaxis "MMM DD YYYY":

```javascript
const d = new Date("Mar 25 2015");
```

El mes y el día pueden estar en cualquier orden:

```javascript
const d = new Date("25 Mar 2015");
```

El mes puede escribirse completo (January) o abreviado (Jan):

```javascript
const d = new Date("January 25 2015");
const d = new Date("Jan 25 2015");
```

Las comas son ignoradas y los nombres son insensibles a mayúsculas y minúsculas:

```javascript
const d = new Date("JANUARY, 25, 2015");
```

## Entrada de Fecha - Analizando Fechas

Si tienes una cadena de fecha válida, puedes usar el método `Date.parse()` para convertirla en milisegundos. Esto es como usar un cronómetro que cuenta desde un momento específico (1 de enero de 1970).

```javascript
let msec = Date.parse("March 21, 2012");
```

Luego, puedes utilizar el número de milisegundos para convertirlo en un objeto de fecha:

```javascript
const d = new Date(msec);
```

## Conclusión

Entender los formatos de fecha en JavaScript es esencial para trabajar eficazmente con datos temporales. Las analogías y los conceptos técnicos aquí presentados son herramientas valiosas en tu camino para convertirte en un experto frontend.

---

# Métodos para Obtener Fechas en JavaScript

## El Constructor `new Date()`
En JavaScript, los objetos de fecha se crean utilizando `new Date()`.

Cuando usas `new Date()`, te devuelve un objeto de fecha con la fecha y hora actual.

### Ejemplo:
```javascript
const date = new Date();
```

### **Analogía:**
Imagina que `new Date()` es como sacar una foto del reloj en tu pared. En el momento en que la tomas, captura la hora exacta en ese instante. Pero, la foto no cambia; no se mueve. Solo refleja ese momento específico.

## Métodos para Obtener Datos de Fechas
Estos métodos permiten extraer partes específicas de una fecha, como el año, mes, día, etc.

| Método               | Descripción                                                  |
|----------------------|--------------------------------------------------------------|
| `getFullYear()`       | Obtiene el año como un número de cuatro dígitos (yyyy).       |
| `getMonth()`          | Obtiene el mes como un número (0-11).                        |
| `getDate()`           | Obtiene el día como un número (1-31).                        |
| `getDay()`            | Obtiene el día de la semana como un número (0-6).            |
| `getHours()`          | Obtiene la hora (0-23).                                      |
| `getMinutes()`        | Obtiene los minutos (0-59).                                  |
| `getSeconds()`        | Obtiene los segundos (0-59).                                 |
| `getMilliseconds()`   | Obtiene los milisegundos (0-999).                            |
| `getTime()`           | Obtiene el tiempo en milisegundos desde el 1 de enero de 1970.|

### Nota 1:
Los métodos `get` devuelven la hora local (de tu zona horaria).

### Nota 2:
El tiempo en un objeto de fecha es estático. Es decir, una vez que creas la fecha, no cambia automáticamente con el tiempo real. La "foto" del reloj no se mueve sola.

### **Analogía:**
Es como si hubieras creado una copia de la fecha y hora en un papel. Ese papel no cambia por sí solo, aunque el tiempo real sí siga avanzando.

## El Método `getFullYear()`
El método `getFullYear()` devuelve el año de una fecha como un número de cuatro dígitos.

### Ejemplo:
```javascript
const d = new Date("2021-03-25");
console.log(d.getFullYear()); // 2021
```

### Advertencia:
El método `getYear()` es obsoleto y puede dar resultados incorrectos. Evita usarlo.

## El Método `getMonth()`
El método `getMonth()` devuelve el mes de una fecha como un número (0-11).

### Nota:
En JavaScript, el mes de enero es 0, febrero es 1, y así sucesivamente, hasta diciembre, que es 11.

### Ejemplo:
```javascript
const d = new Date("2021-03-25");
console.log(d.getMonth()); // 2 (Marzo, ya que comienza desde 0)
```

### **Analogía:**
Imagina que los meses son cajones en una cajonera. El primer cajón (Enero) está etiquetado como 0, el segundo (Febrero) es el 1, y así hasta llegar al último cajón, que es diciembre (11).

Para facilitar, puedes usar una lista de nombres de meses y obtener el nombre en lugar del número:

```javascript
const months = ["Enero", "Febrero", "Marzo", "Abril", "Mayo", "Junio", "Julio", "Agosto", "Septiembre", "Octubre", "Noviembre", "Diciembre"];
const d = new Date("2021-03-25");
let month = months[d.getMonth()];
console.log(month); // "Marzo"
```

## El Método `getDate()`
El método `getDate()` devuelve el día del mes (1-31).

### Ejemplo:
```javascript
const d = new Date("2021-03-25");
console.log(d.getDate()); // 25
```

## El Método `getHours()`
El método `getHours()` devuelve la hora de una fecha como un número (0-23).

### Ejemplo:
```javascript
const d = new Date("2021-03-25T10:20:30");
console.log(d.getHours()); // 10
```

## El Método `getMinutes()`
El método `getMinutes()` devuelve los minutos de una fecha (0-59).

### Ejemplo:
```javascript
const d = new Date("2021-03-25T10:20:30");
console.log(d.getMinutes()); // 20
```

## El Método `getSeconds()`
El método `getSeconds()` devuelve los segundos de una fecha (0-59).

### Ejemplo:
```javascript
const d = new Date("2021-03-25T10:20:30");
console.log(d.getSeconds()); // 30
```

## El Método `getMilliseconds()`
El método `getMilliseconds()` devuelve los milisegundos de una fecha (0-999).

### Ejemplo:
```javascript
const d = new Date("2021-03-25T10:20:30.123");
console.log(d.getMilliseconds()); // 123
```

## El Método `getDay()`
El método `getDay()` devuelve el día de la semana como un número (0-6), donde 0 es domingo y 6 es sábado.

### Ejemplo:
```javascript
const d = new Date("2021-03-25");
console.log(d.getDay()); // 4 (Jueves)
```

Para convertir el número en el nombre del día de la semana, puedes usar una lista:

```javascript
const days = ["Domingo", "Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado"];
const d = new Date("2021-03-25");
let day = days[d.getDay()];
console.log(day); // "Jueves"
```

## El Método `getTime()`
El método `getTime()` devuelve el tiempo en milisegundos desde el 1 de enero de 1970.

### Ejemplo:
```javascript
const d = new Date("1970-01-01");
console.log(d.getTime()); // 0
```

## El Método `Date.now()`
El método `Date.now()` devuelve la cantidad de milisegundos desde el 1 de enero de 1970 hasta el momento actual.

### Ejemplo:
```javascript
let ms = Date.now();
console.log(ms);
```

Este método es estático, lo que significa que no puedes usarlo en una fecha específica, solo como `Date.now()`.

## Métodos UTC
Estos métodos son similares a los métodos `get`, pero devuelven la fecha y hora en tiempo universal (UTC), en lugar de la hora local.

| Método              | Equivalente      | Descripción                        |
|---------------------|------------------|------------------------------------|
| `getUTCDate()`       | `getDate()`      | Devuelve el día en UTC             |
| `getUTCFullYear()`   | `getFullYear()`  | Devuelve el año en UTC             |
| `getUTCMonth()`      | `getMonth()`     | Devuelve el mes en UTC             |
| `getUTCDay()`        | `getDay()`       | Devuelve el día de la semana en UTC|
| `getUTCHours()`      | `getHours()`     | Devuelve la hora en UTC            |
| `getUTCMinutes()`    | `getMinutes()`   | Devuelve los minutos en UTC        |
| `getUTCSeconds()`    | `getSeconds()`   | Devuelve los segundos en UTC       |
| `getUTCMilliseconds()`| `getMilliseconds()` | Devuelve los milisegundos en UTC|

### **Analogía:**
Imagina que UTC es como la hora estándar que usan en una conferencia internacional, sin importar el lugar donde estés. Todos sincronizan su reloj a esa hora para estar en la misma página.

## El Método `getTimezoneOffset()`
Este método devuelve la diferencia (en minutos) entre la hora local y la hora UTC.

### Ejemplo:
```javascript
let diff = d.getTimezoneOffset();
```

---

# Métodos para Establecer Fechas en JavaScript

En JavaScript, puedes utilizar varios métodos para establecer partes específicas de una fecha, como el año, mes, día, hora, minutos, segundos, y milisegundos. Estos métodos te permiten modificar una fecha según tus necesidades.

## Métodos para Establecer Fechas
Los métodos para **"establecer"** (`set`) en JavaScript permiten modificar partes específicas de un objeto de fecha:

| Método               | Descripción                                         |
|----------------------|-----------------------------------------------------|
| `setDate()`          | Establece el día del mes (1-31)                     |
| `setFullYear()`      | Establece el año (opcionalmente el mes y día)       |
| `setHours()`         | Establece la hora (0-23)                            |
| `setMilliseconds()`  | Establece los milisegundos (0-999)                  |
| `setMinutes()`       | Establece los minutos (0-59)                        |
| `setMonth()`         | Establece el mes (0-11)                             |
| `setSeconds()`       | Establece los segundos (0-59)                       |
| `setTime()`          | Establece el tiempo en milisegundos desde el 1 de enero de 1970 |

### **Analogía:**
Imagina que tienes una agenda de papel y puedes cambiar cualquier detalle de una cita que ya habías anotado: el día, la hora, el mes o incluso el año. Los métodos `set` en JavaScript hacen lo mismo, te permiten modificar partes específicas de una fecha existente.

## El Método `setFullYear()`
El método `setFullYear()` establece el año de un objeto de fecha.

### Ejemplo:
```javascript
const d = new Date();
d.setFullYear(2020);
```

Este código cambia el año de la fecha actual a 2020.

### **Analogía:**
Es como si agarraras una página de tu calendario y, en lugar de tachar toda la fecha, solo cambias el año que está escrito, dejando el resto intacto. En este caso, cambias el año a 2020 pero el mes y el día no se tocan.

Este método también puede establecer opcionalmente el mes y el día:

### Ejemplo:
```javascript
const d = new Date();
d.setFullYear(2020, 11, 3);  // Año 2020, Diciembre 3
```

### **Analogía Extendida:**
Ahora no solo cambias el año, sino que también decides mover la fecha a un mes específico (en este caso diciembre, porque los meses empiezan desde 0) y un día específico (el 3). Es como ajustar varios detalles de tu cita en la agenda, no solo el año.

## El Método `setMonth()`
El método `setMonth()` establece el mes de un objeto de fecha.

### Ejemplo:
```javascript
const d = new Date();
d.setMonth(11);  // Diciembre, porque los meses empiezan desde 0
```

### **Analogía:**
Piensa que estás en una hoja de tu calendario y quieres cambiar el mes de tu cita. Cambias el número del mes, como si cambiaras de la página de noviembre a diciembre. Recuerda que en JavaScript, los meses comienzan desde 0, por lo que 0 es enero y 11 es diciembre.

## El Método `setDate()`
El método `setDate()` establece el día del mes.

### Ejemplo:
```javascript
const d = new Date();
d.setDate(15);  // Establece el día 15 del mes actual
```

### **Analogía:**
Imagina que ya tienes una cita en tu calendario, pero decides moverla a otro día del mismo mes. Es como si estuvieras borrando el día original y anotaras el nuevo día, por ejemplo, del 1 al 15.

También puedes usar este método para **agregar días a una fecha**:

### Ejemplo:
```javascript
const d = new Date();
d.setDate(d.getDate() + 50);  // Añade 50 días a la fecha actual
```

### **Analogía:**
Es como si en lugar de cambiar una cita a una fecha exacta, decidieras moverla 50 días más adelante, sin importar el mes. Si la fecha se mueve a otro mes o año, JavaScript ajusta eso automáticamente, como si el calendario se deslizara correctamente hasta la nueva fecha.

## El Método `setHours()`
El método `setHours()` establece las horas de un objeto de fecha.

### Ejemplo:
```javascript
const d = new Date();
d.setHours(22);  // Establece las 10 PM
```

### **Analogía:**
Esto es como cambiar la hora de una reunión en tu agenda. Decides moverla de la mañana a la noche y escribes las 10 PM.

## El Método `setMinutes()`
El método `setMinutes()` establece los minutos.

### Ejemplo:
```javascript
const d = new Date();
d.setMinutes(30);  // Establece los minutos en 30
```

### **Analogía:**
Es como si ajustaras los minutos de una cita. Por ejemplo, en lugar de que sea a las 10:00, decides que sea a las 10:30.

## El Método `setSeconds()`
El método `setSeconds()` establece los segundos de un objeto de fecha.

### Ejemplo:
```javascript
const d = new Date();
d.setSeconds(30);  // Establece los segundos en 30
```

### **Analogía:**
Si fueras extremadamente preciso con tu agenda, podrías incluso ajustar los segundos exactos en los que ocurren las cosas. En este caso, decides que algo ocurrirá a los 30 segundos del minuto.

## Comparar Fechas
Puedes comparar fácilmente fechas en JavaScript para ver cuál es anterior o posterior.

### Ejemplo:
```javascript
let text = "";
const today = new Date();
const someday = new Date();
someday.setFullYear(2100, 0, 14);  // Establece la fecha en 14 de enero de 2100

if (someday > today) {
  text = "Hoy es antes del 14 de enero de 2100.";
} else {
  text = "Hoy es después del 14 de enero de 2100.";
}
```

Este código compara la fecha de hoy con el 14 de enero de 2100 y te dice si la fecha de hoy es anterior o posterior a esa fecha.

### **Analogía:**
Imagina que tienes dos citas en tu calendario y quieres saber cuál ocurre primero. Simplemente comparas las dos fechas y decides cuál es anterior. JavaScript te permite hacer exactamente eso, comparando dos objetos de fecha para ver cuál es "más temprano" o "más tarde".

## Nota sobre los Meses en JavaScript
Recuerda que JavaScript cuenta los meses del 0 al 11: enero es 0 y diciembre es 11. Esto es algo importante a tener en cuenta cuando trabajas con fechas.

### **Analogía:**
Es como si tuvieras una lista de casilleros donde el primer casillero es el 0, no el 1. Entonces, si estás buscando "enero", en lugar de ir al casillero 1, tienes que buscar en el casillero 0.

---

# Entendiendo el Objeto Math en JavaScript

El objeto `Math` en JavaScript nos permite realizar tareas matemáticas sobre números de una forma eficiente y directa. Sin embargo, a diferencia de otros objetos en JavaScript, `Math` no necesita ser "construido" o instanciado. Es como una calculadora siempre lista en tu escritorio, que solo tienes que usar sin tener que encenderla ni programarla.

## ¿Cómo funciona el Objeto Math?

Imagina que `Math` es como una caja de herramientas matemáticas. Todas las herramientas (funciones) están listas para usarse, no necesitas crear la caja, simplemente abres la tapa y usas lo que necesitas.

### Ejemplo simple
```javascript
Math.PI; // Devuelve el valor de PI
```

### Propiedades de Math
Las propiedades en `Math` son como las reglas universales de las matemáticas que ya conocemos, y JavaScript nos las entrega listas para usar.

```javascript
Math.E        // Número de Euler
Math.PI       // Valor de PI
Math.SQRT2    // Raíz cuadrada de 2
Math.SQRT1_2  // Raíz cuadrada de 1/2
Math.LN2      // Logaritmo natural de 2
Math.LN10     // Logaritmo natural de 10
Math.LOG2E    // Logaritmo en base 2 de E
Math.LOG10E   // Logaritmo en base 10 de E
```

### Métodos de Math
Las herramientas en esta caja también incluyen métodos para realizar operaciones con números, como redondear o sacar raíces. Aquí tienes algunas de las más útiles.

#### Convertir un Número a Entero
Imagina que tienes una cantidad de monedas y necesitas contar cuántas hay de forma más aproximada (sin decimales). JavaScript ofrece varios métodos para redondear números a enteros, dependiendo de si quieres redondear hacia arriba, hacia abajo o al más cercano.

1. **`Math.round(x)`** - Redondea al entero más cercano (sube o baja según el decimal):
    ```javascript
    Math.round(4.6); // 5
    Math.round(4.4); // 4
    ```

2. **`Math.ceil(x)`** - Redondea siempre hacia arriba:
    ```javascript
    Math.ceil(4.2);  // 5
    Math.ceil(-4.2); // -4
    ```

3. **`Math.floor(x)`** - Redondea siempre hacia abajo:
    ```javascript
    Math.floor(4.9);  // 4
    Math.floor(-4.2); // -5
    ```

4. **`Math.trunc(x)`** - Corta la parte decimal, devolviendo solo la parte entera:
    ```javascript
    Math.trunc(4.9);  // 4
    Math.trunc(-4.9); // -4
    ```

#### ¿Qué Signo Tiene un Número?
A veces queremos saber si un número es positivo, negativo o cero. Imagina que estás viendo la temperatura y quieres saber si hace calor, frío o si estás en el punto justo:

```javascript
Math.sign(4);  // 1 (positivo)
Math.sign(-4); // -1 (negativo)
Math.sign(0);  // 0 (ni frío ni calor)
```

#### Elevar a una Potencia
¿Alguna vez quisiste calcular una potencia, como en la fórmula del área de un cuadrado? El método `Math.pow(x, y)` nos permite elevar un número `x` a la potencia `y`.

```javascript
Math.pow(2, 3); // 8 (2 elevado a la 3)
```

#### Raíz Cuadrada
Si quieres encontrar la raíz cuadrada de un número (por ejemplo, para calcular la diagonal de un cuadrado), puedes usar `Math.sqrt(x)`.

```javascript
Math.sqrt(64); // 8
```

#### Valor Absoluto
Si necesitas deshacerte del signo negativo de un número (como cuando restas distancias y solo te interesa la cantidad, no la dirección), el método `Math.abs(x)` te devuelve siempre el valor positivo.

```javascript
Math.abs(-4.7); // 4.7
```

### Trigonometría Básica
`Math` también ofrece funciones trigonométricas. Aunque no es algo que usaremos todos los días, puede ser útil si trabajas con gráficos o ángulos.

1. **`Math.sin(x)`** - Devuelve el seno del ángulo `x` en radianes. Si prefieres trabajar con grados, debes convertir los grados a radianes:

   ```javascript
   Math.sin(90 * Math.PI / 180); // 1 (seno de 90 grados)
   ```

2. **`Math.cos(x)`** - Devuelve el coseno del ángulo `x` en radianes:

   ```javascript
   Math.cos(0 * Math.PI / 180); // 1 (coseno de 0 grados)
   ```

### Mínimos y Máximos
Si necesitas encontrar el valor más pequeño o más grande en una lista de números, puedes usar `Math.min()` o `Math.max()`.

```javascript
Math.min(0, 150, 30, 20, -8, -200); // -200
Math.max(0, 150, 30, 20, -8, -200); // 150
```

### Generar un Número Aleatorio
Finalmente, si quieres generar un número aleatorio entre 0 y 1 (sin incluir el 1), puedes usar `Math.random()`. Este método es útil para simulaciones o para juegos donde necesitas crear algo al azar.

```javascript
Math.random(); // Ejemplo: 0.5687
```

## Resumen
El objeto `Math` en JavaScript es una caja de herramientas repleta de funciones matemáticas listas para ser usadas. No necesitas crear instancias ni preocuparte por detalles técnicos complicados, simplemente puedes usar las herramientas cuando las necesites. Con estas funciones, puedes hacer de todo, desde redondear números hasta generar valores aleatorios o realizar operaciones trigonométricas.

---

# JavaScript: Generación de Números Aleatorios

## ¿Qué es `Math.random()`? 

Imagina que tienes una caja llena de bolitas numeradas entre el 0 y el 1. Cada vez que metes la mano en la caja y sacas una bolita, obtienes un número al azar. Ese número siempre será mayor o igual que 0, pero menor que 1 (es decir, **nunca llegarás a sacar un 1 exacto**). En JavaScript, esta "caja" es la función **`Math.random()`**.

### Ejemplo:

```javascript
// Retorna un número aleatorio entre 0 y 1 (sin incluir el 1)
Math.random();
```

### Concepto técnico:
- **`Math.random()`** genera un número decimal (punto flotante) en el rango [0, 1), es decir, desde 0 (incluido) hasta 1 (excluido).
- Cada vez que llamas a **`Math.random()`**, obtienes un valor distinto dentro de ese rango.

## Números Enteros Aleatorios

Aunque **`Math.random()`** te da un número decimal, lo que muchas veces necesitamos en programación son **números enteros** (sin decimales), como por ejemplo, si queremos simular el lanzamiento de un dado (que solo puede mostrar números enteros del 1 al 6). 

Para convertir ese número decimal en un número entero, combinamos **`Math.random()`** con **`Math.floor()`**.

### Analogía:
Piensa en **`Math.floor()`** como una especie de tijera que corta los decimales. Si tienes el número 4.7, **`Math.floor()`** lo convierte en 4, eliminando la parte decimal sin redondear.

### Ejemplo: Números enteros del 0 al 9

```javascript
// Retorna un número entero aleatorio entre 0 y 9
Math.floor(Math.random() * 10);
```

Aquí, estamos multiplicando el número aleatorio (que está entre 0 y 1) por 10 para llevar el rango de números a [0, 10). Luego, **`Math.floor()`** elimina los decimales, dándonos un número entre 0 y 9.

### Concepto técnico:
- **`Math.floor()`** redondea el número hacia abajo al entero más cercano.
- Al multiplicar **`Math.random()`** por un número, expandes el rango. Por ejemplo, si multiplicas por 10, ahora el rango de salida será entre 0 y 9 (ya que **`Math.floor()`** corta los decimales).

## Más Ejemplos de Números Enteros Aleatorios

- **Número entero entre 0 y 10**:
  ```javascript
  Math.floor(Math.random() * 11);
  ```
  Este código genera un número entre 0 y 10 (incluyendo ambos).

- **Número entero entre 0 y 99**:
  ```javascript
  Math.floor(Math.random() * 100);
  ```

- **Número entero entre 1 y 100**:
  ```javascript
  Math.floor(Math.random() * 100) + 1;
  ```

### Explicación:
En los ejemplos anteriores, multiplicamos **`Math.random()`** por el rango que necesitamos. Para obtener números enteros desde 1, simplemente sumamos 1 al resultado.

### Analogía:
Imagina que tienes una ruleta con 100 números, pero la primera posición es 0. Si quieres que el primer número sea 1, solo tienes que mover los números un lugar hacia adelante. Eso es lo que hacemos al sumar 1 en la última línea del código.

## Creando una Función para Números Aleatorios Personalizados

A veces, necesitarás generar un número aleatorio dentro de un rango específico. En lugar de repetir el mismo código cada vez, es mejor crear una **función reutilizable**.

### Ejemplo:

```javascript
function getRndInteger(min, max) {
  return Math.floor(Math.random() * (max - min)) + min;
}
```

### ¿Qué hace esta función?

- **`min`**: El valor mínimo que quieres obtener.
- **`max`**: El valor máximo que quieres obtener (sin incluirlo).
- **`Math.random()`**: Genera un número entre 0 y 1.
- **Multiplicación**: Al multiplicar por **`(max - min)`**, expandimos el rango entre **`min`** y **`max`**.
- **Suma**: Al sumar **`min`**, desplazamos el rango para que el valor más bajo sea **`min`**.

### Ejemplo con la función:

```javascript
// Retorna un número entre 5 y 15 (excluyendo 15)
getRndInteger(5, 15);
```

### Función para incluir el valor máximo

Si quieres que tanto el valor mínimo como el máximo estén incluidos en el rango de posibles resultados, puedes ajustar la función:

```javascript
function getRndIntegerInclusive(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}
```

### Explicación técnica:

- Sumamos **1** al cálculo de **`(max - min)`** para asegurarnos de que el número máximo esté incluido en el resultado.
  
### Ejemplo:

```javascript
// Retorna un número entre 1 y 100, incluyendo ambos extremos
getRndIntegerInclusive(1, 100);
```

## Resumen

- **`Math.random()`** es una herramienta poderosa para generar números aleatorios entre 0 y 1.
- Al combinar **`Math.random()`** con **`Math.floor()`**, podemos generar números enteros en cualquier rango que necesitemos.
- Crear funciones reutilizables para generar números aleatorios dentro de rangos específicos es una buena práctica y te ahorra tiempo al escribir código.

---

# Booleans en JavaScript

## ¿Qué es un Boolean en JavaScript?

Imagina que tienes un interruptor de luz en la pared. Solo tiene dos posiciones posibles: encendido (ON) o apagado (OFF). En programación, a menudo necesitamos un tipo de dato que solo pueda tener dos valores posibles, como este interruptor. En JavaScript, esto se llama **Boolean**, y los dos valores que puede tomar son `true` (verdadero) o `false` (falso).

### Valores Booleanos
Al programar, hay muchas situaciones donde solo queremos saber si algo es `sí` o `no`, `verdadero` o `falso`, como:
- ¿Está el interruptor encendido?
- ¿Es mayor de 18 años?
- ¿El valor es mayor que 10?

En estos casos, usamos un **Booleano**, que solo puede ser `true` o `false`.

### Ejemplo:

```javascript
// Devuelve true, ya que 10 es mayor que 9
Boolean(10 > 9);
```

Incluso más simple, ni siquiera necesitas la función `Boolean()`. Puedes directamente hacer una comparación:

```javascript
// Devuelve true
10 > 9;
```

## Comparaciones y Condiciones

Los valores booleanos son la base de las comparaciones y condiciones en JavaScript. Aquí algunos ejemplos comunes:

| Operador  | Descripción           | Ejemplo                  |
|-----------|-----------------------|--------------------------|
| ==        | Igual a               | `if (dia == "Lunes")`    |
| >         | Mayor que             | `if (sueldo > 9000)`     |
| <         | Menor que             | `if (edad < 18)`         |

### Concepto técnico:
Cuando haces comparaciones como `10 > 9`, JavaScript devuelve un valor Booleano (`true` o `false`), que luego puedes usar en declaraciones condicionales como `if`.

## Todo lo que tiene un "valor" es verdadero

### Analogía:
Piensa en cualquier número o palabra como si fueran objetos físicos. Mientras tengas algo en tus manos, sea lo que sea, eso cuenta como "verdadero" (tienes algo). En JavaScript, cualquier cosa que no esté vacía o sea `0` se considera **true**.

### Ejemplos de valores verdaderos (`true`):

```javascript
Boolean(100);      // true
Boolean(3.14);     // true
Boolean(-15);      // true
Boolean("Hola");   // true
Boolean("false");  // true
Boolean(7 + 1);    // true
```

- Cualquier número que no sea 0 es `true`, incluso números negativos.
- Cualquier cadena (string) no vacía, como `"Hola"` o incluso `"false"`, también es `true`.

## Todo lo que "no tiene valor" es falso

### Analogía:
Si tus manos están vacías, eso significa "falso". En JavaScript, ciertos valores son considerados "vacíos" o **falsos**.

### Ejemplos de valores falsos (`false`):

```javascript
Boolean(0);          // false
Boolean(-0);         // false
Boolean("");         // false
Boolean(undefined);  // false
Boolean(null);       // false
Boolean(false);      // false
Boolean(NaN);        // false
```

- El número `0`, el string vacío `""`, `undefined`, `null`, `false`, y `NaN` (Not a Number) son todos considerados **falsos**.

### Concepto técnico:
Cualquier valor que se considere "vacío" o sin valor será evaluado como `false`. Esto es útil en condiciones donde solo te interesa si hay algo o no, como verificar si un usuario ha introducido datos en un formulario.

## Booleans en JavaScript como Objetos

Normalmente, los valores booleanos en JavaScript son **primitivos**. Esto significa que son simples valores como `true` o `false` creados directamente, sin mucha complejidad.

### Ejemplo:

```javascript
let x = false;  // Booleano primitivo
```

Sin embargo, también puedes crear booleans como **objetos** utilizando la palabra clave `new`:

```javascript
let y = new Boolean(false);  // Booleano como objeto
```

### ¿Cuál es la diferencia?

- **`typeof x`** devolverá `"boolean"` porque `x` es un valor booleano primitivo.
- **`typeof y`** devolverá `"object"` porque `y` es un objeto creado con `new Boolean()`.

### Advertencia: ¡No uses booleans como objetos!

- Crear booleans como objetos (con `new`) complica el código y hace que sea más lento.
- Además, puede generar resultados inesperados.

### Ejemplo de comportamiento inesperado:

Cuando comparas un booleano primitivo con un booleano objeto usando el operador `==`, parecen iguales:

```javascript
let x = false;
let y = new Boolean(false);
x == y;  // true
```

Pero cuando usas el operador `===`, que compara tanto el valor como el tipo, no son iguales:

```javascript
x === y;  // false
```

### Concepto técnico:
El operador `==` compara solo el valor, pero el operador `===` compara tanto el valor como el tipo de dato. Como `x` es un booleano primitivo y `y` es un objeto, `x === y` devuelve `false`.

### Resumen:

- En JavaScript, los booleans representan dos valores: `true` o `false`.
- Los valores que "tienen algo" se consideran `true` (como números o cadenas no vacías).
- Los valores "vacíos" se consideran `false` (como `0`, `""`, `undefined`, `null`, etc.).
- No utilices booleans como objetos con `new Boolean()` porque complican el código y generan comportamientos inesperados.

---

# Operadores de Comparación y Lógicos en JavaScript

Los operadores de comparación y lógicos se utilizan para evaluar condiciones y determinar si son verdaderas o falsas.

## Operadores de Comparación

Los operadores de comparación se utilizan en declaraciones lógicas para determinar la igualdad o diferencia entre variables o valores.

### Tabla de Operadores de Comparación

Dado que `x = 5`, la siguiente tabla explica los operadores de comparación:

| Operador | Descripción                           | Comparando          | Retorna | Prueba |
|----------|---------------------------------------|---------------------|---------|--------|
| `==`     | igual a                               | `x == 8`            | false   |        |
|          |                                       | `x == 5`            | true    |        |
|          |                                       | `x == "5"`          | true    |        |
| `===`    | valor igual y tipo igual              | `x === 5`           | true    |        |
|          |                                       | `x === "5"`         | false   |        |
| `!=`     | no igual                              | `x != 8`            | true    |        |
| `!==`    | valor no igual o tipo no igual        | `x !== 5`           | false   |        |
|          |                                       | `x !== "5"`         | true    |        |
|          |                                       | `x !== 8`           | true    |        |
| `>`      | mayor que                             | `x > 8`             | false   |        |
| `<`      | menor que                             | `x < 8`             | true    |        |
| `>=`     | mayor o igual que                     | `x >= 8`            | false   |        |
| `<=`     | menor o igual que                     | `x <= 8`            | true    |        |

### Cómo se Puede Usar

Los operadores de comparación se pueden usar en declaraciones condicionales para comparar valores y tomar acciones dependiendo del resultado. Por ejemplo:

```javascript
if (edad < 18) texto = "Demasiado joven para comprar alcohol";
```

Aprenderás más sobre el uso de declaraciones condicionales en el próximo capítulo de este tutorial.

## Operadores Lógicos

Los operadores lógicos se utilizan para determinar la lógica entre variables o valores.

### Tabla de Operadores Lógicos

Dado que `x = 6` y `y = 3`, la siguiente tabla explica los operadores lógicos:

| Operador | Descripción | Ejemplo                             | Prueba |
|----------|-------------|-------------------------------------|--------|
| `&&`     | y           | `(x < 10 && y > 1)` es verdadero   |        |
| `||`     | o           | `(x == 5 || y == 5)` es falso      |        |
| `!`      | no          | `!(x == y)` es verdadero            |        |

### Analogía:
Imagina que tienes una caja con dos compartimentos. Si quieres que ambos compartimentos contengan algo para que la caja se considere "llena", usarías el operador `&&` (y). Si solo uno de los compartimentos necesita contener algo, usarías `||` (o). Y si quieres comprobar que un compartimento está vacío, usarías `!` (no).

## Operador Condicional (Ternario)

JavaScript también contiene un operador condicional que asigna un valor a una variable basado en una condición.

### Sintaxis

```javascript
nombreVariable = (condición) ? valor1 : valor2;
```

### Ejemplo

```javascript
let votable = (edad < 18) ? "Demasiado joven" : "Suficientemente mayor";
```

Si la variable `edad` es un valor inferior a 18, el valor de la variable `votable` será "Demasiado joven"; de lo contrario, el valor de `votable` será "Suficientemente mayor".

## Comparando Diferentes Tipos

Comparar datos de diferentes tipos puede dar resultados inesperados.

Cuando se compara una cadena con un número, JavaScript convertirá la cadena a un número durante la comparación. Una cadena vacía se convierte en 0. Una cadena no numérica se convierte en NaN (No es un número), que siempre es falso.

### Ejemplos de Comparaciones

| Caso                | Valor | Prueba   |
|---------------------|-------|----------|
| `2 < 12`            | true  |          |
| `2 < "12"`          | true  |          |
| `2 < "John"`        | false |          |
| `2 > "John"`        | false |          |
| `2 == "John"`       | false |          |
| `"2" < "12"`        | false |          |
| `"2" > "12"`        | true  |          |
| `"2" == "12"`       | false |          |

Al comparar dos cadenas, "2" será mayor que "12" porque (alfabéticamente) 1 es menor que 2.

Para obtener un resultado adecuado, las variables deben ser convertidas al tipo adecuado antes de la comparación:

```javascript
edad = Number(edad);
if (isNaN(edad)) {
  votable = "La entrada no es un número";
} else {
  votable = (edad < 18) ? "Demasiado joven" : "Suficientemente mayor";
}
```

## El Operador de Coalescencia Nula (??)

El operador `??` devuelve el primer argumento si no es nulo (null o undefined). De lo contrario, devuelve el segundo argumento.

### Ejemplo

```javascript
let nombre = null;
let texto = "faltante";
let resultado = nombre ?? texto;
```

El operador de coalescencia es compatible con todos los navegadores desde marzo de 2020.

| Navegador  | Versión  |
|------------|----------|
| Chrome     | 80       |
| Edge       | 80       |
| Firefox    | 72       |
| Safari     | 13.1     |
| Opera      | 67       |

## El Operador de Encadenamiento Opcional (?.)

El operador `?.` devuelve undefined si un objeto es undefined o null (en lugar de lanzar un error).

### Ejemplo

```javascript
// Crear un objeto:
const auto = {tipo: "Fiat", modelo: "500", color: "blanco"};
// Pedir el nombre del auto:
document.getElementById("demo").innerHTML = auto?.nombre;
```

El operador de encadenamiento opcional es compatible con todos los navegadores desde marzo de 2020.

| Navegador  | Versión  |
|------------|----------|
| Chrome     | 80       |
| Edge       | 80       |
| Firefox    | 72       |
| Safari     | 13.1     |
| Opera      | 67       |

---

# JavaScript: if, else y else if

Las declaraciones condicionales se utilizan para realizar diferentes acciones basadas en diferentes condiciones.

## Declaraciones Condicionales

Muy a menudo, al escribir código, deseas realizar diferentes acciones según diferentes decisiones.

Puedes utilizar declaraciones condicionales en tu código para hacer esto.

En JavaScript, tenemos las siguientes declaraciones condicionales:

- **if**: Especifica un bloque de código que se ejecutará si una condición especificada es verdadera.
- **else**: Especifica un bloque de código que se ejecutará si la misma condición es falsa.
- **else if**: Especifica una nueva condición para probar si la primera condición es falsa.
- **switch**: Especifica muchos bloques alternativos de código que se pueden ejecutar. La declaración `switch` se describirá en el próximo capítulo.

## La Declaración if

Utiliza la declaración `if` para especificar un bloque de código JavaScript que se ejecutará si una condición es verdadera.

### Sintaxis

```javascript
if (condición) {
  //  bloque de código que se ejecutará si la condición es verdadera
}
```

**Nota**: `if` debe escribirse en minúsculas. Las letras mayúsculas (If o IF) generarán un error en JavaScript.

### Ejemplo

Haz un saludo de "Buen día" si la hora es menor a las 18:00:

```javascript
if (hora < 18) {
  saludo = "Buen día";
}
```

El resultado de `saludo` será:

```
Buen día
```

### Analogía

Imagina que eres un chef en un restaurante. Tienes que decidir qué platillo preparar según la hora del día. Si es antes de las 18:00, decides preparar un almuerzo (es decir, "Buen día"). Pero si ya pasó esa hora, tal vez debas considerar servir la cena.

---

## La Declaración else

Utiliza la declaración `else` para especificar un bloque de código que se ejecutará si la condición es falsa.

### Sintaxis

```javascript
if (condición) {
  //  bloque de código que se ejecutará si la condición es verdadera
} else {
  //  bloque de código que se ejecutará si la condición es falsa
}
```

### Ejemplo

Si la hora es menor a 18, crea un saludo de "Buen día"; de lo contrario, "Buenas noches":

```javascript
if (hora < 18) {
  saludo = "Buen día";
} else {
  saludo = "Buenas noches";
}
```

El resultado de `saludo` será:

```
Buen día
```

### Analogía

Siguiendo con la analogía del chef: si decides que es hora de almuerzo, servirás un platillo ligero. Si ya es tarde y la hora de la cena ha llegado, optas por un plato más elaborado y pesado, es decir, "Buenas noches".

---

## La Declaración else if

Utiliza la declaración `else if` para especificar una nueva condición si la primera condición es falsa.

### Sintaxis

```javascript
if (condición1) {
  //  bloque de código que se ejecutará si condición1 es verdadera
} else if (condición2) {
  //  bloque de código que se ejecutará si condición1 es falsa y condición2 es verdadera
} else {
  //  bloque de código que se ejecutará si condición1 es falsa y condición2 es falsa
}
```

### Ejemplo

Si la hora es menor a las 10:00, crea un saludo de "Buen día"; si no, pero la hora es menor a las 20:00, crea un saludo de "Buen día"; de lo contrario, "Buenas noches":

```javascript
if (hora < 10) {
  saludo = "Buen día";
} else if (hora < 20) {
  saludo = "Buen día";
} else {
  saludo = "Buenas noches";
}
```

El resultado de `saludo` será:

```
Buen día
```

### Analogía

Imagina que eres un recepcionista en un hotel. Si llega un huésped muy temprano (antes de las 10:00), lo recibes con un cálido "¡Buen día!". Si llega durante el día (antes de las 20:00), también le das la bienvenida con "¡Buen día!". Pero si llega tarde en la noche, le dices "¡Buenas noches!" porque es el momento adecuado para ello.

---

## Más Ejemplos

### Ejemplo Aleatorio

Este ejemplo generará un enlace a W3Schools o a la Fundación Mundial para la Naturaleza (WWF). Al utilizar un número aleatorio, hay un 50% de probabilidad de cada uno de los enlaces.

```javascript
let randomNumber = Math.random();
if (randomNumber < 0.5) {
  document.write('<a href="https://www.w3schools.com">Visita W3Schools</a>');
} else {
  document.write('<a href="https://www.worldwildlife.org">Visita WWF</a>');
}
```

### Analogía

Piensa en un juego de azar, como lanzar un dado. Si sacas un número menor a 4, ganas un premio. Si sacas un número mayor o igual a 4, no ganas nada. De manera similar, este código elige aleatoriamente entre dos enlaces.

---

# JavaScript: Declaración Switch

La declaración `switch` se utiliza para realizar diferentes acciones basadas en diferentes condiciones.

## La Declaración Switch en JavaScript

Utiliza la declaración `switch` para seleccionar uno de muchos bloques de código que se ejecutarán.

### Sintaxis

```javascript
switch (expresión) {
  case x:
    // bloque de código
    break;
  case y:
    // bloque de código
    break;
  default:
    // bloque de código
}
```

### ¿Cómo Funciona?

1. La expresión del `switch` se evalúa una vez.
2. El valor de la expresión se compara con los valores de cada caso.
3. Si hay una coincidencia, se ejecuta el bloque de código asociado.
4. Si no hay coincidencia, se ejecuta el bloque de código por defecto.

### Ejemplo

El método `getDay()` devuelve el día de la semana como un número entre 0 y 6 (Domingo=0, Lunes=1, Martes=2, etc.).

Este ejemplo utiliza el número del día de la semana para calcular el nombre del día:

```javascript
switch (new Date().getDay()) {
  case 0:
    day = "Domingo";
    break;
  case 1:
    day = "Lunes";
    break;
  case 2:
    day = "Martes";
    break;
  case 3:
    day = "Miércoles";
    break;
  case 4:
    day = "Jueves";
    break;
  case 5:
    day = "Viernes";
    break;
  case 6:
    day = "Sábado";
}
```

El resultado de `day` será:

```
Miércoles
```

### Analogía

Imagina que eres un organizador de eventos. Cada día de la semana tiene un evento especial. Usas un `switch` para decidir qué evento ocurre en función del día actual. Si es domingo, preparas un brunch, si es lunes, un seminario, y así sucesivamente.

---

## La Palabra Clave break

Cuando JavaScript alcanza la palabra clave `break`, sale del bloque `switch`.

Esto detendrá la ejecución dentro del bloque `switch`.

No es necesario incluir `break` en el último caso de un bloque `switch`, ya que el bloque se termina allí de todos modos.

**Nota**: Si omites la declaración `break`, se ejecutará el siguiente caso, incluso si la evaluación no coincide con el caso.

### Ejemplo

Si la expresión es igual al caso 1, se ejecutará el bloque correspondiente y luego saldrá del `switch` gracias al `break`. 

---

## La Palabra Clave default

La palabra clave `default` especifica el código que se ejecutará si no hay coincidencia en los casos:

### Ejemplo

Si hoy no es sábado (6) ni domingo (0), escribe un mensaje por defecto:

```javascript
switch (new Date().getDay()) {
  case 6:
    text = "Hoy es Sábado";
    break;
  case 0:
    text = "Hoy es Domingo";
    break;
  default:
    text = "Esperando el fin de semana";
}
```

El resultado de `text` será:

```
Esperando el fin de semana
```

### Analogía

Si eres el chef de un restaurante y alguien llega un lunes, si no tienes un menú especial, ofreces un mensaje genérico como "Esperando el fin de semana", porque quizás tengas platos especiales solo los fines de semana.

---

## Casos Comunes de Bloques de Código

A veces, querrás que diferentes casos de `switch` utilicen el mismo código.

### Ejemplo

En este ejemplo, los casos 4 y 5 comparten el mismo bloque de código, y 0 y 6 comparten otro bloque:

```javascript
switch (new Date().getDay()) {
  case 4:
  case 5:
    text = "Pronto es fin de semana";
    break;
  case 0:
  case 6:
    text = "Es fin de semana";
    break;
  default:
    text = "Esperando el fin de semana";
}
```

### Analogía

Imagina que eres un maestro de ceremonias. Si es jueves o viernes, dices "¡Pronto es fin de semana!". Pero si es sábado o domingo, celebras diciendo "¡Es fin de semana!".

---

## Detalles del Switch

- Si múltiples casos coinciden con un valor de caso, se selecciona el primer caso.
- Si no se encuentran casos coincidentes, el programa continúa con la etiqueta `default`.
- Si no se encuentra ninguna etiqueta `default`, el programa continúa con la(s) declaración(es) después del `switch`.

### Comparación Estricta

Los casos del `switch` utilizan comparación estricta (===). Los valores deben ser del mismo tipo para coincidir.

En este ejemplo, no habrá coincidencia para `x`:

```javascript
let x = "0";
switch (x) {
  case 0:
    text = "Apagar";
    break;
  case 1:
    text = "Encender";
    break;
  default:
    text = "Valor no encontrado";
}
```

### Analogía

Piensa en un control remoto. Si presionas el botón de encendido y el control remoto está configurado para "encender" pero solo si presionas el botón exacto, no habrá coincidencia si presionas el botón equivocado.

---

# JavaScript: Bucle For

Los bucles pueden ejecutar un bloque de código varias veces.

## Bucles en JavaScript

Los bucles son útiles si quieres ejecutar el mismo código repetidamente, cada vez con un valor diferente.

Esto es especialmente común al trabajar con arreglos:

En lugar de escribir:

```javascript
text += cars[0] + "<br>";
text += cars[1] + "<br>";
text += cars[2] + "<br>";
text += cars[3] + "<br>";
text += cars[4] + "<br>";
text += cars[5] + "<br>";
```

Puedes escribir:

```javascript
for (let i = 0; i < cars.length; i++) {
  text += cars[i] + "<br>";
}
```

## Diferentes Tipos de Bucles

JavaScript soporta diferentes tipos de bucles:

- **for**: itera a través de un bloque de código un número específico de veces.
- **for/in**: itera a través de las propiedades de un objeto.
- **for/of**: itera a través de los valores de un objeto iterable.
- **while**: itera a través de un bloque de código mientras una condición específica sea verdadera.
- **do/while**: también itera a través de un bloque de código mientras una condición específica sea verdadera.

## El Bucle For

La declaración `for` crea un bucle con 3 expresiones opcionales:

```javascript
for (expresión 1; expresión 2; expresión 3) {
  // bloque de código a ejecutar
}
```

- **Expresión 1** se ejecuta (una vez) antes de la ejecución del bloque de código.
- **Expresión 2** define la condición para ejecutar el bloque de código.
- **Expresión 3** se ejecuta (cada vez) después de que el bloque de código ha sido ejecutado.

### Ejemplo

```javascript
for (let i = 0; i < 5; i++) {
  text += "El número es " + i + "<br>";
}
```

En el ejemplo anterior, puedes leer:

- **Expresión 1** establece una variable antes de que comience el bucle (`let i = 0`).
- **Expresión 2** define la condición para que el bucle se ejecute (`i debe ser menor que 5`).
- **Expresión 3** incrementa un valor (`i++`) cada vez que se ha ejecutado el bloque de código en el bucle.

### Expresión 1

Normalmente, usarás la expresión 1 para inicializar la variable que se usará en el bucle (`let i = 0`).

Esto no siempre es necesario. JavaScript no se preocupa por ello. La expresión 1 es opcional.

Puedes iniciar varios valores en la expresión 1 (separados por comas):

#### Ejemplo

```javascript
for (let i = 0, len = cars.length, text = ""; i < len; i++) {
  text += cars[i] + "<br>";
}
```

Y puedes omitir la expresión 1 (como cuando tus valores están establecidos antes de que comience el bucle):

#### Ejemplo

```javascript
let i = 2;
let len = cars.length;
let text = "";
for (; i < len; i++) {
  text += cars[i] + "<br>";
}
```

### Expresión 2

A menudo, la expresión 2 se utiliza para evaluar la condición de la variable inicial.

Esto no siempre es necesario. JavaScript no se preocupa por ello. La expresión 2 también es opcional.

Si la expresión 2 devuelve verdadero, el bucle comenzará de nuevo. Si devuelve falso, el bucle terminará.

Si omites la expresión 2, debes proporcionar un `break` dentro del bucle. De lo contrario, el bucle nunca terminará. Esto puede hacer que tu navegador se bloquee. Lee sobre los `break` en un capítulo posterior de este tutorial.

### Expresión 3

A menudo, la expresión 3 incrementa el valor de la variable inicial.

Esto no siempre es necesario. JavaScript no se preocupa por ello. La expresión 3 es opcional.

La expresión 3 puede hacer cualquier cosa, como un incremento negativo (`i--`), un incremento positivo (`i = i + 15`), o cualquier otra cosa.

La expresión 3 también puede omitirse (como cuando incrementas tus valores dentro del bucle):

#### Ejemplo

```javascript
let i = 0;
let len = cars.length;
let text = "";
for (; i < len; ) {
  text += cars[i] + "<br>";
  i++;
}
```

## Ámbito del Bucle

### Usando var en un bucle:

```javascript
var i = 5;

for (var i = 0; i < 10; i++) {
  // algún código
}

// Aquí i es 10
```

### Usando let en un bucle:

```javascript
let i = 5;

for (let i = 0; i < 10; i++) {
  // algún código
}

// Aquí i es 5
```

En el primer ejemplo, al usar `var`, la variable declarada en el bucle redeclara la variable fuera del bucle.

En el segundo ejemplo, al usar `let`, la variable declarada en el bucle no redeclara la variable fuera del bucle.

Cuando se utiliza `let` para declarar la variable `i` en un bucle, la variable `i` solo será visible dentro del bucle.

## Bucles For/Of y For/In

Los bucles `for/in` y `for/of` se explican en el próximo capítulo.

## Bucles While

Los bucles `while` y `do/while` se explican en los próximos capítulos.

---

### Analogía para entender los bucles

Imagina que estás organizando un evento y necesitas invitar a varias personas. En lugar de escribir una invitación para cada persona manualmente, puedes usar un bucle. 

Cada vez que llames a la lista de invitados (como un arreglo), el bucle se encarga de enviar una invitación a cada uno de ellos. Es mucho más eficiente y rápido.

Así es como funcionan los bucles: automatizan tareas repetitivas, lo que te permite centrarte en otras partes importantes de tu evento.

---

# JavaScript: For In

## El Bucle For In

La declaración `for...in` de JavaScript recorre las propiedades de un objeto.

### Sintaxis

```javascript
for (key in object) {
  // bloque de código a ejecutar
}
```

### Ejemplo

```javascript
const person = {fname: "John", lname: "Doe", age: 25};

let text = "";
for (let x in person) {
  text += person[x];
}
```

### Explicación del Ejemplo

1. **Iteración sobre un objeto**: El bucle `for...in` itera sobre el objeto `person`.
2. **Clave de Iteración**: En cada iteración, se devuelve una clave (en este caso, `x`).
3. **Acceso a Valor**: La clave se utiliza para acceder al valor de la propiedad del objeto.
4. **Valor de la Clave**: El valor de la clave se obtiene a través de `person[x]`, que representa el valor correspondiente a la clave actual.

### Analogía Sencilla

Imagina que tienes un armario con varias estanterías (cada estante es una propiedad del objeto). Si deseas ver qué hay en cada estante, puedes usar un bucle `for...in` para mirar cada uno de ellos. Así, cada vez que miras un estante (una clave), puedes sacar lo que hay en él (el valor de esa clave).

---

## For In sobre Arrays

La declaración `for...in` de JavaScript también puede recorrer las propiedades de un arreglo.

### Sintaxis

```javascript
for (variable in array) {
  // código
}
```

### Ejemplo

```javascript
const numbers = [45, 4, 9, 16, 25];

let txt = "";
for (let x in numbers) {
  txt += numbers[x];
}
```

### Precaución

No se debe usar `for...in` sobre un arreglo si el orden de los índices es importante. El orden de los índices es dependiente de la implementación, y los valores del arreglo pueden no ser accedidos en el orden que esperas.

Es mejor utilizar un bucle `for`, un bucle `for...of`, o `Array.forEach()` cuando el orden es importante.

---

## Array.forEach()

El método `forEach()` llama a una función (una función de retorno de llamada) una vez para cada elemento del arreglo.

### Ejemplo

```javascript
const numbers = [45, 4, 9, 16, 25];

let txt = "";
numbers.forEach(myFunction);

function myFunction(value, index, array) {
  txt += value;
}
```

### Argumentos de la Función

Nota que la función toma 3 argumentos:

- **El valor del elemento**
- **El índice del elemento**
- **El arreglo mismo**

El ejemplo anterior usa solo el parámetro de valor. Puede reescribirse de la siguiente manera:

### Ejemplo Simplificado

```javascript
const numbers = [45, 4, 9, 16, 25];

let txt = "";
numbers.forEach(myFunction);

function myFunction(value) {
  txt += value;
}
```

### Analogía para forEach()

Imagina que estás organizando una fiesta y necesitas invitar a cada uno de tus amigos. En lugar de enviar las invitaciones una por una, puedes usar `forEach()` como una lista de invitados. Cada vez que llamas a un amigo de la lista (cada elemento del arreglo), le envías la invitación (ejecutas la función). Esto te ayuda a asegurarte de que cada amigo reciba su invitación de manera eficiente y sin olvidar a nadie.

---

# JavaScript: For Of

## The For Of Loop

La declaración `for...of` en JavaScript itera sobre los valores de un objeto iterable. Esto te permite recorrer estructuras de datos iterables, como arreglos, cadenas, mapas, NodeLists y más.

### Sintaxis

```javascript
for (variable of iterable) {
  // bloque de código a ejecutar
}
```

- **variable**: En cada iteración, se asigna el valor de la siguiente propiedad a la variable. La variable puede declararse con `const`, `let` o `var`.
- **iterable**: Un objeto que tiene propiedades iterables.

### Soporte en Navegadores

El `for...of` se agregó a JavaScript en 2015 (ES6). El primer navegador en soportar `for...of` fue Safari 7:

| Navegador   | Versión | Fecha       |
|-------------|---------|-------------|
| Chrome      | 38      | Oct 2014    |
| Edge        | 12      | Jul 2015    |
| Firefox     | 51      | Oct 2016    |
| Safari      | 7       | Oct 2013    |
| Opera       | 25      | Oct 2014    |

Ten en cuenta que `for...of` no es compatible con Internet Explorer.

---

## Iterando sobre un Arreglo

### Ejemplo

```javascript
const cars = ["BMW", "Volvo", "Mini"];

let text = "";
for (let x of cars) {
  text += x;
}
```

### Explicación

En este ejemplo, la declaración `for...of` recorre el arreglo `cars`. En cada iteración, el valor de `x` es asignado al siguiente elemento del arreglo, y luego se añade a la variable `text`.

### Analogía

Imagina que tienes una caja de chocolates. Cada vez que abres la caja, tomas un chocolate (un elemento del arreglo). En lugar de contar los chocolates (usando índices), simplemente los comes uno por uno hasta que se acaben. Así es como funciona el `for...of`: tomas el valor directamente sin preocuparte por su posición.

---

## Iterando sobre una Cadena

### Ejemplo

```javascript
let language = "JavaScript";

let text = "";
for (let x of language) {
  text += x;
}
```

### Explicación

Aquí, el `for...of` itera sobre la cadena `language`. En cada iteración, se toma un carácter de la cadena y se añade a `text`.

### Analogía

Imagina que estás leyendo un libro. Cada vez que pasas la página, ves una letra (un carácter de la cadena). En lugar de contar cuántas letras quedan en el libro, simplemente sigues leyendo una por una. Eso es lo que hace el `for...of`: recorre los caracteres sin preocuparte por su índice.

---

# JavaScript: While Loop

## Loops

Los bucles pueden ejecutar un bloque de código mientras una condición especificada sea verdadera.

## El Bucle While

El bucle `while` itera a través de un bloque de código mientras una condición especificada sea verdadera.

### Sintaxis

```javascript
while (condition) {
  // bloque de código a ejecutar
}
```

### Ejemplo

En el siguiente ejemplo, el código en el bucle se ejecutará repetidamente mientras la variable `i` sea menor que 10:

```javascript
let i = 0; // Inicializamos la variable
let text = "";

while (i < 10) {
  text += "El número es " + i + "\n"; // Concatenamos el texto
  i++; // Aumentamos i en 1
}
```

### Advertencia

Si olvidas aumentar la variable utilizada en la condición, el bucle nunca terminará, lo que puede hacer que tu navegador se bloquee. Es importante siempre asegurarse de que la condición eventualmente se vuelva falsa.

### Analogía

Imagina que estás llenando un balde con agua. Cada vez que echas agua en el balde (ejecutas el código), miras si el balde está lleno (evalúas la condición). Si no aumentas el nivel de agua en el balde (no aumentas la variable), el balde nunca se llenará y seguirás echando agua sin parar.

---

## El Bucle Do While

El bucle `do while` es una variante del bucle `while`. Este bucle ejecutará el bloque de código al menos una vez antes de verificar si la condición es verdadera, y luego repetirá el bucle mientras la condición siga siendo verdadera.

### Sintaxis

```javascript
do {
  // bloque de código a ejecutar
} while (condition);
```

### Ejemplo

En el siguiente ejemplo, el bucle `do while` siempre se ejecutará al menos una vez, incluso si la condición es falsa:

```javascript
let i = 0; // Inicializamos la variable
let text = "";

do {
  text += "El número es " + i + "\n"; // Concatenamos el texto
  i++; // Aumentamos i en 1
} while (i < 10);
```

### Advertencia

Al igual que con el bucle `while`, no olvides aumentar la variable utilizada en la condición. De lo contrario, el bucle nunca terminará.

### Analogía

Piensa en un juego donde tienes que lanzar un dado. Lanzas el dado (ejecutas el código) al menos una vez. Después de cada lanzamiento, decides si quieres seguir jugando (evalúas la condición). Si no has establecido un límite en cuántas veces lanzar el dado, podrías terminar lanzándolo indefinidamente.

---

## Comparando For y While

Si has leído el capítulo anterior sobre el bucle `for`, notarás que un bucle `while` es muy similar a un bucle `for`, con la primera y la tercera declaración omitidas.

### Ejemplo de Bucle For

```javascript
const cars = ["BMW", "Volvo", "Saab", "Ford"];
let i = 0; // Inicializamos el índice
let text = "";

for (; cars[i];) {
  text += cars[i]; // Concatenamos el texto
  i++; // Aumentamos i en 1
}
```

### Ejemplo de Bucle While

```javascript
const cars = ["BMW", "Volvo", "Saab", "Ford"];
let i = 0; // Inicializamos el índice
let text = "";

while (cars[i]) {
  text += cars[i]; // Concatenamos el texto
  i++; // Aumentamos i en 1
}
```

---

# JavaScript: Break y Continue

En JavaScript, las instrucciones `break` y `continue` permiten controlar el flujo de los bucles de manera efectiva.

## La Instrucción Break

La instrucción `break` "salta fuera" de un bucle. 

### Ejemplo

En este ejemplo, el bucle se detiene cuando el contador (i) es igual a 3:

```javascript
let text = "";
for (let i = 0; i < 10; i++) {
  if (i === 3) { 
    break; 
  }
  text += "El número es " + i + "<br>";
}
```

### Explicación

- El bucle comienza en 0 y se incrementa hasta 10.
- Cuando `i` es igual a 3, se ejecuta la instrucción `break`, lo que hace que el bucle se detenga inmediatamente.
- Por lo tanto, la salida será: "El número es 0", "El número es 1" y "El número es 2".

### Analogía

Imagina que estás en un juego de mesa, y cada vez que llegas a la casilla 3, decides que has tenido suficiente y te sales del juego (ejecutando `break`). Ya no sigues avanzando en el tablero.

---

## La Instrucción Continue

La instrucción `continue` "salta" una iteración en el bucle. Cuando se cumple una condición especificada, se omite el resto del código en esa iteración y se continúa con la siguiente.

### Ejemplo

En este caso, el valor 3 se omite:

```javascript
let text = "";
for (let i = 0; i < 10; i++) {
  if (i === 3) { 
    continue; 
  }
  text += "El número es " + i + "<br>";
}
```

### Explicación

- Aquí, el bucle itera del 0 al 9.
- Cuando `i` es igual a 3, se ejecuta `continue`, lo que hace que el bucle salte esa iteración.
- Por lo tanto, la salida será: "El número es 0", "El número es 1", "El número es 2", "El número es 4", "El número es 5", etc.

### Analogía

Imagina que estás en una fila para entrar a una tienda y decides saltarte a la persona que está en la posición 3 porque está tomando demasiado tiempo. Sigues avanzando en la fila y dejas atrás a esa persona (ejecutando `continue`).

---

## Etiquetas en JavaScript

Para etiquetar instrucciones en JavaScript, se preceden las instrucciones con un nombre de etiqueta y dos puntos:

```javascript
label:
statements
```

Las instrucciones `break` y `continue` son las únicas instrucciones de JavaScript que pueden "saltar fuera" de un bloque de código.

### Sintaxis

- Para la instrucción `break` con etiqueta:

```javascript
break labelname;
```

- Para la instrucción `continue` con etiqueta:

```javascript
continue labelname;
```

### Ejemplo con Etiqueta

Aquí hay un ejemplo utilizando una etiqueta:

```javascript
const cars = ["BMW", "Volvo", "Saab", "Ford"];
list: {
  text += cars[0] + "<br>";
  text += cars[1] + "<br>";
  break list; // Salta fuera del bloque "list"
  text += cars[2] + "<br>";
  text += cars[3] + "<br>";
}
```

### Explicación

- En este ejemplo, el bloque de código que está etiquetado como `list` se ejecuta.
- Cuando se encuentra la instrucción `break list`, el flujo se sale del bloque etiquetado y no se ejecutan las líneas siguientes.

---

# JavaScript Iterables

Los iterables son objetos que se pueden recorrer (como los arreglos). 

Los iterables se pueden acceder con un código simple y eficiente, y se pueden iterar con bucles `for..of`.

## El Bucle For Of

La declaración `for..of` en JavaScript recorre los elementos de un objeto iterable.

### Sintaxis

```javascript
for (variable of iterable) {
  // bloque de código a ejecutar
}
```

### Iteración

La iteración es fácil de entender. Simplemente significa recorrer una secuencia de elementos.

### Ejemplos fáciles:

- Iterando sobre una cadena (string)
- Iterando sobre un arreglo (array)

## Iterando Sobre una Cadena

Puedes usar un bucle `for..of` para iterar sobre los elementos de una cadena:

### Ejemplo

```javascript
const name = "W3Schools";

for (const x of name) {
  // bloque de código a ejecutar
}
```

### Analogía

Imagina que estás leyendo un libro. Cada vez que pasas una página, ves una letra (o palabra) nueva. En este caso, cada letra de la cadena es como una página que se está "leyendo" en cada iteración del bucle.

---

## Iterando Sobre un Arreglo

Puedes usar un bucle `for..of` para iterar sobre los elementos de un arreglo:

### Ejemplo 1

```javascript
const letters = ["a", "b", "c"];

for (const x of letters) {
  // bloque de código a ejecutar
}
```

### Ejemplo 2

```javascript
const numbers = [2, 4, 6, 8];

for (const x of numbers) {
  // bloque de código a ejecutar
}
```

### Analogía

Piensa en un arreglo como un plato de frutas. Cada fruta (o elemento) es un objeto en el plato. Usar `for..of` es como tomar cada fruta una por una y observarla.

---

## Iterando Sobre un Set

Puedes usar un bucle `for..of` para iterar sobre los elementos de un Set:

### Ejemplo

```javascript
const letters = new Set(["a", "b", "c"]);

for (const x of letters) {
  // bloque de código a ejecutar
}
```

### Nota

Los Sets y Maps se cubren en los siguientes capítulos.

---

## Iterando Sobre un Map

Puedes usar un bucle `for..of` para iterar sobre los elementos de un Map:

### Ejemplo

```javascript
const fruits = new Map([
  ["apples", 500],
  ["bananas", 300],
  ["oranges", 200]
]);

for (const x of fruits) {
  // bloque de código a ejecutar
}
```

### Analogía

Imagina que un Map es como un directorio telefónico. Cada entrada tiene un nombre (clave) y un número de teléfono (valor). Al usar `for..of`, estás recorriendo cada entrada en el directorio y viendo el nombre y el número de teléfono.

---

## JavaScript Iterators

El protocolo del iterador define cómo producir una secuencia de valores a partir de un objeto. 

Un objeto se convierte en un iterador cuando implementa un método `next()`.

### El Método next()

El método `next()` debe devolver un objeto con dos propiedades:

- **value**: el próximo valor
- **done**: (verdadero o falso)

**value**: El valor devuelto por el iterador (puede omitirse si done es verdadero).

**done**: verdadero si el iterador ha terminado, falso si el iterador ha producido un nuevo valor.

### Nota

Técnicamente, los iterables deben implementar el método `Symbol.iterator`.

Las cadenas, arreglos, TypedArray, Map y Set son todos iterables, porque sus objetos prototipo tienen un método `Symbol.iterator`.

---

## Iterable Hecho a Mano

Este iterable devuelve una secuencia infinita: 10, 20, 30, 40,... Cada vez que se llama a `next()`:

### Ejemplo

```javascript
// Iterable Hecho a Mano
function myNumbers() {
  let n = 0;
  return {
    next: function() {
      n += 10;
      return {value: n, done: false};
    }
  };
}

// Crear Iterable
const n = myNumbers();
n.next(); // Devuelve 10
n.next(); // Devuelve 20
n.next(); // Devuelve 30
```

### Problema con un Iterable Hecho a Mano

No admite la declaración `for..of` de JavaScript. Un iterable de JavaScript es un objeto que tiene un `Symbol.iterator`. 

El `Symbol.iterator` es una función que devuelve una función `next()`.

Un iterable se puede recorrer con el siguiente código:

```javascript
for (const x of iterable) {
  // Cualquier código aquí
}
```

### Ejemplo

```javascript
// Crear un Objeto
myNumbers = {};

// Hacerlo Iterable
myNumbers[Symbol.iterator] = function() {
  let n = 0;
  done = false;
  return {
    next() {
      n += 10;
      if (n == 100) { done = true }
      return { value: n, done: done };
    }
  };
}
```

Ahora puedes usar `for..of`:

```javascript
for (const num of myNumbers) {
  // Cualquier código aquí
}
```

El método `Symbol.iterator` se llama automáticamente con `for..of`. Pero también podemos hacerlo "manualmente":

### Ejemplo Manual

```javascript
let iterator = myNumbers[Symbol.iterator]();

while (true) {
  const result = iterator.next();
  if (result.done) break;
  // Cualquier código aquí
}
```

### Analogía

Imagina que eres un repartidor de cartas. Tu trabajo es entregar cartas (valores) a cada destinatario (iteración). Cada vez que entregas una carta, decides si hay más cartas que entregar (done). Si no hay más cartas, simplemente terminas la entrega.

---

# JavaScript Sets

Un **Set** en JavaScript es una colección de valores únicos. Esto significa que cada valor solo puede ocurrir una vez en un Set.

Los valores en un Set pueden ser de cualquier tipo, ya sea valores primitivos u objetos.

## Cómo Crear un Set

Puedes crear un Set en JavaScript de las siguientes maneras:

1. Pasando un array al constructor `new Set()`.
2. Creando un Set vacío y utilizando el método `add()` para añadir valores.

### El Método new Set()

Para crear un Set, puedes pasar un array al constructor `new Set()`:

#### Ejemplo

```javascript
// Crear un Set
const letters = new Set(["a", "b", "c"]);
```

### Crear un Set y Añadir Valores

También puedes crear un Set vacío y usar el método `add()` para añadir valores:

#### Ejemplo

```javascript
// Crear un Set
const letters = new Set();

// Añadir Valores al Set
letters.add("a");
letters.add("b");
letters.add("c");
```

### Crear un Set y Añadir Variables

Otra opción es crear un Set y luego añadir variables:

#### Ejemplo

```javascript
// Crear un Set
const letters = new Set();

// Crear Variables
const a = "a";
const b = "b";
const c = "c";

// Añadir Variables al Set
letters.add(a);
letters.add(b);
letters.add(c);
```

## El Método add()

Puedes utilizar el método `add()` para añadir elementos al Set. Si añades elementos iguales, solo se guardará el primero:

#### Ejemplo

```javascript
letters.add("d");
letters.add("e");
letters.add("a"); // Solo se guardará el primero
```

En el siguiente ejemplo, intentar añadir el mismo valor varias veces no cambiará el Set:

#### Ejemplo

```javascript
letters.add("a");
letters.add("b");
letters.add("c");
letters.add("c"); // Ignorado
letters.add("c"); // Ignorado
letters.add("c"); // Ignorado
```

### Listando los Elementos

Puedes listar todos los elementos de un Set utilizando un bucle `for..of`:

#### Ejemplo

```javascript
// Crear un Set
const letters = new Set(["a", "b", "c"]);

// Listar todos los Elementos
let text = "";
for (const x of letters) {
  text += x;
}
console.log(text); // Salida: abc
```

### Sets Son Objetos

En JavaScript, los Sets son un tipo de objeto. Puedes verificar el tipo utilizando `typeof` y también puedes comprobar si es una instancia de Set utilizando `instanceof`.

#### Ejemplo

```javascript
typeof letters;      // Retorna "object"
letters instanceof Set;  // Retorna true
```

## Analogías para Entender Sets

Imagina que un Set es como una caja de juguetes. Solo puedes tener un tipo de juguete por cada categoría. Si intentas meter dos juguetes del mismo tipo (por ejemplo, dos pelotas de fútbol), solo habrá una en la caja. Esta característica de los Sets asegura que cada juguete (o valor) sea único.

Al igual que en una caja de juguetes, puedes abrir la caja (utilizar un bucle `for..of`) y sacar cada juguete (valor) para jugar con él, pero siempre recordando que no puedes tener duplicados.

---

# Métodos de Sets en JavaScript

Los **Sets** en JavaScript son colecciones de valores únicos. A continuación, exploraremos algunos de los métodos más utilizados para trabajar con Sets, junto con ejemplos y analogías que faciliten su comprensión.

## El Método new Set()

Para crear un Set, puedes pasar un array al constructor `new Set()`:

### Ejemplo

```javascript
// Crear un Set
const letras = new Set(["a", "b", "c"]);
```

### Analogía

Imagina que un Set es como una caja de herramientas. Cuando compras un juego de herramientas, cada herramienta (valor) viene en su propio espacio y no puedes tener dos de la misma herramienta en el mismo espacio. Así es como funciona un Set: solo puedes tener una instancia de cada valor.

## El Método add()

Puedes añadir valores a un Set usando el método `add()`. Si intentas añadir valores duplicados, solo se guardará la primera ocurrencia.

### Ejemplo

```javascript
letras.add("d");
letras.add("e");

// Si intentas añadir elementos iguales, solo se guardará el primero
letras.add("a");
letras.add("b");
letras.add("c");
letras.add("c"); // Ignorado
```

### Analogía

Siguiendo con la analogía de la caja de herramientas, si intentas meter dos martillos en el mismo espacio, solo uno de ellos permanecerá en la caja. Así, al añadir un valor que ya existe, el Set ignorará el nuevo valor.

## Listando Elementos del Set

Puedes listar todos los elementos de un Set utilizando un bucle `for..of`.

### Ejemplo

```javascript
// Crear un Set
const letras = new Set(["a", "b", "c"]);

// Listar todos los Elementos
let texto = "";
for (const x of letras) {
  texto += x;
}
console.log(texto); // Salida: abc
```

### Analogía

Imagina que estás sacando herramientas de tu caja y mostrando cada una a tus amigos. Con el bucle `for..of`, puedes ir mostrando cada herramienta (valor) que hay en tu caja (Set).

## El Método has()

El método `has()` devuelve `true` si un valor especificado existe en un Set.

### Ejemplo

```javascript
// Crear un Set
const letras = new Set(["a", "b", "c"]);

// ¿Contiene el Set "d"?
const respuesta = letras.has("d"); // false
```

### Analogía

Es como revisar si tienes una herramienta específica en tu caja. Preguntarte "¿tengo un destornillador?" sería como usar el método `has()`. Si la herramienta está ahí, obtendrás una respuesta positiva; de lo contrario, no.

## El Método forEach()

El método `forEach()` invoca una función para cada elemento del Set.

### Ejemplo

```javascript
// Crear un Set
const letras = new Set(["a", "b", "c"]);

// Listar todas las entradas
let texto = "";
letras.forEach(function(valor) {
  texto += valor;
});
console.log(texto); // Salida: abc
```

### Analogía

Imagina que le pides a un amigo que enumere todas las herramientas de tu caja. El método `forEach()` actúa como ese amigo, mencionando cada herramienta una por una.

## El Método values()

El método `values()` devuelve un objeto iterador con los valores en un Set.

### Ejemplo 1

```javascript
// Crear un Set
const letras = new Set(["a", "b", "c"]);

// Obtener todos los Valores
const miIterador = letras.values();

// Listar todos los Valores
let texto = "";
for (const entrada of miIterador) {
  texto += entrada;
}
console.log(texto); // Salida: abc
```

### Ejemplo 2

```javascript
// Crear un Set
const letras = new Set(["a", "b", "c"]);

// Listar todos los Valores
let texto = "";
for (const entrada of letras.values()) {
  texto += entrada;
}
console.log(texto); // Salida: abc
```

### Analogía

Piensa en el método `values()` como en un directorio de herramientas. Te da un acceso fácil a cada herramienta (valor) de la caja (Set), permitiéndote enumerarlas todas.

## El Método keys()

El método `keys()` devuelve un objeto iterador con los valores en un Set. 

### Nota

Un Set no tiene claves, por lo que `keys()` devuelve lo mismo que `values()`. Esto hace que los Sets sean compatibles con Maps.

### Ejemplo 1

```javascript
// Crear un Set
const letras = new Set(["a", "b", "c"]);

// Crear un Iterador
const miIterador = letras.keys();

// Listar todos los Elementos
let texto = "";
for (const x of miIterador) {
  texto += x;
}
console.log(texto); // Salida: abc
```

### Ejemplo 2

```javascript
// Crear un Set
const letras = new Set(["a", "b", "c"]);

// Listar todos los Elementos
let texto = "";
for (const x of letras.keys()) {
  texto += x;
}
console.log(texto); // Salida: abc
```

### Analogía

Imagina que el método `keys()` es como tener un mapa de la caja de herramientas. Aunque no tengas claves, puedes ver qué herramientas están disponibles. Esto es similar a cómo `keys()` y `values()` te dan acceso a los mismos valores.

## El Método entries()

El método `entries()` devuelve un iterador con pares [valor, valor] de un Set.

### Nota

El método `entries()` se supone que devuelve un par [clave, valor] de un objeto. Como un Set no tiene claves, el método `entries()` devuelve [valor, valor]. Esto hace que los Sets sean compatibles con Maps.

### Ejemplo 1

```javascript
// Crear un Set
const letras = new Set(["a", "b", "c"]);

// Obtener todas las Entradas
const miIterador = letras.entries();

// Listar todas las Entradas
let texto = "";
for (const entrada of miIterador) {
  texto += entrada;
}
console.log(texto); // Salida: abcabc
```

### Ejemplo 2

```javascript
// Crear un Set
const letras = new Set(["a", "b", "c"]);

// Listar todas las Entradas
let texto = "";
for (const entrada of letras.entries()) {
  texto += entrada;
}
console.log(texto); // Salida: abcabc
```

### Analogía

El método `entries()` es como recibir una lista de herramientas con una descripción de cada una. Aunque en realidad no hay claves, puedes ver qué herramientas tienes y su respectiva "descripción" (valor).

---

# JavaScript Maps

Un **Map** en JavaScript es una colección de pares clave-valor donde las claves pueden ser de cualquier tipo de dato. A diferencia de los objetos, un Map recuerda el orden de inserción original de las claves.

## Cómo Crear un Map

Puedes crear un Map en JavaScript de las siguientes maneras:

1. Pasando un Array al constructor `new Map()`
2. Creando un Map y utilizando el método `Map.set()`

### El nuevo método Map()

Puedes crear un Map pasando un Array al constructor `new Map()`:

#### Ejemplo

```javascript
// Crear un Map
const fruits = new Map([
  ["manzanas", 500],
  ["bananas", 300],
  ["naranjas", 200]
]);
```

### Analogía

Imagina un estante donde colocas frutas. Cada fruta (clave) tiene una cantidad (valor). Cuando creas un Map, es como colocar esas frutas en un estante, recordando cuántas tienes de cada tipo.

## El método set()

Puedes añadir elementos a un Map con el método `set()`:

#### Ejemplo

```javascript
// Crear un Map
const fruits = new Map();

// Establecer valores en el Map
fruits.set("manzanas", 500);
fruits.set("bananas", 300);
fruits.set("naranjas", 200);
```

El método `set()` también se puede utilizar para cambiar los valores existentes en el Map:

#### Ejemplo

```javascript
fruits.set("manzanas", 200);
```

### Analogía

Piensa en el método `set()` como un asistente que organiza tus frutas en el estante. Si decides cambiar la cantidad de manzanas que tienes, simplemente le dices al asistente que lo actualice.

## El método get()

El método `get()` obtiene el valor de una clave en un Map:

#### Ejemplo

```javascript
fruits.get("manzanas"); // Devuelve 500
```

### Analogía

Usar `get()` es como preguntarle a tu asistente cuántas manzanas hay en el estante. Él te responderá con la cantidad exacta.

## Maps son Objetos

Cuando utilizas `typeof` en un Map, devuelve "object":

#### Ejemplo

```javascript
// Devuelve object:
typeof fruits; // "object"
```

El operador `instanceof` retorna `true` si un objeto es una instancia de Map:

#### Ejemplo

```javascript
// Devuelve true:
fruits instanceof Map; // true
```

### Analogía

Los Maps son como una categoría especial de objetos en JavaScript. Aunque son objetos, tienen propiedades únicas que los hacen diferentes y más organizados.

## Diferencias entre Objetos de JavaScript y Maps

Aquí hay algunas diferencias clave entre objetos y Maps en JavaScript:

| **Objeto**                             | **Map**                             |
|----------------------------------------|-------------------------------------|
| No son directamente iterables          | Son directamente iterables           |
| No tienen una propiedad de tamaño      | Tienen una propiedad de tamaño      |
| Las claves deben ser Cadenas (o Símbolos) | Las claves pueden ser de cualquier tipo de dato |
| Las claves no están bien ordenadas     | Las claves están ordenadas por inserción |
| Tienen claves predeterminadas          | No tienen claves predeterminadas    |

### Analogía

Imagina que los objetos son como cajas de almacenamiento desordenadas, donde las cosas están apiladas sin un orden específico. Por otro lado, los Maps son como estanterías organizadas, donde cada elemento tiene su lugar y puedes acceder a ellos fácilmente.

## Referencia Completa de Map

Para una referencia completa, consulta nuestra [Referencia Completa de JavaScript Map](#).

La referencia contiene descripciones y ejemplos de todas las propiedades y métodos de Map.

## Soporte en Navegadores

Map es una característica de ES6 (JavaScript 2015). ES6 es completamente compatible en todos los navegadores modernos desde junio de 2017:

| Navegador    | Versión |
|--------------|---------|
| Chrome       | 51      |
| Edge         | 15      |
| Firefox      | 54      |
| Safari       | 10      |
| Opera        | 38      |

**Nota:** Map no es compatible con Internet Explorer.

---

# Métodos de Mapas en JavaScript

Un **Map** en JavaScript es una colección de pares clave-valor donde las claves pueden ser de cualquier tipo de dato. Aquí exploraremos varios métodos que puedes usar con Mapas y cómo funcionan.

## El Método new Map()

Puedes crear un mapa pasando un arreglo al constructor `new Map()`:

### Ejemplo

```javascript
// Crear un Map
const frutas = new Map([
  ["manzanas", 500],
  ["bananas", 300],
  ["naranjas", 200]
]);
```

### Analogía

Imagina que el mapa es una despensa en la que almacenas diferentes frutas. Cada tipo de fruta (clave) tiene una cantidad asociada (valor).

## Map.get()

Para obtener el valor de una clave en un mapa, se utiliza el método `get()`:

### Ejemplo

```javascript
frutas.get("manzanas"); // Retorna 500
```

### Analogía

Es como preguntar a un amigo cuántas manzanas tienes en la despensa. Él te dirá la cantidad exacta.

## Map.set()

Puedes agregar elementos a un mapa con el método `set()`:

### Ejemplo

```javascript
// Crear un Map
const frutas = new Map();

// Establecer valores en el Map
frutas.set("manzanas", 500);
frutas.set("bananas", 300);
frutas.set("naranjas", 200);
```

El método `set()` también se puede usar para cambiar valores existentes en el mapa:

### Ejemplo

```javascript
frutas.set("manzanas", 400); // Cambia la cantidad de manzanas
```

### Analogía

Imagina que estás reorganizando tu despensa. Si decides cambiar la cantidad de manzanas, solo le dices a tu amigo que actualice el número.

## Map.size

La propiedad `size` devuelve el número de elementos en un mapa:

### Ejemplo

```javascript
frutas.size; // Retorna 3
```

### Analogía

Es como contar cuántas diferentes frutas tienes en tu despensa.

## Map.delete()

El método `delete()` elimina un elemento del mapa:

### Ejemplo

```javascript
frutas.delete("manzanas"); // Elimina las manzanas
```

### Analogía

Es como quitar una fruta de la despensa. Después de usarla, ya no está allí.

## Map.clear()

El método `clear()` elimina todos los elementos de un mapa:

### Ejemplo

```javascript
frutas.clear(); // Elimina todas las frutas
```

### Analogía

Es como vaciar completamente tu despensa.

## Map.has()

El método `has()` devuelve `true` si una clave existe en el mapa:

### Ejemplo

```javascript
frutas.has("manzanas"); // Retorna false si las manzanas fueron eliminadas
```

### Analogía

Es como preguntar si todavía tienes manzanas en tu despensa. Si no están, la respuesta será "no".

### Prueba Esto

```javascript
frutas.delete("manzanas"); // Elimina las manzanas
frutas.has("manzanas"); // Verifica si las manzanas aún existen
```

## Map.forEach()

El método `forEach()` invoca una función de retorno de llamada para cada par clave/valor en un mapa:

### Ejemplo

```javascript
// Listar todas las entradas
let texto = "";
frutas.forEach(function(valor, clave) {
  texto += clave + ' = ' + valor + "\n";
});
```

### Analogía

Es como hacer un inventario de todas las frutas que tienes. Vas nombrando cada fruta y su cantidad.

## Map.entries()

El método `entries()` devuelve un objeto iterador con las [clave, valor] en un mapa:

### Ejemplo

```javascript
// Listar todas las entradas
let texto = "";
for (const x of frutas.entries()) {
  texto += x[0] + " = " + x[1] + "\n";
}
```

### Analogía

Imagina que tu despensa tiene etiquetas en cada estante que indican qué frutas hay y cuántas.

## Map.keys()

El método `keys()` devuelve un objeto iterador con las claves en un mapa:

### Ejemplo

```javascript
// Listar todas las claves
let texto = "";
for (const x of frutas.keys()) {
  texto += x + "\n";
}
```

### Analogía

Es como hacer una lista de todas las frutas que tienes en la despensa.

## Map.values()

El método `values()` devuelve un objeto iterador con los valores en un mapa:

### Ejemplo

```javascript
// Listar todos los valores
let texto = "";
for (const x of frutas.values()) {
  texto += x + "\n";
}
```

Puedes usar el método `values()` para sumar los valores en un mapa:

### Ejemplo

```javascript
// Sumar todos los valores
let total = 0;
for (const x of frutas.values()) {
  total += x;
}
```

### Analogía

Es como contar cuántas frutas hay en total en tu despensa.

## Objetos como Claves

Una característica importante de los Mapas es que puedes usar objetos como claves.

### Ejemplo

```javascript
// Crear Objetos
const manzanas = {nombre: 'Manzanas'};
const bananas = {nombre: 'Bananas'};
const naranjas = {nombre: 'Naranjas'};

// Crear un Map
const frutas = new Map();

// Agregar nuevos elementos al Map
frutas.set(manzanas, 500);
frutas.set(bananas, 300);
frutas.set(naranjas, 200);
```

Recuerda: la clave es un objeto (`manzanas`), no una cadena (`"manzanas"`):

### Ejemplo

```javascript
frutas.get("manzanas"); // Retorna undefined
```

### Analogía

Es como usar una foto de una fruta en lugar de su nombre para identificarla en tu despensa. Si buscas el nombre, no lo encontrarás.

## JavaScript Map.groupBy()

ES2024 agregó el método `Map.groupBy()` a JavaScript.

El método `Map.groupBy()` agrupa elementos de un objeto según los valores de cadena devueltos por una función de retorno de llamada. Este método no cambia el objeto original.

### Ejemplo

```javascript
// Crear un Arreglo
const frutas = [
  {nombre: "manzanas", cantidad: 300},
  {nombre: "bananas", cantidad: 500},
  {nombre: "naranjas", cantidad: 200},
  {nombre: "kiwi", cantidad: 150}
];

// Función de retorno de llamada para agrupar elementos
function miCallback({ cantidad }) {
  return cantidad > 200 ? "ok" : "bajo";
}

// Agrupar por cantidad
const resultado = Map.groupBy(frutas, miCallback);
```

## Soporte del Navegador

`Map.groupBy()` es una característica de ES2024 y está soportada en nuevos navegadores desde marzo de 2024:

| Navegador  | Versión |
|------------|---------|
| Chrome     | 117     |
| Edge       | 117     |
| Firefox    | 119     |
| Safari     | 17.4    |
| Opera      | 103     |

### Advertencia

Las características de ES2024 son relativamente nuevas. Los navegadores más antiguos pueden necesitar un código alternativo (Polyfill).

## Object.groupBy() vs Map.groupBy()

La diferencia entre `Object.groupBy()` y `Map.groupBy()` es:

- `Object.groupBy()` agrupa elementos en un objeto JavaScript.
- `Map.groupBy()` agrupa elementos en un objeto Map.

---

# JavaScript: Understanding the `typeof` Operator

## El operador typeof

El operador `typeof` devuelve el tipo de dato de una variable en JavaScript. Imagina que tienes un amigo que es capaz de decirte de qué tipo de animal es cada uno de tus mascotas solo con mirarlas. Eso es lo que hace `typeof` con las variables.

### Tipos de datos primitivos

En JavaScript, un valor primitivo es un solo valor que no tiene propiedades ni métodos. Piensa en ellos como en diferentes tipos de frutas en una frutera: cada fruta es única y tiene su propia identidad.

JavaScript tiene **7 tipos de datos primitivos**:

- **string**: Texto. Ejemplo: "manzana"
- **number**: Números. Ejemplo: 42
- **boolean**: Verdadero o falso. Ejemplo: true
- **bigint**: Números enteros grandes. Ejemplo: 123456789012345678901234567890n
- **symbol**: Un identificador único. Ejemplo: Symbol()
- **null**: Representa "nada" o "vacío". Ejemplo: null
- **undefined**: Una variable que no ha sido definida. Ejemplo: undefined

El operador `typeof` devuelve el tipo de una variable o expresión.

### Ejemplos

```javascript
typeof "John"         // Retorna "string"
typeof ("John"+"Doe") // Retorna "string"
typeof 3.14           // Retorna "number"
typeof 33             // Retorna "number"
typeof (33 + 66)      // Retorna "number"
typeof true           // Retorna "boolean"
typeof false          // Retorna "boolean"
typeof 1234n          // Retorna "bigint"
typeof Symbol()       // Retorna "symbol"
typeof x              // Retorna "undefined"
typeof null           // Retorna "object"
```

**Nota**: En JavaScript, `null` es un valor primitivo. Sin embargo, `typeof` devuelve "object". Este es un bug conocido en JavaScript que tiene razones históricas.

### Tipos de datos complejos

Un tipo de dato complejo puede almacenar múltiples valores y/o diferentes tipos de datos juntos. Puedes pensar en esto como una ensalada de frutas, donde cada tipo de fruta puede ser diferente, pero todas están juntas en un solo plato.

JavaScript tiene **un tipo de dato complejo**:

- **object**: Un contenedor para almacenar datos en pares clave-valor.

Todos los demás tipos complejos, como arreglos, funciones, conjuntos y mapas, son solo diferentes tipos de objetos.

El operador `typeof` solo devuelve dos tipos para objetos:

- **object**
- **function**

### Ejemplo

```javascript
typeof {name:'John'}   // Retorna "object"
typeof [1,2,3,4]       // Retorna "object"
typeof new Map()       // Retorna "object"
typeof new Set()       // Retorna "object"
typeof function (){}   // Retorna "function"
```

**Nota**: El operador `typeof` devuelve "object" para todos los tipos de objetos:

- objetos
- arreglos
- conjuntos
- mapas

No puedes usar `typeof` para determinar si un objeto en JavaScript es un arreglo o una fecha.

### Cómo reconocer un arreglo

¿Cómo saber si una variable es un arreglo? 

ECMAScript 5 (2009) definió un nuevo método para esto: `Array.isArray()`.

### Ejemplo

```javascript
// Crear un arreglo
const frutas = ["manzanas", "bananas", "naranjas"];
Array.isArray(frutas); // Retorna true
```

### El operador instanceof

El operador `instanceof` devuelve `true` si un objeto es una instancia de un tipo de objeto especificado. Es como si tu amigo te dijera si la criatura que tienes es un perro o un gato.

### Ejemplos

```javascript
// Crear una fecha
const tiempo = new Date();
console.log(tiempo instanceof Date); // Retorna true

// Crear un arreglo
const frutas = ["manzanas", "bananas", "naranjas"];
console.log(frutas instanceof Array); // Retorna true

// Crear un mapa
const frutas = new Map([
  ["manzanas", 500],
  ["bananas", 300],
  ["naranjas", 200]
]);
console.log(frutas instanceof Map); // Retorna true

// Crear un conjunto
const frutas = new Set(["manzanas", "bananas", "naranjas"]);
console.log(frutas instanceof Set); // Retorna true
```

### Variables indefinidas

El `typeof` de una variable indefinida es "undefined". 

### Ejemplo

```javascript
typeof coche; // Retorna "undefined"
```

El `typeof` de una variable sin valor es también "undefined".

### Ejemplo

```javascript
let coche;
typeof coche; // Retorna "undefined"
```

Cualquier variable puede ser vaciada asignando el valor `undefined`.

### Ejemplo

```javascript
let coche = "Volvo";
coche = undefined; // Ahora el valor es undefined
```

### Valores vacíos

Un valor vacío no tiene nada que ver con `undefined`. 

Una cadena vacía tiene tanto un valor legal como un tipo.

### Ejemplo

```javascript
let coche = "";
typeof coche; // Retorna "string"
```

### Null

En JavaScript, `null` es "nada". Se supone que es algo que no existe. Desafortunadamente, en JavaScript, el tipo de dato de `null` es un objeto.

Puedes vaciar un objeto asignándole `null`.

### Ejemplo

```javascript
// Crear un objeto
let persona = {nombre: "Juan", apellido: "Doe", edad: 50, colorOjos: "azul"};
persona = null; // Ahora el valor es null, pero el tipo sigue siendo "object"
```

También puedes vaciar un objeto asignándole `undefined`.

### Ejemplo

```javascript
let persona = {nombre: "Juan", apellido: "Doe", edad: 50, colorOjos: "azul"};
persona = undefined; // Ahora tanto el valor como el tipo son "undefined"
```

### Diferencia entre Undefined y Null

`undefined` y `null` son iguales en valor, pero diferentes en tipo:

```javascript
typeof undefined      // "undefined"
typeof null           // "object"

null === undefined    // false
null == undefined     // true
```

### La propiedad constructor

La propiedad `constructor` devuelve la función constructora para todas las variables de JavaScript.

### Ejemplo

```javascript
// Retorna la función Object():
{name:'Juan', edad:34}.constructor

// Retorna la función Array():
[1,2,3,4].constructor

// Retorna la función Date():
new Date().constructor

// Retorna la función Set():
new Set().constructor

// Retorna la función Map():
new Map().constructor

// Retorna la función Function():
function () {}.constructor
```

Con el constructor, puedes verificar si un objeto es un arreglo:

### Ejemplo

```javascript
(myArray.constructor === Array); // Retorna true si es un arreglo
```

Con el constructor, también puedes verificar si un objeto es una fecha:

### Ejemplo

```javascript
(myDate.constructor === Date); // Retorna true si es una fecha
```

### Todo junto

```javascript
typeof "Juan"          // Retorna "string"
typeof ("Juan" + "Doe") // Retorna "string"
typeof 3.14            // Retorna "number"
typeof (33 + 66)       // Retorna "number"
typeof NaN             // Retorna "number"
typeof 1234n           // Retorna "bigint"
typeof true            // Retorna "boolean"
typeof false           // Retorna "boolean"
typeof {nombre:'Juan'} // Retorna "object"
typeof [1,2,3,4]       // Retorna "object"
typeof {}              // Retorna "object"
typeof []              // Retorna "object"
typeof new Object()    // Retorna "object"
typeof new Array()     // Retorna "object"
typeof new Date()      // Retorna "object"
typeof new Set()       // Retorna "object"
typeof new Map()       // Retorna "object"
typeof function () {}  // Retorna "function"
typeof x               // Retorna "undefined"
typeof null            // Retorna "object"
```

**Nota**: ¡El tipo de dato de `NaN` (Not a Number) es `number`!

### El operador void

El operador `void` evalúa una expresión y devuelve `undefined`. Este operador se usa a menudo para obtener el valor primitivo `undefined`, utilizando `void(0)` (útil cuando evalúas una expresión sin usar el valor de retorno).

### Ejemplo

```html
<a href="javascript:void(0);">
  Enlace inútil
</a>

<a href="javascript:void(document.body.style.backgroundColor='red');">
  Haz clic aquí para cambiar el color de fondo a rojo
</a>
```

---

# JavaScript Type Conversion

JavaScript es un lenguaje que permite cambiar el tipo de las variables de manera flexible. Este proceso se llama **Conversión de Tipo**. Imagina que tienes un conjunto de piezas de lego. Algunas son cuadrados, otras son rectángulos y otras son triángulos. En JavaScript, puedes transformar esas piezas (variables) en otras formas (tipos de datos) según lo necesites. Aquí te explico cómo funciona esto:

## Conversión de Cadenas a Números

La función global `Number()` convierte una variable (o un valor) en un número.

- Una cadena numérica (como "3.14") se convierte en un número (como 3.14).
- Una cadena vacía (como "") se convierte en 0.
- Una cadena no numérica (como "John") se convierte en NaN (Not a Number).

### Ejemplos

Estos convertirá:

```javascript
Number("3.14") // 3.14
Number(Math.PI) // 3.14159
Number(" ")    // 0
Number("")     // 0
```

Estos no convertirá:

```javascript
Number("99 88") // NaN
Number("John")  // NaN
```

### Métodos de Número

En el capítulo de Métodos de Número, encontrarás más métodos que pueden utilizarse para convertir cadenas a números:

| Método         | Descripción                                    |
|----------------|------------------------------------------------|
| `Number()`     | Devuelve un número, convertido desde su argumento |
| `parseFloat()` | Analiza una cadena y devuelve un número de punto flotante |
| `parseInt()`   | Analiza una cadena y devuelve un entero       |

### El Operador Unario +

El operador unario `+` se puede utilizar para convertir una variable en un número.

#### Ejemplo

```javascript
let y = "5";      // y es una cadena
let x = +y;      // x es un número
```

Si la variable no puede ser convertida, se convertirá en NaN:

```javascript
let y = "John";   // y es una cadena
let x = +y;      // x es un número (NaN)
```

## Conversión de Números a Cadenas

El método global `String()` puede convertir números a cadenas.

Se puede utilizar en cualquier tipo de números, literales, variables o expresiones:

### Ejemplo

```javascript
String(x)         // devuelve una cadena de la variable numérica x
String(123)       // devuelve una cadena del literal numérico 123
String(100 + 23)  // devuelve una cadena del número de una expresión
```

El método `toString()` de Number hace lo mismo.

### Ejemplo

```javascript
x.toString()        // convierte x a cadena
(123).toString()    // convierte 123 a cadena
(100 + 23).toString() // convierte el resultado a cadena
```

### Más Métodos

En el capítulo de Métodos de Número, encontrarás más métodos para convertir números a cadenas:

| Método               | Descripción                                           |
|----------------------|-------------------------------------------------------|
| `toExponential()`    | Devuelve una cadena, con un número redondeado y escrito en notación exponencial |
| `toFixed()`          | Devuelve una cadena, con un número redondeado y escrito con un número especificado de decimales |
| `toPrecision()`      | Devuelve una cadena, con un número escrito con una longitud especificada |

## Conversión de Fechas a Números

El método global `Number()` también se puede utilizar para convertir fechas a números.

```javascript
let d = new Date();
Number(d)          // devuelve 1404568027739
```

El método `getTime()` de Date hace lo mismo.

```javascript
let d = new Date();
d.getTime()        // devuelve 1404568027739
```

## Conversión de Fechas a Cadenas

El método global `String()` puede convertir fechas a cadenas.

```javascript
String(Date())  // devuelve "Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)"
```

El método `toString()` de Date hace lo mismo.

### Ejemplo

```javascript
Date().toString()  // devuelve "Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)"
```

### Más Métodos

En el capítulo de Métodos de Fecha, encontrarás más métodos para convertir fechas a cadenas:

| Método               | Descripción                                       |
|----------------------|---------------------------------------------------|
| `getDate()`          | Obtiene el día como un número (1-31)              |
| `getDay()`           | Obtiene el día de la semana como un número (0-6)  |
| `getFullYear()`      | Obtiene el año de cuatro dígitos (yyyy)           |
| `getHours()`         | Obtiene la hora (0-23)                             |
| `getMilliseconds()`   | Obtiene los milisegundos (0-999)                   |
| `getMinutes()`       | Obtiene los minutos (0-59)                         |
| `getMonth()`         | Obtiene el mes (0-11)                              |
| `getSeconds()`       | Obtiene los segundos (0-59)                        |
| `getTime()`          | Obtiene el tiempo (milisegundos desde el 1 de enero de 1970) |

## Conversión de Booleanos a Números

El método global `Number()` también puede convertir booleanos a números.

```javascript
Number(false)     // devuelve 0
Number(true)      // devuelve 1
```

## Conversión de Booleanos a Cadenas

El método global `String()` puede convertir booleanos a cadenas.

```javascript
String(false)      // devuelve "false"
String(true)       // devuelve "true"
```

El método `toString()` de Boolean hace lo mismo.

```javascript
false.toString()   // devuelve "false"
true.toString()    // devuelve "true"
```

## Conversión de Tipo Automática

Cuando JavaScript intenta operar con un tipo de dato "incorrecto", intenta convertir el valor al tipo "correcto". 

El resultado no siempre es el esperado:

```javascript
5 + null    // devuelve 5         porque null se convierte en 0
"5" + null  // devuelve "5null"   porque null se convierte en "null"
"5" + 2     // devuelve "52"      porque 2 se convierte en "2"
"5" - 2     // devuelve 3         porque "5" se convierte en 5
"5" * "2"   // devuelve 10        porque "5" y "2" se convierten en 5 y 2
```

## Conversión Automática a Cadena

JavaScript llama automáticamente a la función `toString()` de la variable cuando intentas "salir" un objeto o una variable:

```javascript
document.getElementById("demo").innerHTML = myVar;

// si myVar = {name:"Fjohn"}  // toString convierte a "[object Object]"
// si myVar = [1,2,3,4]       // toString convierte a "1,2,3,4"
// si myVar = new Date()      // toString convierte a "Fri Jul 18 2014 09:08:55 GMT+0200"

// los números y booleanos también se convierten, pero esto no es muy visible:
// si myVar = 123             // toString convierte a "123"
// si myVar = true            // toString convierte a "true"
// si myVar = false           // toString convierte a "false"
```

## Tabla de Conversión de Tipo en JavaScript

Esta tabla muestra el resultado de convertir diferentes valores de JavaScript a Número, Cadena y Booleano:

| Valor Original       | Convertido a Número | Convertido a Cadena | Convertido a Booleano |
|----------------------|----------------------|----------------------|------------------------|
| false                | 0                    | "false"              | false                  |
| true                 | 1                    | "true"               | true                   |
| 0                    | 0                    | "0"                  | false                  |
| 1                    | 1                    | "1"                  | true                   |
| "0"                  | 0                    | "0"                  | true                   |
| "000"                | 0                    | "000"                | true                   |
| "1"                  | 1                    | "1"                  | true                   |
| NaN                  | NaN                  | "NaN"                | false                  |
| Infinity             | Infinity             | "Infinity"           | true                   |
| -Infinity            | -Infinity            | "-Infinity"          | true                   |
| ""                   | 0                    | ""                   | false                  |
| "20"                 | 20                   | "20"                 | true                   |
| "twenty"             | NaN                  | "twenty"             | true                   |
| [ ]                  | 0                    | ""                   | true                   |
| [20]                 | 20                   | "20"                 | true                   |
| [10,20]             | NaN                  | "10,20"              | true                   |
| ["twenty"]

          | NaN                  | "twenty"             | true                   |
| { }                  | NaN                  | "[object Object]"    | true                   |
| { x:20 }            | NaN                  | "[object Object]"    | true                   |

## Conclusión

La conversión de tipo en JavaScript es un proceso fundamental que te permite manipular datos de manera flexible y dinámica. Entender cómo funciona puede ayudarte a evitar errores y a escribir un código más eficiente. ¡Sigue explorando y practicando!

---

# JavaScript Destructuring

Destructuring is a powerful feature in JavaScript that allows you to unpack values from arrays or properties from objects into distinct variables. To illustrate this concept, consider the following analogies and examples.

## Destructuring Assignment Syntax

The destructuring assignment syntax allows us to extract values from objects or arrays and assign them to variables, making our code cleaner and more readable.

### Analogía: Desempaquetar una Caja

Imagina que tienes una caja con varios compartimentos. Cada compartimento contiene un objeto (o un valor) que deseas usar. Destructuring es como abrir la caja y tomar los objetos directamente de cada compartimento sin tener que buscarlos uno por uno.

**Ejemplo de Destructuración de Objetos:**

```javascript
// Crear un objeto
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50
};

// Desestructuración
let { firstName, lastName } = person;
```

**Nota:** El orden de las propiedades no importa:

```javascript
// Desestructuración
let { lastName, firstName } = person;
```

> **Nota Importante:** Destructuring no es destructivo; no cambia el objeto original.

## Valores Predeterminados en Objetos

A veces, puede que una propiedad no exista en el objeto. Para manejar esto, podemos establecer valores predeterminados.

### Analogía: Una Fiesta Sorpresa

Supón que organizas una fiesta sorpresa, pero algunos invitados no pueden asistir. Puedes planear un “invitado de reserva” que se presente en su lugar.

**Ejemplo:**

```javascript
// Crear un objeto
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50
};

// Desestructuración con valor predeterminado
let { firstName, lastName, country = "US" } = person;
```

## Alias de Propiedades de Objetos

A veces, queremos renombrar las propiedades al desestructurarlas.

### Analogía: Cambiar el Nombre de un Producto

Imagina que vendes un producto que se llama "gafas de sol", pero en tu tienda lo llamas "accesorio de verano". Al desestructurar, puedes darle un nuevo nombre a la propiedad.

**Ejemplo:**

```javascript
// Crear un objeto
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50
};

// Desestructuración con alias
let { lastName: name } = person;
```

## Desestructuración de Cadenas

La desestructuración también se puede usar para desempaquetar caracteres de cadenas.

### Analogía: Separar Letras de un Nombre

Imagina que tienes una bolsa con letras y quieres sacar algunas para formar un nombre.

**Ejemplo:**

```javascript
// Crear una cadena
let name = "W3Schools";

// Desestructuración
let [a1, a2, a3, a4, a5] = name;
```

## Desestructuración de Arreglos

Podemos extraer valores de arreglos y asignarlos a nuestras propias variables.

### Analogía: Seleccionar Frutas de una Canasta

Si tienes una canasta llena de frutas, puedes seleccionar algunas directamente.

**Ejemplo:**

```javascript
// Crear un arreglo
const fruits = ["Bananas", "Oranges", "Apples", "Mangos"];

// Desestructuración
let [fruit1, fruit2] = fruits;
```

### Omitiendo Valores del Arreglo

Si quieres omitir algunos valores, puedes usar comas.

**Ejemplo:**

```javascript
// Crear un arreglo
const fruits = ["Bananas", "Oranges", "Apples", "Mangos"];

// Desestructuración
let [fruit1, , , fruit2] = fruits;
```

### Valores de Posición en el Arreglo

Puedes seleccionar valores de posiciones específicas del arreglo.

**Ejemplo:**

```javascript
// Crear un arreglo
const fruits = ["Bananas", "Oranges", "Apples", "Mangos"];

// Desestructuración
let { [0]: fruit1, [1]: fruit2 } = fruits;
```

## La Propiedad Rest

Puedes finalizar una sintaxis de desestructuración con una propiedad rest, que almacena todos los valores restantes en un nuevo arreglo.

### Analogía: Agrupar Todo lo Que Sobra

Imagina que al final de una fiesta, decides agrupar todos los juguetes sobrantes en una caja.

**Ejemplo:**

```javascript
// Crear un arreglo
const numbers = [10, 20, 30, 40, 50, 60, 70];

// Desestructuración
const [a, b, ...rest] = numbers;
```

## Desestructuración de Maps

También puedes usar la desestructuración con objetos `Map`.

### Analogía: Un Menú de Restaurante

Imagina un menú donde cada plato tiene un precio. Puedes iterar sobre el menú y extraer los nombres y precios de los platos.

**Ejemplo:**

```javascript
// Crear un Map
const fruits = new Map([
  ["apples", 500],
  ["bananas", 300],
  ["oranges", 200]
]);

// Desestructuración
let text = "";
for (const [key, value] of fruits) {
  text += key + " es " + value + "\n";
}
```

## Intercambiando Variables en JavaScript

Puedes intercambiar los valores de dos variables usando una asignación de desestructuración.

### Analogía: Cambiar de Ropa

Si decides intercambiar camisetas con un amigo, simplemente te las quitas y se las das.

**Ejemplo:**

```javascript
let firstName = "John";
let lastName = "Doe";

// Desestructuración
[firstName, lastName] = [lastName, firstName];
```

---

