# Cómo Funcionan los Navegadores

## Introducción

Los navegadores web son el software más utilizado. En este manual, explico cómo trabajan detrás de escena. Veremos lo que sucede cuando escribes `google.com` en la barra de direcciones hasta que ves la página de Google en la pantalla del navegador.

### Navegadores de los que hablaremos

En la actualidad, se utilizan cinco navegadores principales en las computadoras de escritorio: Chrome, Internet Explorer, Firefox, Safari y Opera. En los dispositivos móviles, los principales navegadores son el navegador Android, iPhone, Opera Mini y Opera Mobile, el navegador UC, los navegadores Nokia S40/S60 y Chrome. Todos estos navegadores, excepto los Opera, se basan en WebKit. Proporcionaré ejemplos de los navegadores de código abierto Firefox y Chrome, y Safari (que es parcialmente de código abierto). Según las estadísticas de StatCounter (hasta junio de 2013), Chrome, Firefox y Safari representan alrededor del 71% del uso global de navegadores de escritorio. En los dispositivos móviles, el navegador Android, iPhone y Chrome constituyen alrededor del 54% del uso.

## La Funcionalidad Principal del Navegador

La función principal de un navegador es presentar el recurso web que elijas solicitándolo al servidor y mostrándolo en la ventana del navegador. Por lo general, el recurso es un documento HTML, pero también puede ser un PDF, una imagen o algún otro tipo de contenido. El usuario especifica la ubicación del recurso mediante un URI (identificador uniforme de recursos).

La manera en que el navegador interpreta y muestra los archivos HTML se especifica en las especificaciones HTML y CSS. La organización W3C (World Wide Web Consortium), que es la organización de estándares para la Web, mantiene estas especificaciones. Durante años, los navegadores se adaptaron a solo una parte de las especificaciones y desarrollaron sus propias extensiones, lo que provocó graves problemas de compatibilidad para los autores web. En la actualidad, la mayoría de los navegadores se ajustan en mayor o menor medida a las especificaciones.

Las interfaces de usuario de los navegadores tienen mucho en común. Entre los elementos comunes de la interfaz de usuario, se encuentran los siguientes:

- Barra de direcciones para insertar un URI
- Botones para retroceder y avanzar
- Opciones para agregar a favoritos
- Botones de actualización y detención para actualizar o detener la carga de documentos actuales
- Botón de inicio que te lleva a la página principal

Curiosamente, la interfaz de usuario del navegador no está especificada en ninguna especificación formal, sino que proviene de buenas prácticas formadas a lo largo de años de experiencia y de que los navegadores se imitan entre sí. La especificación HTML5 no define los elementos de la interfaz de usuario que debe tener un navegador, sino que enumera algunos elementos comunes. Entre ellos, se encuentran la barra de direcciones, la barra de estado y la barra de herramientas. Por supuesto, existen funciones exclusivas de un navegador específico, como el administrador de descargas de Firefox.

## Infraestructura de Alto Nivel

Los componentes principales del navegador son los siguientes:

1. **Interfaz de Usuario**: Incluye la barra de direcciones, el botón Atrás/Adelante, el menú de favoritos, etc. Se muestran todas las partes del navegador, excepto la ventana donde ves la página solicitada.
2. **El Motor del Navegador**: Ordena las acciones entre la IU y el motor de renderización.
3. **El Motor de Renderización**: Es responsable de mostrar el contenido solicitado. Por ejemplo, si el contenido solicitado es HTML, el motor de renderización analiza HTML y CSS, y muestra el contenido analizado en la pantalla.
4. **Herramientas de Redes**: Para llamadas de red, como solicitudes HTTP, mediante diferentes implementaciones para diferentes plataformas detrás de una interfaz independiente de la plataforma.
5. **Backend de la IU**: Se usa para dibujar widgets básicos, como ventanas y cuadros combinados. Este backend expone una interfaz genérica que no es específica de la plataforma. Debajo, se usan los métodos de la interfaz de usuario del sistema operativo.
6. **Intérprete de JavaScript**: Se usa para analizar y ejecutar código JavaScript.
7. **Almacenamiento de Datos**: Esta es una capa de persistencia. Es posible que el navegador deba guardar todo tipo de datos de forma local, como las cookies. Los navegadores también admiten mecanismos de almacenamiento como localStorage, IndexedDB, WebSQL y FileSystem.

