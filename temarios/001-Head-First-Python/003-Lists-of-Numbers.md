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

Una vez completada la **Tarea n.° 1**, es hora de pasar a la **Tarea n.° 2**. Hay un poco de trabajo por hacer pero, al igual que con las actividades del capítulo anterior, puedes abordar las cosas poco a poco como se detalla en el último capítulo:

<img width="1004" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/323bfad3-3891-47a8-94a5-dc653182209b">

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

Como se muestra en la parte superior de la última página, en el capítulo anterior, tomó un string y luego le aplicó los métodos eliminar sufijo **removesuffix** y **split** para producir los valores de datos que necesitaba a partir del nombre del archivo.

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

En el capítulo anterior tomó un string y luego le aplicó los métodos **removesuffix** y **split** para producir los valores de datos que necesitaba a partir del nombre del archivo.

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

Con este código escrito en una celda vacía de su notebook, presione **Shift+Enter** para ejecutarlo. Aparece en pantalla el valor **8795**.

<img width="931" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a98ddb9d-68e0-4324-acc6-d5fe76def4d7">

Vale la pena tomarse un momento para considerar el cálculo realizado por este código:

<img width="946" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/df8eced4-7458-4f56-a11f-3142a15e6ec4">

Si ejecuta el código en su celda de código más reciente, produce el resultado esperado: **8795** centésimas de segundo, por lo que el cálculo anterior es correcto.

Ahora, es posible reescribir el código anterior de la siguiente manera (tenga en cuenta la ausencia de algunos de los paréntesis circundantes):

<img width="916" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/5c11c153-426d-4759-9d19-c3f53a128314">

Esta versión del cálculo también produce el mismo valor: **8795**. Sin embargo, para entender lo que está pasando, otros programadores necesitan entender las reglas de precedencia de Python para estar en condiciones de determinar cómo ocurrió el cálculo, por ejemplo: ¿el **`*`** ¿Ocurre antes del **`+`** o después? ¿Quién sabe? No existe tanta confusión con la primera versión del cálculo, ya que los paréntesis dejan explícito qué se calcula y cuándo. Sí, es más escribir (y más código), pero no se puede subestimar la capacidad de comprender lo que sucede con el cálculo.

<img width="941" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e4e86c59-9d22-4b34-ba75-9c09210396b2">

**Si puedes convertir un tiempo de natación...**

Puedes convertirlos todos. Y no hay crédito adicional por adivinar que necesitas un **bucle** aquí.

Como la mayoría de los lenguajes de programación, Python ofrece muchas formas de realizar bucles, siendo el bucle **for** uno de los favoritos.

Lo vio por primera vez en la charla inicial, pero recordemos cómo se ve un bucle **for** considerando un bucle simple que toma cada una de los strings de la lista **`times`** y las muestra en la pantalla.

## "Una revisión rápida del bucle for de Python"

Aquí hay un bucle **for** simple que toma cada una de los strings de tiempo en la lista **`times`** y las muestra en la pantalla (gracias a **print** BIF):

<img width="942" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c6a55cd5-5d6a-4746-8361-c090fb041613">

**P:** ¿No utilizan la mayoría de los programadores **“i”** como variable de bucle en esta situación?

**R:** Sí, lo hacen. Pero siempre consideramos **"i"** como una abreviatura de "índice-index", lo que no tiene sentido en el bucle anterior. Usar **"t"** como abreviatura de "time" tiene más sentido para nosotros.

**P:** Me pregunto si hay algo en el PSL que pueda ayudar a convertir estas time strings.

**R:** Buena pregunta y la respuesta es: *casi*. La PSL (Python Standard Library) incluye dos módulos que pueden ayudar: **`time`** y **`datetime`**. Si necesita trabajar con fechas y/u horas, ambas libraries proporcionan muchas funciones integradas. Sin embargo, (hasta donde podamos ver) no brindamos ningún soporte para realizar las operaciones aritméticas o de clasificación que necesitarán aquí para calcular el tiempo promedio de natación según lo requiera el entrenador, por lo que no utilice cualquiera de las libraries aquí. Por supuesto, nos reservamos el derecho de cambiar de opinión si nuestras manipulaciones del tiempo se convierten en un lío espinoso en algún momento...

