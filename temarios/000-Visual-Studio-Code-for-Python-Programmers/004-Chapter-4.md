# CHAPTER 4: Managing Projects and Collaboration - Gestión de proyectos y colaboración
* Files and Folders
* Environments
* Source Control
* Live Share
* Summary

Administrar el código fuente dentro del contexto de un proyecto requiere poder navegar y mantener archivos, trabajar dentro del entorno Python apropiado y mantener los cambios con control de código fuente. Cada una de estas tareas está disponible en Visual Studio Code como funcionalidad estándar o con la instalación de una extensión. En este capítulo, se exploran las funciones principales para gestionar proyectos en una aplicación de chatbot creada con la biblioteca ChatBotAI. (Para obtener más información sobre la biblioteca ChatBotAI, visite pypi.org/project/chatbotAI). La aplicación utiliza la biblioteca de Wikipedia para buscar información en artículos de Wikipedia. (Para obtener más información sobre la biblioteca de Wikipedia, visite pypi.org/project/wikipedia/.) Los ejercicios de este capítulo se completan dentro de la Wikipeida_Chatbotcarpeta.

Archivos y carpetas
En Visual Studio Code, trabajar con archivos y carpetas va más allá del simple acceso a un archivo. Puede abrir un proyecto completo en el editor y administrar varios archivos en subcarpetas simultáneamente. Una vez que se abre un proyecto en el editor, Visual Studio Code proporciona funciones útiles para navegar y buscar entre carpetas. La vista del Explorador muestra el contenido de un proyecto abierto, lo que proporciona un fácil acceso para administrar y abrir archivos en el editor.

Abrir un proyecto
Para administrar un proyecto en Visual Studio Code, primero abra su carpeta en el editor usando uno de estos métodos:

Terminal externo : navegue hasta la ubicación de la carpeta e ingrese code .para abrir en Visual Studio Code.
Menú : seleccione Archivo ➪ Abrir carpeta o Archivo ➪ Abrir reciente.
Atajo de teclado : Presione Cmd+K, O/Ctrl+K, O.
Página de bienvenida : seleccione Abrir carpeta o un elemento en Reciente. Ver Figura 4.1 .

Figura 4.1 :El enlace Abrir carpeta se muestra en la página de bienvenida de Visual Studio Code.

Vista del explorador : si no hay ninguna carpeta abierta, haga clic en Abrir carpeta (consulte la Figura 4.2 ).

Figura 4.2 :El botón Abrir carpeta está disponible en la vista del Explorador cuando no hay ninguna carpeta abierta.

Pruébelo: utilice su método preferido para abrir la carpeta Wikipedia_Chatbot.

Cuando se abre una carpeta, la vista del Explorador muestra el contenido de la carpeta. Los archivos se pueden abrir con un solo clic o con un doble clic; sin embargo, el resultado difiere para cada acción. Un solo clic abre un archivo en una pestaña dentro del editor. Si hace clic en otro archivo, la pestaña del archivo inicial se reemplaza con el archivo siguiente. Si se realizan ediciones en un archivo en una pestaña del editor, al hacer clic una vez en un archivo en la vista del Explorador se abre el archivo en una nueva pestaña.

Un doble clic abre el archivo en una pestaña del editor. Un simple clic posterior en otro archivo en el editor abre el archivo en una nueva pestaña en el editor. El beneficio decon un doble clic podrá abrir varios archivos dentro de un proyecto en nuevas pestañas del editor sin la necesidad de editar ningún archivo dentro del editor.

Pruébelo: en la vista del Explorador, abra el README.mdarchivo. A continuación, navegue hasta la examplescarpeta y abra el Example.pyarchivo para mostrarlo en el editor (consulte la Figura 4.3 ).


Figura 4.3 :LosREADME.mdyExample.pyse abren en el editor.

NOTA Para abrir varios archivos en el editor a la vez, seleccione cada archivo y use el método abreviado de teclado Ctrl+Enter.

NOTA Puede alternar entre la vista del editor y del Explorador con el método abreviado de teclado Cmd/Ctrl+Shift+E.

Si hay archivos o carpetas que desea que Visual Studio Code oculte en el Explorador y en la función de búsqueda, puede definir el patrón con la configuración Archivo: Excluir (consulte la Figura 4.4 ).


Figura 4.4 :La configuración Archivos: Excluir está disponible en Configuración. Haga clic en Agregar patrón para incluir una nueva entrada para la configuración.

Navegar por archivos
El historial de navegación se guarda cada vez que navega entre archivos en el editor. Si hay varios archivos abiertos en el editor, puede ver todos los archivos en un grupo de editor con el método abreviado de teclado Ctrl+Tab. Se muestra una lista de archivos abiertos en la parte superior del editor. Puede cambiar el archivo activo manteniendo presionada la tecla Ctrl mientras presiona Tab para seleccionar el archivo y luego suelta Ctrl para aplicar la selección. El método abreviado de teclado Ctrl+Shift+Tab navega por la lista en orden inverso cuando hay muchos archivos abiertos.

Pruébelo: presione Ctrl+Tab para cambiar el archivo activo (consulte la Figura 4.5 ).


Figura 4.5 :Cada archivo abierto aparece en la lista de archivos disponibles para cambiar.

También puede navegar por los archivos de una carpeta utilizando Breadcrumbs. La pantalla Breadcrumbs se puede encontrar en la parte superior del editor y muestra la ruta del archivo. Al seleccionar una ruta de navegación en la ruta se muestra un menú desplegable con los hermanos del nivel. Luego puede seleccionar un hermano para navegar a otras carpetas y archivos (consulte la Figura 4.6 ).


Figura 4.6 :Las rutas de navegación muestran la ruta alExample.pyarchivo.

El comando Paleta de comandos Focus Breadcrumbs se utiliza para interactuar con las rutas de navegación. Cuando se utiliza, se selecciona el último elemento de la ruta de navegación y se abre un menú desplegable que le permite navegar a un archivo o carpeta hermano. Utilice las teclas de flecha arriba y abajo para seleccionar un elemento hermano. Para navegar a los elementos secundarios de un hermano, use las teclas de flecha izquierda y derecha (consulte la Figura 4.7 ).

