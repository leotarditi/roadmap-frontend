# Cómo colaborar en un proyecto de GitHub

Colaborar en un proyecto de GitHub es como unirse a un equipo de cocina donde cada uno aporta su receta única para crear un plato delicioso. Aquí, aprenderemos los pasos para hacer tu contribución de manera efectiva.

## 1. Revisar la política de colaboración en el proyecto

Antes de comenzar, es importante revisar las directrices de colaboración del proyecto. Cada cocina tiene sus propias reglas, y entenderlas te ayudará a integrarte mejor en el equipo.

## 2. Hacer un fork del repositorio

Forkear un repositorio es como tomar prestada la receta del chef principal para modificarla a tu gusto. En este caso, hacemos un fork del repositorio original:

```
https://github.com/jmsampayo/gazelle-analyser-api.git
```

Para hacer el fork, ve al repositorio en GitHub y haz clic en el botón **Fork**.

## 3. Clonar el repositorio forked

Clonar el repositorio es como llevar tu versión de la receta a tu cocina. Esto te permite hacer cambios sin afectar la receta original.

```bash
git clone https://github.com/neklaf/gazelle-analyser-api.git
```

## 4. Actualizar la rama master

Es crucial asegurarte de que tu versión esté actualizada con los últimos cambios del chef principal. Esto se logra actualizando tu rama master:

```bash
git pull -r upstream master
```

### Agregando la URL del repositorio original

Primero, debes agregar la URL del repositorio original para poder mantener tu versión actualizada:

```bash
git remote add upstream https://github.com/jmsampayo/gazelle-analyser-api.git
```

### Verificar la configuración remota

Para asegurarte de que todo esté en su lugar, verifica las configuraciones remotas:

```bash
git remote -v
```

Deberías ver algo como esto:

```
origin	https://github.com/neklaf/gazelle-analyser-api.git (fetch)
origin	https://github.com/neklaf/gazelle-analyser-api.git (push)
upstream	https://github.com/jmsampayo/gazelle-analyser-api.git (fetch)
upstream	https://github.com/jmsampayo/gazelle-analyser-api.git (push)
```

## 5. Crear una rama para nuestras mejoras

Ahora es el momento de hacer nuestras mejoras. Crea una nueva rama donde implementarás tus cambios:

```bash
git checkout -b my-collaboration-feature
```

## 6. Hacer los cambios

Realiza las modificaciones necesarias en tu archivo, por ejemplo:

```bash
vim README.md
```

Verifica el estado de tus cambios:

```bash
git status -s
```

Verás un resultado como este:

```
  M README.md
```

## 7. Hacer commit de los cambios

Es el momento de guardar tus cambios en la historia de la receta:

```bash
git add README.md
git commit -m 'Añadí mi increíble nueva característica al proyecto en el que colaboro'
```

## 8. Hacer push de los cambios

Ahora, empuja tus cambios a tu repositorio forked en GitHub:

```bash
git push --set-upstream origin my-collaboration-feature
```

## 9. Crear un Pull Request

Para compartir tus mejoras con el resto del equipo, debes crear un Pull Request. Asegúrate de vincular tu PR con un issue abierto (si es aplicable) a través de la interfaz web de GitHub.

## 10. Sincronizar un fork

Es importante mantener tu fork sincronizado con el repositorio original. Para ello, primero obtén las ramas y commits:

```bash
git fetch upstream
```

### Cambiar a la rama master de tu fork

Asegúrate de estar en la rama master de tu fork:

```bash
git checkout master
```

### Fusionar los cambios

Fusiona los cambios desde el repositorio original a tu rama local:

```bash
git merge upstream/master
```

Si tu rama local no tiene commits únicos, Git realizará un "fast-forward":

```bash
git merge upstream/master
```

## 11. Rebase de un Pull Request

Si necesitas rebasear tu Pull Request, asegúrate de que tu fork esté sincronizado. Luego, sigue estos pasos:

1. Cambia a la rama de tu PR:

    ```bash
    git checkout my-collaboration-feature
    ```

2. Ejecuta el rebase sobre la rama de desarrollo:

    ```bash
    git rebase upstream/master
    ```

3. Realiza un **force push** para actualizar tu PR:

    ```bash
    git push -f
    ```

### ¿Qué hacer si se requieren cambios en tu PR?

Es recomendable tener solo un commit en tu PR. Si has hecho varios commits, asegúrate de agruparlos en uno solo:

```bash
git reset --soft HEAD~5
git commit -m "ID-1234 | Mejorar la calidad del código"
```

Dado que ya has empujado cambios al remoto, utiliza:

```bash
git push origin +my-collaboration-feature
```

El signo `+` actúa como un **force push** para reescribir el historial.

## Referencias

