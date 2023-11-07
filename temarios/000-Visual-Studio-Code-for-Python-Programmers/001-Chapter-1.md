# CHAPTER 1: Getting Started
* Installing Visual Studio Code
* The Visual Studio Code User Interface
* Command Palette
* Extensions
* Customizations
* Summary
* Note

Cuando comenzó su viaje de desarrollo de **Python**, lo más probable es que le presentaran el **Integrated Development and Learning Environment (IDLE) de Python**. La simplicidad de IDLE es ideal para los recién llegados, pero deja mucho que desear para aquellos que se sienten más cómodos con el lenguaje y necesitan un flujo de trabajo eficiente y productivo. Hay una variedad de editores de código y entornos de desarrollo integrados (IDE) disponibles para el desarrollo de Python: algunos para desarrollo general con soporte multilenguaje (como **Atom** o **Sublime**) y otros creados exclusivamente para Python (como **PyCharm**). Seleccionar un entorno de desarrollo es una cuestión de preferencia personal. Como programador experimentado, es posible que ya haya probado algunos editores y, por lo tanto, sepa qué funciones desea más. Si necesita un editor de código extensible que proporcione amplia flexibilidad, eficiencia y productividad para administrar el código fuente de Python, entonces vale la pena considerar Visual Studio Code.

**Visual Studio Code** (también conocido como VS Code) es un editor de código gratuito, de código abierto y multiplataforma desarrollado por Microsoft. Visual Studio Code, clasificado como el entorno de desarrollo más popular en la encuesta para desarrolladores de Stack Overflow de 2019, es un editor de código rico en funciones y altamente personalizable que no solo es excelente para editar código fuente, sino que también tiene soporte integrado para colaboración y entornos alojados en la nube. El código fuente de Visual Studio Code está disponible en el repositorio GitHub del producto en github.com/microsoft/vscode. Le invitamos a contribuir al proyecto y también puede ver la hoja de ruta del producto dentro del repositorio. Visual Studio Code se actualiza mensualmente con nuevas característicasy corrección de errores. Para los primeros usuarios, la compilación VS Code Insiders proporciona una nueva compilación al menos todos los días con funciones y correcciones de errores.

Visual Studio Code tiene soporte integrado solo para **JavaScript, TypeScript, HTML y CSS**, pero admite muchos lenguajes adicionales, como Python, a través de extensiones. Antes de comenzar a programar en Python, debe instalar la extensión. Luego podrá comenzar a familiarizarse con la interfaz del editor dentro del contexto de Python.

## Instalación del código de Visual Studio

Como editor de código multiplataforma gratuito, Visual Studio Code se ejecuta en macOS, Linux y Windows. Descargue el código de Visual Studio desde code.visualstudio.com. Si el navegador no detecta su sistema operativo, visite code.visualstudio.com/#alt-downloads para obtener más opciones. Los pasos de instalación específicos de la plataforma están disponibles en code.visualstudio.com/docs/setup/setup-overview. Tanto macOS como Windows ofrecen la opción de agregar Visual Studio Code a su variable de entorno PATH. Agregar Visual Studio Code a su variable de entorno PATH brinda la conveniencia de abrir una carpeta directamente desde la consola usando el comando **`code <folder>`** o **`code`**. (para abrir la carpeta actual).

Como se mencionó, Microsoft lanza una nueva versión de Visual Studio Code a menudo con nuevas características y correcciones de errores importantes. Si su plataforma admite la actualización automática, Visual Studio Code le solicitará que instale la nueva versión cuando esté disponible. Como alternativa, puede buscar actualizaciones manualmente ejecutando Help ➪ Check For Updates en Linux y Windows o ejecutando Code ➪ Check For Updates en macOS.

<hr>

**NOTA** Si está interesado en probar la compilación VS Code Insiders, puede descargar una copia desde code.visualstudio.com/insiders/. Puede instalar la compilación de Insiders junto con la última compilación mensual, lo que le permite utilizar ambas versiones del editor de código de forma independiente.

<hr>

## La interfaz de usuario de Visual Studio Code

La interfaz de usuario (UI) de Visual Studio Code proporciona un diseño mínimo y simple que mantiene el código fuente como foco del entorno de desarrollo. Cuando inicia Visual Studio Code por primera vez, muestra un diseño predeterminado. Cada vez que inicia Visual Studio Code en el futuro, el editor se abre en el mismo estado que tenía la última vez que se cerró.