NOTA Puede desactivar las rutas de navegación con el botón Mostrar rutas de navegación (Ver ➪ Mostrar rutas de navegación) o con la breadcrumbs.enabledconfiguración.


Figura 4.7 :Se muestra el elemento secundario de la carpeta de ejemplos.

Buscar entre archivos
La búsqueda en archivos en una carpeta abierta se puede realizar rápidamente con la vista de búsqueda (Cmd+Shift+F/Ctrl+Shift+F). Los resultados de la búsqueda se muestran debajo de la barra de búsqueda a medida que escribe el término de búsqueda. Los resultados de la búsqueda se agrupan en archivos que contienen el término de búsqueda. Los resultados del término de búsqueda (ver Figura 4.8 ) incluyen el número total de apariciones del término en cada archivo y las ubicaciones respectivas. Puede expandir un archivo para ver una vista previa de todas las apariciones dentro del archivo y hacer clic una vez en una aparición para verla en el editor.


Figura 4.8 :Los resultados de la búsqueda muestran que hay 22 resultados en 4 archivos con el términowikipedia.

NOTA Los resultados de la búsqueda dependen de la configuración de Búsqueda: Excluir.

Pruébelo: busque el término wikipedia en todos los archivos de la carpeta Wikipedia_Chatbot. Una vez encontrado, haga clic en una ocurrencia en el Example.pyarchivo para verla en el editor.

En la vista de búsqueda, ingrese el término de búsqueda wikipedia . Los resultados muestran que hay 22 resultados en 4 archivos con el término wikipedia (ver Figura 4.9 ).

Figura 4.9 :Busquewikipediaen la barra de búsqueda.

NOTA El icono Alternar contraer y expandir (consulte la Figura 4.9 ) contrae y expande todos los resultados de la búsqueda. Para descartar archivos en los resultados de búsqueda, haga clic en la X junto al nombre del archivo.

Seleccione la primera aparición en el Example.pyarchivo para ver el archivo y la ubicación del término en el editor (consulte la Figura 4.10 ).

Figura 4.10 :Al seleccionar la primera aparición dewikipediaen elExample.pyarchivo, se abre el archivo en el editor y se resalta el término en el archivo.

Puede filtrar su búsqueda seleccionando si desea que los resultados coincidan con mayúsculas y minúsculas (Opción+Cmd+C/Alt+C) o con la palabra completa (Opción+Cmd+W/Alt+W). Además de los atajos de teclado, se puede acceder a cada filtro utilizando los íconos en la barra de búsqueda (ver Figura 4.11 ).


Figura 4.11 :En la vista de búsqueda, los iconos Coincidir mayúsculas y minúsculas (A), Coincidir palabra completa (B) y Usar expresión regular (C) aparecen junto a la barra de búsqueda.

La función de búsqueda también admite la búsqueda de expresiones regulares. Para alternar la búsqueda de expresiones regulares, haga clic en el icono Usar expresión regular en la barra de búsqueda (consulte la Figura 4.11 , C) o use el método abreviado de teclado Opción+Cmd+R/Alt+R.

Los resultados de la búsqueda también podrían sustituirse por otro término. Haga clic en la flecha al lado del campo de búsqueda, que abre el campo Reemplazar (consulte la Figura 4.12 , A). Esta característica le permite conservar el caso (ver Figura 4.12 , B) y reemplazar todas (ver Figura 4.12 , C) instancias del término en el proyecto.


Figura 4.12 :El campo Reemplazar (A) se muestra cuando se selecciona la flecha al lado del campo Buscar. Los iconos a la derecha del campo Reemplazar le permiten seleccionar Conservar caso (B) o Reemplazar todo (C).

Para especificar qué archivos incluir o excluir de los resultados de búsqueda, haga clic en el icono Alternar detalles de búsqueda (consulte la Figura 4.13 ) debajo del campo de búsqueda. Ingrese el nombre de los archivos en el campo correspondiente.


Figura 4.13 :El icono Alternar detalles de búsqueda abre los campos Archivos para incluir y Archivos para excluir.

Los resultados de la búsqueda también se pueden mostrar en el editor haciendo clic en Abrir en el editor (consulte la Figura 4.14 ). Cuando se selecciona, los resultados de la búsqueda se muestran en una nueva pestaña, que enumera cada instancia del término de búsqueda y la ubicación respectiva por línea en un formato desplazable.

También existe la posibilidad de buscar un término directamente desde el editor. El método abreviado de teclado Cmd+F/Ctrl+F abre una barra de búsqueda dentro de la pestaña activa (ver Figura 4.15 ). Ingrese el término de búsqueda en la pestaña para buscar el archivo. La barra de búsqueda del editor incluye algunos comandos similares de la vista de búsqueda. Además, hay una selección Buscar en como lo indica el ícono de triple línea.


Figura 4.14 :Cuando los resultados de la búsqueda se abren en el editor, cada instancia del término aparece junto a la línea respectiva en el archivo.


Figura 4.15 :El método abreviado de teclado Cmd+F/Ctrl+F abre una barra de búsqueda dentro de la pestaña activa. Aunque la mayoría de las funciones de la vista de búsqueda están disponibles para esta función, hay una función adicional para buscar un término en una selección.

Cerrar un archivo o carpeta
Visual Studio Code se actualiza cuando se cierra una carpeta. Puedes cerrar un archivo o carpeta en el editor de varias maneras.

Menú : seleccione Archivo ➪ Cerrar ventana o Cerrar carpeta.
Editor (cerrar archivo) : haga clic en la X en la pestaña Archivo.
Método abreviado de teclado (cerrar ventana) : presione Cmd+W/Ctrl+W.
Método abreviado de teclado (cerrar carpeta) : presione Cmd+K, F/Ctrl+K, F.
Ambientes
La extensión Python para Visual Studio Code proporciona funciones de integración para trabajar con entornos globales, virtuales y conda. Aunque un entorno global proporciona la forma más rápida de empezar a escribir un lenguaje Pythonprograma, se recomienda administrar proyectos en sus propios entornos virtuales o conda aislados para evitar conflictos de versiones de biblioteca entre diferentes proyectos. El uso de entornos aislados también le ayuda a comprender claramente qué bibliotecas se utilizan con cada proyecto específico.

