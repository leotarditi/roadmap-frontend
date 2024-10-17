# Estrategias de Merge en Git

Cuando trabajamos con Git, uno de los mecanismos clave para combinar diferentes ramas es el **merge**. Git nos permite elegir diferentes estrategias de merge utilizando la opción `-s` en los comandos `git merge` y `git pull`. Algunas estrategias también tienen sus propias opciones, que se pueden pasar con el argumento `-X`.

Para entender mejor cómo funcionan estas estrategias, imagina que estás organizando una fiesta con tus amigos y cada uno trae sus propias ideas. Algunas ideas coinciden y otras no, pero al final, todos deben decidir juntos cómo será la fiesta. Las estrategias de merge son las reglas que siguen para fusionar esas ideas en un solo plan.

## Estrategia Ort (default)
La estrategia `ort` es como el organizador principal de la fiesta que, en caso de conflicto, se asegura de que las ideas de todos se tomen en cuenta de manera justa. Usa un algoritmo llamado "merge de tres vías" que revisa tanto las ideas comunes (ancestros) como las propuestas actuales, y trata de combinar lo mejor de ambas.

### Analizando un conflicto con Ort:
- **Opción ours**: Si hay un conflicto, se elige nuestra idea por encima de la de los demás. Es como decir: "Vamos a seguir con lo que yo propuse".
- **Opción theirs**: Lo contrario de `ours`. Si hay conflicto, se elige la idea de la otra persona.
- **Ignorar cambios en espacios**: Algunas opciones como `ignore-space-change` y `ignore-all-space` hacen que los cambios menores, como los espacios en blanco, no generen conflictos. Es como decidir que no importa si alguien trae comida en platos de papel o porcelana, mientras sea la misma comida.

### Ejemplo práctico:
Imagina que dos amigos sugieren cómo decorar la sala. Uno propone globos rojos y el otro globos azules. Usando la estrategia `ort`, revisas las propuestas, consultas cómo se hizo en fiestas anteriores (ancestros comunes) y decides una combinación que use los colores de ambos.

## Estrategia Recursiva (la anterior por defecto)
Antes de que `ort` fuera la predeterminada, la estrategia usada era `recursive`. Sigue un proceso similar de "merge de tres vías", pero con diferencias en cómo trata los archivos renombrados y los cambios menores.

### Opciones adicionales de la estrategia recursiva:
- **paciencia**: Es como si el organizador de la fiesta fuera más paciente a la hora de combinar las ideas, dándole más tiempo a cada detalle para que se resuelva correctamente.
- **no renames**: Desactiva la detección de renombrados. Útil cuando no quieres complicarte si alguien decide cambiar el nombre de un archivo (o la temática de una actividad en la fiesta).

## Otras Estrategias de Merge
Git también tiene otras estrategias de merge que puedes usar en situaciones específicas:

- **resolve**: Útil cuando solo tienes dos propuestas de ideas. Intenta resolver los conflictos de la mejor manera posible, pero no es buena para manejar renombrados.
- **octopus**: Ideal cuando tienes varias ramas (o propuestas) y quieres combinarlas de forma sencilla, pero sin permitir grandes conflictos.
- **ours**: Ignora completamente las otras ideas y sigue adelante solo con la tuya. Es como si dijeras: "Esta fiesta será exactamente como yo quiero, sin importar las sugerencias de los demás".
- **subtree**: Esta estrategia es como ajustar una idea para que encaje en el contexto general. Si alguien propone una actividad que es parte de otra mayor, primero ajustas esa pequeña parte para que se integre con el todo.

---

### Resumen:
Las estrategias de merge en Git son como diferentes formas de tomar decisiones cuando organizamos una fiesta en grupo. Algunas estrategias intentan combinar las mejores ideas de todos, mientras que otras favorecen una idea sobre otra. Saber qué estrategia usar depende de cómo queremos manejar los conflictos y las diferentes versiones de nuestro código.

---

# Git Fast-Forward VS Non-Fast-Forward

**Fecha**: 07-03-2023  
**Duración**: 8 minutos de lectura (aproximadamente 1210 palabras)  
**Visitas**: 

