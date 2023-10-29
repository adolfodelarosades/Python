# Capítulo 5 Formater Literales de String : *Crear Gráficos a partir de Datos*

<img width="893" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/67925a72-557f-4d67-8991-1f51eeb7233f">

**A veces son los enfoques más simples los que hacen el trabajo.**

En este capítulo, finalmente comenzará a producir gráficos de barras para el Coach. Harás esto usando nada más que **strings**. Ya sabes que los strings de Python vienen repletas de bondades incorporadas, y las **formatted string literals** de Python, también conocidas como ***f-strings***, mejoran lo que es posible de maneras bastante interesantes. Puede parecer extraño que estemos proponiendo crear gráficos de barras con texto pero, como estás a punto de descubrir, no es tan absurdo como parece. En el camino, utilizará Python para crear archivos e iniciar un navegador web con solo unas pocas líneas de código. Finalmente, el entrenador cumple su deseo: la generación automática de gráficos a partir de sus datos de tiempos de natación. ¡Hagámoslo!

<img width="948" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b0c26011-8925-47ff-b47b-df9a3fbe4272">


**Es fantástico escucharlo, ya que tenemos todos los datos que necesitamos.**

Ahora todo lo que tenemos que hacer es descubrir cómo convertir los datos en un gráfico de barras.

<img width="949" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/38b6da18-779a-4804-b269-cd24bb26a6dc">

<img width="1025" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/5667d1e7-c203-482d-8755-4415f6036205">

**Nosotros también.**

No hay otra opción. Es hora de sentarse con el entrenador.

<img width="1054" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/586de4da-5628-4117-9695-06a3bba2fe0d">

**Head First**: Hola, entrenador. Como seguramente sabrá, ahora tenemos todos los datos que necesitamos para comenzar a dibujar algunos gráficos.

**Coach**: Vaya, caramba, es genial escucharlo. Tenía muchas ganas de generar rápidamente mis gráficos de barras.

**Head First**: Supongo que has estado usando tu hoja de cálculo hasta ahora...

**Coach**: Bueno, si soy totalmente honesto, tengo tantos jóvenes nadando múltiples estilos que estoy un poco atrasado en mis análisis.

**Head First**: No se preocupe, entrenador. Volvamos a encaminarte. Si puede dedicar unos minutos, ¿tenemos algunas preguntas?

**Coach**: Dispara.

**Head First**: ¿El sistema es solo para usted o planea dejar que otros lo usen también?

**Coach**: Oh, no había pensado en poner mis gráficos a disposición de mis nadadores y sus padres. Emmm… que interesante. Supongo que tendría que decir que soy el usuario principal y que todos los demás son usuarios ocasionales.

**Head First**: Está bien, genial. Siguiente pregunta: ¿qué tipo de dispositivos crees que todos usarán para conectarse a su sistema?

**Coach**: ¿¡¿Dispositivos?!?

**Head First**: ¿Te gustan las computadoras de escritorio, portátiles, tabletas o lo que sea?

**Coach**: Oh, ya te tengo. Bueno, en mi caso, tengo mi gran PC de 25 pulgadas en mi oficina y tengo una computadora portátil tirada por aquí en alguna parte. Pero todos mis nadadores, cuando no están en la piscina, están haciendo una cosa: todos tienen la nariz pegada a sus teléfonos y veo a muchos de sus padres con esas cosas...

**Head First**: ¿iPads?

**Coach**: Sí, al menos eso es lo que creo que son. Tengo un teléfono inteligente pero lo uso principalmente para llamadas. ¡Los nadadores más jóvenes piensan que soy muy anticuado!

**Head First**: ¿Con qué frecuencia tienes una sesión de natación?

**Coach**: Nunca más de una vez al día, pero puede durar un poco, especialmente cuando los nadadores individuales quieren practicar y perfeccionar más de una de sus brazadas.

**Head First**: Entonces, ¿muchos datos?

**Coach**: Supongo. Como saben, la última sesión generó sesenta archivos de datos. Eso es bastante típico cuando tengo a todos en la piscina.

**Head First**: ¿Todos a la vez?

**Coach**: ¡Ja, no! Tenemos seis carriles en uso durante una sesión, pero solo se cronometra un carril con un solo nadador. Después de todo, sólo hay uno de mí.

**Head First**: Sí, por supuesto, lo siento... localiza al no nadador.

