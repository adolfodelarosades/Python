# Capítulo 2. Sumérgete: *Demonos un chapuzón*

<img width="931" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a092743b-b24c-4caa-a7c8-88fd1d8ff5cd">

* “¿Cómo está trabajando el entrenador en este momento?”

* “El entrenador necesita un cronómetro más capaz”

* “Conversación en el cubículo”

* “El archivo y la hoja de cálculo están “relacionados””

* "Nuestra primera tarea: extraer los datos del nombre del archivo"

* “Un string es un objeto con atributos”

* “Extraer los datos del nadador del nombre del archivo”

* "No intentes adivinar qué hace un método..."

* “Splitting(Partir) (también conocido como romper) un string”

* “Aún queda trabajo por hacer”

* "Leer mensajes de error de abajo hacia arriba"

* "Tenga cuidado al combinar llamadas a métodos"

* "Probemos con otro string method"

* “Solo queda crear algunas variables”

* “¡La tarea n.° 1 está terminada!”

* “Tarea #2: Procesar los datos en el archivo”

**La mejor manera de aprender un lenguaje es escribir código.**

Y si vas a escribir código, necesitarás un problema **real**. Quiso la suerte que tengamos uno de esos. En este capítulo, comenzará su viaje de desarrollo de aplicaciones Python dando un chapuzón con nuestro amigable entrenador de natación local. Comenzará con **strings** de Python, aprenderá a **manipularlas** según sus deseos y, al mismo tiempo, trabajará para producir una solución basada en Python para el problema del entrenador. También verá más de la estructura de datos **list** incorporada de Python, aprenderá cómo funcionan las variables y descubrirá cómo leer los mensajes de error de Python sin salirse del extremo, todo mientras resuelve un problema real con código Python real. Vamos a sumergirnos (de cabeza primero)…

<img width="1019" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/82080edc-fda5-4bc7-ac02-5000939bda9b">


**Esto suena interesante.**

La conversación posterior con el entrenador comienza a desentrañar algunos de los detalles...

Cuando se trata de seguir el progreso de sus jóvenes nadadores, el entrenador lo hace todo manualmente. Durante una sesión de entrenamiento, registra los tiempos de entrenamiento de cada nadador en su confiable portapapeles y luego, más tarde en casa, escribe manualmente los tiempos de cada nadador en su programa de hoja de cálculo favorito para realizar un análisis de rendimiento simple.

Por ahora, este análisis es sencillo. Los tiempos para el...

## 💻 Ejecución de código descargado del material de apoyo.

El archivo de este capítulo se llama **Darius.ipynb**.

Vamos a definir un **string** y comprobaremos su tipo:

```py
fn = "Darius-13-100m-Fly.txt"
```

<img width="1202" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/ab1aae05-d0a6-452c-b16c-df554d060aee">

Vamos a ver todos los atributos de un **str**.

```py
print(dir(fn))
```

<img width="1175" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e15ca613-7651-4b2a-9f24-9ca15caeece6">

```sh
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__',
'__getattribute__', '__getitem__', '__getnewargs__', '__getstate__', '__gt__', '__hash__', '__init__', '__init_subclass__',
'__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__',
'__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold',
'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha',
'isascii', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper',
'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'removeprefix', 'removesuffix', 'replace', 'rfind', 'rindex',
'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate',
'upper', 'zfill']
```

Podemos convertir un **str** a mayusculas con el método **`upper`** aplicado sobre la variable **str**.

```py
fn.upper()
```

<img width="1189" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/d396d7b6-89a3-4d5f-8b71-a92eceeaeaf8">

Podemos convertir un **str** a minusculas con el método **`lower`** aplicado sobre la variable **str**.

```py
fn.lower()
```

<img width="1199" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/812c56f5-3569-47e5-854d-6972a7c90be3">

Sin embargo si vemos el valor de la variable **`fn`** no a cambiado.

```py
fn
```

<img width="1187" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/8c1fead3-c42a-42ad-89f7-5665a759eb3c">

Dentro de los atributos del **str** tenemos **`split`**, podemos ver la documentación de este método:

```py
help(fn.split)
```

<img width="1183" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/0a7a8d30-d250-47f1-869a-aac440ba35c9">

Como podemos ver **`split`** toma un **str** y nos devuelve una lista de substrings.

Por ejemplo vamos a definir un nuevo **str** y vamos a aplicarle el método **`split()`**

```py
title = "So long, and thanks for all the fish."

title.split()
```

<img width="1185" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/570cd5dd-b378-4c9d-b434-e329e2fbe35a">

No hemos puesto ningún argumento al método **`split()`** y lo que nos ha hecho es recuperar todos los subStrings que encuentra en **`title`** tomando como separador el carácter de espacío **` `**.

