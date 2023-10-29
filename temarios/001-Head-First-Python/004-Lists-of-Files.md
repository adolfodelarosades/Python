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

<img width="925" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/12a2f2e0-059c-46b0-8d78-cd3b526280a9">

Con su función definida, asegúrese de guardarla antes de continuar con esta *Test Drive*.

Deje su código **`swimclub.py`** abierto en VS Code (si lo desea), luego abra otro notebook nuevo y llámelo **`Files.ipynb`**. Ya sabes cómo funciona la sentencia **`import`** de Python con PSL. Resulta que **`import`** también puede importar sus módulos personalizados. ¿Y adivina qué? El archivo **`swimclub.py`** es un módulo de Python, por lo que puedes usar **`import`**, como se muestra a continuación:

<img width="1053" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/cca17241-c5ea-4c14-a099-0225456a9b6c">

<img width="915" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/668899e4-9886-4ead-b8a2-ef8ec51ab5ac">

**Sí, eso es exactamente.**

Los argumentos enviados a una función se asignan a los nombres de los parámetros definidos en la firma de la función, mientras que los resultados se devuelven al código de llamada mediante una sentencia **`return`**.

<img width="914" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/0d1e182a-35b5-412c-9535-797ce4d52c77">

No es un gran cambio, pero sí importante.

Tómese un momento para revisar su función **`read_swim_data`** en el archivo **`swimclub.py`** y luego, en el espacio a continuación, escriba la sentencia **return** que agregaría al final de su función para enviar valores de regreso a la persona que llama a la función.

Encontrará nuestra sentencia **return** sugerida en la página siguiente, pero intente crear esta única línea de código usted mismo antes de pasar la página. (Pista: decidimos return seis valores de la función).

<img width="922" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/7277c63a-bd53-4317-817d-f94c1093c6bf">

<img width="922" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a172f7ba-c249-4097-beec-28828ce80a8b">

### Actualiza y guarda tu código antes de continuar...

Antes de pasar a la página siguiente, asegúrese de agregar la siguiente línea de código como última línea en su función **`read_swim_data`** dentro de su archivo **`swimclub.py`**. Tenga cuidado de hacer coincidir la sangría de esta línea de código con la sangría utilizada para el resto del código de su función:

<img width="931" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/bde1b53b-ab75-4cc1-8fc4-835893b4364e">

Habiendo guardado este cambio en el código de su módulo, probablemente no pueda esperar a volver a su notebook **`Files.ipynb`** para ver qué diferencia hace el cambio, ¿verdad?

Nosotros tampoco, pero… odiamos tener que decirles que a todos nos espera la *decepción*.

<img width="911" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/6c03965f-c946-462e-8974-13de2172fb76">

Con la sentencia **return** agregada a su función **`read_swim_data`** y el módulo **`swimclub`** guardado, regrese a su notebook **`Files.ipynb`**, haga clic en la primera celda del código, luego use **Shift+Enter** para volver a ejecutar las dos celdas de su notebook.

<img width="926" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/d0111e34-078d-47bd-ab97-4f03be39a1e7">

Aunque cambió y guardó el código de su módulo, volver a ejecutar la sentencia **`import`** y luego volver a invocar la función no hizo ninguna diferencia. Todavía no hay resultados. **¿Qué está sucediendo?**

<img width="921" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4c026931-4fc4-4ef6-af1c-f06ec80bff6d">

**Sí, se siente como si hubiera algo seriamente roto aquí...**

En realidad, no es Jupyter el que está causando el problema, sino el intérprete de Python. Y (por extraño que parezca) las cosas deben funcionar de esta manera.

Creemos que alguien tiene algunas preguntas serias que responder.

<img width="913" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b785061e-da12-44c1-b515-a61052df5097">

**Head First**: Gracias por sentarse con nosotros, especialmente con tan poca antelación.

**import**: Feliz de estar aquí.

**Head First**: tengo que admitir que la prueba de manejo más reciente me ha desconcertado un poco. Modifiqué y guardé mi código, luego volví a ejecutar mi sentencia **`import`**, pero nada cambió. ¿Se supone que las cosas deben funcionar de esta manera?

**import**: Sí.

**Head First**: ¿En serio?

**import**: Así es como ruedo…

**Head First**: Pero, ¿cómo soluciono esto?

**import**: En realidad no es tan difícil, pero… necesitabas reiniciar, no volver a importar.

**Head First**: ¿Eh?

**import**: Déjame explicarte.

**Head First**: por favor hazlo. Soy todo oídos…

**import**: cuando creó su nuevo notebook, el intérprete de Python creó una nueva sesión para que se ejecutara su código. Lo primero que hizo en esta nueva sesión fue ejecutarme, su sentencia **`import`** amigable, en su módulo **`swimclub`**.

**Head First**: Sí, luego ejecuté mi función, me di cuenta de que no devolvía ningún dato, lo arreglé, lo guardé y luego importé mi módulo nuevamente.

**import**: Sólo que no lo hiciste.

**Head First**: Me has perdido...

**import**: Hiciste todo eso, excepto el último bit: la parte "importé mi módulo nuevamente". Verá, tengo fama de ser un poco pesado en lo que respecta al uso de recursos, por lo que los desarrolladores del intérprete de Python siempre están buscando formas de optimizar mi uso. Me han dicho que puedo tomarme un tiempo para hacer lo mío.

**Head First**: Em... Está bien...

**import**: Entonces... como la importación a veces puede ser costosa desde el punto de vista computacional, se tomó la decisión de almacenar en caché los módulos importados. No importa cuántas veces se importe un módulo dentro de una sesión particular de Python, solo se ejecuta la primera importación y se ignoran las repeticiones posteriores.

