# CHAPTER 3: Editing Code
* Quick Fixes
* Code Completion, Definitions, and Declarations
* Formatting
* Linting
* Refactoring
* Snippets
* Summary

Visual Studio Code proporciona una serie de funciones de edición estándar que funcionan para todos los lenguajes de programación.

* Quick Fixes
* Code completion
* Definitions
* Declarations
* Formatting
* Linting
* Refactoring
* Code snippets

Estas funciones de edición integradas ahorran tiempo al reducir la cantidad de tareas manuales y escritura que normalmente pueden ser necesarias para editar el código.

La extensión de Python amplía la funcionalidad de las funciones de edición de código al proporcionar soporte específico de Python. Con la extensión Python, importar bibliotecas requiere un esfuerzo mínimo, ya que la extensión puede sugerir paquetes instalados para importar a un programa. Más a menudo, después de unos pocos caracteres escritos, el editor puede autocompletar líneas de código, proporcionar definiciones e incluso localizar declaraciones.

Ya sea que prefiera autopep8, Black o YAPF, puede configurar el formateador que desee y personalizar la configuración para asegurarse de que el código fuente tenga el formato que desee. A medida que ejecuta su código Python, linting analiza cómo se ejecuta el código y genera errores en el panel Problemas. Si encuentra la necesidad de refactorizar un programa Python, hay comandos disponibles para extraer variables, métodos y ordenar importaciones. Además, puede ahorrar tiempo utilizando fragmentos de código para evitar ingresar manualmente patrones de código repetidos.

En este capítulo, cada función de edición se explora en un script llamado circle_area.pyque utiliza el mathmódulo para calcular el área de un círculo. Antes de probar los ejemplos de este capítulo, cree un nuevo archivo Python llamado circle_area.pyen una carpeta de proyecto adecuada.

Arreglos rápidos
Las soluciones rápidas ayudan a solucionar problemas identificados mediante advertencias o errores. Si hay una posible solución disponible, Visual Studio Code muestra una línea ondulada azul debajo del código fuente y un ícono de bombilla en el margen izquierdo del editor. Al hacer clic en la bombilla se muestra la opción Solución rápida o se realiza la acción.

Además de las correcciones rápidas que están disponibles de forma predeterminada con Visual Studio Code, las extensiones instaladas desde Marketplace también pueden incluir su propio conjunto de correcciones rápidas. La extensión Python, por ejemplo, tiene una solución rápida para agregar importaciones que completa rápidamente importlas declaraciones. Cuando comience a escribir el nombre de un paquete en el editor, notará que aparece una solución rápida para completar automáticamente la importdeclaración. Al seleccionar el icono de la bombilla se muestra una lista de sugerencias de importación. importLas declaraciones para paquetes se enumeran primero, seguidas de declaraciones para módulos y/o miembros adicionales (clases, objetos, etc.) de paquetes específicos.

NOTA Esta funcionalidad requiere el uso de Microsoft Python Language Server. Para habilitar el servidor de idiomas, configúrelo "python.jediEnabled ": falseen su settings.jsonarchivo.

NOTA La solución rápida para agregar importaciones requiere que el módulo que desea importar ya esté instalado en el entorno.

Pruébelo: en el editor, escriba mathpara invocar la solución rápida para agregar importaciones. Seleccione la acción del código (por ejemplo, la bombilla). Sugiere Visual Studio Code import math as m(consulte la Figura 3.1 ). Seleccione para agregar la importdeclaración al código.


Figura 3.1 :Sugiere la acción de código Agregar importacionesimport math as m.

Una vez que se agrega la importdeclaración, Visual Studio Code la elimina mathdel código y la reemplaza con la declaración de importación.

La acción de código agregar importaciones también reconoce otras abreviaturas comunes para los siguientes paquetes de Python: NumPy as np, TensorFlow as tf, pandas as pd, matplotlib.pyplot as plt, matplotlib as mpl, SciPi as spioy SciPy as sp.