Puedes sentirte como en casa personalizando el diseño a tu gusto. Sin embargo, antes de comenzar a mover cosas, debe conocer las áreas principales de la interfaz de usuario y su función respectiva (consulte la Figura 1.1 ).

![image](https://github.com/adolfodelarosades/Python/assets/23094588/cdd808c8-4349-4d17-a5c4-f844b6940b95)

**Figura 1.1 :La interfaz de usuario de Visual Studio Code.**

### Activity Bar

La barra de actividades, ubicada en el extremo izquierdo, le permite cambiar entre vistas. Las vistas brindan acceso rápido a tareas comunes como las siguientes:

* **Explorer**: gestión de archivos y carpetas
* **Search**: búsqueda global y reemplazo en carpetas abiertas utilizando texto sin formato o expresiones regulares
* **Source Control**: control de código fuente de Git para mantener repositorios de código
* **Run**: funciones utilizadas durante la depuración, como variables, call stacks, y breakpoints.
* **Extensions**: navegación, instalación y administración de extensiones desde Extension Marketplace

Además de las vistas predeterminadas, la barra de actividades también puede incluir vistas personalizadas proporcionadas por las extensiones que instala desde Extension Marketplace. Cada vista tiene un icono que refleja su función respectiva.

Puede reordenar las vistas arrastrándolas y soltándolas en la barra de actividades. Las vistas también se pueden ocultar si hace clic derecho en la vista y selecciona Ocultar de la barra de actividad. Las vistas son parte de su diseño personalizado que se conserva cada vez que ejecuta Visual Studio Code.

### Side Bar

La barra lateral, ubicada a la derecha de la barra de actividades, muestra la vista activa. Si no se selecciona ninguna vista, la barra lateral se contrae. Puede cambiar el tamaño de la barra lateral haciendo clic y arrastrando el borde que comparte con el editor. Las vistas predeterminadas para la barra lateral son Explorer, Search, Source Control, Run y Extensions (consulte las Figuras 1.2 a 1.6 , respectivamente).

Explorer, Search, Source Control, Run, and Extensions
**Figura 1.2 :Vista del explorador.**

![image](https://github.com/adolfodelarosades/Python/assets/23094588/622062b3-e61e-4ec7-a509-b7bbe40ebdd4)
**Figura 1.3 : Vista de búsqueda.**

![image](https://github.com/adolfodelarosades/Python/assets/23094588/1f3ab21f-cad8-4e18-8fdc-818ade9f1552)
**Figura 1.4 : Vista de control de código fuente.**

![image](https://github.com/adolfodelarosades/Python/assets/23094588/28e5b81c-53b5-439a-81b9-d18c682c6181)
**Figura 1.5 : Vista de ejecución.**

![image](https://github.com/adolfodelarosades/Python/assets/23094588/a94e52f4-29d5-4ced-a025-b4929f036629)
**Figura 1.6 :Vista de extensiones.**

### Editor

El editor, que ocupa la mayor parte de la pantalla, es donde editas archivos. Puedes cambiar el tamaño del editor haciendo clic y arrastrando los bordes que comparte con la barra lateral y los paneles.

La región del editor superior puede cambiar según el tipo de archivo que esté activo en el editor. Por ejemplo, si edita un archivo Markdown, aparece un icono de Vista previa, lo que habilita la Vista previa de Markdown de Visual Studio Code (consulte la Figura 1.7 ).


Figura 1.7 :En la imagen superior, el ícono de Vista previa aparece en la región del editor superior desde que se abre un archivo Markdown. Al hacer clic en el icono se muestra una vista previa del archivo Markdown, como se muestra en la imagen inferior.

Cuando abres un archivo Python, ves un ícono Ejecutar archivo Python en la terminal (que se muestra como un botón Reproducir) en la región superior del editor. (El ícono Ejecutar archivo Python en la terminal es una forma rápida de ejecutar un programa Python). Cuando se selecciona, se abre una terminal y se ejecuta el archivo Python (consulte la Figura 1.8 ).


Figura 1.8 :El ícono Ejecutar archivo Python en la terminal aparece en la parte superior de la región del editor. Al hacer clic en el icono se ejecuta el archivo Python.

Para la mayoría de los tipos de archivos, la región superior del editor también incluye un ícono Abrir cambios para ver los cambios en el archivo desde la última confirmación del control de fuente (consulte la Figura 1.9 ). Al seleccionar el icono se abre el editor de diferencias (consulte la Figura 1.10 ). El editor de diferencias se abre en una nueva pestaña con una vista de lado a lado de las diferencias. También puede acceder al editor de diferencias seleccionando el archivo en la vista Control de código fuente.


Figura 1.9 :Cuando se hace clic en el icono Abrir cambios, se abre una nueva pestaña que muestra las diferencias del archivo.


Figura 1.10 :El editor de diferencias muestra los cambios realizados en el archivo desde la última confirmación.

La región también contiene un icono Dividir editor hacia la derecha para dividir el editor (consulte la Figura 1.11 ). Cuando se selecciona, se abre un nuevo grupo de editores a la derecha del editor inicial. Puede abrir y modificar archivos en cualquiera de las ventanas del editor.


Figura 1.11 :Cuando se hace clic en el icono Dividir editor derecho, se abre un nuevo grupo de editores a la derecha.

Un archivo abierto y activo muestra el código fuente en el medio del editor, y un minimapa se encuentra en la parte superior derecha (consulte la Figura 1.12 ). El Minimapa proporciona una vista en miniatura condensada de todo el archivo y es excelente para una navegación rápida y saber visualmente dónde se encuentra en el contexto de todo el archivo.


Figura 1.12 :Aparece un minimapa a la derecha delbankaccount.pyarchivo. Puede hacer clic en cualquier parte del Minimapa para navegar rápidamente hasta el código en esa ubicación.

Puedes abrir tantos archivos como quieras en el editor. Cada archivo abierto se distingue por un encabezado con pestañas. El archivo activo es el archivo en el que aparece el cursor. Puede arrastrar pestañas para reordenarlas y también fijar pestañas (Cmd+K Shift+Enter/Ctrl+K Shift+Enter 1 ) para mantener sus archivos más utilizados a su alcance. Se muestra una pestaña fijada con el ícono de idioma para el archivo respectivo (consulte la Figura 1.13 ).


Figura 1.13 :Elhelloworld.pyarchivo es una pestaña fijada. Un ícono de alfiler al lado del nombre del archivo en la pestaña indica que el archivo está anclado.

Por motivos de organización, puede agrupar los archivos abiertos en grupos de editores separados (consulte la Figura 1.14 ) dentro de la ventana dividida.


Figura 1.14 :Los grupos de editores se utilizan para editar el código fuente de un programa Python que crea cuentas bancarias.

Los nuevos editores se pueden abrir de varias maneras:

En la vista del Explorador, presione Ctrl+clic/Alt+clic y haga clic en un archivo.
En la vista del Explorador, seleccione un archivo y presione Ctrl+Entrar/Ctrl+\ para abrir un archivo a la derecha de un grupo de editores existente.
Haga clic en el icono Editor dividido en la región del editor superior.
Arrastre y suelte un archivo en cualquier lado de la región del editor.
En la lista Apertura rápida (Cmd+P/Ctrl+P), resalte un archivo y presione Cmd+Entrar/Ctrl+Entrar.

NOTA Para abrir un archivo en un grupo de editores específico, el grupo de editores debe estar activo.

De forma predeterminada, los archivos y los grupos de editores se muestran verticalmente adyacentes a la derecha uno del otro (consulte la Figura 1.15 ). Sin embargo, puede arrastrar y soltar el área de título del editor para reordenar y cambiar el tamaño de los editores.


Figura 1.15 :Se utilizan tres ventanas de grupo de editores dentro del editor para mostrar el contenido de cada archivo. Dos ventanas de grupo de editores se muestran verticalmente y una se muestra horizontalmente en la parte inferior del editor.

NOTA Cuando tiene más de un editor abierto, puede cambiar entre ellos rápidamente manteniendo presionado Cmd/Ctrl y presionando 1, 2 o 3.

Paneles
Los paneles debajo del editor contienen una o más áreas para la salida del programa, información de depuración, errores y advertencias, etc. También puede arrastrar algunas de las vistas desde la barra de actividades (como Buscar) al área de Paneles.

También puedes abrir el terminal integrado en el área de Paneles. El terminal integrado proporciona una interfaz de línea de comandos para su sistema operativo. El diseño predeterminado de Visual Studio Code incluye una terminal integrada que está abierta a la raíz de su proyecto. También puede abrir una terminal REPL para su intérprete de Python dentro de Visual Studio Code. La terminal integrada se activa cada vez que ejecuta un programa Python. Puede iniciar manualmente una terminal con el método abreviado de teclado Ctrl+~/Ctrl+Shift+`. En el Capítulo 2 , "Hola mundo para Python", se proporciona información adicional sobre cómo ejecutar programas Python .

Barra de estado
La barra de estado, ubicada en la parte inferior de la ventana de VS Code, contiene información sobre el proyecto abierto y los archivos que edita. Algunas de las características básicas de la barra de estado incluyen las siguientes:

Gestión de control de código fuente con Git
Número total de problemas para los programas abiertos (por ejemplo, variables no definidas)
Línea/columna
Configuración de sangría para espacios o tabulaciones
Configuración de codificación
Configuración de secuencia de fin de línea
Modo de idioma
Mecanismo de retroalimentación de Visual Studio Code
Notificaciones
Al hacer clic en un elemento de la barra de estado, se ejecuta un comando o se abre una ventana para modificar la configuración respectiva. Para el desarrollo de Python, aparece una etiqueta adicional en la barra de estado para el intérprete de Python seleccionado.

Las extensiones que instale desde Extension Marketplace pueden agregar etiquetas adicionales a la barra de estado para proporcionar acceso rápido para activar comandos de extensión. Por ejemplo, con la extensión GitHub Pull Requests and Issues, puedes publicar tu código fuente en GitHub desde la barra de estado.

Paleta de comandos
Visual Studio Code brinda acceso a todos los comandos disponibles a través de la paleta de comandos, y muchos de estos comandos no están disponibles a través de menús u otros elementos de la interfaz de usuario. Dentro de la paleta de comandos, puede ejecutar comandos para ejecutar tareas del editor además de comandos de extensión (consulte la Figura 1.16 ). Puede acceder a la paleta de comandos con el método abreviado de teclado Cmd+Shift+P/Ctrl+Shift+P. Acostúmbrate a esta pulsación de tecla; ¡Lo usarás mucho con Visual Studio Code!

Una vez que la paleta de comandos esté abierta, puede buscar comandos de extensión escribiendo algunos caracteres del nombre de la extensión. En la lista que aparece, desplácese por los resultados para encontrar el comando que necesita; luego presione Entrar. La figura 1.17 muestra un ejemplo.


Figura 1.16 :La paleta de comandos se muestra en la parte superior del editor.


Figura 1.17 :Al ingresara Python, se muestra una lista de comandos para la extensión de Python en la paleta de comandos.

Desplácese por la paleta de comandos para ver una lista completa de comandos. La mayoría de los comandos siguen una convención de nomenclatura de Función/Extensión: Acción (por ejemplo, Python: Seleccionar intérprete). Si hay una combinación de teclas configurada para el comando, el método abreviado de teclado se muestra a la derecha del comando. A medida que utiliza un comando repetidamente, el comando aparece en la parte superior de la paleta de comandos como un comando usado recientemente. Esto proporciona acceso rápido a los comandos utilizados con más frecuencia.

NOTA ¿No estás seguro de qué acciones puedes realizar desde cualquier lugar del código fuente? En la paleta de comandos, escriba? para obtener una lista de comandos disponibles que puede ejecutar.

NOTA En este libro, se le solicita que ejecute comandos desde la Paleta de comandos cada vez que aparece la convención de nomenclatura Función/Extensión: Acción .


Extensiones
Puede ampliar la funcionalidad de Visual Studio Code instalando extensiones desde Visual Studio Code Marketplace. Visual Studio Code Marketplace contiene más de 1500 extensiones creadas tanto por Microsoft como por la comunidad de desarrolladores. Estas extensiones agregan más funciones, temas, herramientas y compatibilidad con idiomas para su flujo de trabajo de desarrollo. Puede buscar extensiones en Marketplace dentro de la vista Extensiones (consulte la Figura 1.18 ).


Figura 1.18 :Se accede al Mercado de extensiones a través de la vista Extensiones en la barra de actividades.

NOTA También se puede acceder a Visual Studio Code Marketplace a través del navegador en marketplace.visualstudio.com/VSCode. Si elige instalar una extensión del navegador, se le solicitará que abra Visual Studio Code para completar la instalación.

En la vista Extensiones, puede escribir directamente en la barra de búsqueda para buscar una extensión. Los resultados de la búsqueda muestran el nombre de la extensión, la versión de la extensión, una breve descripción de la extensión y el nombre del editor. Cuando selecciona una extensión de los resultados de la búsqueda, el editor muestra la página de detalles de la extensión (consulte la Figura 1.19 ).

Para instalar una extensión, haga clic en el botón Instalar en la página de detalles de la extensión. ¿Cambiaste de opinión y descubres que ya no necesitas una extensión? Puede desinstalar una extensión desde la página de detalles de la extensión haciendo clic en Desinstalar (consulte la Figura 1.20 ).

El menú Más acciones (es decir, el ícono de tres puntos ubicado en la parte superior derecha de la vista Extensiones) brinda acceso para ver todas las extensiones instaladas, recomendadas, habilitadas y deshabilitadas. Si está buscando una nueva extensión para respaldar su flujo de trabajo de desarrollo, consulte las extensiones recomendadas. La vista Extensiones proporciona recomendaciones de extensiones basadas en archivos abiertos recientemente, así como en otras extensiones instaladas.


Figura 1.19 :La página de la extensión Python muestra información útil sobre la extensión.


Figura 1.20 :El botón Desinstalar aparece solo una vez que se instala una extensión. Al hacer clic en el botón, se elimina la extensión de Visual Studio Code.

NOTA Cualquiera puede escribir una extensión para uso personal o publicación en Marketplace. Para obtener más información, consulte la documentación de la interfaz de programación de aplicaciones (API) de extensión en code.visualstudio.com/api.

Personalizaciones
Básicamente, cada elemento y función de la interfaz de usuario dentro de Visual Studio Code se puede personalizar. Si bien algunas personalizaciones son de naturaleza puramente estética, una cantidad significativa de personalizaciones en Visual Studio Code pueden convertir su entorno de desarrollo en un entorno accesible y productivo. Puede optar por realizar personalizaciones globalmente para el editor o para un espacio de trabajo específico. Una carpeta de proyecto en Visual Studio Code se considera un espacio de trabajo. El espacio de trabajo en sí consta de los archivos y carpetas del proyecto.

Ajustes
La configuración en Visual Studio Code se puede administrar tanto globalmente como por espacio de trabajo. La configuración global se administra dentro de la configuración del usuario y se aplica a cualquier instancia de Visual Studio Code que abra. La configuración del espacio de trabajo se aplica solo cuando se abre un espacio de trabajo y se puede compartir entre los desarrolladores de un proyecto. La configuración del espacio de trabajo también anula la configuración del usuario.

Puede administrar la configuración de Usuario y Espacio de trabajo en el editor de Configuración (presione Cmd+,/Ctrl+, o seleccione Preferencias ➪ Abrir Configuración; consulte la Figura 1.21 ). En el editor, las configuraciones se clasifican en sus respectivos grupos. Todas las configuraciones de extensión están agrupadas bajo el encabezado Extensiones. La barra de búsqueda proporciona una forma rápida de encontrar la configuración que necesita.


Figura 1.21 :El editor de configuración enumera todas las configuraciones para Visual Studio Code y las extensiones instaladas.

Los cambios se guardan automáticamente a medida que realiza selecciones en el editor. Si desea volver al valor predeterminado para una configuración, haga clic en el ícono de ajustes al lado de la configuración y seleccione Restablecer configuración (consulte la Figura 1.22 ).


Figura 1.22 :La opción de menú Restablecer configuración restablece la configuración al valor predeterminado.

Visual Studio Code guarda su configuración en un archivo nombrado settings.jsondentro de una .vscodecarpeta. Puede trabajar con la configuración directamente en este archivo, si lo prefiere, en lugar de con la interfaz de usuario. Si prefiere administrar el settings.jsonarchivo subyacente, haga clic en el icono Abrir configuración (JSON) en la parte superior de la región del editor (consulte la Figura 1.23 ). Alternativamente, puede ejecutar el comando Abrir configuración (JSON).


Figura 1.23 :Al hacer clic en el icono Abrir configuración (JSON), se abre elsettings.jsonarchivo en un nuevo editor.

Aunque puede editar el settings.jsonarchivo manualmente, Visual Studio Code proporciona un acceso directo para modificar algunas de las configuraciones. Si pasa el cursor sobre una configuración y ve un ícono de lápiz a la izquierda de la tecla, puede hacer clic en el ícono de lápiz para ver una lista de valores posibles (consulte la Figura 1.24 ).


Figura 1.24 :En elsettings.jsonarchivo, al hacer clic en el icono de lápiz junto a una configuración se proporciona una lista de valores posibles para la configuración.

A diferencia del editor de configuración, debe guardar (Cmd+S/Ctrl+S) el settings.jsonarchivo para que los cambios surtan efecto. Si Visual Studio Code detecta algún error de sintaxis en el archivo, aparece un mensaje solicitando que corrija los errores en el archivo. La sintaxis de la configuración sigue el formato (por ejemplo, es la configuración de la ruta del intérprete de Python para la extensión de Python). category/extension: setting python: pythonPath

NOTA ¿Necesita restablecer todas sus configuraciones de usuario a la configuración predeterminada? En el settings.jsonarchivo, elimine todo lo que esté entre llaves y guarde el archivo.


Temas e íconos de colores
La estética realmente puede mejorar la experiencia al proporcionar combinaciones de colores e iconografía para satisfacer las necesidades y preferencias visuales. Los temas de color le permiten cambiar el color tanto de la interfaz de usuario del editor como del resaltado de sintaxis de su código. El selector de tema de color (Cmd+K, Cmd+T/Ctrl+K, Ctrl+T proporciona acceso a los temas de color disponibles. Puede instalar temas de color adicionales desde Visual Studio Code Marketplace o crear su propio tema de color personalizado.

Los temas de íconos de archivos le permiten cambiar los íconos de archivos que se muestran en el Explorador de archivos y en los encabezados de pestañas. El selector de Tema de ícono de archivo (Preferencias ➪ Tema de ícono de archivo) brinda acceso a los temas de íconos de archivo disponibles. Al igual que con los temas de color, puede instalar temas adicionales desde Visual Studio Code Marketplace o crear su propio tema de ícono de archivo personalizado.

Atajos de teclado
Una vez que tenga experiencia con Visual Studio Code, probablemente querrá mejorar su eficiencia aprendiendo atajos de teclado para los comandos más comunes. Las combinaciones de teclas le brindan la posibilidad de ejecutar la mayoría de los comandos de Visual Studio Code con la ayuda de atajos de teclado. Aunque algunas combinaciones de teclas están preestablecidas de forma predeterminada, puede administrar todas las combinaciones de teclas usted mismo en el editor de métodos abreviados de teclado (Cmd+K, Cmd+S/Ctrl+K, Ctrl+S). El editor de atajos de teclado enumera todos los comandos disponibles con y sin combinaciones de teclas.

Para cambiar una combinación de teclas en el editor de atajos de teclado, seleccione el comando y use el atajo de teclado Cmd+K, Cmd+K/Ctrl+K, Ctrl+K. En la ventana que aparece, ingrese la combinación de teclas que desee y presione Entrar. Si hay un conflicto de combinación de teclas, aparece una alerta en la parte inferior de la ventana que le indica cuántos comandos existentes tienen la combinación de teclas. Al seleccionar la alerta se muestra una lista de todos los comandos que tienen la combinación de teclas asignada.

¿Prefieres utilizar los atajos de teclado de otro entorno de desarrollo? ¡Ningún problema! Las extensiones de mapa de teclas (Cmd+K, Cmd+M/Ctrl+K, Ctrl+M) están disponibles en Extensions Marketplace para Vim, Sublime y Atom, por nombrar algunas. Estas extensiones trasladan las combinaciones de teclas de otros editores a Visual Studio Code.

Idioma de la pantalla
El idioma de visualización predeterminado para Visual Studio Code es el inglés. Puede modificar esta configuración con las extensiones del paquete de idioma. Cuando abre Visual Studio Code por primera vez, el editor detecta automáticamente el idioma de la interfaz de usuario del sistema operativo. Si el idioma no es el inglés, Visual Studio Code le solicita que instale el paquete de idioma apropiado (si está disponible). Una vez instalado el paquete de idioma, reinicie Visual Studio Code para aplicar los cambios.

Si prefiere anular el idioma predeterminado de la interfaz de usuario, utilice el comando Configurar idioma de visualización y seleccione uno de los idiomas disponibles.

Resumen
En este capítulo, aprendió cómo hacer lo siguiente:

Descargue e instale Visual Studio Code desdecode.visualstudio.com/#downloads
Navegar por la interfaz de Visual Studio Code
Reordenar vistas en la barra de actividades
Cree un grupo de editores y abra un nuevo editor
Acceder a la paleta de comandos
Buscar e instalar extensiones en la vista Extensiones
Administre la configuración tanto globalmente como por espacio de trabajo
Cambiar temas de color
Crear combinaciones de teclas personalizadas
Cambiar el idioma de visualización
Con el tiempo, podrá determinar mejor qué extensiones, personalizaciones y configuraciones adicionales pueden ayudarlo a fomentar un flujo de trabajo eficiente y productivo. Si alguna vez necesita información adicional sobre las características de Visual Studio Code, consulte la documentación en code.visualstudio.com/docs.

Nota
1    Las pulsaciones de teclas presentadas en este libro se proporcionan primero para macOS y luego para Windows/Linux.