**Head First**: Entonces, si escribe, por ejemplo, **`import abc`** en tres celdas de código y luego presiona **Shift+Enter** en cada una de ellas, ¿solo se ejecuta la primera celda?

**import**: Bueno... todas las celdas se ejecutan, pero solo la primera importación hace algo. La segunda y tercera importaciones se ignoran porque el módulo importado ya está en la caché.

**Head First**: e incluso si el código del módulo cambia entre la primera y la segunda importación, o entre la segunda y la tercera, el intérprete de Python ignora las últimas importaciones ya que está optimizado para leer desde el caché, ¿verdad?

**import**: Sí.

**Head First**: ¡Ah, ja! Ahora lo entiendo. Pero, ¿cómo soluciono este problema? ¿Puedo borrar el caché o decirle al intérprete que lo ignore?

**import**: la mejor “solución” es reiniciar su sesión de Python, en lugar de volver a importar su módulo. De esa manera, la próxima vez que importe su módulo, lo hará en una nueva sesión de Python que tiene un caché de reinicio.

**Head First**: OK, todo eso tiene sentido. Pero, ¿cuál es la mejor manera de reiniciar mi sesión?

**import**: con Jupyter Notebook, hay un ***gran botón brillante de Reiniciar en la parte superior de la ventana*** de VS Code que funcionará. Cuando haces clic en eso, tu sesión anterior de Python se elimina, incluido su caché, y puedes comenzar de nuevo.

**Head First**: Genial, me voy a hacer eso ahora mismo. Gracias por tu ayuda, **¡importa!**

**import**: ¡De nada!

<img width="917" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/505f50ad-4e3f-4d24-9273-14a3e9d018bb">

¿Será que a la tercera va vencida?

Haga clic en el botón ***Restart*** en la parte superior de la ventana de VS Code (mientras muestra su notebook **`Files.ipynb`**):

<img width="890" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/75b94724-1301-4289-9577-aefa8af3a2b1">

Su clic reinicia su sesión de Python, lo que restablece el caché del módulo y elimina cualquier variable existente y sus valores de la RAM. Nos gusta seguir un reinicio con otro clic rápido en este botón:

<img width="917" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a82afe40-62f2-4765-88a0-cfcac35498e4">

Con su sesión de Python reiniciada, usemos **Shift+Enter** para ejecutar esas dos celdas de código una vez más:

<img width="914" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/93f39279-4154-4f89-9ddd-d6db50acd147">

## Utilice módulos para compartir código

Si observa el código en su archivo **`swimclub.py`**, consta de una única declaración **`import`**, una única definición constante y una única función.

Una vez que mueves el código a su propio archivo, se convierte en un **módulo de Python**, que puedes importar según sea necesario.

<img width="909" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/3d48eb29-35d7-4a44-886f-6825c4cc9446">

<img width="927" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/9cbcfa81-3853-4505-9c2e-b83dccfa4565">

**Este es un nombre completamente calificado.**

Cuando te refieres a tu función con **“module DOT function”**, estás calificando el nombre de tu función con el nombre del módulo que la contiene. Esto es muy común en la práctica, aunque existen otras técnicas de importación comunes. Verá ejemplos de estos a medida que continúe trabajando en este libro.

### Disfrute de la gloria de los datos devueltos

Echemos otro vistazo a los datos devueltos por su invocación más reciente de su función **`read_swim_data`**:

<img width="934" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/d16ce9b2-8dc6-413a-b58f-b97a35ddfb41">

<img width="814" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/2138605a-919f-4f5a-8b16-a47355cd0d55">

**Buen ojo. Bien visto también.**

Puede que esta no sea la explicación que esperas aquí, pero esos paréntesis deben estar ahí.

Profundicemos un poco en esto para que puedas apreciar lo que está pasando. Ya hemos analizado la sentencia **`import`**, por lo que ahora es el turno de **`Function’s`**.

<img width="916" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/9d374a24-f67e-4e86-86a4-13317176668d">

**Head First**: Gracias por tomarse el tiempo de su ajetreado día para charlar con nosotros.

**Function**: No hay problema.

**Head First**: ¿Cómo es que estás tan ocupado?

**Function**: Me utilizan en todas partes, todo el tiempo.

**Head First**: ¿Y trabajarás con cualquier cosa?

**Function**: Si te refieres a los datos que aceptaré, entonces sí, aceptaré con gusto todo lo que me des.

**Head First**: ¿Le importaría expandirse?

**Function**: Claro. Puede enviarme cualquier cantidad de valores de argumentos, que felizmente haré coincidir con mis parámetros, y todo lo que necesita hacer es asegurarse de enviarme el número correcto. Si tengo dos parámetros, asegúrese de enviarme dos valores de argumento.

**Head First**: ¿Qué sucede si envío, digamos, un argumento o tres?

**Function**: Me pongo de mal humor.

**Head First**: ya veo. Es así, ¿verdad?

**Function**: Sí. Soy bastante estricto en ese tipo de cosas. A menos, por supuesto, que uno de mis dos parámetros esté declarado como opcional.

**Head First**: ¿Qué pasa entonces?

**Function**: Continuando con mi ejemplo de una función de dos parámetros... si, por ejemplo, el segundo parámetro es opcional, aceptaré con gusto uno o dos valores de argumento, sin hacer preguntas.

**Head First**: Y si te llamo con un solo argumento, ¿qué se asigna al segundo parámetro?

**Function**: normalmente asigno un valor predeterminado que ha sido decidido por el programador que me creó.

**Head First**: Eso suena un poco complejo.

**Function**: En realidad no lo es y, para ser honesto, no es algo que toda función necesite, pero es parte de mí si lo necesitas. Soy bastante flexible.

**Head First**: ¿Y qué pasa con los valores devueltos? ¿Es el mismo trato? ¿Se puede devolver cualquier número de valores?

