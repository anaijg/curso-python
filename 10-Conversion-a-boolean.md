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

### Valores booleanos

Suponiendo que las variables tienen los siguientes valores booleanos:

```text
a = True
b = False
c = a and not b
```

Introduce el resultado de evaluar la expresión:

```text
a and (not c or b)
```

#### Solución

```text
False
```

Explicación:

1. `c = True and not False` → `c = True`.

2. `not c` → `False`.

3. `not c or b` → `False or False` → `False`.

4. `a and False` → `True and False` → `False`.

### Valores booleanos

Suponiendo que las variables tienen los siguientes valores booleanos:

```text
a = True
b = not a
```

Introduce el resultado de evaluar la expresión:

```text
not (a and b)
```

Pista: En Python, los valores booleanos `True` y `False` comienzan con mayúscula. Por tanto, ¡la respuesta distingue entre mayúsculas y minúsculas!

#### Solución

```text
True
```

### Falso en Python

Elige todos los valores falsy (considerados falsos). Un valor falsy es un valor que se considera falso cuando se evalúa en un contexto booleano.

Consejo: ¡Estamos seguros de que las secuencias vacías se evalúan como `False`!

Selecciona una o varias opciones de la lista:

1. `False`

2. `"False"`

3. `""`

4. `"0"`

5. `0`

Solución correcta: `False`, `""` y `0`.

* `False`: es el valor booleano falso.

* `""`: es una cadena vacía.

* `0`: es el número cero.

Las cadenas `"False"` y `"0"` son cadenas no vacías, por lo que se consideran verdaderas (`True`) en Python.

### Cuando lo soleado se encuentra con lo lluvioso: un giro lógico

Enunciado

Dado el siguiente fragmento de código Python:

```text
is_raining = True
```

y

```text
is_sunny = False
```

¿Cuál será el resultado de evaluar la expresión?

```text
not is_raining and is_sunny
```

Selecciona una opción de la lista:

* `True`

* `None`

* `False`

* `Error`

Solución correcta: `False`

Explicación:

1. `is_raining` es `True`, por lo que `not is_raining` es `False`.

2. `is_sunny` es `False`.

3. La expresión `False and False` devuelve `False`.

En Python, el operador `and` devuelve `True` únicamente cuando ambos operandos son verdaderos.

### Tipo booleano

¿Qué valores se consideran booleanos en Python?

Selecciona una o varias opciones de la lista:

1. `"True"`

2. `True`

3. `0`

4. `False`

5. `None`

6. `1`

Solución correcta:

* `True`

* `False`

Explicación: En Python, los únicos valores del tipo booleano (`bool`) son `True` y `False`. Aunque `0` y `1` pueden utilizarse en contextos booleanos, son valores de tipo entero (`int`).

### Prioridad

Ordena las operaciones booleanas de mayor a menor prioridad.

Coloca los elementos en el orden correcto:

1. `not`

2. `and`

3. `or`

Solución correcta (de mayor a menor prioridad):

1. `not` — Negación

2. `and` — Conjunción (Y)

3. `or` — Disyunción (O)