## Motores de Renderización

La responsabilidad del motor de renderización es bien... la renderización, que es mostrar el contenido solicitado en la pantalla del navegador.

De forma predeterminada, el motor de procesamiento puede mostrar imágenes y documentos HTML y XML. Puede mostrar otros tipos de datos a través de complementos o extensiones, por ejemplo, para mostrar documentos PDF con un complemento de lector de PDF. Sin embargo, en este capítulo nos enfocaremos en el caso de uso principal: mostrar imágenes y HTML con formato CSS.

Los diferentes navegadores utilizan distintos motores de representación: Internet Explorer usa Trident, Firefox usa Gecko y Safari usa WebKit. Chrome y Opera (de la versión 15) utilizan Blink, una horquilla de WebKit.

**Analogía:** Imagina que el motor de renderización es como el pintor de una casa. El pintor recibe las instrucciones (HTML y CSS) sobre cómo debe verse la casa y se encarga de pintar cada pared y habitación (renderizar el contenido) según esas instrucciones.

WebKit es un motor de renderización de código abierto que comenzó como un motor para la plataforma Linux y que Apple modificó para ser compatible con Mac y Windows.

### El Flujo Principal

El motor de renderización comenzará a obtener el contenido del documento solicitado de la capa de red. Por lo general, esto se hace en fragmentos de 8 KB.

**Analogía:** Piensa en el motor de renderización como un chef que está cocinando una receta. El chef no recibe todos los ingredientes de una vez; en cambio, los recibe en partes (fragmentos) y comienza a cocinar mientras sigue recibiendo más ingredientes.

A continuación, este es el flujo básico del motor de renderización:

1. **Análisis**: El motor de renderización comenzará a analizar el documento HTML y convertirá los elementos en nodos DOM en un árbol denominado "árbol de contenido".
2. **Estilo**: El motor analizará los datos de estilo, tanto en archivos CSS externos como en elementos de estilo. La información de estilo junto con las instrucciones visuales en el código HTML se usará para crear otro árbol: el árbol de renderización.
3. **Diseño**: El árbol de renderización contiene rectángulos con atributos visuales, como el color y las dimensiones. Los rectángulos están en el orden correcto para que se muestren en la pantalla.
4. **Painting (Pintura)**: Se recorrerá el árbol de renderización y se pintará cada nodo con la capa de backend de la IU.

**Analogía:** Imagina que el análisis es como leer la receta (documento HTML), el estilo es como elegir los colores de las pinturas (CSS), el diseño es como planificar la distribución de los muebles en la habitación, y la pintura es el acto de pintar las paredes y colocar los muebles en el lugar correcto.

Es importante que entiendas que este es un proceso gradual. Para mejorar la experiencia del usuario, el motor de renderización intentará mostrar contenido en la pantalla lo antes posible. No esperará hasta que se analice todo el HTML para comenzar a compilar y diseñar el árbol de representación. Se analizarán y se mostrarán partes del contenido, mientras que el proceso continúa con el resto del contenido que continúa procediendo de la red.

## Análisis: General

Dado que las aplicaciones web modernas son tan complejas y pueden tener mucha interacción de usuario, es fundamental comprender que el análisis puede no ser lineal. Además, debido a la forma en que los navegadores representan y optimizan el contenido, los flujos de trabajo internos pueden variar entre los navegadores. El enfoque descrito aquí es una simplificación del proceso real y no toma en cuenta todas las optimizaciones o particularidades que pueden ocurrir.

## Analizador HTML

### ¿Qué Hace un Analizador HTML?

Imagina que el analizador HTML es como un lector de recetas de cocina. Este lector toma una receta escrita en un formato específico (HTML) y la convierte en un formato más comprensible, como una lista de ingredientes y pasos a seguir.

### Gramática HTML

La gramática HTML es como un conjunto de reglas para escribir recetas. Estas reglas, definidas por la organización W3C, dictan cómo deben ser las recetas (en este caso, los documentos HTML). Así como una receta tiene ingredientes y pasos específicos, HTML tiene etiquetas y atributos.

### Diferencias con XML