**Function**: No.

**Head First**: ¿En serio? ¿No? ¿Eso es todo lo que vas a decir sobre esto?

**Function**: Bueno… pensé que era algo obvio. Piense en las matemáticas donde las funciones devuelven un único resultado, no múltiples resultados. Es lo mismo conmigo. Cualquier número de valores, pero solo UN resultado.

**Head First**: Pero… emm… err… mira la llamada a la función **`read_swim_data`** en la página anterior. Se devuelven seis resultados.

**Function**: No, no la hay, sólo hay UNO.

**Head First**: ¿Qué...?

**Function**: si miras de cerca, notarás esos paréntesis que rodean los seis valores de datos, ¿verdad?

**Head First**: Sí, pero…

**Function**: Sin “peros” al respecto. Esos paréntesis son una única tupla que contiene los seis valores de datos individuales. Como dije, solo se devuelve UN resultado, ya sea un resultado único o una única tupla con múltiples valores contenidos en él.

**Head First**: pero el código no convierte los seis valores de retorno en una tupla.

**Function**: Sí, el código no, pero yo sí. Lo hago automáticamente cuando veo que un programador intenta devolver más de UN resultado. Me lo puedes agradecer después.

**Head First**: No, te lo agradeceré ahora. Es importante saberlo. ¡Gracias por el chat!

**Function**: ¡Siempre estoy feliz de aclarar las cosas!

## Las funciones devuelven una tupla cuando es necesario

Cuando llamas a una función que parece que va a devolver múltiples resultados, piénsalo de nuevo, porque no es así. En su lugar, **obtendrá una única tupla que contiene una colección de resultados**, independientemente de cuántos valores de resultados individuales haya.

<img width="909" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/76843c93-2214-4263-94a6-9d103a0f098c">

<img width="844" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b69f2c57-3040-484d-93e3-1b90ada32a2b">

**Esa es una gran sugerencia.**

No es que estemos sugiriendo que haya un poco de lectura mental aquí, pero da un poco de miedo que tuviéramos la misma idea...

<img width="922" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/64ac709f-f48b-4667-9085-df961d5e1e79">

**De cerca y en persona con la tupla de Python.**

Los documentos de Python afirman que una **tupla** es una *secuencia inmutable*.

**¿Inmutable?**

Ya conoces dos tipos de datos *inmutables*: **numbers** y **strings**. Ambos comparten la característica de que una vez que se crea un valor en el código, **el valor no se puede cambiar**. Por ejemplo, **`42`** es siempre **`42`**: no puede cambiar, es inmutable. Lo mismo ocurre con los **strings** en Python: "**`hello`**" siempre es "**`hello`**": una vez creada, no puede cambiar, es inmutable.

La **tupla** de Python toma esta idea de inmutabilidad y la aplica a una colección de valores de datos. A veces puede resultar útil pensar en ***una tupla como una lista constante***. Una vez que se asignan valores a una tupla, la tupla no puede cambiar, es inmutable.

**¿Secuencia?**

Si puedes usar la notación entre corchetes para acceder a elementos (o espacios) de una colección, entonces estás trabajando con una ***secuencia***. La ***lista de Python es el tipo de secuencia más familiar***, pero existen otros, incluidas ***strings*** y… ***tuplas***. Además de admitir el uso de corchetes, ***las secuencias también mantienen el orden de los elementos que contienen***.

<img width="928" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/2528584d-ea8a-441e-a6b1-13a8376cff46">

<img width="922" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b484a93d-f39f-4b6a-b1dd-caa31e345977">

Suponga que la siguiente línea de código se ha ejecutado en una celda de código nueva y vacía en su notebook (pista: siga adelante y ejecute esta línea de código en su notebook para que pueda experimentar según sea necesario):

<img width="871" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/939a1bc0-8bb9-496e-b6bb-9c3b480b28b5">

Usando la notación de corchetes, extraiga la lista de tiempos de natación de la tupla **`data`**, asignándolos a una lista llamada **`times`**. Luego muestre el contenido de la lista **`times`**. Escribe el código que usaste aquí:

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

Utilizando la tecnología de desempaquetado de Python (también conocida como asignación múltiple-*multiple assignment*), extraiga todos los elementos en variables nombradas: **`swimmer`**, **`age`**, **`distance`**, **`stroke`**, **`times2`** y **`average`**. Luego muestre el contenido de la lista **`times2`** en la pantalla:

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

<img width="923" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/81cb3c5f-6981-4e25-a619-a3d741d03214">

**P: Acabo de hacer un “print dir” en mi tupla `data` y solo hay dos métodos que no son tontos. ¿Se da el caso de que no puedes hacer nada útil con las tuplas?**

**R**: No, ese no es el caso. Ahora bien, dicho esto, si comparas la salida del **print dir** combo mambo para una lista con una tupla, ciertamente parece que las tuplas son inferiores a las listas, ya que casi no tienen métodos asociados. Pero recuerde: las tuplas son inmutables, por lo que nunca podrá cambiar una tupla una vez que se le hayan asignado datos (este hecho por sí solo reduce la cantidad de métodos que necesita con las tuplas). A medida que avance en este libro, verá ejemplos de dónde tiene sentido utilizar una tupla sobre una lista y viceversa. En pocas palabras: necesitas ambos.

<img width="918" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/82a6d62a-6308-4068-ac14-29c1e5e66bf4">


Suponga que la siguiente línea de código se ha ejecutado en una celda de código nueva y vacía en su notebook (pista: siga adelante y ejecute esta línea de código en su notebook para que pueda experimentar según sea necesario):

<img width="871" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/939a1bc0-8bb9-496e-b6bb-9c3b480b28b5">

