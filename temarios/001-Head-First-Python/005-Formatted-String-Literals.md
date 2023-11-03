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

Quiso la suerte que *Head First Coders* acaba de enviar un pequeño módulo de Python (llamado **`hfpy_utils`**), junto con un notebook (llamado **`HowTo.ipynb`**) que le muestra cómo convertir cualquier número a su equivalente dentro de algún otro rango. Copie ambos archivos en su carpeta de *Learning* y luego únase a nosotros en la parte superior de la página siguiente.

<hr>

**NOTA**

Encontrará el módulo y el notebook incluidos con el material de descarga de este libro.

<hr>

<img width="1045" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e718585b-4c31-4737-bad3-4b8e1aea53f6">

<img width="639" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/7e1c1bdc-2722-49e0-8e9b-b9666c5b8831">

## Escalar valores numéricos para que encajen

<img width="1035" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/0a8e3e24-7e1c-4257-9695-b983188fe05c">

No es necesario que comprenda cómo funciona el código del módulo **`hfpy_utils`** (ni se le pedirá que lo cambie de ninguna manera).

Sin embargo, es necesario comprender qué hace la función **`convert2range`**. La prueba de manejo en la página anterior demostró la función en acción, convirtiendo los valores (bastante grandes) de centésimas de segundo en números en un rango de 0 a 400.

Puede aprender a controlar cómo funciona la escala observando la firma de la función **`convert2range`**:

<img width="1032" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/2cf07239-ff6a-4d34-9766-0548fa42aaf6">

Y para aquellos de ustedes que tienen una urgente necesidad de verlo, aquí, en todo su esplendor, está todo el código del módulo **`hfpy_utils`**:

<img width="1054" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a646e4a1-8207-4627-983c-6f7dd1128175">

<img width="1124" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/9c321c92-06c3-4961-9666-ad60dd30ec75">

**Sí, no lo hemos olvidado.**

Y podemos ver de dónde viene el entrenador. Parece que nos estamos desviando de la generación de los gráficos de barras necesarios, pero no temas: todo está a punto de concretarse.

<img width="912" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/9caea642-4cc5-4c5b-a447-ebe8d43818e6">

Ahora que ha visto las f-strings en acción y ha estudiado el código en el notebook **`HowTo.ipynb`**, tomemos un tiempo para crear el código necesario para generar los tags SVG para cada uno de los tiempos de natación del nadador actual. Revisaremos esto paso a paso, mientras usted piensa en lo que se requiere, experimenta con el código en su notebook y luego (toma su lápiz y) escribe el código que necesita en los espacios a continuación.

Comience escribiendo una línea de código que cree tres variables a partir de los datos del nadador llamando a la función **`read_swim_data`**, creando la lista **`times`**, la variable **`average`** y la lista **`converts`**:

__________________________________________________________________

Crea otra variable llamada **`from_max`**, asignándole el valor máximo de la lista **`converts`**:

__________________________________________________________________

Importe el módulo **`hfpy_utils`**, luego cree una nueva variable llamada **`svgs`**, inicializándola en una cadena vacía:

__________________________________________________________________

__________________________________________________________________

Supongamos que existe un valor llamado **`n`** que contiene un valor de ranura que se indexa en su lista **`converts`**. Proporcione una línea de código que cree una variable llamada **`bar_width`** y la establezca en un valor de **`n`** que escala de **`0-from_max`** a **`0-400`**:

__________________________________________________________________

<hr>

**NOTA**

Sugerencia: estudie el código en el cuaderno “**`HowTo.ipynb`**” para obtener una aproximación cercana al código que necesita aquí.

<hr>

__________________________________________________________________

Escriba la primera línea de un bucle **`for`** que itere sobre una lista de tiempos enumerados, creando dos nuevas variables de bucle llamadas **`n`** y **`t`**:

__________________________________________________________________

Aquí está el fragmento de SVG tomado del archivo **`bar.html`**:

<img width="912" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b05bc43b-68af-469e-8b77-3d580c34e1ab">

Cree una f-string multilínea con comillas triples que utilice las variables **`bar_width`** y **`t`** de la última página para crear una etiqueta SVG para el tiempo de natación actual:

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