**Coach**: [Risas] ¿En qué más puedo ayudarte?

**Head First**: mirando su hoja de cálculo de muestra, ¿cuál es el detalle más importante que le gustaría conservar?

**Coach**: Me siento tentado a decir "todo", pero el detalle más importante para mí es el orden de los datos en la página en contraste con el orden de los datos presentados en el gráfico de barras. La lista de tiempos de natación está ordenada de arriba a abajo y se muestra en el orden en que se registraron. Sin embargo, el gráfico de barras muestra los datos con el tiempo registrado más reciente en la barra superior y el primer nado del nadador en la parte inferior. Es un poco contradictorio, pero así es como me gusta.

**Head First**: No te preocupes. Después de todo, eres el jefe. Gracias por la charla, entrenador. Es hora de volver al trabajo.

**Coach**: Yo también. Estaré en cubierta en cinco minutos. Tengo que correr. ¡Gracias!


<hr>

<img width="1043" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/7851575b-b0c4-41c2-9019-1125e7c280e7">

**Sam**: Basándonos en esa conversación, creo que estamos pensando en crear algo para la web.

**Alex**: ¿Cómo es eso?

**Sam**: Piensa en todos esos usuarios. Por supuesto, el entrenador está en su escritorio, pero todos los demás están en un dispositivo móvil. ¿Y sabes lo que puedes dar por sentado en un dispositivo móvil?

**Mara**: Sí, datos.

**Sam**: Más específicamente, conectividad web.

**Alex**: ¿Entonces ambos están pensando que todos interactuarán con el sistema a través de algún tipo de página web?

**Sam**: Sí.

**Mara**: ¿Un tipo de cosa con el mínimo común denominador?

**Sam**: Estoy pensando más en aprovechar el hecho de que todos tienen acceso a un navegador web en sus dispositivos, que está conectado a la red...

**Alex**: Entonces, ¿tendremos que crear un sitio web y escribir una gran cantidad de HTML?

**Sam**: Sí y no, porque vamos a construir todo lo que necesitamos con Python.

**Alex**: ¿Cómo es eso?

**Sam**: Python es fantástico cuando se trata de trabajar con texto. HTML es texto, aunque en forma estructurada. Cuando lo combinas con SVG, también puedes crear imágenes y texto.

**Mara**: ¡¿SVG?!? ¿En serio?

**Alex**: Nunca había oído hablar de eso...

**Sam**: SVG significa "Scalable Vector Graphics-Gráficos vectoriales escalables". Es un estándar web, se puede utilizar para definir casi cualquier elemento visual y, lo que es más importante, está basado en texto y está integrado en todos los navegadores web.

**Alex**: Entonces... para seguir adelante, ahora tengo que aprender HTML y esto de SVG...

**Sam**: No, ese no es el caso. Tengo todo el HTML y SVG que necesitarás, así que concentrémonos en crear el código Python que necesitamos.

**Alex**: Está bien, confío en ti, así que lo intentaré. ¿Qué pasa primero?

**Sam**: Echemos un vistazo rápido a HTML y SVG.

## Cree gráficos de barras simples con HTML y SVG

Ahora, antes de que alguien tenga un ataque de pánico, tenga en cuenta que la intención de este libro no es servir como manual ni para HTML ni para SVG.

**Código horneado listo**

<img width="1053" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/79e53dea-51ef-4dfe-8ead-ffc11a1d2c30">

Nuestra suposición es que usted tiene un conocimiento muy limitado de HTML y aún menos de SVG. Entonces, aquí hay un pequeño archivo HTML llamado **`bar.html`** que contiene HTML y SVG, y que dibuja un gráfico de barras cuando se ve en un navegador web. Continúe y tome **`bar.html`** de la página de GitHub de este libro (en la carpeta del capítulo 04):

https://github.com/headfirstpython/third

<img width="929" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/0bd9b0fe-8b8b-427b-8232-1fb72a6b88a9">

<hr>

<img width="837" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/ecf8e0f7-6734-49c2-b5e5-417a5d4ccd4e">

Con **`bar.html`** descargado y guardado en su carpeta de **Learning**, continúe y ábralo en su navegador web favorito. Esto es lo que vimos:

<img width="901" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/079ab92f-0760-4764-acce-5ab51119cb66">