Si aplicamos el método **`split()`** sobre **`fn`** nos va a retornar una lista con un solo elemento ya que no hay substrings separados por blancos.

```py
fn.split()
```

<img width="1187" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/8d5dca6e-324b-4ed2-b4a1-c4425a38bbfb">

Si indicamos que queremos obtener los substring en base al separador **`", "`** vamos a obtener una lista con solo dos elementos.

```py
title.split(", ")
```

<img width="1185" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/a0559a44-2a7e-4964-af5f-5e959b1a88b8">

Si indicamos que queremos obtener los substring en base al separador **`"-"`** sobre **`fn`** vamos a obtener una lista con cuatro elementos.


```py
fn.split("-")
```

<img width="1171" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/078bc7dd-64a4-405a-add0-0c31c8a8c0ba">

Si indicamos que queremos obtener los substring en base al separador **`"13"`** sobre **`fn`** vamos a obtener una lista con dos elementos.

```py
fn.split("13")
```

<img width="1186" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/5ad5ac9b-7930-4bbe-82ca-ae0c1ef8a47e">

Si indicamos que queremos obtener los substring en base al separador **`"-1"`** sobre **`fn`** vamos a obtener una lista con tres elementos.

```py
fn.split("-1")
```

<img width="1179" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/311f1d1b-459a-4bfb-bc92-8bb58c60b463">


Si indicamos que queremos obtener los substring en base al separador **`"."`** sobre **`fn`** vamos a obtener una lista con dos elementos.

```py
fn.split(".")
```

<img width="1178" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/59f1415c-0543-4920-8c29-585a9def8eec">

Si indicamos que queremos obtener los substring en base al separador **`"-."`** sobre **`fn`** vamos a obtener una lista con un elemento, ya que no existe **`"-."`** en la cadena.

```py
fn.split("-.")
```

<img width="1193" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/0c80aa8c-dd05-4b3c-96ff-eaaf33b29643">

Si intentamos aplicar dos veces el método **`split()`** sobre **`fn`** vamos a tener un error.

```py
fn.split("-").split(".")
```

<img width="1200" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/aaa9ee7b-b0d3-4989-a5f9-4d2e2e81267f">

Esto es por que el primer **`split("-")`** nos retorna una lista y queremos aplicar **`split(".")`** sobre la lista pero ese método no existe para aplicarse sobre una lista.

Dentro de los atributos de un **str** nos aparecia el método **`removesuffix`**, podemos ver su documentación.


```py
help(fn.removesuffix)
```

<img width="1198" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/dc896356-4bc2-4c75-94b7-952b61d64b4d">

Sobre la cadena **`Fly.txt`** removemos el sufijo **`.txt`** y lo que se obtiene es un **str**.

```py
"Fly.txt".removesuffix(".txt")
```

<img width="1206" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/45419af7-9671-4be5-8bf7-68de32b4f529">


Repetimos sobre varias cadenas diferentes.
```py
"Free.txt".removesuffix(".txt")
```

<img width="1191" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/0de0570f-f563-4d0f-8360-19b339078a7b">

Ahora vamos a aplicar dos métodos sobre **`fn`**

```py
fn.removesuffix(".txt").split("-")
```

Primero quitamos el sufijo y obtenemos un **str** y sobre este obtenemos todos los substrings separados por **`-`**, teniendo una lista de 4 elementos.

<img width="1199" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/93da5086-f9e5-459e-9fb4-12ede4c3a2b0">

Vamos a definir una variable númerica, vamos a ver su tipo y su valor:

```py
pie = 3.14

type(pie)

pie
```

<img width="1195" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/eabbfbf0-81cf-4417-a438-b3912a9a9336">


Podemos definir dos variables en una misma línea.

```py
pie, meaning = 3.14, 42

pie

meaning
```

<img width="1200" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e2cea6d6-3d05-432c-808c-472c14c8de93">

Otra forma de definir algo similar es mediante una lista.

```py
pie, meaning = [3.14, 42]

pie

meaning
```

<img width="1205" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/e1b56d1b-fdd3-4aca-a234-3844344b3b54">

Vamos a combinar varias cosas que hemos visto y ver los resultados.

```py
fn = "Darius-13-100m-Fly.txt"

swimmer, age, distance, stroke = fn.removesuffix(".txt").split("-")

print(swimmer)
print(age)
print(distance)
print(stroke)
```

<img width="1183" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/8dbc5267-a8c6-4734-bc55-100bf5ae1d22">


```py
fn = "Abi-10-50m-Back.txt"

swimmer, age, distance, stroke = fn.removesuffix(".txt").split("-")

print(swimmer)
print(age)
print(distance)
print(stroke)
```

<img width="1196" alt="image" src="https://github.com/adolfodelarosades/Python/assets/23094588/ac45b55a-1fa8-4646-a284-882896135905">