- [Documentación de Git](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)
- [Stack Overflow sobre reescritura de historial](http://stackoverflow.com/a/5201642/295797)
- [Combinar múltiples commits en uno](https://feeding.cloud.geek.nz/posts/combining-multiple-commits-into-one/)

## Nota

Puedes crear un alias `git nb` que facilitará crear y cambiar a una nueva rama que rastrea la rama actual:

```bash
git config --global alias.foo '!git checkout --track $(git config branch.$(git rev-parse --abbrev-ref HEAD).remote)/$(git rev-parse --abbrev-ref HEAD) -b'
```

## Conclusión

Colaborar en un proyecto de GitHub puede parecer complicado al principio, pero al seguir estos pasos y usar estas analogías, te convertirás en un miembro valioso del equipo de desarrollo. ¡Listo para cocinar tu próximo plato de código!

---

## 1. Usando Respuestas Guardadas

Cuando comentas en un **issue** o **pull request**, puedes agregar una respuesta guardada que ya hayas configurado. Imagina que tienes una receta favorita que siempre compartes con tus amigos; en lugar de escribirla de nuevo cada vez, simplemente la guardas y la compartes con un clic.

### Pasos para agregar una respuesta guardada:

1. En GitHub, navega a la página principal del repositorio.
2. Haz clic en **Issues** o **Pull requests**.
3. Selecciona el **issue** o **pull request** deseado.
4. Para agregar una respuesta guardada, selecciona el ícono de respuesta guardada sobre el campo de comentario.
5. Elige la respuesta que deseas agregar. Puedes editar el contenido si lo necesitas.
6. Selecciona **Comment** para añadir tu comentario.

### Consejo
Puedes usar un atajo de teclado para autocompletar el comentario con una respuesta guardada. Esto es como tener una tecla mágica para compartir tus recetas sin esfuerzo.

---

## 2. Mencionando a Alguien (@mencion)

¿Alguna vez has querido llamar la atención de alguien específico sobre un **issue** o **pull request**? Puedes hacerlo usando **@menciones**. Es como levantar la mano en una clase para que el profesor se fije en ti.

### Cómo funcionan las @menciones:

Cuando mencionas a un usuario de GitHub con **@nombredeusuario**, esa persona recibe una notificación y se suscribe a futuras actualizaciones. Esto asegura que no se pierda nada importante, como un estudiante que siempre está al tanto de las tareas.

### Mejoras en el Control de Notificaciones
Ahora puedes gestionar las configuraciones de notificación a nivel de **issue** o **pull request**. Esto te permite suscribirte a **issues** que te interesen sin tener que comentar, o darte de baja de **issues** que ya no son relevantes.

---

## 3. Agregar Reacciones a Pull Requests, Issues y Comentarios

Las conversaciones en GitHub son como un café donde muchos amigos se reúnen a charlar sobre proyectos, ideas y soluciones. A veces, solo quieres mostrar tu apoyo a un comentario sin tener que responder con un largo mensaje. Aquí es donde entran las **reacciones**.

### Uso de Reacciones:
Ahora puedes expresar tus sentimientos con reacciones como 👍, 👎, 😄, 😕, ❤, 🎉. Es como si tuvieras un botón de "me gusta" en la vida real, permitiendo que la conversación fluya sin el ruido de muchos comentarios.

---

## 4. Introducción a GitHub Discussions

**GitHub Discussions** es como un foro de café donde la comunidad puede conversar sobre un proyecto. A diferencia de los **issues**, que están más orientados a problemas específicos, las discusiones permiten un diálogo más fluido y abierto.

### Cómo habilitar GitHub Discussions:

1. Navega a la página principal de tu repositorio en GitHub.
2. Haz clic en **Settings**.
3. Desplázate a la sección "Features" y haz clic en **Set up discussions**.
4. Edita la plantilla de discusión según los recursos y el tono que deseas establecer para tu comunidad.

### Promoviendo Contribuciones
Puedes crear una publicación de bienvenida para invitar a la comunidad a participar y establecer pautas sobre cómo comunicarse. Esto es como poner un cartel de bienvenida en tu cafetería para que todos se sientan cómodos al entrar.

---

## Conclusión

A medida que avances en tu camino para convertirte en un Frontend Developer, recuerda que cada herramienta y técnica que aprendas es como un ingrediente en tu receta de éxito. Tómate tu tiempo para experimentar y disfrutar del proceso. ¡Feliz codificación!

---

# Roadmap para Convertirse en Frontend Developer

## Creando una Solicitud de Extracción desde un Fork

### Introducción

Crear una solicitud de extracción (pull request) desde un fork es como enviar una propuesta para hacer cambios en un proyecto en grupo. Imagina que tienes una hoja de trabajo en la que estás trabajando, y quieres sugerir que ciertas modificaciones se incorporen al documento principal. 

### ¿Quién puede usar esta función?

Cualquiera que tenga acceso de escritura a un repositorio puede crear una solicitud de extracción desde un fork. Piensa en ello como tener el permiso de un profesor para hacer cambios en su cuaderno. 

Si tu solicitud de extracción compara tu rama de trabajo (también conocida como "rama de características") con una rama en el repositorio original (la rama base), tu rama de trabajo se llama "rama de comparación". 

**Ejemplo:**
- Tu rama de trabajo (o “rama de características”) es donde estás haciendo cambios en tu repositorio bifurcado (por ejemplo, `mi-rama-de-tema`).
- La rama base es la rama en el repositorio original donde deseas fusionar tus cambios (por ejemplo, `main`).
- La solicitud de extracción compara los cambios propuestos por tu rama de trabajo (`mi-rama-de-tema`) con la rama base (`main`), por lo que `mi-rama-de-tema` se conoce como la "rama de comparación".

### Cómo crear una Solicitud de Extracción

1. Navega al repositorio original donde creaste tu fork.
2. En la parte superior de la lista de archivos, en la barra amarilla, haz clic en **Comparar y crear solicitud de extracción** para crear una solicitud para la rama asociada.
3. En la página para crear una nueva solicitud de extracción, haz clic en **comparar entre forks**.
4. En el menú desplegable de "rama base", selecciona la rama del repositorio original a la que deseas fusionar los cambios.
5. En el menú desplegable "fork de cabeza", selecciona tu fork, luego utiliza el menú desplegable "rama de comparación" para seleccionar la rama donde hiciste tus cambios.
6. Escribe un título y una descripción para tu solicitud de extracción.

Si deseas permitir que cualquier persona con acceso de escritura al repositorio original pueda hacer cambios en tu solicitud de extracción, selecciona **Permitir ediciones por parte de los mantenedores**.

### Advertencia

Si tu fork contiene flujos de trabajo de GitHub Actions, la opción es **Permitir ediciones y acceso a secretos por parte de los mantenedores**. Esto también permite a un mantenedor editar los flujos de trabajo del repositorio bifurcado, lo que puede revelar valores secretos.

### Creando la Solicitud de Extracción

Para crear una solicitud de extracción lista para revisión, haz clic en **Crear solicitud de extracción**. Para crear una solicitud de extracción en borrador, utiliza el menú desplegable y selecciona **Crear solicitud de extracción en borrador**, luego haz clic en **Solicitud de extracción en borrador**.

**Consejo:** Después de crear una solicitud de extracción, puedes pedir a una persona específica que revise tus cambios propuestos.

---

## Invitando Colaboradores a un Repositorio Personal

### Introducción

Invitar a otros a colaborar en tu repositorio es como abrir la puerta de tu casa a amigos para que te ayuden a organizar una fiesta. Puedes permitirles que participen y colaboren en el proyecto.

### ¿Quién puede usar esta función?

Si estás utilizando GitHub Free, puedes agregar colaboradores ilimitados en repositorios públicos y privados. Piensa en esto como tener un club donde puedes invitar a tantas personas como desees.

### Sobre la Colaboración en un Repositorio Personal

Para colaborar con usuarios en un repositorio que pertenece a tu cuenta personal en GitHub, puedes invitarlos como colaboradores. Es como permitir que amigos específicos accedan a tus juguetes para jugar juntos.

Si deseas otorgar un acceso más granular al repositorio, puedes crear un repositorio dentro de una organización.

### Cómo Invitar a un Colaborador

1. Pregunta el nombre de usuario de la persona que deseas invitar como colaborador. Si aún no tienen un nombre de usuario, pueden registrarse en GitHub.
2. En GitHub, navega a la página principal del repositorio.
3. Bajo el nombre de tu repositorio, haz clic en **Configuración**.
4. En la sección "Acceso" de la barra lateral, haz clic en **Colaboradores**.
5. Haz clic en **Agregar personas**.
6. En el campo de búsqueda, comienza a escribir el nombre de la persona que deseas invitar, luego selecciona un nombre de la lista de coincidencias.
7. Haz clic en **Agregar NOMBRE al REPOSITORIO**.

El usuario recibirá un correo electrónico invitándolo al repositorio. Una vez que acepten tu invitación, tendrán acceso como colaboradores a tu repositorio.

### Nota Importante

GitHub limita el número de personas que pueden ser invitadas a un repositorio dentro de un período de 24 horas. Si superas este límite, debes esperar 24 horas o crear una organización para colaborar con más personas.

---

# Hoja de Ruta para Convertirse en Desarrollador Frontend

## Agregar Colaboradores Externos a Repositorios en tu Organización

### Introducción

Agregar colaboradores externos a tus repositorios es como abrir las puertas de tu taller a un amigo que no es parte del club, pero que tiene habilidades que pueden ayudar a mejorar el proyecto. 

### ¿Quién Puede Usar Esta Función?

Las personas con acceso de administrador a un repositorio pueden agregar a un colaborador externo. Esto es como tener la llave del taller que solo algunas personas pueden usar.

### Sobre Colaboradores Externos

Un colaborador externo es alguien que no es miembro de tu organización, pero que tiene acceso a uno o más repositorios de la misma. Puedes elegir el nivel de acceso que otorgar a cada colaborador externo, como decidir si tu amigo puede solo mirar o también trabajar en el proyecto.

Cuando agregas un colaborador externo a un repositorio, también deberás agregarlo a cualquier bifurcación del repositorio a la que quieras que tenga acceso. Esto es como permitirle a tu amigo acceder a las copias de los planos del taller.

### Consideraciones

- Si agregas un colaborador externo a un repositorio privado y no estás en un plan gratuito, esto utilizará una de tus licencias pagadas. 
- Las organizaciones que usan GitHub Enterprise Cloud pueden restringir la capacidad de invitar colaboradores externos.
- Si tu organización requiere autenticación de dos factores, todos los colaboradores externos deben activarla antes de aceptar tu invitación para colaborar en un repositorio.

### Cómo Agregar Colaboradores Externos a un Repositorio

Puedes otorgar acceso a colaboradores externos a un repositorio en la configuración del mismo. Imagina que es como añadir un nuevo amigo a la lista de personas que pueden entrar al taller.

---

## Sobre Issues

### Introducción

Los issues son una herramienta esencial en GitHub que te permite planificar, discutir y rastrear tareas, ideas y errores. Piensa en los issues como una pizarra donde anotas todo lo que hay que hacer, desde arreglos pequeños hasta grandes proyectos.

### Acerca de los Sub-Issues

Puedes dividir un issue en sub-issues para descomponer tareas más grandes en partes más manejables, como dividir una fiesta en diferentes tareas: decoración, comida, música, etc. Esto ayuda a que el trabajo se organice y sea más claro.

### Integración con GitHub

Los issues se integran con todo tu trabajo en GitHub. Mencionar un issue en otro issue o pull request crea referencias entre ellos, facilitando el seguimiento del progreso.

### Mantente Actualizado

Puedes suscribirte a un issue para recibir notificaciones sobre los últimos comentarios. Es como recibir actualizaciones sobre el progreso de las tareas que has delegado.

### Gestión de la Comunidad

Para ayudar a los colaboradores a abrir issues significativos, puedes usar formularios de issues y plantillas. Esto es como darles a tus amigos una lista de preguntas que deben responder para que puedas obtener la información que necesitas.

### Comunicación Eficiente

Puedes mencionar a tus colaboradores en un issue para atraer su atención, o asignar issues para que quede claro quién está trabajando en qué tarea. Esto ayuda a mantener la comunicación fluida, como pasarle un mensaje a un compañero para que sepa qué debe hacer.

### Comparando Issues y Discusiones

No todas las conversaciones son adecuadas para issues. Para discusiones más generales o preguntas, puedes usar GitHub Discussions, que es como tener una charla informal con amigos en lugar de una reunión de trabajo.

---

## Clonar y Bifurcar Repositorios en GitHub

### Introducción

Una de las principales ventajas de usar un sistema de control de versiones es la capacidad de obtener tu propia copia de un proyecto de manera rápida y sencilla. Clonar y bifurcar son las dos maneras más comunes de copiar un repositorio en GitHub.

### ¿Qué es Clonar?

Clonar un repositorio significa crear una copia local en tu computadora que puedes sincronizar con el repositorio remoto en GitHub. Es como llevarte un libro de la biblioteca para leerlo en casa y hacer anotaciones.

### ¿Y Qué hay de Bifurcar?

Una bifurcación es una copia de un repositorio que te permite hacer cambios sin afectar el proyecto original. Es como tomar una receta familiar y modificarla a tu gusto, sin alterar la receta original. Puedes contribuir de vuelta al proyecto original a través de Pull Requests.

### Cómo Clonar un Repositorio

Para clonar un repositorio, ve a la página principal del repositorio y haz clic en el botón verde **Code**. En el menú desplegable, tendrás la opción de clonar mediante HTTPS, SSH o usando GitHub CLI.

### Cómo Bifurcar un Repositorio

Bifurcar un proyecto es tan fácil como hacer clic en el botón **Fork** en la parte superior de la página del repositorio. Una vez completado, se te llevará a tu copia bifurcada donde puedes comenzar a colaborar.