Para seleccionar un entorno, ejecute Python: seleccione el comando Intérprete en la paleta de comandos. La paleta de comandos proporciona una lista de intérpretes de Python. En la lista de intérpretes, los entornos virtual y conda se indican mediante env o conda entre paréntesis. Los entornos globales se presentan sin paréntesis. Ver Figura 4.16 .


Figura 4.16 :Se muestra una lista de entornos disponibles en la lista de entornos. Hay dos entornos globales y un entorno virtual.

Entornos virtuales
Visual Studio Code detecta automáticamente cuando crea un nuevo entorno virtual y le solicita que seleccione si el nuevo entorno virtual debe seleccionarse para el espacio de trabajo (consulte la Figura 4.17 ). Si se selecciona, Visual Studio Code guarda la ruta al intérprete de Python en el entorno virtual en la configuración del espacio de trabajo.


Figura 4.17 :Después de crear un entorno virtual, Visual Studio Code proporciona una notificación solicitando si se selecciona el entorno para la carpeta del espacio de trabajo. Al hacer clic en Sí se activa el entorno virtual y se selecciona el entorno virtual como intérprete.

Entornos Conda
Antes de poder crear un entorno conda, se debe configurar conda como el shell de terminal integrado predeterminado para usar comandos conda en Visual Studio Code. El shell se puede configurar en la configuración del usuario.

Ejecute el comando Preferencias: Abra Configuración de usuario.
En la navegación izquierda, seleccione Funciones ➪ Terminal. Desplácese hacia abajo hasta la configuración de Integrado ➪ Shell.
Seleccione el enlace Editar en settings.json correspondiente a su sistema operativo (consulte la Figura 4.18 ).

Figura 4.18 :Editar en settings.json está seleccionado para el sistema operativo Windows.

En el settings.jsonarchivo, establezca terminal.integrated.shell.<platform>, además de terminal.integrated.shellArgs.<platform>. Por ejemplo, para Windows, la entrada sería la siguiente:
"terminal.integrated.shell.windows": "C:\\Windows\\System32\\cmd.exe",
"terminal.integrated.shellArgs.windows": ["/K", "C:\\<path to conda installation>\\Scripts\\activate.bat C:\\<path to conda installation>"],
Al seleccionar un intérprete, Visual Studio Code detecta automáticamente entornos conda existentes que contienen un intérprete de Python. Si crea un entorno conda mientras se ejecuta Visual Studio Code, primero debe recargar la ventana para actualizar la lista de entornos que está disponible al seleccionar un intérprete de Python. Para actualizar la ventana, ejecute el comando Desarrollador: Recargar ventana.

Es posible que el entorno conda tarde un momento en aparecer en la lista. Si el entorno conda no aparece al principio, intente el comando nuevamente en 15 segundos.

Pruébelo: cree un entorno virtual o conda para el proyecto Wikipedia_Chatbot. Una vez activado el entorno aislado, instale ChatBotAI y Wikipedia.

Entorno virtual :pip install chatbotAI, pip install wikipedia
entorno de conda :conda install -c anaconda chatbotAI, conda install -c anaconda wikiedpia
Ejecute Examples.pypara probar la aplicación; ver Figura 4.19 . Cuando se inicia la aplicación, el chatbot saluda y continúa haciendo una serie de preguntas relacionadas con tu respuesta. Para realizar una consulta en Wikipedia, pregunte al chatbot Quién/Qué es <consulta> (por ejemplo, Qué es Visual Studio Code). Suponiendo que hay una página de Wikipedia para el tema, el chatbot devuelve el párrafo introductorio del tema. Si no hay ningún artículo relevante de Wikipedia, el chatbot regresa con la cadena No conozco <query> .

Para detener el programa, ingrese quit.


Figura 4.19 :Se realiza una consulta al chatbot sobre Visual Studio Code. La respuesta proporcionada por el chatbot es el párrafo introductorio de la página de Wikipedia de Visual Studio Code.

Fuente de control
Visual Studio Code está equipado con control de fuente integrado que le permite rastrear y administrar cambios en el código. El control de código fuente también proporciona una forma de colaborar con otros en un proyecto conectándose a un repositorio remoto, como un repositorio en GitHub. Aunque el editor viene con el administrador de control de fuente (SCM) de Git integrado, puede instalar un SCM adicional desde Extension Marketplace. Se debe instalar la versión 2.0.0 o posterior de Git para utilizar las funciones de Git. Para instalar o actualizar Git, visite git-scm.com/download.

NOTA En Extension Marketplace, puede filtrar por proveedores de SCM buscando @categoría:"proveedores de SCM" .

La vista Control de código fuente proporciona información de control de versiones para su proyecto, como cambios, cambios por etapas y cambios de combinación. El icono de Control de código fuente siempre indica una descripción general de cuántos archivos se han modificado en su repositorio (consulte la Figura 4.20 ).


Figura 4.20 :El icono de control de código fuente en la barra de actividades indica que hay un cambio pendiente.

Si no tiene una carpeta abierta, la vista Control de código fuente le indica que abra una carpeta que contenga un repositorio Git o que clone un repositorio. Ver Figura 4.21 .


Figura 4.21 :En la vista Control de código fuente, puede inicializar un repositorio Git haciendo clic en el botón Inicializar repositorio.

La barra de estado contiene una barra de estado de Git que muestra la rama retirada (consulte la Figura 4.22 , A) y una acción Sincronizar cambios o Publicar (consulte la Figura 4.22 , B). Se explica información adicional sobre cada acción en la sección posterior titulada "Remotos".


Figura 4.22 :La barra de estado de Git indica la rama retirada (A) y muestra un icono para publicar en GitHub (B).