Con su cadena f-string, muestre el código que la agrega al final de la variable **`svgs`** creada en la última página:

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________


<img width="936" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/98d3f44f-4ec2-4ee6-b797-d606edcb2538">


Ahora que ha visto las f-strings en acción y ha estudiado el código en el notebook **`HowTo.ipynb`**, tomemos un tiempo para crear el código necesario para generar los tags SVG para cada uno de los tiempos de natación del nadador actual. Revisaremos esto paso a paso, mientras usted piensa en lo que se requiere, experimenta con el código en su notebook y luego (toma su lápiz y) escribe el código que necesita en los espacios a continuación.

Comience escribiendo una línea de código que cree tres variables a partir de los datos del nadador llamando a la función **`read_swim_data`**, creando la lista **`times`**, la variable **`average`** y la lista **`converts`**:

<img width="948" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/bfd62607-bccb-4209-adb8-8043d005fa8c">

Crea otra variable llamada **`from_max`**, asignándole el valor máximo de la lista **`converts`**:

<img width="929" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4ff30bdb-3a08-43a3-b758-2b0bff12d6b8">

Importe el módulo **`hfpy_utils`**, luego cree una nueva variable llamada **`svgs`**, inicializándola en una cadena vacía:

<img width="921" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4baa3bc0-f9c2-4224-b7ff-9ff010455a84">

Supongamos que existe un valor llamado **`n`** que contiene un valor de ranura que se indexa en su lista **`converts`**. Proporcione una línea de código que cree una variable llamada **`bar_width`** y la establezca en un valor de **`n`** que escala de **`0-from_max`** a **`0-400`**:

<img width="929" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/fe70688d-dc14-468a-b7aa-a9f73e3188c3">

Escriba la primera línea de un bucle **`for`** que itere sobre una lista de tiempos enumerados, creando dos nuevas variables de bucle llamadas **`n`** y **`t`**:

<img width="982" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/f19669a1-2e6a-4af2-858a-df64808d8547">

Aquí está el fragmento de SVG tomado del archivo **`bar.html`**:

<img width="912" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b05bc43b-68af-469e-8b77-3d580c34e1ab">

Cree una f-string multilínea con comillas triples que utilice las variables **`bar_width`** y **`t`** de la última página para crear una etiqueta SVG para el tiempo de natación actual:

<img width="940" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e57a8e66-4505-4e3e-bb38-e567b306ddcd">


Con su cadena f-string, muestre el código que la agrega al final de la variable **`svgs`** creada en la última página:

<img width="942" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/74739b42-7085-4ed2-8375-7b28cbe112fa">

<img width="923" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/f089006a-2432-42af-b97b-a12a234f70be">

Con sólo unos pocos ajustes menores, el código que creó durante el ejercicio que acaba de completar se puede combinar en una sola celda de código en su notebook, así:

<img width="909" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/47f33044-89ad-4b44-8352-abb06f18ba7c">

Al presionar **Shift+Enter** en esta celda se ejecuta el código, pero no se muestra nada. En la siguiente celda, use el BIF **print** para ver su obra:

<img width="975" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/2b59ee5a-a573-45fb-adc6-92f5b714f544">

### Todo lo que queda es el final de tu página web.

Probablemente esté ansioso por ver cómo se ve el marcado HTML y SVG generado en su navegador, pero aún no ha terminado. Recuerde que el final del archivo **`bar.html`** tiene este marcado:

<img width="945" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c22fccc8-feb4-4fda-b696-e675c203f14a">

Como estás en camino de convertirte en un ninja de f-string, solo te daremos el código para esta parte:

<img width="967" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b75dd318-3605-40c5-ad53-5c844e83244d">

Crear la página completa de marcado HTML no es difícil:

<img width="1118" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/1c0c688a-a58f-4c63-b38c-1c2d70b0f7a0">

**Sí. Pero primero guardemos el HTML en un archivo.**

El PSL incluye un módulo llamado **`webbrowser`**, que puede utilizar para mostrar HTML en su navegador web. Desafortunadamente, no puede enviar al módulo una gran cadena de HTML para mostrar. El HTML debe estar disponible en la web o guardarse primero en un archivo.

