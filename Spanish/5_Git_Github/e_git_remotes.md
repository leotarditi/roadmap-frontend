# Guía sobre Repositorios Remotos

En esta guía, aprenderás sobre los repositorios remotos en GitHub, su importancia en el desarrollo colaborativo y cómo trabajar con ellos.

## Acerca de los Repositorios Remotos
El enfoque colaborativo de GitHub para el desarrollo depende de publicar commits desde tu repositorio local a GitHub para que otras personas puedan ver, obtener y actualizar tu código.

### ¿Qué es un URL remoto?
Un URL remoto es una forma elegante de Git de referirse a "el lugar donde se almacena tu código". Este URL podría ser tu repositorio en GitHub, el fork de otro usuario o incluso un servidor completamente diferente.

**Analogía**: Imagina que tu código es como una carta. El URL remoto es la dirección a la que envías esa carta. Solo puedes enviar tu carta (hacer push) a dos tipos de direcciones:

- Un URL HTTPS, como `https://github.com/user/repo.git`
- Un URL SSH, como `git@github.com:user/repo.git`

Git asocia un URL remoto con un nombre, y tu remoto predeterminado suele llamarse `origin`.

## Creando Repositorios Remotos
Puedes usar el comando `git remote add` para asociar un URL remoto con un nombre. Por ejemplo, escribirías lo siguiente en la línea de comandos:

```bash
git remote add origin <REMOTE_URL>
```

Esto asocia el nombre `origin` con el `REMOTE_URL`.

**Analogía**: Esto es como ponerle una etiqueta a una caja de almacenamiento. Al etiquetar la caja, puedes identificar rápidamente lo que hay dentro.

Puedes usar el comando `git remote set-url` para cambiar el URL de un remoto.

## Elegir un URL para tu Repositorio Remoto
Hay varias formas de clonar repositorios disponibles en GitHub.

Cuando ves un repositorio mientras estás conectado a tu cuenta, los URLs que puedes usar para clonar el proyecto en tu computadora están disponibles debajo de los detalles del repositorio.

Para obtener más información sobre cómo establecer o cambiar tu URL remoto, consulta "Gestionando repositorios remotos".

## Clonando con URLs HTTPS
Los URLs de clonación `https://` están disponibles en todos los repositorios, independientemente de su visibilidad. Los URLs `https://` funcionan incluso si estás detrás de un firewall o proxy.

Cuando ejecutas `git clone`, `git fetch`, `git pull` o `git push` a un repositorio remoto usando URLs `HTTPS` en la línea de comandos, Git te pedirá tu nombre de usuario y contraseña de GitHub. Cuando Git te pida tu contraseña, introduce tu token de acceso personal. Alternativamente, puedes usar un helper de credenciales como el Git Credential Manager. La autenticación basada en contraseña para Git ha sido eliminada en favor de métodos de autenticación más seguros.

**Analogía**: Clonar usando HTTPS es como usar una tarjeta de crédito para comprar algo en línea. Proporcionas tus credenciales para confirmar tu identidad y proceder con la acción.

Consejos:
- Puedes usar un helper de credenciales para que Git recuerde tus credenciales de GitHub cada vez que interactúe con GitHub.
- Para clonar un repositorio sin autenticarte en GitHub en la línea de comandos, puedes usar GitHub Desktop para clonar en su lugar.

## Clonando con URLs SSH
Los URLs SSH proporcionan acceso a un repositorio Git a través de SSH, un protocolo seguro. Para usar estos URLs, debes generar un par de claves SSH en tu computadora y agregar la clave pública a tu cuenta en GitHub.

Cuando ejecutas `git clone`, `git fetch`, `git pull` o `git push` a un repositorio remoto usando URLs SSH, se te pedirá una contraseña y deberás proporcionar la frase de paso de tu clave SSH.

**Analogía**: Usar SSH es como tener una llave única para tu casa. Solo quienes tienen esa llave pueden entrar y acceder a tu código.

Consejo: Puedes usar un URL SSH para clonar un repositorio en tu computadora o como una forma segura de desplegar tu código en servidores de producción.

## Clonando con GitHub CLI
También puedes instalar GitHub CLI para usar flujos de trabajo de GitHub en tu terminal. Para más información, consulta "Acerca de GitHub CLI".