Visual Studio Code detecta los cambios realizados dentro de la interfaz de usuario de Visual Studio Code además de los cambios realizados a través de la interfaz de línea de comandos (CLI). Por lo tanto, puede ejecutar comandos CLI en otro shell o en el terminal integrado de Visual Studio Code, dado que Visual Studio Code se sincroniza con el estado actual. Si ingresa comandos dentro de la interfaz de usuario de Visual Studio Code, puede abrir la ventana de salida de Git para ver los comandos. Para acceder a la ventana de salida de Git, navegue hasta Ver ➪ Salida (Ctrl+Cmd+U/Ctrl+Shift+U) y seleccione Git en el menú desplegable de la ventana Salida (consulte la Figura 4.23 ).


Figura 4.23 :La ventana Salida muestra la salida de Git para el repositorio.

Inicializar un repositorio
La vista Código fuente muestra el mensaje "No hay proveedores de control de código fuente registrados" si Visual Studio Code no detecta un repositorio Git existente. Para inicializar un repositorio, haga clic en el comando Inicializar repositorio que aparece en la vista. Alternativamente, ejecute el comando Git: Inicializar repositorio desde la paleta de comandos.

Cuando inicializa un repositorio, Visual Studio Code crea los archivos de metadatos del repositorio Git necesarios y muestra sus archivos como archivos que aún no se han confirmado por primera vez. Estos archivos se denominan cambios sin seguimiento (indicados por un icono U) listos para ser preparados.

Pruébelo: inicialice un repositorio para chatbot.

Ejecute el comando Git: Inicializar repositorio y seleccione la carpeta Wikipedia_Chatbot. Observe que los archivos dentro de Wikipedia_Chatbot ahora tienen un ícono U (indicativo de cambios sin seguimiento) al lado del nombre del archivo. La vista Control de código fuente también muestra el número total de cambios pendientes (consulte la Figura 4.24 ).

Figura 4.24 :El icono de la vista Control de código fuente indica que hay 982 cambios pendientes. Además, aparece un icono sin seguimiento junto a cada archivo en la vista del Explorador.

El icono Vistas y más acciones (consulte la Figura 4.25 ) dentro de la vista Control de código fuente proporciona una lista de opciones para cambiar cómo se ven y ordenan los archivos dentro de la sección Cambios. La opción de menú Ver y ordenar proporciona la opción de ver los cambios como una lista o un árbol. La configuración predeterminada es ver como una lista. Si la sección Cambios está configurada para verse como una lista, puede ordenar la lista por nombre, ruta o estado.


Figura 4.25 :Al hacer clic en el icono Vistas y más acciones, se ofrecen opciones para cambiar la forma en que se ordena la lista de cambios.

Pruébelo: cambie la vista de los cambios para verlos como un árbol (consulte la Figura 4.26 ).


Figura 4.26 :Al cambiar la vista a un árbol se muestran los archivos del proyecto dentro de sus respectivas carpetas.

Cometer cambios
Puede confirmar cómodamente cambios para su proyecto desde la vista Control de código fuente. La sección Cambios dentro de la vista muestra todos los cambios realizados dentro del proyecto. Al lado de cada archivo está el estado de Git indicado por una letra.

U: sin seguimiento
M —Modificado
A —Agregado
NOTA El estado de Git también se muestra en la vista del Explorador junto al archivo modificado.

Puede descartar todos los cambios (consulte la Figura 4.27 ) o organizar todos los cambios usando los íconos en el encabezado Cambios. Para ver los íconos, pase el cursor sobre el encabezado.


Figura 4.27 :El primer icono (A), Descartar todos los cambios, se utiliza para descartar todos los cambios preparados. El segundo icono (B), Preparar todos los cambios (B), se utiliza para preparar todos los cambios pendientes para el repositorio.

Si pasa el cursor sobre un archivo dentro de la sección Cambios, tendrá la opción de abrir el archivo (A), descartar los cambios (B) o preparar los cambios (C). Ver Figura 4.28 .


Figura 4.28 :Los íconos que aparecen al lado del archivo le permiten administrar los cambios para el archivo singular. El primer icono (A), Abrir archivo, abre el archivo en la ventana del editor. El segundo icono (B), Descartar cambios, se utiliza para descartar el cambio. El tercer icono (C), Organizar cambios, se utiliza para preparar el cambio pendiente.

Una vez que se prepara un cambio, el archivo se mueve a la sección Cambios preparados. Si pasa el cursor sobre un archivo dentro de la sección Cambios preparados, tendrá la opción de abrir el archivo (A) o cancelar los cambios (B). Ver Figura 4.29 .


Figura 4.29 :El primer icono (A), Abrir archivo, abre el archivo en la ventana del editor. El segundo icono (B), Desactivar cambios, desactiva el cambio.

Los mensajes de confirmación se ingresan en la barra de mensajes (consulte la Figura 4.30 ). Para confirmar los cambios, presione Cmd+Entrar/Ctrl+Entrar o seleccione el icono Confirmar.


Figura 4.30 :Los mensajes de confirmación se ingresan en la barra de mensajes.

Antes de enviar archivos de proyecto al repositorio, es probable que desee ignorar algunos archivos, como la carpeta del entorno virtual o cualquier archivo que contenga variables de entorno. Visual Studio Code proporciona dos formas rápidaspara agregar archivos a un .gitignorearchivo. Una vez creado el .gitignorearchivo, puede agregar archivos directamente desde la vista Control de código fuente o la Paleta de comandos. Cuando se agrega un archivo .gitignore, Visual Studio Code abre el .gitignorearchivo en una nueva pestaña.

Antes de agregar un archivo a .gitignore, el archivo debe estar sin preparar. Para agregar un archivo .gitignoredesde la vista Control de código fuente, haga clic derecho en el archivo y seleccione Agregar a .gitignore (consulte la Figura 4.31 ).


Figura 4.31 :En la vista Control de código fuente, seleccione la.gitignoreopción de menú Agregar a para agregar los.envarchivos.gitignore.