A diferencia de XML, que es muy estricto (como un libro de recetas que no permite variaciones), HTML es más flexible (como un libro de recetas que permite sustituciones). HTML permite ciertos errores y omisiones, lo que facilita la vida del autor pero hace más difícil la definición formal.

### DTD de HTML

El DTD (Definición del Tipo de Documento) es como un libro de recetas que describe qué ingredientes (etiquetas) están permitidos y cómo deben estar organizados. Aunque HTML no es exactamente una gramática libre de contexto, el DTD define las reglas básicas para la estructura HTML.

## DOM (Document Object Model)

### ¿Qué es el DOM?

El DOM es como una representación visual de la receta una vez que está cocinada. Si HTML es la receta cruda, el DOM es el platillo final. El DOM organiza los elementos HTML en un árbol, donde cada nodo representa una parte de la receta (etiquetas y atributos).

### Ejemplo del DOM

Para un documento HTML simple como:

```html
<html>
  <body>
    <p>Hello World</p>
    <div><img src="example.png"/></div>
  </body>
</html>
```

El árbol del DOM se vería así:

```
Document
│
├── html
│   └── body
│       ├── p ("Hello World")
│       └── div
│           └── img (src="example.png")
```

### Especificación del DOM

El DOM está definido por la W3C y proporciona una interfaz para manipular documentos HTML y XML. Cada nodo del árbol DOM representa un objeto del documento.

## Algoritmo de Análisis

### ¿Cómo Funciona el Análisis?

Analizar HTML es como leer una receta paso a paso y luego organizar los ingredientes en la cocina. HTML no sigue una gramática formal rígida, por lo que se utilizan técnicas especializadas para analizarlo.

### Etapas del Análisis

1. **Asignación de Tokens**: Imagina que esta etapa es como identificar ingredientes y pasos en una receta. Se reconocen las etiquetas y atributos HTML y se transforman en tokens.
   
2. **Construcción del Árbol**: Aquí, los tokens se organizan en un árbol del DOM. Es como organizar los ingredientes en la cocina para preparar el platillo.

### Ejemplo de Asignación de Tokens

Para el HTML:

```html
<html>
  <body>
    Hello world
  </body>
</html>
```

El proceso de asignación de tokens sería:

- **Estado Inicial**: Leer el carácter `<` cambia al estado "Tag open".
- **Token de Etiqueta de Inicio**: Se crea un token para `<html>`.
- **Estado de Datos**: Leer "Hello world" crea un token de texto.
- **Token de Etiqueta de Fin**: Se crea un token para `</body>`, y así sucesivamente.

### Construcción del Árbol

En la construcción del árbol, los tokens se convierten en nodos del DOM. Por ejemplo:

- El token `<html>` crea un nodo `HTMLHtmlElement`.
- El token `<body>` crea un nodo `HTMLBodyElement`.

## Navegadores y Tolerancia a Errores

### ¿Cómo Manejan los Navegadores los Errores?

Imagina que en la cocina, si un ingrediente está mal medido, el chef lo ajusta sobre la marcha. Los navegadores hacen lo mismo con HTML. Corrigen errores y muestran el contenido de la mejor manera posible.

### Ejemplos de Tolerancia a Errores

- **Etiquetas Mal Escribas**: `<br>` en lugar de `</br>`.
- **Tablas Desviadas**: Una tabla dentro de otra no en una celda.

Los navegadores ajustan la estructura HTML para corregir estos errores y asegurar que la página se muestre correctamente.

## Análisis de CSS

### ¿Qué es CSS?

CSS es como el libro de recetas para la presentación. Mientras que HTML es la estructura, CSS define cómo se ve. La gramática de CSS se puede analizar formalmente, lo que facilita su procesamiento.

### Ejemplo de Gramática CSS

La gramática de CSS se define con expresiones regulares y BNF. Por ejemplo, para una regla CSS:

```css
div.error, a.error {
  color: red;
  font-weight: bold;
}
```

- **Selector**: `div.error, a.error`
- **Declaración**: `color: red; font-weight: bold;`

La gramática define cómo se combinan los selectores y las declaraciones.

# Construcción de Árbol de Renderización