**Analogía**: Usar GitHub CLI es como tener un asistente personal que te ayuda a administrar tu trabajo en GitHub sin necesidad de abrir el navegador.

---

# Guía para Git: Comando git fetch

En esta guía, aprenderás sobre el comando `git fetch`, su importancia en el trabajo colaborativo con Git, y cómo usarlo de manera efectiva.

## ¿Qué es el comando git fetch?
El comando `git fetch` descarga commits, archivos y referencias desde un repositorio remoto a tu repositorio local. Este comando es lo que haces cuando quieres ver en qué han estado trabajando los demás. Es similar al `svn update` en que te permite ver cómo ha progresado el historial central, pero no te obliga a fusionar los cambios en tu repositorio. 

**Analogía**: Imagina que estás en una biblioteca y quieres ver los nuevos libros que han llegado. Haces un recorrido (fetch) por las estanterías para ver qué hay de nuevo, pero no decides llevarte ningún libro todavía. 

El contenido descargado se aísla del contenido local existente, lo que significa que no afecta en absoluto tu trabajo de desarrollo local. Para integrar el contenido descargado, debes usar el comando `git checkout`. Esto hace que `git fetch` sea una forma segura de revisar commits antes de integrarlos con tu repositorio local.

## Cómo funciona git fetch con ramas remotas
Para entender mejor cómo funciona `git fetch`, veamos cómo Git organiza y almacena los commits. En el directorio `./.git/objects` del repositorio, Git almacena todos los commits, tanto locales como remotos. Git mantiene los commits de las ramas remotas y locales separados a través del uso de referencias de ramas.

**Analogía**: Piensa en tu repositorio como un gran archivo con carpetas (ramas). Cada carpeta contiene documentos (commits). Las carpetas de tus documentos son diferentes a las carpetas que pertenecen a otros.

Las referencias para las ramas locales se almacenan en `./.git/refs/heads/`. Al ejecutar el comando `git branch`, obtendrás una lista de las referencias de las ramas locales:

```bash
git branch
```

El resultado podría ser:

```
main
feature1
debug2
```

Las ramas remotas tienen una estructura similar, pero se prefijan con el nombre del remoto al que pertenecen, para que no las confundas con las locales. Las referencias de las ramas remotas se encuentran en `./.git/refs/remotes/`. Por ejemplo:

```bash
git branch -r
```

Podrías ver algo como:

```
# origin/main
# origin/feature1
# origin/debug2
# remote-repo/main
# remote-repo/other-feature
```

Este resultado muestra las ramas locales que examinamos anteriormente, pero ahora están prefijadas con `origin/`, además de las ramas remotas con el prefijo `remote-repo`. Puedes revisar una rama remota como lo harías con una local, pero esto te coloca en un estado de `HEAD` separado (similar a revisar un antiguo commit). Puedes pensar en ellas como ramas de solo lectura.

## Comandos y opciones de git fetch
Aquí tienes algunas variantes del comando `git fetch`:

- **Para obtener todas las ramas desde un repositorio**:

    ```bash
    git fetch <remote>
    ```

- **Para obtener solo una rama específica**:

    ```bash
    git fetch <remote> <branch>
    ```

- **Para obtener todas las ramas de todos los remotos**:

    ```bash
    git fetch --all
    ```

- **Para hacer una simulación de lo que haría el comando sin aplicarlo**:

    ```bash
    git fetch --dry-run
    ```

## Ejemplo de uso de git fetch
Imagina que tienes un repositorio central llamado `origin` del que clonaste tu repositorio local. Ahora supongamos que hay un repositorio remoto adicional llamado `coworkers_repo` que contiene una rama llamada `feature_branch`. 

Primero, necesitas configurar el repositorio remoto usando el comando `git remote`:

```bash
git remote add coworkers_repo git@bitbucket.org:coworker/coworkers_repo.git
```

Aquí hemos creado una referencia al repositorio de tu compañero usando la URL del repositorio. Ahora, pasamos el nombre remoto a `git fetch` para descargar el contenido:

```bash
git fetch coworkers_repo coworkers/feature_branch
```

Ahora tienes en tu repositorio local el contenido de `coworkers/feature_branch`. Para integrar esto en tu copia de trabajo local, usamos el comando `git checkout`:

