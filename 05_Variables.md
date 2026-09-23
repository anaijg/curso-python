# Variables
Puedes utilizar un lenguaje de programación como Python para realizar cálculos o trabajar con valores [**constantes**](https://hyperskill.org/learn/step/5859 "En Python, una constante es un tipo de variable que, una vez que se le asigna un valor, no puede reasignarse. Sin embargo, Python no proporciona compatibilidad integrada para las constantes y los nombres de las variables no se imponen como constantes. En su lugar, los programadores utilizan convenciones de nomenclatura para indicar que una variable debe tratarse como una constante. En el contexto del texto, se habla de dos constantes concretas, `inf` y `-inf`, que representan el infinito positivo y negativo, respectivamente. Estas constantes forman parte del sistema de aritmética de números en coma flotante y siguen las mismas reglas que otros números en coma flotante. Se pueden utilizar en operaciones aritméticas y permiten optimizar algoritmos y encontrar los valores mínimo y máximo de una lista de valores.") como las cadenas de texto. Pero ¿es suficiente? Cuando escribes programas reales, normalmente necesitas **almacenar valores** o resultados de evaluaciones en la memoria del ordenador.

## ¿Qué es una variable?

Una **variable** es un espacio con nombre donde puedes almacenar un valor para acceder a él posteriormente. Imagina una caja donde guardas algo. Esa caja es una variable.

Por ejemplo, calculas un resultado y quieres volver a utilizarlo en otro lugar. En este caso, puedes utilizar una caja de este tipo para guardar el resultado y ahorrar tiempo.

En general, es una buena práctica dar a una variable un nombre que describa su contenido.

## Definir una variable y asignar valores

Puedes almacenar prácticamente cualquier cosa en las variables asignando un valor a una variable con nombre mediante el signo igual. Según [PEP 8](https://www.python.org/dev/peps/pep-0008/#whitespace-in-expressions-and-statements), utilizar un espacio antes y después del signo de asignación se considera una buena práctica.

```python
day_of_week = "Monday"
```

Ahora tienes el valor de cadena `"Monday"` almacenado en la memoria del ordenador. Puedes recuperar el valor utilizando el [**nombre de la variable**](https://hyperskill.org/learn/step/5859 "En Python, un nombre de variable es un identificador único asignado a una variable, que se utiliza para hacer referencia a una ubicación de memoria donde se almacena un valor. Elegir cuidadosamente los nombres de las variables es fundamental para escribir código claro y comprensible, ya que los programadores a menudo necesitan leer y comprender código escrito por otras personas. La guía de estilo de Python, PEP 8, proporciona reglas para nombrar variables, como utilizar letras minúsculas con guiones bajos para separar palabras y evitar palabras reservadas. Además, es una buena práctica elegir nombres de variables que reflejen con precisión su propósito y uso en el código.").

```python
print(day_of_week)  # Monday
```

`day_of_week` almacena un valor de tipo `str`.

```python
print(type(day_of_week))  # <class 'str'>
```

Siempre puedes asignar un nuevo valor a una variable ya definida.

```python
day_of_week = "Tuesday"
```

Ahora recuperarás otro valor:

```python
print(day_of_week)  # Tuesday
```

Es posible asignar el valor de una variable a otra variable:

```python
a = 10
b = a  # b is 10
```

Si no has definido una variable dentro del [**ámbito (scope)**](https://hyperskill.org/learn/step/5859 "En Python, un ámbito hace referencia a la visibilidad o accesibilidad de una variable dentro del código. Cuando se define una variable, puede ser global o local. Una variable global se define en el nivel superior del módulo y puede ser accesible desde cualquier bloque de código del programa, lo que resulta útil para compartir información de estado o configuración entre diferentes funciones. Las variables locales, por otro lado, solo son visibles dentro del ámbito más cercano y no se pueden acceder desde fuera de él. La palabra clave 'global' se utiliza para declarar una variable como global, lo que permite acceder a ella y modificarla desde dentro de una función. De forma predeterminada, las variables creadas dentro de una función son locales y no se pueden acceder desde fuera de ella.") de tu código, aparecerá un error cuando intentes utilizarla:

```python
print(month_name)  # NameError: name 'month_name' is not defined
```

Python permite asignar valores de diferentes tipos a una misma variable. Vamos a asignar el nombre de un mes a una variable y mostrar su tipo.

```python
month = "December"
print(type(month))  # <class 'str'>
```

Ahora vamos a asignar a la variable el número correspondiente a ese mes y volveremos a mostrar su tipo.

```python
month = 12
print(type(month))  # <class 'int'>
```

Esta asignación funciona porque Python es un lenguaje con [**tipado dinámico**](https://hyperskill.org/learn/step/5859 "En Python, el tipado dinámico es una característica mediante la cual el tipo de una variable se determina durante la ejecución, en lugar de hacerlo durante la compilación. Esto significa que el tipo de una variable puede cambiar a lo largo de la ejecución de un programa. Por ejemplo, puedes almacenar un entero en una variable y posteriormente almacenar una cadena de texto en esa misma variable. Esto es diferente de los lenguajes con tipado estático, donde el tipo de una variable se determina durante la compilación y no puede cambiar durante la ejecución del programa. Es importante señalar que, aunque Python tiene tipado dinámico, también tiene tipado fuerte, lo que significa que las variables no pueden cambiar de tipo accidentalmente. Sin embargo, es posible convertir explícitamente variables de un tipo a otro mediante la conversión de tipos.")**.

No abuses del tipado dinámico. Si tu código es largo, podrías olvidar que has cambiado el tipo de una variable. ¡Esta es una causa habitual de errores!

## Reglas para nombrar variables

Como hemos mencionado anteriormente, cada variable tiene un nombre que la distingue de las demás. Hay algunas reglas para nombrar variables que debes seguir:

* Los nombres distinguen entre mayúsculas y minúsculas (`month` no es lo mismo que `Month`).
* Un nombre comienza por una letra o un guion bajo, seguido de letras, dígitos o guiones bajos (por ejemplo, `user_name`, `score1`, `_count`).
* Un nombre no puede comenzar por un dígito (por ejemplo, `2q` no es válido).
* Un nombre no puede ser una palabra clave.

No incumplas estas reglas; de lo contrario, tu programa no funcionará.

## Conclusión

En este tema hemos aprendido qué son las variables en Python. También hemos visto cómo definirlas, asignarles valores y cuáles son las reglas para nombrarlas. ¡Esperamos que estos nuevos conocimientos te ayuden en tu camino para aprender Python!

## ¡Adivina el tipo!

Si ejecutamos el siguiente código, ¿qué tipo de dato se almacenará en la variable `b`?

```python
a = "Tuesday"
b = 10
a = b
b = a
```

En otras palabras, si ejecutamos `print(type(b))` después de ejecutar el código, ¿qué tipo se mostrará?

**Selecciona una opción de la lista:**

* `str`
* `None` (Python producirá un error porque hemos intentado asignar un valor `int` a una variable de tipo cadena)
* `int` ✅
* `None` (la variable no estará definida)
* `float`

## Definir una cadena de texto

Crea una variable `holiday` con el valor `Cinnamon Roll Day`, que debe ser una cadena de texto.

**Escribe un programa en Python 3:**

```python
holiday = "Cinnamon Roll Day"
```
## Calcular e imprimir el cubo de un número entero

Se te propone una tarea sencilla: declarar una variable que sea igual al valor del **cubo del número entero proporcionado**. Después, muestra el valor de la variable resultante.

**Entrada de ejemplo 1:**

```text
5
```

**Salida de ejemplo 1:**

```text
125
```

**Entrada de ejemplo 2:**

```text
3
```

**Salida de ejemplo 2:**

```text
27
```

**Escribe un programa en Python 3:**

```python
# Empieza solicitando un número entero al usuario

n = int(input())

# Ahora necesitas calcular el cubo del número entero proporcionado. El cubo de un número se puede calcular
# multiplicando el número por sí mismo dos veces. En Python, podemos escribirlo como: number * number * number
# Después de obtener el cubo, asígnalo a una variable.
cube = n * n * n

# Finalmente, muestra el cubo calculado del número entero proporcionado utilizando la función print.
print(cube)
```

## Inicializar y mostrar diferentes tipos de datos

Dado un fragmento de código en Python en el que se inicializan diferentes tipos de datos básicos, como cadenas de texto, enteros, números en coma flotante y booleanos, en distintas variables, debes mostrar todos estos datos. Sin embargo, faltan algunas partes del programa. Tu tarea consiste en completar los huecos para que el código se ejecute correctamente sin producir excepciones ni errores.

Las variables booleanas solo pueden tener un valor: `True` o `False`. Las cadenas de texto en Python solo se pueden concatenar con otras cadenas, por lo que todos los valores deben convertirse a cadenas antes de concatenarlos.

**Rellena los huecos con los elementos correspondientes:**

```python
# Variables in python
name = "John"  # String variable
age = 20  # Integer variable
gpa = 3.9  # Float variable
is_student = False  # Boolean variable

# Prints all the data in string format
print("Name: " + name)
print("Age: " + str(age))
print("GPA: " + str(gpa))
print("Is student: " + str(is_student))
```

## Mostrar variables con un formato específico

Supongamos que tienes tres variables: `name` (`str`), `age` (`int`) e `is_graduated` (`bool`). Debes mostrar estas variables de la siguiente manera: `"Name: "` seguido del nombre, `"Age: "` seguido de la edad y `"Graduated: "` seguido del estado de graduación. Completa los huecos del código para conseguirlo.

**Rellena los huecos con los elementos correspondientes:**

```python id="qj3x8s"
name = "John Doe"
age = 25
is_graduated = True
print("Name: " + name)
print("Age: " + str(age))
print("Graduated: " + str(is_graduated))
```

## ¡Crea un número!

Define una variable numérica con el nombre `number` y el valor `10`. Ten en cuenta que **no debes mostrarla por pantalla**.

**Escribe un programa en Python 3:**

```python
number = 10
```

