# CHAPTER 2: Hello World for Python

* Installing a Python Interpreter
* Installing the Python Extension for Visual Studio Code
* Creating a Python File
* Selecting an Interpreter
* Selecting a Linter
* Editing a Python File
* Running a Python File
* Workflow Recap
* Summary
  
Como se mencionó en el Capítulo 1 , “Introducción”, la compatibilidad con la mayoría de los lenguajes en Visual Studio Code, incluido Python, se logra mediante extensiones. Entonces, para usar Python, debe instalar la extensión junto con un intérprete de Python adecuado. La creación y ejecución de su primer Hello Worldarchivo Python prepara el escenario para las próximas funciones y ejemplos que se exploran en este libro. Como aprenderá en este capítulo, existen varias formas de realizar la misma tarea, como crear, guardar y ejecutar programas. Considere utilizar los enfoques explorados como guía para determinar qué opciones son mejores para su estilo de programación.

Instalación de un intérprete de Python
Visual Studio Code es compatible con Python 2.7 y Python 3.6 o posterior. Aunque la compatibilidad con Python 2.7 está disponible, se recomienda utilizar Python 3.6 o posterior debido a que la versión está obsoleta. Puede confirmar la versión de Python 3.x instalada en su computadora con el comando python3 --version(Linux/macOS) o py -3 --version(Windows). Además, se recomienda agregar Python a su variable de entorno PATH para que pueda escribir code .en cualquier carpeta y comenzar a editar archivos en esa carpeta en particular con Visual Studio Code.

Pruébelo: instale un intérprete de Python para su sistema operativo respectivo. Las instrucciones de instalación recomendadas en esta sección se resumen para cada plataforma compatible.

Mac OS
En macOS, es probable que necesites actualizar tu versión instalada de Python. Se recomienda completar una instalación de Python con Homebrew.

En la terminal, ingrese el comando brew install python3 para instalar Python 3.
En la paleta de comandos de Visual Studio Code, ingrese el comando Comando de Shell: Instalar el comando 'código' en PATH .
Una vez completada la instalación, reinicie el terminal para que el nuevo valor de RUTA surta efecto.
linux
Se admite la instalación integrada de Python 3 en Linux. Sin embargo, para instalar una versión posterior de Python, visite python.org/downloads. Una vez completada la descarga, siga las instrucciones del asistente de instalación para instalar Python.

ventanas
Python se puede instalar desde Microsoft Store.

En Microsoft Store, busque Python .
En los resultados de la búsqueda, seleccione la última versión del idioma.
Haga clic en el botón Obtener para iniciar la descarga.
Una vez completada la descarga, siga las instrucciones del asistente de instalación para instalar Python. Cuando se le solicite, asegúrese de marcar la casilla Agregar Python 3.x a la RUTA.
Instalación de la extensión Python para Visual Studio Code
La extensión Python para Visual Studio Code brinda soporte para el lenguaje Python e incluye características como coloración de sintaxis, finalización de código, linting, depuración, navegación de código y formato de código, junto con características específicas de Python como la compatibilidad con Jupyter Notebook. La extensión de Python se instala en la vista Extensiones de Visual Studio Code. Como cualquier extensión instalada desde Extension Marketplace, puede modificar la configuración de la extensión Python dentro del editor o settings.jsonarchivo de configuración. La pestaña Contribuciones destacadas en la página de detalles de la extensión proporciona una lista completa de configuraciones.

NOTA En el Editor de configuración, las configuraciones de extensión se encuentran dentro de la categoría Extensiones. Para encontrar rápidamente una configuración de extensión de Python específica, busque la configuración en la barra de búsqueda.

Pruébelo: instale la extensión Python desde Extensions Marketplace.

En la barra de actividades, seleccione la vista Extensiones.
Busque Python y seleccione la extensión publicada por Microsoft.
En la página de detalles de la extensión, haga clic en Instalar (consulte la Figura 2.1 ).

Figura 2.1 :Para instalar la extensión Python, haga clic en el botón Instalar en la página de detalles de la extensión debajo de la descripción de la extensión.

Después de la instalación, confirme que la extensión esté instalada desde la página de detalles de la extensión.

Confirme que la extensión esté instalada marcando el botón Desinstalar (consulte la Figura 2.2 ).

Figura 2.2 :Si la extensión Python está instalada, aparece un botón Desinstalar debajo de la descripción de la extensión.