## Introducción

Cuando ejecutamos `git push`, a veces nos encontramos con rechazos porque la rama remota no se puede actualizar mediante un *fast-forward*. Esto ocurre porque podríamos haber hecho algo incorrecto y un mecanismo de Git se activa para prevenir la pérdida de commits.

Por ejemplo, al intentar hacer un `git push`, podemos recibir un mensaje como el siguiente:

```bash
$ git push
To github.com:leimao/onnx.git
 ! [rejected]          grid_sample_nd -> grid_sample_nd (non-fast-forward)
error: failed to push some refs to 'github.com:leimao/onnx.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

En este artículo, discutiré la diferencia entre *fast-forward* y *non-fast-forward*, entendiendo la lógica detrás de estas diferencias y cómo usar `git push --force` de manera correcta y cuidadosa.

## Fast-Forward

Un *fast-forward* ocurre cuando se actualiza una rama que apunta al commit A para apuntar a otro commit B, y B es un descendiente de A. En este caso, el conjunto de commits sobre el que se construyó el commit A es un subconjunto de los commits sobre los que se construye el nuevo commit B. Por lo tanto, no se pierde ninguna historia.

### Ejemplo 1

Este es el ejemplo más común que encontramos en nuestro uso diario de Git. Creamos una rama local, hacemos un nuevo commit y queremos actualizar la rama remota desde la rama local.

Si el commit B es un descendiente del commit A, la rama remota puede ser actualizada mediante un *fast-forward* con `git push`.

Antes de la actualización mediante *fast-forward*, el diagrama se ve así:

```
     B (rama local)
    /
---A (rama remota)
```

Después de la actualización, el diagrama se verá así:

```
---A---B (rama remota y rama local)
```

### Ejemplo 2

En este ejemplo, extendemos el anterior creando múltiples commits en la rama local y queremos actualizar la rama remota.

El commit C es un descendiente del commit A, por lo que la rama remota puede ser actualizada mediante *fast-forward* usando `git push`.

Antes de la actualización, el diagrama es:

```
     B---C (rama local)
    /
---A (rama remota)
```

Después de la actualización, el diagrama se verá así:

```
---A---B---C (rama remota y rama local)
```

Esto normalmente ocurre cuando el usuario crea una rama y es el único que trabaja en ella.

### Ejemplo 3

En este caso, mientras creamos commits en la rama local, la rama remota se actualizó por otros colaboradores. Queremos actualizar la rama remota desde la rama local.

```
     B (rama local)
    /
---X---A (rama remota)
```

Debemos hacer un pull de los commits de la rama remota a la rama local, resolver los conflictos de merge si los hay, resultando en un nuevo commit C.

```
     B---C (rama local)
    /   /
---X---A (rama remota)
```

Después de la actualización, el diagrama se verá así:

```
---X---A---C (rama remota y rama local)
```

## Non-Fast-Forward

En contraste, una actualización *non-fast-forward* perderá historia. Supongamos que tú y otra persona comenzaron en el mismo commit X. Tú construiste una historia que lleva al commit B, mientras que la otra persona construyó una historia que lleva al commit A.

### Ejemplo de Rebase en Git

Es muy común que la rama remota se quede atrás con respecto a la rama principal en un repositorio colaborativo. Por lo tanto, cuando el usuario intenta fusionar la rama remota con la rama principal, pueden surgir conflictos de merge.

```
     B (rama remota)
    /
---X---A (rama principal)
```

Un hábito común es que el usuario rebasa la rama remota con la rama principal y resuelve conflictos si los hay durante el rebase, para que cuando la rama remota se fusiona con la rama principal, el diagrama se vea así:

```
         C (rama remota)
        /
---X---A (rama principal)
```

Sin embargo, en la práctica, después de hacer el rebase, cuando el usuario intenta actualizar la rama remota desde la rama local, esta no puede ser actualizada mediante *fast-forward*.

Antes de hacer el rebase, el diagrama es:

```
     B (rama remota y rama local)
    /   
---X---A (rama principal)
```

Después del rebase y de resolver los conflictos, el diagrama será:

```
     B (rama remota)
    /   