Usando la notación de corchetes, extraiga la lista de tiempos de natación de la tupla **`data`**, asignándolos a una lista llamada **`times`**. Luego muestre el contenido de la lista **`times`**. Escribe el código que usaste aquí:

<img width="933" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/46e4c503-5a7a-414e-9f93-8f939b72594a">

Utilizando la tecnología de desempaquetado de Python (también conocida como asignación múltiple-*multiple assignment*), extraiga todos los elementos en variables nombradas: **`swimmer`**, **`age`**, **`distance`**, **`stroke`**, **`times2`** y **`average`**. Luego muestre el contenido de la lista **`times2`** en la pantalla:

<img width="926" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4f6d7635-271b-4460-8490-baad921df91c">

<img width="904" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/5bf72c4c-97d7-4c69-9e5a-bc35a8347488">

Esto es lo que vimos en nuestro notebook cuando ejecutamos las celdas de código del Ejercicio más reciente. A la variable **`data`** se le asigna la tupla completa (de seis partes) devuelta por **`read_swim_data`**, mientras que **`times`** y **`times2`** "seleccionan" los strings de tiempo de natación del espacio que las contiene dentro de la tupla de datos (aunque usando diferentes mecanismos de acceso):

<img width="660" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/8d8c2ec0-543a-422f-afed-5dd3aae26928">

<img width="831" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/aecf17d2-483f-48a2-950a-f49394bf2bc3">

**Una lista de nombres de archivos estaría bien.**

Su función **`read_swim_data`**, parte del módulo **`swimclub`**, toma el nombre de archivo de cualquier nadador y le devuelve una tupla de resultados.

<hr>

**NOTA**

Hasta ahora solo hemos usado uno de los archivos de datos de Darius. Siéntete libre de usar cualquier otro nombre de archivo de tu carpeta **"swimdata"** y pasarlo a tu función **"read_swim_data"** para confirmar que tu código funciona con cualquiera de los archivos de datos del entrenador. Recuerde: Jupyter Notebook *vive* para permitirle experimentar al crear su código.

<hr>

Lo que se necesita ahora es la lista completa de nombres de archivos, que debería poder obtener de su sistema operativo subyacente. Como puedes imaginar, el PSL te cubre cuando se trata de hacer este tipo de cosas.

#### NO HAY PREGUNTAS TONTAS

**P: Acaba de aparecer una nueva carpeta llamada `__pycache__` dentro de mi carpeta Learning. ¿Qué es eso y de dónde viene?**

**R**: El intérprete de Python utiliza internamente esa carpeta para guardar copias compiladas en caché de cualquier módulo que cree y luego importe. Aunque no es necesario compilar el código Python para ejecutarlo, detrás de escena Python convierte el código en un código de bytes interno, que luego se ejecuta. Como este proceso a veces puede resultar costoso al importar módulos, el intérprete almacena en caché una copia del código de bytes compilado en la carpeta **`__pycache__`** durante el proceso de importación. La próxima vez que importe su módulo (en una nueva sesión), el intérprete compara la marca de tiempo de su módulo con la marca de tiempo del código de bytes almacenado en caché y, si son iguales, reutiliza el código de bytes. De lo contrario, el proceso de código a código de bytes comienza de nuevo. Puede ignorar con seguridad cualquier archivo en la carpeta **`__pycache__`** y dejar todo en manos del intérprete para que lo administre (aunque es posible que desee excluir la carpeta de su repositorio de Git).

## Obtengamos una lista de los nombres de archivos del entrenador.

Cuando se trata de trabajar con su sistema operativo (ya sea Windows, macOS o Linux), el PSL lo tiene cubierto. El módulo **`os`** permite que su código Python se comunique con su sistema operativo de una manera independiente de la plataforma, y ahora usará el módulo **`os`** para obtener una lista de los archivos en la carpeta **`swimdata`**.

Asegúrese de seguirlo en su notebook **`Files.ipynb`**.

<img width="885" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/df2d4f5f-4807-44bc-ac60-c82bdceee4c6">

Quiere los nombres de los archivos en su carpeta **`swimdata`**, y el módulo del sistema operativo proporciona la útil función **`listdir`** para hacer precisamente eso. Cuando pasas la ubicación de una carpeta, **`listdir`** devuelve una lista de todos los archivos que contiene:

<img width="860" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/19994b0f-08e8-40db-bf33-6a87582347b2">

Se le perdonará si espera que la lista **`swim_files`** contenga 60 datos. Después de todo, hay 60 archivos en tu carpeta. Sin embargo, en nuestra Mac, nos llevamos una sorpresa cuando comprobamos dos veces el tamaño de **`swim_files`**:

<img width="825" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/f3c59000-280c-41ad-bf00-b8a0e15aca90">

### Es hora de hacer un poco de trabajo detectivesco...

Esperaba que su lista de archivos tuviera 60 nombres de archivo, pero el BIF **`len`** informa 61 elementos en su variable **`swim_files`**.

Para comenzar a intentar descubrir qué está sucediendo aquí, primero mostremos el valor de la lista **`swim_files`** en la pantalla:

<img width="889" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/cff18b31-7779-43cd-afb8-a68f0bc6a266">

<img width="1071" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/01711ec8-605e-4c67-a0fd-482c4d4c9601">

<img width="1227" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/690902d7-4a81-422d-834e-41652ba80130">


**Que buena idea.**

Usemos el combo mambo **print dir** para ver qué está integrado en las listas.

### ¿Qué puedes hacer con las listas?

Aquí está la salida mambo del combo **print dir** para su lista **`swim_files`**:

<img width="1087" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c885aa36-3fb0-4d0e-91a0-a2440d5309be">

<img width="1040" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/2baa95cf-efc7-46dd-9e8f-e1cf2fa1008b">

**Es necesario tener cuidado con las listas integradas (especialmente si cambian su lista).**

