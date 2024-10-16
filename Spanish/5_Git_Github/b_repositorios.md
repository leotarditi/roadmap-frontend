# Sobre los Repositorios

Un repositorio contiene todo tu código, tus archivos y el historial de revisiones de cada archivo. Puedes discutir y gestionar tu trabajo dentro del repositorio.

## En este artículo

- Sobre los repositorios
- Terminología de repositorios
- Sobre la propiedad del repositorio
- Sobre la colaboración
- Sobre la visibilidad del repositorio
- Próximos pasos

## Sobre los Repositorios

Un repositorio es el elemento más básico de GitHub. Es un lugar donde puedes almacenar tu código, tus archivos y el historial de revisiones de cada archivo. Imagina que un repositorio es como una caja de herramientas: dentro guardas todas tus herramientas (código y archivos) y también tienes un registro de cuándo utilizaste cada herramienta (historial de revisiones). 

Los repositorios pueden tener múltiples colaboradores y pueden ser públicos o privados. Puedes crear un nuevo repositorio yendo a [https://github.com/new](https://github.com/new). Para obtener instrucciones, consulta "Introducción rápida a los repositorios".

## Terminología de Repositorios

Antes de empezar con los repositorios, aprende estos términos importantes.

| Término        | Definición                                                                                     |
|----------------|------------------------------------------------------------------------------------------------|
| **Branch**     | Una versión paralela de tu código que está contenida dentro del repositorio, pero no afecta a la rama principal. Piensa en una rama de un árbol que crece en una dirección diferente, pero sigue conectada al tronco. |
| **Clone**      | Descargar una copia completa de los datos de un repositorio desde GitHub.com, incluyendo todas las versiones de cada archivo y carpeta. Es como hacer una fotocopia de un libro completo. |
| **Fork**       | Un nuevo repositorio que comparte código y configuraciones de visibilidad con el repositorio original "upstream". Es como tomar prestada una receta y adaptarla a tu estilo. |
| **Merge**      | Tomar los cambios de una rama y aplicarlos a otra. Es como combinar dos versiones de un libro para crear una edición revisada. |
| **Pull request** | Una solicitud para fusionar cambios de una rama a otra. Piensa en esto como pedirle a un editor que revise y apruebe tus cambios en el manuscrito. |
| **Remote**     | Un repositorio almacenado en GitHub, no en tu computadora. Imagina que es una copia de tu libro que está en una biblioteca, mientras que tú tienes la versión física. |
| **Upstream**   | La rama en un repositorio original que ha sido bifurcada o clonada. La rama correspondiente en la rama clonada o bifurcada se llama "downstream". Es como el río principal que da origen a un afluente. |

## Sobre la Propiedad del Repositorio

Puedes ser el propietario de repositorios individualmente, o puedes compartir la propiedad de repositorios con otras personas en una organización. Es como tener una casa (repositorio) que puedes poseer solo tú o compartir con tus amigos.

En cualquier caso, el acceso a los repositorios se gestiona mediante permisos. Para más información, consulta "Niveles de permiso para un repositorio de cuenta personal" y "Roles de repositorio para una organización".

## Sobre la Colaboración

Puedes utilizar los repositorios para gestionar tu trabajo y colaborar con otros. Es como trabajar en un proyecto de grupo: cada miembro tiene su rol y puede aportar ideas.

- Puedes usar **issues** para recopilar comentarios de usuarios, reportar errores de software y organizar tareas que te gustaría realizar. Para más información, consulta "Sobre los issues".
- Puedes usar **GitHub Discussions** para hacer y responder preguntas, compartir información, hacer anuncios y participar en conversaciones sobre un proyecto. Para más información, consulta "Sobre las discusiones".
- Puedes usar **pull requests** para proponer cambios en un repositorio. Para más información, consulta "Sobre las pull requests".
- Puedes usar **Projects** para organizar y priorizar tus issues y pull requests. Para más información, consulta "Sobre Projects".

Con GitHub Free para cuentas personales y organizaciones, puedes trabajar con colaboradores ilimitados en repositorios públicos ilimitados con un conjunto completo de funciones, o en repositorios privados ilimitados con un conjunto de funciones limitado. Para obtener herramientas avanzadas para repositorios privados, puedes actualizar a GitHub Pro, GitHub Team o GitHub Enterprise Cloud. Para más información, consulta "Planes de GitHub".

## Sobre la Visibilidad del Repositorio

Puedes restringir quién tiene acceso a un repositorio eligiendo la visibilidad del repositorio: pública o privada. Es como decidir si quieres que tu casa sea visible para todos o si prefieres mantenerla cerrada a un grupo selecto.

Cuando creas un repositorio, puedes elegir hacerlo público o privado. Los repositorios en organizaciones que utilizan GitHub Enterprise Cloud y son propiedad de una cuenta de empresa también se pueden crear con visibilidad interna. Para más información, consulta la documentación de GitHub Enterprise Cloud.

- **Los repositorios públicos** son accesibles para todos en Internet.
- **Los repositorios privados** son accesibles solo para ti, las personas con las que compartes explícitamente el acceso y, en el caso de los repositorios de organización, ciertos miembros de la organización.
- Los propietarios de la organización siempre tienen acceso a cada repositorio creado en una organización. Para más información, consulta "Roles de repositorio para una organización".

Las personas con permisos de administrador para un repositorio pueden cambiar la visibilidad de un repositorio existente. Para más información, consulta "Configuración de la visibilidad del repositorio".

---

# git-init - Crear un repositorio Git vacío o reinicializar uno existente

## SINOPSIS
`git init [-q | --quiet] [--bare] [--template=<directorio-de-plantilla>]`  
`      [--separate-git-dir <git-dir>] [--object-format=<formato>]`  
`      [--ref-format=<formato>]`  
`      [-b <nombre-de-rama> | --initial-branch=<nombre-de-rama>]`  
`      [--shared[=<permisos>]] [<directorio>]`

## DESCRIPCIÓN
Este comando crea un repositorio Git vacío, que básicamente es un directorio `.git` con subdirectorios para objetos, referencias/ramas, referencias/etiquetas y archivos de plantilla. Se creará una rama inicial sin ningún commit (vea la opción `--initial-branch` a continuación para su nombre).

### Analogía
Imagina que estás construyendo una casa (repositorio). Cuando ejecutas `git init`, estás estableciendo la estructura básica de tu casa. La carpeta `.git` es como el cimiento y las paredes; dentro de ella se encuentran todas las herramientas y materiales (objetos, referencias) que necesitas para construir tu hogar (proyecto). La rama inicial es como el primer piso de tu casa, donde empezarás a añadir habitaciones (cambios).

Si la variable de entorno `$GIT_DIR` está establecida, especifica una ruta a utilizar en lugar de `./.git` como base del repositorio.

Si el directorio de almacenamiento de objetos se especifica mediante la variable de entorno `$GIT_OBJECT_DIRECTORY`, entonces los directorios sha1 se crean en ese lugar; de lo contrario, se utiliza el directorio predeterminado `$GIT_DIR/objects`.

Ejecutar `git init` en un repositorio existente es seguro. No sobrescribirá lo que ya existe. La razón principal para volver a ejecutar `git init` es recoger nuevas plantillas agregadas (o mover el repositorio a otro lugar si se proporciona `--separate-git-dir`).

## OPCIONES
- `-q`  
  `--quiet`  
  Solo imprime mensajes de error y advertencia; todo otro output será suprimido.

- `--bare`  
  Crea un repositorio bare (sin archivos de trabajo). Si no se establece el entorno `GIT_DIR`, se establece en el directorio de trabajo actual.  
  **Analogía:** Un repositorio bare es como un terreno vacío sin casa; puedes ver el espacio, pero no hay nada construido sobre él.

- `--object-format=<formato>`  
  Especifica el formato de objeto (algoritmo de hash) para el repositorio. Los valores válidos son `sha1` y (si está habilitado) `sha256`. `sha1` es el predeterminado.  
  **Analogía:** Es como elegir el tipo de ladrillo que usarás para construir tu casa; diferentes materiales pueden tener diferentes características.

- `--template=<directorio-de-plantilla>`  
  Especifica el directorio del cual se utilizarán las plantillas. (Vea la sección "DIRECTORIO DE PLANTILLA" a continuación).

- `--separate-git-dir=<git-dir>`  
  En lugar de inicializar el repositorio como un directorio dentro de `$GIT_DIR` o `./.git/`, crea un archivo de texto que contenga la ruta al repositorio real. Este archivo actúa como un enlace simbólico a prueba de sistema de archivos al repositorio.  
  **Analogía:** Es como tener la dirección de tu casa en un papel en lugar de tener la casa en sí; sabes dónde está, pero no tienes que estar físicamente allí.

- `-b <nombre-de-rama>`  
  `--initial-branch=<nombre-de-rama>`  
  Usa `<nombre-de-rama>` para la rama inicial en el nuevo repositorio creado. Si no se especifica, se usa el nombre predeterminado (actualmente `master`, pero esto podría cambiar en el futuro).  
  **Analogía:** Esto es como decidir el nombre de tu casa; puede ser "Casa de la felicidad" o "Refugio de paz".

- `--shared[=(false|true|umask|group|all|world|everybody|<perm>)]`  
  Especifica que el repositorio Git debe ser compartido entre varios usuarios. Esto permite que los usuarios pertenecientes al mismo grupo puedan empujar cambios a ese repositorio.  
  **Analogía:** Es como tener una casa que se comparte entre amigos; todos pueden entrar y hacer mejoras.

## DIRECTORIO DE PLANTILLA
Los archivos y directorios en el directorio de plantilla cuyo nombre no comienza con un punto serán copiados al `$GIT_DIR` después de su creación.  
**Analogía:** Esto es como tener un conjunto de muebles (plantillas) que puedes usar para decorar tu casa; eliges qué poner en tu hogar.

El directorio de plantilla será uno de los siguientes (en orden):

- el argumento dado con la opción `--template`;
- el contenido de la variable de entorno `$GIT_TEMPLATE_DIR`;
- la variable de configuración `init.templateDir`; o
- el directorio de plantilla predeterminado: `/usr/share/git-core/templates`.

El directorio de plantilla predeterminado incluye una estructura de directorio, patrones de exclusión sugeridos (vea `gitignore[5]`), y archivos de gancho de muestra.

Los ganchos de muestra están deshabilitados por defecto. Para habilitar uno de los ganchos de muestra, renombrarlo eliminando su sufijo `.sample`.

## EJEMPLOS
### Iniciar un nuevo repositorio Git para un código existente
```bash
$ cd /ruta/a/mi/codigo
$ git init      (1)
$ git add .     (2)
$ git commit    (3)
```
1. Crea un directorio `/ruta/a/mi/codigo/.git`.
2. Agrega todos los archivos existentes al índice.
3. Registra el estado prístino como el primer commit en la historia.

## CONFIGURACIÓN
Todo lo que esté debajo de esta línea en esta sección se incluye selectivamente de la documentación de `git-config[1]`. El contenido es el mismo que el que se encuentra allí:

- `init.templateDir`  
  Especifica el directorio del cual se copiarán las plantillas.

- `init.defaultBranch`  
  Permite sobrescribir el nombre de la rama predeterminada, por ejemplo, al inicializar un nuevo repositorio.

- `init.defaultObjectFormat`  
  Permite sobrescribir el formato de objeto predeterminado para nuevos repositorios. Vea `--object-format=` en `git-init[1]`. Tanto la opción de línea de comando como la variable de entorno `GIT_DEFAULT_HASH` tienen prioridad sobre esta configuración.

- `init.defaultRefFormat`  
  Permite sobrescribir el formato de almacenamiento de referencia predeterminado para nuevos repositorios. Vea `--ref-format=` en `git-init[1]`. Tanto la opción de línea de comando como la variable de entorno `GIT_DEFAULT_REF_FORMAT` tienen prioridad sobre esta configuración.

---

# Git Config

En este documento, vamos a profundizar en el comando `git config`. Este comando es fundamental para la configuración de Git y permite establecer valores de configuración a nivel global o local en un proyecto. Las configuraciones se almacenan en archivos de texto llamados `.gitconfig`, y ejecutar `git config` modificará uno de esos archivos.

## ¿Qué es git config?

Imagina que Git es una tienda muy organizada. El comando `git config` actúa como un gerente que ayuda a establecer las reglas y configuraciones de la tienda. Estas reglas pueden variar dependiendo de si son para una tienda en particular (local) o para todas las tiendas de una cadena (global).

### Niveles de configuración

Los niveles de configuración en Git son:

- **Local**: Se aplica solo al repositorio en el que se ejecuta el comando. Los valores se almacenan en el archivo `.git/config` dentro del directorio del repositorio.
- **Global**: Se aplica a todos los repositorios del usuario en el sistema. Los valores se almacenan en el archivo `~/.gitconfig` en sistemas Unix o `C:\Users\<Usuario>\.gitconfig` en Windows.
- **System**: Se aplica a todo el sistema operativo y afecta a todos los usuarios y repositorios. El archivo de configuración se encuentra en `$(prefix)/etc/gitconfig` en Unix y en `C:\ProgramData\Git\config` en Windows.

### Uso básico

La forma más simple de usar `git config` es para ver una configuración específica. Por ejemplo, para ver la dirección de correo electrónico configurada:

```bash
git config user.email
```

Aquí, `user.email` es una propiedad que pertenece al bloque de configuración del usuario. Esto devolverá la dirección de correo electrónico que Git asociará con los commits creados localmente.

### Escribiendo valores

Para establecer una dirección de correo electrónico, puedes usar:

```bash
git config --global user.email "tu_email@example.com"
```

Esto configura el correo electrónico para el usuario actual en el sistema.

### Configuración del editor

Muchos comandos de Git requieren que se abra un editor de texto para ingresar información adicional. Puedes configurar el editor predeterminado con:

```bash
git config --global core.editor "nano"
```

Esto establece `nano` como el editor por defecto.

## Colores en la salida de Git

Git permite personalizar la salida de la terminal con colores, lo que facilita la lectura. Puedes activar los colores con:

```bash
git config --global color.ui auto
```

Esto aplicará colores a la salida de Git, haciendo que sea más fácil identificar errores y advertencias.

### Alias de Git

Los alias son atajos para comandos que usas con frecuencia. Por ejemplo, si quieres acortar el comando para hacer un commit, puedes crear un alias:

```bash
git config --global alias.ci commit
```

Ahora puedes usar `git ci` en lugar de `git commit`, ahorrando tiempo y esfuerzo.

### Resumen

En este artículo, hemos cubierto cómo usar el comando `git config` para configurar tu entorno de Git. Hemos visto cómo establecer el editor, los colores y los alias, además de cómo funciona la jerarquía de configuración.

Con un entendimiento básico de `git config`, podrás personalizar tu flujo de trabajo en Git y hacerlo más eficiente.

---

# Personalizando Git - Configuración de Git

Hasta ahora, hemos cubierto lo básico sobre cómo funciona Git y cómo usarlo, así como varias herramientas que proporciona para facilitar su uso. En este capítulo, veremos cómo puedes personalizar Git para que opere de manera más adaptada a tus necesidades, presentando varios ajustes de configuración importantes y el sistema de hooks. Con estas herramientas, es fácil hacer que Git funcione exactamente como tú, tu empresa o tu grupo lo necesitan.

## Configuración de Git

Al iniciar Git, puedes especificar los ajustes de configuración con el comando `git config`. Uno de los primeros pasos que diste fue configurar tu nombre y dirección de correo electrónico:

```bash
$ git config --global user.name "Juan Pérez"
$ git config --global user.email juanperez@ejemplo.com
```

Ahora aprenderás algunas de las opciones más interesantes que puedes establecer para personalizar tu uso de Git.

### Archivos de Configuración

Git utiliza una serie de archivos de configuración para determinar el comportamiento no predeterminado que puedes desear. El primer lugar donde Git busca estos valores es en el archivo de configuración del sistema `[ruta]/etc/gitconfig`, que contiene ajustes aplicados a todos los usuarios del sistema y todos sus repositorios. Si pasas la opción `--system` a `git config`, leerá y escribirá específicamente en este archivo.

El siguiente lugar que Git revisa es el archivo `~/.gitconfig` (o `~/.config/git/config`), que es específico para cada usuario. Puedes hacer que Git lea y escriba en este archivo pasando la opción `--global`.

Finalmente, Git busca los valores de configuración en el archivo de configuración dentro del directorio de Git (`.git/config`) del repositorio que estás utilizando actualmente. Estos valores son específicos de ese único repositorio, representando la opción `--local` en `git config`. Si no especificas qué nivel deseas trabajar, este es el predeterminado.

Cada uno de estos "niveles" (sistema, global, local) sobrescribe los valores del nivel anterior, por lo que los valores en `.git/config` anulan a los de `[ruta]/etc/gitconfig`, por ejemplo.

### Nota

Los archivos de configuración de Git son de texto plano, por lo que también puedes establecer estos valores editando manualmente el archivo e insertando la sintaxis correcta. Sin embargo, generalmente es más fácil ejecutar el comando `git config`.

### Configuración Básica del Cliente

Las opciones de configuración reconocidas por Git caen en dos categorías: del lado del cliente y del lado del servidor. La mayoría de las opciones son del lado del cliente, configurando tus preferencias de trabajo personales. Hay muchas opciones de configuración disponibles, pero una gran parte de ellas son útiles solo en ciertos casos especiales; aquí cubriremos solo las opciones más comunes y útiles. Si deseas ver una lista de todas las opciones que tu versión de Git reconoce, puedes ejecutar:

```bash
$ man git-config
```

Este comando enumera todas las opciones disponibles con bastante detalle. También puedes encontrar este material de referencia en [la documentación oficial](https://git-scm.com/docs/git-config).

### Conceptos Clave

1. **core.editor**: Por defecto, Git usa el editor de texto que hayas configurado mediante las variables de entorno `VISUAL` o `EDITOR`, o cae de nuevo en el editor `vi` para crear y editar tus mensajes de commit. Para cambiar ese valor predeterminado a otro, puedes usar la opción `core.editor`:

   ```bash
   $ git config --global core.editor emacs
   ```

   Ahora, independientemente de lo que esté configurado como tu editor predeterminado, Git abrirá Emacs para editar mensajes.

2. **commit.template**: Si estableces esto en la ruta de un archivo en tu sistema, Git usará ese archivo como el mensaje inicial predeterminado cuando hagas un commit. Esto es útil para recordarte (o a otros) el formato y estilo correcto al crear un mensaje de commit. Por ejemplo, considera un archivo de plantilla en `~/.gitmessage.txt` que se vea así:

   ```
   Línea de asunto (intenta mantenerla bajo 50 caracteres)

   Descripción de múltiples líneas del commit,
   siéntete libre de ser detallado.

   [Ticket: X]
   ```

   Para que Git lo use como mensaje predeterminado que aparece en tu editor cuando ejecutas `git commit`, establece el valor de configuración `commit.template`:

   ```bash
   $ git config --global commit.template ~/.gitmessage.txt
   $ git commit
   ```

3. **core.pager**: Esta configuración determina qué paginador se utiliza cuando Git muestra salidas como log y diff. Puedes configurarlo a `more` o a tu paginador favorito (por defecto, es `less`), o puedes desactivarlo estableciendo una cadena vacía:

   ```bash
   $ git config --global core.pager ''
   ```

4. **user.signingkey**: Si estás creando etiquetas firmadas (como se discute en Firmando tu Trabajo), establecer tu clave de firma GPG como un ajuste de configuración facilita las cosas. Configura tu ID de clave de esta manera:

   ```bash
   $ git config --global user.signingkey <gpg-key-id>
   ```

   Ahora puedes firmar etiquetas sin tener que especificar tu clave cada vez con el comando `git tag`.

5. **core.excludesfile**: A veces, deseas ignorar ciertos archivos para todos los repositorios en los que trabajas. Si tu computadora está ejecutando macOS, es probable que estés familiarizado con los archivos `.DS_Store`. Esta configuración te permite escribir una especie de archivo `.gitignore` global. Si creas un archivo `~/.gitignore_global` con estos contenidos:

   ```
   *~
   .*swp
   .DS_Store
   ```

   Y ejecutas:

   ```bash
   $ git config --global core.excludesfile ~/.gitignore_global
   ```

   Git no te molestará nunca más con esos archivos.

6. **help.autocorrect**: Si escribes incorrectamente un comando, Git intenta adivinar lo que quisiste decir. Si estableces `help.autocorrect` a `1`, Git realmente ejecutará el comando que parece que querías:

   ```bash
   $ git chekcout master
   ```

   Git mostrará un mensaje de advertencia y asumirá que querías decir `checkout` en 0.1 segundos automáticamente.

### Colores en Git

Git admite completamente la salida de terminal coloreada, lo que facilita mucho la lectura rápida de la salida de comandos. Varias opciones pueden ayudarte a configurar el color a tu preferencia.

1. **color.ui**: Git colorea automáticamente la mayor parte de su salida, pero hay un interruptor maestro si no te gusta este comportamiento. Para desactivar toda la salida de terminal coloreada de Git, haz esto:

   ```bash
   $ git config --global color.ui false
   ```

   La configuración predeterminada es `auto`, que colorea la salida cuando va directamente a una terminal, pero omite los códigos de control de color cuando la salida se redirige a un pipe o a un archivo.

2. **color.***: Si deseas ser más específico sobre qué comandos se colorean y cómo, Git proporciona configuraciones de color específicas para cada verbo. Cada una de estas se puede establecer en `true`, `false`, o `always`.

### Herramientas Externas de Merge y Diff

Aunque Git tiene una implementación interna de `diff`, puedes establecer una herramienta externa en su lugar. También puedes configurar una herramienta gráfica para la resolución de conflictos de merge en lugar de tener que resolver conflictos manualmente.

Para comenzar, descarga P4Merge de Perforce. Luego, establecerás scripts de envoltura externos para ejecutar tus comandos. A continuación, se muestra cómo configurar las herramientas de merge y diff:

```bash
$ git config --global merge.tool extMerge
$ git config --global mergetool.extMerge.cmd 'extMerge "$BASE" "$LOCAL" "$REMOTE" "$MERGED"'
$ git config --global mergetool.extMerge.trustExitCode false
$ git config --global diff.external extDiff
```

Después de todo esto, si ejecutas comandos de diff, en lugar de obtener la salida en la línea de comandos, Git abrirá P4Merge.

## Conclusión

La personalización de Git te permite ajustar su comportamiento para que se adapte a tus necesidades específicas. Al aplicar estas configuraciones, no solo mejoras tu flujo de trabajo, sino que también creas un entorno de desarrollo más agradable y eficiente.
```

### Explicación de las Analogías

- **Configuraciones**: Se presenta la idea de que cada archivo de configuración actúa como una "carta de presentación" que le dice a Git cómo comportarse.
- **Template de Commit**: Se compara con una hoja de estilo para un documento, ayudando a mantener la consistencia.
- **Paginadores y Colores**: Se utiliza la analogía de una biblioteca bien organizada que facilita encontrar información rápidamente.

---

# Git vs Working Directory – Aprende la diferencia

El **Directorio de Trabajo** y el **Directorio de Git** son repositorios (carpetas) para almacenar archivos, pero funcionan de maneras diferentes. Aquí están las principales distinciones entre ellos.

## Creador de un Git vs. Directorio de Trabajo

- **Directorio de Trabajo**: Es una carpeta que tú creas para almacenar todos los archivos de tu proyecto. Piensa en ella como tu **mesa de trabajo** donde organizas tus herramientas y materiales.
  
- **Directorio de Git**: Es una carpeta que Git crea dentro del directorio de trabajo que le indicaste que monitorice. Es como un **almacén oculto** donde Git guarda la información sobre los cambios que has realizado.

## Visibilidad

- **Directorio de Git**: Es una carpeta oculta. Imagina que es un **cuarto trasero** de tu oficina que no está a la vista, pero que contiene cosas importantes.
  
- **Directorio de Trabajo**: Es una carpeta normal. Es como el **escritorio** de tu oficina donde puedes ver todo lo que necesitas a simple vista.

## Uso de un Git vs. Directorio de Trabajo

- **Directorio de Git**: Registra las versiones de los archivos que autorizaste a Git a seguir. Es como un **libro de registro** que lleva cuenta de cada cambio importante.
  
- **Directorio de Trabajo**: Puede almacenar cualquier tipo de archivo. Puede contener archivos (o carpetas) que están bajo control de versiones y aquellos que no lo están. Es como un **almacén** donde guardas tanto cosas que están en uso como cosas que no.

## Ubicación

- Puedes crear un **Directorio de Trabajo** en cualquier parte de tu sistema. Es como decidir dónde quieres montar tu oficina.
  
- Git crea el **Directorio de Git** dentro de un repositorio de trabajo. Así que, si tu oficina es el directorio de trabajo, el directorio de Git es como el **sótano** de esa oficina.

## Contenido de un Git vs. Directorio de Trabajo

- **Directorio de Trabajo**: Contiene archivos tanto **seguros** como **no seguros**. Es como una **cajonera** que tiene cosas organizadas y otras que no, pero todas están ahí.
  
- **Directorio de Git**: Contiene solo archivos **seguros**. Es como una **caja fuerte** donde solo se guardan documentos importantes.

---

# Introducción - ¿Qué es Git?

## ¿Qué es Git?

Entonces, ¿qué es Git en pocas palabras? Esta es una sección importante para comprender, porque si entiendes qué es Git y los fundamentos de cómo funciona, usar Git de manera efectiva será mucho más fácil para ti. A medida que aprendas Git, trata de despejar tu mente de las cosas que puedes saber sobre otros Sistemas de Control de Versiones (VCS), como CVS, Subversion o Perforce; hacerlo te ayudará a evitar confusiones sutiles al usar la herramienta. Aunque la interfaz de usuario de Git es bastante similar a la de estos otros VCS, Git almacena y piensa sobre la información de una manera muy diferente, y entender estas diferencias te ayudará a evitar confusiones mientras lo usas.

## Instantáneas, no diferencias

La principal diferencia entre Git y cualquier otro VCS (incluyendo Subversion y similares) es la forma en que Git piensa sobre sus datos. Conceptualmente, la mayoría de otros sistemas almacenan información como una lista de cambios basados en archivos. Estos sistemas (CVS, Subversion, Perforce, etc.) piensan en la información que almacenan como un conjunto de archivos y los cambios realizados en cada archivo a lo largo del tiempo (esto se describe comúnmente como control de versiones basado en **deltas**).

**Almacenando datos como cambios a una versión base de cada archivo**  
Imagina que cada vez que editas un documento, solo se guarda la **diferencia** entre el documento anterior y el nuevo. Esto es lo que hacen otros VCS.

Pero Git no piensa ni almacena sus datos de esta manera. En cambio, Git piensa en sus datos más como una serie de **instantáneas** de un sistema de archivos en miniatura. Con Git, cada vez que confirmas (commit) o guardas el estado de tu proyecto, Git básicamente toma una **foto** de cómo lucen todos tus archivos en ese momento y almacena una referencia a esa instantánea. Para ser eficiente, si los archivos no han cambiado, Git no almacena el archivo nuevamente, solo un enlace al archivo idéntico que ya ha almacenado. Git piensa sobre sus datos más como un **flujo de instantáneas**.

**Git almacena datos como instantáneas del proyecto a lo largo del tiempo**  
Esta es una distinción importante entre Git y casi todos los otros VCS. Esto hace que Git replantee casi todos los aspectos del control de versiones que la mayoría de otros sistemas copiaron de la generación anterior. Esto hace que Git se asemeje más a un **mini sistema de archivos** con algunas herramientas increíblemente potentes construidas sobre él, en lugar de simplemente ser un VCS.

## Casi cada operación es local

La mayoría de las operaciones en Git solo necesitan archivos y recursos locales para operar; generalmente, no se necesita información de otra computadora en tu red. Si estás acostumbrado a un **CVCS** donde la mayoría de las operaciones tienen esa latencia de red, este aspecto de Git te hará sentir que los dioses de la velocidad han bendecido a Git con poderes sobrenaturales. Debido a que tienes toda la historia del proyecto justo ahí en tu disco local, la mayoría de las operaciones parecen casi instantáneas.

Por ejemplo, para navegar por la historia del proyecto, Git no necesita ir al servidor para obtener la historia y mostrarla para ti; simplemente la lee directamente de tu base de datos local. Esto significa que ves la historia del proyecto casi al instante. Si quieres ver los cambios introducidos entre la versión actual de un archivo y el archivo de hace un mes, Git puede buscar el archivo de hace un mes y hacer un cálculo de diferencia localmente, en lugar de tener que pedirle a un servidor remoto que lo haga o descargar una versión anterior del archivo del servidor remoto para hacerlo localmente.

Esto también significa que hay muy poco que no puedas hacer si estás fuera de línea o fuera de la VPN. Si subes a un avión o a un tren y quieres hacer un poco de trabajo, puedes confirmar felizmente (en tu copia local, recuerda) hasta que llegues a una conexión de red para subir tus cambios. Si llegas a casa y no puedes hacer que tu cliente de VPN funcione correctamente, aún puedes trabajar. En muchos otros sistemas, hacer esto es casi imposible o doloroso. Por ejemplo, en Perforce, no puedes hacer mucho cuando no estás conectado al servidor; en Subversion y CVS, puedes editar archivos, pero no puedes confirmar cambios en tu base de datos (porque tu base de datos está fuera de línea). Esto puede no parecer un gran problema, pero te sorprendería la gran diferencia que puede hacer.

## Git tiene integridad

Todo en Git se verifica antes de ser almacenado y luego se hace referencia a ese checksum. Esto significa que es imposible cambiar el contenido de cualquier archivo o directorio sin que Git lo sepa. Esta funcionalidad está integrada en Git en los niveles más bajos y es integral a su filosofía. No puedes perder información en tránsito o sufrir corrupción de archivos sin que Git pueda detectarlo.

El mecanismo que Git utiliza para esta verificación se llama un **hash SHA-1**. Este es un string de 40 caracteres compuesto por caracteres hexadecimales (0–9 y a–f) y se calcula en base al contenido de un archivo o estructura de directorios en Git. Un hash SHA-1 se ve algo así:

```
24b9da6552252987aa493b52f8696cd6d3b00373
```

Verás estos valores hash por todas partes en Git porque se usan mucho. De hecho, Git almacena todo en su base de datos no por el nombre del archivo, sino por el valor hash de su contenido.

## Git generalmente solo agrega datos

Cuando realizas acciones en Git, casi todas solo agregan datos a la base de datos de Git. Es difícil hacer que el sistema haga algo que no sea reversible o que borre datos de alguna manera. Al igual que con cualquier VCS, puedes perder o estropear cambios que no has confirmado aún, pero después de confirmar una instantánea en Git, es muy difícil perderla, especialmente si empujas regularmente tu base de datos a otro repositorio.

Esto hace que usar Git sea un placer porque sabemos que podemos experimentar sin el peligro de arruinar las cosas severamente. Para una mirada más profunda sobre cómo Git almacena sus datos y cómo puedes recuperar datos que parecen perdidos, consulta "Deshaciendo Cosas".

## Los tres estados

Presta atención ahora: aquí está lo principal que debes recordar sobre Git si quieres que el resto de tu proceso de aprendizaje fluya sin problemas. Git tiene tres estados principales en los que pueden residir tus archivos: **modificado**, **preparado** y **confirmado**:

- **Modificado**: Significa que has cambiado el archivo, pero no lo has confirmado en tu base de datos aún.
  
- **Preparado**: Significa que has marcado un archivo modificado en su versión actual para que vaya a tu próxima instantánea de confirmación.
  
- **Confirmado**: Significa que los datos están guardados de forma segura en tu base de datos local.

Esto nos lleva

 a los conceptos de **staging area** (área de preparación) y **commit** (confirmar). La staging area es donde colocas tus archivos antes de confirmar los cambios.

```plaintext
+-----------------+    +------------------+
|    Modificado   | -> |     Preparado    |
|                 |    |                  |
+-----------------+    +------------------+
                           |
                           |
+-------------------------+-----------------------+
|                       Confirmado                  |
| (Datos almacenados de manera segura en la base de  |
|             datos local de Git)                   |
+---------------------------------------------------+
```

## Conclusión

Con estas bases sobre lo que es Git, estarás mejor preparado para entender los comandos y flujos de trabajo que usarás más adelante. Recuerda que Git es una herramienta poderosa que te permitirá gestionar tu código de manera eficiente y efectiva.

---

# Git Commit

## ¿Qué es un Git Commit?

El comando `git commit` crea un commit, que es como una instantánea de tu repositorio. Imagina que tu repositorio es un álbum de fotos y cada commit es una foto que captura un momento específico en el tiempo. Estos commits son instantáneas de tu repositorio en momentos concretos. Deberías hacer nuevos commits con frecuencia, basados en unidades lógicas de cambio. Con el tiempo, los commits deberían contar la historia de la evolución de tu repositorio y cómo llegó a ser lo que es actualmente. Los commits incluyen muchos metadatos además del contenido y el mensaje, como el autor, la marca de tiempo y más.

## Cómo Funciona Git Commit

Los commits son los bloques de construcción de "puntos de guardado" dentro del control de versiones de Git. Utilizar `git commit` te permite moldear la historia de tu proyecto de manera intencionada y segura. Puedes hacer commits en diferentes ramas y especificar exactamente qué cambios deseas incluir. Los commits se crean en la rama que tienes actualmente seleccionada (donde está apuntando HEAD), por lo que siempre es una buena idea ejecutar `git status` antes de hacer un commit para asegurarte de que estás en la rama correcta. Antes de hacer un commit, necesitarás preparar los cambios que deseas incluir en el commit utilizando `git add [archivo]`.

Los commits son hashes SHA ligeros, objetos dentro de Git. Siempre que trabajes con archivos de texto, no necesitarás preocuparte por cuántos archivos tienes, cuán grandes son o cuántos commits realizas. ¡Git puede manejarlo!

## Haciendo Commits en Dos Fases

Los commits tienen dos fases que te ayudan a crear commits correctamente. Los commits deberían ser unidades lógicas y atómicas de cambio que representan una idea específica. Pero, no todos trabajamos de la misma manera. Puede que te entusiasmes y termines resolviendo dos o tres problemas antes de acordarte de hacer un commit. ¡Está bien! Git puede manejar eso. Una vez que estés listo para crear tus commits, usarás `git add <NOMBRE_ARCHIVO>` para especificar los archivos que deseas "preparar" para el commit. Sin añadir archivos, el comando `git commit` no funcionará. Git solo revisa el área de preparación para saber qué incluir en el commit. Preparar o agregar archivos es posible a través de la línea de comandos y también con la mayoría de las interfaces de Git como GitHub Desktop, seleccionando las líneas o archivos que deseas preparar.

También puedes utilizar un comando útil, `git add -p`, para revisar los cambios y separarlos, incluso si están en el mismo archivo.

## Cómo Usar Git Commit

### Usos y Opciones Comunes para Git Commit

- `git commit`: Este comando inicia el proceso de commit, pero como no incluye una opción -m para el mensaje, se abrirá tu editor de texto predeterminado para que crees el mensaje del commit. Si no has configurado nada, hay una buena posibilidad de que esto sea VI o Vim. (Para salir, presiona Esc, luego :wq y luego Enter.)
  
- `git commit -m "mensaje descriptivo del commit"`: Este comando inicia el proceso de commit y permite incluir el mensaje del commit al mismo tiempo.
  
- `git commit -am "mensaje descriptivo del commit"`: Además de incluir el mensaje del commit, esta opción te permite omitir la fase de preparación. La adición de -a automáticamente preparará cualquier archivo que ya esté siendo rastreado por Git (cambios en archivos que ya has confirmado antes).

- `git commit --amend`: Reemplaza el commit más reciente con un nuevo commit. (¡Más sobre esto más adelante!)

Para ver todas las opciones posibles que tienes con `git commit`, consulta la documentación de Git.

## Cómo Deshacer Commits en Git

A veces, es posible que necesites cambiar la historia. Tal vez necesites deshacer un commit. Si te encuentras en esta situación, hay algunas cosas muy importantes que recordar:

- Si estás "deshaciendo" un commit que existe en el remoto, podrías crear grandes problemas para tus colaboradores.
- Deshacer un commit en trabajo que solo tienes localmente es mucho más seguro.

### ¿Qué puede salir mal al cambiar la historia?

Cambiar la historia para los colaboradores puede ser problemático de varias maneras. Imagina: tú y otro colaborador tienen el mismo repositorio, con la misma historia. Pero, ellos hacen un cambio que elimina el commit más reciente. Ellos continúan haciendo nuevos commits a partir del commit anterior. Mientras tanto, tú sigues trabajando con el commit que el colaborador intentó eliminar. Cuando ellos hagan push, tendrán que 'forzar el push', lo que debería mostrarles que están cambiando la historia. ¿Qué crees que sucederá cuando tú intentes hacer push?

En casos dramáticos, Git puede decidir que las historias son demasiado diferentes y los proyectos ya no están relacionados. Esto es poco común, pero un gran problema.

El resultado más común es que tu `git push` devolvería el commit "eliminado" a la historia compartida. (Primero, tendrías que hacer `git pull` si estabas trabajando en la misma rama y luego fusionar, pero los resultados serían los mismos.) Esto significa que lo que era tan importante eliminar ahora está de vuelta en el repositorio. Un password, token o archivo binario grande puede volver sin que nunca te avise.

## git revert

`git revert` es la forma más segura de cambiar la historia con Git. En lugar de eliminar commits existentes, `git revert` revisa los cambios introducidos en un commit específico y luego aplica la inversa de esos cambios en un nuevo commit. Funciona como un comando de "deshacer commit", sin sacrificar la integridad de la historia de tu repositorio. `git revert` siempre es la forma recomendada de cambiar la historia cuando sea posible.

## git reset

A veces, un commit incluye información sensible que realmente necesita ser eliminada. `git reset` es un comando muy poderoso que puede hacer que pierdas trabajo. Al restablecer, mueves el puntero HEAD y el puntero de rama a otro punto en el tiempo, haciendo que parezca que los commits intermedios nunca sucedieron. Antes de usar `git reset`:

- Asegúrate de hablar con tu equipo sobre cualquier commit compartido.
- Investiga los tres tipos de reset para ver cuál es el adecuado para ti (`--soft`, `--mixed`, `--hard`).
- Confirma cualquier trabajo que no quieras perder intencionalmente: el trabajo que está confirmado puede recuperarse, pero el trabajo no confirmado no puede.

## git reflog

Si estás cambiando la historia y deshaciendo commits, deberías conocer `git reflog`. Si te metes en problemas, el reflog podría sacarte de apuros. El reflog es un registro de cada commit al que HEAD ha apuntado. Por ejemplo, si usas `git reset` y pierdes commits accidentalmente, puedes encontrarlos y acceder a ellos con `git reflog`.

## Actualizando Commits Con Git Commit Amend

Si bien `git commit --amend` cambia la historia, solo modifica el commit más reciente en tu rama actual. Este puede ser un comando extremadamente útil para commits que:

- No han sido enviados al remoto todavía.
- Tienen un error tipográfico en el mensaje del commit.
- No contienen los cambios que te gustaría que contuvieran.

### Ejemplos de Git Commit

Una vez que hayas preparado los archivos que deseas incluir en tu commit, estás listo. Ya sea que confirmes en una herramienta como GitHub Desktop, o a través de tu línea de comandos, el mensaje del commit es importante. Los mensajes de commit deben ser breves y descriptivos sobre tu cambio. Si estás revisando la historia de tu repositorio, te guiarán los mensajes de commit, así que deben contar una historia. Los commits en la línea de comandos pueden incluir el mensaje con el siguiente formato:

```bash
git commit -m "ejemplo de mensaje de commit"
```

Los mensajes de commit deberían estar en presente y ser directivos, como los siguientes ejemplos:

```bash
git commit -m "crear estructura de archivos para guías de Git"
git commit -m "traducir la hoja de trucos de Git al alemán"
git commit -m "actualizar URL rota a recursos de Git"
```

Si deseas incluir más contexto en tus mensajes de commit, también puedes agregar un mensaje de commit extendido.

### Comandos Relacionados

- `git add [archivo]`: Prepara el archivo para la versión, añadiéndolo al área de preparación.
- `git status`: Siempre es buena idea. Este comando te muestra en qué rama estás, qué archivos están en el directorio de trabajo o de preparación, y cualquier otra información importante.
- `git push`: Sube todos los commits de rama local al remoto.
- `git log`: Navega e inspecciona la evolución de los archivos del proyecto.

---

# gitignore - Especifica archivos intencionadamente no rastreados que se deben ignorar

## SINOPSIS

`$XDG_CONFIG_HOME/git/ignore`, `$GIT_DIR/info/exclude`, `.gitignore`

## DESCRIPCIÓN

Un archivo `.gitignore` especifica archivos intencionadamente no rastreados que Git debería ignorar. Los archivos ya rastreados por Git no se ven afectados; consulta las NOTAS a continuación para más detalles.

Cada línea en un archivo `.gitignore` especifica un patrón. Al decidir si ignor

ar un archivo, Git se compara con cada patrón en orden hasta que uno de ellos coincida.

Puedes utilizar comentarios en los archivos `.gitignore` para mantener la claridad. Estos comienzan con un `#` y continúan hasta el final de la línea.

## MUESTRA DEL ARCHIVO .gitignore

```gitignore
# archivos de construcción
/build/
/dist/

# archivos de salida de IDE
*.log
*.class

# archivos de copia
*.swp

# ignorar un archivo específico
config/database.yml

# ignorar todos los archivos en un directorio
temp/*
```

## CREANDO UN ARCHIVO .gitignore

Para crear un archivo `.gitignore`, simplemente crea un archivo de texto en la raíz de tu repositorio y nómbralo `.gitignore`. Puedes abrirlo con cualquier editor de texto y comenzar a añadir los patrones que deseas ignorar.

## NOTAS

Los archivos que ya están siendo rastreados por Git no se verán afectados por las reglas en `.gitignore`. Para dejar de rastrear un archivo que ya está en el repositorio, primero debes eliminarlo con `git rm --cached [archivo]` y luego añadir el archivo a tu `.gitignore`.

### Ignorando directorios

Para ignorar un directorio entero, simplemente coloca una barra al final del nombre del directorio:

```gitignore
# Ignorar directorio
logs/
```

### Ignorando archivos por extensión

Puedes ignorar todos los archivos de un tipo específico utilizando el carácter comodín `*`. Por ejemplo, para ignorar todos los archivos `.log`, usarías:

```gitignore
# Ignorar archivos de log
*.log
```

---

## Conclusión

Aprender sobre `git commit` y cómo utilizarlo correctamente es esencial para cualquier desarrollador. Asegúrate de realizar commits significativos y de utilizar el archivo `.gitignore` para mantener tu repositorio limpio y organizado. Recuerda siempre comunicarte con tu equipo cuando necesites cambiar la historia de tu repositorio y utilizar `git revert` o `git reflog` cuando sea necesario.

---

Aquí tienes un archivo Markdown que explica cómo ver el historial de commits en Git, utilizando analogías sencillas y agregando conceptos técnicos para una mejor comprensión. 

```markdown
# Git Basics - Visualizando el Historial de Commits

## Visualizando el Historial de Commits

Imagina que tienes un diario donde escribes tus pensamientos y experiencias cada día. A medida que pasan los días, tus entradas se acumulan y, en algún momento, querrás mirar hacia atrás y ver lo que has escrito. En Git, el historial de commits funciona de manera similar. Cada vez que haces un commit, estás escribiendo una nueva entrada en tu "diario de código".

### Comando `git log`

El comando más básico y poderoso para ver el historial de commits es `git log`. Cuando has creado varios commits o has clonado un repositorio con un historial existente, este comando te permitirá revisar qué ha pasado.

Para clonar un proyecto simple llamado “simplegit”, puedes ejecutar el siguiente comando:

```bash
$ git clone https://github.com/schacon/simplegit-progit
```

Una vez clonado el proyecto, al ejecutar `git log`, deberías obtener una salida similar a esta:

```bash
$ git log
commit ca82a6dff817ec66f44342007202690a93763949
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Mon Mar 17 21:52:11 2008 -0700

    Cambiar el número de versión

commit 085bb3bcb608e1e8451d4b2432f8ecbe6306e7e7
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sat Mar 15 16:40:33 2008 -0700

    Eliminar prueba innecesaria

commit a11bef06a3f659402fe7563abf99ad00de2209e6
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sat Mar 15 10:31:28 2008 -0700

    Commit inicial
```

#### Desglose de la Salida

Al ejecutar `git log`, obtienes información sobre cada commit:

- **SHA-1**: Es como una huella dactilar única para cada entrada en tu diario.
- **Autor**: Quién hizo el commit.
- **Fecha**: Cuándo se realizó el commit.
- **Mensaje**: Una breve descripción de lo que se cambió.

Por defecto, `git log` lista los commits en orden cronológico inverso; es decir, los commits más recientes aparecen primero.

### Opciones Útiles para `git log`

Hay una gran cantidad de opciones disponibles para personalizar la salida de `git log`. Aquí hay algunas de las más útiles:

- **Mostrar diferencias**: La opción `-p` o `--patch` muestra las diferencias (cambios) introducidas en cada commit.
  
  ```bash
  $ git log -p -2
  ```

- **Estadísticas**: Usando `--stat`, puedes ver estadísticas de los archivos modificados en cada commit.

  ```bash
  $ git log --stat
  ```

- **Formato personalizado**: Con `--pretty`, puedes cambiar la salida a un formato que prefieras. Por ejemplo, `--pretty=oneline` muestra cada commit en una sola línea.

  ```bash
  $ git log --pretty=oneline
  ```

### Usando `git log` con Gráficos

Para ver la historia de tu proyecto de una manera más visual, puedes agregar la opción `--graph`, que muestra un gráfico ASCII de la historia de ramas y merges:

```bash
$ git log --pretty=format:"%h %s" --graph
```

Este tipo de salida es especialmente útil a medida que trabajas con ramas y merges en Git.

### Filtrando la Salida del Log

Además de las opciones de formato, `git log` también tiene opciones para limitar la salida. Por ejemplo, si solo deseas ver los últimos dos commits, puedes usar:

```bash
$ git log -2
```

Además, puedes filtrar los commits por autor o buscar palabras clave en los mensajes de commit utilizando las opciones `--author` y `--grep`.

```bash
$ git log --author="Scott Chacon"
$ git log --grep="Cambiar"
```

### Conclusión

Al igual que revisar las entradas de tu diario, `git log` te permite mirar hacia atrás en el historial de tu proyecto y entender cómo ha evolucionado con el tiempo. Las diferentes opciones que ofrece te ayudarán a personalizar la forma en que ves y entiendes el progreso de tu código.

Utiliza estos comandos y opciones para explorar tu historial de commits y así obtener un mejor control sobre tus proyectos en Git. ¡Feliz codificación!