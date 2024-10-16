# Git y GitHub: Esenciales para la Documentación de Microsoft Learn

Como contribuyente a la documentación de Microsoft Learn, interactuarás con múltiples herramientas y procesos. Trabajarás en paralelo con otros colaboradores en el mismo proyecto, potencialmente en el mismo contenido, incluso al mismo tiempo. Todo esto es posible gracias al software de Git y GitHub.

Git es un sistema de control de versiones de código abierto. Facilita este tipo de colaboración de proyectos a través del control de versiones distribuido de archivos que residen en repositorios. En esencia, Git hace posible integrar flujos de trabajo realizados por múltiples contribuyentes a lo largo del tiempo, para un repositorio determinado.

GitHub es un servicio de alojamiento basado en la web para repositorios de Git, como aquellos utilizados para almacenar contenido de Microsoft Learn. Para cualquier proyecto, GitHub alberga el repositorio principal, a partir del cual los colaboradores pueden hacer copias para su propio trabajo.

## Conceptos Clave

### Rama (Branch)

Las ramas separan flujos de trabajo (típicamente referidos como versiones). Las contribuciones siempre se realizan y se limitan a una rama específica. 

Imagina que estás en una reunión donde cada grupo de trabajo discute un proyecto diferente. Cada grupo tiene su propia pizarra (rama) para hacer sus anotaciones sin interferir con los demás. A medida que avanzan, pueden integrar sus ideas (cambios) en una pizarra principal (rama por defecto).

En realidad, dependiendo del tipo de trabajo que realices, puedes terminar con varias ramas en tu repositorio. No es raro trabajar en múltiples ramas al mismo tiempo, cada una representando un proyecto diferente.

### Fork

Este término se utiliza normalmente como un sustantivo para referirse a una copia de un repositorio principal de GitHub. En la práctica, un fork es solo otro repositorio. Pero es especial en el sentido de que GitHub mantiene una conexión de vuelta al repositorio principal o "padre". A veces, se utiliza como un verbo, como en "Primero debes hacer un fork del repositorio".

### Git

Si estás familiarizado con sistemas de control de versiones centralizados (como Team Foundation Server, SharePoint o Visual SourceSafe), notarás que Git tiene un flujo de trabajo y una terminología de contribución únicos para respaldar su modelo distribuido. Por ejemplo, no hay bloqueo de archivos asociado normalmente con operaciones de chequeo/ingreso. En su lugar, Git se preocupa por los cambios a un nivel más fino, comparando archivos byte por byte.

Git utiliza una estructura jerárquica para almacenar y gestionar el contenido de un proyecto:

- **Repositorio**: También conocido como "repo", esta es la unidad más alta de almacenamiento. Un repositorio contiene una o más ramas.
- **Rama**: Una unidad de almacenamiento que contiene los archivos y carpetas que componen el conjunto de contenido de un proyecto.

Los contribuyentes interactúan con Git para actualizar y manipular repositorios tanto a nivel local como en GitHub:

- **Localmente** a través de herramientas como la consola de Git Bash, que soporta comandos de Git para gestionar repositorios locales y comunicarse con repositorios de GitHub.
- **A través de www.github.com**, que integra Git para gestionar la reconciliación de contribuciones que fluyen de vuelta al repositorio principal.

### GitHub

> **Nota**: Aunque las pautas de documentación se basan en el uso de GitHub, algunos equipos utilizan Visual Studio Team Services para alojar repositorios de Git. El cliente Visual Studio Team Explorer proporciona una interfaz gráfica para interactuar con los repositorios de Team Services, como alternativa al uso de comandos de Git a través de una línea de comandos.

Todas las flujos de trabajo comienzan y terminan en el nivel de GitHub, donde se almacena el repositorio principal para cualquier proyecto de documentación. Las copias que crean los colaboradores para su propio uso se distribuyen a través de múltiples computadoras. Estas copias eventualmente se reconciliarán de nuevo en el repositorio principal de GitHub del proyecto.

## Organización de Directorios

La rama por defecto de un proyecto sirve como la versión actual del contenido. El contenido en la rama por defecto (y las ramas creadas a partir de ella) está alineado de manera flexible con la organización de los artículos en las páginas correspondientes de Microsoft Learn. Se utilizan subdirectorios para separar artículos similares (como servicios), contenido multimedia (como archivos de imagen) y archivos de "inclusión" (que permiten la reutilización de contenido).

### Subdirectorio de Artículos

