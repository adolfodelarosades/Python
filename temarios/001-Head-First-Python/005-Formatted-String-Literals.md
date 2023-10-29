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