Creando un archivo Python
Utilice una de las siguientes acciones para crear un nuevo archivo:

En el menú, seleccione Archivo ➪ Nuevo archivo.
Presione el método abreviado de teclado Cmd+N/Ctrl+N.
En la vista del Explorador, haga clic en el icono Nuevo archivo.
Al crear un nuevo archivo utilizando uno de los dos primeros métodos, se crea y se abre un nuevo archivo sin título sin guardar en el editor. Si no se proporciona una extensión de archivo en el nombre del archivo, el tipo de archivo predeterminado es Texto sin formato. Cuando Visual Studio Code no conoce el tipo de archivo, el editor no puede proporcionar ningún resaltado de sintaxis ni otras características específicas del idioma. Nombra siempre los archivos Python con la .pyextensión de archivo, que es la forma en que Visual Studio Code sabe activar el intérprete de Python y, de lo contrario, trata el archivo como Python. Si crea un archivo nuevo desde la vista del Explorador, aparece un archivo nuevo en el árbol de carpetas además de un cursor de edición esperando que ingrese un nombre para el archivo. Este método de creación de un nuevo archivo no solo le permite nombrar el archivo con la extensión respectiva, sino que también lo guarda inicialmente. Después de nombrar el archivo, el archivo se abre automáticamente en el editor. Hay mucho que decir sobre cómo organizar sus archivos; sin embargo, esto se explora más en el Capítulo 4 , “Gestión de proyectos y colaboración”.

Pruébelo: utilizando la vista del Explorador, cree un nuevo archivo Python llamado helloworld.py(consulte la Figura 2.3 ).

Abra su carpeta preferida para guardar archivos de Python navegando a Archivo ➪ Abrir o presionando el método abreviado de teclado Cmd+O/Ctrl+O.
En la vista del Explorador, haga clic en el icono Nuevo archivo.

Figura 2.3 :El icono Nuevo archivo en la vista del Explorador crea un nuevo archivo en la carpeta.

Asigne un nombre al archivo helloworld.pyy presione Entrar para abrir el archivo en el editor.
Seleccionar un intérprete
Como se mencionó anteriormente, la extensión Python para Visual Studio Code funciona en conjunto con un intérprete de Python para proporcionar algunas de las características del lenguaje. Hay una etiqueta para la extensión Python en la barra de estado (ver Figura 2.4 ). Esta etiqueta aparece solo si hay un archivo Python abierto. Cuando se abre un archivo Python, la etiqueta muestra el intérprete seleccionado actualmente o un mensaje de advertencia para seleccionar un intérprete.


Figura 2.4 :La barra de estado indica el intérprete de Python seleccionado.

De forma predeterminada, la extensión de Python busca y utiliza el primer intérprete de Python que encuentra en la ruta del sistema. Si la extensión no encuentra un intérprete, la barra de estado le solicita con una advertencia que seleccione uno (consulte la Figura 2.5 ).


Figura 2.5 :Advertencia de la barra de estado para seleccionar un intérprete de Python

Puede seleccionar un intérprete desde la advertencia de la barra de estado o desde el comando Python: seleccione intérprete.

Barra de estado : en la barra de estado, haga clic en la advertencia Seleccionar intérprete de Python. En la ventana que aparece, seleccione un intérprete de la lista de intérpretes disponibles.
Python: seleccione intérprete: ejecute el comando en la paleta de comandos y seleccione un intérprete de la lista de intérpretes disponibles.
Al seleccionar un intérprete, Visual Studio Code le proporciona una lista de entornos globales, virtuales y conda (consulte la Figura 2.6 ). Alternativamente, puede seleccionar Ingresar ruta del intérprete para proporcionar una ruta personalizada a un intérprete.


Figura 2.6 :Se muestra una lista de intérpretes de Python en una ventana después de ejecutar el comando para seleccionar un intérprete.

Se explora información adicional sobre la gestión de entornos en el Capítulo 4 , “Gestión de proyectos y colaboración”.

Pruébelo: seleccione un intérprete para el helloworld.pyarchivo. Pruebe ambos métodos para seleccionar un intérprete.

Configurar un intérprete predeterminado
El intérprete predeterminado es administrado por la configuración Ruta de intérprete predeterminada ( python.pythonPath ). Puede configurar manualmente un intérprete predeterminado dentro del editor de configuración o del settings.jsonarchivo.

Editor de configuración
En el editor de Configuración, busque python.pythonPath .
En la configuración Python: Ruta de Python, ingrese la ruta al intérprete (consulte la Figura 2.7 ).