*Si se frota las manos de alegría ante la perspectiva de utilizar el método **sort** para reordenar su lista, dé un paso atrás. El método **sort** realiza su reordenamiento "en el lugar", lo que significa que el nuevo orden **sobrescribe**(!!) lo que estaba anteriormente en la lista. El antiguo orden de la lista se pierde para siempre... y no se puede deshacer.*

*Si desea mantener el orden existente en su lista pero aún necesita ordenar, hay un BIF que puede ayudar aquí. El BIF **sorted** devuelve una copia ordenada de los datos de su lista, dejando intacto el orden de la lista existente. Aquí tampoco se puede deshacer, ya que la lista original no se modifica.*

<img width="1062" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/2faf52d0-32be-43c3-831e-f65b15a8f761">

<img width="974" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b21b08f6-8e8b-433b-b3da-5b35e12dd516">

**Sí, ese es un problema potencial.**

Como el archivo **`swimdata.zip`** se creó inicialmente en una Mac, el archivo **`.DS_Store`** se agregó automáticamente al archivo ZIP. Este tipo de problema específico del sistema operativo suele ser motivo de preocupación.

Antes de continuar, es importante eliminar ese nombre de archivo no deseado de la lista **`swim_files`**.

<img width="1035" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/bbf8a7b5-ba83-450f-b44b-81f0462aab9b">

Aquí está la lista de métodos integrados disponibles cuando se trabaja con listas:

<img width="1019" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/669ed8ca-a62d-4f6b-b71f-e5521f6804b6">

Ya sabes lo que hacen los métodos **`append`** y **`sort`**, pero ¿qué pasa con los demás?

Utilizando el BIF **`help`**, dedique algo de tiempo a su notebook para aprender qué hacen algunos de estos otros métodos. Su objetivo es identificar el método a utilizar para eliminar ese nombre de archivo **`.DS_Store`** no deseado de su lista. Cuando crea que ha identificado un método, escriba su nombre en el espacio a continuación:

__________________________________________________________________

__________________________________________________________________

<img width="1124" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/94a0ee74-4de7-49cf-964b-9038ba038cb1">

<img width="1044" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e2730529-ce4b-4ac2-baa5-1d4256ea8d67">

No se estrese si, como resultado de completar el ejercicio anterior, identifica más de una forma de realizar la tarea asignada. Esto está bien, ya que a veces el mismo resultado se puede lograr de muchas maneras diferentes. Rara vez existe una manera absolutamente correcta de hacer algo. Como ocurre con la mayoría de las cosas, primero debe concentrarse en lograr que su código haga lo que necesita antes de intentar cualquier tipo de optimización.

<img width="1042" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/97e1f6f6-b233-4665-9e8d-8c0dbe88d048">

Aquí está la lista de métodos integrados disponibles cuando se trabaja con listas:

<img width="1019" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/669ed8ca-a62d-4f6b-b71f-e5521f6804b6">

Ya sabes lo que hacen los métodos **`append`** y **`sort`**, pero ¿qué pasa con los demás?

Utilizando el BIF **`help`**, dedique algo de tiempo a su notebook para aprender qué hacen algunos de estos otros métodos. Su objetivo es identificar el método a utilizar para eliminar ese nombre de archivo **`.DS_Store`** no deseado de su lista. Cuando crea que ha identificado un método, escriba su nombre en el espacio a continuación:

<img width="1054" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e15f430d-37bd-4eee-819d-eee985d90afb">

**P: Si descomprimo `swimdata.zip` en algo que no sea una Mac, ¿seguiré viendo ese `.DS_Store` específico de Mac?**

**R**: Lamentablemente, sí. El archivo ZIP se creó en un dispositivo Apple, por lo que el archivo **`.DS_Store`** estará allí, a menos que quien haya creado el archivo haya indicado a su herramienta zip que excluya el archivo infractor (lo que no ha sucedido en este caso).

**P: ¿No podemos evitar este problema pidiéndole al entrenador que use algo que no sea una Mac para esto?**

**R**: Preguntamos y el entrenador nos dijo que prefería comer vidrio…

**P: Puedo ver la relación entre tuplas y listas, en el sentido de que son algo similares. Supongo que una lista también es una secuencia, pero ¿es inmutable?**

**R**: Las listas son de hecho una secuencia, pero (no) **las listas no son inmutables**. Más bien, **las listas son mutables**, ya que pueden cambiar dinámicamente a medida que se ejecuta el código (a diferencia de las tuplas).

**P: Supongo que las listas son mucho más útiles que las tuplas, ¿verdad?**

**R**: Depende. Tanto las listas como las tuplas tienen sus usos. En general, las listas ven más acción que las tuplas, ya que las listas admiten muchos más casos de uso. Pero no es cierto que las listas sean “mejores” o “más útiles” que las tuplas: las listas y las tuplas están diseñadas para propósitos diferentes.

<img width="1052" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/cddbec3b-1627-4434-b77d-ff130c767f3b">

De los 11 métodos integrados en cada lista de Python, el que nos llamó la atención fue **`remove`**.

Esto es lo que informó el BIF **`help`** sobre **`remove`**:

<img width="1078" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/af9a982e-c874-4b39-a1d3-c700a5e98652">

Efectivamente, cuando se invoca el método **`remove`** en la lista **`swim_files`** (con **`.DS_Store`** dado como el nombre de archivo asignado para el corte), la lista se reduce de 61 elementos a 60:

<img width="1102" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/83005328-0be9-441a-9bf7-0c6925179dbb">

<img width="771" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4cd55c31-7444-47c0-b8e3-5a675dd8f9e8">

**Sería bueno, ¿no?**

Podríamos dejar de lado la precaución y lanzarnos a crear algunos gráficos de barras, pero puede que sea demasiado pronto para eso.