Alternativamente, puede agregar un archivo desde la paleta de comandos con el comando Git: Agregar a .gitignore. Antes de ejecutar el comando, asegúrese de que el archivo esté activo en el editor.

Pruébelo: prepare y envíe los archivos del proyecto Wikipedia_Chatbot a la rama maestra.

En la vista Control de código fuente, seleccione las carpetas/archivos apropiados para agregar .gitignore(por ejemplo, la carpeta del entorno virtual).
Haga clic en el icono + para organizar todos los archivos dentro de Cambios (consulte la Figura 4.32 ).

Figura 4.32 :Se selecciona el icono + para organizar todos los cambios.

Ingrese un mensaje de confirmación en la barra de mensajes (por ejemplo, "agregar archivos de proyecto al repositorio"; consulte la Figura 4.33 ).

Figura 4.33 :El mensaje de confirmación "agregar archivos de proyecto al repositorio" se ingresa en la barra de mensajes.

Confirme los cambios (consulte la Figura 4.34 ).

Figura 4.34 :El icono Confirmar cambios se utiliza para confirmar los cambios por etapas.

Sucursales
Al colaborar con otros, los cambios de código, como nuevas funciones o correcciones de errores, a menudo se crean en una rama. Las bifurcaciones permiten a los colaboradores bifurcarse desde el código base y completar su trabajo en un entorno aislado e independiente de los demás. Con Git, los cambios realizados en una rama se pueden fusionar con el código base o la rama maestra. En Visual Studio Code, hay dos formas de crear una nueva rama:

Paleta de comandos : ejecute el comando Git: Crear rama. Cuando se le solicite, ingrese un nombre para la sucursal.
Barra de estado : haga clic en el indicador de sucursal y seleccione + Crear nueva sucursal (consulte la Figura 4.35 ).

Figura 4.35 :En la ventana que aparece, haga clic en+Crear nueva rama para crear una nueva rama para el repositorio.

Cuando crea una nueva rama, la rama se desprotege automáticamente. Al extraer una rama se actualizan los archivos en el directorio de trabajo para que coincidan con la versión almacenada en esa rama. Cuando se retira una rama, Git registra todas las confirmaciones nuevas en la rama. Hay dos formas de retirar manualmente una sucursal:

Paleta de comandos : ejecute el comando Git: Checkout To. Cuando se le solicite, seleccione una sucursal de la lista.
Barra de estado : haga clic en el indicador de sucursal y seleccione una sucursal de la lista.
Pruébelo: cree una nueva rama para el proyecto Wikipedia_Chatbot. En Example.py, cambie la cadena asignada a la first_questionvariable a Hi, what would you like to know?.

Ejecute el comando Git: Crear rama.
Cuando se le solicite, asigne un nombre a la sucursal vscode-chatbot-exercises. Ver Figura 4.36 .

Figura 4.36 :Se ingresa el nombre de la sucursal para crear una nueva sucursal.

Confirme que la vscode-chatbot-exercisessucursal esté retirada en la barra de estado (consulte la Figura 4.37 ).

Figura 4.37 :El indicador de sucursal en la barra de estado muestra que lavscode-chatbot-exercisessucursal está retirada.

Cambie la cadena asignada a la first_questionvariable aHi, what would you like to know?
Mandos a distancia
Visual Studio Code también admite repositorios conectados a un control remoto, como GitHub. Puede insertar, extraer y sincronizar una rama con su origen, todo dentro del editor. Los comandos de Git antes mencionados están disponibles en la vista Control de código fuente dentro del menú Más acciones. Ver Figura 4.38 .


Figura 4.38 :Se puede acceder al menú Más acciones desde la parte superior de la vista Control de código fuente.

La acción Sincronizar cambios en la barra de estado de Git lleva los cambios remotos a su repositorio local y luego envía las confirmaciones locales al repositorio remoto. Si no hay ningún repositorio remoto configurado, la acción Publicar está habilitada, lo que le permite publicar la rama actual en un repositorio remoto.

Visual Studio Code también puede recuperar cambios desde un control remoto. El beneficio de esta característica es que el editor puede mostrarle cuántos cambios está su repositorio local por delante o por detrás del remoto. Aunque esta función está deshabilitada de forma predeterminada, puede modificar la configuración git.autofetchpara truehabilitarla.

Indicadores de canalón
Si realiza cambios en un archivo dentro de una carpeta que es un repositorio de Git, el código de Visual Studio agrega anotaciones a la izquierda de la ventana del editor, lo que se conoce como medianil ( consulte la Figura 4.39 ). Hay tres indicadores visuales:


Figura 4.39 :Para elExample.pyarchivo, el medianil indica que se ha eliminado una línea (A), se ha modificado una línea (B) y se ha agregado una nueva línea (C).

Etiqueta A: se han eliminado líneas
Etiqueta B: líneas modificadas
Etiqueta C : nuevas líneas agregadas
Ver diferencias
Los cambios se comparan en el editor Diff. Para ver las diferencias de un archivo, seleccione el archivo en la vista Control de código fuente. El editor de diferencias se abre en una nueva pestaña con una vista de lado a lado de las diferencias (consulte la Figura 4.40 ).


Figura 4.40 :Las diferencias se muestran en el editor de diferencias para elExample.pyarchivo original y la versión recién modificada.

Puede alternar a la vista en línea abriendo el menú Más acciones en la parte superior del editor de diferencias y seleccionando Alternar vista en línea (consulte la Figura 4.41 ).


Figura 4.41 :Se puede acceder al elemento de menú Alternar vista en línea desde el menú Más acciones en la parte superior del editor Diff.

Los iconos de Cambio anterior (Ctrl+Opción+F5/Shift+Alt+F3) y Cambio siguiente (Opción+F5/Alt+F3) se utilizan para navegar por las diferencias. Ver Figura 4.42 .


Figura 4.42 :El icono de Cambio anterior (A) es una flecha hacia arriba. El icono de Próximo cambio (B) es una flecha hacia abajo.

Pruébelo: en el Example.pyarchivo, cambie la cadena asignada a la first_questionvariable a Hi, what would you like to know?. Guarda el archivo.

