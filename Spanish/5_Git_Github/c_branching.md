# Git Branching - Basic Branching and Merging

## Introducción

En este artículo, exploraremos cómo funciona el **branching** (ramificación) y **merging** (fusión) en Git a través de un ejemplo sencillo. Imaginemos que estamos trabajando en una página web y debemos gestionar nuestro trabajo de manera efectiva.

## Ejemplo de Ramificación y Fusión

Imagina que estás trabajando en un proyecto web. Tu tarea es mejorar la sección del pie de página para un nuevo usuario. Tu proceso sería el siguiente:

1. Haces algunas mejoras en la página web.
2. Creas una **rama** (branch) para la nueva historia de usuario en la que estás trabajando.
3. Realizas cambios en esa rama.
4. En ese momento, recibes un aviso de que hay un problema crítico que necesita un **hotfix** (corrección urgente). Entonces, harás lo siguiente:
   - Cambias a la rama de producción.
   - Creas una rama para agregar la corrección.
   - Después de probarlo, fusionas la rama del hotfix y la envías a producción.
5. Finalmente, regresas a tu historia de usuario y continúas trabajando.

### Ramificación Básica

Supongamos que ya tienes algunos commits en la rama `master` de tu proyecto. Tu historial de commits es sencillo.

#### Creación de una Nueva Rama

Para crear una nueva rama y cambiarte a ella al mismo tiempo, puedes usar el siguiente comando:

```bash
$ git checkout -b iss53
Switched to a new branch "iss53"
```

Este comando es un atajo para:

```bash
$ git branch iss53
$ git checkout iss53
```

Cuando trabajas en tu página web y haces algunos commits, la rama `iss53` avanza porque la tienes seleccionada (es decir, tu `HEAD` apunta a ella):

```bash
$ vim index.html
$ git commit -a -m 'Crear nuevo pie de página [issue 53]'
```

### Realizando un Hotfix

Ahora, recibes un aviso de que hay un problema con el sitio web que necesita atención inmediata. Con Git, no es necesario que envíes tu arreglo junto con los cambios de `iss53`, ni que inviertas mucho esfuerzo en revertir esos cambios antes de trabajar en el arreglo. Simplemente cambias de vuelta a la rama `master`:

```bash
$ git checkout master
Switched to branch 'master'
```

Tu directorio de trabajo ahora es exactamente como estaba antes de que comenzaras a trabajar en `iss53`, lo que te permite concentrarte en tu hotfix.

Ahora creas una nueva rama para el hotfix:

```bash
$ git checkout -b hotfix
Switched to a new branch 'hotfix'
```

Realizas las modificaciones necesarias y confirmas el cambio:

```bash
$ vim index.html
$ git commit -a -m 'Corregir dirección de correo electrónico rota'
```

#### Fusión del Hotfix

Una vez que estés seguro de que tu hotfix está correcto, fusionas la rama `hotfix` de vuelta a `master`:

```bash
$ git checkout master
$ git merge hotfix
```

Notarás que el mensaje indica "fast-forward" en esa fusión. Esto sucede porque el commit de la rama `hotfix` que fusionaste está directamente adelante del commit en el que estás actualmente, por lo que Git simplemente mueve el puntero hacia adelante.

### Regresando a tu Historia de Usuario

Después de desplegar la corrección importante, estás listo para regresar al trabajo que estabas realizando antes de ser interrumpido. Primero, eliminas la rama `hotfix` porque ya no la necesitas:

```bash
$ git branch -d hotfix
Deleted branch hotfix (3a0874c).
```

Ahora, puedes volver a tu rama de trabajo en `iss53` y continuar:

```bash
$ git checkout iss53
Switched to branch "iss53"
$ vim index.html
$ git commit -a -m 'Terminar el nuevo pie de página [issue 53]'
```

Es importante notar que los cambios que hiciste en la rama `hotfix` no están contenidos en los archivos de la rama `iss53`. Si necesitas integrarlos, puedes fusionar la rama `master` en tu rama `iss53` cuando lo decidas.

### Fusión Básica

Supongamos que decides que tu trabajo en `issue #53` está completo y listo para ser fusionado en la rama `master`. Para hacer eso, fusionas tu rama `iss53` en `master`, de manera similar a como fusionaste tu rama `hotfix`:

```bash
$ git checkout master
Switched to branch 'master'
$ git merge iss53
```

### Conflictos de Fusión Básicos

A veces, el proceso de fusión no es tan fluido. Si cambiaste la misma parte del mismo archivo de manera diferente en las dos ramas que estás fusionando, Git no podrá fusionarlas correctamente. Si tu arreglo para `issue #53` modificó la misma parte de un archivo que la rama del hotfix, recibirás un conflicto de fusión.