<img width="861" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/3c8c84ba-5cdf-48f5-975b-2db1592d60f2">

**Apenas estamos comenzando.**

Aunque es fantástico ver al entrenador tan entusiasmado, es importante tener en cuenta que el archivo **`bar.html`** es una "maqueta" del gráfico de barras que eventualmente esperamos construir a partir de datos reales.

Hagamos coincidir su HTML y SVG con el resultado que ve en la pantalla:

<img width="838" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/995b0856-a490-4f91-a143-d8f6c2b1b182">

<img width="753" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/3bd21db0-9d0c-493a-bf98-3469ee020e03">

## Pasar de un gráfico simple a un gráfico de Coach

Esperemos que estés empezando a ver hacia dónde vamos con esto. El gráfico simple en **`bar.html`** no está a un millón de millas de un gráfico que necesita para satisfacer los requisitos del Entrenador:

<img width="717" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/78cd427c-039e-46d1-a8dc-db82040ddc85">

<img width="816" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/88dde67c-6913-4eb7-9c06-94d64a35c059">

**¡De hecho lo hay!**

Podemos escribir código Python para generar HTML y SVG sobre la marcha.

## Cree los strings que su HTML necesita en el código

Aquí está el primer fragmento de HTML desde **`bar.html`**, hasta el tag **`<h3>`** incluido. La mayor parte de este marcado se puede conservar, aunque el texto **`<title>`** y **`<h3>`** debe cambiar para que la página incluya los detalles del nadador.

<img width="1055" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/44fc1521-ec50-43d2-827a-8160308d57de">

Los datos de identificación del nadador se devuelven como parte de la tupla de su función **`read_swim_data`**. Una vez que tenga esos datos, puede crear un markup HTML como el que se muestra arriba con el texto reemplazado según sea necesario.

Como se muestra en la última línea de código, es posible crear el string que necesita, aunque puede resultar un poco complicado. Echar un vistazo:

<img width="1123" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/3d64eb5b-70d1-4208-a195-075dfd273236">

<img width="1039" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/150c9e4c-7f6b-4730-9964-f035ef537383">

Veamos esas líneas de código en acción. Cree un nuevo notebook (en su carpeta *Learning*) llamado **`Charts.ipynb`**, luego escriba las cuatro líneas de código desde la parte inferior de la última página, antes de presionar **Shift+Enter**. Suponiendo que el código se ejecuta sin errores, escriba el título en la siguiente celda y luego presione **Shift+Enter** nuevamente. Deberías ver lo que vemos:

<img width="1090" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/137b51f3-489b-4a17-9c0e-2617959e8cbe">

<img width="1041" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e8b96214-2151-412c-8649-e757a7a2fcee">

Para este ejercicio, puede asumir que el código de prueba anterior se ha ejecutado, así que continúe siguiéndolo en su notebook **`Charts.ipynb`**.

Eche un vistazo al fragmento de HTML que se muestra en la parte superior de la página anterior, luego escriba un código Python que cree una variable llamada **`html`**, asignando un string que contiene el fragmento de HTML de la página anterior a su nueva variable pero con el valor de **`title`** sustituido por el texto “**`A simple bar chart`**”.

Escriba el código que utilizó a continuación (y, pista, pista, el operador de concatenación de cadenas **`+`** debería ayudar):

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

<img width="1052" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/97a1a04a-bdee-4ddb-8570-c090d4ecf03e">

<img width="1109" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c3859a15-60bd-404e-bfd9-51555aec0391">

<img width="1064" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4c446373-af0b-4660-8699-8b4ebfa33a75">

Echemos un vistazo a estas dos afirmaciones en nuestro notebook:

<img width="1047" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b7270b34-0b47-42a8-9504-a3d188134071">

<hr>

## La concatenación de Strings no escala

A primera vista, los fragmentos de código de la página anterior parecen correctos, ya que el resultado producido es un fragmento de HTML con el valor de **`title`** sustituido correctamente.

¡Pero mire todos esos operadores de concatenación (**`+`**) y todas esas comillas dobles! Realmente necesitas prestar atención para ver lo que está pasando aquí.

Este tipo de código hace que a la mayoría de los programadores les duela la cabeza; hay mucho que vigilar mientras se determina lo que hace este código, y esto hace que las cosas sean aún más complicadas cuando se trata de realizar cambios.