Cuando tu navegador está listo para mostrar una página web, realiza una serie de pasos para convertir el código HTML y CSS en algo que puedas ver en la pantalla. Uno de los pasos más importantes es la construcción del **árbol de renderización**. Vamos a desglosar este proceso y usar algunas analogías para facilitar su comprensión.

## ¿Qué es el Árbol de Renderización?

Imagina que estás construyendo una maqueta de una ciudad en miniatura. Tienes planos (el HTML) y materiales (el CSS) para construir edificios, carreteras y parques. A medida que montas cada elemento, decides cómo se verá y en qué orden debe colocarse. El **árbol de renderización** es como el modelo final que ves en tu maqueta: representa cómo se deben mostrar los elementos en tu página web.

En el navegador, mientras construyes el **árbol del DOM** (Document Object Model), que es como un esquema de los elementos HTML en tu página, también se construye el árbol de renderización. Este árbol contiene todos los elementos visuales y en el orden en que se mostrarán.

- **Firefox** llama a los elementos en el árbol de renderización "marcos".
- **WebKit** (el motor de renderizado de Safari) usa el término "procesador" o "objeto de renderización".

### Analogía del Procesador de Renderización

Piensa en el procesador de renderización como un maestro constructor que sabe cómo diseñar y construir cada tipo de edificio en tu maqueta. Cada procesador se encarga de un área rectangular en la maqueta, como un bloque de apartamentos o un parque, y sabe cómo colocar sus elementos.

```cpp
class RenderObject {
  virtual void layout();  // Organiza el espacio del objeto
  virtual void paint(PaintInfo);  // Dibuja el objeto
  virtual void rect repaintRect();  // Define el área del objeto
  Node* node;  // Nodo del DOM
  RenderStyle* style;  // Estilo computado
  RenderLayer* containingLayer;  // Capa de z-index contenedora
}
```

En esta clase, `RenderObject` es como el maestro constructor que organiza y pinta los elementos en el área que le corresponde.

## Relación entre el Árbol de Renderización y el Árbol del DOM

No todos los nodos del DOM se convierten en elementos visuales. Imagina que en tu maqueta tienes planos para algunos elementos que no se construirán, como cimientos subterráneos. Estos no aparecerán en la maqueta final, al igual que los elementos del DOM con `display: none`.

Además, algunos elementos del DOM pueden corresponderse con varios elementos visuales. Por ejemplo, un elemento `<select>` puede ser representado por varios procesadores: uno para el área desplegable, uno para el botón y uno para la lista de opciones.

También, algunos elementos visuales se colocan en diferentes partes del árbol de renderización según su estilo. Los elementos con posición absoluta o flotante se colocan en lugares específicos, mientras que los demás siguen el flujo normal del documento.

### Analogía de la Ciudad

En tu maqueta de ciudad, los edificios (elementos visuales) no siempre se construyen en el mismo orden que en los planos (DOM). Algunos edificios pueden tener características especiales (como un parque en lugar de un rascacielos) y se colocan en diferentes áreas de la maqueta según sus características (estilos).

## Construcción del Árbol de Renderización

En **Firefox**, el proceso de construir el árbol de renderización se delega al `FrameConstructor`, que resuelve el estilo y crea los marcos (representadores) correspondientes. En **WebKit**, el proceso se llama "adjunto", donde cada nodo del DOM se convierte en un objeto de renderización.

La raíz del árbol de renderización corresponde al área visible de la ventana del navegador, y es donde se empiezan a construir todos los demás bloques.

### Analogía del Construcción

Imagina que el `FrameConstructor` es como un arquitecto que construye la estructura básica de la ciudad a partir de los planos. Luego, los trabajadores (procesadores de renderización) añaden los detalles a cada edificio según los planos y el estilo definido.

## Cálculo de Estilo

Para pintar cada elemento correctamente, el navegador necesita calcular cómo se deben aplicar los estilos CSS. Este proceso se conoce como **cálculo de estilo**.

El estilo de cada elemento se compone de varias fuentes: hojas de estilo del navegador, del autor de la página y del usuario. Estos estilos se calculan y se aplican en cascada, teniendo en cuenta reglas de prioridad y especificidad.

### Analogía de la Selección de Materiales