Figura 2.7 :La ruta a un intérprete de Python se puede ingresar directamente en la interfaz de usuario del Editor de configuración para Python: configuración de ruta de Python.

Archivo settings.json
Ejecute el comando Abrir configuración (JSON).
En el settings.jsonarchivo, cree una nueva línea para python.pythonPath(consulte la Figura 2.8 ).
Para el valor de python.pythonPath, ingrese la ruta al intérprete.

Figura 2.8 :Se crea una nueva línea en elsettings.jsonarchivo para la configuración de la ruta del intérprete de Python.

Seleccionar un Linter
La extensión Python para Visual Studio Code está equipada con linting, una característica que ayuda a detectar problemas en su programa. Aunque no es necesario que utilice un linter, Visual Studio Code le ofrece la opción de instalar uno (Pylint, el valor predeterminado) si el editor detecta que hay un archivo Python abierto.

Visual Studio Code admite los siguientes linters:

Pylint (predeterminado)
escama8
mipy
estilo pydocs
estilopycode (pep8)
prospector
pílama
bandido
Puede seleccionar un linter haciendo clic en el mensaje para instalar Pylint o seleccionando uno con el comando Python de la paleta de comandos: seleccione Linter. El comando Python: Seleccionar Linter se puede utilizar para desactivar linting.

Pruébelo: seleccione un linter para el helloworld.pyarchivo.

Ejecute el comando Python: seleccione Linter en la paleta de comandos.
Seleccione su linter preferido. Si no tiene una preferencia, seleccione Pylint.
Editar un archivo Python
Cuando comienza a editar archivos en Visual Studio Code, una variedad de características trabajan juntas para ayudarlo a mantener su código. IntelliSense es una de esas funciones que proporciona finalización de código, información de parámetros, información rápida y listas de miembros. Otra característica es el formato, que proporciona coherencia en la forma en que se escribe el código y no afecta la funcionalidad del código.

Visual Studio Code proporciona varios indicadores visuales que le permiten saber si sus cambios se han guardado.

Ícono del Explorador : en la barra de actividades, aparece un ícono de número rodeado por un círculo encima del ícono del Explorador para indicar la cantidad de archivos abiertos no guardados (consulte la Figura 2.9 ).

Figura 2.9 :El número 1 en el ícono del Explorador indica que hay un archivo abierto sin guardar en el editor.

Editores abiertos : en la vista del Explorador, los archivos no guardados se enumeran en la sección Editores abiertos. La etiqueta # Unsaved a la derecha del encabezado de la sección indica la cantidad de archivos no guardados (consulte la Figura 2.10 ).

Figura 2.10 :La etiqueta 1 No guardado en la sección Editores abiertos indica que hay un archivo abierto sin guardar en el editor.

Punto en el nombre de archivo: en la vista del Explorador, aparece un punto a la derecha del nombre de un archivo si los cambios no se guardan (consulte la Figura 2.11 ).

Figura 2.11 :El ícono de punto al lado del nombre del archivo indica que los cambios realizados en el archivo no se han guardado.

Cerrar guardados (Cmd+K, U/Ctrl+K, U) : en la región superior del editor, haga clic en los tres puntos seguidos del elemento de menú Cerrar guardados para cerrar todos los archivos que se han guardado (consulte la Figura 2.12 ).

Figura 2.12 :Se accede al elemento de menú Cerrar guardado seleccionando los tres puntos en la región superior del editor.

Como la mayoría de los comandos de Visual Studio Code, existen varias formas de guardar un archivo.

En el menú, seleccione Archivo ➪ Guardar o Archivo ➪ Guardar todo.
Presione Cmd+S/Ctrl+S (para guardar).
Presione Opción+Cmd+S/Ctrl+K+S (para guardar todo).
Tenga en cuenta que ejecutar un archivo Python, como se describe en la siguiente sección, guarda automáticamente el archivo antes de ejecutar el programa.

