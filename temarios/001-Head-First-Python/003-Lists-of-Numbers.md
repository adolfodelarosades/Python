# Capítulo 3. Listas de números: *procesamiento de datos de listas*

<img width="744" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/62331a69-da66-408d-bbdf-a7acfa9794fb">

* “Tarea #2: Procesar los datos en el archivo”

* “Obtenga una copia de los datos del entrenador”

* “El open BIF funciona con archivos”

* "Usar open para abrir (y close) un archivo"

* "Las variables se crean dinámicamente, según sea necesario"

* “Los datos del archivo son lo que realmente quieres”

* “Tenemos los datos del nadador en el archivo”

* “Lo que debe suceder a continuación me resulta familiar”

* “El capítulo anterior está dando dividendos”

* "Convertir una time string en un time value"

* “A centésimas de segundo con Python”

* "Una revisión rápida del bucle for de Python"

* “Nos quitamos los guantes… bucles for versus bucles while”

* "¡Ahora estás navegando y haciendo grandes progresos!"

* “Conservemos una copia de las conversiones”

* "Mostrar una lista de los métodos de su lista"

* “Es hora de calcular el promedio”

* "Convierta el promedio en una time string de natación"

* “Es hora de unirlo todo”

* “¡La tarea número 2 (finalmente) supera la línea!”


**Cuanto más código escribas, mejor serás. Es así de simple.**

En este capítulo, continuará creando código Python para ayudar al entrenador. Aprenderá a **leer** datos de un **archivo** de datos proporcionado por Coach, integrando sus líneas en una **lista**, una de las **estructuras de datos** integradas más poderosas de Python. Además de crear listas a partir de los datos del archivo, también aprenderá cómo crear listas desde cero, haciendo **crecer** su lista **dinámicamente** según sea necesario. Y procesará listas utilizando una de las construcciones de bucle más populares de Python: el bucle **for**. **Convertirás** valores de un formato de datos a otro e incluso harás un nuevo mejor amigo (tu propio mejor amigo de Python **BFF**). Ya te has saciado de café y pastel, así que es hora de arremangarte y volver al trabajo.


## “Tarea #2: Procesar los datos en el archivo”

Una vez completada la Tarea n.° 1, es hora de pasar a la Tarea n.° 2. Hay un poco de trabajo por hacer pero, al igual que con las actividades del capítulo anterior, puedes abordar las cosas poco a poco como se detalla en el último capítulo:

  1️⃣ **Lea las líneas del archivo.**

  2️⃣ **Ignora la segunda línea.**

  3️⃣ **Separe la primera línea con "," para producir una lista de horas.**

  4️⃣ **Toma cada uno de los tiempos y conviértelos a un número del formato “mins:secs.hundredths (minutos: segundos.centésimas)”.**

  5️⃣ **Calcule el tiempo promedio y luego conviértalo nuevamente al formato “mins:secs.hundredths (minutos: segundos.centésimas)” (para fines de visualización).**

  6️⃣ **Muestre las variables de la Tarea n.° 1, luego la lista de tiempos y el promedio calculado de la Tarea n.° 2.**

<img width="1193" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b9773b40-5201-408e-8800-c304e34490aa">

**Em… eh… en mi café?**

Puede que tengamos un pequeño choque de culturas aquí, pero se agradece el sentimiento del entrenador.

Comencemos obteniendo una copia de los datos de este capítulo antes de sumergirnos en la subtarea (a) y aprender cómo Python lee los datos de un archivo.


## “Obtenga una copia de los datos del entrenador”

No tiene sentido aprender a leer datos de un archivo si no tienes datos con los que trabajar. Entonces, dirígete al sitio web de soporte de este libro y obtén la copia más reciente de los archivos de datos del Coach. Hay sesenta archivos de datos individuales empaquetados como un archivo ZIP. Obtenga una copia de esta URL (dentro de la carpeta capítulo02): https://github.com/headfirstpython/third

<hr>

**NOTA**

No se preocupe, esos 60 archivos de datos son pequeños, por lo que solo se necesitan unos segundos para descargar el ZIP.

<hr>