Cuando construyes un edificio en tu maqueta, decides qué materiales usar (por ejemplo, ladrillo o madera). Estos materiales se seleccionan de acuerdo con un conjunto de reglas y prioridades. De manera similar, el navegador selecciona las propiedades de estilo para cada elemento basándose en las reglas CSS.

## Cómo Compartir Datos de Estilo

En WebKit, los nodos del DOM pueden compartir objetos de estilo (`RenderStyle`) si cumplen con ciertas condiciones, como tener el mismo estado del mouse, clase o atributos. Esto ayuda a optimizar el rendimiento al evitar cálculos repetidos.

### Analogía de los Materiales Compartidos

Si tienes varios edificios en tu maqueta que usan el mismo tipo de ladrillo, puedes comprar una gran cantidad a la vez para ahorrar costos. Del mismo modo, compartir objetos de estilo entre nodos ayuda a reducir el tiempo de cálculo y el uso de memoria.

# Guía de Diseño y Renderización en Frontend

## Diseño

Imagina que estás organizando una fiesta y tienes que ubicar los muebles en una sala. Primero, decides dónde irá cada mueble y cuánto espacio ocuparán. Esto es similar al proceso de diseño en un navegador web. El diseño se encarga de calcular la posición y el tamaño de los elementos en una página web. 

**¿Qué hace el diseño?**
- Cuando creas un elemento HTML, como un div o un párrafo, inicialmente no tiene una posición ni tamaño específico. El proceso de calcular estos valores se llama **diseño** o **reprocesamiento**.
- HTML utiliza un modelo de diseño basado en flujo. Esto significa que los elementos se colocan de manera secuencial de izquierda a derecha y de arriba hacia abajo, como si estuvieras colocando los muebles en la sala en una fila ordenada.

**Sistema de Coordenadas**
- La posición de cada elemento se mide en relación con el marco raíz. La posición (0,0) corresponde a la esquina superior izquierda de la ventana del navegador.

**Diseño Recursivo**
- El proceso de diseño comienza en el elemento raíz (`<html>`) y luego se propaga a través de todos los elementos secundarios, calculando la información geométrica para cada uno.

## Sistema de Bits Sucios

Para no tener que reorganizar toda la sala cada vez que cambias algo pequeño, los navegadores usan un sistema de **bits sucios**. 

**¿Qué es un bit sucio?**
- Cuando se realiza un cambio en un elemento, ese elemento y sus elementos secundarios se marcan como "sucios", lo que indica que necesitan un nuevo diseño. Solo estos elementos necesitan ser recalculados, en lugar de todo el diseño.

## Diseño Incremental y Global

**Diseño Global**
- A veces, necesitas reorganizar toda la sala, como cuando haces un cambio de estilo que afecta a todos los elementos de la página, como cambiar el tamaño de la fuente. Esto es el **diseño global**.

**Diseño Incremental**
- Otras veces, solo necesitas ajustar una parte de la sala, como cuando agregas un nuevo mueble. Este es el **diseño incremental**, donde solo los elementos que han cambiado se actualizan.

## Diseño Asíncrono y Síncrono

**Diseño Asíncrono**
- El diseño incremental se realiza de manera **asíncrona**, es decir, no ocurre inmediatamente, sino que se programa para ejecutarse en el futuro. 

**Diseño Síncrono**
- El diseño global generalmente ocurre de manera **síncrona**, lo que significa que se realiza de inmediato. 

## Optimizaciones

**Uso de Caché**
- Para evitar recalcular todo el diseño desde cero, el navegador utiliza una **caché**. Si un elemento cambia de tamaño o posición, se consultan los valores previamente calculados en lugar de volver a calcular todo.

**Diseño Local**
- Si solo se modifica un pequeño detalle en la página, como agregar texto en un campo de formulario, el diseño solo afecta a esa parte, sin tener que recalcular toda la página.

## Proceso de Diseño

El diseño sigue estos pasos básicos:

1. **Determina el ancho del elemento superior.**
2. **Ubica los elementos secundarios dentro del elemento superior.**
3. **Calcula la altura total del elemento superior basada en sus hijos.**
4. **Marca el proceso como completo.**

## Cálculo del Ancho

