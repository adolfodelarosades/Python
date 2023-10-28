# Capítulo 4. Lista de Archivos: *Funciones, Módulos y Archivos*

<img width="768" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/6e56bf9d-ae76-44c2-8394-98584988f89d">

Su código no puede vivir en un notebook para siempre. Quiere ser libre.

Y cuando se trata de liberar su código y **compartirlo** con otros, el primer paso es una **función** personalizada, seguida poco después por un **módulo** que le permite organizar y compartir su código. En este capítulo, creará una función directamente a partir del código que ha escrito hasta ahora y, en el proceso, también creará un módulo que se puede **compartir**. Inmediatamente pondrás tu módulo a funcionar mientras procesas los datos de natación del entrenador con bucles **for**, declaraciones **if**, pruebas condicionales y **PSL**(*Python Standard Library*). También aprenderá a **comentar** sus funciones (lo cual siempre es una buena idea). ¡Hay mucho por hacer, así que vamos a ello!

* "Ya tienes la mayor parte del código que necesitas"

* "Cómo crear una función en Python"

* “Guarda tu código tantas veces como quieras”

* “No basta con copiar el código”

* "Asegúrate de copiar todo el código que necesitas"

* "Utilice módulos para compartir código"

* "Disfruta de la gloria de los datos devueltos"

* "Las funciones devuelven una tupla cuando es necesario"

* "Consigamos una lista de los nombres de archivos del entrenador"

* "Es hora de hacer un poco de trabajo detectivesco..."

* "¿Qué puedes hacer con las listas?"

* "¿El problema está en tus datos o en tu código?"

* “Decisiones, decisiones, decisiones”

* “Busquemos los dos puntos” en “la cadena”

* "¿Terminaste con 60 archivos procesados?"

* “El código del entrenador está tomando forma…”



### Conversación en cubículo

<img width="748" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/612082d2-1d81-43ee-8401-ef256350e958">

**Sam**: He actualizado al entrenador sobre el progreso hasta la fecha.

**Alex**: ¿Y está feliz?

**Sam**: Hasta cierto punto, sí. Está emocionado de que las cosas hayan comenzado. Sin embargo, como puedes imaginar, lo único que realmente le interesa es el producto final, que para el coach es el gráfico de barras.

**Alex**: Lo cual debería ser bastante fácil de hacer ahora que el cuaderno más reciente produce los datos que necesitamos, ¿verdad?

**Mara**: Bueno... más o menos.

**Alex**: ¿Cómo es eso?

**Mara**: El notebook actual, **`Times.ipynb`**, produce datos de Darius nadando los 100m mariposa en el grupo de menores de 13 años. Pero es necesario realizar las conversiones y el cálculo promedio para el archivo de cualquier nadador.

**Alex**: Claro, eso es fácil: simplemente reemplace el nombre del archivo en la parte superior del cuaderno con otro nombre de archivo, luego presione el botón Ejecutar todo y, ¡listo!, tendrá sus datos.

**Mara**: ¿Y crees que el entrenador estará feliz de hacerlo?

**Alex**: Errr... No había pensado en cómo el entrenador va a manejar estas cosas.

**Sam**: Vamos en la dirección correcta, ya que necesitamos un mecanismo que funcione con el nombre de archivo de cualquier nadador. Si eso se puede producir, podemos continuar con la creación de código para el gráfico de barras.

**Alex**: Así que aún nos queda mucho camino por recorrer...

**Mara**: Sí, pero no muy lejos. Como ya mencionaste, todo el código que necesitamos está en el notebook **`Times.ipynb`**…

**Alex**: …que no le quieres dar al entrenador…

**Mara**: …bueno, no es su forma actual.

**Alex**: ¿Entonces cómo?

**Sam**: Necesitamos una forma de empaquetar el código para que pueda usarse con cualquier nombre de archivo y accederse fuera del notebook...

**Alex**: Ah, pero claro: ¡necesitamos una función!

**Sam**: Lo que nos lleva a parte del camino.

**Mara**: Si la función se coloca dentro de un módulo de Python, se puede compartir en muchos lugares.

**Alex**: Me parece bien. ¿Donde empezamos?

**Mara**: Comencemos por convertir el código del notebook existente en una función que podamos llamar y luego compartir.

## Ya tienes la mayor parte del código que necesitas.

Pero el código que necesita se encuentra actualmente en su notebook **`Times.ipynb`**.

Cuando se trata de experimentar y crear código desde cero, nada mejor que usar un notebook Jupyter. Sin embargo, cuando se trata de reutilizar y compartir el código existente, los notebook pueden no ser la mejor opción (y, para ser justos, los notebook no se diseñaron teniendo en cuenta esta actividad).