Una vez que se complete la descarga, descomprima el archivo y luego copie la carpeta de datos de natación resultante en su carpeta de Aprendizaje. Esto garantiza que el código siguiente pueda encontrar los datos ya que estarán en un lugar conocido.

Cada archivo de la carpeta ***swimdata*** contiene los tiempos registrados de los intentos de un nadador en una combinación de distancia/brazada específica. Recuerde el archivo de datos del comienzo del capítulo anterior que muestra los tiempos de Darius sub-13 en los 100 m mariposa:

<img width="1110" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4eca15a2-8033-4f6c-91b7-928493134847">

<img width="1156" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/454fe07c-2d39-4ddb-971d-d36e0122346c">

**Sí, lo hace.**

Hay un BIF llamado **open** que puede trabajar con archivos, abriéndolos para leerlos, escribirlos, agregarlos o cualquier combinación de lo anterior.

El **open** BIF es poderoso por sí solo, pero brilla cuando se combina con la declaración... em, eh... **with** de Python.

<hr>

**NOTA**

El PSL viene con una library para trabajar directamente con archivos ZIP, llamada **"zipfile"**. A pesar de esto, asumiremos que ha descomprimido el archivo manualmente, lo que nos permite trabajar con los archivos ".txt".

<hr>

## “El open BIF funciona con archivos”

Ya sea que su archivo contenga datos textuales o binarios, el **open** BIF puede abrir su archivo para leerlo, escribirlo o agregarle datos. De forma predeterminada, **open** lee desde un archivo de texto, lo cual es perfecto ya que eso es lo que quieres hacer con el archivo de datos de Darius.

Puede llamar a **open** directamente en su código, abrir un archivo con nombre, procesar sus datos y luego cerrar el archivo cuando haya terminado. Este patrón de apertura-proceso-cierre es muy común, independientemente del lenguaje de programación que utilice. De hecho, Python tiene una declaración de lenguaje que hace que trabajar con el patrón abrir-proceso-cerrar sea especialmente conveniente: la declaración **with**.

Aunque hay un poco más en la declaración **with** de lo que inicialmente parece, solo hay una cosa que necesita saber ahora mismo: si abre su archivo con, Python se encarga de cerrarlo automáticamente cuando haya terminado. independientemente de lo que suceda durante cualquier procesamiento que realice en el archivo.

<img width="1209" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/59741951-4a6a-4ebf-8414-2f5d9631009f">

**Alex:** ¿Es realmente tan importante organizar el cierre automático de mi archivo abierto?

**Sam:** Para uno o dos archivos puede que no importe. Sin embargo, a medida que su código crece, es posible que termine abriendo muchos, muchos archivos; imagine actualizar todos los archivos HTML en un sitio web grande. Cada archivo abierto implica cierta sobrecarga de memoria y la mayoría de los sistemas operativos limitan la cantidad de archivos que se pueden abrir a la vez, por lo que cerrar archivos automáticamente es realmente útil.

**Mara:** Cualquier cosa que me salve de tener que acordarme de hacer algo está bien para mí porque, créeme, siempre lo olvido…

**Alex:** Vale, estoy convencido, aunque usar la palabra **with** para abrir un archivo parece extraño.

**Sam:** La palabra **with** es una palabra clave de Python que verás utilizada en muchos contextos: no solo para usar con archivos. Lo que hace **with** es configurar un contexto dentro del cual se ejecuta su código, y el código puede tener un mecanismo de configuración y desmontaje. Para los archivos, la configuración abre el archivo y el desmontaje lo cierra.

**Mara:** Voy a utilizar **with** con otros recursos que necesito cerrar porque, como creo que ya he mencionado, siempre me estoy olvidando…

<img width="1178" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c04ac38f-6bee-4a0f-b101-00b63bde508d">


## "Usar open para abrir (y close) un archivo"

Antes de abrir un archivo, debe identificar el archivo con el que planea trabajar, generalmente proporcionando dos datos: ***el nombre del archivo y su ubicación***. Así es como los programadores de Python podrían definir constantes para estos valores:

<img width="1125" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/82f83264-8534-4a9b-81f7-98d573e29145">

Cuando vea el nombre de una variable en mayúscula, piense en **"constante"**.

Aunque anteriormente se lo denomina "constantes", ***Python no admite la noción de valores constantes***, por lo que ***es una convención dentro de la comunidad de programación de Python usar nombres de variables en MAYÚSCULAS para indicar a otros programadores que los valores son constantes (y no deben ser cambió)***. Y sí, los lectores con ojos de águila se habrán dado cuenta de que ignoramos (¡¡de manera bastante descarada!!) esta convención en el capítulo anterior con la variable **“fn”**. Este es un uso impactante de un nombre de variable en minúscula cuando debería haberse usado un nombre de constante en mayúscula. Nos salimos con la nuestra porque Python no aplica esta convención de nomenclatura, ya que no es una regla del lenguaje. Dicho esto, a partir de ahora nos aseguraremos de seguirlo.

Con sus constantes definidas, aquí está el código Python que abre el archivo, ***lee*** todos sus datos en una lista llamada (aquí explotando una imaginación sin precedentes) **`lines`** y luego cierra automáticamente el archivo:

<img width="1172" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/104d979d-db02-402a-8fc3-d8ec7179bb8b">

<img width="1073" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/6eccb333-715e-46ff-b403-7760a7d3a539">

<img width="1186" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4946d54b-9f87-47a4-9b82-f8220833a87e">

<img width="1154" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/7d4dc330-a28a-40b6-8346-90df70cf0e51">

<img width="1117" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/033f359e-12ca-484f-9b02-6fee63fc47e8">

Veamos qué sucede cuando ejecuta este código.

Para que el código que sigue funcione, se supone que ya has descargado los datos del entrenador, descomprimiendo el archivo en una carpeta llamada ***swimdata*** dentro de tu carpeta de ***Learning***. Hazlo ahora si lo olvidaste; aquí está la URL a usar (busque dentro de la carpeta capítulo02): https://github.com/headfirstpython/third

Para comenzar, cree un nuevo notebook en VS Code y asígnele el nombre **`Average.ipynb`**, guardando este último notebook en su carpeta ***Learning***. Seguir a lo largo:

<img width="1139" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/2b7437ef-511a-440b-af32-3bcf5943dfb6">

<img width="1100" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/baeb4e7e-4283-45a9-84aa-21947bc47fb5">

Aunque no hay soporte directo para la noción de constantes en Python, PSL ofrece el módulo **`enum`**, que puede ayudarle en la mayor parte del camino. Consulte los documentos de enumeración para obtener más información: https://docs.python.org/3/library/enum.html.

El PSL también ofrece alternativas a la hora de trabajar con nombres de archivos y carpetas. Si prefiere utilizar una API orientada a objetos con su sistema de archivos, consulte la library **`pathlib`** (que bien puede ser lo que busca). Nuevamente, los documentos de Python son el lugar al que puede acudir para obtener más información; consulte: https://docs.python.org/3/library/pathlib.html.

## "Las variables se crean dinámicamente, según sea necesario"

Las variables **`file`** y **`lines`** se crearon como resultado de la asignación. Aunque es fácil ver cómo surgieron las **`lines`** gracias al uso del operador de asignación (**`=`**), no está tan claro qué sucede con el archivo.


<img width="1150" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/78781f3a-7790-443d-be05-2231a2f1f916">

La palabra clave es **"as"**.

Gracias a que **`with`**, la palabra clave **`as`** toma el valor de retorno del **open** BIF y lo asigna al nombre de la variable identificada, que es **`file`** en su código. Es como si se ejecutara este código:

<img width="1089" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/ad9bee53-a77a-4f9e-9f50-b89f5f859fc8">

La palabra clave **`as`**, junto con **`with`**, hace lo mismo (y también se ve mejor).

Echemos un vistazo más de cerca a qué es un **`file`** y aprendamos un poco sobre lo que puede hacer:

<img width="1204" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/51d09856-5d5c-44ce-8301-00cd59973e81">


## “Los datos del archivo son lo que realmente quieres”