Imagina que estás ajustando el ancho de una mesa para que se ajuste a un espacio específico. El navegador calcula el ancho de los elementos HTML de manera similar, teniendo en cuenta el contenedor, los márgenes y los bordes.

**Ejemplo:**
```html
<div style="width: 30%"></div>
```
- El ancho se calcula como un porcentaje del contenedor disponible, ajustado por márgenes y bordes.

## Saltos de Línea

Cuando un elemento no cabe en una línea, se ajusta en la siguiente línea, similar a cómo se moverían los muebles para encajar en una sala. 

## Pintura

**Pintura Global e Incremental**
- **Pintura Global**: Como pintar toda la sala de nuevo.
- **Pintura Incremental**: Solo se repinta la parte afectada, similar a tocar una pared que se ha dañado.

**Orden de Pintura**
- La pintura sigue un orden específico: color de fondo, imagen, borde, y luego el contenido de los elementos.

## Almacenamiento Rectangular y Cambios Dinámicos

**Almacenamiento Rectangular**
- Antes de repintar, algunos navegadores almacenan un mapa de bits de la pantalla anterior para actualizar solo las áreas cambiadas.

**Cambios Dinámicos**
- Los cambios menores, como un cambio de color, solo afectan el elemento específico. Cambios mayores, como agregar un nuevo elemento, requieren rediseño y repintado de la página.

## Subprocesos del Motor de Renderización

El navegador utiliza un **subproceso principal** para gestionar el diseño y la pintura, mientras que las operaciones de red se manejan en subprocesos paralelos.

**Bucle de Eventos**
- El navegador mantiene un **bucle de eventos** que espera y procesa eventos de diseño y pintura de manera continua.

## Modelo Visual CSS2

**El Lienzo**
- El **lienzo** es el área donde se renderiza el contenido de la página. Es esencialmente el espacio donde los elementos se pintan en la pantalla.

**Modelo de Caja CSS**
- Cada elemento en una página web es como una caja. La **caja** incluye el área de contenido, relleno, borde y margen. 

**Ejemplos de Caja**
- **Cuadro de Bloques**: Un bloque que ocupa su propio espacio en la página.
- **Cuadro Intercalado**: Se coloca dentro de un bloque existente y fluye horizontalmente.

**Posicionamiento**
- **Relativo**: Mueve un elemento en relación con su posición original.
- **Flotante**: Desplaza el elemento a la izquierda o derecha, haciendo que otros elementos fluyan a su alrededor.
- **Absoluto y Fijo**: Posiciona el elemento en un lugar específico, independiente del flujo normal de la página.

## Representación en Capas

**Índice Z**
- El **índice z** determina el orden de apilamiento de los elementos, donde los elementos con un índice z mayor se pintan sobre los de índice z menor.

**Ejemplo:**
```html
<style>
  div { position: absolute; }
  .red { z-index: 3; background-color: red; }
  .green { z-index: 1; background-color: green; }
</style>
```
- El `div` rojo se pintará sobre el `div` verde, aunque el verde se defina antes en el HTML.

---

# Poblando la página: Cómo Funcionan los Navegadores

Los usuarios desean experiencias web rápidas y fáciles de interactuar. Por lo tanto, los desarrolladores deben trabajar para optimizar ambos aspectos. Para mejorar el rendimiento y la percepción de la velocidad, es crucial entender cómo funciona el navegador.

## Descripción General

Los sitios web rápidos ofrecen mejores experiencias de usuario. Los usuarios esperan que el contenido se cargue rápidamente y sea fácil de interactuar. Los dos problemas principales en el rendimiento web son la latencia y el hecho de que los navegadores operan en un solo hilo.

### Latencia

Imagina que estás en una tienda y pides un producto a un empleado. Si el empleado tiene que ir a buscar el producto en otro departamento, esto toma tiempo. La latencia es el tiempo que toma transmitir los datos desde el servidor hasta tu navegador. El objetivo es minimizar este tiempo para que el sitio cargue lo más rápido posible.

### Navegadores de un Solo Hilo

Piénsalo como si tu navegador fuera una persona que realiza tareas una a una. Primero, el navegador tiene que terminar una tarea (como pintar la pantalla) antes de pasar a la siguiente. Esto significa que es crucial que cada tarea se complete de manera eficiente para que la experiencia sea fluida.

