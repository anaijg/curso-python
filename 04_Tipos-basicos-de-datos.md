# Tipos basicos de datos
Cada [**objeto de datos**](https://hyperskill.org/learn/step/5852 "En Python, un objeto de datos es un contenedor que almacena información sobre un valor y que también puede almacenar datos adicionales, como su identidad. Cuando asignas un valor a una variable, Python crea un nuevo objeto, coloca el valor dentro del objeto y, a continuación, crea una referencia desde el nombre de la variable al objeto. Algunos ejemplos de objetos de datos en Python son las listas, las tuplas, los conjuntos y los diccionarios. Cada objeto de datos tiene un tipo que describe cómo almacenarlo en memoria, qué operaciones se pueden aplicar sobre él y cómo ejecutar dichas operaciones.") (una variable o una [**constante**](https://hyperskill.org/learn/step/5852 "En Python, una constante es un tipo de variable que, una vez que se le asigna un valor, no puede reasignarse. Sin embargo, Python no proporciona compatibilidad integrada para las constantes y los nombres de las variables no se imponen como constantes. En su lugar, los programadores utilizan convenciones de nomenclatura para indicar que una variable debe tratarse como una constante. En el contexto del texto proporcionado, se habla de dos constantes concretas, `inf` y `-inf`, que representan el infinito positivo y negativo, respectivamente. Estas constantes forman parte del sistema de aritmética de números en coma flotante y siguen las mismas reglas que otros números en coma flotante. Se pueden utilizar en operaciones aritméticas y permiten optimizar algoritmos y encontrar los valores mínimo y máximo de una lista de valores.")**) tiene un **tipo** que describe cómo almacenarlo en memoria, qué operaciones se pueden aplicar a este objeto y cómo ejecutarlas.

Una analogía de los tipos en el mundo real serían las especies biológicas o cualquier otra característica abstracta compartida por determinados objetos. Por ejemplo, todos los perros que has visto tienen el tipo *perro*, pero cada uno es un objeto individual. Si pensamos en *perro* como un tipo, podemos suponer que hay determinadas operaciones disponibles. Por ejemplo, un perro puede ladrar.

En este tema estudiaremos algunos de los tipos de datos más sencillos y utilizados habitualmente en programación.

## Cadenas de texto

Siempre que quieras utilizar información textual en tu programa, tendrás que trabajar con **cadenas de texto**. En Python, el tipo cadena de texto se denomina `str`. Las cadenas son extremadamente comunes y útiles. Como hemos visto, los [**literales de cadena**](https://hyperskill.org/learn/step/5852 "En Python, un literal de cadena es una secuencia de caracteres delimitada por un par de comillas simples o dobles. No existe diferencia entre ambas, aunque hay convenciones sobre su uso. Para incluir cualquier tipo de comilla dentro de una cadena, puedes utilizar el símbolo de barra invertida () delante de la comilla dentro de la cadena. Esto indica a Python que la comilla que aparece a continuación forma parte de la cadena y no representa su final o su comienzo. Los literales de cadena se pueden utilizar para representar información textual en un programa, como el correo electrónico de una persona o una organización.") pueden delimitarse utilizando comillas simples o dobles.

* Ejemplos de cadenas entre comillas dobles:

```python
print("")               # una cadena vacía
print("string")         # una palabra
print("Hello, world!")  # una frase
```

* Ejemplos de cadenas entre comillas simples:

```python
print('a')                   # un solo carácter
print('1234')                # una secuencia de dígitos
print('Bonjour, le monde!')  # una frase
```

En un programa real, una cadena puede representar el correo electrónico de una persona o de una organización.

```python
print('hello@hyperskill.org')  # imprimir un correo electrónico
```

Como puedes ver, ¡las cadenas son muy fáciles de utilizar!

## Tipos numéricos

Los números son fundamentales para cualquier programador. Es muy difícil escribir un programa que no utilice números, así que vamos a estudiar algunos [**tipos numéricos**](https://hyperskill.org/learn/step/5852 "En Python, los tipos numéricos son una categoría de tipos de datos que representan y gestionan valores numéricos. Se dividen a su vez en varios subtipos, entre ellos: 1. Enteros: también conocidos como ints, representan números enteros, ya sean positivos, negativos o cero. El término con signo hace referencia a que el entero puede ser positivo o negativo, a diferencia de un entero sin signo, que solo puede ser positivo o cero. Los enteros con signo se utilizan para contar objetos en el mundo real. 2. Números en coma flotante: representan números reales y tienen una parte decimal. Los números en coma flotante se utilizan para manejar valores numéricos más precisos que requieren decimales. 3. Números complejos: son números con una parte real y una parte imaginaria, representados como a + bi. Cada objeto de datos, como una variable o una constante, tiene un tipo que describe cómo almacenarlo en memoria, qué operaciones se pueden aplicar sobre él y cómo ejecutar dichas operaciones.")**:

* `int` **(**[**enteros con signo**](https://hyperskill.org/learn/step/5852 "En Python, un entero con signo es un tipo de dato numérico que representa números enteros, que pueden ser positivos, negativos o cero. El término con signo hace referencia a que el entero puede ser positivo o negativo, a diferencia de un entero sin signo, que solo puede ser positivo o cero. Los enteros con signo se utilizan para contar objetos en el mundo real y son inmutables, lo que significa que, una vez creados, su valor no puede modificarse. En Python, los enteros con signo son un tipo de dato fundamental y se utilizan ampliamente en programación.")**)**. Se denominan enteros o *ints* y son números positivos, negativos o cero que no tienen parte decimal.
* `float` **(**[**números en coma flotante**](https://hyperskill.org/learn/step/5852 "En Python, un número en coma flotante es un tipo de dato que representa un número real. Se utiliza en cálculos estadísticos y científicos y también puede manejar valores especiales como infinito y Not a Number (NaN). Los números en coma flotante se distinguen de los enteros por la presencia de una parte decimal. Se pueden utilizar para realizar comparaciones y pueden resultar útiles para optimizar algoritmos, como encontrar el valor mínimo y máximo de una lista. Los números en coma flotante son fundamentales para cualquier programador, ya que es muy difícil escribir un programa que no utilice números.")**)**. Se denominan *floats*, representan números reales y tienen una parte decimal.

Puedes empezar a trabajar con un número simplemente mostrándolo:

```python
print(11)    # muestra 11
print(11.0)  # muestra 11.0
```

Aunque `11` y `11.0` representan el mismo número, el primero es un entero y el segundo es un número en coma flotante. La forma más sencilla de distinguirlos es observar la parte decimal. Los números en coma flotante tienen **parte decimal**, mientras que los enteros no. ¡Presta atención!

También puedes utilizar números negativos y ceros:

```python
print(0)      # muestra 0
print(-5)     # muestra -5
print(-1.03)  # muestra -1.03
```

Los números enteros pueden utilizarse para contar objetos del mundo real, mientras que los números en coma flotante son una buena opción para cálculos estadísticos y científicos.

## Mostrar los tipos

También disponemos de una forma de mostrar los tipos de diferentes objetos: utilizar la función `type()`, que forma parte de Python.

```python
print(type('hello'))  # <class 'str'>
print(type("world"))  # <class 'str'>

print(type(100))      # <class 'int'>
print(type(-50))      # <class 'int'>

print(type(3.14))     # <class 'float'>
print(type(-0.5))     # <class 'float'>
```

Como puedes observar en los ejemplos anteriores, la función `type()` indica el tipo de dato del valor proporcionado después de la palabra *class*.

## Resumen

Esperamos que ahora tengas una cierta intuición sobre los [**tipos de datos**](https://hyperskill.org/learn/step/5852 "En Python, un tipo de dato es una clasificación de datos que determina cómo se almacenan en memoria, qué operaciones se pueden realizar sobre ellos y cómo se ejecutan dichas operaciones. Es similar a una especie biológica o a cualquier otra característica abstracta compartida por determinados objetos. Por ejemplo, todos los perros que has visto tienen el tipo perro, pero cada uno es un objeto individual. En Python, los tipos de datos incluyen tipos básicos como las cadenas de texto, los tipos numéricos y los tipos utilizados para mostrar información. Cuando asignas un valor a una variable, Python crea un nuevo objeto, coloca el valor dentro del objeto y, a continuación, crea una referencia desde el nombre de la variable al objeto.")**. Debes recordar los tipos más sencillos, `str`, `int` y `float`, y cómo escribir sus literales. En los siguientes temas aprenderemos las características específicas de cada tipo. Si necesitas conocer el tipo de un objeto, puedes mostrarlo utilizando la función `type()`.

## EJERCICIOS

## Simplemente un entero

Introduce un ejemplo de un objeto `int` sin ningún carácter adicional. Ten en cuenta que no necesitas crear una variable.
**Introduce un texto breve.**
4

## Imprimir una cadena de texto

Imprime la cadena de texto `Supercalifragilisticexpialidocious`.

```python
print("Supercalifragilisticexpialidocious")
```

## Identificación e impresión del tipo de dato

El código siguiente define varias variables, determina e imprime el tipo de dato de cada una. Completa los huecos para que el código funcione correctamente. Ten en cuenta que necesitas una **función**, no una cadena de texto con el nombre del tipo de dato.

**Rellena los huecos con los elementos correspondientes:**

```python
# Define a variable with a string value
data = "Hello, world!"
data_type = type(data)
print("The data is a", data_type)

# Define a variable with an integer value
data = 42
data_type = type(data)
print("The data is an", data_type)

# Define a variable with a float value
data = 3.14
data_type = type(data)
print("The data is a", data_type)
```

## Relaciona los tipos

svg

svg **Informar de un error**

Relaciona los objetos con sus tipos.

**Relaciona los elementos de las columnas izquierda y derecha:**

| Tipo    | Objeto  |
| ------- | ------- |
| `float` | `0.0`   |
| `int`   | `0`     |
| `str`   | `'0.0'` |

## Elige un tipo

En tu programa necesitas el número `99.99`. No necesitas realizar ningún cálculo con él, solo **representarlo y mostrarlo**. ¿Qué tipos de datos puedes utilizar para ello? Hay más de una respuesta correcta.

**Selecciona una o más opciones de la lista:**

* `float` ✅
* `int`
* `str` ✅

## Imprimir un entero

Imprime un `int` con el valor `10`.

**Escribe un programa en Python 3:**

```python
print(10)
```

## El tipo

Escribe un código que muestre el tipo de los tres objetos indicados a continuación (en el orden dado).

```python
"int"
394
2.12
```

Utiliza las funciones `print()` y `type()` para cada uno de estos objetos. Por ejemplo, para el primero utiliza `print(type("int"))`.

**Programa:**

```python
print(type("int"))
print(type(394))
print(type(2.12))
```