from chatbot import Chat, register_call
import wikipedia
import os
import warnings
warnings.filterwarnings("ignore")
 
@register_call("whoIs")
 def who_is(session, query):
    try:
        return wikipedia.summary(query)
    except Exception:
        for new_query in wikipedia.search(query):
            try:
                return wikipedia.summary(new_query)
            except Exception:
                pass
    return "I don't know about "+query
 
first_question = "Hi, what would you like to know?"
chat = Chat(os.path.join(os.path.dirname(os.path.abspath(__file__)), "Example.template"))
chat.converse(first_question)
Seleccione el Example.pyarchivo en la vista Control de código fuente para ver las diferencias en elEditor de diferencias (consulte la Figura 4.43 ) y luego confirme los cambios.


Figura 4.43 :El editor Diff muestra elExample.pyarchivo original y la versión recién modificada.

También puedes seleccionar manualmente dos archivos cualesquiera para ver las diferencias:

Vista del Explorador : haga clic con el botón derecho en el archivo en el Explorador o en la lista Abrir editores y seleccione Seleccionar para comparar. A continuación, haga clic derecho en el segundo archivo para comparar y seleccione Comparar con <nombre de archivo_usted_eligió>.
Atajo de teclado : seleccione un archivo en la ventana del editor para convertirlo en el archivo activo. Ingrese el método abreviado de teclado Cmd+Shift+P/Ctrl+Shift+P y seleccione Archivo: Comparar archivo activo con. Seleccione el archivo para comparar de la lista de archivos recientes.
Empujar y fusionar confirmaciones
A medida que se confirman los cambios, la barra de estado enumera el número total de confirmaciones para enviar al origen. Al seleccionar el elemento de la barra de estado se ejecuta la tarea de empujar y tirar al origen. Ver Figura 4.44 .


Figura 4.44 :El número de confirmaciones que se enviarán al servidor remoto se muestra en la barra de estado junto a la rama desprotegida.

Después de enviar las confirmaciones, el elemento de la barra de estado cambia para mostrar solo el ícono Sincronizar cambios (consulte la Figura 4.45 ).


Figura 4.45 :El icono Sincronizar cambios aparece junto a la rama retirada.

Solicitudes de extracción
El flujo de trabajo de solicitud de extracción se admite en Visual Studio Code con extensiones de solicitud de extracción. Una de esas extensiones es la extensión GitHub Pull Requests and Issues. Las extensiones de solicitud de extracción le permiten revisar, comentar y fusionar solicitudes de extracción, todo dentro del editor para un control remoto (consulte la Figura 4.46 ).


Figura 4.46 :La extensión GitHub Pull Requests and Issues proporciona una vista en el Explorador (A), que se utiliza para administrar las solicitudes de extracción. La vista muestra solicitudes de extracción (B) y problemas (C).

Compartir en vivo
La extensión Live Share permite compartir y colaborar entre múltiples usuarios pero dentro de Visual Studio Code. Un anfitrión comparte un proyecto en Visual Studio Code con invitados que pueden ver o editar el proyecto de forma remota. Los colaboradores pueden trabajar juntos simultáneamente en un proyecto, eliminando así las tareas de ida y vuelta para confirmaciones, envíos, solicitudes de extracción y conflictos de fusión. Live Share proporciona funcionalidad completa para todos los participantes, independientemente de si se unen a una sesión en el cliente de escritorio de Visual Studio Code (en cualquier sistema operativo) o en un navegador web. Al final, una sesión colaborativa da como resultado un compromiso único. Se requiere una cuenta de Microsoft o GitHub para participar en una sesión de Live Share. Compartir o unirse a la sesión se produce en cuestión de segundos y mantiene el acceso a las configuraciones y ajustes de su entorno preferido.

Instalar en vivo compartir
Descargue la extensión Live Share desde Extension Marketplace. La página de extensión incluye los requisitos necesarios para utilizar la extensión.

Una vez que esté instalado, vuelva a cargar y espere a que se descarguen e instalen las dependencias. Puede verificar el estado de la instalación dentro de la barra de estado. Una vez completada la instalación, se agregan al editor algunos elementos y funciones de la interfaz de usuario adicionales.

NOTA Para los usuarios de Linux, si se le promociona para instalar bibliotecas, haga clic en Instalar, ingrese su contraseña y reinicie Visual Studio Code una vez completado.

Barra de estado: Live Share : el elemento de la barra de estado de Live Share se utiliza para iniciar sesión en Live Share y también proporciona estados de sesión que se actualizan durante una colaboración activa. Ver Figura 4.47 . También puede ver una lista de participantes seleccionando el ícono de personas.

Figura 4.47 :El elemento de la barra de estado de Live Share se muestra en la barra de estado. Al seleccionar la barra, se inicia sesión en Live Share. Si ha iniciado sesión y actualmente organiza o asiste a una sesión activa, puede ver los estados y los participantes de la sesión.

Barra de actividad: Vista del Explorador de Live Share: la vista del Explorador de Live Share dentro de la barra de actividad muestra el proyecto compartido activo además de los participantes de la sesión (consulte la Figura 4.48 ). También puede acceder a todas las funciones de Live Share dentro de esta vista.

Figura 4.48 :El icono de Live Share Explorer se utiliza para abrir la vista de Live Share Explorer. Esta vista muestra los detalles de la sesión y los contactos.

Paleta de comandos : todas las funciones de Live Share están disponibles en la paleta de comandos. Para ver una lista completa de comandos, escriba Live Share en la paleta de comandos. Una lista contextualizada de comandos está disponible seleccionando el elemento de la barra de estado de Live Share.
Inicia sesión para compartir en vivo
Por motivos de seguridad, es necesario iniciar sesión para utilizar Live Share. Se requieren los siguientes tipos de cuenta:

Cuenta personal de Microsoft (p. ej., @ outlook.com)
Cuenta profesional o educativa respaldada por Microsoft (Azure Active Directory—AAD)
cuenta GitHub
Para iniciar sesión, haga clic en el elemento de la barra de estado de Live Share. Aparece una notificación que le solicita que inicie sesión a través del navegador. Haga clic en Iniciar sesión para abrir el navegador en una página de inicio de sesión. Alternativamente, puede ejecutar el comando Live Share: Iniciar sesión con el navegador para acceder a la página de inicio de sesión. Una vez que haya iniciado sesión, cierre el navegador y regrese a Visual Studio Code.

Si inició sesión sin unirse a una sesión, la barra de estado refleja que ha iniciado sesión (consulte la Figura 4.49 ) y muestra un icono para que pueda compartir un proyecto.


Figura 4.49 :Después de iniciar sesión en Live Share, la barra de estado muestra el nombre proporcionado para la cuenta que inició sesión.

Si inició sesión después de acceder a un enlace para unirse a una sesión, la barra de estado inicialmente refleja que se está uniendo a una sesión seguido de un cambio de estado para indicar que se ha unido a la sesión.

NOTA Si tiene problemas con Visual Studio Code al detectar un inicio de sesión exitoso, puede ingresar un código de usuario en su lugar. Ejecute el comando Live Share: Iniciar sesión con código de usuario para abrir el navegador. Después de iniciar sesión, haga clic en el enlace ¿Tiene problemas? Haga clic aquí para obtener instrucciones sobre el código de usuario . para ver el código de usuario. En Visual Studio Code, ingrese el código en el campo de entrada que apareció cuando ejecutó el comando. Una vez hecho esto, presione Entrar para completar el proceso de inicio de sesión.

Compartir un proyecto
Un anfitrión proporciona acceso a una sesión de Live Share compartiendo un enlace de invitación con los invitados. Antes de poder generar un enlace de invitación, primero se debe abrir el proyecto.en código de Visual Studio. Los anfitriones tienen total flexibilidad con respecto a qué archivos/carpetas son visibles para los invitados. Además, los anfitriones pueden seleccionar si la sesión permite ediciones o es de solo lectura.

Los pasos para compartir un proyecto son los siguientes:

Abra una carpeta que desee compartir con los invitados.
NOTA De forma predeterminada, Live Share oculta los archivos/carpetas a los que se hace referencia en .gitignorelos archivos. Ocultar un archivo evita que aparezca en el árbol de archivos del invitado. También puede excluir un archivo, lo que impide que Live Share abra el archivo para los invitados. Puede ocultar/excluir archivos creando un .vsls.jsonarchivo en su proyecto. Para obtener información adicional sobre cómo crear un .vsls.jsonarchivo, visite docs.microsoft.com/visualstudio/liveshare/reference/security.

En la barra de estado, haga clic en el elemento de la barra de estado de Live Share o ejecute el comando Live Share: Iniciar una sesión de colaboración (Compartir).
Después de compartir, aparece una notificación para informarle que el enlace de invitación se ha copiado en su portapapeles (consulte la Figura 4.50 ). El enlace siempre está disponible para acceder haciendo clic en el elemento de la barra de estado y seleccionando Invitar a otros (Copiar enlace). La notificación también le permite configurar la sesión en solo lectura. Una sesión de solo lectura impide que otros editen el proyecto. Esta configuración puede resultar útil para una sesión con invitados externos en los que quizás no confíe o cuando realice una programación en pareja.


Figura 4.50 :Aparece una notificación en el editor para informarle que el enlace de invitación se ha copiado en el portapapeles. La notificación también ofrece la opción de hacer que la sesión sea de solo lectura.

Comparte el enlace con un invitado. Cuando un invitado hace clic en el enlace, se le solicita que inicie sesión para unirse a la sesión. Si el invitado elige iniciar sesión como anónimo, Visual Studio proporciona una notificación al anfitrión solicitando aprobación para permitir que el invitado anónimo se una a la sesión (consulte la Figura 4.51 ).

Figura 4.51 :Visual Studio Code muestra una notificación que solicita si se debe permitir que el invitado anónimo John Doe se una a la sesión. El anfitrión también podría seleccionar la opción para permitir siempre que se unan invitados anónimos. Seleccionar la última opción permite que invitados anónimos se unan automáticamente a sesiones futuras sin la aprobación del anfitrión.

NOTA Si prefiere solicitar aprobación para unirse a una sesión, agregue la siguiente entrada a settings.json: "liveshare.guestApprovalRequired": true.

Una vez que la sesión está activa, la barra de estado refleja que hay una sesión de colaboración activa (consulte la Figura 4.52 ) y proporciona un recuento total de invitados. Los invitados son dirigidos automáticamente al archivo que estás editando una vez que se unen a la sesión.


Figura 4.52 :La barra de estado muestra que hay un invitado actualmente en la sesión.

NOTA El terminal no se comparte por defecto. El anfitrión debe compartir manualmente la terminal para que los invitados ejecuten comandos. Consulte "Compartir una terminal" para obtener más información.

Cuando haya terminado de compartir el proyecto, deje de compartir haciendo clic en el icono Detener sesión de colaboración en la vista Live Share (consulte la Figura 4.53 ). Una vez que se detiene el intercambio, se notifica a todos los invitados que la sesión ha finalizado. En ese momento, los invitados ya no tienen acceso al proyecto y los archivos temporales se limpian automáticamente.


Figura 4.53 :El icono Detener sesión de colaboración aparece en la sección Detalles de la sesión de la vista Live Share. Haga clic en el icono para detener la sesión.

Unirse a una sesión
Los invitados reciben acceso a una sesión de Live Share navegando al enlace de invitación compartido por el anfitrión. Los invitados pueden unirse a una sesión a través de un navegador web o mediante el cliente de escritorio Visual Studio Code (consulte la Figura 4.54 ). Unirse a través del navegador es ideal para invitados que quizás no tengan instaladas las herramientas necesarias y proporciona un acceso más rápido a la sesión. El acceso al navegador es óptimo para invitados a corto plazo que no necesitarían instalar Visual Studio Code localmente. El navegador también es una alternativa para los colaboradores que trabajan en una tableta, teléfono inteligente o cualquier otro dispositivo que no pueda ejecutar Visual Studio Code, mientras que unirse con Visual Studio Code es ideal para invitados que ya tienen el editor ejecutándose o que tienen problemas para unirse. el enlace de invitación.