<img width="1073" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e5544b2b-4812-40d4-ba50-869410d9f7a2">

<img width="1096" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a05b68f5-e58c-43d5-8fe0-f130a9b7de15">

**Sí, las f-strings ayudarán.**

Las **f-strings**, abreviatura de ***formatted string literals***, son muy interesantes (y ese es el término técnico correcto para usar aquí).

Una **f-strings** le permite construir un String sin tener que depender del problemático operador **`+`**. En su lugar, incrusta los valores de sus variables en la **f-strings**.

Aprendamos un poco más de un auténtico experto en **f-strings**.

<img width="1041" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a772628e-4ab6-4c03-850c-6303ffe47556">

**Head First**: Permítanme comenzar preguntando cómo se siente que lo llamen “muy genial”.

**f-string**: Un poco abrumador, para ser honesto. Soy el último de una larga lista de mecanismos de construcción de cadenas de Python y, aunque lo que hago siempre fue posible, parezco ser muy popular.

**Head First**: Creo que es más que eso: hoy en día es como si fueras la primera opción de todos cuando se trata de crear una cadena formateada.

**f-string**: Vaya, gracias por decir eso. Realmente solo estoy haciendo mi trabajo. Nada más y nada menos.

**Head First**: hablemos de tu forma de hacer las cosas en comparación con otra. Comparémoslo con el uso del operador **`+`** para crear una cadena formateada con concatenación.

**f-string**: OK, suena bien. Imagina que tienes dos variables definidas, una llamada **`first`** y otra llamada **`second`**. A la variable **`first`** se le asigna la cadena "Tim", mientras que a **`second`** se le asigna la cadena "O'Reilly".

**Head First**: ¿Con esos valores de cadena elegidos completamente al azar…?

**f-string**: ¡Pero por supuesto! De todos modos, es necesario crear una cadena (también conocida como *literal formateado-formatted literal*) que se evalúe como "Hi there, Tim O’Reilly!" Usando la concatenación de cadenas, este código funcionaría:

<img width="1033" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/24703b49-3b6e-4d13-8f3e-70d7dee1e3e0">

**Head First**: Y ese código no tiene nada de malo. Cuando lo ejecuto en mi Jupyter Notebook, muestra correctamente el mensaje.

**f-string**: Seguro que sí. Sin embargo, debes concentrarte en todos esos operadores **`+`** y esas cadenas adicionales, como **`" "`** y **`"!"`** para poder averiguar qué está pasando. Pero me complace admitir que funciona, aunque el código es un poco complicado.

**Head First**: Entonces, ¿qué harías diferente?

**f-string**: Eche un vistazo a mi versión del mismo literal de cadena formateado:

<img width="1057" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a491beb5-fa7f-4497-b6d6-9170f4bb8d15">

**Head First**: No se ve tan diferente... ¿y supongo que esto también muestra correctamente el mensaje?

**f-string**: Sí. Ahora, eche un vistazo más de cerca. ¿Viste el carácter "**`f`**" que antecede la cadena?

**Head First**: Ehhh… oh, sí, ahora lo veo. ¿Justo al principio?

**f-string**: Sí, el carácter "**`f`**" le dice a Python que lo que sigue es una *f-string*. ¿Y notaste el uso de llaves *dentro* de la cadena **`{`** y **`}`**?

**Head First**: ¿Esas llaves que rodean los nombres de las variable **`first`** y **`second`**? Sí, los vi de inmediato.

**f-string**: Genial. Cuando veo el nombre de una variable entre llaves, obtengo el valor de la variable y lo inserto en la cadena en lugar de las llaves y el nombre de la variable. Hay un nombre para este mecanismo: se llama ***interpolación variable - variable interpolation***.

**Head First**: Lo cual es simplemente una forma elegante de decir *insertar aquí*, ¿verdad?

**f-string**: Sí. Eso es lo que significa ***interpolación***.

**Head First**: Acabo de ejecutar su línea de código y me complace informarle que muestra exactamente el mismo mensaje que el código de concatenación de cadenas. Lo que no entiendo es por qué su mecanismo es mejor...

**f-string**: Bueno, una vez que entiendes lo que hacen las llaves, no hay nada más en qué concentrarte. Con el código de concatenación, tienes mucho más de qué preocuparte y, a medida que el formato de tu cadena se vuelve más complejo, se vuelve más difícil de entender, mientras que mi mecanismo, francamente, no. Es así de simple.