---X---A (rama principal)
        \
         C (rama local después del rebase)
```

Para actualizar la rama remota, debemos forzar la actualización *non-fast-forward* usando `git push --force`.

```
         C (rama remota y rama local)
        /   
---X---A (rama principal)
```

Si hay otro commit D que se fusionó en la rama remota antes de `git push --force`, como:

```
     B---D (rama remota)
    /   
---X---A (rama principal)
        \
         C (rama local después del rebase)
```

El commit D será borrado por la actualización *non-fast-forward* y se perderá. El diagrama quedará así:

```
         C (rama remota y rama local)
        /   
---X---A (rama principal)
```

### Ejemplo de Modificación de Commit en Git

Las operaciones de Git que cambian el historial de commits, como `git commit --amend`, a veces desactivan la actualización *fast-forward*.

Antes de la actualización, el diagrama se ve así:

```
     A (rama local)
    /
---X (rama remota)
```

Después de la actualización, el diagrama será:

```
---X---A (rama remota y rama local)
```

Luego, continuamos trabajando en la rama local y, de alguna manera, usamos `git commit --amend`, que crea un nuevo commit B y cambia el historial anterior. El diagrama ahora se verá así:

```
     B (rama local)
    / 
---X---A (rama remota)
```

En esta situación, aunque sabemos que el commit B es una continuación del commit A, actualizar la rama remota desde la rama local se vuelve imposible, porque el commit B de la rama local no es un descendiente del commit A de la rama remota. Tendremos que usar `git push --force` y el diagrama resultante será:

```
---X---B (rama remota y rama local)
```

## Conclusiones

Por lo tanto, `git push --force` es "peligroso" y puede causar la pérdida de commits. Pero no es un enemigo; en muchas situaciones es inevitable usarlo. Debemos saber lo que estamos haciendo y comunicarnos bien con los colaboradores cuando trabajamos en una rama que no es principal. Sin embargo, la rama principal nunca debe ser actualizada *non-fast-forward*, ya que normalmente no podemos permitirnos perder commits de la rama principal.

---

# Git Squash Commits – Combinando los Últimos N Commits en Uno

**Autor:** Kolade Chris

Si estás trabajando en un proyecto y tratando de implementar una nueva funcionalidad, es probable que realices varios commits mientras pruebas tu código. Esto te permite ver cómo funciona o se ve el código. Sin embargo, a medida que avanzas, es posible que tu historial de commits se vuelva desordenado, ya que puedes tener varios commits, incluso para cambios que no son necesarios.

Para solucionar esto, podrías querer combinar todos esos commits en uno solo. Este proceso se llama **squashing** de commits.

## ¿Qué es el Squashing de Commits?

Imagina que estás cocinando un guiso y has añadido ingredientes uno por uno. Si al final tienes demasiados recipientes en la mesa, podrías decidir mezclar todos esos ingredientes en una sola olla. Esto simplifica el proceso y hace que sea más fácil de manejar. En Git, hacer squash de commits es similar: tomas varios cambios pequeños y los combinas en uno más limpio y manejable.

## Cómo Hacer Squash de Commits en Git con Rebase Interactivo

En este proceso, utilizarás el comando `git rebase` con el flag `-i` para combinar tus commits. Este comando no solo te permite hacer squash, sino también eliminar commits, modificar mensajes de commits y agregar nuevos archivos.

Supongamos que tienes estos commits que deseas combinar:

![Comandos de Git](link_a_tu_imagen)

### 1. Verifica tus commits

Primero, debes verificar cuántos commits deseas combinar. Ejecuta el siguiente comando:

```bash
git log --oneline
```

### 2. Prepara el Rebase

Si deseas hacer squash de todos los commits en tu rama `new-feature`, necesitarás ir atrás en el tiempo, digamos, 6 commits. Ejecuta:

```bash
git rebase -i HEAD~6
```

Esto abrirá tu editor de texto (por defecto es Vim, pero en este caso es VS Code).

### 3. Modifica los Commits

En el editor, verás algo como esto:

```
pick abcdef1 Primer commit
pick abcdef2 Segundo commit
pick abcdef3 Tercer commit
pick abcdef4 Cuarto commit
pick abcdef5 Quinto commit
pick abcdef6 Sexto commit
```

Reemplaza todas las palabras `pick` (o `p`) con `squash` (o simplemente `s`) a excepción del primero. Esto le dice a Git que combine esos commits:

```
pick abcdef1 Primer commit
squash abcdef2 Segundo commit
squash abcdef3 Tercer commit
squash abcdef4 Cuarto commit
squash abcdef5 Quinto commit
squash abcdef6 Sexto commit
```

### 4. Guarda y Cierra

Después de hacer esto, guarda el archivo y ciérralo. Git abrirá otro editor donde podrás ver el nuevo mensaje de commit generado:

![Mensaje de Commit](link_a_tu_imagen)

Aquí puedes deshacerte de todos ellos y agregar tu mensaje personalizado. Guarda y cierra nuevamente.

### 5. Verifica el Resultado

Después de completar el rebase, verifica tu historial de commits nuevamente:

```bash
git log --oneline
```

Deberías ver que todos los commits se han combinado en uno solo con el nuevo mensaje:

![Historial de Commits](link_a_tu_imagen)

## Cómo Hacer Squash de Commits con el Comando Merge y el Flag --squash

También puedes combinar múltiples commits en uno al momento de fusionar ramas. Esto ayuda a limpiar la rama de los commits redundantes. Sin embargo, esta opción no te da tanto control como el rebase.

### 1. Reestablece tus Commits

Si deseas volver a los commits previos, puedes ejecutar:

```bash
git reset --hard HEAD@{7}
```

Luego, verifica tu historial nuevamente.

### 2. Cambia a la Rama Principal

Cambia a la rama principal ejecutando:

```bash
git switch main
```

### 3. Fusiona y Haz Squash

Para fusionar la rama `new-feature` a `main` y hacer squash de los commits, usa:

```bash
git merge --squash new-feature
```

Si verificas el log de Git en este momento, no verás ningún commit en la rama `new-feature` todavía. Pero si ejecutas `git status`, verás los cambios listos para ser confirmados.

### 4. Realiza el Commit

Ahora, haz el commit de esos cambios con un mensaje adecuado. Después de esto, verifica tu log nuevamente para asegurarte de que todo está en orden.

## Conclusión

En este artículo, hemos aprendido cómo hacer squash de múltiples commits en uno de dos maneras diferentes. Independientemente de la opción que elijas, el objetivo final de combinar los commits se logra.

Si deseas tener más control sobre el proceso, puedes usar la opción de rebase con `-i`. Pero si prefieres un método más sencillo, puedes hacer squash de los commits al fusionar. Solo ten en cuenta que con esta opción, deberás confirmar tus cambios nuevamente.

---

# Cómo Hacer Squash de Commits en Git
## Guía Fácil para Hacer Squash de Commits con Solución de Problemas

### Introducción

Imagina que estás preparando una receta de cocina. Cada ingrediente que agregas a la mezcla es como un commit en Git. A veces, después de agregar varios ingredientes, te das cuenta de que quieres simplificar tu receta y combinar algunos de esos ingredientes en uno solo. Esto es lo que hacemos cuando hacemos "squash" de commits: tomamos varios cambios y los combinamos en uno solo para que nuestra historia sea más limpia y fácil de seguir.

### Paso a Paso para Hacer Squash

1. **Cambia a la rama que quieres "squash"**.
   ```bash
   git checkout <nombre de la rama>
   // ejemplo: git checkout develop
   ```

2. **Verifica cuántos commits tienes en esa rama**.
   ```bash
   git log
   ```

3. **Realiza el squash**.
   ```bash
   git rebase -i HEAD~<número de commits>