Para unirse a una sesión a través del navegador web, haga clic en el enlace de invitación proporcionado por el anfitrión. El enlace lo lleva a una página web que brinda la opción de continuar con el navegador. Una vez que se una a la sesión, tendrá acceso completo a todas las funciones de edición de Visual Studio Code. Para salir de la sesión, cierre la ventana del navegador.


Figura 4.54 :Cuando un invitado hace clic en el enlace de invitación para unirse a la sesión, se le da la opción de unirse a través de Visual Studio Code o continuar en el navegador.

Unirse a una sesión a través del cliente de escritorio requiere que la extensión Live Share ya esté instalada en el editor. Después de iniciar sesión en Live Share, navegue hasta la vista Live Share en la barra de actividades y haga clic en el icono Unirse a sesión de colaboración (consulte la Figura 4.55 ).


Figura 4.55 :El ícono Unirse a la sesión de colaboración aparece en la sección Detalles de la sesión de la vista Live Share.

Puede pegar la URL del enlace de invitación y presionar Enter para confirmar (consulte la Figura 4.56 ). Una vez confirmada, estará conectado a la sesión y la barra de estado se actualizará para reflejar que se ha unido y el recuento total de invitados.


Figura 4.56 :La URL de invitación se ingresa cuando se le solicita unirse a la sesión.

Para salir de la sesión, cierre la ventana de Visual Studio Code (consulte la Figura 4.57 ). Alternativamente, si prefiere mantener la ventana abierta, haga clic en el ícono Abandonar sesión de colaboración en la vista Live Share.


Figura 4.57 :Para abandonar una sesión, seleccione el icono Abandonar sesión de colaboración en la vista Live Share.

Edición y colaboración
Durante la sesión, todos tienen la capacidad de editar código simultáneamente (si la sesión no es de solo lectura) y navegar por los archivos y carpetas del proyecto. Tanto el anfitrión como los invitados pueden ver las ediciones y selecciones de cada uno en tiempo real. Visual Studio Code muestra una bandera junto al cursor de un invitado cuando pasa el cursor o cuando edita, resalta o mueve el cursor (consulte la Figura 4.58 ).


Figura 4.58 :Visual Studio Code indica dónde tienen el cursor los participantes de la sesión en el editor.

Seguir a un participante
Seguir le permite seguir todo lo que hace el anfitrión u otro invitado en el editor. Puedes seguir a una persona seleccionando su nombre en la lista de participantes. Si está siguiendo a alguien, el círculo al lado de su nombre se completa y también se muestra el número de línea en su archivo activo (consulte la Figura 4.59 ).


Figura 4.59 :Cuando se sigue a una persona, aparece un círculo relleno junto a su nombre.

También puedes seguir a alguien haciendo clic en el ícono de chincheta en la esquina derecha del grupo del editor (ver Figura 4.60 ). Si hay más de una persona en la sesión, se le pedirá que seleccione al participante que desea seguir.


Figura 4.60 :El icono de pin en la ventana del editor se puede utilizar para seguir a un participante de la sesión.

NOTA Debido a que el seguimiento está vinculado a un grupo de editores, puede usar la vista dividida para seguir a un participante en un grupo y luego trabajar en otra cosa de forma independiente en otro.

Puedes dejar de seguir a alguien seleccionando nuevamente el ícono de pin o con el método abreviado de teclado Cmd+Alt+F/Ctrl+Alt+F. Además, lo siguiente se detiene automáticamente si realiza alguna de las siguientes acciones:

Comience a editar el archivo actualmente activo
Abrir un archivo diferente
Cerrar el archivo actualmente activo
Compartir una terminal
Los anfitriones también pueden compartir terminales con los invitados (ver Figura 4.61 ). Compartir una terminal permite a los invitados ejecutar comandos por sí mismos sin la necesidad de depender del anfitrión. Esto puede resultar útil en los casos en los que puede resultar más eficiente para un invitado ejecutar una serie de comandos en lugar de guiar al host a través de los comandos que debe ejecutar dentro de la terminal. Aunque los terminales no se comparten de forma predeterminada, el anfitrión puede compartir un terminal haciendo clic en el icono Compartir terminal o en la entrada en la vista Live Share. Antes de compartir el terminal, Visual Studio Code ofrece la opción de seleccionar uno de los dos modos de acceso siguientes:

Acceso de solo lectura : los invitados solo pueden ver la entrada y salida del terminal del anfitrión.
Acceso de lectura/escritura : los invitados pueden ver la terminal del anfitrión, escribir en la terminal y ejecutar comandos.
NOTA El acceso de lectura y escritura solo se debe otorgar a los invitados cuando realmente lo necesiten. El acceso de lectura y escritura brinda a los invitados la posibilidad de ejecutar cualquier comando en la computadora del anfitrión.


Figura 4.61 :El anfitrión puede seleccionar una terminal en el espacio de trabajo para compartirla con los invitados.

Visual Studio Code proporciona una nueva terminal compartida una vez que se selecciona el modo de acceso. Cuando finaliza una sesión de terminal compartida, todos los invitados se desconectan. Los hosts pueden detener una sesión de terminal compartida de tres maneras:

Escribe en la terminal exit
Cerrar la ventana de la terminal
Haga clic en el icono Dejar de compartir terminal en la vista Live Share
NOTA Para obtener información adicional sobre Live Share y ver un video de ejemplo de una sesión, consulte visualstudio.microsoft.com/services/live-share/.

Resumen
En este capítulo, aprendió cómo hacer lo siguiente:

Navegar por archivos de proyecto en la vista del Explorador o con rutas de navegación
Buscar en archivos de proyecto en la vista de búsqueda
Activar un entorno virtual o conda para un proyecto
Gestionar el control de versiones con Git
Colabora con otras personas de forma remota mediante Live Share
Ahora está preparado para administrar un proyecto de Python y colaborar con otros en Visual Studio Code.
