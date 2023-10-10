# Capítulo 1 ¿Por qué Python?: Similares pero diferentes

<img width="859" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c2280e35-83ec-44c6-96a5-3591b1e7c5ea">

**Python comienza a contar desde cero, lo que debería resultarle familiar.**

De hecho, Python tiene mucho en **común** con otros lenguajes de programación. Hay **variables, bucles, condicionales, funciones** similares. En este, nuestro capítulo inicial, lo llevamos a un recorrido de alto nivel por los conceptos básicos de Python, presentando el lenguaje sin entrar demasiado en detalles. Aprenderá cómo crear y ejecutar código con **Jupyter Notebook** (ejecutándose dentro de VS Code). Verá cómo muchas funciones de programación vienen integradas en Python, que aprovechará para hacer las cosas. También aprenderá que, aunque Python comparte muchas de sus ideas con otros lenguajes de programación, la forma en que se manifiestan en su código Python puede ser, bueno, diferente. Ahora bien, no se haga una idea equivocada: estamos hablando de un bien diferente, no de un mal diferente. Continúe leyendo para obtener más información...

<hr>

**PYTHON EXPUESTO: LA ENTREVISTA DE HOY ES CON UN INVITADO MUY ESPECIAL: EL LENGUAJE DE PROGRAMACIÓN PYTHON.**

<img width="833" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/09728b53-4ddc-4018-9ce8-0581983b980d">

**Head First:**  Permítanme decirles que es un placer tenerlos aquí hoy.

**Python:** Vaya, gracias.

**Head First:** se le considera uno de los lenguajes de programación más populares que se utilizan en la actualidad. ¿Por qué crees que es?

**Python:** (Sonrojada) Dios... eso es un gran elogio. Supongo que diría que les agrado a muchos programadores.

**Head First:** Claramente. ¿Pero por qué crees que es así? ¿Qué te hace tan diferente?

**Python:** no creo que sea tan diferente de la mayoría de los otros lenguajes de programación. Tengo variables, bucles, condicionales, funciones, etc., como todos los demás.

**Head First:** Está bien, pero ¿a qué se debe su éxito?

**Python:** Supongo que es una combinación de cosas.

**Head First:** ¿Como…?

**Python:** Bueno... me han dicho que soy fácil de leer.

**Head First:** ¿¡¿Quieres decir que la gente sabe lo que estás pensando?!?

**Python:** Oh, eso es muy gracioso y muy divertido. Por supuesto, me refiero al hecho de que mi código es fácil de leer.

**Head First:** ¿Y por qué crees que es así?

**Python:** para empezar, no necesito punto y coma al final de mis declaraciones, y el uso de paréntesis alrededor de todo es necesario con menos frecuencia que con otros lenguajes de programación. Esto hace que mi código sea muy limpio, lo que ayuda a mejorar la legibilidad y la comprensión.

**Head First:** ¿Qué más?

**Python:** Bueno, está el tema de la sangría. En mi humilde opinión, recibo muchas críticas injustificadas por esto, ya que uso sangría con espacios en blanco para señalar bloques de código. Esto hace que mi código parezca consistente, limpio y legible. Además de esto, no es necesario discutir sobre la ubicación "correcta" de las llaves.

**Head First:** Entonces... ¿no hay llaves en tu código entonces?

**Python:** En realidad, simplemente no hay bloques alrededor. En Python, las llaves rodean los datos, no el código. Para indicar bloques, aplique sangría con espacios en blanco.

**Head First:** Eso es interesante... y me imagino que los programadores acostumbrados a lenguajes como C, C++, Java, C#, Go, Rust, etc., ¿luchan con esto?

**Python:** Sí, lamentablemente los viejos hábitos cuestan morir. Ahora bien, no solo estoy diciendo esto, sino que después de haber escrito código conmigo, casi nunca notarás el espacio en blanco, ya que se convierte en una segunda naturaleza muy rápidamente. También ayuda que los editores modernos sean expertos en Python y realicen la sangría por usted. Rara vez hay motivos para quejarse.

**Head First:** Por supuesto, la legibilidad es A Good Thing™, pero ¿su popularidad debe tener algo más que eso?

**Python:** también está mi biblioteca estándar: una colección de bibliotecas de código incluidas que ayudan con todo tipo de problemas de programación. Y, por supuesto, ¿está PyPI?

**Head First:** Py…P… ¿¡¿Qué?!?

**Python:** Py…P…I, que es una abreviatura de **Python Package Index**, un repositorio en línea y accesible globalmente de módulos Python de terceros que se pueden compartir. Estos ayudan a los programadores a abordar todos los problemas de programación imaginables que se puedan imaginar. Es un maravilloso recurso comunitario.

**Head First:** ¿Entonces esto de PyPI te permite explotar el código de otros programadores sin escribir el tuyo propio?

**Python:** Suena un poco cutre cuando lo dices así...

**Head First:** Lo siento, ¿quizás “apalancamiento” sea una mejor palabra?

**Python:** Sí, eso es todo: apalancamiento. Mi filosofía rectora es garantizar que los programadores solo escriban código nuevo cuando realmente sea necesario.

**Head First:** ¿Cómo es eso?

**Python:** una palabra: integrado.

**Head First:** Esas son dos palabras...

**Python:** Sí, pero ahí está el guión... de todos modos, la conclusión es que tengo más que mi biblioteca estándar integrada...

**Head First:** … estoy esperando…

**Python:** me refiero a mis otras funciones integradas. Para empezar, están los **BIF**, mis funciones integradas. Se trata de pequeños motores de funcionalidad genérica que funcionan en muchos lugares y situaciones.