// ejemplo: git rebase -i HEAD~2
   ```

4. **Selecciona qué commits deseas combinar**. Si quieres "squash" ese commit, escribe `squash` antes del número del commit. Si quieres seleccionar el commit al que se combinarán otros, escribe `pick` antes del número del commit. Debería verse algo así:
   ```
   pick 1234567 Primer commit
   squash 2345678 Segundo commit
   ```

5. **Presiona `esc`, luego escribe `:wq` y presiona `enter`.**

6. **Vuelve a escribir `:wq` y presiona `enter` nuevamente.**

7. **Realiza un push forzado de tus cambios**.
   ```bash
   git push -f
   ```

### Solución de Problemas

Si te encuentras con errores de conflicto de fusión al hacer squash, no entres en pánico. Simplemente escribe:
```bash
git mergetool
```
Esto abrirá una herramienta de fusión externa donde podrás resolver errores fácilmente. Busca la línea marcada en rojo que indica el error. Después de resolver el conflicto, presiona `cmd+s` y cierra la herramienta. Luego, continúa con el squash:
```bash
git rebase --continue
```

Si tienes más de dos commits para hacer squash, es posible que tengas que repetir estos pasos más de una vez. No te preocupes, es normal.

### Consejos para Hacer Squash

Un pequeño consejo: **siempre haz squash después de hacer un commit**. Cuantos más commits tengas que combinar, mayor será la probabilidad de conflictos. Haz del squash un hábito después de cada commit.

---

# Ramificación en Git - Rebasing
## Qué es el Rebasing

En Git, hay dos maneras principales de integrar cambios de una rama a otra: **merge** y **rebase**. En esta sección aprenderás qué es el rebasing, cómo hacerlo, por qué es una herramienta impresionante y en qué casos no querrás usarlo.

### El Rebasing Básico

Imagina que estás construyendo una casa. Tienes dos equipos trabajando en diferentes habitaciones (ramas). A medida que cada equipo hace su trabajo, se desvían de los planos originales (cambios realizados). El `merge` es como juntar todas las habitaciones al final, mientras que el `rebase` es como tomar los cambios de una habitación y aplicarlos a la otra antes de juntar todo.

Por ejemplo, puedes cambiar a la rama de experimentación y luego hacer un rebase sobre la rama principal:
```bash
git checkout experiment
git rebase master
```

Este proceso funciona yendo al ancestro común de las dos ramas, obteniendo las diferencias introducidas por cada commit, guardando esos cambios en archivos temporales, reiniciando la rama actual al mismo commit de la rama a la que te estás "rebasando" y aplicando cada cambio en orden.

### Más Rebases Interesantes

Supongamos que deseas fusionar los cambios del cliente en la rama principal para un lanzamiento, pero deseas posponer los cambios del servidor hasta que se hayan probado más. Puedes tomar los cambios del cliente y volver a aplicarlos en la rama principal usando la opción `--onto` de `git rebase`:
```bash
git rebase --onto master server client
```

Esto permite que los cambios del cliente se apliquen a la rama principal directamente.

### Los Peligros del Rebasing

A pesar de su utilidad, el rebasing tiene sus desventajas. Recuerda:

**No hagas rebase de commits que existan fuera de tu repositorio y que otras personas puedan haber basado su trabajo en ellos.**

Si reescribes commits públicos, tus colaboradores tendrán que lidiar con conflictos y el trabajo puede volverse confuso. Siempre que sigas esta regla, estarás a salvo.

---

# Resolviendo conflictos de fusión usando la línea de comandos

## Navegación en la plataforma
- **Mac**
- **Windows**
- **Linux**

## En este artículo
- Conflictos de fusión por cambios de línea en competencia
- Conflictos de fusión por archivos eliminados
- Lectura adicional

Los conflictos de fusión ocurren cuando se realizan cambios en competencia en la misma línea de un archivo, o cuando una persona edita un archivo y otra persona elimina el mismo archivo. Para más información, consulta "[Acerca de los conflictos de fusión](https://docs.github.com/en/get-started/using-git/merging-branches#about-merge-conflicts)".

**Consejo:** Puedes usar el editor de conflictos en GitHub para resolver conflictos de fusión por cambios de línea en competencia entre ramas que son parte de una solicitud de extracción. Para más información, consulta "[Resolviendo un conflicto de fusión en GitHub](https://docs.github.com/en/get-started/using-git/resolving-a-merge-conflict-on-github)".

## Conflictos de fusión por cambios de línea en competencia

Imagina que estás organizando una fiesta y tu amigo también. Ambos quieren decidir el menú, pero cada uno tiene ideas diferentes sobre lo que debería haber. Al final, tienen que llegar a un acuerdo para que la fiesta sea un éxito.

Para resolver un conflicto de fusión causado por cambios de línea en competencia, debes elegir qué cambios incorporar de las diferentes ramas en un nuevo compromiso.

### Pasos para resolver conflictos de línea:

1. **Abre Git Bash.**
2. **Navega al repositorio local que tiene el conflicto de fusión.**
   ```bash
   cd NOMBRE-DEL-REPOSITORIO
   ```
3. **Genera una lista de los archivos afectados por el conflicto de fusión.**
   ```bash
   git status
   ```
   ```plaintext
   # En la rama branch-b
   # Tienes rutas no fusionadas.
   #   (arregla los conflictos y ejecuta "git commit")
   #
   # Rutas no fusionadas:
   #   (usa "git add <archivo>..." para marcar la resolución)
   #
   # ambos modificados:      styleguide.md
   #
   # no hay cambios añadidos para el commit (usa "git add" y/o "git commit -a")
   ```

4. **Abre tu editor de texto favorito** (como Visual Studio Code) y navega hasta el archivo que tiene conflictos de fusión.

5. **Busca el marcador de conflicto `<<<<<<<`.** En tu archivo, verás los cambios de la rama base después de la línea `<<<<<<< HEAD`, luego verás `=======`, que divide tus cambios de los cambios en la otra rama, seguido de `>>>>>>> NOMBRE-DE-LA-RAMA`.

   ```plaintext
   Si tienes preguntas, por favor
   <<<<<<< HEAD
   abre un issue
   =======
   pregunta en nuestro canal de IRC.
   >>>>>>> branch-a
   ```

6. **Decide qué cambios conservar.** Puedes conservar solo los cambios de tu rama, solo los de la otra rama, o hacer un cambio nuevo que incorpore cambios de ambas ramas. Elimina los marcadores de conflicto y realiza los cambios que desees en la fusión final:

   ```plaintext
   Si tienes preguntas, por favor abre un issue o pregunta en nuestro canal de IRC si es más urgente.
   ```

7. **Agrega o prepara tus cambios.**
   ```bash
   git add .
   ```

8. **Confirma tus cambios con un comentario.**
   ```bash
   git commit -m "Resolver conflicto de fusión incorporando ambas sugerencias"
   ```

Ahora puedes fusionar las ramas en la línea de comandos o enviar tus cambios a tu repositorio remoto en GitHub y fusionar tus cambios en una solicitud de extracción.

## Conflictos de fusión por archivos eliminados

Siguiendo con nuestra fiesta, supongamos que mientras uno de ustedes decide qué platos incluir, otro decide que debería eliminar un plato del menú. Aquí también deben acordar si mantienen el plato o lo eliminan.

### Pasos para resolver conflictos por archivos eliminados:

1. **Abre Git Bash.**
2. **Navega al repositorio local que tiene el conflicto de fusión.**
   ```bash
   cd NOMBRE-DEL-REPOSITORIO
   ```
3. **Genera una lista de los archivos afectados por el conflicto de fusión.**
   ```bash
   git status
   ```
   ```plaintext
   # En la rama main
   # Tu rama y 'origin/main' han divergido,
   # y tienen 1 y 2 commits diferentes cada una, respectivamente.
   #  (usa "git pull" para fusionar la rama remota en la tuya)
   # Tienes rutas no fusionadas.
   #  (arregla los conflictos y ejecuta "git commit")
   #
   # Rutas no fusionadas:
   #  (usa "git add/rm <archivo>..." según corresponda para marcar la resolución)
   #
   # eliminado por nosotros:   README.md
   #
   # no hay cambios añadidos para el commit (usa "git add" y/o "git commit -a")
   ```

4. **Abre tu editor de texto favorito** y navega hasta el archivo que tiene conflictos de fusión.

5. **Decide si quieres mantener el archivo eliminado.** Puede que quieras ver los últimos cambios realizados en el archivo eliminado.

6. **Para agregar el archivo eliminado de nuevo a tu repositorio:**
   ```bash
   git add README.md
   ```

7. **Para eliminar este archivo de tu repositorio:**
   ```bash
   git rm README.md
   ```

8. **Confirma tus cambios con un comentario.**
   ```bash
   git commit -m "Resolver conflicto de fusión manteniendo el archivo README.md"
   ```

Ahora puedes fusionar las ramas en la línea de comandos o enviar tus cambios a tu repositorio remoto en GitHub y fusionar tus cambios en una solicitud de extracción.

## Resolviendo conflictos de fusión en Visual Studio

Cuando fusionas una rama en otra, los cambios en los archivos de los commits de una rama pueden entrar en conflicto con los cambios en la otra. Git intenta resolver estos cambios utilizando el historial en tu repositorio para determinar cómo deberían verse los archivos fusionados. Cuando no está claro cómo fusionar los cambios, Git detiene la fusión y te informa sobre los archivos en conflicto.

### Pasos para resolver conflictos en Visual Studio:

1. **Prevención de conflictos de fusión:**
   Git es bueno en la fusión automática de cambios de archivos en la mayoría de los casos, siempre que el contenido del archivo no cambie drásticamente entre los commits. Si tu rama está muy atrasada respecto a la rama principal, considera rebasear tus ramas antes de abrir una solicitud de extracción.

2. **Resolviendo conflictos de fusión:**
   Si colaboras con otros en la misma rama, podrías ver conflictos de fusión cuando empujas tus cambios.

   Visual Studio detecta si la rama local en la que has estado trabajando está detrás de su rama remota y te da opciones para elegir.

   ![Opciones de fusión en Visual Studio](ruta/a/la/imagen.png)

   **Nota:** Si tu repositorio remoto admite "Force Push", puedes habilitarlo usando `Git > Settings`.

   En este ejemplo, selecciona **Pull** y luego **Push** para incluir los cambios introducidos en el repositorio remoto. Si hay conflictos de fusión al jalar cambios o intentar fusionar dos ramas, Visual Studio te lo notificará en la ventana de cambios de Git.

   ![Notificación de conflicto de fusión](ruta/a/la/imagen.png)

3. **Resolviendo los conflictos:**
   La ventana de cambios de Git muestra una lista de archivos con conflictos. Para comenzar a resolver los conflictos, haz doble clic en un archivo o selecciona **Open Merge Editor**.

   En el editor de fusión, comienza a resolver tu conflicto utilizando cualquiera de los siguientes métodos:
   - Ve tus conflictos línea por línea y elige entre mantener el lado derecho o el izquierdo seleccionando las casillas de verificación.
   - Selecciona el botón **Take Incoming** (o presiona F10) para aceptar todos los cambios entrantes, o el botón **Take Current** (o presiona F11) para mantener tu versión actual de todos los cambios en conflicto. También puedes hacer lo mismo seleccionando una de las casillas de verificación en la parte superior de cualquiera de los marcos lado a lado.
   - Edita manualmente tu código en la ventana de Resultados.

   ![Resolviendo conflictos en Visual Studio](ruta/a/la/imagen.png)

4. **Finalizando la resolución:**
   Cuando termines de resolver los conflictos de fusión, selecciona **Accept Merge**. Repite este proceso para todos los archivos en conflicto.

   Usa la ventana de cambios de Git para crear un commit de fusión y resolver el conflicto.

   ![Creando un commit de fusión](ruta/a/la/imagen.png)

   **Nota:** Si deseas mantener todos tus cambios en un archivo, puedes hacer clic derecho en él en la sección de cambios no fusionados y seleccionar **Keep Current (Local)** sin tener que abrir el editor de fusión.

5. **Configurando tu herramienta de comparación:**
   Si configuraste tu archivo `.gitconfig` para usar una herramienta de comparación de

 terceros, puedes abrir tu herramienta de comparación seleccionando **Comparar con una herramienta de comparación** y eligiendo la herramienta que deseas usar.

   ![Configuración de herramienta de comparación](ruta/a/la/imagen.png)

   Si deseas aprender más sobre las herramientas de comparación y fusión que se pueden utilizar con Visual Studio, consulta "[Configurando una herramienta de comparación externa para Git](https://learn.microsoft.com/en-us/visualstudio/version-control/configuring-external-merge-tools?view=vs-2019)".

---

# Git Cherry-Pick: Aplicando Cambios de Commits Existentes

## Introducción
`git cherry-pick` es una herramienta en Git que te permite aplicar los cambios introducidos por uno o más commits existentes. Imagina que tienes un delicioso pastel de chocolate, y decides que te gustaría tomar una rebanada para llevar a otra fiesta sin tener que hornear todo el pastel nuevamente. `git cherry-pick` hace algo similar: toma solo las partes de un commit que necesitas y las aplica en tu rama actual, creando un nuevo commit.

## Sinopsis
```bash
git cherry-pick [--edit] [-n] [-m <parent-number>] [-s] [-x] [--ff]
                  [-S[<keyid>]] <commit>…