## Navegación

La navegación es el primer paso para cargar una página web. Es como pedir una dirección en una ciudad desconocida. La URL que introduces es como el nombre de una calle que quieres visitar. El navegador primero necesita encontrar la dirección IP del servidor que aloja la página, lo cual se realiza a través de una búsqueda de DNS.

### Búsqueda de DNS

Si nunca has visitado un sitio web, el navegador debe encontrar su dirección IP. Esto es como buscar una dirección en una guía telefónica. La búsqueda de DNS se realiza una vez por nombre de host y se almacena en caché para agilizar futuras visitas.

### Apretón de Manos TCP

Una vez que se conoce la dirección IP, el navegador establece una conexión con el servidor mediante un "apretón de manos" de tres vías (SYN-SYN-ACK). Es como si dos personas se dieran la mano y acordaran los detalles de una reunión antes de comenzar a hablar. Esto asegura que la conexión es estable antes de empezar a intercambiar datos.

### Negociación TLS

Para conexiones seguras (HTTPS), se realiza un segundo "apretón de manos" llamado negociación TLS. Es como asegurarse de que ambos participantes en una conversación secreta estén usando el mismo idioma cifrado antes de empezar a hablar. Este proceso agrega tiempo a la carga de la página, pero garantiza que los datos estén seguros.

## Respuesta

Con la conexión establecida, el navegador envía una solicitud HTTP GET para obtener el archivo HTML de la página. El servidor responde con el contenido del HTML, que incluye referencias a otros recursos como CSS, JavaScript e imágenes.

### Control de Congestión / TCP Inicio Lento

El TCP inicio lento es como ajustar la cantidad de paquetes de información que envías a un amigo para no sobrecargarlo. Envías unos pocos paquetes al principio y luego aumentas la cantidad gradualmente si todo va bien. Esto ayuda a equilibrar la carga y optimizar el rendimiento de la red.

## Analizar

Cuando el navegador recibe los datos, comienza a analizar la información para convertirla en un formato que pueda mostrar en la pantalla. Es como leer un libro y convertirlo en una representación visual. El navegador convierte el HTML en un árbol DOM y el CSS en un árbol CSSOM.

### Construyendo el Árbol DOM

El árbol DOM es como un plano de tu casa. Cada nodo representa un elemento en la página, y la estructura muestra cómo están organizados. Los elementos que no se mostrarán (como los scripts ocultos) no se incluyen en el árbol de renderizado.

### Escáner de Precarga

Mientras el navegador construye el árbol DOM, el escáner de precarga busca y descarga recursos importantes (como CSS y JavaScript) en segundo plano. Es como preparar los ingredientes para una receta mientras estás cocinando para que todo esté listo cuando lo necesites.

### Construyendo el Árbol CSSOM

El árbol CSSOM es como una guía de estilos para los elementos en la página. Convierte las reglas CSS en un formato que el navegador puede usar para aplicar estilos a los elementos. 

## Otros Procesos

### Compilación de JavaScript

JavaScript se analiza, compila e interpreta. Esto es como traducir un texto a un idioma que pueda entender el navegador. El código se convierte en un formato que el navegador puede ejecutar para hacer que la página sea interactiva.

### Construyendo el Árbol de Accesibilidad

El árbol de accesibilidad es una representación semántica del DOM que ayuda a los dispositivos de asistencia a interpretar el contenido de la página. Es como tener una versión en braille de un libro para personas con discapacidad visual.

## Render

El proceso de renderizado incluye estilo, diseño, pintura y, en algunos casos, composición. Los árboles CSSOM y DOM se combinan en un árbol de renderizado, que se usa para calcular el diseño de cada elemento visible y luego pintarlo en la pantalla.

### Estilo

El árbol de renderizado combina el DOM y el CSSOM. Es como juntar un plano arquitectónico con una guía de decoración para construir un modelo visual de la casa.

### Diseño

El diseño determina las dimensiones y la ubicación de cada elemento en la página. Es como organizar los muebles en una habitación según las dimensiones del espacio.

En resumen, entender cómo funciona el navegador te ayudará a optimizar el rendimiento y mejorar la experiencia del usuario en tus páginas web. Cada paso, desde la búsqueda de DNS hasta el renderizado, juega un papel crucial en la rapidez y la eficiencia con que se carga una página.