Normalmente puedes encontrar un directorio principal de artículos desde la raíz del repositorio. Este directorio contiene un conjunto de subdirectorios. Los artículos en los subdirectorios están formateados como archivos Markdown que utilizan una extensión .md. Algunos repositorios que soportan múltiples servicios utilizan un subdirectorio genérico /articles, como el repositorio de Azure-Docs. Otros pueden utilizar un nombre específico del servicio, como el repositorio de IntuneDocs, que utiliza /IntuneDocs.

Dentro de la raíz de este directorio, puedes encontrar artículos generales que se relacionan con el servicio o producto general. Típicamente, luego puedes encontrar otra serie de subdirectorios que coinciden con las características/servicios o escenarios comunes. Por ejemplo, los artículos de "máquinas virtuales" de Azure están en el subdirectorio /virtual-machines.

### Subdirectorio de Multimedia

Cada directorio de artículo contiene un subdirectorio /media para los archivos multimedia correspondientes. Los archivos multimedia contienen imágenes utilizadas por artículos que tienen referencias a imágenes.

### Subdirectorio de Inclusiones

Siempre que tenemos contenido reutilizable que se comparte en dos o más artículos, se coloca en un subdirectorio /includes fuera del directorio principal de artículos. En un archivo Markdown que utiliza el archivo de inclusión, se coloca una extensión "include" correspondiente en la ubicación donde se necesita hacer referencia al archivo de inclusión.

## Plantilla de Archivo Markdown

Para conveniencia, la raíz de cada repositorio típicamente contiene un archivo de plantilla Markdown llamado template.md. Puedes usar este archivo de plantilla como un "archivo de inicio" si necesitas crear un nuevo artículo para su presentación al repositorio. El archivo contiene:

