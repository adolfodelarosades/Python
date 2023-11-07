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
  
Como se mencionó en el Capítulo 1, “Introducción”, la compatibilidad con la mayoría de los lenguajes en Visual Studio Code, incluido Python, se logra mediante extensiones. Entonces, para usar Python, debe instalar la extensión junto con un intérprete de Python adecuado. La creación y ejecución de su primer archivo **`Hello World`** Python prepara el escenario para las próximas funciones y ejemplos que se exploran en este libro. Como aprenderá en este capítulo, existen varias formas de realizar la misma tarea, como crear, guardar y ejecutar programas. Considere utilizar los enfoques explorados como guía para determinar qué opciones son mejores para su estilo de programación.

## Instalación de un intérprete de Python

Visual Studio Code es compatible con **Python 2.7** y **Python 3.6** o posterior. Aunque la compatibilidad con **Python 2.7** está disponible, se recomienda utilizar **Python 3.6** o posterior debido a que la versión está obsoleta. Puede confirmar la versión de **Python 3.x** instalada en su computadora con el comando **`python3 --version`** (Linux/macOS) o **`py -3 --version`** (Windows). Además, se recomienda agregar Python a su variable de entorno PATH para que pueda escribir **`code .`** en cualquier carpeta y comenzar a editar archivos en esa carpeta en particular con Visual Studio Code.

**Pruébelo**: instale un intérprete de Python para su sistema operativo respectivo. Las instrucciones de instalación recomendadas en esta sección se resumen para cada plataforma compatible.

### Mac OS

En macOS, es probable que necesites actualizar tu versión instalada de Python. Se recomienda completar una instalación de Python con Homebrew.

1. En la terminal, ingrese el comando **`brew install python3`** para instalar Python 3.
2. En la paleta de comandos de Visual Studio Code, ingrese el comando Comando de Shell: **Install ‘code’ command in PATH.**
3. Una vez completada la instalación, reinicie el terminal para que el nuevo valor de PATH surta efecto.

### Linux

Se admite la instalación integrada de Python 3 en Linux. Sin embargo, para instalar una versión posterior de Python, visite python.org/downloads. Una vez completada la descarga, siga las instrucciones del asistente de instalación para instalar Python.

### Windows

Python se puede instalar desde Microsoft Store.

1. En Microsoft Store, busque *Python*.
2. En los resultados de la búsqueda, seleccione la última versión del language.
3. Haga clic en el botón Get para iniciar la descarga.
4. Una vez completada la descarga, siga las instrucciones del asistente de instalación para instalar Python. Cuando se le solicite, asegúrese de marcar la casilla Add Python 3.x To PATH box.

### Instalación de la extensión Python para Visual Studio Code

La extensión Python para Visual Studio Code brinda soporte para el lenguaje Python e incluye características como coloración de sintaxis, finalización de código, linting, depuración, navegación de código y formato de código, junto con características específicas de Python como la compatibilidad con **Jupyter Notebook**. La extensión de Python se instala en la vista Extensiones de Visual Studio Code. Como cualquier extensión instalada desde Extension Marketplace, puede modificar la configuración de la extensión Python dentro del editor o archivo **`settings.json`** de configuración. La pestaña Featured Contributions en la página de detalles de la extensión proporciona una lista completa de configuraciones.

<hr>

**NOTA** En el Editor de configuración, las configuraciones de extensión se encuentran dentro de la categoría Extensiones. Para encontrar rápidamente una configuración de extensión de Python específica, busque la configuración en la barra de búsqueda.

<hr>

**Pruébelo**: instale la extensión Python desde Extensions Marketplace.

