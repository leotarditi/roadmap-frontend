# Mensajes de Commit

## Curso de Fundamentos

### Introducción
Esta lección explicará la importancia de los buenos mensajes de commit, cómo escribirlos, cuándo hacer un commit y por qué tener un historial de buenos commits es tan importante.

### Descripción general de la lección
Esta sección contiene un resumen general de los temas que aprenderás en esta lección.

1. Cómo escribir un mensaje de commit significativo.
2. Por qué los mensajes de commit significativos son importantes.
3. Cuándo hacer un commit.
4. ¿Son tan importantes los mensajes de commit que merecen su propia lección?
   - ¡Sí! Aquí tienes una lista rápida de razones por las cuales:

   - Cuando postulas a trabajos, los empleadores revisarán tus proyectos en GitHub y examinarán tu historial de commits. Tener buenos commits como desarrollador novato te ayudará a destacar.
   
   - Tener un buen historial de mensajes de commit permitirá a ti (o a otros desarrolladores que trabajen en tu código) ver rápidamente qué cambios se hicieron y por qué. ¡Esto es útil si se encuentra un error en el código que necesita ser corregido!
   
   - Un buen historial de mensajes de commit también será útil si regresas a un proyecto en el que estabas trabajando después de un tiempo. Seguramente no recordarás tu proceso de pensamiento y los cambios realizados al escribir inicialmente el código.

### Malos vs. Buenos Commits
Al escribir commits, es crucial saber cómo redactarlos efectivamente. Aquí hay un ejemplo de un mal mensaje de commit:

```
fix a bug
```
Aunque describe lo que hiciste, el mensaje es demasiado vago, lo que deja confundidos a otros desarrolladores de tu equipo. Un buen mensaje de commit explicará el **por qué** detrás de tus cambios. En otras palabras, un mensaje de commit describe qué problema resuelven tus cambios y cómo lo hacen.

Los commits efectivos constan de dos partes separadas: un **asunto** y un **cuerpo**.

#### Asunto
Un resumen breve del cambio que realizaste en el proyecto.  
Ejemplo: 
```
Agrega un enlace y texto alternativo faltante al logotipo de la empresa
```
GitHub tiene un límite de 72 caracteres, por lo que recomendamos mantener los asuntos de tus commits dentro de esta cantidad.

#### Cuerpo
Una descripción concisa pero clara de lo que hiciste.  
Ejemplo:
```
Los lectores de pantalla no leerán las imágenes a los usuarios con discapacidades sin esta información.
```
¡Ah, eso es mejor! Ahora, los desarrolladores pueden comprender mejor este mensaje de commit porque:

- Proporciona un asunto que especifica la acción de tu código (por ejemplo, “Agrega un enlace y texto alternativo faltante al logotipo de la empresa”).
- Contiene un cuerpo que proporciona una descripción concisa pero clara de por qué fue necesario hacer el commit (por ejemplo, “Los lectores de pantalla no leerán las imágenes a los usuarios con discapacidades sin esta información”).
- Separa el asunto del cuerpo con una línea nueva en blanco. Esta es una práctica recomendada que recomendamos seguir. Hace que los mensajes de commit sean más fáciles de leer para otros desarrolladores.

### Cómo hacer un commit con un asunto y cuerpo en el mensaje
Hasta ahora, se te ha dicho que hagas un commit con `git commit -m <mensaje>`. Para hacer un commit con un asunto y un cuerpo en el mensaje, la forma más simple es escribir `git commit` sin la opción `-m` y el argumento del mensaje.

Esto abrirá una nueva pestaña en Visual Studio Code si lo has configurado como tu editor de Git. Puedes eliminar cualquier comentario y escribir tus mensajes de varias líneas. Cuando guardes y cierres la pestaña, se creará tu commit.

### Cuándo hacer un commit
Una buena manera de ver un commit es como una “instantánea” de tu código en el momento en que se realizó. Esa versión de tu código hasta ese punto se guardará para que puedas volver a ella o mirarla más adelante.

Al escribir código, se considera una buena práctica hacer un commit cada vez que tienes un cambio significativo en el código. Esto creará una línea de tiempo de tu progreso y mostrará que tu código final no apareció de la nada.

En otras palabras, haz un commit si logras que un pedazo de código funcione como quieres, corrige un error tipográfico o arreglas un bug. A medida que ganes experiencia, desarrollarás una mejor percepción de lo que debería ser commitido.

Llegará un momento en que estés trabajando en un proyecto y finalmente consigas que algo esté justo como lo querías (¡este sería un buen momento para hacer un commit!), y tal vez 30 segundos a unos días después, se rompe. No tienes idea de lo que cambiaste, todo parece estar igual y no recuerdas haber editado esa línea, pero, desafortunadamente, ya no funciona como querías. Podrías revisar tu historial de commits y revertir tu código a la última commit que hiciste cuando esa parte funcionaba, o volver y ver cómo lucía tu código en ese momento.