**P:** ¿Supongo que Python admite otros operadores además de “**`+`**” y “**`*`**”?

R: Sí, seguro que sí. Todos los habituales están ahí: **`+`**, **`-`**, **`*`**, **`/`**, etc. Hay un par de extras que son específicos de Python, por ejemplo **`//`** y **`**`**, y (si los necesita) nos aseguramos de contarle todo lo que necesita saber.

<img width="929" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/dc46445c-4cc6-4704-b5df-21d7caa0c338">

<img width="965" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/2dc1bbf2-36ea-4914-a0ce-ae5467764b64">

<img width="1038" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/7acffb7c-b632-4335-803c-88f34206cc7e">

**Genial, ¿no?**

El bucle **for** es lo suficientemente inteligente como para saber todo sobre la longitud de la lista que está procesando.

Siempre existe la tentación de utilizar el **len** BIF para calcular el tamaño de su lista antes de que se repita, pero este es un paso innecesario. El bucle **for** comienza con el primer valor de la lista, toma cada valor en orden, procesa el valor y luego pasa al siguiente. Cuando la lista se agota, el bucle **for** termina.

Este es el tipo de magia que amamos.

<img width="940" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/fe3c5cd1-0f2a-4366-bf6f-9363a314d0d4">

Ahora que has visto el bucle **for** en acción, tómate un momento para experimentar en tu notebook y combinar el código de centésimas de segundo de unas cuantas páginas atrás con un bucle **for** para convertir todos los tiempos de natación en la lista **`times`**. mostrando los tiempos de natación y sus valores convertidos en la pantalla a medida que avanza. Cuando haya terminado, escriba el código que utilizó en el espacio a continuación. Nuestro código aparecerá en dos páginas.

___________________________________________

___________________________________________

___________________________________________

___________________________________________

___________________________________________

___________________________________________

<img width="1028" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e6fb2ffc-3eaa-4f68-b139-995326051856">

**De hecho, Python admite while.**

Pero el bucle **while** en Python se usa mucho menos que su equivalente **for**.

Antes de llegar a nuestro código de solución para el ejercicio anterior, tomemos un momento para comparar los bucles **for** con los bucles **while**.

## “Nos quitamos los guantes… bucles for versus bucles while”

Aquí está el bucle **for** anterior, junto con su resultado:

<img width="988" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/53b5bef4-bc66-442e-b9d0-81a6befbf39f">

Y aquí hay un bucle **while** equivalente que hace exactamente lo mismo:

<img width="993" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/6fbf7f4f-dac2-44fa-8a83-67d54a0e8321">

¡No solo el código del bucle **while** tiene el doble de líneas que el bucle **for**, sino que también mira todas las cosas adicionales de las que tienes que preocuparte! Hay muchos lugares donde el bucle **while** puede salir mal, a diferencia del bucle **for**. No es que los bucles **while** no deban usarse, solo recuerda usar primero el bucle **for** en la mayoría de los casos.

<img width="930" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/8bb6bb62-2b4a-4a00-949a-d28f9921bb87">

Ahora que ha visto el bucle **for** en acción, debe tomarse un momento para experimentar en su notebook para combinar el código de centésimas de segundo de unas cuantas páginas atrás con un bucle **for** para convertir todos los tiempos de natación a centésimas de segundos, mostrando los tiempos de natación y sus valores convertidos en pantalla. Debías escribir el código que usaste en el espacio a continuación. Aquí está el código que se nos ocurrió:


<img width="1132" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/80bf0002-43ac-42fe-88fb-0350a70d901d">

Al probar el código de la solución del ejercicio se obtiene el resultado esperado:

<img width="945" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/2150cda0-091f-4c48-b5aa-756a23c905b1">

<hr>

## "¡Ahora estás navegando y haciendo grandes progresos!"

Ahora ha pasado el punto medio de sus subtareas para la Tarea n.° 2:

<img width="1013" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/05373331-3cb4-4fef-b473-d0d5e9add78b">

<img width="1219" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4caaf293-f5b1-4652-9e96-176a3039ae77">

**Si y no.**