```bash
git checkout coworkers/feature_branch
```

Nota: estás en un estado de `HEAD` separado. Esto significa que puedes explorar, hacer cambios experimentales y confirmar (commit) sin afectar a las ramas existentes. Si deseas crear una nueva rama para retener los commits que realices, puedes hacerlo usando `-b` con el comando checkout:

```bash
git checkout -b <new-branch-name>
```

## Sincronizando origin con git fetch
Ahora veamos un flujo de trabajo típico para sincronizar tu repositorio local con la rama principal del repositorio central:

```bash
git fetch origin
```

Esto mostrará las ramas que se han descargado:

```
a1e8fb5..45e66a4 main -> origin/main
a1e8fb5..9e8ab1c develop -> origin/develop
* [new branch] some-feature -> origin/some-feature
```

Para ver qué commits se han agregado a la rama principal en el remoto, puedes ejecutar:

```bash
git log --oneline main..origin/main
```

Para aprobar los cambios y fusionarlos en tu rama principal local, usa los siguientes comandos:

```bash
git checkout main
git log origin/main
git merge origin/main
```

Las ramas `origin/main` y `main` ahora apuntan al mismo commit, y estás sincronizado con los desarrollos en el remoto.

## Resumen de git fetch
En resumen, `git fetch` es un comando principal utilizado para descargar contenido desde un repositorio remoto. Se usa junto con `git remote`, `git branch`, `git checkout`, y `git reset` para actualizar un repositorio local al estado de un remoto. Es una herramienta crítica en los flujos de trabajo colaborativos con Git. A diferencia de `git pull`, `git fetch` puede considerarse una versión más segura y no destructiva.

---

# Haciendo Push de Commits a un Repositorio Remoto

Usa `git push` para enviar commits realizados en tu rama local a un repositorio remoto.

## En este artículo

- Acerca de `git push`
- Renombrando ramas
- Tratando con errores de "non-fast-forward"
- Haciendo push de etiquetas
- Eliminando una rama o etiqueta remota
- Remotos y forks
- Lectura adicional

## Acerca de `git push`

El comando `git push` toma dos argumentos:

- Un nombre de remoto, por ejemplo, `origin`.
- Un nombre de rama, por ejemplo, `main`.

Por ejemplo:

```bash
git push NOMBRE-DEL-REMOTO NOMBRE-DE-LA-RAMA
```

### Analogía

Imagina que tienes un cuaderno de notas (tu repositorio local) y quieres compartir tus apuntes con un grupo de estudio (el repositorio remoto). Al usar `git push origin main`, estás enviando tus apuntes de la página principal de tu cuaderno al grupo. 

## Renombrando ramas

Para renombrar una rama, usarías el mismo comando `git push`, pero añadirías un argumento más: el nombre de la nueva rama. Por ejemplo:

```bash
git push NOMBRE-DEL-REMOTO NOMBRE-DE-LA-RAMA-LOCAL:NOMBRE-DE-LA-RAMA-REMOTA
```

Esto envía la `NOMBRE-DE-LA-RAMA-LOCAL` a tu `NOMBRE-DEL-REMOTO`, pero se renombra a `NOMBRE-DE-LA-RAMA-REMOTA`.

### Analogía

Si decides que el nombre de tu página en el cuaderno no es el adecuado, puedes cambiarlo. Con `git push origin mi-rama:mi-nueva-rama`, estás diciendo: "Envía mis apuntes de 'mi-rama' pero renómbrala a 'mi-nueva-rama' en el grupo".

## Tratando con errores de "non-fast-forward"

Si tu copia local de un repositorio está desactualizada o "detrás" del repositorio remoto al que estás haciendo push, recibirás un mensaje indicando que las actualizaciones "non-fast-forward" fueron rechazadas. Esto significa que debes recuperar, o "fetch", los cambios del remoto antes de poder enviar tus cambios locales.

### Analogía

Piensa en esto como si intentaras enviar un documento a un amigo que ya ha actualizado el archivo con nueva información. Debes primero revisar qué cambios ha hecho tu amigo antes de enviar tu versión.

Para más información sobre este error, consulta "Tratando con errores de non-fast-forward".

## Haciendo push de etiquetas