## Escribir en archivos, como leer, es indoloro

Recuerde este código que utilizó para leer los tiempos de natación de un archivo en una nueva lista llamada **`data`**:

<img width="966" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/046ccde0-2657-4be1-bd93-7f68172d6cf0">

El BIF **open**, de forma predeterminada, abre un archivo para lectura, pero también es posible abrir un archivo en *modo de escritura* proporcionando un segundo argumento para **open**:

<img width="1064" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/3fd6ece8-1d88-4043-a4bd-b293cda7a714">

Si ejecuta este código en una nueva celda de código, crea **`test.txt`** si no existe, luego almacena el mensaje (demasiado interesante) en el archivo, antes de cerrar el archivo automáticamente (gracias a su viejo amigo, la sentencia **`with`** ).

Si **`test.txt`** ya existe, este código sobrescribe (!!!) el contenido antiguo del archivo con el mensaje. Si desea conservar el contenido existente del archivo, el modo de agregar puede hacerlo por usted, suponiendo que reemplace el argumento "**`w`**" del BIF abierto con "**`a`**".

**Sabiendo todo esto, usemos un código similar al que se muestra arriba para guardar la página web generada en un archivo.**

<img width="916" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/19ae4f84-8886-4719-83b8-da956e272ed3">

Antes de comenzar este ejercicio, cree una subcarpeta en su carpeta **Learning** y llámela **charts**.

En lugar de usar un nombre genérico para el archivo de su página web, generemos uno a partir del nombre ya almacenado en la variable **`fn`**. Específicamente, creemos una cadena **`f`** que convierta un nombre de archivo que se ajuste a este patrón:

<img width="1014" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/82e821e8-ebc5-4f7b-93d0-815b9b522879">

en uno que se ajuste a este patrón:

<img width="974" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/8a61ad79-5c8b-4d3a-9fce-0d0081821423">

Cuando hayas calculado la f-string que logra esto (pista: puedes poner código Python entre las llaves de una f-string, no solo nombres de variables), toma tu lápiz y escribe en la f-string que deseas. utilizar en el espacio siguiente. Asigne la f-string a una variable llamada **`save_to`**:

__________________________________________________________________

Proporcione el código que usaría para guardar su HTML (actualmente en la variable **`page`**) en el archivo cuyo nombre está en la variable **`save_to`**:

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

__________________________________________________________________

<img width="961" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/ee824ca9-59c4-457b-ae6c-b2bfdfaa46cb">


Antes de comenzar este ejercicio, cree una subcarpeta en su carpeta **Learning** y llámela **charts**.

En lugar de usar un nombre genérico para el archivo de su página web, generemos uno a partir del nombre ya almacenado en la variable **`fn`**. Específicamente, creemos una cadena **`f`** que convierta un nombre de archivo que se ajuste a este patrón:

<img width="1014" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/82e821e8-ebc5-4f7b-93d0-815b9b522879">

en uno que se ajuste a este patrón:

<img width="974" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/8a61ad79-5c8b-4d3a-9fce-0d0081821423">

Cuando hayas calculado la f-string que logra esto (pista: puedes poner código Python entre las llaves de una f-string, no solo nombres de variables), toma tu lápiz y escribe en la f-string que deseas. utilizar en el espacio siguiente. Asigne la f-string a una variable llamada **`save_to`**:

<img width="955" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/408d518f-b018-429f-86e1-bd5c9918fc16">


Proporcione el código que usaría para guardar su HTML (actualmente en la variable **`page`**) en el archivo cuyo nombre está en la variable **`save_to`**:

<img width="928" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/de1692e8-97fd-4bdd-9db9-35587f4c28d0">

### Es hora de mostrar tu obra

Con su HTML y SVG guardados en un archivo en la carpeta **charts**, pedirle al módulo **`webbrowser`** del PSL que muestre el gráfico es sencillo:

<img width="968" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/abc14037-147a-44cc-98ad-d14ff4a4a462">

<img width="936" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/aac92149-07ba-4edf-954a-8621ab1572e8">

### Todo lo que queda son dos ajustes estéticos...

