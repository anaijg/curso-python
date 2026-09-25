# Operaciones con booleanos

## Tipo booleano

En los lenguajes de programación, el tipo **booleano**, o lógico, es una forma habitual de representar algo que solo puede tener dos estados opuestos, como *encendido* o *apagado*, *sí* o *no*, etc. Es un tipo muy útil que comprobarás rápidamente cuando empieces a trabajar en tus proyectos o incluso cuando escribas pequeños programas.

En este tema veremos el [**tipo booleano**](https://hyperskill.org/learn/step/6025) en Python y aprenderemos a utilizarlo. 

## Tipo booleano

El tipo **Boolean**, o simplemente `bool`, es un tipo de dato especial que solo puede tener dos valores: `True` y `False`. En Python, los nombres de los [**valores booleanos**](https://hyperskill.org/learn/step/6025) comienzan con mayúscula. 

Si estás escribiendo una aplicación que controla las aperturas de una puerta, resulta natural utilizar `bool` para almacenar el estado actual de la puerta:

```python
is_open = True
is_closed = False

print(is_open)    # True
print(is_closed)  # False
```

## Operaciones booleanas

En Python existen tres operadores booleanos integrados:

* `and`
* `or`
* `not`

Los dos primeros son operadores **binarios**, lo que significa que necesitan dos operandos. `not` es un operador **unario**, por lo que siempre se aplica a un único operando. 

### `and`

`and` es un operador binario. Recibe dos argumentos y devuelve `True` si **ambos argumentos son verdaderos**. En caso contrario, devuelve `False`.

```python
a = True and True    # True
b = True and False   # False
c = False and False  # False
d = False and True   # False
```

### `or`

`or` es un operador binario. Devuelve `True` si **al menos uno de los argumentos es verdadero**. En caso contrario, devuelve `False`.

```python
a = True or True    # True
b = True or False   # True
c = False or False  # False
d = False or True   # True
```

### `not`

`not` es un operador unario que **invierte el valor booleano** de su argumento.

```python
to_be = True           # to_be is True
not_to_be = not to_be  # not_to_be is False
```

## Prioridad de las operaciones booleanas

Los [**operadores lógicos**](https://hyperskill.org/learn/step/6025) tienen diferentes prioridades, lo que afecta al orden en que se evalúan. El orden de prioridad es:

1. `not`
2. `and`
3. `or`

Por tanto, primero se evalúa `not`, después `and` y finalmente `or`. 

Por ejemplo:

```python
print(False or not False)  # True
```

Primero se evalúa `not False`, que da `True`. La expresión queda entonces:

```text
False or True
```

El resultado es `True`. 

Esta prioridad será especialmente importante cuando trabajemos con valores denominados **truthy** y **falsy**.

## Valores truthy y falsy

Aunque Python tiene el tipo de datos booleano, a menudo queremos utilizar valores que **no son booleanos** dentro de un contexto lógico.

Python permite comprobar prácticamente cualquier objeto para determinar si se considera verdadero o falso. Cuando se utilizan operadores lógicos, los valores de tipos no booleanos, como enteros o cadenas, se denominan **truthy** o **falsy**, dependiendo de si se interpretan como `True` o `False`. 

Los siguientes valores se evalúan como `False` en Python:

* Las constantes que representan falsedad: `None`, `False`.
* El cero de cualquier tipo numérico: `0`, `0.0`.
* Secuencias y contenedores vacíos: `""`, `[]`, `{}`. 

Cualquier otro valor generalmente se evalúa como `True`.

Por ejemplo:

```python
print(0.0 or False)  # False
print("True" and True)  # True
print("" or False)  # False
```

En general, `and` y `or` pueden recibir cualquier argumento que pueda comprobarse como un valor booleano. 

## Cómo funcionan `and` y `or` con valores no booleanos

Aquí aparece un detalle importante: los operadores `and` y `or` **devuelven uno de sus operandos**, que no tiene por qué ser de tipo booleano. En cambio, `not` siempre devuelve un valor booleano. 

### `and`

`and` devuelve el primer valor si este se evalúa como `False`; en caso contrario, devuelve el segundo valor.

```python
>>> False and True
False

>>> True and True
True

>>> True and False
False
```

### `or`

`or` devuelve el primer valor si este se evalúa como `True`; en caso contrario, devuelve el segundo valor.

```python
>>> True or False
True

>>> False or True
True

>>> True or True
True

>>> False or False
False
```

Por ejemplo:

```python
# `and` has a higher priority than `or`
truthy_integer = False or 5 and 100  # 100
```

Como `and` tiene mayor prioridad que `or`, primero se evalúa:

```python
5 and 100
```

Tanto `5` como `100` son valores **truthy**, por lo que `and` devuelve `100`.

Después queda:

```python
False or 100
```

`or` devuelve `100`, no `True`.

## Uso de paréntesis

Los paréntesis permiten especificar el orden en el que se realizan las operaciones.

Por ejemplo:

```python
tricky = not (False or '')  # True
```

Primero se evalúa:

```python
False or ''
```

La cadena vacía `''` se considera `False`, por lo que `or` devuelve esa cadena vacía.

Después se aplica `not`:

```python
not ''
```

El resultado es `True`.

El operador `not` crea un nuevo valor que, por definición, es de tipo booleano. Por eso, `not` siempre devuelve un valor lógico. 

## Evaluación de cortocircuito

Los operadores lógicos de Python utilizan **evaluación de cortocircuito** (*short-circuit evaluation*). Por este motivo también se denominan **perezosos** (*lazy*).

Esto significa que el segundo operando solo se evalúa si el primero **no es suficiente para determinar el resultado de toda la expresión**. 

Las reglas son:

* `x and y` devuelve `x` si `x` es *falsy*; de lo contrario, evalúa y devuelve `y`.
* `x or y` devuelve `x` si `x` es *truthy*; de lo contrario, evalúa y devuelve `y`. 

Por ejemplo:

```python
# division is never evaluated, because the first argument is True
lazy_or = True or (1 / 0)  # True

# division is never evaluated, because the first argument is False
lazy_and = False and (1 / 0)  # False
```

En el primer caso, `True or ...` ya tiene necesariamente el resultado `True`, por lo que Python **no llega a evaluar** `1 / 0`.

En el segundo caso, `False and ...` ya tiene necesariamente el resultado `False`, por lo que Python tampoco evalúa `1 / 0`.

Esto evita incluso que se produzca el error de división por cero.

## Resumen

En este tema hemos aprendido sobre el **tipo booleano** de Python, sus operaciones (`not`, `and`, `or`) y su prioridad.

También hemos conocido los conceptos de valores **truthy** y **falsy**, así como el motivo por el que los operadores lógicos de Python utilizan **evaluación de cortocircuito**.

Estos son los conceptos básicos de los valores booleanos y las operaciones lógicas en Python, y es muy importante conocerlos desde el principio. 

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