**Head First:** proporcione a nuestros lectores un ejemplo rápido.

**Python:** considere **`len`**, que es una abreviatura de "longitud". Dale a **`len`** un objeto y te informará qué tan grande es el objeto.

**Head First:** Gracias a Dios estoy sentado.

**Python:** Ja, ja. Sé que suena trivial, pero **`len`** es un poco sorprendente. Dale a **`len`** una lista y te dirá cuántos objetos hay en la lista. Dale una cadena y **`len`** te dirá cuántos caracteres hay en la cadena, y así sucesivamente. Si un objeto puede informar su tamaño, **`len`** puede decirle de qué se trata.

**Head First:** ¿Entonces **`len`** es polimórfico?

**Python:** Ooooooh, esa es una jerga elegante, ¿no? Pero sí, como muchos de mis **BIF**, **`len`** funciona con muchos objetos diferentes de muchos tipos diferentes. En un instante, estoy de acuerdo en que **`len`** es polimórfico.

**Head First:** Entonces, ¿qué más te hace popular?

**Python:** Mi atractiva personalidad.

**Head First:** Más bien tu personalidad frívola. Vamos, intentemos mantener esto como un negocio.

**Python:** ¿Seguramente puedo divertirme un poco? Después de todo, mi nombre proviene de un grupo de comedia británico de los años 60.

**Head First:** ¿En serio? Ahora estás tirando de mi cadena.