Eche un vistazo a los dos gráficos que se muestran a continuación. El gráfico de su código está a la izquierda, mientras que el gráfico de "objetivo" de antes en este capítulo está a la derecha. ¿Notas alguna diferencia?

<img width="1272" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/dafd300f-7e24-458d-994a-f5e1c0364d71">

<img width="1324" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4d2f32dc-4b4a-4d93-b2b3-87bbee95fc70">

**Alex**: Ambos son muy similares...

**Mara**: Pero hay diferencias sutiles.

**Sam**: Para empezar, el gráfico de la izquierda muestra sus barras en el orden incorrecto.

**Mara**: Sí, el entrenador fue bastante claro cuando nos dijo que quería ver el tiempo de natación más reciente en la parte superior de la tabla.

**Alex**: ¿Seguramente es una solución fácil?

**Sam**: Creo que sí, sí. Las listas vienen con un método inverso incorporado que creo que podemos explotar aquí.

**Mara**: Es sólo cuestión de llamar a reversa en el lugar correcto para que el código generador de SVG procese los datos en el orden correcto.

**Alex**: ¿Qué más pasa? No se me ocurre nada más.

**Sam**: Mara dijo que la diferencia era sutil. Observe cómo el gráfico de barras de la derecha tiene espacios en blanco adicionales después de cada una de las barras, antes de que se muestren los tiempos.

**Mara**: Eso no es un gran problema, pero ciertamente significa que el gráfico de la derecha es más agradable a la vista. El gráfico de la izquierda me parece desordenado.

**Alex**: Ah, sí, ya lo veo. ¿También es una solución fácil?

**Mara**: Eso espero.

**Sam**: Recuerda que el *ancho* de cada barra se determina llamando a la función **`hfpy_utils.convert2range`**. Creo que podremos manipular esas llamadas para solucionar este problema sin demasiados problemas.

**Alex**: Genial. Entonces, son dos soluciones rápidas. Eso no debería llevar mucho tiempo...

<img width="1240" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/f9e19766-2d00-46be-9d23-8d1292fd0d69">

Ajuste su celda de código como se muestra a continuación, reinicie su notebook y luego vuelva a ejecutar todo su código para ver las diferencias que hacen estas pequeñas ediciones:

<img width="1045" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/6b5824b9-f0ba-4b5a-9b97-ef7c853519b9">

Efectivamente, su última versión del gráfico de barras se ve mucho mejor que antes. El orden está arreglado y todo se ve un poco más ordenado ahora que hay un espacio adicional:

<img width="1111" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/6efe2c79-f393-452e-bb51-6a142ba17872">

<img width="1102" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a9ddc8b1-f61c-40eb-befc-abd2d8719ab7">

## Es hora de otra función personalizada

El código en su notebook **`Charts.ipynb`** produce un gráfico de barras que es una buena aproximación de lo que el coach necesita, además de coincidir estrechamente con lo que el coach creó con la hoja de cálculo. El gráfico de barras no coincide exactamente y esto tiene que ver con el hecho de que el eje x de su gráfico comienza en cero, mientras que el eje x de la hoja de cálculo comienza en 1:13,44, por lo que la escala está un poco fuera de lugar. No te preocupes, lo que has producido aquí es más que suficiente.

Todo lo que falta es la capacidad de llamar a su código para cualquier nombre de archivo, no sólo el que contiene los tiempos de natación de Darius. Crear otra función debería funcionar. Recuerde la estrategia de tres pasos para la creación de funciones del último capítulo:

1️⃣ **Piensa en un nombre bonito y significativo.**

Llamemos a su función **`produce_bar_chart`**, que, incluso si lo decimos nosotros mismos, es el nombre de función más fino que probablemente encontrará.

2️⃣ **Decida el número y los nombres de los parámetros.**

Al igual que **`read_swim_data`**, su nueva función toma un único parámetro que identifica el nombre del archivo para generar un gráfico de barras.

3️⃣ **Sangra el código de tu función bajo una declaración `def`.**

**`def`** introduce la función, especificando el nombre de la función y cualquier parámetro. Como siempre, el código sangrado bajo la palabra clave **`def`** es el bloque de código de la función.

