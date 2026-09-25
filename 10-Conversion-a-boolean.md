# Conversión a booleano

## Valores truthy y falsy

Ya sabes que todos los objetos de Python pueden interpretarse como [**valores booleanos**](https://hyperskill.org/learn/step/10327). Los objetos que se evalúan como `True` se denominan [**truthy**](https://hyperskill.org/learn/step/10327), mientras que los objetos que se evalúan como `False` se denominan **falsy**.

Los siguientes valores son *falsy*:

* Algunas constantes: `None` y `False`.
* El cero: `0`, `0.0`, `0j`.
* Contenedores vacíos, como la cadena `""`, la lista `[]` y otros.

Todos los demás objetos se evalúan como `True`.

Esto permite utilizar objetos de cualquier tipo en [**expresiones booleanas**](https://hyperskill.org/learn/step/10327). En este tema aprenderemos cuándo puede resultar útil y cuándo debemos convertir explícitamente los objetos en valores booleanos.

## Comprobación de truthiness

Como hay pocos objetos en Python que se evalúan como `False`, no hay demasiados casos en los que se utilicen valores no booleanos en expresiones lógicas.

Uno de los casos más habituales es comprobar si un contenedor está vacío o no. Vamos a escribir una función que muestre una lista si no está vacía y la cadena `"empty list"` si está vacía.

```python
def print_list(lst):
    if lst:
        print(lst)
    else:
        print('empty list')


print_list([2, 3, 4])  # [2, 3, 4]
print_list([])         # empty list
```

Según **PEP 8**, es preferible escribir `if lst` en lugar de `if len(lst) > 0`, pero debes comprender bien qué objetos pueden pasarse a tu función.

En este ejemplo, si el argumento `lst` resulta ser `None`, la función mostrará `"empty list"`.

Aquí y en el resto de este tema, todos los ejemplos utilizan listas, pero lo mismo se puede aplicar a otros contenedores.

Existe una forma más compacta de implementar la misma función, pero requiere comprender bien cómo funcionan los operadores `and` y `or` con valores no booleanos.

## Operaciones lógicas con valores no booleanos

Ya sabes que, dados dos valores booleanos, `and` devuelve `True` si ambos operandos son `True`, mientras que `or` devuelve `True` si al menos uno de los operandos es `True`.

Cuando los operandos son de un tipo cualquiera, Python puede aplicarles los operadores `and` y `or`, pero el resultado será **uno de los operandos**, en lugar de los valores booleanos `True` o `False`.

Las siguientes tablas muestran qué devuelven los operadores `and`, `or` y `not` dependiendo de si sus operandos son *truthy* o *falsy*.

### Operador `and`

|  **a** |  **b** | **a and b** |
| :----: | :----: | :---------: |
| truthy | truthy |      b      |
| truthy |  falsy |      b      |
|  falsy | truthy |      a      |
|  falsy |  falsy |      a      |

### Operador `or`

|  **a** |  **b** | **a or b** |
| :----: | :----: | :--------: |
| truthy | truthy |      a     |
| truthy |  falsy |      a     |
|  falsy | truthy |      b     |
|  falsy |  falsy |      b     |

### Operador `not`

|  **a** | **not a** |
| :----: | :-------: |
| truthy |  `False`  |
|  falsy |   `True`  |

Ahora podemos implementar la función `print_list()` en una sola línea:

```python
def print_list(lst):
    print(lst or 'empty list')


print_list([2, 3, 4])  # [2, 3, 4]
print_list([])         # empty list
```

Según la segunda tabla, cuando `lst` no está vacía, es decir, es *truthy*, el operador `or` devuelve el primer operando (la propia lista). Cuando `lst` está vacía, es *falsy*, por lo que `or` devuelve el segundo operando (la cadena en nuestro caso).

Otro aspecto importante es que, cuando el primer operando determina por sí solo el resultado de la operación, Python **no evalúa el segundo operando**.

Esto ocurre cuando:

* el primer operando de `and` es *falsy*;
* el primer operando de `or` es *truthy*.

Por ejemplo, si queremos comprobar que la lista `lst` no está vacía y que su primer elemento es positivo, podemos escribir:

```python
if lst and lst[0] > 0:
    ...
```

Si `lst` está vacía, la expresión `lst[0] > 0` no sería válida, pero no provoca una excepción porque **nunca llega a evaluarse**.

## Función `bool()`

Aunque podemos utilizar cualquier objeto en expresiones booleanas, hay situaciones en las que necesitamos convertir explícitamente los objetos en valores booleanos reales.

Esto se puede hacer mediante la función `bool()`.

La función `bool()` devuelve `True` si el argumento proporcionado es *truthy* y `False` si es *falsy*.

```python
print(bool(True), bool(False))    # True False
print(bool(None))                 # False
print(bool([]), bool([2, 3, 9]))  # False True
```

Esta función no se utiliza con mucha frecuencia, pero hay casos específicos en los que puede resultar útil.

## ¿Cuándo utilizar la función `bool()`?

A veces necesitas **guardar el resultado de una expresión lógica** o incluso escribirlo en un archivo. En ese caso, querrás obtener `True` o `False`, y no simplemente un objeto *truthy* o *falsy*.

Veamos un ejemplo. Tenemos una lista de listas con valores enteros. Queremos comprobar, para cada lista interna, si la lista no está vacía y si su primer elemento no es cero.

La solución es:

```python
def check_list(lst):
    return lst and lst[0]


lists = [[5, 9], [0, 0], []]
result = []
for lst in lists:
    result.append(check_list(lst))

print(result)  # [5, 0, []]
```

Aunque `5` es un valor *truthy* y `0` y `[]` son valores *falsy*, probablemente prefieras obtener una lista formada por valores booleanos reales:

```python
result = [True, False, False]
```

Por tanto, debes convertir explícitamente el resultado de la función en un valor booleano:

```python
def check_list(lst):
    return bool(lst and lst[0])


lists = [[5, 9], [0, 0], []]
result = []
for lst in lists:
    result.append(check_list(lst))

print(result)  # [True, False, False]
```

Cuando **no necesitas guardar el resultado** de una expresión lógica, no es necesario utilizar `bool()`.

Por ejemplo, esto:

```python
if lst:
```

es más legible que:

```python
if bool(lst):
```

## Resumen

* Todos los objetos de Python pueden interpretarse como valores booleanos.
* Algunos operadores booleanos, como `and` y `or`, devuelven uno de los operandos como resultado; `not`, por el contrario, siempre devuelve un valor booleano.
* Está bien utilizar la comprobación de *truthiness* para comprobar si un contenedor está vacío, pero hay que hacerlo con cuidado.
* Cuando quieres **guardar el resultado de una operación lógica**, y no simplemente comprobar si es verdadera o falsa, debes convertirlo explícitamente en un valor booleano mediante la función `bool()`.

## Ejercicios

### Punto fijo

Encuentra un valor `x` tal que, cuando Python lo convierte a un valor booleano mediante `bool(x)`, el resultado sea igual al propio `x`.

En otras palabras, `x` es un punto fijo de la función `bool()` si la expresión `bool(x) == x` se evalúa como `True`.

No escribas `bool()` en tu respuesta; proporciona únicamente el valor de `x`.

Introduce un texto breve.

Solución: `True`

### Corrige un error

El código siguiente resuelve el problema de comprobar si una fracción es igual a `0.5`, dados el numerador y el denominador.

El programa debe imprimir `True` o `False`. Si el denominador es igual a `0`, el resultado debe ser `False`.

```Python
def compare(numerator, denominator):
    return denominator and numerator / denominator == 0.5


a = int(input())
b = int(input())

print(compare(a, b))
```

Sin embargo, este código funciona incorrectamente. Encuentra y corrige el error y, a continuación, ejecuta el código.

#### Ejemplo de entrada 1

```text
5
10
```

#### Ejemplo de salida 1

```text
True
```

#### Ejemplo de entrada 2

```text
3
0
```

#### Ejemplo de salida 2

```text
False
```

#### Ejemplo de entrada 3

```text
-1
-2
```

#### Ejemplo de salida 3

```text
True
```

Escribe un programa en Python 3.

#### Solución

El error está en que, cuando `denominator` es `0`, la expresión `denominator and ...` devuelve `0`, en lugar de `False`.

Para garantizar que el resultado sea siempre un booleano, podemos utilizar una condición explícita:

```python
def compare(numerator, denominator):
    return denominator != 0 and numerator / denominator == 0.5


a = int(input())
b = int(input())

print(compare(a, b))
```

La expresión `denominator != 0` devuelve `False` cuando el denominador es cero y `True` en caso contrario. Así, la función devuelve siempre `True` o `False`.

### Saluda

Es habitual saludar a los usuarios después de que se registren en tu sitio web.

En este ejercicio, debes implementar una función que reciba una cadena `name` como argumento e imprima `"Hello, NAME!"`, donde NAME se sustituye por el nombre del usuario.

Sin embargo, algunos usuarios pueden preferir no revelar su nombre, por lo que `name` puede ser una cadena vacía. En ese caso, tu programa debe imprimir `"Hello, Anonymous!"`.

Tu programa no debe leer ninguna entrada ni llamar a la función; únicamente debes implementarla.

#### Ejemplo de entrada 1

```text
Eve
```

#### Ejemplo de salida 1

```text
Hello, Eve!
```

#### Ejemplo de entrada 2

```text
```

#### Ejemplo de salida 2

```text
Hello, Anonymous!
```

Escribe un programa en Python 3.

**Solución**

```python
def say_hello(name):
    if name == "":
        print("Hello, Anonymous!")
    else:
        print("Hello, " + name + "!")
```

La función comprueba si `name` está vacío. Si lo está, imprime el saludo anónimo; en caso contrario, utiliza el nombre recibido.

### Valores falsy

Selecciona todos los valores falsy (considerados falsos) en Python.

Selecciona una o varias opciones de la lista:

1. `0`

2. `[None]`

3. `""`

4. `"False"`

Solución correcta:

* `0`

* `""`

Explicación:

* `0`: es un valor falsy porque es el número cero.

* `[None]`: es una lista no vacía, por lo que es truthy (`True`).

* `""`: es una cadena vacía, por lo que es falsy.

* `"False"`: es una cadena no vacía, por lo que es truthy (`True`).

### Encuentra la contraseña

Imagina que eres un hacker y has conseguido acceder a un servidor web escrito en Python. El problema es que te pide una contraseña que no conoces.

Sin embargo, este servidor es de código abierto, por lo que sabes que existe una función `wrong_password()` que recibe una contraseña y la comprueba con `real_password`.

```python
def wrong_password(password):
    return (password == "" or (not password and real_password)) or password != real_password
```

No puedes acceder a la variable `real_password`, pero puedes llamar a la función `wrong_password()` y explotar su vulnerabilidad para obtener la contraseña.

Escribe tu código dentro de la función `solve()`. Piensa en un argumento que puedas pasar a la función `wrong_password()` para que esta devuelva el valor de `real_password`.

Imprime el resultado de la función `wrong_password()`.

Tu programa no debe leer ninguna entrada ni llamar a la función `solve()`. Tu tarea consiste únicamente en implementarla.

Consejo: Recuerda que los operadores `and` y `or` devuelven uno de sus operandos. Consulta las tablas que muestran qué operandos devuelven los operadores en los distintos casos.

Escribe un programa en Python 3.

**Solución**

```python
def solve():
    print(wrong_password(None))
```

Explicación:

Al pasar `None`:

* `password == ""` es `False`.

* `not password` es `True`, por lo que `not password and real_password` devuelve `real_password`.

* La expresión completa devuelve `real_password`, porque el operador `or` devuelve el primer operando verdadero.

Por tanto, `wrong_password(None)` devuelve la contraseña real sin necesidad de conocerla previamente.