Nadie va a sugerir que calcular un promedio es difícil, pero: ¿hacemos esto manteniendo un total acumulado, luego dividimos o recordamos los valores de conversión en (digamos) otra lista y luego realizamos el cálculo promedio más tarde?

Cualquiera de los dos enfoques funciona, pero quizás conservar una copia de los tiempos convertidos no sea tan mala idea. ¿Qué opinas?


## “Conservemos una copia de las conversiones”

Suponemos que esos valores convertidos serán necesarios al menos una vez más en nuestro código, por lo que es mejor si los colocamos en otra lista a medida que realizamos cada conversión.

Para hacer esto, necesita aprender un poco más sobre las listas. Específicamente, cómo crear una lista nueva y vacía y cómo agregar valores de datos de forma incremental a su lista a medida que itera sobre la lista **`times`**.

## Creando una lista nueva y vacía

Paso 1: piense en un nombre de variable significativo para su lista. Paso 2: Asigne una lista vacía a su nuevo nombre de variable.

Llamemos a su nueva lista **`converts`**. A continuación se explica cómo realizar los pasos 1 y 2 en una sola línea de código:

<img width="955" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/3e042150-e365-4bc5-81bc-a06528cea29d">


Recuerde que el **type** BIF se utiliza para determinar a qué tipo se refiere una variable. Una llamada rápida para escribir confirma que está trabajando con una lista y una llamada al BIF **len** confirma que su nueva lista está *vacía*:

<img width="925" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/81fe2c6c-32f5-4a89-a56a-a8913a62b430">

**¿Recuerdas lo que debes hacer para mostrar los métodos integrados de tu nueva lista?**

## "Mostrar una lista de los métodos de su lista"

¡Es hora de combo mambo!

Como ocurre con cualquier objeto en Python, la combinación **print dir** enumera los atributos y métodos integrados del objeto. Y como todo en Python es un objeto, ¡las listas también son objetos!

<img width="978" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/14dfff27-611d-4e05-8649-9e7d7d9bc64f">

El primer nombre del método es **append**. Probablemente puedas adivinar lo que hace, pero usemos el **help** BIF para confirmarlo:

<img width="944" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4acb6f18-396b-4089-86a3-73deda9210df">

¡Ah, ja!

Esa última línea de resultado (*“Append object to the end of the list.”*) es todo lo que necesita saber, aunque es tentador tomarse un tiempo para experimentar con esos otros métodos, algunos de los cuales suenan bien. Pero no hagamos eso ahora.

<hr>

**NOTA**

Por supuesto, si sientes la necesidad de experimentar con esos otros métodos, no dejes que te detengamos.

<hr>

Sigamos con la tarea de crear una nueva lista de valores de tiempo de natación convertidos a medida que avanzamos.

<img width="1052" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/14508a1d-77e7-4553-82f5-b7511c2acfb1">

**No, no necesitas preocuparte.**

En el capítulo inicial, dimos mucha importancia a que las listas en Python sean *como* arrays en otros lenguajes de programación.

Sin embargo, a diferencia de algunos arrays, donde normalmente hay que decir el tamaño probable del array (por ejemplo, 1000 slots) y qué tipo de datos contendrá (por ejemplo, números enteros), no es necesario declarar ninguno de estos con tus listas de Python.

Las listas de Python son dinámicas, lo que significa que crecen según sea necesario (por lo que no es necesario declarar previamente el número de espacios). Y las listas de Python no contienen valores de datos, contienen **referencias de objetos**, por lo que puedes poner cualquier dato de cualquier tipo en una lista de Python. ***Incluso puedes mezclar tipos de combinaciones***.

<img width="930" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/66c6c943-8ac1-40ce-a554-0bf1474c50c1">

Toma tu lápiz, ya que tienes trabajo que hacer. Aquí está el código más reciente, que muestra las time strings de natación junto con la conversión equivalente a centésimas de segundo:

<img width="930" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/96ff06d1-0c64-4a0a-b1fe-de95e59c490b">

Ajuste el código anterior para hacer dos cosas: (1) crear una nueva lista vacía llamada **`converts`** justo antes de que comience el ciclo y (2) reemplazar la línea que comienza con una llamada al **print** BIF con una línea de código que agrega el código convertido al final de la lista **`converts`**. Escriba su código en el espacio a continuación (y, cuando esté listo, compare su código con el nuestro en la página siguiente):