<img width="1064" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/41a30461-796e-4241-aefc-1535481256e1">

**Acordado. Eso es una buena idea.**

Después de todo, el código que estás creando es parte del sistema que estás construyendo para el Coach, así que mantengamos todo el código que planeas usar en un módulo.

Eche un vistazo (en la página siguiente) al código que agregamos a nuestro archivo **`swimclub.py`**. También debes hacer esto, mientras prestas atención a los ajustes menores que hicimos en nuestra versión final.

## Agreguemos otra función a su módulo.

Agregue las siguientes dos líneas en la parte superior de su archivo **`swimclub.py`**, luego agregue la función modificada como se muestra:

<img width="682" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/aa3872f4-9d7b-4341-9a5d-31c51a77a8be">

<img width="1237" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/d3339ac7-2f30-4a4b-8ec8-f28c1516403b">

Asegúrese de que el módulo **`swimclub`** esté actualizado con el código modificado de la última página.

Regrese a su cuaderno **`Charts.ipynb`** y haga clic en el botón **Restart** de VS Code para borrar del intérprete los restos de cualquier celda de código ejecutada anteriormente. Trabajando en la parte inferior de su notebook, agregue y ejecute el código como se muestra a continuación. Asegúrese de que los resultados que ve aquí se repliquen en su pantalla.

<img width="805" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/b8db0b61-59db-4381-802c-46b06e39492d">

<img width="865" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/0c5fddbf-b6c0-40b7-a43f-cb5ac694e6fd">

<img width="902" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c841ae77-876d-4581-9dc1-e7eb1f35eed5">

## ¿Qué pasa con ese valor de centésimas?

Su código ha producido un valor de "**`2`**" para el valor de centésimas de Lizzie. El problema es que no está claro si este valor debería ser "**`20`**" o "**`02`**". Aquí está la línea de código del módulo **`swimclub`** que produce este valor:

<img width="1253" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/f8b51544-a83f-4a2f-8479-0026d4108369">

<img width="1278" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c494d23d-c224-4b2d-83ec-8db93ca4b313">

**Es un poco misterioso, ¿no?**

De hecho, ese código se ve bien, pero no se puede escapar del hecho de que no funciona del todo con los datos de Lizzie. Gorrón.

¿Qué hacer?

<img width="1284" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/9e40660e-6dd3-4ac2-a083-735c36b12e88">

## Redondear no es lo que quieres (en este caso)

Cuando se trata de redondear con el BIF **round**, el énfasis está en realizar correctamente el cálculo, no en formatear correctamente el resultado para su visualización. Es como si el redondeo fuera una operación demasiado contundente cuando se trata de utilizar el resultado de la **round** directamente con fines de visualización.

Además de facilitar la *producción* de strings, la tecnología f-string de Python proporciona especificadores de **string formatting specifiers**. Hay muchos de estos especificadores y no vamos a entrar en describir lo que hacen todos aquí. En lugar de eso, veamos la solución que necesitamos:

<img width="1273" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/43fef07f-c0cb-4ff9-9627-5f0e882f39eb">

Asignar la split f-string a **`mins_secs`** y **`hundredths`** (como lo hizo con la línea de código ofensiva) le brinda un reemplazo directo que corrige el error y resuelve el misterio de la codificación.

<img width="1248" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/37ddaf63-f24d-41e9-9957-50e6f422b73b">

Si desea saber un poco más sobre los especificadores de formato de f-string, como se sugirió anteriormente, comience con los ejemplos incluidos en los documentos de Python: 

https://docs.python.org/3/reference/lexical_analysis.html#f-strings

<img width="1244" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a15e06e7-b6e4-448d-aa97-d752d4b726f0">

Ajuste la función **`read_swim_data`** en el módulo **`swimclub`** para reemplazar la línea de código que usaba el BIF **round** con el código f-string de la página anterior. Aquí está el fragmento de código que necesita:

<img width="1264" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/da974b47-9199-4100-9e89-972dfccbec80">

Con el módulo **`swimclub`** guardado, reinicie su notebook **`Charts.ipynb`** y luego vuelva a ejecutar las celdas de código que producen el gráfico de barras de Lizzie. Cuando lo hagas, verás el mismo gráfico que la última vez, pero la molesta arruga se solucionó y el tiempo promedio se muestra correctamente:

<img width="1236" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c6992e0e-5485-4f68-af08-f0ed151145d0">

## Un pequeño ajuste de formato más

Ajustar el formato de visualización para el valor de las centésimas plantea otro problema: ¿qué sucede si el valor de los segundos es solo un dígito, digamos **`2`**? Por el momento, el código actual crea una cadena de tiempo que se parece a esta "**`1:2.20`**" (que parece decididamente extraña) en lugar de esta "**`1:02.20`**" (que se ve mucho mejor). La tecnología de formato f-string también puede ayudar en este caso. Para evitar que ocurra esta situación, cambie la penúltima línea de código en su función **`read_swim_data`** (en **`swimclub.py`**) para que se vea así:

<img width="1260" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/ebcd6fe6-2a73-4e71-9bfc-e20b70935f85">

## Las cosas van bien...

Con esta última solución aplicada, ahora tiene un mecanismo que, dado el nombre de archivo de cualquier nadador, puede producir un gráfico de barras asociado. Este es un paso importante para proporcionar al entrenador un sistema que reemplace su confiable portapapeles y su programa de hoja de cálculo.

Cómo proporcionarás esta funcionalidad al coach sigue siendo una cuestión abierta. Pero no nos preocupemos por esos detalles ahora. Disfrute de la gloria de sus hermosos gráficos de barras HTML.

<img width="1026" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/17fc77ed-39ea-488e-a57e-419bbb1d7603">

**¡Excelente! Y hay más por venir.**

Ahora que tenemos un código que dibuja un gráfico de barras para cualquiera de los archivos de datos del entrenador, debemos hacer arreglos para que el entrenador seleccione fácilmente con qué archivo de nadador trabajar. Comenzaremos con este trabajo en el próximo capítulo.

Antes de eso, relájate, tómate un descanso, revisa el resumen de este capítulo y no olvides probar el crucigrama de este capítulo.

<img width="831" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/3770d3a3-0d5e-4e73-926b-b61f96c49040">

* Aunque este libro no está diseñado para enseñarle **HTML**, como programador moderno de Python, le resultará difícil no encontrarse con el procesamiento de HTML en algún momento.

* Además de generar una página HTML completa, este capítulo también utiliza el marcado **SVG** para dibujar las barras en los gráficos del Coach.

* El PSL viene con el módulo **webbrowser** que, como su nombre indica, permite a Python interactuar con su navegador web favorito. El módulo **webbrowser** puede abrir HTML en un archivo, así como desde una dirección web.

* Cuando se trata de crear **formatted strings**, Python te ofrece opciones. Además de construir strings con el venerable operador de concatenación (**`+`**), los chicos geniales (así como nosotros, los viejos) recurren cada vez más a **f-strings** para este tipo de cosas.

* Las **f-strings** facilitan la inclusión del valor de una variable en una cadena formateada gracias a la **interpolación**. Piense en "insertar en" y estará bien. Las llaves se utilizan para indicar en qué parte de la cadena formateada debe ir el valor de la variable. Recuerde: en Python, **las llaves normalmente rodean los datos, no el código**.

* El módulo **`hfpy_utils`** proporciona una función de conversión que puede convertir un valor de un rango en un valor de otro rango. Esta función, llamada (en una hazaña de imaginación incognoscible) **`convert2range`**, se utilizó para garantizar que el ancho de las barras en el gráfico del entrenador no terminara siendo de miles de píxeles.

* Si cree que somos realmente inteligentes al crear la función **`convert2range`**, piénselo de nuevo. Eche un vistazo al código **`htpy_utils.py`** (parte de la descarga de este libro) y observe el comentario que le indica quién es la persona realmente inteligente.

* Además de abrir archivos para leer, el BIF **open** también puede escribir en archivos, lo cual es muy útil cuando su código necesita crear un nuevo archivo. El modo "**`w`**" le dice a **open** que cree/sobrescriba/escriba en el archivo nombrado.

