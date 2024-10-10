# Árbol DOM

La columna vertebral de un documento HTML son las etiquetas.

Según el Modelo de Objetos del Documento (DOM), cada etiqueta HTML es un objeto. Las etiquetas anidadas son "hijas" de la que las envuelve. El texto dentro de una etiqueta también es un objeto.

Todos estos objetos son accesibles mediante JavaScript, y podemos usarlos para modificar la página.

Por ejemplo, `document.body` es el objeto que representa la etiqueta `<body>`.

Ejecutar este código hará que el `<body>` se vuelva rojo durante 3 segundos:

```javascript
document.body.style.background = 'red'; // hacer el fondo rojo
setTimeout(() => document.body.style.background = '', 3000); // volver
```

Aquí usamos `style.background` para cambiar el color de fondo de `document.body`, pero hay muchas otras propiedades, como:

- `innerHTML` – contenido HTML del nodo.
- `offsetWidth` – ancho del nodo (en píxeles).
- …y así sucesivamente.

Pronto aprenderemos más formas de manipular el DOM, pero primero necesitamos conocer su estructura.

## Un Ejemplo del DOM

Comencemos con el siguiente documento simple:

```html
<!DOCTYPE HTML>
<html>
<head>
  <title>Acerca de los alces</title>
</head>
<body>
  La verdad sobre los alces.
</body>
</html>
```

El DOM representa HTML como una estructura de árbol de etiquetas. Así es como se ve:

```
▾
HTML
▾
HEAD
#text ↵␣␣
▾
TITLE
#text Acerca de los alces
#text ↵
#text ↵
▾
BODY
#text ↵␣␣La verdad sobre los alces.↵
```

En la imagen de arriba, puedes hacer clic en los nodos de elementos, y sus hijos se abrirán o colapsarán.

Cada nodo del árbol es un objeto.

Las etiquetas son nodos de elemento (o simplemente elementos) y forman la estructura del árbol: `<html>` está en la raíz, luego `<head>` y `<body>` son sus hijos, etc.

El texto dentro de los elementos forma nodos de texto, etiquetados como `#text`. Un nodo de texto contiene solo una cadena. Puede no tener hijos y siempre es una hoja del árbol.

Por ejemplo, la etiqueta `<title>` tiene el texto "Acerca de los alces".

Ten en cuenta los caracteres especiales en los nodos de texto:

- un salto de línea: ↵ (en JavaScript se conoce como `\n`)
- un espacio: ␣

Los espacios y saltos de línea son caracteres totalmente válidos, como letras y dígitos. Forman nodos de texto y se convierten en parte del DOM. Entonces, por ejemplo, en el ejemplo anterior, la etiqueta `<head>` contiene algunos espacios antes de `<title>`, y ese texto se convierte en un nodo `#text` (contiene un salto de línea y algunos espacios solamente).

### Exclusiones de Nivel Superior

Solo hay dos exclusiones de nivel superior:

1. Los espacios y saltos de línea antes de `<head>` se ignoran por razones históricas.
2. Si ponemos algo después de `</body>`, entonces eso se mueve automáticamente dentro del cuerpo, al final, ya que la especificación HTML requiere que todo el contenido debe estar dentro de `<body>`. Por lo tanto, no puede haber espacios después de `</body>`.

En otros casos, todo es sencillo: si hay espacios (al igual que cualquier carácter) en el documento, entonces se convierten en nodos de texto en el DOM, y si los eliminamos, no quedará ninguno.

### Sin Nodos de Texto Solo con Espacios

Aquí no hay nodos de texto solo con espacios:

```html
<!DOCTYPE HTML>
<html><head><title>Acerca de los alces</title></head><body>La verdad sobre los alces.</body></html>
```

```
▾
HTML
▾
HEAD
▾
TITLE
#text Acerca de los alces
▾
BODY
#text La verdad sobre los alces.
```

Los espacios al principio y al final de la cadena y los nodos de texto solo con espacios suelen estar ocultos en las herramientas. Las herramientas del navegador (que cubriremos pronto) que trabajan con el DOM generalmente no muestran los espacios al principio/final del texto y los nodos de texto vacíos (saltos de línea) entre etiquetas.

Las herramientas para desarrolladores ahorran espacio en la pantalla de esta manera.

En las próximas imágenes del DOM, a veces omitiremos estos nodos cuando sean irrelevantes. Dichos espacios generalmente no afectan cómo se muestra el documento.

### Autocorrección

Si el navegador encuentra HTML mal formado, lo corrige automáticamente al crear el DOM.