Puede darle a cualquiera una *copia* de su computadora portátil para que la ejecute dentro de su propio entorno Jupyter, y ese es un excelente caso de uso. Pero imagina que estás creando una aplicación que necesita usar parte del código que reside actualmente en tu notebook...

<hr>

**NOTA**

En el Apéndice A, analizamos una extensión de Jupyter que puede ayudar con este requisito, pero, desde el principio, compartir el código de su computadora portátil puede ser complicado.

<hr>

¿Cómo se comparte ese código?

Para compartir el código de su notebook, necesita crear una **función** que contenga su código y luego compartir su función en un **módulo**. Y harás ambas cosas en este capítulo.

Para comenzar, cree un archivo nuevo y vacío en su carpeta **Learning**, luego cambie el nombre de su archivo a **`swimclub.py`**:

<img width="1069" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/606007f6-ac32-4b6a-b1d8-a0919990525d">

## Cómo crear una función en Python

Además del código real de la función, debes pensar en la *signature-firma* de la función. Hay tres cosas a tener en cuenta. Necesitas:

1️⃣ **Piensa en un nombre bonito y significativo.**

El código del notebook **`Times.ipynb`** primero procesa el nombre del archivo y luego lee el contenido del archivo para extraer los datos requeridos por el Coach. Entonces llamemos a esta función **`read_swim_data`**. Es un nombre bonito, es un nombre significativo... ¡Caramba, es casi perfecto!

2️⃣ **Decida el número y los nombres de los parámetros.**

Su nueva función **`read_swim_data`** toma un solo parámetro, que identifica el nombre de archivo a usar. Llamemos a este parámetro **`filename`**.

3️⃣ **Sangra el código de tu función bajo una declaración `def`.**

La palabra clave **`def`** introduce la función, permitiéndole especificar el nombre de la función y cualquier parámetro. Cualquier código sangrado bajo la palabra clave **`def`** es el bloque de código de la función.

<hr>

**NOTA**

Puede resultar útil pensar en **"def"** como una abreviatura de **"define function"**.

<hr>

<img width="755" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/6f2073e0-1588-4bc1-9d0d-285ca1650ee7">

## Guarda tu código tantas veces como quieras

Continúe y agregue la *signature-firma* para la función **`read_swim_data`** en la parte superior de su archivo **`swimclub.py`**:

<img width="936" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/3969fa6c-062b-4c26-9427-a6ee249006b1">

### Agrega el código que deseas compartir a la función.

Con la firma de la función escrita, la siguiente tarea es tomar el código que desea compartir de su computadora portátil y copiar el código en **`swimclub.py`**. El código que necesita se encuentra en el notebook **`Times.ipynb`** del capítulo anterior.

<img width="918" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/11932504-0815-4508-b2ce-f57bfbf68e95">

Tómese un momento para revisar el código en su notebook **`Times.ipynb`**. ¿Crees que necesitas **todo** el código de este notebook?

## Simplemente copiar código no es suficiente

Seguimos adelante y copiamos el código que creemos que necesitamos y lo agregamos a nuestra función **`read_swim_data`**. Así es como se ve el código en VS Code para nosotros:

<img width="933" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/3ad94e03-4b78-4c16-ac23-a671ee356bc0">

<img width="809" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b5dddb01-3bfa-4250-85df-809b8a13e518">

**De hecho lo hacen, y están bien vistos.**

Este es VS Code que le indica que su código se basa en valores que aún no se han definido. Aunque el código es Python sintácticamente correcto, no se ejecutará porque faltan esos valores.

Esos valores están en el notebook **`Times.ipynb`**.

## Asegúrate de copiar todo el código que necesitas.

Al observar las líneas onduladas de la página anterior, está claro que *faltan* **`FN`**, **`FOLDER`** y **`statistics`**.

**`FOLDER`** y **`statistics`** son soluciones fáciles. Simplemente agregue estas dos líneas de código en la parte superior del archivo **`swimclub.py`** (fuera de la función):

<img width="926" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/34c33490-1c03-4e59-adfc-46aa48ad46dd">

Si sigue las instrucciones, notará que en el momento en que escribe cada una de estas líneas de código en VS Code, las líneas onduladas desaparecen.

Enojado por este éxito, es posible que también sienta la tentación de copiar y pegar la definición de la constante **`FN`**, pero eso sería un error. Recuerde que en el notebook **`Times.ipynb`**, **`FN`** se refiere a uno de los archivos de datos asociados con Darius. Si continúa usando **`FN`**, su nueva función usará ese archivo y ningún otro. La solución a este problema es utilizar el valor pasado a la función **`read_swim_data`** en lugar de la constante **`FN`**. De esa manera el Coach puede usar tu función para procesar el archivo de datos de cualquier nadador:

<img width="951" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/61158f90-f868-4622-baf5-0985cb1bf638">