1. En la Activity Bar, seleccione la vista Extensiones.
2. Busque Python y seleccione la extensión publicada por Microsoft.
3. En la página de detalles de la extensión, haga clic en Instalar (consulte la Figura 2.1 ).

   ![image](https://github.com/adolfodelarosades/Python/assets/23094588/466aba70-4103-4fde-bc24-a41b7af11f3e)

   **Figura 2.1: Para instalar la extensión Python, haga clic en el botón Instalar en la página de detalles de la extensión debajo de la descripción de la extensión.**

   Después de la instalación, confirme que la extensión esté instalada desde la página de detalles de la extensión.

4. Confirme que la extensión esté instalada marcando el botón Desinstalar (consulte la Figura 2.2 ).

   ![image](https://github.com/adolfodelarosades/Python/assets/23094588/e907cce1-34e5-4f52-aa98-e62852792422)

   **Figura 2.2 :Si la extensión Python está instalada, aparece un botón Uninstall debajo de la descripción de la extensión.**

## Creando un archivo Python

Utilice una de las siguientes acciones para crear un nuevo archivo:

* En el menú, seleccione File ➪ New File.
* Presione el método abreviado de teclado **`Cmd+N/Ctrl+N`**.
* En la vista del Explorador, haga clic en el icono New File.
  
Al crear un nuevo archivo utilizando uno de los dos primeros métodos, se crea y se abre un nuevo archivo sin título sin guardar en el editor. Si no se proporciona una extensión de archivo en el nombre del archivo, el tipo de archivo predeterminado es Plain Text - Texto Plano. Cuando Visual Studio Code no conoce el tipo de archivo, el editor no puede proporcionar ningún resaltado de sintaxis ni otras características específicas del lenguaje. Nombra siempre los archivos Python con la extensión **`.py`** de archivo, que es la forma en que Visual Studio Code sabe activar el intérprete de Python y, de lo contrario, trata el archivo como Python. Si crea un archivo nuevo desde la vista del Explorador, aparece un archivo nuevo en el árbol de carpetas además de un cursor de edición esperando que ingrese un nombre para el archivo. Este método de creación de un nuevo archivo no solo le permite nombrar el archivo con la extensión respectiva, sino que también lo guarda inicialmente. Después de nombrar el archivo, el archivo se abre automáticamente en el editor. Hay mucho que decir sobre cómo organizar sus archivos; sin embargo, esto se explora más en el Capítulo 4 , “Gestión de proyectos y colaboración”.

**Pruébelo**: utilizando la vista del Explorador, cree un nuevo archivo Python llamado **`helloworld.py`**(consulte la Figura 2.3).

1. Abra su carpeta preferida para guardar archivos de Python navegando a File ➪ Open o presionando el método abreviado de teclado **`Cmd+O/Ctrl+O`**.
2. En la vista del Explorador, haga clic en el icono New File.

   ![image](https://github.com/adolfodelarosades/Python/assets/23094588/c52c6f44-5f2c-4932-ac99-527b20a7c103)

   **Figura 2.3: El icono New File en la vista del Explorador crea un nuevo archivo en la carpeta.**

3. Asigne un nombre al archivo **`helloworld.py`** y presione Enter  para abrir el archivo en el editor.

### Seleccionar un intérprete

Como se mencionó anteriormente, la extensión Python para Visual Studio Code funciona en conjunto con un intérprete de Python para proporcionar algunas de las características del lenguaje. Hay una etiqueta para la extensión Python en la barra de estado (ver Figura 2.4 ). Esta etiqueta aparece solo si hay un archivo Python abierto. Cuando se abre un archivo Python, la etiqueta muestra el intérprete seleccionado actualmente o un mensaje de advertencia para seleccionar un intérprete.

![image](https://github.com/adolfodelarosades/Python/assets/23094588/7ef21e37-e303-4fe0-a5eb-5efe729f7972)

**Figura 2.4: La barra de estado indica el intérprete de Python seleccionado.**

De forma predeterminada, la extensión de Python busca y utiliza el primer intérprete de Python que encuentra en la ruta del sistema. Si la extensión no encuentra un intérprete, la barra de estado le solicita con una advertencia que seleccione uno (consulte la Figura 2.5 ).

![image](https://github.com/adolfodelarosades/Python/assets/23094588/6f764b2d-ed9c-43ca-81b5-217e37c95e81)

**Figura 2.5: Advertencia de la barra de estado para seleccionar un intérprete de Python**

Puede seleccionar un intérprete desde la advertencia de la barra de estado o desde el comando Python: Select Interpreter.

* **Status Bar**: en la barra de estado, haga clic en la advertencia Seleccionar intérprete de Python. En la ventana que aparece, seleccione un intérprete de la lista de intérpretes disponibles.
* **Python: Select Interpreter**: ejecute el comando en la paleta de comandos y seleccione un intérprete de la lista de intérpretes disponibles.

Al seleccionar un intérprete, Visual Studio Code le proporciona una lista de entornos globales, virtuales y conda (consulte la Figura 2.6 ). Alternativamente, puede seleccionar Enter Interpreter Path para proporcionar una ruta personalizada a un intérprete.

![image](https://github.com/adolfodelarosades/Python/assets/23094588/aa649ba4-40a7-44e2-a507-aa8905712abb)

**Figura 2.6: Se muestra una lista de intérpretes de Python en una ventana después de ejecutar el comando para seleccionar un intérprete.**

Se explora información adicional sobre la gestión de entornos en el Capítulo 4, “Gestión de proyectos y colaboración”.

**Pruébelo**: seleccione un intérprete para el archivo **`helloworld.py`**. Pruebe ambos métodos para seleccionar un intérprete.

### Configurar un intérprete predeterminado

El intérprete predeterminado es administrado por la configuración Ruta de intérprete predeterminada ( **`python.pythonPath`** ). Puede configurar manualmente un intérprete predeterminado dentro del editor de configuración o del archivo **`settings.json`**.

#### Editor de configuración 

1. En el editor de Configuración, busque **`python.pythonPath`**.
2. En la Python: Python Path setting, ingrese la ruta al intérprete (consulte la Figura 2.7 ).

   ![image](https://github.com/adolfodelarosades/Python/assets/23094588/a971c360-cfe9-4dba-acb4-a7d4b8acab48)

   **Figura 2.7: La ruta a un intérprete de Python se puede ingresar directamente en la Settings Editor UI for the Python: Python Path setting.**

#### Archivo `settings.json`

1. Ejecute el comando Open Settings (JSON).
2. En el archivo **`settings.json`**, cree una nueva línea para **`python.pythonPath`**(consulte la Figura 2.8 ).

Para el valor de **`python.pythonPath`**, ingrese la ruta al intérprete.

![image](https://github.com/adolfodelarosades/Python/assets/23094588/ff0aff2b-37c7-445f-a042-dc32ef4c3bad)

**Figura 2.8: Se crea una nueva línea en el archivo `settings.json` para la configuración de la ruta del intérprete de Python.**

### Seleccionar un Linter

La extensión Python para Visual Studio Code está equipada con linting, una característica que ayuda a detectar problemas en su programa. Aunque no es necesario que utilice un linter, Visual Studio Code le ofrece la opción de instalar uno (**Pylint**, el valor predeterminado) si el editor detecta que hay un archivo Python abierto.

Visual Studio Code admite los siguientes linters:

* Pylint (default)
* Flake8
* mypy
* pydocsstyle
* pycodestyle (pep8)
* prospector
* pylama
* bandit

Puede seleccionar un linter haciendo clic en el mensaje para instalar Pylint o seleccionando uno con el Command Palette command Python: Select Linter. The Python: Select Linter command se puede utilizar para desactivar linting.

**Pruébelo**: seleccione un linter para el archivo **` helloworld.py`**.

1. Ejecute el comando Python: Select Linter from the Command Palette.
2. Seleccione su linter preferido. Si no tiene una preferencia, seleccione Pylint.


### Editar un archivo Python

Cuando comienza a editar archivos en Visual Studio Code, una variedad de características trabajan juntas para ayudarlo a mantener su código. **IntelliSense** es una de esas funciones que proporciona finalización de código, información de parámetros, información rápida y listas de miembros. Otra característica es el formato, que proporciona coherencia en la forma en que se escribe el código y no afecta la funcionalidad del código.

Visual Studio Code proporciona varios indicadores visuales que le permiten saber si sus cambios se han guardado.

* **Explorer Icon**: en la barra de actividades, aparece un ícono de número rodeado por un círculo encima del ícono del Explorador para indicar la cantidad de archivos abiertos no guardados (consulte la Figura 2.9 ).

   ![image](https://github.com/adolfodelarosades/Python/assets/23094588/3feebb86-dc55-48e2-8097-1485f5abf708)

   **Figura 2.9: El número 1 en el ícono del Explorador indica que hay un archivo abierto sin guardar en el editor.**

* **Open Editors**: en la vista del Explorador, los archivos no guardados se enumeran en la sección Editores abiertos. La etiqueta # Unsaved a la derecha del encabezado de la sección indica la cantidad de archivos no guardados (consulte la Figura 2.10 ).

   ![image](https://github.com/adolfodelarosades/Python/assets/23094588/b86ca83a-2902-4873-bc6a-7854cae14350)

   **Figura 2.10: La etiqueta 1 No guardado en la sección Editores abiertos indica que hay un archivo abierto sin guardar en el editor.**

* **Dot on Filename**: en la vista del Explorador, aparece un punto a la derecha del nombre de un archivo si los cambios no se guardan (consulte la Figura 2.11 ).

   ![image](https://github.com/adolfodelarosades/Python/assets/23094588/f803e1fe-3085-48d7-810e-c91e429130fc)

   **Figura 2.11: El ícono de punto al lado del nombre del archivo indica que los cambios realizados en el archivo no se han guardado.**

* **Close Saved (`Cmd+K, U/Ctrl+K, U`)**: en la región superior del editor, haga clic en los tres puntos seguidos del elemento de menú Cerrar guardados para cerrar todos los archivos que se han guardado (consulte la Figura 2.12 ).

   ![image](https://github.com/adolfodelarosades/Python/assets/23094588/f444e3fc-c5a6-4298-9f74-ac58ba667005)

   **Figura 2.12: Se accede al elemento de menú Close Saved seleccionando los tres puntos en la región superior del editor.**

Como la mayoría de los comandos de Visual Studio Code, existen varias formas de guardar un archivo.

* En el menú, seleccione File ➪ Save or File ➪ Save All.
* Presione **`Cmd+S/Ctrl+S`** (para guardar).
* Presione **`Option+Cmd+S/Ctrl+K+S`** (para guardar todo).

Tenga en cuenta que ejecutar un archivo Python, como se describe en la siguiente sección, guarda automáticamente el archivo antes de ejecutar el programa.

Los cambios también se pueden guardar automáticamente en lugar de guardarlos explícitamente. La opción Auto Save guarda los cambios después de un retraso configurado o cuando su enfoque abandona el editor. Para habilitar el guardado automático, navegue hasta File ➪ Auto Save. Antes de habilitar el guardado automático, considere si esta función es ideal para su proyecto. Si está utilizando el control de código fuente junto con su proyecto, Auto Save puede proporcionar una versión anterior a la que puede volver. Sin embargo, si no está utilizando el control de código fuente, el guardado automático puede sobrescribir un archivo anterior, lo que hace que sea más difícil recuperar una versión anterior. Si no ha cerrado el editor después de un guardado automático reciente, puede usar Deshacer (**`Cmd+Z/Ctrl+Z`**) para deshacer los cambios. Desafortunadamente, si cerró el editor después de guardar los cambios, la versión anterior del archivo será irrecuperable.

Se pueden establecer ajustes de configuración adicionales para el guardado automático en la configuración de Usuario o Workspace.

**`files.autoSave`** puede tener estos valores:

* **`off`**—para desactivar el guardado automático
* **`afterDelay`**—para guardar archivos después de un retraso configurado (predeterminado 1000 ms)
* **`onFocusChange`**—para guardar archivos cuando el foco sale del editor del archivo no guardado
* **`onWindowChange`**—para guardar archivos cuando el foco sale de la ventana de Visual Studio Code

La configuración **`files.autoSaveDelay`** configura el retraso en milisegundos cuando **`files.autoSave`** está configurado en **`afterDelay`**.

**Pruébelo**: en el archivo **`helloworld.py`**, realice un cambio y guárdelo.

## Ejecutar un archivo Python

En Visual Studio Code, los archivos Python se ejecutan en la terminal integrada utilizando el intérprete de Python seleccionado actualmente. Cuando se ejecuta un archivo, el terminal integrado se abre en el área de Paneles. El terminal integrado comienza en la raíz de su espacio de trabajo.

Los archivos se pueden ejecutar de una de tres maneras:

* Haga clic en el botón Play (consulte la Figura 2.13 ).
* Haga clic derecho en cualquier parte del editor y seleccione Run Python File en la terminal.
* Ejecute el comando Python: Run Python File en la terminal.

El comando Run abre la terminal integrada, activa el intérprete de Python que eligió para el archivo y luego inicia el intérprete de Python con el archivo como entrada.

![image](https://github.com/adolfodelarosades/Python/assets/23094588/63197034-2774-4be7-b3d3-9ce3ef1bfbd1)

**Figura 2.13: El botón Play aparece en la parte superior derecha del editor.**

**Pruébelo**: pruebe cada método para ejecutar un archivo Python en la terminal integrada. Cada vez que pruebe un nuevo método, modifique la cadena en la sentencia **`print`** y ejecute el método sin guardar explícitamente el archivo.

## Resumen del Workflow

Después de seleccionar un intérprete de Python para el editor, en su forma más simple, el flujo de trabajo para crear y ejecutar archivos de Python requiere lo siguiente:

1. Cree un nuevo archivo en Visual Studio Code y asígnele un nombre con la extensión Python (consulte la Figura 2.14 ).

   ![image](https://github.com/adolfodelarosades/Python/assets/23094588/15696a92-5cc5-4946-88cd-38ad065d6260)

   **Figura 2.14: Seleccione el icono New File en la vista del Explorador y asigne un nombre con la extensión `.py`.**

2. Ingrese el código en el editor para el archivo y guárdelo (consulte la Figura 2.15 ). Si hay algún error, asegúrese de corregirlo.

    ![image](https://github.com/adolfodelarosades/Python/assets/23094588/6fc723c9-fd73-4e20-a842-41bbdbda7aae)

    **Figura 2.15: En el editor, ingrese el código en el archivo.**

3. Ejecute el archivo Python (consulte la Figura 2.16 ).

   ![image](https://github.com/adolfodelarosades/Python/assets/23094588/fbaff196-49a7-4734-a3c0-473abf91bb50)

   **Figura 2.16: Haga clic en el botón Play en la región del editor superior para abrir el terminal integrado y ejecutar el archivo.**

## Resumen

En este capítulo, aprendió cómo hacer lo siguiente:

* Para editar y ejecutar código Python en Visual Studio Code, debe instalar la extensión Python y un intérprete de Python adecuado versión 3.6+.
* Visual Studio Code indica visualmente los archivos no guardados de tres maneras: el ícono del Explorador, la etiqueta No guardado y un ícono de punto al lado del nombre del archivo. Alternativamente, también puede seleccionar el elemento de menú Close Saved en la región del editor superior.
* Para configurar un intérprete predeterminado, seleccione el intérprete en el editor de configuración o ingrese la ruta **`python: pythonPath`** en **`settings.json`**.
* Aunque Pylint es el linter predeterminado, puede ejecutar el comando Python: Select Linter para seleccionar un linter diferente.
* Guarde archivos usando el menú File o los atajos de teclado.
* Hay varias formas de ejecutar un archivo Python, como el botón Play y el comando Python: Run Python File In Terminal.

En esta etapa, su entorno está configurado y listo para el desarrollo de Python. El Capítulo 4 explora más formas en las que puede administrar sus programas y proyectos Python. Asegúrese de familiarizarse con el flujo de trabajo básico de creación, guardado y ejecución de programas antes de continuar con los siguientes ejemplos en capítulos posteriores.