### Tarea
Este artículo, [Cómo Escribir un Mensaje de Commit en Git](https://example.com), cubre todos los aspectos principales sobre cómo escribir buenos mensajes de commit. El artículo completo es excelente e informativo, pero la parte más importante es “Las siete reglas de un gran mensaje de commit”.

### Consejos y cosas a recordar
- Usar VSCode como tu editor de texto (deberías haberlo configurado en la sección de Fundamentos de Git) te permitirá hacer mensajes de commit de múltiples líneas fácilmente, ver la longitud de caracteres de cada línea y usar extensiones de corrección ortográfica en VSCode para asegurarte de que tu ortografía sea correcta.
- Utiliza voz activa: “Arreglar generador de tarjetas”.
- Evita mensajes de commit vagos como “guardado” o “actualizado”.
- ¡Commit temprano y a menudo!

### Revisión de conocimientos
Las siguientes preguntas son una oportunidad para reflexionar sobre temas clave en esta lección. Si no puedes responder a una pregunta, haz clic en ella para revisar el material, pero ten en cuenta que no se espera que memorices o domines este conocimiento.

1. ¿Cuáles son dos beneficios de tener mensajes de commit bien escritos y un buen historial de commits?
2. ¿Cuántos caracteres debería tener la línea de asunto de tu mensaje de commit?

### Recursos adicionales
Esta sección contiene enlaces útiles a contenido relacionado. No es obligatorio, así que considéralo suplementario.

- Una forma de formular mensajes de commit con mucha información es seguir una plantilla. [Commits Convencionales](https://example.com) es una de las muchas plantillas de mensajes de commit que puedes explorar.
- Explora este increíble video tutorial sobre [Commits Convencionales](https://example.com). El video muestra la plantilla de Commits Convencionales del recurso anterior. También menciona la creación de versiones y muestra el uso de algo llamado “Yarn”. Estas dos partes están fuera del alcance de esta parte del curso, así que no te preocupes por ellas y concéntrate en la plantilla de commit.

---

## ¿Qué es exactamente un Mensaje de Commit?
Un mensaje de commit es un texto descriptivo que se agrega por el desarrollador que hizo el commit en el objeto de commit.

### ¿Por qué deberías escribir buenos Mensajes de Commit?
Existen varios usos para los mensajes de commit:

- Los futuros lectores no tendrán problemas para entender qué cambió y por qué cambió.
- Facilitar deshacer ciertas modificaciones.
- Hacer cambios en las notas de la versión.

Cada uno de estos casos de uso requiere un estilo de mensaje de commit consistente.

### Opciones de Commit
- `-m` (para agregar el mensaje de commit)  
  ```bash
  git commit -m "tu mensaje de commit aquí"
  ```
- `-a` o `--all` (agrega y commit archivos rastreados con un solo comando)  
  ```bash
  git commit -a -m "tu mensaje de commit aquí"
  ```
- `--amend` (te permite modificar y agregar cambios al commit más reciente)  
  ```bash
  git commit --amend
  ```
**Nota:** Es excelente usar `--amend` para limpiar commits locales, y una vez que termines, puedes enviar la versión actualizada a un repositorio compartido. Sin embargo, es mejor evitar cambiar commits que ya se han hecho públicos.

### Cómo escribir buenos mensajes de commit
Aquí hay una gran plantilla para un buen mensaje de commit.

```
[opcional Ticket-Id] <tipo>[alcance opcional]: <descripción>

[cuerpo opcional]
```
Ejemplos:
```
(JIRA-231) feat (dashboard): agregar botón de cierre de sesión
```
o
```
build: actualizar versión
```
o
```
(JIRA-333) fix (perfil): commit de prueba
```

### Cambio IMPORTANTE
Para mostrar cómo agregar un cuerpo en el commit, el tipo de commit puede ser:
- `feat:` Commits, que agregan una nueva característica.
- `fix:` Commits, que corrigen un error.
- `refactor:` Commits, que reescriben/reestructuran tu código, sin cambiar ningún comportamiento.
- `perf:` Commits, que son commits de refactorización especiales que mejoran el rendimiento.
- `style:` Commits, que no afectan el significado (espacios en blanco, formato, puntos y coma faltantes, etc).
- `test:` Commits, que agregan pruebas falt

antes o corrigen pruebas existentes.
- `chore:` Commits, que no afectan el comportamiento ni son partes importantes del proyecto.

### Reglas para buenos mensajes de commit
- Se debe utilizar el imperativo.
- El mensaje debe ser breve pero descriptivo, el primer bloque debe tener un máximo de 50 caracteres.
- Se debe usar una línea en blanco para separar el resumen del cuerpo.
- El cuerpo debe tener un máximo de 72 caracteres por línea.

---

# Convenciones de Nomenclatura para Ramas de Git — una Guía Práctica

## Introducción

Git es un sistema de control de versiones distribuido que permite a los desarrolladores de software hacer seguimiento de los cambios en su código a lo largo del tiempo. Un aspecto crucial del uso efectivo de Git es la correcta utilización y nombramiento de las ramas. Una rama en Git es, esencialmente, un conjunto único de cambios en el código con un nombre único.

Imaginemos que estamos construyendo una casa (nuestro proyecto de software). Cada habitación de la casa representa una funcionalidad diferente (una rama), y es importante que cada habitación tenga un nombre claro que refleje su propósito.

## Reglas Básicas

1. **Minúsculas y Separadas por Guiones**: Mantén las nombres de las ramas en minúsculas y usa guiones para separar las palabras. Por ejemplo, `feature/nueva-login` o `bugfix/estilo-cabecera`.
2. **Caracteres Alfanuméricos**: Usa solo caracteres alfanuméricos (a-z, 0-9) y guiones. Evita puntuaciones, espacios, guiones bajos o cualquier carácter no alfanumérico.
3. **Sin Guiones Continuos**: No utilices guiones continuos. Por ejemplo, `feature--nueva-login` puede ser confuso y difícil de leer.
4. **Sin Guiones Finales**: No termines tu nombre de rama con un guion. Por ejemplo, `feature-nueva-login-` no es una buena práctica.
5. **Descriptivo**: El nombre debe ser descriptivo y conciso, idealmente reflejando el trabajo realizado en la rama.

## Prefijos de Ramas

Usar prefijos en los nombres de las ramas ayuda a identificar rápidamente el propósito de las ramas. Aquí hay algunos tipos comunes de ramas con sus correspondientes prefijos:

- **Ramas de Funcionalidad (Feature)**: Se utilizan para desarrollar nuevas características. Usa el prefijo `feature/`. Ejemplo: `feature/sistema-login`.
- **Ramas de Corrección de Errores (Bugfix)**: Se utilizan para corregir errores en el código. Usa el prefijo `bugfix/`. Ejemplo: `bugfix/estilo-cabecera`.
- **Ramas de Hotfix**: Se crean directamente desde la rama de producción para solucionar errores críticos en el entorno de producción. Usa el prefijo `hotfix/`. Ejemplo: `hotfix/problema-seguridad-critico`.
- **Ramas de Release**: Se utilizan para preparar un nuevo lanzamiento de producción. Permiten los últimos retoques. Usa el prefijo `release/`. Ejemplo: `release/v1.0.1`.
- **Ramas de Documentación**: Se utilizan para escribir, actualizar o corregir la documentación. Usa el prefijo `docs/`. Ejemplo: `docs/puntos-api`.

## Inclusión de Números de Tickets de Jira

En algunos flujos de trabajo, especialmente en equipos más grandes, es común incluir el número de ticket de una herramienta de gestión de proyectos como Jira en el nombre de la rama. Esto facilita el seguimiento del trabajo realizado en un ticket específico. Por ejemplo, si estás trabajando en un ticket numerado “T-123” para agregar un nuevo sistema de inicio de sesión, el nombre de la rama podría ser `feature/T-123-nuevo-sistema-login`.

## Ejemplos de Nombres de Ramas

Aquí tienes algunos ejemplos de buenos nombres de ramas que siguen las convenciones anteriores:

- `feature/T-456-autenticacion-usuario`
- `bugfix/T-789-correccion-estilo-cabecera`
- `hotfix/T-321-parche-seguridad`
- `release/v2.0.1`
- `docs/T-654-actualizar-readme`

## Conclusión

Las convenciones de nomenclatura de ramas en Git, aunque no son impuestas por el sistema mismo, son cruciales para mantener una base de código limpia y comprensible, especialmente cuando se trabaja en equipo. Siguiendo estas convenciones, puedes asegurarte de que tus ramas sean fácilmente identificables y que tu flujo de trabajo sea más eficiente.

---

# Mejores Prácticas para Pull Requests

Las pull requests (PR) son una parte esencial del trabajo en equipo en Git. Seguir mejores prácticas puede mejorar la consistencia y calidad de las PR y sus revisiones.

## Mejores Prácticas para Crear Pull Requests

1. **Escribe PRs Pequeños**: Apunta a crear pull requests pequeñas y enfocadas que cumplan un solo propósito. Las PR más pequeñas son más fáciles y rápidas de revisar y fusionar, dejan menos margen para introducir errores y proporcionan un historial de cambios más claro.

   **Analogía**: Es como enviar un paquete pequeño en lugar de una caja enorme llena de cosas; es más fácil para el destinatario revisar y entender lo que contiene.

2. **Revisa tu Propia PR Primero**: Revisa, compila y prueba tu propia pull request antes de enviarla. Esto te permitirá detectar errores o errores tipográficos que puedes haber pasado por alto.

3. **Proporciona Contexto y Orientación**: Escribe títulos y descripciones claras para tus pull requests para que los revisores puedan entender rápidamente qué hace la PR. En el cuerpo de la PR, incluye:

   - El propósito de la pull request.
   - Un resumen de lo que cambió.
   - Enlaces a cualquier contexto adicional, como problemas de seguimiento o conversaciones anteriores.

   **Analogía**: Es como entregar un manual junto con un nuevo electrodoméstico; ayuda a los demás a entender cómo usarlo correctamente.

4. **Si Tu PR Incluye Cambios en Múltiples Archivos, Proporciona Orientación**: Indica a los revisores el orden en el que deben revisar los archivos. Recomienda por dónde comenzar y cómo proceder con la revisión.

## Mejores Prácticas para Gestionar Pull Requests

1. **Usa Plantillas de Pull Request**: Las plantillas de PR te permiten personalizar y estandarizar la información que te gustaría que se incluya cuando alguien crea una PR en tu repositorio.

   **Analogía**: Es como tener un formulario que los empleados deben llenar cuando solicitan tiempo libre; ayuda a que la información necesaria sea consistente.

2. **Define Propietarios de Código (Code Owners)**: Puedes asegurarte de que personas específicas revisen siempre los cambios en ciertos códigos o archivos en tu repositorio. Por ejemplo, puede que quieras que un redactor técnico de tu equipo revise siempre los cambios en el directorio de documentación.

3. **Usa Ramas Protegidas**: Puedes usar ramas protegidas para evitar que se fusionen pull requests en ramas importantes, como `main`, hasta que se cumplan ciertas condiciones. Por ejemplo, puedes requerir que las pruebas de CI pasen o que se realice una revisión aprobada.

4. **Usa Reglas de Push**: Con las reglas de push, puedes bloquear las inserciones en un repositorio privado o interno y en toda su red de bifurcaciones en función de las extensiones de archivo, longitudes de rutas de archivo y tamaños de archivos.

5. **Usa Herramientas Automatizadas para Revisar el Estilo del Código**: Utiliza herramientas automatizadas, como linters, en las pull requests de tu repositorio para mantener un estilo consistente y hacer que el código sea más comprensible.

   **Analogía**: Piensa en un corrector ortográfico que revisa un documento; te ayuda a centrarte en el contenido en lugar de en errores menores.

## Conclusión

Siguiendo estas mejores prácticas, puedes mejorar la calidad de tus pull requests y hacer que el proceso de revisión sea más fluido y eficiente. La colaboración efectiva en equipo es clave para el éxito en el desarrollo de software, y estas prácticas ayudarán a lograrlo.

---

# Una guía práctica para mejores y más rápidas revisiones de código

> "Una revisión de código es un diálogo, pero también es una crítica del trabajo de una persona, y tanto el revisor como el autor deben tener en cuenta la psicología de la propiedad y la crítica. Algunas de las cosas más valiosas que surgen durante la revisión de código son cosas sobre las que diferentes desarrolladores pueden estar razonablemente en desacuerdo, y discutir tales cosas es exactamente cómo aprendemos e innovamos." — Alexandra Hill, *The Art of Giving and Receiving Code Reviews (Gracefully)*

## Descargo de responsabilidad

Toda la información proporcionada ha sido recopilada y adaptada de las referencias citadas al final del documento. Las pautas están ilustradas con mis propios ejemplos, fruto de mi experiencia personal escribiendo y revisando código. Muchas gracias a todas las fuentes de información y colaboradores.

## 📔 Consideraciones

- Una revisión de código es un diálogo y, como tal, siempre debe realizarse de manera respetuosa y constructiva.
- Muchas decisiones de programación son opiniones. Una revisión de código abre una conversación sobre los compromisos para llegar a una resolución que satisfaga a todos.
- Una revisión de código es una forma de comunicación asincrónica, por lo que se pierde mucho contexto (como el lenguaje corporal y la oportunidad de interacciones).
- Para los autores y revisores, una revisión de código es una herramienta colaborativa para la difusión del conocimiento y la mejora de la calidad del código.

## 📔 Pautas

### Para ambos, autores y revisores

- **Sé respetuoso / Pregunta - Explica - Sugiere**  
  La base de una buena revisión es el respeto mutuo. Evitemos el uso de imperativos o juicios. Preguntemos y expliquemos nuestras perspectivas.

- **Detén la "hemorragia" de respuestas / Ofrece hablar en persona**  
  Si la discusión se complica, sugiere una conversación cara a cara para aclarar malentendidos.

- **Ofrece ánimo y apreciación / Da retroalimentación positiva**  
  No olvidemos que una buena práctica también merece reconocimiento. Un simple "¡bien hecho!" puede hacer maravillas.

- **Acuerda un estilo de codificación / Automatiza**  
  Es esencial establecer un estilo de codificación compartido y utilizar herramientas automáticas como formateadores de código y linters.

### Para los autores

- **Y el primer revisor eres... ¡tú! / Evalúa tu código**  
  Antes de que otros revisen tu PR, tómate un tiempo para revisarlo tú mismo. A veces, un vistazo desde fuera de tu IDE revela errores o inconsistencias.

- **Sé proactivo / Proporciona contexto**  
  Si tu PR es complejo, proporciona un comentario general que explique su propósito y los cambios realizados.

- **Espera la luz verde**  
  Ahorra tiempo: si tu pipeline CI/CD tiene una etapa de pruebas, espera a que todas las pruebas pasen antes de invitar a otros a revisar.

- **Elige tu audiencia**  
  Considera quién debe ver los cambios y quién puede ofrecerte la mejor retroalimentación.

- **Elige el número correcto de revisores**  
  Un grupo demasiado grande puede llevar a comentarios contradictorios; comienza con un núcleo y luego expande.

- **Mantén los PR pequeños / Divide y conquistarás**  
  Los PR más pequeños son más fáciles de revisar y proporcionan retroalimentación más rápida y valiosa.

- **Roma no se construyó en un día / Crea nuevas tareas**  
  Si surgen necesidades de refactorización durante la revisión, crea una nueva tarea y vincúlala a la revisión.

- **No lo tomes como algo personal / Mantén la mente abierta**  
  Recuerda que el objetivo es mejorar el código, no criticar a la persona.

- **Aclara primero el código / Ayuda a futuros desarrolladores**  
  Si un revisor no entiende algo, tu respuesta debe ser aclarar el código.

- **Deja este mundo un poco mejor de lo que lo encontraste / La regla del boy scout**  
  Haz pequeñas mejoras en el código, incluso si no son parte de tu PR.

- **Responde todos los comentarios / Escribe el final de la historia**  
  Responde a todos los comentarios antes de cerrar la revisión para mantener el diálogo claro y completo.

- **Practica la atención plena / Amor**  
  Recuerda que el código puede afectar a muchas personas. Escribe código con gratitud y amor.

### 👓 Para los revisores

- **Empatiza / La otra persona eres tú**  
  Considera el impacto de tus palabras. Escribe comentarios útiles y amables.

- **Evita la propiedad selectiva / ¡Es nuestro código!**  
  Usa un lenguaje inclusivo; en lugar de "tu" o "mío", utiliza "nuestro".

- **Proporciona referencias**  
  No asumas que el autor sabe de qué hablas; apóyate en ejemplos o documentación.

- **Busca la perspectiva del autor / Siempre aprendemos**  
  Intenta entender por qué el autor tomó ciertas decisiones; pueden tener una buena razón.

- **No seas un guardián / Las mejoras tienen un umbral**  
  Equilibra la calidad del código y la felicidad del desarrollador; no exijas cambios interminables.

- **Asegura la mejor calidad de revisión**  
  Si no te sientes calificado para revisar, invita a alguien que lo esté.

## ¿Qué buscar?

Examina cada línea de código y asegúrate de entender lo que hace, prestando especial atención a:

- **Diseño**: ¿Las interacciones tienen sentido? 
- **Funcionalidad**: ¿El código hace lo que se pretendía?
- **Complejidad**: ¿Es fácil de entender?
- **Pruebas**: ¿Hay pruebas unitarias adecuadas?
- **Nombres**: ¿Los nombres son claros y descriptivos?
- **Comentarios**: ¿Son útiles y explican el "por qué" y el "qué"?
- **Consistencia**: ¿El código sigue las convenciones del proyecto?

---

# Guía para Convertirse en Frontend Developer

## Introducción a las Revisiones de Código

Aprende sobre las revisiones de código y obtén información sobre cómo son esenciales para aumentar la calidad del código. Ver cómo las herramientas de revisión de código, incluidas las impulsadas por IA, ayudan a los equipos de desarrollo a agilizar el proceso de revisión de código, identificar problemas y ayudar a los desarrolladores a entregar un software excelente más rápido.

### ¿Qué es una Revisión de Código?

Una revisión de código es un proceso donde uno o más desarrolladores revisan el código que otro desarrollador escribió. Durante la revisión, los desarrolladores evalúan el código para asegurarse de que esté listo para fusionarse en la base de código. Para garantizar la calidad, debe haber al menos un revisor de código que no participó en la redacción del código.

> **Analogía:** Piensa en la revisión de código como en la revisión de un ensayo escolar. Antes de entregarlo al profesor, un compañero lo lee para asegurarse de que no haya errores gramaticales y que las ideas se expresen claramente. Esto ayuda a mejorar la calidad del trabajo antes de que sea evaluado.

### Propósito de una Revisión de Código

El propósito de una revisión de código en el desarrollo de software es ayudar a garantizar que el código cumpla con los estándares y requisitos de la organización, sea de alta calidad y sea mantenible. Además de identificar errores y fallos, las revisiones de código también promueven una cultura de aprendizaje y colaboración entre el equipo de desarrollo.

### Beneficios de las Revisiones de Código

También conocidas como revisiones entre pares, las revisiones de código ayudan a los equipos de desarrollo a:

- **Aumentar la calidad del código**: Identificando defectos y problemas, como vulnerabilidades de seguridad y problemas de rendimiento, antes de fusionar el código en la rama principal.
- **Asegurar el cumplimiento de estándares**: Verificando que el código cumpla con las regulaciones y el estilo de código del equipo.
- **Ahorrar tiempo y dinero**: Detectando problemas temprano en el proceso de desarrollo, antes de que se vuelvan más complejos y costosos de solucionar.
- **Fomentar la colaboración**: Proporcionando un foro para discutir el código, hacer preguntas, compartir ideas y aprender unos de otros.
- **Asegurar la mantenibilidad**: Identificando problemas de mantenimiento del software y sugiriendo mejoras.

### Desafíos de las Revisiones de Código

Aunque muchos equipos de desarrollo realizan revisiones de código con éxito, existen algunos desafíos. Las revisiones pueden ser:

- **Que consumen tiempo**: Especialmente si la base de código es grande. Los revisores necesitan dedicar tiempo a leer y entender el código.
- **Subjetivas**: Ya que diferentes revisores pueden tener opiniones distintas sobre lo que constituye un buen código. La retroalimentación negativa puede generar conflictos.
- **Costosas**: Especialmente si los desarrolladores revisan el código manualmente sin herramientas de revisión de código.

### Proceso de Revisión de Código

Las revisiones de código generalmente tienen lugar antes de la fase de prueba en el ciclo de vida del desarrollo de software. Los pasos comunes en el proceso de revisión de código incluyen:

1. **Preparar el código**: El autor del código lo prepara para la revisión asegurándose de que esté completo, bien documentado y cumpla con los estándares de codificación.
2. **Solicitar revisiones entre pares**: El autor envía el código para revisión a uno o más revisores.
3. **Revisar el código**: Los revisores examinan el código, señalan errores y sugieren mejoras, normalmente a través de comentarios.
4. **Discutir comentarios**: El autor y los revisores discuten los comentarios dejados.
5. **Aprobar el código**: Después de abordar todos los comentarios, los revisores aprueban el código y se fusiona en la base de código.

### Tipos de Revisiones de Código

Las prácticas de revisión de código varían según el tamaño del equipo de desarrollo y las herramientas que utilicen. Algunos tipos incluyen:

- **Revisiones "over-the-shoulder"**: Donde el revisor y el autor revisan el código juntos en pantalla.
- **Programación en pareja**: Donde dos desarrolladores trabajan juntos, uno escribiendo el código y el otro revisándolo en tiempo real.
- **Revisiones asincrónicas**: Donde los revisores revisan el código de forma independiente a su propio ritmo.
- **Revisiones de QA**: Incluyendo miembros del equipo de aseguramiento de calidad.
- **Revisiones asistidas por herramientas**: Donde se utilizan herramientas de revisión de código para mejorar la calidad.

### Herramientas de Revisión de Código

Existen varias herramientas de revisión de código disponibles que ayudan a los equipos a agilizar el proceso de revisión. Por ejemplo, las herramientas de revisión de código de GitHub incluyen:

- **Pull requests**: Para proponer nuevas características o cambios.
- **Herramientas de discusión de código**: Para permitir que los desarrolladores hagan preguntas sobre la estructura y dejen comentarios detallados.

### Llevar la Revisión de Código al Siguiente Nivel con IA

Las herramientas impulsadas por IA ayudan a automatizar y acelerar los procesos de revisión de código al analizar el código y detectar problemas. Por ejemplo, GitHub Copilot sugiere completaciones de código y ayuda a los equipos a escribir mejores descripciones de pull requests.

### Resumen

Las revisiones de código identifican defectos y problemas en el código. Son una parte crítica del desarrollo colaborativo porque ayudan a los desarrolladores a fusionar el código de la más alta calidad en la base de código. Además de mejorar la calidad del código, fomentan el aprendizaje y la colaboración entre los miembros del equipo.

---

## Estableciendo Pautas para los Contribuyentes del Repositorio

### Acerca de las Pautas de Contribución

Para ayudar a los contribuyentes de tu proyecto a hacer un buen trabajo, puedes agregar un archivo con pautas de contribución en la raíz de tu repositorio. Cuando alguien abre una pull request o crea un problema, verá un enlace a ese archivo.

### Agregando un Archivo CONTRIBUTING

1. Navega a la página principal del repositorio en GitHub.
2. Selecciona el menú desplegable "Add file" y luego haz clic en "Create new file".
3. Decide si almacenar tus pautas en la raíz del repositorio, en la carpeta docs o en .github.
4. En el campo del nombre del archivo, escribe "CONTRIBUTING".
5. Agrega las pautas de contribución, que pueden incluir pasos para crear buenos problemas o pull requests, enlaces a documentación externa y expectativas de comportamiento.

### Ejemplos de Pautas de Contribución

Si te falta inspiración, aquí hay algunos ejemplos de pautas de contribución:

- [Pautas de contribución de GitHub Docs](https://github.com/github/docs/blob/main/CONTRIBUTING.md)
- [Pautas de contribución de Ruby on Rails](https://github.com/rails/rails/blob/main/CONTRIBUTING.md)
- [Pautas de contribución del Gobierno Abierto](https://github.com/opengov/CONTRIBUTING.md)

---

# Contribuciones al Proyecto

¡Hola, contribuidor! Nos alegra que desees colaborar con nuestro proyecto. Aquí tienes algunas pautas que te ayudarán a empezar:

1. **Formato del Código**: Asegúrate de que tu código siga las convenciones de estilo definidas en el proyecto.
2. **Pruebas**: Antes de enviar tus cambios, asegúrate de que todas las pruebas se ejecuten correctamente.
3. **Enviar Parches**: Usa un Pull Request para enviar tus cambios. Explica brevemente qué hace tu contribución y por qué es necesaria.

¡Gracias por tu interés en mejorar nuestro proyecto!
```

De un punto de vista de mantenedor, este documento comunica de manera sucinta cómo colaborar mejor. Y para un contribuyente, una rápida verificación de este archivo verifica que su envío siga las pautas del mantenedor.

## Contribuciones Deseadas: Pregunta Dentro

Hoy hemos añadido soporte para compartir tu política preferida para contribuciones con aquellos que desean colaborar contigo en tu proyecto.

Hemos tratado de hacer esto fácil para todos. Como mantenedor, todo lo que necesitas hacer es agregar un archivo `CONTRIBUTING` (o `CONTRIBUTING.md` si estás usando Markdown) a la raíz de tu repositorio. Luego, añadiremos un enlace a tu archivo cuando un colaborador cree un Issue o abra un Pull Request.

Ahora, tan pronto como tus colaboradores empiecen a participar, pueden encontrar fácilmente las pautas que te gustaría que siguieran.

Si no ves un archivo `CONTRIBUTING` en tu proyecto favorito, abre un Pull Request y agrega uno.

---

# Do you have a readable GIT commit history?

Puede parecer que hay pocas razones para preocuparse por tu historial de git. Así me parecía a mí cuando empecé a prestarle atención, porque alguien me obligó a hacerlo 🤓.

### La importancia del historial de GIT

Imagina que tu historial de git es como el índice de un libro. Si está desorganizado, será difícil encontrar la información que necesitas. Cuando trabajas en un proyecto, llegarás a un punto en el que necesitarás tener una comprensión clara de los cambios de ti y tu equipo, su sucesión y tener que encontrar algo significativo de toda esta información. 

Algunos de los beneficios de tener un historial legible incluyen:

- Poder descifrar fácilmente el orden de los commits en tu repositorio.
- Entender más fácilmente qué y cuándo se cambió.
- Facilitar la búsqueda de commits que podrían haber introducido errores y habilitar el rollback si es necesario.
- Permitir la extracción automática de notas de lanzamiento y la creación de un changelog.
- Hacer posible desplegar cualquier commit en tu rama de desarrollo usando tu sistema CI/CD.

### Primer paso: Limpieza de commits

El primer paso que debes dar es deshacerte de los merge commits, ya que hacen muy difícil entender el orden general de los commits y comprender los cambios. Imagina que tu proyecto es como un rompecabezas; los merge commits son piezas que no encajan bien, haciendo que sea complicado ver la imagen completa.

#### Cuidado con los cambios en el historial

La mayoría de las operaciones que presentaré, como rebase y enmienda de commits, son operaciones que cambian el historial en git. Esto significa que puedes romper cosas, especialmente para tus compañeros de equipo, si las usas (incluso por error) en ramas compartidas.

¿Cómo asegurarte de que eso no suceda? Protegiendo tus ramas compartidas para que nadie pueda forzar un push en ellas.

### Pasos para llegar a un historial de commits limpio

1. **Entender el rebase** y reemplazar la obtención de cambios remotos con rebase para eliminar los merge commits en tu rama de trabajo.
2. **Usar opciones de fusión rápida o squash** al agregar tus cambios a la rama objetivo.
3. **Usar commits atómicos**: aprende a enmendar, aplastar o reestructurar tus commits.
4. **Aprender a forzar un push** 🤓.

### Rebasing tu rama de trabajo

Supongamos que ya tienes algunos commits, pero se ha realizado un cambio importante en la rama compartida que necesitas para continuar tu trabajo (o que otro miembro del equipo trabajó en el mismo archivo y tienes un conflicto al crear el Pull Request).

Tienes aquí 2 opciones:

1. **Fusionar la rama compartida en la tuya**, lo que resultará en un merge commit que contiene los cambios entre la rama remota y tus commits desde el último commit que tienes en común.
   ```bash
   git merge origin/shared_branch
   ```

2. **Rebase tus commits** en la parte superior de la rama remota. Esto toma el último commit en tu `shared_branch` y aplica, uno por uno, los commits de tu rama de trabajo. Si tienes conflictos en alguno de los commits, necesitarás resolverlos y luego continuar el rebase.
   ```bash
   git fetch
   git rebase origin/shared_branch
   ```

Si tu rama local ya se había empujado a remoto, necesitarás forzar el push después del rebase.

```bash
git push -f
```

Es muy importante entender que el force push sobrescribirá el estado remoto con el estado local. Asegúrate de verificar tus cambios y de que el rebase haya funcionado bien antes de hacer un force push. No podrás revertir al estado anterior después de hacer un force push.

### Limpiemos las cosas

Este sería el escenario común con el que estoy seguro te puedes relacionar: estás trabajando en terminar tus tareas en una rama separada mientras el resto del equipo hace lo mismo. La historia de la rama rebased es mucho más fácil de entender, leer y la relación entre las ramas puede captarse en un segundo.

### Fusionando ramas de trabajo en tu rama compartida

Ahora has creado tu Pull Request y la revisión ha pasado, y deseas fusionarlo en la rama compartida. Si estás utilizando Bitbucket o GitHub, ambas plataformas tienen opciones sobre cómo debería verse el commit en la rama compartida.

Si deseas hacerlo manualmente, aquí están los comandos de git para ello:

```bash
git merge --squash working_branch
git commit -m "Squashed commit from working_branch" // mensaje de commit significativo aquí
```

---

## Sobre los archivos CITATION

Puedes agregar un archivo CITATION a tu repositorio para ayudar a los usuarios a citar correctamente tu software.

### En este artículo

- Acerca de los archivos CITATION
- Citar algo que no sea software
- Citar un conjunto de datos
- Otros archivos de cita
- Formatos de cita

### Acerca de los archivos CITATION

Al igual que un maestro en un salón de clases que proporciona una guía sobre cómo citar sus obras, puedes agregar un archivo `CITATION.cff` en la raíz de tu repositorio para informar a otros cómo te gustaría que citen tu trabajo. Este formato de archivo es texto plano y contiene información de cita que es legible tanto para humanos como para máquinas.

**Ejemplo de archivo CITATION.cff:**

```
cff-version: 1.2.0
message: "Si usas este software, por favor cítalo como se indica a continuación."
authors:
- family-names: "Lisa"
  given-names: "Mona"
  orcid: "https://orcid.org/0000-0000-0000-0000"
- family-names: "Bot"
  given-names: "Hew"
  orcid: "https://orcid.org/0000-0000-0000-0000"
title: "Mi Software de Investigación"
version: 2.0.4
doi: 10.5281/zenodo.1234
date-released: 2017-12-18
url: "https://github.com/github-linguist/linguist"
```

Cuando agregas un archivo `CITATION.cff` a la rama predeterminada de tu repositorio, se agrega automáticamente un enlace a la página de inicio del repositorio en la barra lateral derecha, con la etiqueta "Cita este repositorio". Esto facilita que otros usuarios citen tu proyecto de software, utilizando la información que has proporcionado.

### Citar algo que no sea software

Si prefieres que la información de cita de GitHub enlace a otro recurso, como un artículo de investigación, puedes usar la opción de cita preferida en CFF con los siguientes tipos.

**Ejemplo de archivo CITATION.cff extendido que describe el software, pero vinculando a un artículo de investigación como cita preferida:**

```
cff-version: 1.2.0
message: "Si usas este software, por favor cítalo como se indica a continuación."
authors:
- family-names: "Lisa"
  given-names: "Mona"
  orcid: "https://orcid.org/0000-0000-0000-0000"
- family-names: "Bot"
  given-names: "Hew"
  orcid: "https://orcid.org/0000-0000-0000-0000"
title: "Mi Software de Investigación"
version: 2.0.4
doi: 10.5281/zenodo.1234
date-released: 2017-12-18
url: "https://github.com/github-linguist/linguist"
preferred-citation:
  type: article
  authors:
  - family-names: "Lisa"
    given-names: "Mona"
    orcid: "https://orcid.org/0000-0000-0000-0000"
  - family-names: "Bot"
    given-names: "Hew"
    orcid: "https://orcid.org/0000-0000-0000-0000"
  doi: "10.0000/00000"
  journal: "Título del Journal"
  month: 9
  start: 1 # Número de la primera página
  end: 10 # Número de la última página
  title: "Mi increíble software de investigación"
  issue: 1
  volume: 1
  year: 2021
```

### Citar un conjunto de datos

Si tu repositorio contiene un conjunto de datos, puedes establecer `type: dataset` en la parte superior de tu archivo CITATION.cff para producir una cadena de cita de datos en el aviso de cita de GitHub.

### Otros archivos de cita

La función de cita de GitHub también detectará algunos archivos adicionales que suelen ser utilizados por comunidades y proyectos para describir cómo les gustaría que se cite su trabajo.

Nota: Estos nombres de archivos no son sensibles a mayúsculas y deben estar en la raíz del repositorio.

- CITATION
- CITATIONS
- CITATION.bib
- CITATIONS.bib
- CITATION.md
- CITATIONS.md

### Formatos de cita

Actualmente, admitimos los formatos de archivo APA y BibTeX.

¿Buscas formatos de cita adicionales? GitHub utiliza una biblioteca Ruby para analizar los archivos `CITATION.cff`. Puedes solicitar formatos adicionales en el repositorio ruby-cff o contribuir con ellos tú mismo.

---

## Acerca de los wikis

Puedes alojar documentación para tu repositorio en un wiki, para que otros puedan usar y contribuir a tu proyecto.

### ¿Quién puede usar esta función?

Los wikis están disponibles en repositorios públicos con GitHub Free y GitHub Free para organizaciones, y en repositorios públicos y privados con GitHub Pro, GitHub Team, GitHub Enterprise Cloud y GitHub Enterprise Server. Para más información, consulta los "Planes de GitHub."

Cada repositorio en GitHub viene equipado con una sección para alojar documentación, llamada wiki. Puedes usar el wiki de tu repositorio para compartir contenido extenso sobre tu proyecto, como cómo usarlo, cómo lo diseñaste o sus principios fundamentales.

Con los wikis, puedes escribir contenido como en cualquier otro lugar de GitHub. Puedes usar Markdown para agregar expresiones matemáticas renderizadas, diagramas, mapas y modelos 3D a tu wiki.

Si creas un wiki en un repositorio público, el wiki estará disponible para el público. Si lo creas en un repositorio privado, solo las personas con acceso al repositorio podrán acceder al wiki.

### Nota:

- Los motores de búsqueda solo indexarán wikis con 500 estrellas o más que configures para prevenir la edición pública.
- Si necesitas que los motores de búsqueda indexen tu contenido, puedes usar GitHub Pages en un repositorio público.

---

## Acerca de los archivos README

Puedes agregar un archivo README a tu repositorio para comunicar información importante sobre tu proyecto.

### En este artículo

- Acerca de los archivos README
- Tabla de contenido autogenerada para archivos README
- Enlaces a secciones en archivos README y páginas de blob
- Enlaces relativos y rutas de imágenes en archivos README
- Wikis
- Lectura adicional

### Acerca de los archivos README

Un archivo README es como el cartel de bienvenida en una tienda; comunica a los visitantes qué pueden encontrar dentro. Un README, junto con una licencia del repositorio, un archivo de cita, directrices de contribución y un código de conducta, comunica las expectativas para tu proyecto y te ayuda a gestionar las contribuciones.

Un README suele ser el primer elemento que un visitante verá al visitar tu repositorio. Los archivos README suelen incluir información sobre:

- Qué hace el proyecto
- Por qué es útil
- Cómo los usuarios pueden comenzar con el proyecto
- Dónde pueden obtener ayuda
- Quién mantiene y contribuye al proyecto

Si colocas tu archivo README en el directorio oculto `.github`, en la raíz o en el directorio `docs`, GitHub lo reconocerá y lo mostrará automáticamente a los visitantes del repositorio.

### Tabla de contenido autogenerada para archivos README

GitHub generará automáticamente una tabla de contenido para cualquier archivo Markdown en un repositorio, incluyendo los archivos README. Puedes ver la tabla de contenido de un archivo README haciendo clic en el ícono de menú en la esquina superior izquierda de la página renderizada.

---

### Enlaces relativos y rutas de imágenes en archivos README

Puedes definir enlaces relativos y rutas de imágenes en tus archivos renderizados para ayudar a los lectores a navegar a otros archivos en tu repositorio. 

Un enlace relativo es un enlace que es relativo al archivo actual. Por ejemplo, si tienes un archivo README en la raíz de tu repositorio, y tienes otro archivo en una subcarpeta, puedes crear un enlace a él usando su ruta relativa.

---

### Conclusión

En este repositorio, no solo encontrarás información técnica sobre cómo convertirte en un frontend developer, sino también analogías sencillas para que los conceptos sean más comprensibles. ¡Explora y aprende a tu ritmo!

---

# Sintaxis Básica de Escritura y Formato en GitHub

Crea un formato sofisticado para tu prosa y código en GitHub con una sintaxis simple.

## Encabezados
Para crear un encabezado, agrega uno a seis símbolos `#` antes de tu texto de encabezado. El número de `#` que uses determinará el nivel de jerarquía y el tamaño de la tipografía del encabezado.

```markdown
# Encabezado de primer nivel
## Encabezado de segundo nivel
### Encabezado de tercer nivel
```

Cuando usas dos o más encabezados, GitHub genera automáticamente una tabla de contenidos que puedes acceder haciendo clic en el icono dentro del encabezado del archivo. Cada título de encabezado se lista en la tabla de contenidos, y puedes hacer clic en un título para navegar a la sección seleccionada.

## Estilizando texto
Puedes indicar énfasis con texto en **negrita**, _cursiva_, ~~tachado~~, subíndice o superíndice en los campos de comentarios y archivos `.md`.

| Estilo                    | Sintaxis              | Ejemplo                      | Salida                          |
|---------------------------|-----------------------|------------------------------|---------------------------------|
| Negrita                   | `** **` o `__ __`     | `**Este es texto en negrita**` | **Este es texto en negrita**   |
| Cursiva                   | `* *` o `_ _`         | `_Este texto está en cursiva_` | _Este texto está en cursiva_   |
| Tachado                   | `~~ ~~`               | `~~Este fue un texto erróneo~~` | ~~Este fue un texto erróneo~~   |
| Negrita y cursiva anidada | `** **` y `_ _`       | `**Este texto es _extremadamente_ importante**` | **Este texto es _extremadamente_ importante** |
| Todo en negrita y cursiva | `*** ***`             | `***Todo este texto es importante***` | ***Todo este texto es importante*** |
| Subíndice                 | `<sub> </sub>`        | `Este es un <sub>subíndice</sub>` | Este es un subíndice            |
| Superíndice               | `<sup> </sup>`        | `Este es un <sup>superíndice</sup>` | Este es un superíndice          |

## Citando texto
Puedes citar texto con `>`.

```markdown
Texto que no es una cita

> Texto que es una cita
```

El texto citado se indenta, con un color de tipo diferente.

## Citando código
Puedes mencionar un código o un comando dentro de una oración con comillas simples. El texto dentro de las comillas no se formateará.

```markdown
Usa `git status` para listar todos los archivos nuevos o modificados que aún no se han confirmado.
```

Para formatear un bloque de código o texto en su propio bloque distinto, utiliza tres comillas inversas.

```markdown
Algunos comandos básicos de Git son:
```
```
git status
git add
git commit
```

## Modelos de color soportados
En problemas, solicitudes de extracción y discusiones, puedes mencionar colores dentro de una oración usando comillas inversas. Un modelo de color soportado dentro de comillas invertidas mostrará una visualización del color.

```markdown
El color de fondo es `#ffffff` para el modo claro y `#000000` para el modo oscuro.
```

Aquí están los modelos de color soportados actualmente.

| Color | Sintaxis        | Ejemplo                    | Salida                           |
|-------|-----------------|----------------------------|----------------------------------|
| HEX   | `#RRGGBB`       | `#0969DA`                  | ![#0969DA](https://via.placeholder.com/15/0969DA/000000?text=+) |
| RGB   | `rgb(R,G,B)`    | `rgb(9, 105, 218)`        | ![rgb(9,105,218)](https://via.placeholder.com/15/0969DA/000000?text=+) |
| HSL   | `hsl(H,S,L)`    | `hsl(212, 92%, 45%)`      | ![hsl(212,92%,45%)](https://via.placeholder.com/15/0969DA/000000?text=+) |

## Enlaces
Puedes crear un enlace en línea envolviendo el texto del enlace entre corchetes `[ ]`, y luego envolviendo la URL entre paréntesis `( )`.

```markdown
Este sitio fue construido usando [GitHub Pages](https://pages.github.com/).
```

## Enlaces de sección
Puedes enlazar directamente a cualquier sección que tenga un encabezado. Para ver el ancla generada automáticamente en un archivo renderizado, pasa el mouse sobre el encabezado de la sección para exponer el icono y haz clic en el icono para mostrar el ancla en tu navegador.

```markdown
[Enlace al encabezado de muestra](#encabezado-de-muestra).
```

## Enlaces relativos
Puedes definir enlaces relativos y rutas de imagen en tus archivos renderizados para ayudar a los lectores a navegar a otros archivos en tu repositorio.

```markdown
[Directrices de contribución para este proyecto](docs/CONTRIBUTING.md)
```

## Anclas personalizadas
Puedes usar etiquetas de ancla HTML estándar (`<a name="nombre-ancla-única"></a>`) para crear puntos de anclaje de navegación para cualquier ubicación en el documento.

```markdown
# Encabezado de Sección

<a name="mi-punto-de-ancla-personalizado"></a>
Texto que quiero proporcionar un enlace directo, pero que no tiene su propio encabezado.
```

## Imágenes
Puedes mostrar una imagen agregando `!` y envolviendo el texto alternativo en `[ ]`. Luego, envuelve el enlace para la imagen en `()`.

```markdown
![Descripción de la imagen](https://myoctocat.com/assets/images/base-octocat.svg)
```

## Listas
Las listas pueden ser ordenadas o desordenadas. Para crear una lista desordenada, usa `*`, `+`, o `-` para iniciar un nuevo elemento de lista.

```markdown
- Elemento 1
- Elemento 2
  - Sub-elemento 2.1
  - Sub-elemento 2.2
```

Para listas ordenadas, simplemente numera los elementos.

```markdown
1. Primer elemento
2. Segundo elemento
   1. Sub-elemento 2.1
   2. Sub-elemento 2.2
```

## Listas de tareas
Puedes crear listas de tareas utilizando una sintaxis especial.

```markdown
- [ ] Tarea 1
- [x] Tarea completada
```

## Mencionando personas y equipos
Puedes mencionar a personas o equipos en comentarios usando `@`.

```markdown
@usuario o @equipo
```

## Referenciando problemas y solicitudes de extracción
Para referenciar un problema o solicitud de extracción, usa `#` seguido del número.

```markdown
Referencia al problema #123.
```

## Referenciando recursos externos
Puedes incluir enlaces a recursos externos como se mostró anteriormente.

## Subiendo activos
Puedes subir activos directamente a tus comentarios y archivos Markdown arrastrando y soltando archivos.

## Usando emojis
Puedes usar emojis simplemente escribiendo su código. Por ejemplo, `:smile:` se convierte en 😀.

## Párrafos
Los párrafos se crean dejando una línea en blanco entre bloques de texto.

## Notas al pie
Puedes agregar notas al pie de la siguiente manera:

```markdown
Este es un texto con una nota al pie.[^1]

[^1]: Esta es la nota al pie.


```

## Alertas
Puedes usar bloques de aviso con la siguiente sintaxis:

```markdown
> **Nota**: Esto es un aviso importante.
```

## Ocultando contenido con comentarios
Puedes ocultar contenido envolviendo el texto en `<!-- -->`.

```markdown
<!-- Este contenido está oculto -->
```

## Ignorando formato Markdown
Si deseas que el texto no sea procesado como Markdown, usa `\` antes del símbolo.

```markdown
\*Este texto no está en cursiva\*
```

## Deshabilitando el renderizado Markdown
Para deshabilitar el renderizado Markdown en líneas específicas, utiliza el siguiente bloque:

````markdown
~~~markdown
No se renderizará este bloque.
~~~
````