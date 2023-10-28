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

**Head First**: Pero… emm… err… mira la llamada a la función read_swim_data en la página anterior. Se devuelven seis resultados.

**Function**: No, no la hay, sólo hay UNO.

**Head First**: ¿Qué...?

**Function**: si miras de cerca, notarás esos paréntesis que rodean los seis valores de datos, ¿verdad?

**Head First**: Sí, pero…

**Function**: Sin “peros” al respecto. Esos paréntesis son una única tupla que contiene los seis valores de datos individuales. Como dije, solo se devuelve UN resultado, ya sea un resultado único o una única tupla con múltiples valores contenidos en él.

**Head First**: pero el código no convierte los seis valores de retorno en una tupla.

**Function**: Sí, el código no, pero yo sí. Lo hago automáticamente cuando veo que un programador intenta devolver más de UN resultado. Me lo puedes agradecer después.

**Head First**: No, te lo agradeceré ahora. Es importante saberlo. ¡Gracias por el chat!

**Function**: ¡Siempre estoy feliz de aclarar las cosas!