El objeto file es simplemente un medio para un fin: cargar las líneas del archivo en la variable **`lines`**. Entonces, ¿qué son las **`lines`** y qué puedes hacer con ellas?

<img width="1143" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/1ce8d421-baf8-45f9-86d8-07a01518bf1d">

**No olvide presionar Shift+Enter para ejecutar celdas de código.**

Echemos un vistazo a las **`lines`** que contiene:

<img width="1177" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/dc5caba4-3c4a-4933-b168-cd09a5b2febc">

Al igual que los arrays, las lists de Python entienden la conocida notación de corchetes, por lo que es fácil llegar al primer elemento de la lista:

**0 se refiere al primer elemento, 1 al segundo, 2 al tercero, y así sucesivamente…**

<img width="1175" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/cc40c042-cd35-4dad-af97-3da30f383b52">

**Sí, con un poco de ayuda de “with”.**

A pesar de ser un bloque de código de una sola línea, aquí también están sucediendo muchas cosas.

No solo se creó su lista, se asignó a su variable **`lines`** y se completó con los datos contenidos en el archivo del nadador, sino que con la sentencia **`with`** logró completar las dos primeras subtareas de la Tarea n.° 2. ¿Cuan genial es eso?

Échale un vistazo (en la página siguiente).

## “Tenemos los datos del nadador en el archivo”

Esas dos líneas de código tienen un gran impacto. Aquí están de nuevo:

<img width="1083" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4d68218a-e817-4e66-81b4-05c0c10f7cda">

El valor de los datos en el primer espacio de la lista **`lines`** es una cadena que representa los tiempos del nadador (en **`lines[0]`**):

<img width="1094" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/ecec5a6f-04f7-49a6-89a1-dd4d47198fcb">


Puede ignorar con seguridad cualquier otra cosa en el archivo (incluida esa línea en blanco adicional), ya que los datos que necesita se encuentran en el string anterior.

<img width="1230" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/04240f8a-c6e1-4ea0-b153-6134163c7a89">

**No se preocupe, entrenador, lo tenemos cubierto.**

Piense en la línea anterior como los datos sin procesar del archivo. Todavía queda algo de procesamiento por hacer, al que llegaremos pronto.

## Hagamos un balance de nuestro progreso hasta el momento

Con solo unas pocas líneas de código hasta ahora, tienes las subtareas (a) y (b) resueltas:

<img width="1028" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/2cd0165c-8e79-43f9-924e-43f6c18d9178">

La tercera subtarea no debería ser difícil para cualquiera que haya pasado algún tiempo trabajando con la tecnología de string de Python. Quiso la suerte que acabas de trabajar con el material de string del capítulo anterior, así que estás listo para intentarlo. Pero antes de pasar a esa subtarea, debemos hablar un poco sobre una parte específica de la sentencia: los dos puntos **`:`**.

**Para su información: los documentos de Python se refieren a un *"bloque de código"* como una *"suite"*.**

<hr>

**NOTA**

Creemos que esto también es extraño.

<hr>

#### Tu nuevo mejor amigo, el colon `:` de Python

Los dos puntos (**`:`**) indican que un bloque de código está a punto de comenzar. Y un bloque de código en Python finaliza cuando finaliza la sangría.

En su declaración **with**, el bloque contiene solo una línea de código, pero potencialmente podría contener cualquier cantidad de líneas de código. El código con sangría al mismo nivel que la línea de código inmediatamente anterior pertenece al mismo bloque.

El uso de **`:`** es fundamental aquí (por eso es tu nuevo mejor amigo). Como en la vida real, si olvidas a tu mejor amigo, suceden cosas malas. Si olvida los dos puntos **`:`** al final de esa línea, ¡Python se niega a ejecutar su código!

Piense en los dos puntos **`:`** y la sangría como algo que va de la mano: ***no se puede tener uno sin el otro***.


<img width="1091" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c6daca66-6ff4-45d3-a2d0-d1a742917d36">

<img width="952" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/2a68c01a-22a8-4bf2-bdbe-2aa02a24a62d">