Finalización de códigos, definiciones y declaraciones
IntelliSense es el nombre que utiliza Microsoft para identificar una variedad de herramientas útiles para ayudar con la programación, como la finalización de código, la definición de objetos y la ubicación de declaraciones de objetos o variables. Estas funciones se activan presionando Ctrl+barra espaciadora o escribiendo un carácter activador (como el carácter de punto en Python).

A medida que escribe, la extensión de Python proporciona finalización de código inteligente basada en la semántica de Python y un análisis del código fuente. Si se conoce una posible finalización, Visual Studio Code proporciona sugerencias.

Pruébelo: en circle_area.py, utilice la finalización de código para ver los métodos de Python sugeridos.

En una nueva línea, cree una variable radius. Esta variable contiene la entrada para el radio que se utilizará en el cálculo.
Para la radiusasignación de variables, escriba f. Observe que Visual Studio Code sugiere métodos a medida que escribe (consulte la Figura 3.2 ). Utilice las teclas de flecha seguidas de la tecla Tab para seleccionar el método flotante.

Figura 3.2 :Visual Studio Code sugiere elfloatmétodo.

Dentro del método float, escriba i. En la lista de sugerencias, seleccione el método de entrada.
Complete la asignación de variables con lo siguiente:
radius = float(input('Radius: '))
 
En un ejemplo sencillo como este ejercicio, los beneficios de la finalización automática son mínimos. Sin embargo, el autocompletado es valioso cuando el código se vuelve más complicado y se utilizan objetos, métodos y propiedades que tienen varios niveles de profundidad. En definitiva, estas indicaciones le liberan de tener que consultar la documentación de referencia para conocer cada detalle. En cambio, Visual Studio Code le ofrece la referencia.

Las definiciones traen documentación de referencia externa para bibliotecas importadas al contexto de su código fuente. Como se mencionó, el carácter de punto activa la finalización del código junto con una lista de funciones del módulo.

Pruébelo: en circle_area.py, use definiciones para ver una lista de constantes y funciones dentro del mathmódulo.

En una nueva línea, cree una area =variable. La variable cumple la petición de la ecuación para calcular el área de un círculo (A = π r 2 ).
El valor de π necesario en la ecuación está disponible en la mathbiblioteca como math.pi. Después area =, comience a escribir m.y observe que VS Code proporciona una lista de constantes y funciones en el mathmódulo (consulte la Figura 3.3 ).

Figura 3.3 :Definiciones proporciona una lista de constantes y funciones dentro delmathmódulo.

Utilice las teclas de flecha para desplazarse por la lista y localizar pi. Una vez encontrado, haga clic en la flecha derecha para ver el tipo de objeto (consulte la Figura 3.4 ). Después de ver el tipo de objeto, seleccione pi.
Continúe la ecuación del área con un cálculo para r 2 . En el editor, ingrese m.py use las teclas de flecha para ubicar la powfunción. Una vez encontrada, seleccione la función.

Figura 3.4 :El tipo de objetopies flotante.