Por defecto, y sin parámetros adicionales, `git push` envía todas las ramas que coinciden con los nombres de las ramas remotas.

Para hacer push de una sola etiqueta, puedes usar el mismo comando que usarías para hacer push de una rama:

```bash
git push NOMBRE-DEL-REMOTO NOMBRE-DE-LA-ETIQUETA
```

Para hacer push de todas tus etiquetas, puedes escribir el comando:

```bash
git push NOMBRE-DEL-REMOTO --tags
```

### Analogía

Enviar etiquetas es como poner una etiqueta en un paquete antes de enviarlo. Puedes etiquetar un solo paquete o enviar todos los paquetes etiquetados al mismo tiempo.

## Eliminando una rama o etiqueta remota

La sintaxis para eliminar una rama es un poco arcana al principio:

```bash
git push NOMBRE-DEL-REMOTO :NOMBRE-DE-LA-RAMA
```

Nota que hay un espacio antes de los dos puntos. El comando se asemeja a los mismos pasos que seguirías para renombrar una rama. Sin embargo, aquí le estás diciendo a Git que no envíe nada a `NOMBRE-DE-LA-RAMA` en `NOMBRE-DEL-REMOTO`. Por ello, `git push` elimina la rama en el repositorio remoto.

### Analogía

Eliminar una rama es como quitar un libro de la estantería de tu grupo de estudio. Simplemente le dices al grupo que ya no necesitas ese libro, y lo retiras.

## Remotos y forks

Es posible que ya sepas que puedes "forkear" repositorios en GitHub.

Cuando clonas un repositorio que posees, le proporcionas una URL remota que le dice a Git dónde buscar y enviar actualizaciones. Si deseas colaborar con el repositorio original, deberías agregar una nueva URL remota, típicamente llamada `upstream`, a tu clon local de Git:

```bash
git remote add upstream URL_DEL_REMOTO
```

Ahora puedes obtener actualizaciones y ramas de su fork:

```bash
git fetch upstream
```

### Analogía

Imagina que has copiado un libro de texto (tu repositorio local) y deseas consultar al autor del libro original (el repositorio remoto) para obtener las últimas ediciones. Al agregar `upstream`, le estás diciendo a tu libro que verifique las actualizaciones del autor.

Cuando termines de hacer cambios locales, puedes enviar tu rama local a GitHub e iniciar una solicitud de extracción.

---

# Gestión de Repositorios Remotos

En este documento, aprenderás a trabajar con tus repositorios locales en tu computadora y con los repositorios remotos alojados en GitHub.

## Navegación en la Plataforma
- Mac
- Windows
- Linux

## En este artículo
- Agregar un repositorio remoto
- Cambiar la URL de un repositorio remoto
- Renombrar un repositorio remoto
- Eliminar un repositorio remoto
- Lectura adicional

## Agregar un Repositorio Remoto

Para agregar un nuevo remoto, usa el comando `git remote add` en la terminal, en el directorio donde se encuentra tu repositorio.

### Comando
El comando `git remote add` toma dos argumentos:

- Un nombre remoto, por ejemplo, `origin`.
- Una URL remota, por ejemplo, `https://github.com/OWNER/REPOSITORY.git`.

### Ejemplo
```bash
$ git remote add origin https://github.com/OWNER/REPOSITORY.git
```
Para verificar que el nuevo remoto se ha añadido correctamente, puedes usar:

```bash
$ git remote -v
```

### Analogía
Imagina que tu repositorio local es una biblioteca en tu casa y el repositorio remoto es una biblioteca pública. Cuando usas `git remote add origin`, es como si estuvieras creando un acceso para que las personas de la biblioteca pública puedan ver los libros que tienes en tu biblioteca personal. 

## Solucionando Problemas: El origen remoto ya existe
Si recibes el siguiente error, significa que has intentado agregar un remoto con un nombre que ya existe en tu repositorio local.

```bash
$ git remote add origin https://github.com/octocat/Spoon-Knife.git
> fatal: remote origin already exists.
```

### Soluciones:
- Usa un nombre diferente para el nuevo remoto.
- Renombra el repositorio remoto existente antes de agregar el nuevo.
- Elimina el repositorio remoto existente antes de agregar el nuevo.

## Cambiar la URL de un Repositorio Remoto