Tu función **`read_swim_data`** ha funcionado hasta ahora, pero ¿puedes estar seguro de que funcionará para el archivo de cualquier nadador? Dediquemos un momento a asegurarnos de que nuestra función **`read_swim_data`** funcione como se esperaba sin importar el archivo de datos que se presente.

<img width="1238" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4442909b-70ff-44e9-b614-1adc837130c1">

Veamos si puedes confirmar que tu función **`read_swim_data`** funciona con el archivo de cualquier nadador.

Escriba un bucle **`for`** que procese los nombres de archivos en **`swim_files`** uno a la vez. En cada iteración del bucle, muestre el nombre del archivo que se está procesando actualmente, luego haga arreglos para llamar a su función **`read_swim_data`** con el nombre del archivo actual. No necesita mostrar los datos devueltos por su función, pero sí necesita invocar la función.

Escribe el código que usaste aquí y anota todo lo que aprendiste al ejecutar tu bucle **`for`** en el espacio a continuación:

<img width="907" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c310d620-e927-4546-8b99-3e7031a6201d">

<img width="851" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/6ab56b13-5b9a-4121-9673-843bfa58ca84">

Este es el código que se nos ocurrió después de experimentar en nuestro notebook **`Files.ipynb`**, junto con el resultado generado por el código:

<img width="949" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/edaf5bbb-2f32-459d-bc3e-e9a1727242b6">

### ¿El problema está en tus datos o en tu código?

Ahora que ha identificado el archivo infractor, echemos un vistazo a su contenido para ver si puede llegar a la raíz del problema. Aquí está el archivo **`Abi-10-50m-Back.txt`** abierto en VS Code:

<img width="945" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/1fde77e0-3916-4656-b236-28f277b0de00">

Aquí está la línea de código que genera el error. ¿Puedes ver cuál es el problema?

<img width="966" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/1052d1f1-5f3e-47fc-85b0-0b18cd94e29c">

**El problema es una suposición incorrecta.**

Su código, tal como está escrito, asume que cada tiempo de natación se ajusta al formato **mins:secs.hundredths**, pero este claramente no es el caso con los tiempos de natación de 50m de Abi, y es por eso que obtiene ese **`ValueError`**.

Ahora que sabes cuál es el problema, ¿cuál es la solución?

<img width="1032" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/920d442b-3f02-4787-978d-cd8a6701fd46">

**Sam**: ¿Cuáles son nuestras opciones aquí?

**Alex**: Podríamos arreglar los datos, ¿verdad?

**Mara**: ¿Cómo es eso?

**Alex**: ¿Podríamos preprocesar cada archivo de datos para asegurarnos de que no falten minutos, tal vez anteponiendo un cero y dos puntos cuando falten minutos? De esa forma no tendremos que cambiar ningún código.

**Mara**: Eso funcionaría, pero…

**Sam**: …sería un desastre. Además, no estoy muy interesado en preprocesar todos los archivos, ya que no será necesario cambiar la gran mayoría, lo que parece un desperdicio.

**Mara**: Y aunque, como estrategia, no tendríamos que cambiar ningún código existente, tendríamos que crear el código para realizar el preprocesamiento, tal vez como una utilidad separada.

**Sam**: Recuerde también que los datos están en un formato fijo y que los genera el cronómetro inteligente del entrenador. Realmente no deberíamos alterar los datos, así que dejémoslos como están.

**Alex**: Entonces, ¿estamos pensando en cambiar nuestra función **`read_swim_data`**?

**Mara**: Sí, creo que es una mejor estrategia.

**Sam**: Yo también.

**Alex**: Entonces, ¿qué tenemos que hacer?

**Mara**: Necesitamos identificar en qué parte de nuestro código se deben realizar los cambios...

**Sam**: …y cuáles deben ser esos cambios de código.

**Alex**: Está bien, suena bien. Entonces, vamos a echar un vistazo más de cerca a nuestra función **`read_swim_data`** para que podamos decidir qué código debemos cambiar.

**Mara**: Sí, entonces podemos usar una declaración **`if`** para tomar una decisión basada en si el tiempo de natación que se está procesando actualmente tiene o no un valor de minutos.

<img width="913" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/836d725e-1771-4b83-a408-8d1999b01e99">

Aquí está la versión más reciente del código del módulo **`swimclub`**.

Toma tu lápiz y rodea el área del código que crees que necesita incorporar una declaración **`if`**:

<img width="1054" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/066a9e93-2c5f-4047-be40-6e92b1c0ee79">

<img width="969" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/466b2ac7-b37f-41b7-b300-d200cc3a0311">

Se le mostró la versión más reciente del código del módulo **`swimclub`**.

Tomando su lápiz, se le pidió que rodeara el área del código que cree que necesita incorporar una declaración **`if`**:

<img width="939" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/cc5481b6-c742-4c9d-9569-693e5c657986">

### Decisiones, decisiones, decisiones.

Eso es lo que la sentencia **if** hace, día tras día: tomar decisiones.

<img width="1053" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/2dc12df0-9c3a-4e59-8152-5d932e2666f4">

**Sí, eso es lo que se necesita aquí.**

Echemos un vistazo más de cerca a los dos posibles formatos de tiempo de natación.

Primero, aquí está uno de los tiempos registrados para Darius en su expediente:

<img width="753" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/53a3bc35-5e47-4858-aeb8-6a21342721fc">

Y aquí hay un tiempo tomado de los datos de Abi:

<img width="838" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4abea39e-4a4c-4891-8534-e5673f12968f">

Es fácil detectar la diferencia: los datos de Abi no muestran ningún minuto. Teniendo esto en cuenta, es posible proponer una condición a comprobar a la hora de tomar una decisión. ¿Puedes averiguar qué es? (Pista: considera a tu mejor amiga, los dos puntos).