* El método **`reverse`** (que viene integrado en todas las listas de Python) intercambia el orden de una lista con nombre en el lugar y nos salvó de la vergüenza de mostrarle al entrenador un gráfico de nadador con un orden de barras incorrecto.

* Para ser claros, un “pedido de barra incorrecto” no tiene nada que ver con pedir tres cervezas en lugar de dos.

* Una vez que todo funcionó según las especificaciones, creó la función **`produce_bar_chart`** y luego la agregó al módulo **swimclub**, para que su nueva funcionalidad pueda compartirse más fácilmente.

* Por supuesto, una vez hecho esto, detectó un pequeño error (¿no es siempre así?), que provocó que el valor de centésimas de segundo se mostrara incorrectamente. La siempre versátil f-string vino a tu rescate una vez que te diste cuenta de que el BIF **round** estaba haciendo todo lo posible para arruinarte el día.

* El **format specifier** del mecanismo de f-string te salvó de la ira de **round**, justo a tiempo para que mostraras tu código generador de gráficos de barras al entrenador, quien estaba encantado con tu progreso. ¡Uf!

<img width="847" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/f680ac09-5cca-43cf-b161-fd94ab76ecd1">

Las respuestas a las pistas se encuentran en las páginas de este capítulo y la solución está en la página siguiente.

<img width="598" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/1248d7fa-8de0-4896-92d5-831552b3bcb4">

<img width="868" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4ebe9cdf-6ebf-4e36-8756-2bb38d683bea">

<img width="864" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/bbd5f6c7-7a5a-4c71-b9d6-eb1f5ba24b1a">

<img width="836" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/7ae519b6-53e8-4677-8171-c155dc7b4a43">

<img width="1055" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a15a0599-9a56-4bad-9075-0e0d24ae0d50">


## 💻 Práctica.

### Cree gráficos de barras simples con HTML y SVG

Vamos a crear el archivo **`bar.html`** que contiene HTML y SVG, y que dibuja un gráfico de barras cuando se ve en un navegador web. 

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            A simple bar chart
        </title>
    </head>
    <body>
        <h3>A simple bar chart</h3>
        <svg height="30" width="400">
            <rect height="30" width="300" style="fill:rgb(0,0,255);" />
        </svg>Label 1<br />
        <svg height="30" width="400">
            <rect height="30" width="250" style="fill:rgb(0,0,255);" />
        </svg>Label 2<br />
        <svg height="30" width="400">
            <rect height="30" width="350" style="fill:rgb(0,0,255);" />
        </svg>Label 3<br />
        <p>It's simple, but it works!</p>
    </body>
</html>
```

<img width="1124" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/11cc8396-dccf-4bee-be4e-9d44c258f6e6">

<img width="1512" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/4c488081-f015-42fb-a9c9-d551bc666d73">

### Pasar de un gráfico simple a un gráfico de Coach

Podemos escribir código Python para generar HTML y SVG sobre la marcha.

Vamos a crear un nuevo notebook **`Charts.ipynb`** con el siguiente código:

<img width="1124" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/c1939ee4-c2f1-46c9-a337-f682300d81ae">

```py
import swimclub

fn = "Darius-13-100m-Fly.txt"

(swimmer, age, distance, stroke, *_) = swimclub.read_swim_data(fn)

title = swimmer + " (Under " + age + ") " + distance + " " + stroke


title
```

Este código nos permite obtener un string que representa el title que se puede poner en el archivo HTML.

Ahora vamos a crear una variable **`html`** que va a contener los tags que representan al documento HTML.

```py
html = "<!DOCTYPE html><html><head><title>" + title
html = html + "</title></head><body><h3>" + title + "</h3>"

html
```

```sh
'<!DOCTYPE html><html><head><title>Darius (Under 13) 100m Fly</title></head><body><h3>Darius (Under 13) 100m Fly</h3>'
```

<img width="1124" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a711dde7-0a7d-4631-b7fd-fe819a7edd95">

Estamos usando la concatenación de cadenas usando **`+`**, pero podemos hacerlo usando **f-string** o los **tiple-quoted string**.

<img width="1127" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/9f08de87-6cf6-4ca7-8f0e-00f5797e1a62">

<img width="1127" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/010a8c09-604a-40df-bbfb-0b5e6c820f90">


```py
title = f"{swimmer} (Under {age}) {distance} {stroke}"