El comando `git remote set-url` cambia la URL de un repositorio remoto existente.

### Comando
El comando `git remote set-url` toma dos argumentos:

- Un nombre remoto existente. Por ejemplo, `origin`.
- Una nueva URL para el remoto.

### Ejemplo
Si estás actualizando para usar HTTPS, tu URL podría ser:
```bash
git remote set-url origin https://github.com/OWNER/REPOSITORY.git
```

### Analogía
Volviendo a nuestra biblioteca, cambiar la URL de un repositorio remoto es como actualizar la dirección de la biblioteca pública. Si se muda a un nuevo edificio, necesitas asegurarte de que la dirección que tienes es la correcta para poder visitarla.

## Solucionando Problemas: No existe el remoto '[nombre]'
Este error significa que el remoto que intentaste cambiar no existe:
```bash
$ git remote set-url sofake https://github.com/octocat/Spoon-Knife
> fatal: No such remote 'sofake'
```

### Verificación:
Asegúrate de que has escrito correctamente el nombre del remoto.

## Renombrar un Repositorio Remoto

Usa el comando `git remote rename` para renombrar un remoto existente.

### Comando
El comando `git remote rename` toma dos argumentos:

- Un nombre remoto existente, por ejemplo, `origin`.
- Un nuevo nombre para el remoto, por ejemplo, `destination`.

### Ejemplo
```bash
$ git remote rename origin destination
```

### Analogía
Imagina que cambias el nombre de tu biblioteca personal de "Biblioteca de Juan" a "Biblioteca de Juan y Amigos". Esto no cambia los libros que tienes, solo el nombre que usas para referirte a tu biblioteca.

## Solucionando Problemas: No se pudo renombrar la sección de configuración 'remote.[nombre antiguo]' a 'remote.[nuevo nombre]'
Este error significa que el nombre remoto antiguo que escribiste no existe. Verifica con:

```bash
$ git remote -v
```

## Eliminar un Repositorio Remoto

Usa el comando `git remote rm` para eliminar una URL remota de tu repositorio.

### Comando
El comando `git remote rm` toma un argumento:

- Un nombre remoto, por ejemplo, `destination`.

### Ejemplo
```bash
$ git remote rm destination
```

### Analogía
Eliminar un remoto es como quitar el acceso a la biblioteca pública. Si ya no quieres que las personas vean tus libros, simplemente quitas la dirección de la biblioteca pública.

## Solucionando Problemas: No se pudo eliminar la sección de configuración 'remote.[nombre]'
Este error significa que el remoto que intentaste eliminar no existe:
```bash
$ git remote rm sofake
> error: Could not remove config section 'remote.sofake'
```
Asegúrate de que has escrito correctamente el nombre del remoto.

---

# git-clone - Clonar un repositorio en un nuevo directorio

## SINOPSIS
```bash
git clone [--template=<directorio-de-plantilla>]
          [-l] [-s] [--no-hardlinks] [-q] [-n] [--bare] [--mirror]
          [-o <nombre>] [-b <nombre>] [-u <upload-pack>] [--reference <repositorio>]
          [--dissociate] [--separate-git-dir <git-dir>]
          [--depth <profundidad>] [--[no-]single-branch] [--no-tags]
          [--recurse-submodules[=<pathspec>]] [--[no-]shallow-submodules]
          [--[no-]remote-submodules] [--jobs <n>] [--sparse] [--[no-]reject-shallow]
          [--filter=<filter-spec>] [--also-filter-submodules]] [--] <repositorio>
          [<directorio>]
```

## DESCRIPCIÓN
El comando `git clone` se utiliza para clonar un repositorio en un nuevo directorio creado. Esto significa que se crea una copia exacta del repositorio original, incluidos todos sus archivos, historial de cambios y ramas.

### Analogía
Imagina que estás en una biblioteca (el repositorio original) y decides sacar un libro (clonar el repositorio). Cuando sacas el libro, llevas contigo no solo las páginas, sino también la historia de cada página (historial de cambios) y las notas en los márgenes (ramas). Así, puedes leer, hacer anotaciones y incluso devolver el libro a la biblioteca cuando termines.

Después de clonar, un simple `git fetch` actualizará todas las ramas de seguimiento remoto, y un `git pull` combinará la rama remota principal con la rama actual, si existe.

