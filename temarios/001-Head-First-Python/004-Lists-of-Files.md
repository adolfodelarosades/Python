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

<img width="1087" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c885aa36-3fb0-4d0e-91a0-a2440d5309be">


### ¿Qué puedes hacer con las listas?

Aquí está la salida mambo del combo **print dir** para su lista **`swim_files`**:

<img width="1040" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/2baa95cf-efc7-46dd-9e8f-e1cf2fa1008b">


<img width="1046" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/0231dfdc-689e-470d-a70c-7c97228102a8">


Es necesario tener cuidado con las listas integradas (especialmente si cambian su lista).

Si se frota las manos de alegría ante la perspectiva de utilizar el método de clasificación para reordenar su lista, dé un paso atrás. El método de clasificación realiza su reordenamiento "en el lugar", lo que significa que el nuevo orden sobrescribe (!!) lo que estaba anteriormente en la lista. El antiguo orden de la lista se pierde para siempre... y no se puede deshacer.

Si desea mantener el orden existente en su lista pero aún necesita ordenar, hay un BIF que puede ayudar aquí. El BIF ordenado devuelve una copia ordenada de los datos de su lista, dejando intacto el orden de la lista existente. Aquí tampoco se puede deshacer, ya que la lista original no se modifica.