git cherry-pick (--continue | --skip | --abort | --quit)
```

## Descripción
Dado uno o más commits existentes, `git cherry-pick` aplica los cambios que introduce cada uno, registrando un nuevo commit por cada uno. Esto requiere que tu árbol de trabajo esté limpio (sin modificaciones desde el commit HEAD).

### ¿Qué sucede cuando no es obvio cómo aplicar un cambio?
- La rama actual y el puntero HEAD permanecen en el último commit que se aplicó con éxito.
- El ref `CHERRY_PICK_HEAD` se establece para apuntar al commit que introdujo el cambio que es difícil de aplicar.
- Las rutas donde el cambio se aplicó correctamente se actualizan en el archivo de índice y en tu árbol de trabajo.
- Para las rutas en conflicto, el archivo de índice registra hasta tres versiones. Los archivos del árbol de trabajo incluirán una descripción del conflicto entre los marcadores de conflicto habituales `<<<<<<<` y `>>>>>>>`.

## Opciones
- `<commit>…`: Especifica los commits que se desean aplicar. Puedes pasar un conjunto de commits, pero no se realizará un recorrido por defecto.
  
- `-e`, `--edit`: Permite editar el mensaje del commit antes de confirmarlo.

- `-x`: Al grabar el commit, añade una línea que dice "(cherry picked from commit … )" al mensaje original del commit para indicar de dónde proviene el cambio.

- `-n`, `--no-commit`: Aplica los cambios sin crear un commit. Esto es útil cuando se desean aplicar varios commits secuencialmente.

- `--ff`: Si el HEAD actual es el mismo que el padre del commit cherry-picked, se realizará un avance rápido a este commit.

## Ejemplos
1. **Aplicar un commit del branch master:**
   ```bash
   git cherry-pick master
   ```
   Esto aplica el cambio introducido por el commit en la punta del branch master y crea un nuevo commit con este cambio.

2. **Aplicar múltiples commits:**
   ```bash
   git cherry-pick master~4 master~2
   ```
   Esto aplica los cambios introducidos por el quinto y el tercer commit más reciente en master, creando dos nuevos commits con estos cambios.

3. **Aplicar cambios sin crear un nuevo commit:**
   ```bash
   git cherry-pick -n master~1 next
   ```
   Esto aplica los cambios de los dos últimos commits, pero no crea ningún nuevo commit.

4. **Manejo de conflictos:**
   Si `git cherry-pick` encuentra un conflicto, puede ser necesario abortar la operación y volver al estado anterior:
   ```bash
   git cherry-pick --abort
   ```

## Conclusión
Utilizar `git cherry-pick` es una forma eficiente de aplicar cambios específicos de un commit sin tener que incorporar todos los cambios de un branch. Esta herramienta es especialmente útil en flujos de trabajo donde se necesita mantener un historial limpio y aplicar solo las mejoras necesarias, como llevar una rebanada de pastel a una fiesta en lugar de hornear uno entero.