Cuando esto sucede, Git no ha creado automáticamente un nuevo commit de fusión. En cambio, ha pausado el proceso hasta que resuelvas el conflicto. Puedes ver cuáles archivos no se han fusionado ejecutando:

```bash
$ git status
```

Los archivos que tienen conflictos se marcarán como "no fusionados". Git agrega marcadores estándar de resolución de conflictos en los archivos que tienen problemas, lo que te permite abrirlos manualmente y resolver esos conflictos.

Por ejemplo, un conflicto podría verse así:

```html
<<<<<<< HEAD:index.html
<div id="footer">contact : email.support@github.com</div>
=======
<div id="footer">
 please contact us at support@github.com
</div>
>>>>>>> iss53:index.html
```

Para resolver el conflicto, debes elegir un lado o el otro o fusionar el contenido tú mismo.

Una vez que hayas resuelto todos los conflictos, ejecutas `git add` en cada archivo para marcarlos como resueltos.

### Conclusión

El uso de ramas y fusiones en Git permite gestionar el desarrollo de manera efectiva y ordenada. Al crear ramas para diferentes tareas, puedes trabajar en múltiples características o correcciones sin interferir con la línea principal de desarrollo. Resolver conflictos puede ser un desafío, pero con práctica y herramientas adecuadas, se puede manejar fácilmente. 

¡Continúa explorando más sobre Git y mejora tus habilidades como desarrollador Frontend!

---

# git branch - Listar, crear o eliminar ramas

## Sinopsis
```bash
git branch [--color[=<when>] | --no-color] [--show-current]
    [-v [--abbrev=<n> | --no-abbrev]]
    [--column[=<options>] | --no-column] [--sort=<key>]
    [--merged [<commit>]] [--no-merged [<commit>]]
    [--contains [<commit>]] [--no-contains [<commit>]]
    [--points-at <object>] [--format=<format>]
    [(-r | --remotes) | (-a | --all)]
    [--list] [<pattern>… ]
git branch [--track[=(direct|inherit)] | --no-track] [-f]
    [--recurse-submodules] <branchname> [<start-point>]
git branch (--set-upstream-to=<upstream> | -u <upstream>) [<branchname>]
git branch --unset-upstream [<branchname>]
git branch (-m | -M) [<oldbranch>] <newbranch>
git branch (-c | -C) [<oldbranch>] <newbranch>
git branch (-d | -D) [-r] <branchname>… 
git branch --edit-description [<branchname>]
```

## Descripción

Imagina que tu proyecto es un árbol con muchas ramas. Cada vez que quieres explorar una nueva idea o funcionalidad sin afectar el "tronco" principal, creas una nueva rama. Aquí es donde entra el comando `git branch`.

### Listar Ramas
Cuando utilizas `git branch` sin argumentos, estás pidiendo a Git que te muestre todas las ramas que tienes, como si estuvieras mirando todas las ramas de un árbol. La rama actual estará marcada con un asterisco (*), para que sepas en qué rama estás trabajando.

```bash
git branch
```

### Crear una Nueva Rama
Si quieres explorar una nueva funcionalidad, puedes crear una nueva rama. Esto es como tomar una rama del árbol y empezar a hacerle cambios sin tocar el tronco. Para crear una nueva rama, simplemente usas:

```bash
git branch <nombre-de-la-rama>
```

Sin embargo, esto no cambiará a esa nueva rama automáticamente. Para hacerlo, necesitas usar:

```bash
git switch <nombre-de-la-rama>
```

### Renombrar Ramas
Si decides que el nombre de tu rama no refleja lo que estás haciendo, puedes cambiarlo. Es como si decides que una rama del árbol debería llamarse "Rama de Frutos" en lugar de "Rama Secundaria". Para renombrar una rama, puedes usar:

```bash
git branch -m <nombre-antiguo> <nombre-nuevo>
```

### Eliminar Ramas
Cuando terminas de trabajar en una funcionalidad y ya no necesitas esa rama, puedes eliminarla. Es como si cortaras una rama que ya no te interesa. Para eliminar una rama, utilizas:

```bash
git branch -d <nombre-de-la-rama>
```

Si la rama aún tiene cambios no fusionados y estás seguro de que deseas eliminarla, puedes usar:

```bash
git branch -D <nombre-de-la-rama>
```

## Opciones Comunes

- `-d`: Eliminar una rama que ya ha sido fusionada.
- `-D`: Forzar la eliminación de una rama, incluso si no ha sido fusionada.
- `-m`: Renombrar una rama.
- `-r`: Listar ramas remotas.
- `-a`: Listar todas las ramas, tanto locales como remotas.