<img width="950" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/17d3b465-1b3f-4708-82a1-13913bc498e8">

<img width="888" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/5209e15a-5783-47f8-839f-2fd990e2db6b">

Debías agarrar tu lápiz, como harías en el trabajo. Se le mostró el código más reciente, que muestra los time strings de natación junto con la conversión equivalente a centésimas de segundo:

<img width="859" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/633e5331-76b8-4e06-bcf2-2079539c3526">

Su trabajo consistía en ajustar el código anterior para hacer dos cosas: (1) crear una nueva lista vacía llamada **`converts`** justo antes de que comience el ciclo y (2) reemplazar la línea que comienza con una llamada al **print** BIF con una línea de código que agrega el valor convertido al final de la lista de convertidos.

Aquí está el código que se nos ocurrió:

<img width="1007" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c5135e86-c8c9-4967-953e-683e501c88cd">

<img width="856" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/01b5a9f4-a803-497d-94b5-ce0f4222f609">

Probemos su último código. Recuerde que la versión anterior de su bucle produjo este resultado:

<img width="864" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e7fa5872-3eee-45f3-92ce-5d34cb35e635">

Su nuevo código de bucle es similar, pero no produce ningún resultado. En cambio, la lista **`converts`** se completa con los valores de conversión. A continuación, el nuevo código de bucle se ejecuta en una celda de código (sin generar resultados) y luego, en dos celdas de código posteriores, se muestra el contenido de la lista **`times`** y la (nueva) lista **`converts`**:

<img width="1124" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/975a5dfa-11df-4451-bfb7-ae6c13ddcb43">

<hr>

## “Es hora de calcular el promedio”

No es necesario ser programador para saber cómo calcular un promedio cuando se le da una lista de números. El código no es difícil, pero este hecho por sí solo no justifica su decisión de escribirlo. Cuando se encuentre con una necesidad de codificación que parezca que alguien más ya la ha codificado, hágase esta pregunta: Me pregunto si hay algo en la Python Standard Library que pueda ayudar.

**Oye, ¿recuerdas ese útil PSL? No, no el delicioso café con leche de temporada, ¡el otro PSL!**

No es ninguna vergüenza reutilizar código existente, incluso para algo que consideras simple. Con eso en mente, aquí se explica cómo calcular el promedio de la lista **`converts`** con la ayuda del PSL:

<img width="1068" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4de0c983-7fdd-4580-a1a3-589267b2ce74">

Aunque calcular el promedio es fácil, como se muestra arriba, no ha tenido que escribir un bucle, mantener un conteo, mantener un total acumulado ni realizar el cálculo promedio. Todo lo que debes hacer es pasar el nombre de la lista de números a la función **mean(media)**, que devuelve la media aritmética (es decir, el promedio) de tus datos. Cool. Eso servirá.

<img width="1214" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b752596e-d907-4d86-88cc-113ab551713d">

**Sí, como mins:secs.hundredths.**

De hecho, debes revertir el proceso anterior que convirtió la time string de natación original en su equivalente numérico.

No puede ser tan difícil, ¿verdad?

## "Convierta el promedio en una time string de natación"

Los programadores experimentados de Python saben lo suficiente como para aplicar algunos "trucos" al problema de convertir sus centésimas de segundo nuevamente al formato de string **mins:secs.hundredths**. Aprenderá acerca de estas técnicas más adelante en este libro, ya que mostrárselas ahora probablemente duplicaría el tamaño de este capítulo. Entonces, por ahora, sigamos (principalmente) con el Python que ya conoce para realizar esta tarea.

Siga en su notebook mientras recorre los cinco pasos para realizar la conversión. Esto es lo que estás intentando hacer:

<img width="1138" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/0b8c2664-f882-4fc9-81bb-02612af04544">

<img width="1142" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/28ea2be6-d0b3-48dc-b7be-8053fdf011a4">

<img width="1094" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/d509fb5c-aad6-458f-9f6e-26edfaf3e97b">

<img width="1278" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/cd74de07-6ccc-4611-90c1-787a112e3b7d">