Los cambios también se pueden guardar automáticamente en lugar de guardarlos explícitamente. La opción Guardar automáticamente guarda los cambios después de un retraso configurado o cuando su enfoque abandona el editor. Para habilitar el guardado automático, navegue hasta Archivo ➪ Guardar automáticamente. Antes de habilitar el guardado automático, considere si esta función es ideal para su proyecto. Si está utilizando el control de código fuente junto con su proyecto, Auto Save puede proporcionar una versión anterior a la que puede volver. Sin embargo, si no está utilizando el control de código fuente, el guardado automático puede sobrescribir un archivo anterior, lo que hace que sea más difícil recuperar una versión anterior. Si no ha cerrado el editor después de un guardado automático reciente, puede usar Deshacer (Cmd+Z/Ctrl+Z) para deshacer los cambios. Desafortunadamente, si cerró el editor después de guardar los cambios, la versión anterior del archivo será irrecuperable.

Se pueden establecer ajustes de configuración adicionales para el guardado automático en la configuración de Usuario o Espacio de trabajo.

files.autoSavepuede tener estos valores:

off—para desactivar el guardado automático
afterDelay—para guardar archivos después de un retraso configurado (predeterminado 1000 ms)
onFocusChange—para guardar archivos cuando el foco sale del editor del archivo no guardado
onWindowChange—para guardar archivos cuando el foco sale de la ventana de Visual Studio Code
La files.autoSaveDelayconfiguración configura el retraso en milisegundos cuando files.autoSaveestá configurado en afterDelay.

Pruébelo: en el helloworld.pyarchivo, realice un cambio y guárdelo.

Ejecutar un archivo Python
En Visual Studio Code, los archivos Python se ejecutan en la terminal integrada utilizando el intérprete de Python seleccionado actualmente. Cuando se ejecuta un archivo, el terminal integrado se abre en el área de Paneles. El terminal integrado comienza en la raíz de su espacio de trabajo.

Los archivos se pueden ejecutar de una de tres maneras:

Haga clic en el botón Reproducir (consulte la Figura 2.13 ).
Haga clic derecho en cualquier parte del editor y seleccione Ejecutar archivo Python en la terminal.
Ejecute el comando Python: Ejecute el archivo Python en la terminal.
El comando Ejecutar abre la terminal integrada, activa el intérprete de Python que eligió para el archivo y luego inicia el intérprete de Python con el archivo como entrada.


Figura 2.13 :El botón Reproducir aparece en la parte superior derecha del editor.

Pruébelo: pruebe cada método para ejecutar un archivo Python en la terminal integrada. Cada vez que pruebe un nuevo método, modifique la cadena en la printdeclaración y ejecute el método sin guardar explícitamente el archivo.

Resumen del flujo de trabajo
Después de seleccionar un intérprete de Python para el editor, en su forma más simple, el flujo de trabajo para crear y ejecutar archivos de Python requiere lo siguiente:

Cree un nuevo archivo en Visual Studio Code y asígnele un nombre con la extensión Python (consulte la Figura 2.14 ).

Figura 2.14 :Seleccione el icono Nuevo archivo en la vista del Explorador y asigne un nombre con la.pyextensión.

Ingrese el código en el editor para el archivo y guárdelo (consulte la Figura 2.15 ). Si hay algún error, asegúrese de corregirlo.

Figura 2.15 :En el editor, ingrese el código en el archivo.

Ejecute el archivo Python (consulte la Figura 2.16 ).

Figura 2.16 :Haga clic en el botón Reproducir en la región del editor superior para abrir el terminal integrado y ejecutar el archivo.

Resumen
En este capítulo, aprendió cómo hacer lo siguiente:

Para editar y ejecutar código Python en Visual Studio Code, debe instalar la extensión Python y un intérprete de Python adecuado versión 3.6+.
Visual Studio Code indica visualmente los archivos no guardados de tres maneras: el ícono del Explorador, la etiqueta No guardado y un ícono de punto al lado del nombre del archivo. Alternativamente, también puede seleccionar el elemento de menú Cerrar guardado en la región del editor superior.
Para configurar un intérprete predeterminado, seleccione el intérprete en el editor de configuración o ingrese la ruta python: pythonPathen settings.json.
Aunque Pylint es el linter predeterminado, puede ejecutar el comando Python: seleccione Linter para seleccionar un linter diferente.
Guarde archivos usando el menú Archivo o los atajos de teclado.
Hay varias formas de ejecutar un archivo Python, como el botón Reproducir y el comando Python: ejecutar archivo Python en la terminal.
En esta etapa, su entorno está configurado y listo para el desarrollo de Python. El Capítulo 4 explora más formas en las que puede administrar sus programas y proyectos Python. Asegúrese de familiarizarse con el flujo de trabajo básico de creación, guardado y ejecución de programas antes de continuar con los siguientes ejemplos en capítulos posteriores.
