# Programar con números

Los programas en los que no hay nada que calcular son bastante poco frecuentes. Por eso, aprender a programar con números nunca es una mala idea. Una habilidad aún más valiosa que estamos a punto de aprender es el **procesamiento de los datos introducidos por el usuario**. Gracias a ella, puedes crear aplicaciones interactivas y mucho más flexibles. ¡Así que empecemos!

## Lectura de números introducidos por el usuario

Como ya te has familiarizado con la función `input()` de Python, probablemente no sea nuevo para ti que cualquier dato pasado a esta función se trata como una **cadena de texto (`string`)**. Pero ¿cómo debemos trabajar con valores numéricos? Como regla general, se convierten explícitamente a los correspondientes [**tipos numéricos**](https://hyperskill.org/learn/step/5872):

```python
integer = int(input())
floating_point = float(input())
```

Presta atención a las buenas prácticas actuales: es fundamental **no utilizar como nombres de variables los nombres de tipos integrados** de Python, como **`float`** o **`int`**.

También debemos tener en cuenta los errores que puede cometer el usuario: si un usuario introduce un dato incorrecto, por ejemplo, la cadena `'two'` en lugar del número `2`, se producirá un `ValueError`. Por el momento, no nos centraremos en ello, pero no te preocupes: encontrarás más información sobre los errores en un tema específico.

Ahora veamos un ejemplo más detallado y práctico de cómo trabajar con entradas numéricas.

## Millas aéreas gratuitas

Imagina que tienes una tarjeta de crédito con un programa de bonificación de millas aéreas gratuitas (o quizá ya tienes una). Como usuario, se espera que introduzcas la cantidad de dinero que gastas de media al mes con esta tarjeta.

Supongamos que el programa de bonificación te proporciona **2 millas aéreas gratuitas por cada dólar que gastas**. Este es un sencillo programa para calcular cuándo podrás viajar gratis a algún lugar:

```python
# la cantidad media de dinero al mes
money = int(input("¿Cuánto dinero gastas al mes? "))

# el número de millas por unidad monetaria
n_miles = 2

# millas acumuladas
miles_per_month = money * n_miles

# la distancia entre Londres y París
distance = 215

# cuántos meses necesitas para conseguir
# un viaje gratis de ida y vuelta de Londres a París
print(distance * 2 / miles_per_month)
```

Este programa calculará cuántos meses necesitas para poder recorrer la distancia seleccionada y regresar.

Aunque se recomienda escribir mensajes para los usuarios dentro de la función `input()`, **evítalos en nuestros ejercicios de programación educativos**, ya que de lo contrario tu código podría no superar nuestras pruebas.

## Formas avanzadas de asignación

Siempre que utilizas un signo igual `=`, en realidad estás asignando un valor a una variable. Por este motivo, `=` suele denominarse **operador de asignación**.

Sin embargo, existen otros operadores de asignación que puedes utilizar en Python. También se denominan [**operadores de asignación compuesta**](https://hyperskill.org/learn/step/5872), porque realizan una [**operación aritmética**](https://hyperskill.org/learn/step/5872) y una asignación en un único paso.

Observa el siguiente fragmento de código:

```python
# asignación simple
number = 10
number = number + 1  # 11
```

Este código es equivalente al siguiente:

```python
# asignación compuesta
number = 10
number += 1  # 11
```

Como puedes ver claramente en el ejemplo, el segundo código es más conciso, ya que no repite el nombre de la variable.

Naturalmente, existen formas similares de asignación para el resto de las operaciones aritméticas:

```python
-= 
*= 
/=
//=
%=
**=
```

Cuando tengas la oportunidad, utilízalas para ahorrar tiempo y esfuerzo.

A continuación veremos una posible aplicación de la asignación compuesta.

## Variable contador

En programación existe un concepto llamado **bucle** (*loop*). Se utiliza para repetir un bloque de código un determinado número de veces.

Con mucha frecuencia, los bucles utilizan variables especiales llamadas **contadores**.

Un **contador**, como su propio nombre indica, sirve para contar algo: cuántas veces se cumple una condición, cuántos elementos hay en una [**secuencia**](https://hyperskill.org/learn/step/5872), etc.

Por tanto, los contadores deben ser números enteros. Y aquí llegamos al punto importante: puedes utilizar los operadores `+=` y `-=` para aumentar o disminuir el contador, respectivamente.

Considera este ejemplo, en el que el usuario determina el valor en el que se incrementa el contador:

```python
counter = 1
step = int(input())  # introduce 3
counter += step
print(counter)  # debería ser 4
```

Si solo necesitas obtener números enteros no negativos del usuario (después de todo, estamos incrementando el contador), puedes evitar entradas incorrectas utilizando la función `abs()`.

Es una función integrada de Python que devuelve el **valor absoluto** de un número, es decir, su valor independientemente de su signo.

Vamos a modificar un poco nuestro programa anterior:

```python
counter = 1
step = abs(int(input()))  # el usuario introduce -3
counter += step
print(counter)  # sigue siendo 4
```

Como puedes ver, gracias a la función `abs()` hemos obtenido un número positivo.

Por ahora, no pasa nada si todavía no conoces muchos detalles sobre los **errores**, los **bucles** y las **funciones integradas** de Python. Nos pondremos al día y nos aseguraremos de que conozcas estos temas en profundidad. ¡Sigue aprendiendo!

## Resumen

Hemos profundizado en algunos detalles nuevos sobre la **aritmética con números enteros** y el **procesamiento de entradas numéricas** en Python. No dudes en utilizarlos en tus futuros proyectos.

En este tema hemos aprendido:

* cómo leer números introducidos por el usuario;
* cómo asignar números a variables y utilizar operadores aritméticos para asignar el resultado de un cálculo;
* qué son los contadores y cuándo se utilizan.

## Ejercicios

### Cuenta de ahorro

Informa de un error (Report a typo)

Para una cantidad de dinero determinada, calcula los intereses generados por esta cuenta de ahorro con un tipo de interés del 5 % después de un año.

Utiliza la fórmula del interés simple para calcular los ingresos:

![alt text](image.png)

Guarda el resultado en la variable `income`. NO necesitas imprimirlo.

Escribe un programa en Python 3.

```python
amount = 1000
interest_rate = 5
years = 1
# cambia la siguiente linea
income = (amount * interest_rate * years) / 100
```

### ¿Cuándo conseguirás un viaje gratis?

La compañía aérea "Happy travel" tiene un programa de fidelización para sus clientes: por cada dólar gastado, obtienen 0,01 millas gratuitas en su cuenta, que pueden utilizar más adelante para viajar gratis.

A continuación se muestra el código para calcular las millas aéreas gratuitas de un cliente que planea viajar de Londres a París y regresar:

```python
# número de millas aéreas gratuitas por cada dólar gastado
n_miles = 0.01

# cantidad de dinero gastada al mes
money = 2000

# número de millas aéreas gratuitas acumuladas al mes
miles_per_month = money * n_miles

# distancia entre Londres y París ida y vuelta
total_distance = 215 * 2
```

¿Cuál sería la última línea correcta para calcular cuántos meses tardará este cliente en realizar el viaje deseado sin pagar nada?

### Selecciona una opción de la lista

#### Opción 1

```python
total_distance / miles_per_month
```

#### Opción 2

```python
total_distance * 2
```

#### Opción 3

```python
total_distance * miles_per_month
```

#### Opción 4

```python
total_distance * 2 / miles_per_month
```

### Dividir las nueces equitativamente entre las ardillas

N ardillas han encontrado K nueces y han decidido repartirlas equitativamente.

Determina cuántas nueces recibirá cada ardilla e imprime el resultado. La respuesta debe ser un número entero.

Consejo: ¡Presta atención al orden de las variables!

#### Formato de los datos de entrada

Hay dos números positivos, N y K, cada uno de los cuales no es mayor que 10000.

#### Ejemplo de entrada 1

```text
3
14
```

#### Ejemplo de salida 1

```text
4
```

Escribe un programa en Python 3.

```python
N = int(input())
K = int(input())
nueces_por_ardilla = K // N
print(nueces_por_ardilla)
```

### Encubierto

¿Cuál de los siguientes operadores no tiene nada que ver con la asignación compuesta?

#### Opciones de respuesta

1. `==`

2. `//=`

3. `+=`

4. `-=`

5. `**=`

6. `%=`

### La suma de los dígitos

Dado un número entero de tres cifras (es decir, un número entero entre 100 y 999), encuentra la suma de sus dígitos e imprime el resultado.

Por ejemplo, tu programa recibe `476` como entrada. Entonces, debe sumar 4, 7 y 6 e imprimir el resultado.

Para obtener los dígitos por separado del número entero introducido, utiliza los operadores `%` y `//` (por ejemplo, puedes obtener el 8 del número 508 calculando el resto de la división entre 10).

#### Ejemplo de entrada 1

```text
476
```

#### Ejemplo de salida 1

```text
17
```

Escribe un programa en Python 3.

```python
numero = int(input())
centenas = numero // 100
resto = numero % 100
decenas = resto // 10
unidades = resto % 10
suma = centenas + decenas + unidades
print(suma)`
```