<img width="1226" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/eabd0876-ffe9-4485-8ee3-c799d3fc2bc5">

<img width="1174" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/15456384-cd11-43dc-8418-b39888c53818">

<img width="1224" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/25e43aee-6a62-4066-88c5-c8ca976b1155">

**Sí, y es más fácil de lo que piensas.**

Podrías comenzar y aprender a escribir pruebas automatizadas en Python y luego codificar cualquier cantidad de pruebas para verificar tus cálculos...

O simplemente puede echar otro vistazo a la hoja de cálculo del entrenador de natación para confirmar que su tiempo de natación calculado de **`1:26,58`** coincide con el promedio calculado en la hoja de cálculo del entrenador.

Y lo hace, como se muestra a continuación.

<img width="1115" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/08370954-8ae0-4264-a76f-3bb5f0bcabf3">


## “Es hora de unirlo todo”

¡Felicidades! Por fin puedes marcar la bien merecida subtarea (e).

Todo lo que queda es combinar el código del capítulo anterior con el código visto hasta ahora en este capítulo. Una vez hecho esto, también se realizará la subtarea (f):

<img width="1124" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a36515f2-3472-4c9d-830e-5a0b7467b218">

<hr>

**NOTA**

Todo lo que queda…

<hr>

<img width="1048" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/7b8fc2bc-e233-4a11-8396-773433024065">

En esta etapa, debería tener varios Jupyter notebooks en su carpeta *Learning*. Para completar este ejercicio, necesitarás estudiar el código de dos de ellos: **`Darius.ipynb`** y **`Average.ipynb`**.

Cree un nuevo notebooks, llamado **`Times.ipynb`**, luego agregue el código Python que necesita para completar la subtarea (f). Todo el código que necesita ya existe y todo lo que debe hacer aquí es copiar el código relevante de sus dos notebooks existentes al nuevo.

Asegúrese de ejecutar todo el código en su nuevo notebook para confirmar que se ejecuta como se esperaba.

Tómate tu tiempo con este ejercicio y luego, cuando estés listo, voltea la página para ver nuestro **`Times.ipynb`** en acción.

<img width="1134" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/641cb78b-bada-42be-8dc2-487c2af475b8">

En esta etapa, debería tener varios upyter notebooks en su carpeta *Learning*. Para completar este ejercicio, debías estudiar el código de dos de ellos: **`Darius.ipynb`** y **`Average.ipynb`**.

Debías crear un nuevo cuaderno, llamado **`Times.ipynb`**, que contiene el código Python que necesitabas ejecutar para completar la subtarea (f). Todo el código que necesitas ya existe.

Debías asegurarte de ejecutar todo el código en tu nueva computadora portátil para confirmar que se ejecuta como se esperaba.

Aquí está el código que copiamos en **`Times.ipynb`** y ejecutamos. ¿Cómo se compara el código que copiaste?

<img width="1233" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/25b1c387-bc1d-44fe-8cec-62603a357a2f">

<img width="1151" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/eb7e2383-6008-43b8-acef-66e1a22e0242">

<img width="1194" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/8c61473c-4ea6-4600-a1a3-c555dea53be6">

<img width="1130" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e926384d-822a-4fa7-991a-ee8c1fd15587">

<hr>

## “¡La tarea número 2 (finalmente) supera la línea!”

¡Bien hecho! Con la creación (y ejecución) del notebook **`Times.ipynb`**, las dos tareas identificadas al comienzo del capítulo anterior ya están completas. ¡Es un caso de marcas de verificación por todas partes!

<img width="1219" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/97e8d38c-c31f-4097-82b7-a779b05fea70">

Por supuesto, llegar a este punto no significa necesariamente que haya terminado...

<img width="1098" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/0e61f448-3a36-444f-8a7a-b9e65bb80142">

**¡Excelente! ¡Estamos en camino!**

El siguiente capítulo sienta las bases para llegar al punto en el que pueda abordar el requisito de gráficos del entrenador.

Por ahora, su código solo funciona con los datos de un archivo específico (para Darius). Hay otros 59 archivos en el conjunto de datos del Coach. Sería bueno si hubiera una manera de usar el código desarrollado en este y el capítulo anterior con cualquier otro archivo.