## Ejemplo Práctico

1. **Listar Ramas**:
   ```bash
   git branch
   ```
   Salida esperada:
   ```
   * main
     feature-nueva-funcionalidad
   ```

2. **Crear una Nueva Rama**:
   ```bash
   git branch nueva-rama
   ```

3. **Cambiar a la Nueva Rama**:
   ```bash
   git switch nueva-rama
   ```

4. **Renombrar la Rama**:
   ```bash
   git branch -m nueva-rama rama-renombrada
   ```

5. **Eliminar la Rama**:
   ```bash
   git branch -d rama-renombrada
   ```

## Conclusión

El comando `git branch` es una herramienta fundamental para gestionar y organizar el trabajo en tus proyectos de desarrollo. Al entender cómo crear, listar, renombrar y eliminar ramas, podrás mantener tu código ordenado y hacer cambios sin riesgo en el tronco principal de tu proyecto.

---

# Guía de Ramas en GitHub

## Renombrando una Rama

Renombrar una rama es un proceso sencillo que puede hacer cualquier persona con permisos de escritura en el repositorio. Sin embargo, si la rama es la predeterminada o está protegida, solo los administradores pueden realizar esta acción.

### ¿Quién puede usar esta función?

Las personas con permisos de escritura pueden renombrar ramas, pero no pueden hacerlo con la rama predeterminada o las ramas protegidas. Los administradores pueden renombrar cualquier rama, incluso las predeterminadas y protegidas.

### En este artículo

- Acerca de renombrar ramas
- Renombrar una rama
- Actualizando un clon local después de cambiar el nombre de una rama

### Acerca de renombrar ramas

Renombrar una rama en GitHub es como cambiar el nombre de un camino en un mapa. Cuando haces esto, todos los enlaces que contienen el viejo nombre de la rama se redirigen automáticamente al nuevo nombre. Es importante saber que si renombraste una rama que estaba en una solicitud de extracción (pull request), esa solicitud se cerrará.

### Renombrar una rama

Para renombrar una rama en GitHub:

1. Ve a la página principal del repositorio.
2. En la vista del árbol de archivos a la izquierda, selecciona el menú desplegable de ramas y luego haz clic en "Ver todas las ramas".
3. Junto a la rama que deseas renombrar, selecciona el menú desplegable y haz clic en "Renombrar rama".
4. Escribe un nuevo nombre para la rama.
5. Revisa la información sobre los entornos locales y luego haz clic en "Renombrar rama".

### Actualizando un clon local después de cambiar el nombre de una rama

Una vez que hayas renombrado una rama en GitHub, cualquier colaborador con un clon local del repositorio deberá actualizar su clon. Para hacerlo, ejecuta los siguientes comandos en tu terminal:

```bash
git branch -m OLD-BRANCH-NAME NEW-BRANCH-NAME
git fetch origin
git branch -u origin/NEW-BRANCH-NAME NEW-BRANCH-NAME
git remote set-head origin -a
```

Opcionalmente, puedes ejecutar el siguiente comando para eliminar las referencias de seguimiento al viejo nombre de la rama:

```bash
git remote prune origin
```

---

## Creando y Eliminando Ramas en tu Repositorio

Puedes crear o eliminar ramas directamente en GitHub. Aquí te explicamos cómo hacerlo.

### Creando una Rama

Puedes crear una rama de diferentes maneras en GitHub. Imagina que estás creando un nuevo sendero en el bosque; tienes que elegir un buen nombre para que otros sepan adónde conduce.

#### Crear una rama a través de la vista general de ramas

1. Ve a la página principal del repositorio.
2. En la vista del árbol de archivos a la izquierda, selecciona el menú desplegable de ramas y luego haz clic en "Ver todas las ramas".
3. Haz clic en "Nueva rama".
4. Escribe un nombre para la nueva rama.
5. Elige una fuente para tu rama (si tu repositorio es un fork, selecciona el repositorio correspondiente).
6. Haz clic en "Crear rama".

#### Crear una rama usando el menú desplegable de ramas

1. Ve a la página principal del repositorio.
2. Selecciona el menú desplegable de ramas.
3. Si quieres crear una nueva rama a partir de una rama diferente a la predeterminada, selecciona primero la otra rama.
4. En el campo de texto "Encontrar o crear una rama...", escribe un nombre único para tu nueva rama y haz clic en "Crear rama".

### Eliminando una Rama

Eliminar una rama es como limpiar el sendero en el bosque cuando ya no lo necesitas. Pero asegúrate de que no esté en uso.