Las rosas son rojas, las violetas son azules. No olvides los dos puntos, porque no le agradarás a Python.

## “Lo que debe suceder a continuación me resulta familiar”

Recuerde el código del final del capítulo anterior, que tomó el nombre del archivo, que era un string en la variable **`fn`**, y lo transformó en cuatro variables individuales:

<img width="964" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/df79e32b-97ae-4a8b-b748-dbde0428d6dc">

Debe hacer algo similar a lo que hace la línea de código anterior con los datos sin procesar en **`lines[0]`**:

<img width="1126" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/f14b80c8-1792-4a45-b048-7681c7a7b099">

<img width="958" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/eaa2f963-1c60-466e-8783-126c9ddbf04b">

Como se muestra en la parte superior de la última página, en el capítulo anterior, tomó un string y luego le aplicó los métodos **split** y eliminar sufijo **removesuffix** para producir los valores de datos que necesitaba a partir del nombre del archivo.

Se puede aplicar una estrategia similar a su siguiente subtarea, aunque es poco probable que necesite utilizar **removesuffix**. La cadena con la que estás trabajando tiene un carácter de nueva línea (**`\n`**) al final que no necesitas. Encuentre un método de cadena para usar en lugar de **removesuffix** para permitirle eliminar el carácter de nueva línea de la cadena. Combine la llamada al nuevo método en una cadena que incluya **split** para separar el string por **","** y produzca una nueva lista, que puede asignar a una nueva variable llamada **`times`**.

Experimente en su notebook alojado en VS Code hasta que haya escrito el código que necesita, luego use el código para asignarlo a la variable **`times`**. Proporcione el código que se le ocurrió así como el código que asigna los **`times`** en este espacio:

___________________________________________

___________________________________________

___________________________________________

<hr>

**NOTA**

Sugerencia: el “print dir” combo manbo enumera los atributos y métodos de una variable.

<hr>

<img width="1078" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4ae54867-1dcf-4b42-a6c9-2016039ddfd8">


**Sí, a ambas preguntas.**

Sí, de hecho introdujimos strings en el capítulo anterior y sí, nos concentraremos en las listas en este.

Recuerde que el método **split** produce una lista a partir de un string, que es precisamente la razón por la que necesita usarlo ahora. Si la variable **`times`** anterior no es una lista, es probable que estés haciendo algo mal.

Cuando esté listo, pase la página para ver el código que se nos ocurrió.

<img width="966" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/086c8633-efb4-4b2d-a4d1-476230d3357e">

En el capítulo anterior tomó un string y luego le aplicó los métodos **split** y **removesuffix** para producir los valores de datos que necesitaba a partir del nombre del archivo.

Se puede aplicar una estrategia similar a su siguiente subtarea, aunque es poco probable que necesite utilizar **removesuffix**. El string con el que estás trabajando tiene un carácter de nueva línea (**`\n`**) al final que no necesitas. Sabiendo esto, se le pidió que encontrara un método de string para usar en lugar de **removesuffix** para permitirle eliminar el carácter de nueva línea de la cadena. Debías combinar la llamada al nuevo método en un string que debía incluir **`split`** para separar la cadena por **","** y producir una nueva lista para asignarla a una nueva variable llamada **`times`**. Debías experimentar en tu notebook alojado en VS Code hasta que hubieras escrito el código, luego debías usar el código para asignarlo a la variable **`times`**. Debes proporcionar el código que se te ocurrió así como el código que asigna los **`times`** en este espacio:


<img width="988" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/142de99f-7f6c-410d-805f-e266d6ec5474">


Así es como se veía nuestro código en VS Code. El valor en el primer espacio de la lista **`lines`** (un string) se convierte en una lista de subcadenas. Observe cómo ha desaparecido el carácter de nueva línea y todas esas comas.

<img width="989" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4bd959a5-9ed2-41c4-b0f7-9f8b44d72255">

<hr>


## “El capítulo anterior está dando dividendos”

Con su experiencia previa trabajando con strings del capítulo anterior, esperamos que el ***Sharpen*** más reciente no haya sido demasiado agotador.

