# Capítulo 3. Listas de números: *procesamiento de datos de listas*

<img width="744" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/62331a69-da66-408d-bbdf-a7acfa9794fb">

* “Tarea #2: Procesar los datos en el archivo”

* “Obtenga una copia de los datos del entrenador”

* “El open BIF funciona con archivos”

* "Usar open para abrir (y close) un archivo"

* "Las variables se crean dinámicamente, según sea necesario"

* “Los datos del archivo son lo que realmente quieres”

* “Tenemos los datos del nadador del expediente”

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

## “Los datos del archivo son lo que realmente quieres”

## “Tenemos los datos del nadador del expediente”

## “Lo que debe suceder a continuación me resulta familiar”

## “El capítulo anterior está dando dividendos”

## "Convertir una time string en un time value"

## “A centésimas de segundo con Python”

## "Una revisión rápida del bucle for de Python"

## “Nos quitamos los guantes… bucles for versus bucles while”

## "¡Ahora estás navegando y haciendo grandes progresos!"

## “Conservemos una copia de las conversiones”

## "Mostrar una lista de los métodos de su lista"

## “Es hora de calcular el promedio”

## "Convierta el promedio en una time string de natación"

## “Es hora de unirlo todo”

## “¡La tarea número 2 (finalmente) supera la línea!”

