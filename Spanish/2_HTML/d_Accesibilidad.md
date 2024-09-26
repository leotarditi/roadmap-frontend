# Accesibilidad

## Mejora de la accesibilidad de las páginas web

Este conjunto de documentos es una versión basada en texto de parte del contenido que se aborda en el curso de accesibilidad. En lugar de ser una transcripción directa del curso en video, está diseñado para ser claro y conciso sobre los principios y las prácticas de accesibilidad, con los recursos del curso como base.

### Resumen
- **Descubre qué significa la accesibilidad y cómo se aplica al desarrollo web.**
- **Aprende a hacer que los sitios web sean accesibles y fáciles de usar para todos.**
- **Aprende a incluir accesibilidad básica con un impacto mínimo en el desarrollo.**
- **Descubre qué funciones HTML están disponibles y cómo usarlas para mejorar la accesibilidad.**
- **Aprende técnicas avanzadas de accesibilidad para crear experiencias de accesibilidad pulidas.**

Comprender la accesibilidad, su alcance y su impacto puede ayudarte a mejorar tu habilidad como desarrollador web. Esta guía está pensada para ayudarte a entender cómo puedes hacer que tus sitios sean accesibles y fáciles de usar para todos.

"Accesibilidad" puede ser difícil de deletrear, pero no tiene que ser difícil de lograr. En esta guía, descubrirás cómo obtener beneficios fáciles para mejorar la accesibilidad con un esfuerzo mínimo, cómo usar las funciones integradas de HTML para crear interfaces más accesibles y sólidas, y cómo aprovechar algunas técnicas avanzadas para crear experiencias de accesibilidad pulidas.

También descubrirás que muchas de estas técnicas te ayudarán a crear interfaces que son más agradables y fáciles de usar para todos los usuarios, no solo para aquellos con discapacidades.

Por supuesto, muchos desarrolladores solo tienen una comprensión confusa de lo que significa accesibilidad, y hay muchos conceptos erróneos que dan vueltas. Por ejemplo, muchos desarrolladores creen que abordar la accesibilidad los obligará a elegir entre crear una experiencia encantadora y atractiva, y una que sea tosco y feo, pero accesible.

Ese no es el caso en absoluto, así que aclaremos eso antes de seguir con otra cosa. ¿Qué entendemos por accesibilidad y qué estamos aquí para aprender?

### ¿Qué es la accesibilidad?

En términos generales, cuando decimos que un sitio es accesible, nos referimos a que su contenido está disponible y se puede operar su funcionalidad por literalmente cualquier persona. Como desarrolladores, es fácil suponer que todos los usuarios pueden ver y usar un teclado, mouse o pantalla táctil, además de interactuar con el contenido de la página como lo haces tú. Esto puede resultar en una experiencia que funciona bien para algunas personas pero crea problemas que van desde simples molestias hasta impedimentos para otras personas.

**Analogía**: Imagina que estás organizando una fiesta y asumes que todos tus invitados pueden comer comida con picante. Pero, ¿qué pasa si algunos de ellos tienen alergias o simplemente no les gusta el picante? Si solo ofreces comida picante, algunos invitados pueden sentirse incómodos o no disfrutar de la fiesta. Hacer la comida accesible para todos sería como ofrecer opciones sin picante también.

La accesibilidad, entonces, se refiere a la experiencia de los usuarios que podrían estar fuera del rango reducido del "típico" usuario, que podría acceder a elementos o interactuar con ellos de manera diferente a lo que esperabas. Específicamente, involucra a los usuarios que tienen algún tipo de impedimento o discapacidad, y ten en cuenta que esa experiencia podría no ser física ni temporal.

**Analogía**: Imagina que construyes una casa. Si solo construyes rampas para sillas de ruedas pero no pones escaleras, algunas personas podrían tener problemas para acceder a ciertas áreas de la casa. Hacer tu casa accesible sería como construir rampas y escaleras para asegurarte de que todos puedan moverse libremente.

### Un formulario con mala accesibilidad

Considera un formulario con varios problemas de accesibilidad:

- El texto tiene poco contraste, lo cual dificulta la lectura para los usuarios con visión reducida.
- Tener etiquetas a la izquierda y campos a la derecha dificulta que muchas personas las asocien, y es casi imposible para alguien que necesita hacer zoom usar la página; imagina mirar esto en un teléfono y tener que desplazarte lateralmente para descubrir qué funciona con qué.
- La opción "¿Recuerdas los detalles?" no está asociada a la casilla de verificación, por lo que presionar o hacer clic solo en el pequeño cuadrado en lugar de en la etiqueta; también, alguien que use un lector de pantalla tendría problemas para averiguar la asociación.