Es importante llamar a **`strip`** *antes* de **`split`**, produciendo una nueva lista a partir del valor de datos en el primer espacio de las **`lines`** (**`lines[0]`**). De hecho, su último código es muy similar al código del capítulo anterior:

<img width="973" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/92f39e11-62cf-4a13-8b17-33fc5104c4d4">

Con el resultado de su último código asignado a la variable **`times`**, ha completado la subtarea (c). Es hora de hacer otra marca de verificación.

<hr>

**NOTA**

Casi puedes saborear la limonada multivitamínica de mango, ¿no?

<hr>

<img width="1085" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4e484f73-48fa-429b-9500-75945f69bb13">

**Esos confirman que tenemos una list de strings.**

Aunque esos strings parecen times, no hay tiempos reales, son strings. Todavía tenemos que encontrar una manera de convertirlos en un valor en tiempo “real” antes de intentar realizar cualquier tipo de cálculo sobre ellos…

## "Convertir una time string en un time value"

Después de ejecutar el código de la página anterior, la variable **`times`** hace referencia a una lista de strings, que no es lo que quiere el entrenador. El entrenador necesita números.

<img width="947" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/89baea2b-982b-4341-8f92-3ff3c73c7553">

Los valores en cada uno de los espacios de la lista de **`times`** ciertamente parecen tiempos de natación, pero no lo son. Son strings. Para realizar cualquier cálculo numérico en esta lista, como calcular un promedio, estos strings deben convertirse en valores numéricos.

Echemos un vistazo más de cerca a un solo valor (el primero). Si puede idear una estrategia para convertir esta primera vez, luego puede aplicarla al resto de la lista de time strings.

<img width="1048" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/f7cd792e-40e1-4757-bec1-e81de099b456">

Suponiendo que pueda extraer los tres números que necesita de la cadena, ¿se le ocurre un cálculo que convierta el string en un valor numérico?

<hr>

**NOTA**

Hay más de una forma de hacer esto, así que no te preocupes si lo que piensas no es el mismo método que el nuestro (que se detalla en la página siguiente).

<hr>

## “Convertir el times a centésimas de segundo con Python”

Por el momento, todos los tiempos de natación son *strings*, aunque nuestro cerebro los vea como tiempos. Sin embargo, no es así para nuestras computadoras (y mucho menos para Python). Nuestros amigos digitales necesitan un poco de ayuda con la conversión, y así es como sugerimos que se pueda hacer:

<img width="999" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/5cba918b-6acb-4632-8bc0-059db97564af">

Convertir esta estrategia de conversión en código Python es notablemente sencillo. Vamos a ver.

### A centésimas de segundo con Python

Hicimos todo lo posible con ese objeto visual en la página anterior, y convertir los pasos del objeto visual a código Python es una coincidencia casi uno por uno. El código que se muestra a continuación realiza el cálculo del primer tiempo de natación tomado de su lista de **times**, con el código escrito en una sola celda en el notebook **`Average.ipynb`**.

Para ayudarlo a mantener la claridad, agregamos algunos comentarios a este código. Cuando Python ve el carácter **`#`**, ignora todo lo que sigue a **`#`** hasta el final de la línea actual. (Observe cómo VS Code muestra de manera útil los comentarios en verde).

Escribe este código en tu notebook y no te sientas culpable si decides excluir los comentarios (no te preocupes, no lo diremos). Los colocamos para hacer coincidir el código con los pasos de conversión del objeto visual de la página de vista previa.

<img width="1159" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/bab3e091-c23a-40de-ab3f-5b79caedc5d6">

<img width="1161" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/7d1911e6-6b5b-4e5e-93c0-d54bb982163b">


## "Una revisión rápida del bucle for de Python"

## “Nos quitamos los guantes… bucles for versus bucles while”

## "¡Ahora estás navegando y haciendo grandes progresos!"

## “Conservemos una copia de las conversiones”

## "Mostrar una lista de los métodos de su lista"

## “Es hora de calcular el promedio”

## "Convierta el promedio en una time string de natación"

## “Es hora de unirlo todo”

## “¡La tarea número 2 (finalmente) supera la línea!”