Por ejemplo, la etiqueta superior siempre es `<html>`. Incluso si no existe en el documento, existirá en el DOM porque el navegador la creará. Lo mismo ocurre con `<body>`.

Como ejemplo, si el archivo HTML es la única palabra "Hola", el navegador lo envolverá en `<html>` y `<body>`, y añadirá el `<head>` requerido, y el DOM será:

```
▾
HTML
▾
HEAD
▾
BODY
▾
#text Hola
```

Mientras genera el DOM, los navegadores procesan automáticamente errores en el documento, cierran etiquetas, etc.

### Ejemplo con Etiquetas Sin Cerrar

Un documento con etiquetas sin cerrar:

```html
<p>Hola
<li>Mamá
<li>y
<li>Papá
```

…se convertirá en un DOM normal ya que el navegador lee las etiquetas y restaura las partes que faltan:

```
▾
HTML
▾
HEAD
▾
BODY
▾
P
#text Hola
▾
LI
#text Mamá
▾
LI
#text y
▾
LI
#text Papá
```

### Las Tablas Siempre Tienen `<tbody>`

Un “caso especial” interesante son las tablas. Según la especificación del DOM, deben tener una etiqueta `<tbody>`, pero el texto HTML puede omitirla. Entonces, el navegador crea `<tbody>` en el DOM automáticamente.

Para el HTML:

```html
<table id="tabla"><tr><td>1</td></tr></table>
```

La estructura del DOM será:

```
▾
TABLE
▾
TBODY
▾
TR
▾
TD
#text 1
```

¿Lo ves? El `<tbody>` apareció de la nada. Debemos tener esto en cuenta al trabajar con tablas para evitar sorpresas.

### Otros Tipos de Nodos

Además de los elementos y los nodos de texto, hay otros tipos de nodos.

Por ejemplo, los comentarios:

```html
<!DOCTYPE HTML>
<html>
<body>
  La verdad sobre los alces.
  <ol>
    <li>Un alce es inteligente</li>
    <!-- comentario -->
    <li>...y un animal astuto!</li>
  </ol>
</body>
</html>
```

```
▾
HTML
▾
HEAD
▾
BODY
#text ↵␣␣La verdad sobre los alces.↵␣␣
▾
OL
#text ↵␣␣␣␣
▾
LI
#text Un alce es inteligente
#text ↵␣␣␣␣
#comment comentario
#text ↵␣␣␣␣
▾
LI
#text ...y un animal astuto!
#text ↵␣␣
#text ↵↵↵
```

Aquí podemos ver un nuevo tipo de nodo en el árbol: el nodo de comentario, etiquetado como `#comment`, entre dos nodos de texto.

Podemos pensar: ¿por qué se añade un comentario al DOM? No afecta la representación visual de ninguna manera. Pero hay una regla: si algo está en HTML, también debe estar en el árbol DOM.

Todo en HTML, incluso los comentarios, se convierte en parte del DOM.

Incluso la directiva `<!DOCTYPE...>` al principio de HTML también es un nodo del DOM. Está en el árbol DOM justo antes de `<html>`. Pocas personas saben esto. No vamos a tocar ese nodo; ni siquiera lo dibujamos en los diagramas, pero está ahí.

El objeto documento que representa todo el documento es, formalmente, un nodo del DOM también.

### Resumen de Tipos de Nodos

Hay 12 tipos de nodos. En la práctica, generalmente trabajamos con 4 de ellos:

- **documento** – el "punto de entrada" al DOM.
- **nodos de elemento** – etiquetas HTML, los bloques de construcción del árbol.
- **nodos de texto** – contienen texto.
- **comentarios** – a veces podemos poner información allí; no se mostrará, pero JS puede leerla del DOM.

## Velo Por Ti Mismo

Para ver la estructura del DOM en tiempo real, prueba [Live DOM Viewer](https://live.domviewer.com). Simplemente escribe en el documento y aparecerá como un DOM al instante.

Otra forma de explorar el DOM es utilizar las herramientas de desarrollador del navegador. De hecho, eso es lo que usamos al

 hacer clic derecho en un elemento y seleccionar la opción “Inspeccionar”. ¡Intenta explorar el DOM, es muy útil!

## Conclusión

El árbol DOM es un concepto crucial para el desarrollo web. Comprender su estructura y cómo representa el HTML te ayudará a manipular páginas web dinámicamente con JavaScript.

Este documento proporcionó una visión general básica del árbol DOM y algunas de sus características esenciales. A medida que continúes aprendiendo sobre el desarrollo web, encontrarás que el DOM es una herramienta poderosa para crear aplicaciones web interactivas y dinámicas.