1. Ve a la página principal del repositorio.
2. Desde la vista del árbol de archivos a la izquierda, selecciona el menú desplegable de ramas y haz clic en "Ver todas las ramas".
3. Junto a la rama que deseas eliminar, haz clic en el ícono de la papelera.
4. Si la rama está asociada a al menos una solicitud de extracción abierta, se cerrarán esas solicitudes. Lee la advertencia y haz clic en "Eliminar".

Recuerda, si la rama que deseas eliminar es la rama predeterminada, primero tendrás que elegir una nueva rama predeterminada antes de eliminarla.

## Conclusión

Manejar ramas en GitHub es fundamental para un flujo de trabajo eficiente. Entender cómo renombrar, crear y eliminar ramas te ayudará a mantener tu proyecto organizado y en buen camino. Piensa en las ramas como senderos en un bosque: algunos llevan a lugares interesantes, otros se pueden eliminar cuando ya no son útiles.

---

# git checkout - Cambiar ramas o restaurar archivos del árbol de trabajo

## SINOPSIS
```bash
git checkout [-q] [-f] [-m] [<branch>]
git checkout [-q] [-f] [-m] --detach [<branch>]
git checkout [-q] [-f] [-m] [--detach] <commit>
git checkout [-q] [-f] [-m] [[-b|-B|--orphan] <new-branch>] [<start-point>]
git checkout [-f] <tree-ish> [--] <pathspec>… 
git checkout [-f] <tree-ish> --pathspec-from-file=<file> [--pathspec-file-nul]
git checkout [-f|--ours|--theirs|-m|--conflict=<style>] [--] <pathspec>… 
git checkout [-f|--ours|--theirs|-m|--conflict=<style>] --pathspec-from-file=<file> [--pathspec-file-nul]
git checkout (-p|--patch) [<tree-ish>] [--] [<pathspec>… ]
```

## DESCRIPCIÓN

El comando `git checkout` actualiza los archivos en el árbol de trabajo para que coincidan con la versión en el índice o con el árbol especificado. Si no se proporciona un `pathspec`, `git checkout` también actualizará `HEAD` para establecer la rama especificada como la rama actual.

### Analogía
Imagina que estás en una biblioteca. Cada sección de la biblioteca representa una rama diferente de un libro. Cuando haces `git checkout <branch>`, es como si estuvieras moviéndote de una sección a otra de la biblioteca. Llevas contigo tus notas (cambios locales), pero cambias la sección donde estás leyendo. Al hacerlo, aseguras que puedes seguir trabajando en tus notas, pero en el contexto de la nueva sección (rama).

### Cambiar de Rama
Para preparar el trabajo en `<branch>`, cambia a ella actualizando el índice y los archivos en el árbol de trabajo, y apuntando `HEAD` a la rama. Las modificaciones locales en los archivos del árbol de trabajo se mantienen para que puedan ser confirmadas en `<branch>`.

Si `<branch>` no se encuentra pero existe una rama de seguimiento en exactamente un remoto (llámalo `<remote>`) con un nombre coincidente, se tratará como equivalente a:
```bash
$ git checkout -b <branch> --track <remote>/<branch>
```

### Creando una Nueva Rama
Puedes crear una nueva rama con:
```bash
git checkout -b <new-branch> [<start-point>]
```
Esto es similar a abrir un nuevo libro en la biblioteca. Si utilizas `-B`, se crea la rama si no existe, o se restablece si ya existe. Es como si, al regresar a una sección anterior, decidieras volver a empezar desde allí pero con un nuevo libro.

### Desacoplando HEAD
Puedes trabajar sobre un `<commit>` específico usando `git checkout --detach [<branch>]`. Esto es como tomar un libro y leer un capítulo específico sin seguir la secuencia del libro completo. Estás libre de hacer cambios sin afectar el resto del contenido.

### Opciones
- **-q, --quiet**: Suprime mensajes de retroalimentación. Como leer en silencio en una biblioteca.
- **-f, --force**: Ignora los cambios no confirmados y procede con el cambio de rama, como si decidieras ignorar las notas que tenías y simplemente cambiar de sección.
- **--ours / --theirs**: Al resolver conflictos, selecciona qué versión de los cambios deseas conservar, como elegir entre dos libros diferentes que ofrecen soluciones distintas al mismo problema.

### Resumiendo
El comando `git checkout` es fundamental para navegar y gestionar tus ramas en Git. Al igual que en una biblioteca, puedes mover tus ideas (cambios) entre diferentes libros (ramas), crear nuevas historias (nuevas ramas) y, a veces, decidir explorar un capítulo sin seguir el orden habitual (desacoplar HEAD).