title

html = f"""<!DOCTYPE html>
<html>
    <head>
        <title>{title}</title>
    </head>
    <body>
        <h3>{title}</h3>
"""

html
```

Podemos imprimir el valor de **`html`**.

<img width="1127" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/f9d4b90d-1d26-459b-8c77-7c3642cf6ddf">

En nuestro módulo **`swimdata.py`** actualmente tenemos una cadena que se forma con concatenación.

<img width="995" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/550d5055-2d17-4a10-b603-87545f3b86c5">

La vamos a cambiar para que use **f-string**.

<img width="1133" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/398f0bd6-2138-4c69-ae89-6a059595377b">

```py
# average = str(minutes) + ":" + str(seconds) + "." + hundredths
average = f"{minutes}:{seconds}.{hundredths}"
```

### ¡Generar SVG es fácil con f-strings!

Para utilizar Python para generar mediante programación los gráficos de barras del entrenador, necesitarás crear tantas tags **`<svg>`** como veces haya en los datos de tu nadador. 

Actualmente la función **`read_swim_data`** del modulo **`swimdata.py`** nos retorna los datos así:

<img width="1120" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/fb86867a-a2cd-4b5f-9503-1484cfadb3c4">

Los tiempos son una lista de strings y con las barras del gráfico los tiempos deben ser númericos, por lo que necesitamos retornar una lista de números, si usamos la lista **`converts`** que son los equivalentes numéricos de los tiempos de natación. Actualmente esta lista **`converts`** no se esta devolviendo, solo se usa para calcular el **`average`**, vamos a incluir **`converts`** para devolverla.

<img width="1025" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/50e6c606-3665-4119-9421-736991f4094b">

Si ejecutamos esta nueva versión de la función **`read_swim_data`** del modulo **`swimdata.py`**.

<img width="1134" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/d486547e-18fc-40d0-8ec2-8aee077064f4">

Aunque los datos devueltos parecen correctos, los números son un poco grandes y este es el segundo problema. Específicamente, el fragmento SVG anterior tiene un valor de ancho máximo de **`400`**:

<img width="1048" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/1e6d82d1-e6a8-46e0-915e-6ba9e8b686cb">

Obviamente, ninguno de esos seis números mayores que 8000 es menor que 400. Y si usara esos números tal como están, sus rectángulos SVG probablemente se desplazarían hacia el lado derecho de la pantalla por un margen considerable.

Lo que se necesita aquí es alguna forma de reducir los números más grandes a un valor que se ajuste dentro del rango de 0 a 400, lo que parece que podría necesitar algunos cálculos complicados. ¡Ay!

Quiso la suerte que ***Head First Coders*** acaba de enviar un pequeño módulo de Python (llamado **`hfpy_utils`**), junto con un notebook (llamado **`HowTo.ipynb`** ) que le muestra cómo convertir cualquier número a su equivalente dentro de algún otro rango. Copie ambos archivos en su carpeta de **Learning**.

<img width="341" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/333b5c1d-2fc6-474f-80da-3825de4f50ef">

```py
def convert2range(v, f_min, f_max, t_min, t_max):
    """Given a value (v) in the range f_min-f_max, convert the value
    to its equivalent value in the range t_min-t_max.

    Based on the technique described here:
        http://james-ramsden.com/map-a-value-from-one-number-scale-to-another-formula-and-c-code/
    """
    return round(t_min + (t_max - t_min) * ((v - f_min) / (f_max - f_min)), 2)

```

<img width="1112" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/cc70e794-7665-4419-8a83-1e743f142ffd">

```py
import swimclub

fn = "Darius-13-100m-Fly.txt"

*_, converts = swimclub.read_swim_data(fn)


converts


_


import hfpy_utils

for n in converts:
    print(n, "->", hfpy_utils.convert2range(n, 0, max(converts), 0, 400))
```

<img width="1129" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/2dac5a96-da21-41a1-8057-9aac11ad04af">

<img width="1124" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/6f17fefd-f41f-4c0d-adbb-b87cfd44b86f">



