Este comportamiento predeterminado se logra creando referencias a las ramas remotas bajo `refs/remotes/origin` y configurando las variables de configuración `remote.origin.url` y `remote.origin.fetch`.

## OPCIONES

- **-l, --local**
  - Al clonar desde un repositorio local, esta opción evita el mecanismo de transporte normal de Git y hace una copia de la cabeza (`HEAD`) y todo lo que hay en los directorios `objects` y `refs`. Las archivos en `.git/objects/` se enlazan físicamente para ahorrar espacio, si es posible.
  
  **Analogía:** Es como si tomaras una foto de la estantería en la biblioteca y luego hicieras una copia de los libros en tu casa, asegurándote de que la copia ocupe el mismo espacio que el original.

- **--no-hardlinks**
  - Fuerza al proceso de clonación desde un repositorio en un sistema de archivos local a copiar los archivos en lugar de usar enlaces duros. Esto puede ser útil si deseas hacer una copia de seguridad de tu repositorio.

- **-s, --shared**
  - Cuando el repositorio a clonar está en la máquina local, configura automáticamente `.git/objects/info/alternates` para compartir los objetos con el repositorio fuente. El repositorio resultante comenzará sin ningún objeto propio.

  **Analogía:** Piensa en compartir un libro con un amigo que ya tiene una copia. Ambos pueden usar la misma información sin duplicar el esfuerzo de tener dos copias físicas.

- **--reference[-if-able] <repositorio>**
  - Si el repositorio de referencia está en la máquina local, configura automáticamente `.git/objects/info/alternates` para obtener objetos del repositorio de referencia. Esto reduce el costo de red y almacenamiento local al requerir menos objetos a copiar.

- **--dissociate**
  - Toma prestados los objetos de los repositorios de referencia especificados con las opciones `--reference` solo para reducir la transferencia de red y detiene el préstamo después de que se realiza una clonación.

- **-q, --quiet**
  - Operar de manera silenciosa. No se informa del progreso en la salida de error estándar.

- **-v, --verbose**
  - Ejecutar de manera detallada. No afecta la notificación del estado del progreso a la salida de error estándar.

- **--progress**
  - El estado de progreso se informa por defecto en la salida de error estándar cuando está conectado a un terminal.

- **--bare**
  - Crea un repositorio Git "bare". En lugar de crear un `<directorio>` y colocar los archivos administrativos en `<directorio>/.git`, se convierte el `<directorio>` en el `$GIT_DIR`. Esto implica que no hay árbol de trabajo, ya que no hay un lugar donde realizar la verificación.

  **Analogía:** Es como tener una caja de herramientas vacía sin usar, donde puedes guardar herramientas (commits) pero no puedes trabajar directamente con ellas hasta que las saques (checkout).

- **--depth <profundidad>**
  - Crea una clonación superficial con un historial truncado al número especificado de commits. Implica `--single-branch` a menos que se especifique `--no-single-branch`.

### Más opciones
Hay muchas otras opciones disponibles, cada una con sus propias características y beneficios. Aquí están algunas de las más útiles:

- **--filter=<filter-spec>**
  - Utiliza la función de clonación parcial y solicita que el servidor envíe un subconjunto de objetos alcanzables según un filtro dado.

- **--recurse-submodules[=<pathspec>]**
  - Después de que se crea el clon, inicializa y clona submódulos basados en el `<pathspec>` proporcionado.

## Conclusión
El comando `git clone` es fundamental para trabajar con repositorios en Git, ya que permite duplicar y trabajar en proyectos de manera eficiente. Usando analogías simples, podemos entender mejor los conceptos técnicos detrás de este comando, facilitando el aprendizaje y la aplicación práctica de Git en el desarrollo frontend.

---

# Clonando un Repositorio

## Introducción
Cuando creas un repositorio en GitHub, este existe como un repositorio remoto. Puedes clonar tu repositorio para crear una copia local en tu computadora y sincronizar entre ambas ubicaciones.

### Navegación en la Plataforma
- **Mac**
- **Windows**
- **Linux**

### Navegación de Herramientas
- **GitHub CLI**
- **Escritorio**
- **Navegador Web**