### Busquemos los dos puntos “en” el string

Si los dos puntos aparecen en cualquier cadena de tiempo de natación, entonces el tiempo tiene un valor de minutos. Aunque los strings vienen con muchos métodos integrados, incluidos métodos que pueden realizar una búsqueda, no usemos ninguno de estos aquí. Como la búsqueda es un requisito tan común, Python proporciona el operador **`in`**. Ya lo has visto antes, con **`for`**:

<hr>

**NOTA**

Los métodos de string **"find"** e **"index"** realizan búsquedas.

<hr>

<img width="845" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/131bb115-4fd8-42f6-a91a-02307ef40fd1">

Usar **`in`** con **`for`** identifica la secuencia que se está iterando. Sin embargo, cuando **`in`** se usa fuera de un bucle, adquiere poderes de búsqueda. Considere estos usos de ejemplo de **`in`**:

<img width="865" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/71865a01-964e-4fc2-9cf5-870151ab3191">


<img width="855" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b8ec1ae7-182d-4261-8197-f606c4ce2008">


**También nos encanta la palabra clave "in".**

Es una superpotencia de Python.

<img width="1037" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c27a26c4-47e3-4598-9112-5555385f196b">

Como se vio en el Capítulo 1, aquí está la estructura general de una declaración **`if`** simple:

<img width="1032" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/eb6807a9-0c80-44ab-9b01-e1b5a6c73952">

Ahora que conoce la palabra clave **`in`**, ¿puede idear una declaración condicional que verifique cuándo aparecen los dos puntos en el tiempo de natación actual (que se almacena en una variable denominada **`t`**)? Complete el espacio en blanco a continuación:

<img width="1117" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4ab813d3-0a34-4e24-81a2-9046f8e97d50">

<img width="1040" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/43244dbf-7b6f-44b6-b01b-d50af033984d">

**Asegúrese de escribir sus declaraciones `if` en forma Pythonic**

*Si llega a Python desde uno de los lenguajes tipo C, es posible que sus dedos insistan en codificar paréntesis adicionales alrededor de la condición. O tal vez sienta la necesidad de verificar explícitamente si la condición se evalúa como **True** (o **False**). No caigas en la tentación de hacer ninguna de las dos cosas. El intérprete de Python no te impedirá hacer lo que se muestra a continuación, ¡pero debes resistir, resistir, resistir!*

<img width="1088" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/258761c5-0d07-4b7d-b74d-fa3f8fbb41dc">

Hay una última tarea, y es determinar el código que se ejecuta cuando la condición se evalúa como **`False`**. Aquí está tu declaración **`if`** hasta ahora. ¿Puedes encontrar el código que se debe agregar al bloque de código **`else`**? Experimente en su notebook y luego agregue el código a continuación. Como siempre, nuestra solución está en la página.

<img width="1088" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/5bb2efbf-f783-4579-9127-325281b6eba9">

**P: Supongo que `True` y `False` son los valores booleanos de Python. ¿Puedo usar `1` y `0` en su lugar?**

**R**: Dentro de un contexto *booleano*, **`1`** se evalúa como **`True`** y **`0`** se evalúa como **`False`**. Dicho esto, los programadores de Python rara vez usan **`1`** y **`0`** de esta manera. Esto tiene que ver con el hecho de que cualquier valor en Python se puede utilizar dentro de un contexto booleano.

**P: ¿Existe alguna forma de comprobar qué valor se evalúa dentro de un contexto booleano?**

**R**: Sí, existe un BIF para eso. Se llama **`bool`**. Puede usarlo de forma interactiva (o en su código) para verificar la evaluación booleana de cualquier valor.

**P: ¿Qué pasa con el uso de `true` y `false`, es decir, todo en minúsculas? ¿Cómo se evalúan esos valores?**

**R**: No de la forma que cabría esperar. Usar **`true`** y **`false`** es una mala idea, ya que el caso es significativo. **`True`** es un valor booleano, al igual que **`False`**, mientras que **`true`** y **`false`** no lo son. Son nombres de variables válidos, no booleanos. Y como variables, existen, lo que significa que siempre se evaluarán como **`True`** (¿cómo puede algo que existe ser distinto de **`True`**?). Y sí, estamos de acuerdo en que algo llamado evaluación **`false`** como **`True`** es un poco extraño. Lección de vida: nunca uses **`true`** y **`false`** en minúsculas para representar un valor booleano, usa **`True`** y **`False`** en su lugar.

<img width="1046" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/90a7ad6f-506b-44fe-91a7-f3e6059dbc93">

Tenía una tarea final, que era elaborar el código que se ejecuta cuando la condición se evalúa como **`False`**. Hasta ahora se le proporcionó su declaración **`if`** y se le ocurrió el código que debe agregarse al bloque de código **`else`**. Esto es lo que usamos. ¿Su código es similar, igual o completamente diferente?

<img width="1093" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/cc51e565-be83-45f6-845e-930f00d22247">

<img width="1050" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a3a588cc-7a42-4e6a-9cef-a0a296d43a37">

**Ya casi llegamos. Una última edición.**

Asegúrese de agregar el código que se muestra arriba a su función **`read_swim_data`** dentro del módulo **`swimclub`** y no olvide guardar su archivo.

Su código **`swimclub.py`** debe ser el mismo que el de la página siguiente.

<img width="679" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/f36d615b-159d-4f8d-8805-5bde8d8ca47f">

<img width="928" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/7f865d72-ca15-4b81-8459-a52cb218823e">