- Un encabezado de metadatos en la parte superior del archivo, delimitado por dos líneas de 3 guiones. Contiene las diversas etiquetas utilizadas para rastrear información relacionada con el artículo.
- Una sección de metadatos que describe las diversas etiquetas y valores de metadatos. Si no estás seguro de los valores que utilizar para la sección de metadatos, puedes dejarlos en blanco o comentarlos con un símbolo de almohadilla (#), y serán revisados/completados por el revisor de la solicitud de extracción para el repositorio.

## Origen (Origin)

Este término es el nombre asignado a la conexión entre tu repositorio local y el repositorio del cual fue clonado. En el flujo de trabajo de Microsoft Learn, el origen representa la conexión a tu fork. Este término a veces se utiliza como un apodo para el propio repositorio de origen, como en "Recuerda empujar tus cambios al origen".

## Solicitudes de Extracción (Pull Requests)

Una solicitud de extracción (PR) es una solicitud para que un propietario de contenido extraiga tus cambios en la fuente oficial. Una PR permite el modelo de colaboración de GitHub al pedir que los cambios (también conocidos como commits) de tu rama de trabajo sean extraídos y fusionados en otra rama. En la mayoría de los casos, esa otra rama es la rama por defecto en el repositorio principal.

## Remoto (Remote)

Un remoto es una conexión nombrada a un repositorio remoto, como el remoto "origin" o "upstream". Git se refiere a esto como remoto porque se utiliza para referirse a un repositorio que está alojado en otra computadora.

## Upstream

Al igual que el remoto de origen, upstream es una conexión nombrada a otro repositorio. En el flujo de trabajo de Microsoft Learn, el upstream representa la conexión entre tu repositorio local y el repositorio principal del cual se creó tu fork. Este término a veces se utiliza como un apodo para el propio repositorio upstream, como en "Recuerda extraer los últimos cambios del upstream".

## Aprende Más

Si no estás familiarizado con Git o GitHub, estos recursos pueden ayudarte a aprender, ser productivo o responder preguntas.

- [Recursos de control de versiones Git](https://git-scm.com/book/en/v2)
- [E-book Pro Git (web)](https://git-scm.com/book/en/v2)
- [E-book Pro Git (PDF)](https://git-scm.com/book/en/v2)
- [Curso de Learn Git de Codecademy](https://www.codecademy.com/learn/learn-git)
- [Guías de GitHub](https://guides.github.com/)
- [Recursos de aprendizaje de GitHub](https://github.com/)

## Preguntas Frecuentes

### ¿Qué es Git?

Git ayuda a llevar un registro de los cambios cuando muchas personas trabajan en código de computadora juntas. Es como una máquina del tiempo para el código, para que puedas ver lo que cambió y volver si es necesario.

### ¿Por qué usar Git?

Es excelente para el trabajo en equipo. Git facilita que muchas personas trabajen en el mismo proyecto sin interferir en el trabajo de los demás. También ayuda a corregir errores fácilmente.

### ¿Cómo funciona Git?

Git almacena todas las versiones del código de un proyecto. Cuando haces cambios, Git toma una foto (como una instantánea) de lo que es diferente. Puedes hacer diferentes versiones al

 mismo tiempo y luego unirlas más tarde.

### ¿Qué es GitHub?

GitHub es un sitio web donde puedes almacenar tus proyectos de Git. Es como una biblioteca pública donde todos pueden ver tu código y ayudarte a mejorarlo.

### ¿Cómo empiezo con Git y GitHub?

Comienza por crear una cuenta en GitHub y aprender algunos comandos básicos de Git. Luego puedes empezar a trabajar en tus propios proyectos o contribuir a los de otras personas.

## Conclusión

Usar Git y GitHub es como tener un superpoder para la colaboración en proyectos. Puedes seguir los cambios, trabajar con otros sin problemas y hacer que tu contenido en Microsoft Learn sea mejor cada día. Aprender a usar estas herramientas te permitirá ser más eficiente y eficaz en tu trabajo. ¡Empieza a explorar hoy!

---

# Hello World

Sigue este ejercicio de Hello World para aprender el flujo de trabajo de solicitudes de extracción (pull requests) de GitHub.

## En este artículo

- Introducción
- Paso 1: Crear un repositorio
- Paso 2: Crear una rama
- Paso 3: Hacer y confirmar cambios
- Paso 4: Abrir una solicitud de extracción
- Paso 5: Fusionar tu solicitud de extracción
- Conclusión
- Pasos siguientes
- Lectura adicional

## Introducción

Este tutorial te enseña lo esencial de GitHub, como repositorios, ramas, confirmaciones y solicitudes de extracción. Crearás tu propio repositorio de Hello World y aprenderás el flujo de trabajo de solicitudes de extracción de GitHub, una forma popular de crear y revisar código.

En esta guía rápida, aprenderás a:

- Crear y usar un repositorio.
- Iniciar y gestionar una nueva rama.
- Realizar cambios en un archivo y subirlos a GitHub como confirmaciones.
- Abrir y fusionar una solicitud de extracción.

### Requisitos previos

Debes tener una cuenta de GitHub. Para más información, consulta "Crear una cuenta en GitHub".

No necesitas saber programar, usar la línea de comandos ni instalar Git (el software de control de versiones en el que se basa GitHub).

## Paso 1: Crear un repositorio

Lo primero que haremos es crear un repositorio. Puedes pensar en un repositorio como en una carpeta que contiene elementos relacionados, como archivos, imágenes, videos o incluso otras carpetas. Un repositorio suele agrupar elementos que pertenecen al mismo "proyecto" o cosa en la que estás trabajando.

A menudo, los repositorios incluyen un archivo README, que es un archivo con información sobre tu proyecto. Los archivos README se escriben en Markdown, que es un lenguaje fácil de leer y escribir para formatear texto plano. Aprenderemos más sobre Markdown en el próximo tutorial, "Configurando tu perfil".

GitHub te permite agregar un archivo README al mismo tiempo que creas tu nuevo repositorio. GitHub también ofrece otras opciones comunes, como un archivo de licencia, pero no es necesario seleccionar ninguna de ellas ahora.

Tu repositorio hello-world puede ser un lugar donde almacenes ideas, recursos o incluso compartas y discutas cosas con otros.

1. En la esquina superior derecha de cualquier página, selecciona el ícono de +, y luego haz clic en "Nuevo repositorio".
2. En el cuadro "Nombre del repositorio", escribe `hello-world`.
3. En el cuadro "Descripción", escribe una breve descripción. Por ejemplo, escribe "Este repositorio es para practicar el flujo de GitHub".
4. Selecciona si tu repositorio será Público o Privado.
5. Selecciona "Agregar un archivo README".
6. Haz clic en "Crear repositorio".

## Paso 2: Crear una rama

La creación de ramas te permite tener diferentes versiones de un repositorio al mismo tiempo.

Por defecto, tu repositorio tiene una rama llamada `main`, que se considera la rama definitiva. Puedes crear ramas adicionales a partir de `main` en tu repositorio.

La creación de ramas es útil cuando deseas agregar nuevas características a un proyecto sin cambiar la fuente principal del código. El trabajo realizado en diferentes ramas no aparecerá en la rama principal hasta que lo fusiones, lo cual cubriremos más adelante en esta guía. Puedes usar ramas para experimentar y hacer ediciones antes de confirmarlas en `main`.

Cuando creas una rama a partir de la rama principal, estás haciendo una copia, o instantánea, de `main` tal como estaba en ese momento. Si alguien más realizó cambios en la rama principal mientras trabajabas en tu rama, podrías incorporar esas actualizaciones.

### Creando una rama

1. Haz clic en la pestaña "Código" de tu repositorio hello-world.
2. Arriba de la lista de archivos, haz clic en el menú desplegable que dice `main`.
3. Escribe un nombre para la rama, `readme-edits`, en el cuadro de texto.
4. Haz clic en "Crear rama: readme-edits desde main".

Ahora tienes dos ramas: `main` y `readme-edits`. En este momento, lucen exactamente iguales. A continuación, agregarás cambios a la nueva rama `readme-edits`.

## Paso 3: Hacer y confirmar cambios

Cuando creaste una nueva rama en el paso anterior, GitHub te llevó a la página de código para tu nueva rama `readme-edits`, que es una copia de `main`.

Puedes hacer y guardar cambios en los archivos de tu repositorio. En GitHub, los cambios guardados se llaman confirmaciones. Cada confirmación tiene un mensaje de confirmación asociado, que es una descripción que explica por qué se realizó un cambio en particular. Los mensajes de confirmación capturan el historial de tus cambios para que otros colaboradores puedan entender qué has hecho y por qué.

### Haciendo cambios

1. Bajo la rama `readme-edits` que creaste, haz clic en el archivo `README.md`.
2. Para editar el archivo, haz clic en el ícono de lápiz (✏️).
3. En el editor, escribe un poco sobre ti.
4. Haz clic en "Confirmar cambios".
5. En el cuadro "Confirmar cambios", escribe un mensaje de confirmación que describa tus cambios.
6. Haz clic en "Confirmar cambios".

Estos cambios se realizarán solo en el archivo README de tu rama `readme-edits`, por lo que ahora esta rama contiene contenido que es diferente de `main`.

## Paso 4: Abrir una solicitud de extracción

Ahora que tienes cambios en una rama de `main`, puedes abrir una solicitud de extracción.

Las solicitudes de extracción son el corazón de la colaboración en GitHub. Cuando abres una solicitud de extracción, estás proponiendo tus cambios y solicitando que alguien los revise e incorpore tu contribución y los fusione en su rama. Las solicitudes de extracción muestran las diferencias (diffs) del contenido de ambas ramas. Los cambios, adiciones y eliminaciones se muestran en diferentes colores.

Tan pronto como haces una confirmación, puedes abrir una solicitud de extracción y comenzar una discusión, incluso antes de que el código esté terminado.

### Abriendo una solicitud de extracción

1. Haz clic en la pestaña "Solicitudes de extracción" de tu repositorio hello-world.
2. Haz clic en "Nueva solicitud de extracción".
3. En el cuadro "Ejemplo de comparaciones", selecciona la rama que hiciste, `readme-edits`, para comparar con `main` (la original).
4. Revisa tus cambios en las diferencias en la página de comparación y asegúrate de que son lo que deseas enviar.
5. Haz clic en "Crear solicitud de extracción".
6. Dale un título a tu solicitud de extracción y escribe una breve descripción de tus cambios. Puedes incluir emojis y arrastrar y soltar imágenes y GIFs.
7. Haz clic en "Crear solicitud de extracción".

### Revisando una solicitud de extracción

Cuando comiences a colaborar con otros, este es el momento en que pedirías su revisión. Esto permite que tus colaboradores comenten o propongan cambios a tu solicitud de extracción antes de que fusiones los cambios en la rama principal.

No cubriremos la revisión de solicitudes de extracción en este tutorial, pero si estás interesado en aprender más, consulta "Acerca de las revisiones de solicitudes de extracción". Alternativamente, prueba el curso de GitHub Skills "Revisando solicitudes de extracción".

## Paso 5: Fusionar tu solicitud de extracción

En este paso final, fusionarás tu rama `readme-edits` en la rama `main`. Después de fusionar tu solicitud de extracción, los cambios en tu rama `readme-edits` se incorporarán a `main`.

A veces, una solicitud de extracción puede introducir cambios en el código que entran en conflicto con el código existente en `main`. Si hay algún conflicto, GitHub te alertará sobre el código en conflicto y evitará la fusión hasta que se resuelvan los conflictos. Puedes hacer una confirmación que resuelva los conflictos o usar comentarios en la solicitud de extracción para discutir los conflictos con tus compañeros de equipo.

En este recorrido, no deberías tener conflictos, por lo que estás listo para fusionar tu rama en la rama principal.

### Fusionando la solicitud de extracción

1. En la parte inferior de la solicitud de extracción, haz clic en "Fusionar solicitud de extracción" para fusionar los cambios en `main`.
2. Haz clic en "Confirmar fusión". Recibirás un mensaje de que la solicitud fue fusionada exitosamente y se cerró.
3. Haz clic en "Eliminar rama". Ahora que tu solicitud de extracción está fusionada y tus cambios están en `main`, puedes eliminar de forma segura la rama `readme-edits`. Si deseas hacer más cambios en tu proyecto, siempre puedes crear una nueva rama y repetir este proceso.
4. Haz clic en "Código" en la pestaña de tu repositorio hello-world para ver tus cambios publicados en `main`.

## Conclusión

Al completar este tutorial, has aprendido a crear un proyecto y hacer una solicitud de extracción en GitHub.

Como parte de eso, hemos aprendido a:

- Crear un repositorio.
- Iniciar y gestionar una nueva rama.
- Cambiar un archivo y confirmar esos cambios en GitHub.
- Abrir y fusionar una solicitud de extracción.

---

# Crear una cuenta en GitHub

Crea una cuenta personal para comenzar a usar GitHub.

## En este artículo
- Acerca de tu cuenta personal en GitHub
- Registrarse para una nueva cuenta personal
- Próximos pasos
- Lectura adicional

## Acerca de tu cuenta personal en GitHub
Para comenzar con GitHub, necesitarás crear una cuenta personal gratuita y verificar tu dirección de correo electrónico.

Cada persona que usa GitHub inicia sesión con una cuenta de usuario. Tu cuenta de usuario es tu identidad en GitHub y tiene un nombre de usuario y un perfil. Por ejemplo, puedes ver el perfil de @octocat.

Piensa en tu cuenta de GitHub como tu **carnet de identidad** en el mundo del desarrollo. Al igual que un carnet te identifica en la vida real, tu cuenta te identifica en la comunidad de desarrolladores. Más adelante, puedes explorar los diferentes tipos de cuentas que GitHub ofrece y decidir si necesitas un plan de pago. Para más información, consulta "Tipos de cuentas de GitHub" y "Planes de GitHub".

Ten en cuenta que los pasos en este artículo no se aplican a los Usuarios Administrados por Empresas. Si tu cuenta de GitHub ha sido creada por tu empresa, puedes saltar este artículo y continuar con "¡Hola Mundo!".

## Registrarse para una nueva cuenta personal
Para crear tu cuenta, sigue estos pasos:

1. Navega a [https://github.com/](https://github.com/).
2. Haz clic en **Sign up** (Registrarse).
3. Sigue las instrucciones para crear tu cuenta personal.

Durante el registro, se te pedirá que verifiques tu dirección de correo electrónico. Sin una dirección de correo electrónico verificada, no podrás completar algunas tareas básicas en GitHub, como crear un repositorio.

Verificar tu correo electrónico es como **activar tu tarjeta de crédito**. Aunque la tarjeta exista, no podrás usarla hasta que la actives. Si tienes problemas para verificar tu dirección de correo electrónico, hay algunos pasos de solución de problemas que puedes seguir. Para más información, consulta "Verificando tu dirección de correo electrónico."

## Próximos pasos
Una vez que hayas creado y verificado tu cuenta, estarás listo para comenzar a explorar GitHub. El siguiente paso será aprender a crear tu primer repositorio, lo cual es como crear un **cajón de herramientas** donde almacenarás todos tus proyectos.

## Lectura adicional
- [Documentación de GitHub](https://docs.github.com)
- [Guía de verificación de tu dirección de correo electrónico](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/verifying-your-email-address)

---

# Configuración de tu perfil

Tu perfil le dice a la gente quién eres y qué te interesa.

## En este artículo
- Acerca de tu perfil
- Agregar una foto de perfil y biografía
- Agregar un README de perfil
- Próximos pasos
- Lectura adicional

## Acerca de tu perfil
Tu página de perfil en GitHub es un lugar donde las personas pueden conocer más sobre ti. Puedes usar tu perfil para:

- Compartir tus intereses y habilidades.
- Mostrar tus proyectos y contribuciones.
- Expresar tu identidad y mostrarle a la comunidad de GitHub quién eres.

Piensa en tu perfil como un **currículum** digital. Así como en un currículum muestras tus habilidades y experiencias, en tu perfil de GitHub puedes exhibir tus proyectos y lo que te apasiona. En este tutorial, aprenderás a personalizar tu perfil agregando una foto de perfil, una biografía y un README de perfil.

También aprenderás lo básico de la sintaxis Markdown, que es lo que usarás para dar formato a cualquier escritura que hagas en GitHub.

### Requisitos previos
Debes tener una cuenta de GitHub. Para más información, consulta "Creando una cuenta en GitHub".

## Agregar una foto de perfil y biografía
Primero, vamos a agregar una imagen a tu perfil. Tu foto de perfil ayuda a identificarte en toda GitHub.

### Agregar una foto de perfil
1. En la esquina superior derecha de cualquier página, haz clic en tu avatar de perfil existente y luego, en el menú desplegable, haz clic en **Configuración**.
2. En "Foto de perfil", selecciona **Editar**, luego haz clic en **Subir una foto...**.
3. Selecciona una imagen y haz clic en **Subir**.
4. Recorta tu imagen.
5. Haz clic en **Establecer nueva foto de perfil**.

Tu foto de perfil es como tu **firma** en el mundo digital. Ayuda a las personas a reconocerte y recordar tu trabajo.

### Agregar una biografía
En tu página de perfil, debajo de tu foto de perfil, haz clic en **Editar perfil**.

1. En "Biografía", escribe una o dos oraciones sobre ti, como quién eres y qué haces.

**Nota:** Mantén la biografía corta; agregaremos una descripción más larga de tus intereses en tu README de perfil en la sección siguiente.

2. Para agregar un emoji a tu biografía, visita "Hoja de trucos de emoji" y copia y pega un emoji en el cuadro de diálogo "Biografía".
3. Opcionalmente, agrega tus pronombres preferidos, lugar de trabajo, ubicación y zona horaria, y cualquier enlace a tu sitio web personal y cuentas sociales. Tus pronombres solo serán visibles para los usuarios que estén registrados en GitHub.
4. Haz clic en **Guardar**.

## Agregar un README de perfil
A continuación, crearemos un repositorio especial y un archivo README que se mostrará directamente en tu página de perfil.

Tu README de perfil contiene información como tus intereses, habilidades y antecedentes, y puede ser una excelente manera de presentarte a otras personas en GitHub y mostrar tu trabajo.

Como aprendimos en el tutorial "Hola Mundo", los archivos README.md se escriben utilizando la sintaxis Markdown (nota la extensión .md), que es solo una forma de dar formato al texto plano.

En los siguientes pasos, crearemos y editaremos tu README de perfil.

### Paso 1: Crear un nuevo repositorio para tu README de perfil
1. En la esquina superior derecha de cualquier página, selecciona el signo más (+) y luego haz clic en **Nuevo repositorio**.
2. En "Nombre del repositorio", escribe un nombre que coincida con tu nombre de usuario de GitHub. Por ejemplo, si tu nombre de usuario es "octocat", el nombre del repositorio debe ser "octocat".
3. Opcionalmente, en el campo "Descripción", escribe una descripción de tu repositorio. Por ejemplo, "Mi repositorio personal".
4. Selecciona **Público**.
5. Selecciona **Inicializar este repositorio con un README**.
6. Haz clic en **Crear repositorio**.

### Paso 2: Editar el archivo README.md
1. Haz clic en el ícono de lápiz al lado de tu README de perfil.
2. En la vista "Editar", verás un texto pre-poblado para empezar. En la línea 1, elimina el texto que dice ### Hola a todos y escribe # Sobre mí.

   En la sintaxis Markdown, ### convierte el texto plano en un encabezado pequeño ("tercer nivel"), mientras que ## o # convierten en encabezados de segundo y primer nivel respectivamente.
   
3. Cambia a "Vista previa" para ver cómo se renderiza el texto plano ahora. Deberías ver el nuevo texto mostrado como un encabezado mucho más grande.
4. Cambia de nuevo a la vista "Editar".
5. Elimina la línea 3 y la línea 16. 

   Esta sintaxis HTML (por ejemplo, `<!--`) mantiene ocultas las otras líneas cuando cambias a "Vista previa".
   
6. Completa algunos de los prompts en las líneas 8 a 15 y elimina cualquier línea que no quieras. Por ejemplo, agrega tus intereses, habilidades, pasatiempos o un dato curioso sobre ti.
7. Ahora, cambia a "Vista previa". Deberías ver tus prompts completados renderizados como una lista con viñetas.
8. Cambia de nuevo a "Editar" y elimina cualquier otra línea de texto que no desees mostrar en tu perfil.

Continúa personalizando y editando tu README de perfil. 

- Usa la "Hoja de trucos de emoji" para agregar emojis.
- Usa la "Hoja de trucos de Markdown" para experimentar con un formato adicional de Markdown.

### Paso 3: Publicar tus cambios en tu perfil
Cuando estés satisfecho con cómo se ve tu README de perfil en "Vista previa" y estés listo para publicarlo, haz clic en **Confirmar cambios...**.

1. En el cuadro de diálogo que se abre, simplemente haz clic nuevamente en **Confirmar cambios**.
2. Navega de vuelta a tu página de perfil. Verás tu nuevo README de perfil mostrado en tu perfil.

## Próximos pasos
Ahora que has configurado tu perfil, es hora de comenzar a explorar más sobre GitHub y cómo puedes contribuir a proyectos de código abierto o crear los tuyos propios.

## Lectura adicional
- [Documentación de GitHub](https://docs.github.com)
- [Guía sobre cómo usar Markdown](https://www.markdownguide.org/)

---

# Gestión de tu README de perfil

Puedes agregar un README a tu perfil de GitHub para contarle a otras personas sobre ti.

## ¿Quién puede usar esta función?
Los READMEs de perfil no están disponibles para cuentas de usuario gestionadas.

## En este artículo
- Sobre tu README de perfil
- Requisitos previos
- Agregar un README de perfil
- Eliminar un README de perfil
- Lectura adicional

## Sobre tu README de perfil
Puedes compartir información sobre ti mismo con la comunidad en GitHub creando un README de perfil. GitHub muestra tu README de perfil en la parte superior de tu página de perfil.

Tú decides qué información incluir en tu README de perfil, por lo que tienes control total sobre cómo te presentas en GitHub. Aquí hay algunos ejemplos de información que los visitantes pueden encontrar interesantes, divertidos o útiles en tu README de perfil:

- Una sección "Sobre mí" que describe tu trabajo e intereses.
- Contribuciones de las que estás orgulloso, y contexto sobre esas contribuciones.
- Orientación para obtener ayuda en comunidades en las que estás involucrado.

Imagina que tu README es como un **cartel publicitario** en la entrada de un evento. Así como un cartel puede atraer a las personas al describir lo que pueden esperar, tu README presenta tus habilidades y pasiones a los visitantes de tu perfil.

Puedes formatear texto e incluir emojis, imágenes y GIFs en tu README de perfil utilizando Markdown. Para más información, consulta ["Introducción a la escritura y formateo en GitHub."](https://docs.github.com/es/github/writing-on-github) Para una guía práctica sobre cómo personalizar tu README de perfil, ve a ["Guía rápida para escribir en GitHub."](https://docs.github.com/es/github/writing-on-github)

## Requisitos previos
GitHub mostrará tu README de perfil en tu página de perfil si se cumplen todas las siguientes condiciones:

- Has creado un repositorio con un nombre que coincide con tu nombre de usuario de GitHub.
- El repositorio es público.
- El repositorio contiene un archivo llamado `README.md` en su raíz.
- El archivo `README.md` contiene algún contenido.

**Nota:** Si creaste un repositorio público con el mismo nombre que tu nombre de usuario antes de julio de 2020, GitHub no mostrará automáticamente el README del repositorio en tu perfil. Puedes compartir manualmente el README del repositorio en tu perfil yendo al repositorio en GitHub y haciendo clic en "Compartir en perfil".

## Agregar un README de perfil
1. En la esquina superior derecha de cualquier página, selecciona el ícono de `+`, y luego haz clic en **Nuevo repositorio**.

   ![Menú desplegable de GitHub](https://github.githubassets.com/images/modules/site/new-repo.png)

2. Bajo "Nombre del repositorio", escribe un nombre de repositorio que coincida con tu nombre de usuario de GitHub. Por ejemplo, si tu nombre de usuario es "octocat", el nombre del repositorio debe ser "octocat".
3. Opcionalmente, en el campo "Descripción", escribe una descripción de tu repositorio. Por ejemplo, "Mi repositorio personal."
4. Selecciona **Público**.
5. Selecciona **Inicializar este repositorio con un README**.
6. Haz clic en **Crear repositorio**.
7. En la barra lateral derecha, haz clic en **Editar README**.

El archivo README generado se pre-pobla con una plantilla para inspirarte en tu README de perfil.

Para un resumen de todos los emojis disponibles y sus códigos, consulta ["Hoja de trucos de emojis."](https://emojipedia.org/)

## Eliminar un README de perfil
El README de perfil se eliminará de tu perfil de GitHub si se aplica alguna de las siguientes condiciones:

- El archivo README se elimina o se deja vacío.
- El repositorio se hace privado.
- El nombre del repositorio ya no coincide con tu nombre de usuario debido a un cambio en uno o ambos nombres.

El método que elijas depende de tus necesidades, pero si no estás seguro, te recomendamos hacer que tu repositorio sea privado. Para obtener pasos sobre cómo hacer que tu repositorio sea privado, consulta ["Configuración de la visibilidad del repositorio."](https://docs.github.com/es/github/administering-a-repository/changing-a-repositorys-visibility)

---

# Guía Rápida para Repositorios

Aprende cómo crear un nuevo repositorio y hacer tu primer commit en 5 minutos.

## Navegación de Herramientas
- **GitHub CLI**
- **Navegador Web**

## En Este Artículo
- Crear un Repositorio
- Hacer tu Primer Cambio
- Próximos Pasos

## Crear un Repositorio
Los repositorios de GitHub almacenan una variedad de proyectos. En esta guía, crearás un repositorio y harás tu primer cambio.

1. En la esquina superior derecha de cualquier página, selecciona el ícono `+`, luego haz clic en **Nuevo Repositorio**.

   ![Menú de GitHub](https://github.githubassets.com/images/modules/site/new-repo.png)

2. Escribe un nombre corto y memorable para tu repositorio. Por ejemplo, "hola-mundo".

   ![Nombre del Repositorio](https://github.githubassets.com/images/modules/repository/new-repository.png)

3. Opcionalmente, agrega una descripción de tu repositorio. Por ejemplo, "Mi primer repositorio en GitHub."

4. Elige la visibilidad del repositorio. Para más información, consulta "Acerca de los repositorios."

5. Selecciona **Inicializar este repositorio con un README**.

6. Haz clic en **Crear Repositorio**.

¡Felicidades! Has creado con éxito tu primer repositorio e inicializado con un archivo README.

### Analogía
Crear un repositorio en GitHub es como abrir una **nueva carpeta** en tu computadora. Al nombrar la carpeta y agregar un README, le estás dando un propósito y contexto a los archivos que contendrá, al igual que un organizador.

## Hacer tu Primer Cambio
Un commit es como una **instantánea** de todos los archivos de tu proyecto en un momento particular.

Cuando creaste tu nuevo repositorio, lo inicializaste con un archivo README. Los archivos README son un excelente lugar para describir tu proyecto en más detalle o agregar documentación, como cómo instalar o usar tu proyecto. El contenido de tu archivo README se muestra automáticamente en la página principal de tu repositorio.

Vamos a hacer un cambio en el archivo README.

1. En la lista de archivos de tu repositorio, selecciona `README.md`.

   ![Lista de Archivos](https://github.githubassets.com/images/modules/repository/readme-file-list.png)

2. En la esquina superior derecha de la vista del archivo, haz clic en el ícono del lápiz para abrir el editor de archivos.

   ![Editor de Archivos](https://github.githubassets.com/images/modules/repository/edit-file.png)

3. En el cuadro de texto, escribe información sobre ti mismo.

4. Encima del nuevo contenido, haz clic en **Vista Previa**.

   ![Vista Previa](https://github.githubassets.com/images/modules/repository/preview-file.png)

5. Revisa los cambios que realizaste en el archivo. Si seleccionas **Mostrar diferencia**, verás el nuevo contenido en verde.

   ![Mostrar Diferencia](https://github.githubassets.com/images/modules/repository/preview-diff.png)

6. Haz clic en **Hacer Commit de los Cambios...**

7. En el campo "Mensaje de commit", escribe un mensaje corto y significativo que describa el cambio que hiciste en el archivo. Puedes atribuir el commit a más de un autor en el mensaje de commit. Para más información, consulta "Crear un commit con múltiples autores."

8. Debajo de los campos de mensaje de commit, decide si agregar tu commit a la rama actual o a una nueva rama. Si tu rama actual es la rama predeterminada, deberías elegir crear una nueva rama para tu commit y luego crear una solicitud de extracción. Para más información, consulta "Crear una solicitud de extracción."

   ![Solicitud de Extracción](https://github.githubassets.com/images/modules/repository/pull-request-options.png)

9. Haz clic en **Hacer Commit de los Cambios** o **Proponer Cambios**.

### Analogía
Hacer un commit es como **tomar una foto** de tu progreso en un proyecto. Al capturar el estado actual de tu README, puedes volver a esa "foto" en el futuro si necesitas recordar cómo estaba todo antes de los cambios.

## Acerca de la Visibilidad del Repositorio
Puedes restringir quién tiene acceso a un repositorio eligiendo la visibilidad del mismo: pública o privada.

Cuando creas un repositorio, puedes optar por hacerlo público o privado. Los repositorios en organizaciones que usan GitHub Enterprise Cloud y son propiedad de una cuenta empresarial también pueden crearse con visibilidad interna. Para más información, consulta la documentación de GitHub Enterprise Cloud.

- **Los repositorios públicos** son accesibles para todos en Internet.
- **Los repositorios privados** son solo accesibles para ti, personas con las que compartes explícitamente el acceso y, en el caso de repositorios de organizaciones, ciertos miembros de la organización.

Los propietarios de la organización siempre tienen acceso a cada repositorio creado en una organización. Para más información, consulta "Roles de repositorio para una organización."

Las personas con permisos de administrador para un repositorio pueden cambiar la visibilidad de un repositorio existente. Para más información, consulta "Establecer la visibilidad del repositorio."