El editor proporciona más orientación para usar la función una vez que se agrega un par de paréntesis (consulte la Figura 3.5 ). Escriba (para agregar un par de paréntesis a la powfunción para ver más instrucciones proporcionadas por Visual Studio Code.

Figura 3.5 :Visual Studio Code proporciona una descripción de lapowfunción además de una guía de parámetros.

Complete la asignación de variables, agregue una printdeclaración para imprimir areay ejecute el código.
import math as m
 
radius = float(input('Radius: '))
area = ma.pi * (m.pow(radius, 2))
print(area)
 
A medida que los programas Python se vuelven más complejos, puede convertirse en un desafío realizar un seguimiento de dónde se declaran los objetos o variables en el código fuente. Las declaraciones le ayudan a localizar dónde se declara un objeto o variable: simplemente coloque el cursor de edición en un objeto o variable y Visual Studio Code resaltará cada referencia a ese objeto o variable, hasta su declaración.

Pruébelo: ubique dónde arease declara en el código colocando el cursor en la areavariable en la printdeclaración. Observe que cada instancia de la areavariable ahora está resaltada en el editor (consulte la Figura 3.6 ).


Figura 3.6 :Laareavariable se resalta dos veces en el editor hasta su declaración.

Formato
Los formateadores proporcionan automáticamente un estilo coherente para formatear el código, lo que permite a los desarrolladores dedicar más tiempo a escribir código en lugar de preocuparse por los detalles de seguir una guía de estilo. Para proyectos colaborativos, los formateadores también tienen el potencial de reducir la cantidad de conflictos de fusión como resultado de que los contribuyentes utilicen el mismo formateador, proporcionando así un estilo similar. Considere el bloque del siguiente código del forbucle que toma un número de la lista numbersy lo multiplica por 2 :

numbers = [2, 4, 6, 8]
 
for num in numbers :
    num = num * 2
    print (num)
Tenga en cuenta el uso inadecuado del espaciado. En este caso, se podría utilizar un formateador para formatear automáticamente el código de acuerdo con una guía de estilo definida. Por ejemplo, el formateador autopep8 formatearía el código de la siguiente manera:

numbers = [2, 4, 6, 8]
 
for num in numbers:
    num = num * 2
    print(num)
A medida que los programas se vuelven más largos, la automatización del formateo proporcionada por un formateador se vuelve invaluable para el flujo de trabajo del desarrollador.

La extensión Python para Visual Studio Code admite los siguientes formateadores:

autopep8 (predeterminado) : formatea el código Python para que se ajuste a la guía de estilo PEP 8. autopep8 utiliza la herramienta linting pycodestyle para determinar qué partes del código deben formatearse e intenta solucionarlo.
Negro: se centra en la coherencia y no es configurable. Black ofrece pocas opciones de línea de comandos en comparación con otros formateadores de Python.
YAPF : configurable y se centra únicamente en formatear el código. YAPF toma el código y lo reformatea con el mejor formato que se ajuste a la guía de estilo, incluso si el código original no viola la guía de estilo. YAPF no corrige errores de linting.
Seleccionar un formateador u otro es una cuestión de preferencia personal. Si prefiere seguir la guía de estilo de PEP 8 mientras soluciona los problemas descubiertos por un linter, entonces autopep8 sería el mejor formateador para usted. Si prefiere configurar un formateador para que siga una guía de estilo preferida, formatee su código de acuerdo con la guía de estilo y evite solucionar problemas de linting, entonces YAPF sería el formateador recomendado. Sin embargo, si su prioridad es la coherencia o si está trabajando con una base de código relativamente antigua, que carecía de formato pero necesita un formato coherente, entonces el negro sería lo mejor.

Para especificar un formateador en Visual Studio Code, primero se debe instalar el formateador y luego seleccionarlo como proveedor de formato en la configuración de la extensión Python. Consulte la siguiente lista para conocer los comandos de instalación:

autopep8— _ pip install pep8
Negro — pip install black
YAPF— _ pip install yapf
Cuando selecciona un formateador, la extensión de Python busca pythonPathel formateador en el actual. Si el formateador está instalado en otra ubicación, puede especificar la ubicación en la configuración de ruta personalizada para el formateador. Se pueden administrar configuraciones adicionales para el formateador tanto en el editor de configuración como en settings.jsonel archivo. Para utilizar el formateador, utilice los siguientes atajos de teclado:

Mac : Mayús +Opción+F
Windows : Mayús+Alt+F
Linux: Mayús+Ctrl+I
Editar la configuración de formato en el editor de configuración
En el editor de configuración, el formateador se selecciona de la lista desplegable para la configuración Python ➪ Formato: Proveedor. En la Figura 3.7 , se selecciona el formateador YAPF.


Figura 3.7 :En el editor de configuración, YAPF está seleccionado como proveedor de formato de Python.

Se pueden agregar argumentos personalizados haciendo clic en el botón Agregar elemento para el formateador respectivo. Se debe ingresar un valor de cadena para el argumento. En la Figura 3.8 , se proporcionan argumentos personalizados para el formateador YAPF.


Figura 3.8 :En el editor de Configuración, se agregan argumentos personalizados para estilo y espacios antes del comentario para el formateador YAPF.

Si el formateador no está instalado en el archivo actual pythonPath, especifique la ruta completa de la ubicación del formateador en la configuración de ruta personalizada para el formateador respectivo. En la Figura 3.9 , se proporciona una ruta personalizada para el formateador YAPF.


Figura 3.9 :En el editor de Configuración, se proporciona una ruta personalizada para el formateador YAPF.

Editar la configuración de formato en settings.json
En el settings.jsonarchivo, especifica un formateador agregando una entrada para python.formatting.provider. Los valores admitidos son autopep8, blacky yapf. Aquí hay una entrada de ejemplo para configurar YAPF como formateador:

"python.formatting.provider": "yapf"
También se pueden agregar argumentos personalizados como entrada. Consulte la siguiente lista para conocer la configuración de argumentos personalizados de cada formateador:

autopep8— _ python.formatting.autopep8Args
Negro — python.formatting.blackArgs
YAPF— _ python.formatting.yapfArgs
Para argumentos personalizados, cada elemento de nivel superior de una cadena de argumento que esté separado por un espacio en la línea de comando debe ser un elemento independiente en la argslista. Aquí se proporciona una entrada de ejemplo para YAPF:

"python.formatting.yapfArgs": ["--style", "{based_on_style: google, spaces_before_comment: 4}"]
Si el formateador no está instalado en el archivo actual pythonPath, agregue una entrada para especificar la ubicación del formateador respectivo utilizando la ruta completa. Consulte la siguiente lista para conocer la configuración de ruta personalizada de cada formateador:

autopep8— _ python.formatting.autopep8Path
Negro — python.formatting.blackPath
YAPF— _ python.formatting.yapfPath
Aquí hay una entrada de ejemplo para YAPF:

"python.formatting.yapfPath": "c:/yapfPath/yapf.exe"
pelusa
Como era de esperar, sería casi imposible escribir siempre código sin errores o detectar todos los errores posibles antes de ejecutar el código. Linting analiza cómo se ejecuta el código y detecta posibles errores a medida que escribe. Considere el siguiente bloque de código de una función fullnameque devuelve un valor concatenado de los argumentos pasados ​​a la llamada a la función:

def fullname(fname, lname):
    return fname + " " + lname
 
print(name("April", "Speight"))
La llamada a función dentro de la printdeclaración utiliza la llamada a función incorrecta name. Un linter detectaría este problema como una variable indefinida ″name″. Podría considerar que tanto el linting como el formateo tienen una función similar. Sin embargo, el formateo sólo reestructura la apariencia del código.

Hay una variedad de linters disponibles que se pueden habilitar para su uso. Sin embargo, no es necesario habilitar linting si elige codificar sin linter. Si linting está habilitado, linter se ejecuta automáticamente cada vez que guarda un archivo. También puede invocar un linter manualmente en cualquier momento usando el comando Python: Ejecutar Linting desde la paleta de comandos.

Activar y desactivar Linting
La extensión Python para Visual Studio Code admite los siguientes linters:

Pylint (predeterminado): busca errores e intenta aplicar un estándar de codificación
Flake8: compara el código con las convenciones de estilo en PEP 8, los errores de programación y la complejidad ciclomática.
mypy: comprueba si hay tipos estáticos aplicados opcionalmente
pydocstyle: comprueba el cumplimiento de las convenciones de cadenas de documentación de Python
pycodestyle (pep8): compara el código Python con algunas de las convenciones de estilo en PEP 8
prospector: analiza el código Python y genera información sobre errores, problemas potenciales, violaciones de convenciones y complejidad.
pylama : un contenedor para múltiples herramientas de Python (pycodestyle, pydocstyle, PyFlakes, Mccabe, Pylint, Radon, gjslint, eradicate, mypy)
Bandit : encuentra problemas de seguridad comunes en el código Python
Pylint es el linter predeterminado y, por lo tanto, se habilita al crear un nuevo programa Python. Sin embargo, si Visual Studio Code no detecta un linter habilitado, muestra un mensaje para instalar Pylint.

Puede optar por habilitar un linter diferente usando el comando Python de la paleta de comandos: seleccione Linter. Seleccione un linter de la lista para instalar su paquete y habilitar el linter para el entorno.

Si no es necesario utilizar linting, puede desactivar todos los linting de Python utilizando el comando Python de la paleta de comandos: habilitar Linting. Seleccione Desactivado para desactivar las pelusas.

Ejecutar pelusa
Cuando se ejecuta linter, los resultados aparecen en el panel Problemas y los problemas específicos se subrayan en el editor de código. Para ver detalles en el editor, coloque el cursor sobre un tema subrayado.

Pruébelo: cree un error de sintaxis en el circle_area.pyarchivo para que el linter detecte el error y lo muestre en el panel Problemas.

Agregue un punto después input, antes del paréntesis y guarde el archivo.
import math as m
 
radius = float(input.('Radius: '))
area = m.pi * (m.pow(radius, 2))
print(area)
Haga clic en el panel Problemas para ver el error de sintaxis detectado por el linter (consulte la Figura 3.10 ). La línea 3 detecta un error de sintaxis desconocido.

Figura 3.10 :En el panel Problemas, se detecta un error de sintaxis.

También puede pasar el cursor del mouse sobre la mathvariable en el editor para ver el error (consulte la Figura 3.11 ). Si hubiera una solución rápida disponible, la solución sugerida se mostraría en el problema.


Figura 3.11 :Al pasar el cursor del mouse sobre el error garabateado rojo en el editor, se muestra el error detectado por el linter. El error indica "sintaxis no válida (<desconocida>, línea 3) pylint(error de sintaxis)".

Elimine el punto antes de pasar al siguiente ejercicio.

Configuración de pelusa
La configuración de Linting se puede modificar tanto globalmente como por linter. Puede aplicar todos los cambios de configuración dentro del settings.jsonarchivo. A continuación se proporcionan configuraciones globales que se pueden modificar para cambiar el comportamiento de linting en todos los linters habilitados.

Configuración global de pelusa

CARACTERÍSTICA	AJUSTE ( PYTHON.LINTING.)	VALOR POR DEFECTO
Pelusa en general	enabled	true
Linting al guardar el archivo	lintOnSave	true
Número máximo de mensajes linting	maxNumberOfProblems	100
Excluir patrones de archivos y carpetas	ignorePatterns	[".vscode/*.py", "**/site-packages/**/*.py"]
NOTA Si lintOnSaveestá habilitado, es posible que también desee habilitar la files.autoSaveopción genérica. Auto Saveguarda sus cambios después de un retraso configurado o cuando el foco abandona el editor. Si Auto Saveestá habilitado, no es necesario guardar manualmente un archivo. La combinación de lintOnSavey files.autoSaveproporciona comentarios frecuentes sobre linting en su código a medida que escribe.

Para obtener más información sobre configuraciones específicas de linter, visite code.visualstudio.com/docs/python/linting#_specific-linters.

Refactorización
El propósito de la refactorización es mantener la funcionalidad mientras se mejora la estructura interna o la arquitectura de un programa. La refactorización debería ser una tarea rutinaria que se produzca antes de que se agreguen actualizaciones o nuevas funciones a un programa. Los beneficios de la refactorización incluyen estabilidad y rendimiento mejorados, complejidad reducida y menos tiempo para probar y encontrar errores.

Aunque podría refactorizar manualmente su código, dicha tarea resultaría agotadora para un programa largo. Afortunadamente, Visual Studio Code proporciona tres comandos para ayudar a realizar cambios rápidamente.

Extraer variable
Método de extracción
Ordenar importaciones
Cada comando se puede invocar desde la paleta de comandos o desde un menú contextual que aparece al hacer clic derecho en una selección.

La refactorización requiere la Ropebiblioteca, que se instala con pip install ropeo conda install -c anaconda rope.

Extraer variable
Si descubre que está utilizando el mismo valor constante o expresión en varios lugares de su código, como la misma cadena o número, considere extraer todas las apariciones similares y reemplazarlas con una variable. El comando Extraer variable (Python Refactor: Extraer variable) proporciona dicha funcionalidad. Cuando se invoca, la nueva variable recibe el nombre newvariableNNN, donde NNNes un número aleatorio.

Pruébelo: refactorice la línea de código circle_area.pyque refleja el cálculo de r 2 con una variable.

En el editor, resalte m.pow(radius, 2).
Haga clic derecho y seleccione Extraer variable en el menú contextual. Se crea una nueva variable en el editor (ver Figura 3.12 ).

Figura 3.12 :Se crea una nueva variable param.pow(radius, 2). El editor le solicita que ingrese un nombre para la variable.

Nombra la nueva variable radiusSqry presiona Enter. Observe que el cálculo de r 2 ahora se reemplaza con la radiusSqrvariable. Su código debería mostrarse como tal:
import math as m
 
radius = float(input('Radius: '))
radiusSqr = m.pow(radius, 2)
area = m.pi * (radiusSqr)
print(area)
Ejecute el código para ver que el programa mantiene la misma lógica.
Método de extracción
El comando Extraer método (Python Refactor: Extraer método) extrae todas las apariciones similares de la expresión o bloque seleccionado, crea un método y reemplaza la expresión con una llamada al método. El nuevo método recibe el nombre newmethodNNNde donde NNNhay un número aleatorio.

Pruébelo: todo el código después de la importdeclaración circle_area.pypodría refactorizarse en un método. Refactorice el código en un método.

En el editor, resalte todo el código después de la importdeclaración y antes de la printdeclaración.
Haga clic derecho y seleccione Extraer método en el menú contextual. Se crea un nuevo método en el editor. Ver Figura 3.13 .

Figura 3.13 :Se crea un nuevo método para el código después de laimportdeclaración. El editor le solicita que ingrese un nombre para el método.

Asigne un nombre al nuevo método circleAreay presione Entrar. Observe que todo el código ahora se coloca dentro del cuerpo del circleArea()método y returnse agrega una declaración para devolver area. Además, la llamada a la función se asigna a la variable area.
Su código debería mostrarse como tal:

import math as m
 
def circleArea():
    radius = float(input('Radius: '))
    radiusSqr = m.pow(radius, 2)
    area = m.pi * (radiusSqr)
    return area
 
area = circleArea()
print(area)
Ejecute el código para ver que el programa mantiene la misma lógica.
Ordenar importaciones
El comando Ordenar importaciones (Python Refactor: Sort Imports) utiliza el isortpaquete para consolidar importaciones específicas del mismo módulo en una única declaración de importación y organiza importlas declaraciones en orden alfabético. No es necesaria ninguna selección de código para invocar el comando. Esta característica es útil para limpiar y simplificar sus declaraciones de importación.

Pruébelo: utilice Ordenar importaciones para consolidar y ordenar todas importlas declaraciones en orden alfabético.

Cree un nuevo archivo imports_example.pyy agregue las siguientes importdeclaraciones:
from my_lib import Object
import os
from third_party import lib1, lib2
from my_lib import Object3
from my_lib import Object2
import sys
from third_party import lib3
Haga clic derecho en el editor y seleccione Ordenar importaciones en el menú contextual. Observe que todas las importaciones my_liby third_partyse han consolidado. Además, todas importlas declaraciones están ordenadas alfabéticamente.
Su código debería mostrarse como tal:

import os
import sys
 
from my_lib import Object, Object2, Object3
from third_party import lib1, lib2, lib3
Fragmentos
Si se encuentra repitiendo un patrón de código dentro de un archivo o en varios archivos, considere poner el patrón en un fragmento. Los fragmentos son plantillas de código que se pueden agregar al editor a medida que escribe, lo que reduce la cantidad de pulsaciones de teclas necesarias para crear un programa. Visual Studio Code tiene varios fragmentos integrados. Sin embargo, las extensiones de lenguaje como la extensión Python para Visual Studio Code amplían aún más la lista de fragmentos disponibles al proporcionar un conjunto estándar de fragmentos específicos del lenguaje.

Los fragmentos se invocan con el método abreviado de teclado Ctrl+barra espaciadora o el comando Insertar fragmento. Cuando se invoca, Visual Studio Code muestra una lista de fragmentos disponibles. Al seleccionar un fragmento de la lista, se agrega la plantilla de código a cualquier línea en la que se encuentre el cursor en el editor.

Pruébelo: ejecute el comando Insertar fragmento para ver una lista de fragmentos disponibles proporcionados por la extensión de Python. A medida que avanza por la lista, lea la descripción proporcionada para el fragmento (consulte la Figura 3.14 ).


Figura 3.14 :Se muestra una lista de fragmentos disponibles junto con su descripción en la paleta de comandos.

En la mayoría de los casos, cuando se agrega un fragmento a un archivo, el texto del marcador de posición se resalta (consulte la Figura 3.15 ). Para navegar por el texto del marcador de posición, presione Tab y reemplace el texto según sea necesario.

Aunque la extensión de Python proporciona una variedad de fragmentos de código de uso general, probablemente querrás crear los tuyos propios para tus patrones de código más comunes.

Los fragmentos se crean en JSON dentro de un archivo de fragmentos. El archivo de fragmento admite comentarios de estilo C y puede definir una cantidad ilimitada de fragmentos. Para crear un fragmento, navegue hasta Código o seleccione Archivo ➪ Preferencias ➪ Fragmentos de usuario. Cuando se le solicite, seleccione Python para el idioma. El python.jsonarchivo de fragmento que se abre contiene instrucciones sobre cómo crear un fragmento. Asegúrese de crear el fragmento dentro de las llaves y guarde el archivo una vez hecho.

{
    // Place your snippets for python here. Each snippet is defined under a snippet name and has a prefix, body and 
    // description. The prefix is what is used to trigger the snippet and the body will be expanded and inserted. Possible variables are:
    // $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. Placeholders with the 
    // same ids are connected.
    // Example:
    // "Print to console": {
    //  "prefix": "log",
    //  "body": [
    //      "console.log('$1');",
    //      "$2"
    //  ],
    //  "description": "Log output to console"
    // }
}

Figura 3.15 :Eltry///incluye texto de marcador deexceptposiciónelsepara,y.finallypassexpressionidentifier

Para obtener información adicional sobre cómo crear un fragmento, revise code.visualstudio.com/docs/editor/userdefinedsnippets#_create-your-own-snippets.

Resumen
En este capítulo, aprendió sobre lo siguiente:

Las soluciones rápidas ayudan a solucionar problemas identificados por errores de código si hay una solución potencial disponible.
La solución rápida de add imports completa las declaraciones de importación y reconoce abreviaturas comunes para NumPy, TensorFlow, pandas, matplotlib.pylot, matplotlib, SciPi y SciPy.
La finalización del código, la definición de objetos y la ubicación de las declaraciones de objetos o variables se activan presionando Ctrl+barra espaciadora o escribiendo un carácter activador (como un punto en Python).
La extensión Python admite los siguientes formateadores: autopep8 (predeterminado), Black y YAPF.
La configuración de formato se puede personalizar en settings.json.
Si linting está habilitado, linter se ejecuta automáticamente cada vez que se guarda un archivo.
La extensión de Python admite los siguientes linters: Pylint (predeterminado), Flake8, Mypy, pydocstyle, pycodestyle, prospector, pylama y Bandit.
La configuración de Linting se puede modificar tanto globalmente como por linter dentro de settings.json.
Puede refactorizar código con tres comandos: Extraer variable, Extraer método y Ordenar importaciones.
Los fragmentos proporcionan una plantilla de código que se agrega al editor cuando se invoca con Ctrl+barra espaciadora o el comando Insertar fragmento.
