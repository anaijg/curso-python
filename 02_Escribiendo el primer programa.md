# Escribiendo el primer programa

## El programa Hello World

En este tema aprenderás a desarrollar tus primeros programas en Python. Aunque estos programas son bastante sencillos, siguen siendo sintácticamente correctos y demuestran que programar en Python es una experiencia muy agradable.

Nuestro primer ejemplo será **Hello, World!**. Tradicionalmente se utiliza para introducir a los principiantes en un nuevo lenguaje de programación.

```python
print("Hello, World!")
```

Como puedes ver, este programa consta de una sola línea. Imprime la cadena de texto que se pasa entre paréntesis, pero sin las comillas. Puedes ejecutar este código en línea. Para ello, copia el código en [esta página web](https://onecompiler.com/python) y haz clic en el triángulo. Como alternativa, puedes seguir estos [consejos de instalación](https://www.python.org/about/gettingstarted/#installing). Deberías obtener este resultado:

```text
Hello, World!
```

Aunque este código es muy sencillo, vamos a analizarlo detalladamente.

## Breve explicación

**print** es el nombre de una función. Una **función** es un [**bloque de código**](https://hyperskill.org/learn/step/5208 "En Python, un bloque de código hace referencia a un grupo de líneas de código consecutivas que se ejecutan como una única unidad. Normalmente se define mediante una línea de cabecera, también conocida como una línea que comienza con una palabra clave como 'if', 'for', 'while' o 'def'. A la línea de cabecera le siguen una o más líneas de código indentadas que forman el bloque. Estas líneas indentadas se ejecutan únicamente si se cumple la condición especificada en la línea de cabecera. Una indentación correcta es fundamental para que el bloque de código funcione correctamente. Los bloques de código pueden estar anidados, lo que significa que un bloque de código puede contener otro bloque de código.") que realiza un trabajo útil para ti, por ejemplo, mostrar texto. En cierto sentido, una función es un subprograma que puede reutilizarse dentro de tus programas. Cuando el nombre de una función va seguido de paréntesis, significa que la función ha sido **llamada** para obtener su resultado.

Sigamos: `"Hello, World!"` es una cadena de texto de Python. Todas las cadenas de texto están delimitadas por comillas *simples* o *dobles*, por lo que `'Hello, World!'` también es una cadena válida. Puedes sustituir esta cadena por otra y el programa mostrará la nueva cadena. Por ejemplo:

```python
print('Python 3.x')
```

Como puedes imaginar, este programa mostrará lo siguiente:

```text
Python 3.x
```

## Mostrar comillas

Imagina que la cadena de texto que quieres mostrar ya contiene comillas. Si quieres incluirlas dentro de una cadena, delimita esta cadena utilizando comillas de **otro** tipo. Por ejemplo:

```python
print("Yes, I'm ready to learn Python.")
```

La parte de la cadena que contiene `I'm` se muestra **correctamente** porque has utilizado comillas dobles `"..."` para delimitar toda la cadena:

```text
Yes, I'm ready to learn Python.
```

Escribir lo siguiente es **incorrecto**:

```python
print('Yes, I'm ready to learn Python.')
```

Tu programa no sabrá dónde comienza y dónde termina la cadena.

Puedes ejecutar todos los ejemplos utilizando la [página web](https://onecompiler.com/python) indicada anteriormente. Esto te ayudará a familiarizarte con Python.

## Posibles errores

Incluso las líneas de código más sencillas pueden contener errores. Algunos de los más habituales son:

* **Introducir una indentación adicional**

```python
   print("Hello, World!")
```

Esta instrucción no funciona debido a los espacios adicionales que aparecen antes de `print`.

* **Llamar a una función utilizando un nombre incorrecto**

```python
pint("Hello, World!")
```

Esta línea contiene `pint` en lugar de `print`. Asegúrate de utilizar el nombre correcto de cada función.

* **Escribir los nombres utilizando mayúsculas o minúsculas incorrectamente**

```python
PRINT("All caps")
```

`Print`, `print` y `PRINT` no son lo mismo. En Python, los nombres distinguen entre mayúsculas y minúsculas.

* **Olvidar una o las dos comillas de una cadena de texto**

```python
print("Python)
```

Esta instrucción no funciona porque faltan las comillas de cierre.

* **Olvidar uno o más paréntesis**

```python
print("I have no end"
```

Ten cuidado con los paréntesis, especialmente al llamar a una función.

Con la información anterior, no deberías tener demasiados problemas con este tipo de programas.

## Resumen

En este tema hemos escrito nuestro primer programa en Python. Lo hemos analizado, hemos mostrado algunas cadenas de texto y hemos revisado los errores más habituales que puedes encontrar al principio.

## EJERCICIOS

## La verdad eterna

Las cadenas de texto que quieres imprimir pueden variar mucho y no tienen por qué parecerse al clásico `"Hello, world!"`. ¡Vamos a descubrir si esto puede influir en la sintaxis de tu programa!

Tu tarea consiste en escribir un programa que muestre la siguiente cadena:

```text
2 + 2 = 4
```

**Escribe un programa en Python 3.**

```python
print("2 + 2 = 4")
```

## ¿Cuál es el error?

Como desarrollador, encontrar y corregir errores forma parte de tu rutina diaria.

Mejora esta importante habilidad identificando y nombrando los errores que aparecen en las siguientes líneas de código.

**Relaciona los elementos de las columnas izquierda y derecha:**

| Código                            | Error                                                                 |
| --------------------------------- | --------------------------------------------------------------------- |
| `prnt("This is a test string.")`  | la función se ha llamado con un nombre incorrecto                     |
| `PRINT("This is a test string.")` | el nombre de la función utiliza mayúsculas/minúsculas incorrectamente |
| `print("THIS IS A TEST STRING.)`  | falta una comilla                                                     |
| `print("This is a test string."`  | faltan paréntesis                                                     |

## Crear un programa de saludo personalizado

Completa los huecos del siguiente fragmento de código Python para crear un sencillo programa de saludo. El programa debe pedir y leer el nombre del usuario desde la entrada de la consola y, a continuación, mostrar un mensaje que diga **«Encantado de conocerte,»** seguido del nombre del usuario.

**Rellena los huecos con los elementos correspondientes:**

```python
print("Hello, what is your name?")
user = input()
reply = "Nice to meet you, " + user + "!"
print(reply)
```

## ¿Qué paréntesis debemos poner?

Hemos creado un programa para mostrar un mensaje de saludo, pero hemos olvidado qué paréntesis debemos utilizar con la función `print`. Completa los huecos para terminar el programa.

**Rellena los huecos con los elementos correspondientes:**

```python
print("Hello, how's your day?")
```

## ¿Qué es `print`?

Observa estas cuatro nociones clave de la programación: **sentencias, funciones, comandos y expresiones**. Consulta sus definiciones a continuación y determina cuál de ellas corresponde a `print` en Python 3.

**Selecciona una opción de la lista:**

* **Función** que recibe argumentos entre paréntesis, realiza una tarea específica y devuelve resultados. (Esta es la respuesta correcta).

* **Sentencia** que realiza acciones, pero no devuelve nada y no requiere paréntesis.

* **Comando** que hace que el ordenador realice una tarea específica en la interfaz de línea de comandos.

* **Expresión** que consta únicamente de valores (como `2` o `'hello'`) y operadores (como `+` o `==`).

## Lenguaje de programación favorito

¿Cuál es tu lenguaje de programación favorito? Indícanos cuál es completando los huecos.

**Rellena los huecos con los elementos correspondientes:**

```python
fav_lang = "python"
print(fav_lang)
```

## ¡Error

Una habilidad fundamental para cualquier desarrollador es comprobar el código.

Comienza a desarrollar esta habilidad examinando las siguientes líneas y seleccionando **únicamente las correctas**.

**Selecciona una o más opciones de la lista:**

* `print("Hello, World!"`
* `print(Hello, World!)`
* `PRINT("Hello, World!")`
* `print("Hello, World!")`
* `print('Hello, World!')`