## En este artículo
- Acerca de clonar un repositorio
- Clonando un repositorio
- Clonando un repositorio vacío
- Solucionando errores al clonar
- Lectura adicional

## Acerca de clonar un repositorio
Clonar un repositorio de GitHub.com a tu computadora local, o a un *codespace*, facilita la solución de conflictos de fusión, la adición o eliminación de archivos y el envío de commits más grandes. 

Cuando clonas un repositorio, copias el repositorio de GitHub.com a tu máquina local o a una máquina virtual remota al crear un *codespace*. Clonar un repositorio descarga una copia completa de todos los datos del repositorio que GitHub.com tiene en ese momento, incluyendo todas las versiones de cada archivo y carpeta del proyecto. 

Puedes enviar tus cambios al repositorio remoto en GitHub.com o traer los cambios de otras personas desde GitHub.com. 

## Clonando un repositorio
1. En GitHub, navega a la página principal del repositorio.
2. Encima de la lista de archivos, haz clic en **Code**.
3. Copia la URL del repositorio.
   - Para clonar el repositorio usando HTTPS, haz clic en el icono correspondiente.
   - Para clonar usando una clave SSH, haz clic en SSH y luego en el icono.
   - Para clonar usando GitHub CLI, haz clic en GitHub CLI y luego en el icono.

4. Abre **Git Bash**.
5. Cambia el directorio de trabajo actual a la ubicación donde deseas que esté el directorio clonado.
6. Escribe `git clone`, y luego pega la URL que copiaste anteriormente:

   ```bash
   git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
   ```

7. Presiona **Enter** para crear tu clon local:

   ```bash
   $ git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
   > Clonando en `Spoon-Knife`...
   > remoto: Contando objetos: 10, hecho.
   > remoto: Comprimiendo objetos: 100% (8/8), hecho.
   > deshacer: Total 10 (delta 1), reutilizado 10 (delta 1)
   > Desempaquetando objetos: 100% (10/10), hecho.
   ```

## Clonando un repositorio vacío
Un repositorio vacío no contiene archivos. Esto ocurre frecuentemente si no inicializas el repositorio con un README al crearlo.

1. En GitHub, navega a la página principal del repositorio.
2. Para clonar tu repositorio usando la línea de comandos con HTTPS, haz clic en el icono correspondiente en "Configuración rápida". Para clonar usando una clave SSH, haz clic en SSH y luego en el icono.
3. Alternativamente, para clonar tu repositorio en el Escritorio, haz clic en **Configurar en Escritorio** y sigue las instrucciones para completar la clonación.

4. Abre **Git Bash**.
5. Cambia el directorio de trabajo actual a la ubicación donde deseas que esté el directorio clonado.
6. Escribe `git clone`, y luego pega la URL que copiaste anteriormente:

   ```bash
   git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
   ```

7. Presiona **Enter** para crear tu clon local:

   ```bash
   $ git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
   > Clonando en `Spoon-Knife`...
   > remoto: Contando objetos: 10, hecho.
   > remoto: Comprimiendo objetos: 100% (8/8), hecho.
   > deshacer: Total 10 (delta 1), reutilizado 10 (delta 1)
   > Desempaquetando objetos: 100% (10/10), hecho.
   ```

## Solucionando errores al clonar
Cuando clonas un repositorio, es posible que te encuentres con algunos errores. Si no puedes clonar un repositorio, verifica que:

- Puedes conectarte usando HTTPS.
- Tienes permiso para acceder al repositorio que deseas clonar.
- La rama predeterminada que deseas clonar todavía existe.

---

## Analogías Sencillas

### Clonar un repositorio
Clonar un repositorio es como hacer una copia de un libro en tu biblioteca. Tienes el libro original (el repositorio en GitHub) y decides hacer una copia para leerla en casa (el repositorio local). Puedes escribir en tu copia y, cuando termines, puedes compartir esos cambios con el original.

### Repositorio vacío
Un repositorio vacío es como tener un cuaderno nuevo sin páginas escritas. No importa cuántas veces lo mires, no tiene contenido hasta que decidas escribir algo en él. 

### Solucionando errores
Solucionar errores al clonar es como verificar si tu impresora está encendida antes de intentar imprimir un documento. Si no hay conexión o no tienes permiso, no podrás hacer la copia.