**Analogía**: Es como tener una lista de compras en la que los nombres de los artículos están escritos en una letra muy pequeña y difícil de leer, y están desordenados, lo que hace que sea complicado encontrar lo que buscas. Al cambiar el diseño para que las etiquetas estén cerca de los elementos y mejorar el contraste, estás haciendo que la lista sea mucho más fácil de leer y usar.

### Un formulario con accesibilidad mejorada

Ahora, imagina que hemos corregido esos problemas. Oscurecemos el texto, modificamos el diseño para que las etiquetas estén cerca de los elementos que etiquetan y arreglamos la etiqueta para que se asocie a la casilla de verificación, permitiendo que también puedas alternar con un clic en la etiqueta.

**Analogía**: Es como reescribir la lista de compras con letras grandes y claras, y agrupar los artículos relacionados, para que sea mucho más fácil de leer y usar.

### Lineamientos de accesibilidad para el contenido web

En esta guía, consultaremos los Lineamientos de Accesibilidad para el Contenido Web (WCAG) 2.0, un conjunto de lineamientos y prácticas recomendadas reunidas por expertos en accesibilidad para abordar qué "accesibilidad" de forma metódica.

Las WCAG se organizan en torno a cuatro principios a menudo llamados con el acrónimo POUR:

- **Perceptible**: ¿Los usuarios perciben el contenido? Esto nos ayuda a tener en cuenta que algo es perceptible con un sentido, como la vista, no significa que todos los usuarios puedan percibirlo.
  
  **Analogía**: Es como asegurarte de que todos los invitados a tu fiesta puedan ver el menú, no solo aquellos que están en el centro del salón, sino también los que están en los rincones.

- **Viable**: ¿Pueden los usuarios usar componentes de la IU y navegar por el contenido? Por ejemplo, algo que requiere una interacción al colocar el cursor sobre un elemento no es accesible para alguien que no puede usar un mouse o una pantalla táctil.

  **Analogía**: Es como asegurarte de que todos los invitados a tu fiesta puedan llegar al buffet, ya sea que usen una silla de ruedas o tengan que caminar.

- **Comprensible**: ¿Los usuarios pueden comprender el contenido? ¿Pueden los usuarios comprender la interfaz y es lo suficientemente coherente como para evitar confusiones?

  **Analogía**: Es como hacer que las instrucciones para el juego de la fiesta sean claras y simples para que todos puedan entender cómo jugar.

- **Robust**: ¿Puede una amplia variedad de usuarios-agentes consumir el contenido? (navegadores). ¿Funciona con tecnología de accesibilidad?

  **Analogía**: Es como asegurarte de que el sonido en la fiesta se escuche bien tanto si se escucha con altavoces grandes como si se usa un sistema de audífonos.

Si bien las WCAG brindan una visión general completa de lo que significa que el contenido sea accesible, también puede ser un poco abrumador. Para ayudar a mitigar esto, WebAIM (Web Accessibility in Mind) ha resumido las pautas de las WCAG en una lista de verificación fácil de seguir, dirigida específicamente para el contenido web.

### Comprender la diversidad de los usuarios

Al aprender sobre accesibilidad, es útil comprender la diversa gama de usuarios en el mundo y los tipos de temas de accesibilidad que los afectan. Por ejemplo, la accesibilidad puede implicar personas con discapacidades visuales, motrices, auditivas o cognitivas.

**Analogía**: Es como asegurarte de que todos en tu fiesta puedan disfrutar de la música, ya sea que les guste la música en vivo o los discos, y que todos puedan moverse libremente, ya sea que usen una silla de ruedas o puedan caminar.

### Próximos pasos

Ya hemos cubierto bastante terreno. Has leído:

- Qué es la accesibilidad y por qué es importante para todos.
- Las WCAG y la lista de verificación de accesibilidad de WebAIM.
- Diferentes tipos de discapacidades que debes tener en cuenta.

En el resto de la guía, nos sumergiremos en los aspectos prácticos de la creación de sitios web accesibles. Organizaremos este esfuerzo en torno a tres temas principales áreas:

- **Enfoque**: Veremos cómo crear cosas que se puedan operar con un teclado en lugar de un mouse. Este es importante para los usuarios con discapacidades motrices, pero también garantiza que tu UI esté en buenas condiciones para todos los usuarios.
- **Semántica**: Veremos cómo asegurarnos de expresar nuestra interfaz de usuario de forma sólida, para una variedad de tecnologías de asistencia.
- **Estilos**: Consideraremos los elementos visuales que diseñarás y veremos algunas técnicas para hacer que los elementos visuales del sitio sean lo más flexibles y fáciles de usar posible.