**Python:** No te estoy diciendo ni una palabra de mentira. Búsquelo (consulte: https://docs.python.org/3/faq/general.html#why-is-it-call-python). No llevo el nombre de una serpiente. Mi nombre se debe al Circo Volador de Monty Python.

**Head First:** Si tú lo dices...

**Python:** Y soy partidario del spam con todo.

**Head First:** OK, ahora estás siendo tonto.

**Python:** Está bien, prometo que me portaré bien. Vamos, hazme otra pregunta.

**Head First:** ¿Cuál es su problema con los datos?

**Python:** Me encantan los datos. Ya sea trabajando con mis estructuras de datos integradas (éstas son realmente geniales, por cierto), o hablando con bases de datos, o obteniendo datos de la web, soy tu lenguaje de programación de datos.

**Head First:** Supongo que tu amor por los datos refleja tu posición número uno en el mundo del machine learning, ¿no?

**Python:** Supongo que sí. Sin embargo, para ser honesto, todo ese material de ML me parece un poco presuntuoso. Estoy igual de feliz ejecutando tus funciones, analizando tus bucles y ayudándote a realizar tu trabajo.

**Head First:** ¿Pero seguramente la combinación de Python, los datos y el machine learning es una combinación perfecta?

**Python:** Sí, supongo. Pero no todo el mundo necesita hacer ese tipo de cosas. No me malinterpretes, estoy encantado de ser un actor influyente en el campo de la IA, pero no es que eso sea todo lo que hago.

**Head First:** ¿Le importaría expandirse?

**Python:** Claro. En esencia, soy un simple lenguaje de programación de propósito general, que puede tener muchos usos. Estoy igualmente feliz ejecutando su última aplicación web como ejecutándolo en el Mars Rover. Para mí todo es sólo un código. Código bellamente formateado y fácil de leer. Eso es todo lo que es.

**Head First:** No podría estar más de acuerdo. Gracias, Python, por charlar con nosotros hoy.

**Python:** De nada. ¡Nos vemos!

<hr>

<img width="1041" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/434baf7a-48c1-4b90-81b3-eeec399dc923">

**Seguro. Conozcamos Python.**

Vamos a esperar para hablar del proyecto en el próximo capítulo. Por ahora, concentrémonos en llegar al punto en el que tenga una comprensión firme de algunos de los conceptos básicos, como el uso de su cadena de herramientas para crear, editar y ejecutar su código Python. También presentamos algunas de las características del lenguaje Python para brindarle la sensación que necesita. Mantendremos el ejemplo simple, usándolo principalmente para presentar una descripción general de Python en lugar de usar Python para resolver un problema en particular (habrá mucho de eso próximamente).

<hr>

**NOTA**

Y no se preocupe: todo lo mencionado en la descripción general de este capítulo se trata con más detalle más adelante en este libro.

<hr>

Como confirma la entrevista con Python, hay muchas razones para la popularidad de Python. Hemos enumerado las conclusiones que obtuvimos de la entrevista al final de esta página.

Dediquemos un tiempo a considerar estas conclusiones con más detalle. Una vez que haya examinado nuestra lista, tome un lápiz (sí, un lápiz) y ¡encuéntrenos en la parte superior de la página siguiente!

  1️⃣ **El código Python es fácil de leer.**

  2️⃣ **Python viene con una Standard Library.**

  3️⃣ **Python tiene funciones integradas (BIF) prácticas, potentes y genéricas.**

  4️⃣ **Python viene con estructuras de datos integradas.**

  5️⃣ **Python tiene el Python Package Index (PyPI).**

  6️⃣ **Python no se toma a sí mismo demasiado en serio.**

<hr>

**NOTA**

No subestimes la importancia de este último.

<hr>

**MIRA QUE FÁCIL ES LEER PYTHON**

Aún no sabes mucho sobre Python, pero apostamos a que puedes hacer algunas conjeturas bastante acertadas sobre cómo funciona el código Python. Eche un vistazo a cada línea de código a continuación y anote lo que cree que hace. Hemos hecho el primero para que pueda comenzar. No se preocupe si aún no comprende todo este código; las respuestas se encuentran en la página siguiente, así que siéntase libre de echar un vistazo si se queda atascado.

<img width="842" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/ff8ce9dd-8782-4461-85ef-c87766c08074">

<hr>

**MIRA QUE FÁCIL ES LEER PYTHON**

Aún no sabes mucho sobre Python, pero apostamos a que podrías hacer algunas conjeturas bastante acertadas sobre cómo funciona el código Python. Debías anotar lo que pensabas que hacía cada línea de código a continuación. Hicimos el primero para que puedas comenzar. ¿Cómo se comparan tus notas con las nuestras?

<img width="876" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/072a249f-29b5-4644-8a78-bb2cd40751c5">

<hr>

## "Preparándonos para ejecutar algún código"

Hay un poco de limpieza que realizar antes de ejecutar cualquier código.

Para ayudar a mantener las cosas organizadas, creemos una carpeta en su computadora llamada **Learning**. Puedes colocar esta carpeta en cualquier lugar de tu disco duro, siempre que recuerdes dónde la colocaste, ya que la usarás todo el tiempo. Si es necesario, coloque su nueva carpeta de **Learning** dentro de una carpeta de **HeadFirst** para distinguirla de cualquier otra carpeta de **Learning** que pueda tener.

Con su nueva carpeta de **Learning** creada, inicie VS Code.

<img width="818" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/fcfb8139-1f58-49d7-98e1-9defe247d010">

No entre en pánico si no ha instalado VS Code.

Eso no es gran cosa. Vuelva a la introducción de este libro y recorra las páginas que comienzan en Instalemos la última versión de Python. Allí encontrará las instrucciones para instalar VS Code y algunas extensiones necesarias.

Haga esto ahora y luego vuelva aquí cuando esté listo. Bueno, espera…

<hr>

**NOTA**

No te sientas mal si te saltaste la introducción. No eres el primero en hacer esto y no serás el último.

<hr>

<img width="915" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/47fdc7d0-9663-4298-adbb-2773ae0c6177">

Cada vez que trabaje con VS Code en este libro, abrirá su carpeta **Learning** según sea necesario. ***Haga esto ahora antes de continuar***.

## "Preparándose para su primera experiencia con Jupyter"

DE ACUERDO. Estás ejecutando VS Code y has abierto tu carpeta de **Learning**. Creemos un nuevo notebook seleccionando primero el menú **File**, luego seleccionando la opción de menú **New File…**. Se le presentarán tres opciones:

<img width="931" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/f0bc2f95-5a95-44a7-b307-fbca42685899">

VS Code crea y abre un nuevo *untitled* notebook llamado **`Untitled-1.ipynb`**, que aparece en la pantalla y se parece a esto:

<img width="831" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/5a6e0cec-524a-47c1-93c9-a3e21e3b06ba">

Redoble de tambores por favor. Ahora está listo para escribir y ejecutar código Python.

## "Introduzcamos algo de código en el notebook editor"

Su cursor está esperando en esa celda de código vacía. Antes de escribir algo, tomemos un momento para revisar las primeras cuatro líneas de código del ejemplo de este capítulo:

<img width="999" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e9482251-8d80-41f3-a3ef-fac467cc00e5">

Veamos qué sucede cuando escribe este código en su notebook.

<hr>

**TEST DRIVE**

<img width="824" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/440b8504-863d-472b-af8d-6ae855c30cf4">

Continúe y escriba esas cuatro líneas de código que se muestran arriba en su celda de espera. Esto es lo que vemos:

<img width="861" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/d45200a1-17c7-4ee2-af08-d9ead6f086a9">

<hr>

## "Presione Shift+Enter para ejecutar su código"

Cuando presiona **Shift+Enter**, se ejecuta el código en la celda actualmente seleccionada. Luego, el foco pasa a la siguiente celda de su notebook. Si no existe una “next cell”, Jupyter crea una nueva para usted:

<hr>

**NOTA**

Cuando vea "Shift+Enter" en este libro, presione y mantenga presionada la tecla Shift, luego toque la tecla Enter (antes de soltar ambas).

<hr>

<img width="893" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/9a17f5fb-8961-4584-af36-99945b229e1a">


<img width="969" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/19776cad-c09d-41fe-ba9d-c2163afa68b6">

<hr>

**EXERCISE**

<img width="863" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/d526e4c0-047c-481b-a7ea-f46a3340a054">

Su computadora portátil está esperando más código. Practiquemos un poco usando VS Code agregando el siguiente código a su notebook:

1. Escriba **`suits`** en su waiting cell, luego presione **Shift+Enter**. Anota aquí lo que sucede:

___________________________________________

2. Escriba el código para la función **`draw`** en la siguiente cell, luego presione **Shift+Enter** para ejecutar esa cell también. Aquí hay una copia del código de la función **`draw`** anterior:

<img width="840" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/f5270c0a-0984-4969-8d28-de6e6de4847a">

**P:** Estoy realmente sorprendido de que se hayan ejecutado esas tres primeras líneas de código. ¿Seguramente esas tres variables, **`suits`**, **`faces`** y **`numbered`**, deben declararse previamente con algún tipo de tipo?

**R:** Puede que así sea como funcionan otros lenguajes de programación, pero no Python. Las variables surgen en el momento en que se les asigna un valor, y ese valor puede ser de cualquier tipo. No es necesario declarar previamente la información de tipo, ya que Python calcula los tipos dinámicamente en tiempo de ejecución.

**P:** ¿Importa cómo ingreso mi sangría? ¿Puedo usar la tecla tabulador, la tecla espacio o puedo usar ambas?

**R:** Nos encantaría decirte que no importa, pero sí importa. Cuando se trata de sangrar su código Python, puede usar espacios o tabulaciones, pero no ambos (por lo tanto, no se pueden mezclar y combinar). Por qué esto es así es bastante técnico, por lo que no vamos a entrar en detalles sobre esto ahora. ***Nuestro mejor consejo es configurar su editor para reemplazar automáticamente los toques de la tecla de tabulación con cuatro espacios***. Y sí, existe una convención en la comunidad de programación de Python para sangrar cuatro espacios, no dos ni ocho. Por supuesto, puede ignorar esta convención si así lo desea, pero tenga en cuenta que la mayoría de los demás programadores de Python están programados para esperar una sangría de cuatro espacios. Por supuesto, siempre están los rebeldes que insisten en hacer lo suyo.

**P:** Entonces, ¿presionar Enter no ejecuta mi código? ¿Tengo que seguir usando la combinación **Shift+Enter**?

**R:** Sí, ya que está operando dentro de una computadora Jupyter notebook. Recuerde: cada cell de un notebook es como un pequeño editor integrado. Al presionar la tecla Enter, se finaliza la línea de código actual y luego se abre una nueva línea (para que pueda ingresar más código). Como la tecla **Enter** ya está en uso, la gente de Jupyter tuvo que idear otra forma de ejecutar una cell de código, decidiéndose por **Shift+Enter**.

Por cierto: en la última página de este capítulo, encontrará una práctica hoja de referencia recortada de los atajos de teclado de Jupyter más útiles. Por ahora, **Shift+Enter** es todo lo que necesitas saber.

<img width="831" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/cbb5e3ef-f858-4d93-bc15-b59d0cd1e054">

Su computadora portátil estaba esperando más código y usted debía practicar un poco usando VS Code agregando el siguiente código a su computadora portátil:

1. Debías escribir **`suits`** en tu celda de espera, luego presionar **Shift+Enter**, luego escribir aquí lo que sucede:

<img width="829" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/aa04a163-e8fa-4c3a-99cf-fa479469a6e5">

2. Luego debía escribir el código para la función **`draw`** en la siguiente celda y luego presionar **Shift+Enter** para ejecutar esa celda también. Esto es lo que vimos cuando completamos este ejercicio:

<img width="972" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/fd7b6d17-7166-435f-9c94-1629ef64f4e7">

<img width="863" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e2f8cfe2-67e0-479c-b7ce-ab245e74f3e7">

Saquemos algunas cards de tu baraja de cartas.

En la siguiente cell de código vacía, escriba **`print(draw())`** y luego presione **Shift+Enter**.

Hicimos esto en tres cells para confirmar que el código produce cards aleatorias y

<img width="917" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/3ee2feeb-8cb8-4be7-b8ea-40b174e90ba9">

<hr>

### Entonces… el código Python realmente es fácil de leer… y ejecutar

Además de Jupyter, existen otras formas de ejecutar código Python y aprenderá sobre algunas de ellas a medida que avance en este libro. Sin embargo, usar VS Code con Jupyter es, en nuestra opinión, la manera perfecta de leer, ejecutar, experimentar y jugar con el código Python cuando se aprende el lenguaje por primera vez. Así que prepárate para pasar mucho tiempo en Jupyter y VS Code.

Antes de continuar, tómate un momento para seleccionar **File** y luego **Save** en el menú VS Code para guardar tu notebook con el nombre **`Cards.ipynb`**.

<hr>

**NOTA**

¡Asegúrate de hacer esto ahora!

<hr>

<img width="866" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/807643d9-6bfc-41f6-831a-d7610326a9b8">

No, pero es una gran herramienta para usar cuando se aprende el lenguaje por primera vez, ya que Jupyter se conecta al **REPL** integrado de Python para ejecutar cada una de las celdas de su código. Aprenderá cómo ejecutar su código fuera de un notebook más adelante en este libro pero, por ahora, lo único de lo que debe preocuparse es de usar notebook dentro de VS Code (a medida que avanza).

<hr>

**NOTA**

Para obtener más información sobre qué es un **REPL**, consulte aquí: https://en.wikipedia.org/wiki/Read-eval-print_loop.

<hr>

<img width="888" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/25e1e1ba-eb57-4fc2-8417-7a7e749af0b6">

Sí. Python es un **intérprete** que está diseñado para ejecutar cada línea de código cuando la ve. Para ser técnicamente correcto, Python compila su código, pero todo sucede detrás de escena (para aliviarle la carga de hacerlo usted mismo). Todo lo que tienes que hacer es escribir tu código y luego ejecutarlo: Python se encarga de los detalles y el mecanismo **Shift+Enter** de Jupyter te facilita controlar cuándo ocurre la ejecución.

<img width="868" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c50d4136-f13f-4a2d-9b23-ea5d4e9f3c6f">

Sí, cuando vea el código presentado dentro de un cuadro gris, puede asumir que es un código que se ingresará en una celda de código en su notebook actual, listo para su ejecución con **Shift+Enter**. Para seguir, escriba el código en cada cuadro gris en su notebook, luego ejecútelo (según sea necesario) con **Shift+Enter**.

<img width="921" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/cc0faf78-bc23-44e4-b2ad-2c6b754d4380">

¡Bien! Y el bucle **`for`** de Python es lo que usarías. Echemos un vistazo rápido a cómo usarías **`for`** para hacer esto.


## “¿Qué pasa si quieres más de una card?”

Su función **`draw`** es un gran comienzo, ya que roba una carta de la baraja cada vez que se ejecuta la función. Pero, ¿qué pasa si quieres robar más de una carta?

Aunque sería un poco ridículo sugerir invocar manualmente la función **`draw`** tantas veces como sea necesario, la mayoría de los programadores recurren a un bucle. Aprenderá más sobre los bucles de Python más adelante en este libro. Por ahora, así es como usarías el bucle **`for`** de Python para ejecutar la función **`draw`** cinco veces:

<img width="1003" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4cbff551-2135-456b-963c-ad2bb1e4efec">

<img width="919" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/768e8787-d3d9-4d22-9d98-3cb397cf7997">

**Esa es la variable predeterminada(default) de Python.**

Es típico que la mayoría de los bucles tengan una variable de bucle asociada (siendo “**`i`**” un nombre favorito entre muchos programadores). Sin embargo, si el código de su bucle no usa el valor de esa variable, Python le permite usar el ***carácter de subrayado `_`*** en su lugar.

Cuando vea el guión bajo en el código, piense *“¡Ah, ja! Aquí se requiere sintácticamente una variable, pero su valor no se usa, por lo que la variable no tiene nombre”.*

<img width="844" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/3ce7c8bb-aa77-4f4f-a603-e9a99879e028">

Probemos su primer bucle de Python y veamos qué sucede. Le mostramos el código en un cuadro gris, así que escriba este código en la siguiente celda de código de su notebook y luego presione **Shift+Enter**:

<img width="909" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/ba4bae49-1d40-4e58-973b-d3c444ad6d69">

Y, como era de esperar, aparecen en pantalla los detalles de cinco cartas:

<img width="849" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/556e69a2-8169-4071-8a36-04858e5001e4">

<img width="855" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/fffa6d73-3ab1-4d9a-9d6f-56a36af5b91e">

**Sí, la misma carta se extrae dos veces.**

El problema aquí es que la función de sorteo devuelve la ***Queen of Diamonds*** dos veces. ¡Vaya!

Echemos un vistazo más de cerca a lo que está haciendo el sorteo para ver por qué sucede esto.

## "Eche un vistazo más de cerca al código de sorteo de la carta"

La función **`draw`** tiene solo tres líneas de largo, pero aún así tiene un gran impacto. Echar un vistazo:

<img width="867" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/9067c3ff-d3f6-47fd-b72f-7f6d74460121">

Lo sabemos: todos esos caracteres **`*`** que rodean la palabra "aleatoriamente" en esas anotaciones no fueron una pista suficiente, ¿verdad? Aunque el código **`draw`** logra seleccionar una carta al azar, no protege contra devolver la misma carta dos veces. Después de todo, en la mayoría de los juegos de cartas, una vez que se selecciona una carta de la baraja, rara vez se vuelve a colocar directamente, ¿verdad? Si se tratara de un código de dibujo de tarjeta "real" (a diferencia de un ejemplo inventado diseñado para respaldar la descripción general de Python de este capítulo), probablemente usaríamos una estructura de datos diferente a las arrays que se usan actualmente, ¿verdad?

<img width="848" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/5b2d601c-1f31-426d-a9e1-9e5084ab7e9b">

Si le pidieran que ideara una estructura de datos que modelara mejor una baraja de cartas, ¿qué estructura de datos elegiría?


## "Los 4 grandes: list, tuple, dictionary y set"

El excelente soporte integrado de Python para estructuras de datos es legendario y a menudo se cita como la razón principal por la que a la mayoría de los programadores de Python les encanta Python.

Como este es su capítulo inicial, no lo sobrecargaremos con ningún tipo de discusión en profundidad sobre estas estructuras de datos en este momento. Hay muchas páginas (de hecho, capítulos enteros) dedicadas a *The Big 4* más adelante en este libro.

Aunque no hemos mencionado específicamente su uso, ya has encontrado listas y tuplas. Si bien anteriormente se refirió descaradamente a estos como arrays, cada una de estos "arrays" son, de hecho, una **list** de Python genuina y honesta:

<img width="829" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/867c529d-baef-4746-896e-819f5811f174">

También has visto una buena cantidad de tuplas. Cada vez que invocas la función **`draw`**, te devuelve una **tupla**:

<hr>

**NOTA**

Aquí hay una pregunta rápida: ¿cómo pronunciarías “tupla”? ¿Rima con “pareja(couple)” o rima con “cuádruple”? En realidad, nadie lo sabe.

<hr>

<img width="920" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/921e3c07-9a45-4a61-8811-644ee130e192">

Sería perdonable por pensar que las tuplas se ven un poco raras, y tendríamos que estar de acuerdo en que pensamos que también se ven un poco raras. No dejes que esto te preocupe.

Aprenderá más sobre listas y tuplas más adelante en este libro. Aunque tanto las listas como las tuplas tienen sus usos, no son una buena opción cuando se trata de modelar una baraja de cartas. Aquí se necesita alguna otra estructura de datos. ¿Pero cual?

<hr>

**NOTA**

Pista: hay una gran pista en el título de esta página.

<hr>

## “Modela tu baraja de cartas con un set”

Los conjuntos en Python son conjuntos similares a los de la clase de matemáticas: ***contienen una colección de valores únicos donde no se permiten duplicados***.

<hr>

**NOTA**

No te preocupes si adivinaste “diccionario” (después de todo, siempre sería uno u otro). Aprenderá todo sobre los diccionarios más adelante en este libro.

<hr>

Los set en Python también hacen que sea especialmente conveniente agregar y eliminar objetos. Y sí, otras estructuras de datos también pueden agregar o eliminar objetos, pero, normalmente, primero hay que encontrar el objeto y luego eliminarlo. O debe buscar el objeto para asegurarse de que no esté ya en la estructura de datos antes de agregarlo. En ambos casos, *son dos operaciones para agregar y dos operaciones para eliminar (con las otras estructuras de datos)*.

No ocurre lo mismo con los sets.

***Una sola operación agrega al conjunto y otra operación lo elimina, lo que le libera de la necesidad de realizar toda esa búsqueda***. En nuestra opinión, utilizar un set para modelar una baraja de cartas es una opción casi perfecta.

Continúe siguiendo su notebook **`Cards.ipynb`** mientras primero creamos un conjunto vacío, luego aprendemos un poco sobre los conjuntos, antes de agregar las 52 cartas y luego retirar las cartas de la baraja según sea necesario.

<img width="855" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/580d1c9e-bc64-46b9-ae23-af79c29d030f">

Ahora que su conjunto existe y está asignado a una variable (con un nombre bastante imaginativo) llamada **`deck`**(baraja), aprendamos un poco sobre él. Dos de las funciones integradas (BIF) de Python ayudan aquí: **`type`** y **`len`**:

<img width="865" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/9af143c0-ed6a-4448-9e72-d646674d72e0">

**"BIF" es la abreviatura de "built-in function(función incorporada)"**.

**Ahora que tu conjunto existe, ¿cómo puedes determinar qué puedes hacer con él? Bueno… hay un BIF para eso.**


## “El print dir combo mambo”

Cuando se proporciona el nombre de cualquier objeto Python, el **dir** BIF devuelve una lista de los atributos del objeto que, en el caso de la variable **`deck`**, son los atributos asociados con un objeto establecido.

Como puede ver (a continuación), hay una gran cantidad de atributos asociados con un set de Python. Observe cómo la salida del **dir** se combina con una llamada al **print** BIF, lo que garantiza que la salida mostrada se dibuje en la pantalla en lugar de hacia abajo, lo que reduce la cantidad de desplazamiento requerido por sus pobres dedos. Puede que esto no sea algo para bailar pero, ¡oye!, todo ayuda.

<img width="897" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/ac290405-db8c-42b3-9cb0-498ba928ee79">

<img width="916" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/fa3f5798-2762-4287-a9a2-3b254e4c42d6">

Aquí hay una regla simple a seguir al mirar el resultado del **print dir**: *por ahora, ignore los atributos que comienzan y terminan con un doble guión bajo*. Aprenderás por qué existen más adelante en este libro, pero, por ahora, ¡ignora, ignora, ignora!


## "Obtener ayuda con dir’s output"

Puede que no creas esto al verlo, pero probablemente usarás el **dir** BIF más que cualquier otro BIF cuando trabajes con Python, especialmente cuando experimentes dentro de un Jupyter notebook. Esto se debe a la capacidad de **dir** para revelar la lista de atributos asociados con cualquier objeto. Normalmente, estos atributos incluyen una lista de métodos que se pueden aplicar al objeto.

Aunque puede ser tentador (aunque un poco absurdo) ejecutar aleatoriamente cualquiera de los métodos asociados con la variable **`deck`** para ver qué hacen, un enfoque más sensato es leer la documentación asociada con cualquier método...

<img width="932" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/6ca2b3d5-2696-42ed-a0e6-da9f1c4ab55a">

Ahora, no se preocupe: no vamos a enviarlo a leer miles de páginas de documentación de Python en línea. Esa es la labor de **help** del BIF:

<img width="843" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/d9b7a644-1313-4d9b-bdbb-3ecda5657359">


## “Rellena el set con cartas”

En la parte inferior de la última página (y por suerte) utilizamos el **help** BIF para ver la documentación de Python para el método **`add`**, que está integrado en cada conjunto de Python. Sabiendo lo que hace **`add`**, veamos un código que utiliza los datos de cartas "sin procesar" de antes para construir una baraja de cartas:

<img width="789" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/62366a5e-840f-423c-af4d-ed56347fed83">

<img width="801" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4428d311-9193-4e1d-a7a0-90c34c37da37">

**Si lo hicimos. Y eso está bien.**

Las estructuras de datos de Python pueden crecer y reducirse según sea necesario, por lo que ***no es necesario declarar previamente su tamaño***.

El intérprete de Python maneja todos los detalles subyacentes por usted. La memoria se asigna y desasigna dinámicamente según sea necesario, lo que le permite crear el código que necesita.

## “Esto ahora parece una baraja de cartas”

Ahora que tu baraja de cartas es un conjunto, puedes modelar mejor su comportamiento.

Lamentablemente, seleccionar aleatoriamente una carta de la baraja es complicado por el hecho de que la técnica de elección aleatoria mencionada anteriormente en este capítulo no funciona con conjuntos. Es una lástima, ya que hubiera sido bueno usar **`random.choice(deck)`** para elegir una carta de tu baraja pero, lamentablemente, esto no funcionará.

<hr>

**NOTA**

Por ahora, no te preocupes por el motivo.

<hr>

No es para preocuparse. Un truco rápido le permite convertir primero una copia de su conjunto de tarjetas en una lista, que luego puede usarse con **`random.choice`**. No podría ser más sencillo:

<img width="1054" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/271904a5-6ab1-4b5f-a4b0-d48b26db662a">

Habiendo seleccionado una carta (es el *Ace of Spades(As de Picas)* para nosotros, pero probablemente sea una carta diferente si sigues la carta), realmente deberíamos eliminar la carta de la baraja para que las siguientes elecciones aleatorias ya no la seleccionen.

<img width="1090" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/6bf9fca9-b8e2-48bc-9570-6848adefb408">


## “¿Qué es exactamente “card”?”

Si se pregunta cuál es la variable **`card`**, no se olvide del **type**, que informa el tipo de valor actualmente asignado a la **`card`**:

<img width="1073" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/9f904193-7c6a-4bf8-868b-e83f30c45ba7">

<img width="1049" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/ffbdbf18-6617-424a-b086-c1fae660b825">

Ahora que has visto cómo seleccionar aleatoriamente una carta de tu conjunto, así como eliminar una carta, reescribamos la función **`draw`** para que funcione con el set **`deck`** (a diferencia de esas listas). En el espacio siguiente, proporcione las tres líneas de código que agregaría a su nueva función **`draw`**. La primera línea de código selecciona aleatoriamente una tarjeta del conjunto, la segunda elimina la tarjeta seleccionada del conjunto, luego la tercera (y última) línea de código devuelve la tarjeta seleccionada al llamador de la función:

<img width="942" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/fc47603d-a23e-433f-908c-b1caeb2e2274">

Ahora que habías visto cómo seleccionar aleatoriamente una carta de tu conjunto, así como eliminar una carta, era hora de reescribir la función **`draw`** para que funcione con el set **`deck`** (a diferencia de esas listas). En el espacio siguiente, debías proporcionar las tres líneas de código que agregarías a tu nueva función **`draw`**. La primera línea de código selecciona aleatoriamente una tarjeta del conjunto, la segunda elimina la tarjeta seleccionada del conjunto, luego la tercera (y última) línea de código devuelve la tarjeta seleccionada al llamador(caller) de la función:

<img width="963" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/00d89eb3-245a-4b7c-85c7-33837016ae65">

<hr>

**NO HAY PREGUNTAS TONTAS**

**P: ¿Supongo que los dos puntos al final de la línea de `def` de la función son importantes?**

**R:** Sí, mucho. Conocerá los dos puntos en detalle más adelante en este libro. Por ahora, considérelo como una parte de la sintaxis requerida que informa a todos que un bloque de código sangrado está a punto de comenzar (en la siguiente línea).

**P: ¿Qué pasa con la versión anterior de `draw`? ¿Aún puedo acceder a él si es necesario?**

**R:** La nueva versión de **`draw`** reemplaza a la anterior, que desapareció en el éter digital (en una nube de humo) y nunca más se supo de ella.

**P: Sé que esta pregunta no tiene nada que ver con el código, pero me molesta... ¿por qué la ortografía divertida de Jupyter? ¿No se escribe el planeta con “i”?**

**R:** Sí, el planeta se escribe con una “i”, pero la herramienta no lleva el nombre del planeta.

Jupyter lleva el nombre de los tres lenguajes de programación que admitía inicialmente, a saber, **Julia**, **Python** y **R**. Es por eso que las letras "py" se incluyen en el nombre.

Ese "py" también es una referencia a la extensión de nombre de archivo preferida de Python para archivos de código, que es ***.py***.

**P: La extensión del notebook es bastante complicada: `.ipynb`. ¿Esto significa algo en particular?**

**R:** Sí. Es una abreviatura del ***ipython notebook format***. ¿No te alegra haber preguntado?

<img width="927" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c2502251-fc66-4e7a-bf52-38cc7de32bd6">

Comprobemos que su nueva función **`draw`** esté funcionando como se esperaba.

Continuando trabajando dentro del notebook de este capítulo (**`Cards.ipynb`**), escriba el código para su nueva función **`draw`** en la siguiente celda de código, luego presione **Shift+Enter** para definirlo:

<img width="931" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/9d6aa442-456a-4773-a55b-539599b706de">

Invoque su nueva función con una llamada a **`print`** BIF, que muestra su carta seleccionada al azar en la pantalla:

<img width="982" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/04c968af-6cb0-441d-8adf-95063e05bf80">

Una rápida llamada al **len** BIF confirma que la baraja de cartas tiene una carta menos que antes:

<img width="916" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/3b81f629-28c9-4972-95da-3c6562e564eb">

<img width="938" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/7754223e-9d74-4476-9a33-2fb6ec5ababd">

**Sí. Y es casi demasiado fácil.**

Aunque ya has visto la palabra clave **in** como parte de tu bucle **for**, por sí sola es algo importante.

Voltee la página para obtener más información sobre esta *superpotencia de Python*.


## "¿Necesitas encontrar algo?"

Como se mencionó al final de la última página, ya conoce la palabra clave **in**:

<img width="954" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/cc265e4a-1d38-489b-9d95-68ad5b5a6d55">

Pero la palabra clave **in** puede hacer mucho más: puede ***buscar(search)***.

Dada cualquier estructura de datos de Python, podemos realizar una *membership test(prueba de membresía)* y verificar si se encuentra un valor en ella. Comprobemos si el *As de Corazones(Ace of Hearts)* todavía está en nuestra baraja. Asegúrate de seguir las instrucciones y recuerda usar **Shift+Enter** para ejecutar cada celda:

<img width="1103" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/f8e8ae7a-1500-4818-801f-bbde18aa9c0a">

## “Hagamos una pausa y hagamos balance”

Recuerde la lista extraída de la entrevista con Python al comienzo de este capítulo. Aunque esta descripción general no aborda esta lista en orden (qué rebeldes somos), en esta etapa puedes marcar los puntos que te han presentado:

1️⃣ El código Python de la imagen es fácil de leer. ✔️

2️⃣ Image Python viene con una biblioteca estándar.

3️⃣ Image Python tiene funciones integradas (BIF) prácticas, potentes y genéricas. ✔️

4️⃣ Image Python viene con estructuras de datos integradas. ✔️

5️⃣ Image Python tiene el índice de paquetes de Python (PyPI).

6️⃣ Image Python no se toma a sí mismo demasiado en serio.

<img width="1105" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/77b028a4-43e4-44e2-89e4-98a6f7693909">

**¡Genial, estamos progresando!**

Ahora... en una ruptura bastante impactante con la tradición, veamos los tres puntos restantes en el orden en que aparecen en la lista.

Primero está la ***Python Standard Library***.


## "Python viene con una rica Standard Library"

***The Python Standard Library (PSL)*** es el nombre que se utiliza para referirse a una gran colección de functions, types, modules, classes y packages incluidos con Python. Se garantiza que estarán allí una vez que se instale Python.

<img width="1086" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/5e22e35d-ed79-46ab-b371-042f62569c28">

Cuando escuchas a los programadores referirse a Python como si viniera con “baterías incluidas”, se están refiriendo en parte al PSL. Hay mucho que hacer: https://docs.python.org/3/library/index.html.

**En este libro, "PSL" es la abreviatura de "Python Standard Library".**

<img width="1111" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/d71dbfd3-7cc2-4b89-9c58-0bf94fbb2944">

<img width="1142" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e7d82844-78cc-4ed1-ab2e-1127d707a0c6">

**Sí. Y todos hemos estado allí.**

Abres tu último regalo y te das cuenta de que no viene con todo lo que necesitas: *faltan* las pilas. Cue la música triste...

Python, por otro lado, rara vez decepciona ya que PSL viene con muchas bibliotecas integradas. Ya has visto (y usado) la library **`random`**, pero hay mucho más. Miremos más de cerca.

<hr>

**¿QUIEN HACE QUE?**

Sabemos que todavía tienes que ver el PSL con gran detalle pero, para darte una idea de lo que incluye, hemos ideado una pequeña prueba. Sin echar un vistazo a la documentación mencionada en la última página, considere los nombres de algunos de los módulos del PSL que se muestran a la izquierda de esta página. Toma tu lápiz y dibuja una flecha que conecte el nombre del módulo con lo que crees que es la descripción correcta a la derecha. Para comenzar, el primero ya está hecho para usted. A ver cómo te va con el resto. Nuestras respuestas están en la página siguiente.

<img width="845" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/57273743-68b6-4178-aeee-76be94e95350">

<hr>

**¿QUIÉN HACE QUÉ SOLUCIÓN?**

<img width="757" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/bf644106-2624-4ed4-8bfd-66a28c39500f">

<hr>

<img width="975" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/6da474ee-cac0-4442-84fa-b8b24b6e7769">

**Seguro que están pasando muchas cosas allí.**

Nuestro objetivo es darle una idea de lo que hay en el PSL, no que usted lo explore con gran detalle.

<hr>

**NOTA**

Para ser claros: no estamos hablando de café…

<hr>

No se espera que usted sepa todo esto, ni recuerde lo que hay en la última página, aunque hay tres puntos que debe considerar.

  1️⃣ **Sólo has arañado la superficie.**

El PSL tiene mucho que ofrecer, y lo que hay en las dos páginas anteriores proporciona un breve vistazo. A medida que avance en este libro, le indicaremos los usos del PSL para que no se pierda ninguno.

  2️⃣ **El PSL representa una gran cantidad de código probado que no es necesario escribir, solo utilizar.**

Como el PSL existe desde hace décadas, los módulos que contiene han sido probados hasta su destrucción por legiones de programadores de Python en todo el mundo. En consecuencia, puede utilizar los módulos PSL con confianza.

  3️⃣ **Se garantiza que el PSL estará allí, por lo que puede confiar en que sus módulos estarán disponibles.**

Aparte de algunos casos extremos muy específicos (como un pequeño microcontrolador integrado que proporciona un entorno Python mínimo), puede estar seguro de que su código que utiliza cualquier módulo PSL será portátil a otros sistemas que también admitan PSL.


## “Con Python sólo escribirás el código que necesitas”

El PSL es un excelente ejemplo de cómo Python trabaja arduamente para garantizar que solo escriba código nuevo cuando sea absolutamente necesario. Si un módulo del PSL resuelve su problema, úselo: resista la tentación de codificar todo desde cero.

Y cuando se trata de reutilizar código, hay más que PSL para extraer.


El ecosistema de paquetes de Python es para morirse
No contenta con lo que ya está incluido en PSL, la comunidad Python admite un repositorio centralizado en línea de módulos, clases y paquetes de terceros. Se llama Índice de paquetes de Python y se encuentra aquí: https://pypi.org.

Conocido como PyPI (y pronunciado “pie-pea-eye”), el índice es una enorme colección de software. Una vez que encuentre lo que está buscando, la instalación es muy sencilla y obtendrá mucha práctica en la instalación desde PyPI a medida que avance este libro.

Por ahora, tómate diez minutos para visitar el sitio de PyPI (que se muestra a continuación) y echa un vistazo.

## “Justo cuando pensabas que habías terminado…”