---

¡Claro! Aquí tienes un archivo Markdown que utiliza la analogía y los conceptos técnicos para explicar cómo funcionan los navegadores web, con un toque que hace que los conceptos sean más accesibles:

---

# Cómo Funcionan los Navegadores Web: Un Viaje en Analogías

### 1. La Interfaz del Navegador: Nuestro Panel de Control

Primero, echemos un vistazo a los componentes básicos de un navegador web. Imaginemos que el navegador es como una sala de control en un centro de operaciones.

- **Interfaz de Usuario:** Piensa en esto como el panel de control en la sala. Aquí están todos los botones que usas, como el botón de atrás, el botón de avanzar y la barra de direcciones. Es la parte con la que interactúas directamente.

- **Motor del Navegador:** Este es el operador que se comunica entre el panel de control y el motor de renderizado. Es como el asistente que traduce tus órdenes a acciones.

- **Motor de Renderizado:** Imagina que esto es la impresora 3D. Toma las instrucciones (HTML y CSS) y las convierte en algo visible. Su tarea es procesar todo el contenido y mostrarlo en pantalla.

- **Bloque de Red:** Piensa en esto como el departamento de adquisiciones. Se encarga de ir a Internet a buscar todos los recursos que necesita, como archivos HTML, CSS, imágenes, etc.

- **Intérprete de JavaScript:** Este es el cerebro detrás de las acciones dinámicas en la página. Si HTML y CSS son el diseño estático, JavaScript es lo que hace que todo cobre vida, permitiendo interacciones y cambios en tiempo real.

- **Backend de Interfaz de Usuario:** Aquí se encarga de la creación visual final. Es como el diseñador gráfico que dibuja lo que ves en tu pantalla.

- **Capa de Persistencia de Datos:** Piensa en esto como un archivador. Guarda información como cookies y el historial de navegación para que puedas recordar tus sitios web visitados o datos de inicio de sesión.

### 2. Paso a Paso del Renderizado: De la Idea a la Pantalla

Ahora que tenemos una visión general, veamos el proceso de renderizado en cinco pasos, utilizando una analogía:

#### Paso 1: Recolección de Recursos

**Analogía:** Imagina que estás organizando una fiesta y necesitas todos los ingredientes para el menú. Tienes que ir al supermercado (la web) para recolectar todo lo necesario: recetas (HTML), ingredientes (CSS), y decoraciones (imágenes).

**Técnico:** El navegador utiliza el bloque de red para obtener todos los recursos necesarios de Internet, como archivos HTML, CSS e imágenes.

#### Paso 2: Análisis HTML y Creación del Árbol DOM

**Analogía:** Ahora que tienes todos los ingredientes, necesitas organizar tu cocina. Esto es como crear una lista de tareas y distribuir los ingredientes en diferentes áreas de la cocina.

**Técnico:** El navegador analiza el HTML y crea un árbol de objetos DOM (Modelo de Objetos del Documento). Este árbol representa la estructura jerárquica del contenido de la página.

#### Paso 3: Creación del Árbol de Renderizado

**Analogía:** Con los ingredientes organizados, decides cómo vas a cocinar cada plato. Esto incluye elegir las recetas y decidir qué platos van juntos.

**Técnico:** Aquí, el motor de renderizado toma el árbol DOM y aplica los estilos CSS para crear un árbol de renderizado. Este árbol contiene solo los elementos visibles y sus estilos.

#### Paso 4: Diseño del Árbol de Renderizado

**Analogía:** Ahora que sabes qué platos vas a preparar, necesitas disponerlos en la mesa de la manera más atractiva y funcional.

**Técnico:** En esta etapa, el navegador calcula el tamaño y la posición de cada elemento en el árbol de renderizado, creando un diseño preciso para la visualización.

#### Paso 5: Pintura

**Analogía:** Finalmente, es el momento de servir la comida. Colocas los platos en la mesa y los presentas para que los invitados puedan disfrutar de la fiesta.

**Técnico:** El navegador envía toda la información del diseño al backend de la interfaz de usuario para dibujar y mostrar los elementos en la pantalla.