**Head First**: Lo cual supongo que lo dice todo. Gracias por la explicación, f-string.

**f-string**: No hay problema. Disfruté nuestra charla.

<img width="1040" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/9fa98d7c-72ca-4e58-ad51-d404e7b9203e">

Aunque acabas de conocer las f-strings, vamos a utilizarlas de inmediato. Aquí está el código que utiliza la concatenación para crear el título de su gráfico de barras. Su primera tarea es reescribir este código para usar una f-strings en su lugar.

<img width="1067" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/ad95f92f-9906-477d-80fe-33c57ae0549f">

Su segunda tarea es reescribir el código generador de HTML anterior para usar una f-string. Aquí está el código de antes:

<img width="1068" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/37d8c029-73c1-4c5b-9b86-a8b9cbe1df60">

<img width="1093" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/10c2b88f-a8b4-49c7-978c-fb4cbdf9b709">

Aunque acababas de conocer las f-strings, queríamos que las usaras de inmediato. Este código utiliza concatenación para crear el inicio de su página HTML de gráfico de barras. Su primera tarea fue reescribir este código para usar una f-strings en su lugar.

<img width="1080" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/1cc2402d-4998-4033-ac29-2f2f50fd02f9">

Su segunda tarea fue reescribir el código generador de HTML anterior para usar una f-strings. Aquí está el código de antes:

<img width="1084" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/86183e97-eeb1-4037-96c5-d0a6846b9382">

<img width="1047" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/7b8849ce-a53b-4fb3-ad61-4d2a2fee2d5c">

Ejecutemos las dos f-strings en su notebook para verlas en acción.

Primero, la f-strings que genera el valor del **`title`**:

<img width="1054" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/7a7b73ae-8f9f-4846-8791-91762fd8c5da">

Y, en segundo lugar, la f-strings generadora de HTML:

<img width="1054" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/5e0e3e32-8703-4046-b9fc-115886250e1b">

El resultado producido al mostrar su triple-quoted string se ve un poco extraño hasta que, es decir, lo muestra con el BIF **print**:

<img width="1044" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/de4173d8-3b15-4269-8282-d676f0bc3b24">

**P: ¿Las f-strings admiten especificadores de formato para que pueda rellenar con ceros, formatear números de punto flotante, alinear a la izquierda y a la derecha, etc.?**