Para utilizar la última versión del módulo **`swimclub`**, debe reiniciar su sesión de notebook. La forma más sencilla de hacer esto es borrar todas las celdas de su computadora portátil, reiniciarla y luego ejecutar cada celda. En la parte superior de VS Code, observe las siguientes opciones, en las que debe hacer clic en el orden que se muestran (1, luego 2 y luego 3):

<img width="930" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/ac02654e-ebb9-4df8-ad75-34d9848e2b80">

Una vez que complete los tres pasos anteriores, su bucle **`for`** producirá (con suerte) 60 líneas de salida. Esta vez no hay ningún error de tiempo de ejecución (suponiendo que ninguna otra celda de código genere un error):

<img width="1054" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/6d315409-20d0-4ff9-9e66-1752bc95a26e">

### ¿Terminaste con 60 archivos procesados?

Probablemente esté seguro de que su código más reciente está procesando todos los archivos en su carpeta de datos de natación. Nosotros también. Sin embargo, a menudo es bueno volver a comprobar estas cosas. Como siempre, hay varias maneras de hacer esto, pero numeremos los resultados de su bucle **`for`** agregando una enumeración, comenzando desde 1, a cada línea de salida que se muestra en la pantalla.

Para hacerlo, usemos otro BIF creado para este mismo propósito llamado **enumerate**:

<img width="980" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/17c5a9bc-eff5-473a-8c1f-8aa3e4cd3379">

<img width="912" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/5bfd1639-9da2-445a-9d27-fb00a19068c7">

**P: ¿Por qué tuvimos que reiniciar de nuevo? ¿Seguramente escribir `import swimclub` en una celda vacía recarga el código más nuevo del módulo previamente importado?**

**R**: (Esperamos que estés sentado…) No, no es así. Recuerde de nuestra discusión anterior que el intérprete de Python implementa un esquema de almacenamiento en caché agresivo para los módulos importados que, para todos los efectos, prohíbe efectivamente la reimportación de un módulo ya importado incluso si el código del módulo ha cambiado mientras tanto. Aunque existen algunas técnicas para anular este comportamiento predeterminado de almacenamiento en caché del módulo, según nuestra experiencia, lo más seguro es reiniciar siempre una computadora portátil después de un cambio en el código de un módulo. De esta manera, tiene la garantía de ejecutar el código que cree que está ejecutando.


## El código del Entrenador va tomando forma…

Su módulo **`swimclub`** ya está listo. Dado el nombre de un archivo que contiene una colección de cadenas de tiempo de natación, su nuevo módulo puede producir datos utilizables. El coach espera ver algunos gráficos de barras creados a partir de estos datos, así que profundicemos en la implementación de esa funcionalidad en el próximo capítulo.

Como siempre, puede continuar después de haber revisado el resumen del capítulo y luego intentar resolver el crucigrama de este capítulo.

<img width="927" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/3a8641f3-c087-4bcc-ba67-a087b2b7d7f4">

* La palabra clave **`def`** define una función nueva y personalizada.

* Cuando colocas código en su propio archivo (con una extensión **`.py`**), **creas un módulo**.

* Las sentencias **`import`** le permiten reutilizar un módulo, por ejemplo, **`import swimclub`**.

* Utilice un **fully qualified name** para invocar una función desde un módulo, por ejemplo, **`swimclub.read_swim_data`**.

* La sentencia **return** permite que una función personalizada devuelva un resultado.

* Si una función intenta devolver más de un resultado, la colección de valores devueltos se **agrupa** como una única **tupla**. Esto se debe al hecho de que las funciones de Python solo devuelven un único resultado.

* Una **tupla** es una **estructura de datos de secuencia inmutable**. Una vez que se asignan valores a una tupla, **la tupla no puede cambiar**.

* Las **listas** son como tuplas, salvo el hecho de que **las listas son mutables**.

* El módulo **`os`** (incluido como parte del PSL) permite que su código Python se comunique con su sistema operativo subyacente.

* Aunque las listas vienen con un método **sort** útil, tenga cuidado al usarlo ya que el orden se aplica in situ. Si desea mantener el orden actual de cualquier lista, utilice el BIF **sorted** (que siempre devuelve una copia ordenada de sus datos).

* Las listas vienen integradas con muchos métodos (no solo **sort**), incluido el útil método **remove**.

* El operador **`in`** es uno de nuestros favoritos y debería ser uno de los suyos también. Es excelente para realizar búsquedas (también conocido como *verificar membresía*).

* Cuando necesitas tomar una decisión, nada supera al combo **`if else`**.

* Un BIF a menudo pasado por alto, pero verdaderamente maravilloso, es el de **`enumerate`**. Se puede utilizar para numerar las iteraciones de cualquier bucle **`for`**.

<img width="923" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/16a07106-c7a3-406c-a5f2-abba0bc5d143">

El módulo **`swimclub`** contiene código que funciona, pero se puede mejorar agregando algunos comentarios bien colocados (y bien intencionados). Aquí hay otra versión de **`swimclub.py`** que hace precisamente eso. Depende de usted si decide agregar estos comentarios (o similares) a su código, pero tenga en cuenta que el código disponible en la página de GitHub de este libro los incluye.

<img width="966" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/abd9b099-0d15-4c91-b007-9149cad85333">

<img width="923" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/64558562-266b-4ea5-b213-fe1a60d188fd">

Las respuestas a las pistas se encuentran en las páginas de este capítulo y la solución, como siempre, en la página siguiente.

<img width="691" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/86b98938-3341-4f86-8e98-70f544c4e1b5">

<img width="1031" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/327db6e7-6a4b-4717-bc14-981883bf03c7">

<img width="1038" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/7261d1cc-a906-4b6b-8674-05252d8eb78a">

<img width="948" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/0c4ac577-7ab8-474d-b253-3cfde454dd7e">

<img width="692" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/348f7c44-b6ba-45ea-b971-3bf94447cc5c">