Hacerlo es algo que puede reflexionar de camino al siguiente capítulo, cuando trabajemos juntos para encontrar una solución a este problema.

Por ahora, concluyamos este capítulo con otro resumen y un crucigrama de gran actualidad. ¡Disfrutar!

<img width="1068" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b5debfec-c5ce-4381-aabb-cfa045692ddd">

* Python no tiene una noción real de un valor **constante**, por lo que ha surgido una convención de programación mediante la cual las constantes se asignan a nombres de variables en MAYÚSCULAS. En algunos casos, la library **`enum`** del PSL puede ser lo que necesita.

* La sentencia **`with`** se utiliza para gestionar el contexto dentro del cual se ejecuta su bloque de código.

* Cuando se usa con el **open** BIF, la instrucción **`with`** se organiza automáticamente para cerrar cualquier archivo aún abierto una vez que termina el bloque de código de **`with`**.

* Además, la instrucción **`with`** asigna el archivo abierto a un **file object**, que se utiliza como abreviatura del archivo abierto.

* El objeto de archivo tiene muchos métodos integrados, incluyendo **readlines** que... emm, eh... lee líneas. Las líneas se devuelven como una **list**.

* El resto de los métodos del objeto de archivo se pueden mostrar con el **print dir** combo mambo.

* De forma predeterminada, el **open** BIF abre un archivo con nombre para su lectura. Se supone que el archivo contiene **datos textuales**.

* Los dos puntos, además de ser tu mejor amigo **BFF**, le indican a Python que un bloque **indentado** está a punto de comenzar en la siguiente línea de código.

* La cadena **`.strip().split()`** es muy popular. Es utilizado en muchos lugares por muchos programadores de Python.

* Python tiene todos los operadores habituales (p. ej., **`+`**, **`-`**, **`*`**, **`/`**), y algunos más (p. ej., **`//`** y **`**`**).

* El operador **`//`** realiza la **floor division**, lo que garantiza, entre otras cosas, que el resultado de la división sea siempre un número entero.

* Aunque está en su derecho de amar los bucles **for** y **while** por igual, el bucle **for** tiene mucho más uso en la comunidad y, por lo general, se utiliza primero cuando un programador de Python necesita iterar.

* La **list** de Python es una estructura de datos incorporada muy popular, que comprende la conocida notación de corchetes.

* Una lista vacía se parece a esto: **`[]`**.

* Los elementos de una lista están entre **corchetes(square brackets)** y separados entre sí por una **coma**. Saber esto hace que las listas sean fáciles de detectar.

* Las listas vienen con muchas funciones integradas, pero la estrella del espectáculo (en este capítulo) es el método de **append(agregar)**.

* El **int** BIF convierte su argumento único en un número entero, si puede. El valor **`"42"`** se convierte sin problemas, mientras que **`"cuarenta y dos" `** envía **`int`** al estado de fusión.

* El **PSL** (¡¡no el café!!) proporciona el módulo de **statistics** que, entre otras cosas, proporciona una útil función **mean**. La función **mean(media)** tiene todo que ver con el cálculo de promedios, en lugar de no ser agradable estar cerca...

* El **round** BIF elimina los decimales no deseados.

* El **str** BIF convierte su argumento en un string.

* El entrenador está muy **contento** con tu progreso hasta la fecha, como deberías estarlo tú. Hay mucho buen trabajo en este (y en el anterior) capítulo.

<img width="1092" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/9d20ab9a-def3-4e09-8196-e5606a0c4c86">

Todas las respuestas a las pistas se encuentran en las páginas de este capítulo y la solución está en la página siguiente. ¡A por ello!

<img width="823" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/03173b36-3194-4dac-b52f-fd8fdfe14647">

<img width="1228" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/cfa92816-f833-4407-86f3-55c9193a6c08">

<img width="1031" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/7e7f75d3-58d6-4c21-b0e0-b49f2a9e3313">

<img width="1129" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/ff6b34b1-e9dd-40f9-9664-7a7e6a4d7783">

<img width="889" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/445d0dfb-b245-46a8-aa77-57ef4eba4a9b">