**R**: Sí, pero no nos preocupemos por eso hasta que sea necesario. (Si no puede esperar hasta entonces, comience su exploración leyendo la sección correspondiente de la documentación de Python: https://docs.python.org/3/reference/lexical_analysis.html#f-strings).

## Las f-strings son una característica muy popular de Python

Una vez que entiendas cómo funcionan, comenzarás a ver todo tipo de lugares donde puedes usarlos. Un ejemplo de ello se encuentra cerca de la parte inferior de su código **`swimclub.py`**, donde tiene una línea de código similar a esta:

Refactorizar la línea de código anterior para usar una f-strings da como resultado esto:

<img width="1075" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/05267ea0-3f80-4803-8e28-0cd672d205b4">

que no sólo es más corto, sino que representa más claramente el formato del tiempo de natación. Tenga en cuenta que no es necesario realizar esa conversión de tipo explícita mediante una llamada al BIF **`str`**. Para ser honesto, sería difícil defender el uso de la línea de código que no emplea una f-strings.

<img width="1046" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/02c0d485-874f-42ee-9d4f-92d9cdd952b3">

Antes de continuar, abra su archivo **`swimclub.py`** en VS Code, luego ajuste la parte inferior de su función **`read_swim_data`** para usar una f-strings al crear la variable **`average`**. Una vez aplicado el cambio, asegúrese de guardar **`swimclub.py`**.

<img width="1086" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/8f0cf645-8f09-4cf8-8ba4-b94f7559b070">

<hr>

## ¡Generar SVG es fácil con f-strings!

Aquí está el fragmento HTML de **`bar.html`** que crea una barra SVG etiquetada en azul:

<img width="1091" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/3ff20360-a7c6-4634-8e8c-43aa0840518c">

Para utilizar Python para generar mediante programación los gráficos de barras del Coach, necesitarás crear tantas tags **`<svg>`** como veces haya en los datos de tu nadador. Probablemente haya decidido que lo que se necesita aquí es usar un bucle **for** en los datos de **`times`** devueltos por su función **`read_swim_data`**, y cada iteración de su bucle **for** usa una f-strings para generar una tag **`<svg>`** personalizada según sea necesario. Y haría bien en adoptar esto como estrategia.

<img width="1047" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/41f6acba-2748-4611-83dc-1f76058e0c75">

Tómese un momento para importar la versión más reciente del módulo **`swimclub`** en **`Charts.ipynb`**, luego invoque la función **`read_swim_data`** en la variable **`fn`**, que devuelve los datos de Darius. (Recuerde que es posible que necesite reiniciar su computadora portátil para asegurarse de que se importe el módulo editado más recientemente). Tómese un tiempo para estudiar los datos devueltos por su función (y no olvide verificar también el valor de **`_`**).

Teniendo en cuenta que el atributo **`width`** anterior debe establecerse en un valor extraído de estos datos, ¿puede detectar algún problema con los datos devueltos?

### Todos los datos están ahí, ¿o no?

Los datos devueltos por su función se ven bien. Pero, ¿estos datos por sí solos respaldan la creación de los tags **`<svg>`** que necesitas producir?

<img width="1097" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a60cbdfe-10e9-405d-bf81-7eb4386e4e85">

<img width="1114" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/bb7384a8-9f73-4614-a03f-c433be61a548">

**Sí, bien visto (en ambos temas).**

Aquí faltan algunos datos (pero hay una solución fácil para eso). Y sí, los valores numéricos son muy grandes (mucho mayores que 400), lo que puede dificultar el trabajo con ellos.

## Asegúrate de devolver todos los datos que necesitas.

Eche un vistazo a su función **`read_swim_data`** y observe cómo la lista de **`converts`** se completa con los equivalentes numéricos de los tiempos de natación basados en cadenas, antes de realizar el cálculo promedio. Luego, el valor promedio se devuelve a la persona que llama junto con todos los demás valores. Fundamentalmente, la lista **`converts`** no se devuelve a la persona que llama, principalmente porque no era necesario... *hasta ahora, claro*.

<img width="1067" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/bc2806c0-8f27-4c13-bd13-33bfc634d87e">

No es difícil solucionar este problema. Todo lo que necesitas es un pequeño cambio en la declaración de retorno de tu función para que se vea así:

<img width="1060" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/cb6e9b50-2eb6-4f48-af7c-8274db5ff84f">

Continúe y realice esta edición en el código de su módulo, asegurándose de guardar su trabajo. Luego, reinicie su computadora portátil una vez más para que cualquier importación utilice el código de su módulo actualizado.

Puede volver a ejecutar el código de su computadora portátil desde el principio presionando repetidamente **Shift+Enter**, o puede hacer clic en el botón **Run All** en la parte superior de VS Code.

### Tienes números ahora, pero ¿son utilizables?

Con el cambio realizado en el módulo **`swimclub`** y su computadora portátil reiniciada, su última función también devuelve los equivalentes numéricos de las cadenas de tiempos de natación:

<img width="1059" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/fc907fd8-a0f6-4758-876a-27320f574d63">

Aunque los datos devueltos parecen correctos, los números son un poco grandes y este es el segundo problema. Específicamente, el fragmento SVG anterior tiene un valor de ancho máximo de **`400`**:

<img width="1026" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/58fd82a9-d04d-43e9-8257-6512c39f7585">

Obviamente, ninguno de esos seis números mayores que 8000 es menor que 400. Y si usara esos números tal como están, sus rectángulos SVG probablemente se desplazarían hacia el lado derecho de la pantalla por un margen considerable.

Lo que se necesita aquí es alguna forma de reducir los números más grandes a un valor que se ajuste dentro del rango de 0 a 400, lo que parece que podría necesitar algunos cálculos complicados. ¡Ay!

Quiso la suerte que Head First Coders acaba de enviar un pequeño módulo de Python (llamado hfpy_utils), junto con un cuaderno (llamado HowTo.ipynb) que le muestra cómo convertir cualquier número a su equivalente dentro de algún otro rango. Copie ambos archivos en su carpeta de Aprendizaje y luego únase a nosotros en la parte superior de la página siguiente.

NOTA
Encontrará el módulo y el cuaderno incluidos con el material de descarga de este libro.





