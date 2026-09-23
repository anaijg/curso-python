# El tipo entero aritmético

En la vida real, realizamos con frecuencia [**operaciones aritméticas**](https://hyperskill.org/learn/step/5865 "En Python, las operaciones aritméticas son cálculos matemáticos que se pueden realizar sobre valores numéricos. Python admite operaciones aritméticas básicas como la suma, la resta, la multiplicación y la división. Existe una diferencia entre la división y la división entera. La primera produce un número en coma flotante, mientras que la segunda produce un valor entero, ignorando la parte decimal. Python genera un error si intentas dividir entre cero. Las operaciones aritméticas se pueden combinar para escribir expresiones más complejas. Por ejemplo, la resta o la división se realizarían de forma similar. El principio fundamental es comprender qué significa una operación concreta para tu objeto y definir después el método correspondiente. Python también dispone de varios métodos para la asignación aumentada, que combina operaciones aritméticas estándar con la asignación. Sus nombres son bastante intuitivos, como `+=` o `-=`. Para números complejos, puedes definir el método correspondiente al operador `+=`, que funcionaría sumando el operando derecho al valor actual del operando izquierdo. Además, puedes comparar objetos mediante operadores de comparación como `<`, `>`, `==`, etc.")**. Nos ayudan a calcular el cambio de una compra, determinar el área de una habitación, contar el número de personas que hay en una cola, etc. Las mismas operaciones se utilizan en los programas.

## Operaciones básicas

Python admite las siguientes operaciones aritméticas básicas:

* suma `+`
* resta `-`
* multiplicación `*`
* división `/`
* división entera `//`

Los siguientes ejemplos muestran cómo funcionan con números enteros:

```python
print(10 + 10)   # 20
print(100 - 10)  # 90
print(10 * 10)   # 100
print(77 / 10)   # 7.7
print(77 // 10)  # 7
```

Existe una diferencia entre la división `/` y la división entera `//`. La primera produce un [**número en coma flotante**](https://hyperskill.org/learn/step/5865 "En Python, un número en coma flotante es un tipo de dato que representa un número real. Se utiliza en cálculos estadísticos y científicos y también puede manejar valores especiales como infinito y NaN (Not a Number). Los números en coma flotante se distinguen de los enteros por la presencia de una parte decimal. Se pueden utilizar para realizar comparaciones y pueden resultar útiles para optimizar algoritmos, como encontrar el valor mínimo y máximo de una lista de valores. Los números en coma flotante son fundamentales para cualquier programador, ya que es muy difícil escribir un programa que no utilice números.")** (como `7.7`), mientras que la segunda produce un valor entero (como `7`), ignorando la parte decimal.

Python genera un error si intentas dividir entre cero.

```text
ZeroDivisionError: division by zero
```

## Escribir expresiones complejas

Las operaciones aritméticas se pueden combinar para escribir expresiones más complejas:

```python
print(2 + 2 * 2)  # 6
```

El orden de cálculo coincide con las reglas de las operaciones aritméticas. La multiplicación tiene un nivel de prioridad superior al de la suma y la resta, por lo que la operación `2 * 2` se calcula primero.

Para especificar un orden de ejecución, puedes utilizar **paréntesis**, como en el siguiente ejemplo:

```python
print((2 + 2) * 2)  # 8
```

Al igual que en las expresiones aritméticas, los paréntesis pueden anidarse unos dentro de otros. También puedes utilizarlos para mejorar la claridad.

El operador menos tiene una forma unaria que niega el valor o la expresión. Un número positivo se convierte en negativo y un número negativo se convierte en positivo.

```python
print(-10)  # -10
print(-(100 + 200))  # -300
print(-(-20))  # 20
```

## Otras operaciones

Además de las operaciones aritméticas básicas, Python admite otros dos operadores de uso frecuente:

* exponenciación `**`
* módulo `%`

**El resto de una división.** El operador módulo `%` de Python se utiliza para obtener el resto de una división. Puede resultar útil cuando quieres comprobar si un número es par. Cuando se aplica a un número y a `2`, devuelve `1` si el número es impar y `0` si es par.

```python
print(7 % 2)  # 1, porque 7 es un número impar
print(8 % 2)  # 0, porque 8 es un número par
```

Aquí tienes algunos ejemplos más:

```python
# Divide el número entre sí mismo
print(4 % 4)     # 0
# Al menos uno de los números es un float
print(11 % 6.0)  # 5.0
# El primer número es menor que el divisor
print(55 % 77)   # 55
# Con números negativos, conserva el signo del divisor
print(-11 % 5)   # 4
print(11 % -5)   # -4
```

Calcular el resto de una división entre `0` también provoca un `ZeroDivisionError`.

El comportamiento de la función módulo cuando dos números tienen signos diferentes puede parecer inesperado al principio. Compara `11 % 5 = 1` y `-11 % -5 = -1` (tanto el dividendo como el divisor tienen el mismo signo) con `11 % -5 = -4` y `-11 % 5 = 4` (tienen signos diferentes).

Para entender por qué funciona de esta manera, debemos mirar qué ocurre "por debajo". En Python, el resto siempre tiene el mismo signo que el divisor, y el operador módulo (`%`) y la división entera (`//`) están relacionados internamente mediante la siguiente expresión:

```python
x == (x // y) * y + (x % y)
```

Podemos reescribirla para obtener la "fórmula" de la división módulo:

```python
(x % y) == x - (x // y) * y
```

Ahora vamos a aplicarla a nuestros ejemplos. Queremos calcular `11 % -5`. Primero calculamos `11 // -5` y el resultado es `-3`. Después aplicamos este resultado a nuestra fórmula y obtenemos `11 % -5 == 11 - (-3) * (-5) == 11 - 15 == -4`.

Para `-11 % 5`, tenemos `-11 % 5 == -11 - (-3) * 5`, cuyo resultado es `4`.

Si quieres comprender mejor esta operación, puedes consultar el tema ["División módulo con números negativos"](https://hyperskill.org/learn/step/13541) de la sección de Matemáticas.

**Exponenciación.** Esta es la forma de elevar un número a una potencia:

```python
print(10 ** 2)  # 100
```

Esta operación tiene una prioridad superior a la multiplicación. Se utiliza habitualmente para calcular cuadrados y cubos:

```python
print(5 ** 2)   # 25
print(2 ** 3)   # 8
```

También la encontrarás en fórmulas:

```python
side = 4
print(side ** 2)   # área de un cuadrado: 16
print(side ** 3)   # volumen de un cubo: 64
```

## Prioridad de las operaciones

En resumen, existe una lista de prioridades para todas las operaciones que hemos estudiado:

1. potencia
2. menos unario
3. multiplicación, división y resto
4. suma y resta

Como hemos mencionado anteriormente, el menos unario cambia el signo de su argumento.

A veces las operaciones tienen la misma prioridad:

```python
print(10 / 5 / 2)  # 1.0
print(8 / 2 * 5)   # 20.0
```

Las expresiones anteriores pueden parecer ambiguas, ya que tienen soluciones alternativas dependiendo del orden de las operaciones: `1.0` o `4.0` en el primer ejemplo, y `20.0` o `0.8` en el segundo. En estos casos, Python sigue la convención matemática de realizar las operaciones de izquierda a derecha. ¡Es algo que conviene conocer, así que intenta tenerlo en cuenta!

## ¡Es hora de PEP!

Hay algunas cosas que debemos mencionar sobre el uso de operadores binarios (es decir, los operadores que actúan sobre ambos operandos). Como sabes, la legibilidad es importante en Python. Por tanto, recuerda primero que debes rodear un operador binario con un único espacio a cada lado:

```python
number=30+12      # ¡No!

number = 30 + 12  # Es mejor así
```

Los **operadores** son símbolos especiales que indican qué operación se debe realizar. Los **operandos** son los valores sobre los que se realiza la operación. Veamos nuestro ejemplo: `30 + 12`. Aquí, `+` es un operador y `30` y `12` son operandos.

Además, a veces se utiliza un salto de línea **después** de los operadores binarios. Sin embargo, esto puede perjudicar la legibilidad de dos maneras:

* los operadores no están alineados en una misma columna;
* cada operador se aleja de su operando y pasa a la línea anterior:

```python
# No: los operadores están alejados de sus operandos
income = (gross_wages +
          taxable_interest +
          (dividends - qualified_dividends) -
          ira_deduction -
          student_loan_interest)
```

Los matemáticos y sus editores siguen la convención opuesta para solucionar este problema de legibilidad. Donald Knuth lo explica en su serie *Computers and Typesetting*: «Aunque las fórmulas dentro de un párrafo siempre se dividen después de las operaciones y relaciones binarias, las fórmulas mostradas siempre se dividen antes de las operaciones binarias». Seguir esta tradición hace que el código sea más legible:

```python
# Sí: es fácil relacionar los operadores con sus operandos
income = (gross_wages
          + taxable_interest
          + (dividends - qualified_dividends)
          - ira_deduction
          - student_loan_interest)
```

En código Python, es **permisible** hacer un salto de línea antes o después de un operador binario, siempre que la convención sea coherente localmente. Para código nuevo, **se recomienda el estilo de Knuth**, según PEP 8.

## Resumen

De acuerdo, hagamos ahora un breve repaso de lo que hemos aprendido en este tema:

* qué operaciones aritméticas básicas admite Python y cómo combinarlas en expresiones más complejas;
* otras operaciones útiles, como el cálculo del resto de una división y la exponenciación;
* la [**prioridad de las operaciones**](https://hyperskill.org/learn/step/5865 "En Python, la prioridad de las operaciones (también conocida como precedencia de operadores) hace referencia a la regla que determina el orden en que se realizan las operaciones en una expresión compleja, en función del tipo de operación. Algunas operaciones, como la potencia y el menos unario, tienen mayor prioridad que otras, como la multiplicación, la división y el resto. Cuando las operaciones tienen la misma prioridad, Python sigue la convención matemática de realizarlas de izquierda a derecha. Los paréntesis se pueden utilizar para modificar la prioridad predeterminada y forzar que una operación concreta se realice primero. Este concepto es importante al escribir expresiones aritméticas complejas en Python.")** en Python;
* cómo escribir expresiones siguiendo PEP 8.

## Una expresión sencilla

Escribe un programa que tome 3 números enteros ***a***, ***b*** y ***c***, calcule ***a*** multiplicado por ***b*** y después reste ***c*** al producto. El programa debe mostrar el resultado.

No es necesario crear las variables; simplemente utilízalas en el código siguiente.

**Entrada de ejemplo 1:**

```text
8
11
63
```

**Salida de ejemplo 1:**

```text
25
```

**Escribe un programa en Python 3:**

```python
a = int(input())
b = int(input())
c = int(input())
print(a * b - c)
```

## Elevar a una potencia

¡Ha llegado el momento de trabajar con números realmente grandes! Calcula el valor entero de `2179` y muestra el resultado.

**Consejo:** presta atención a la sintaxis de tus cálculos para evitar errores.

**Escribe un programa en Python 3:**

```python
print(2 ** 179)
```

## Hagamos algo de matemáticas

¿Cuál es el resultado de la siguiente expresión de Python?

```python
print(((3 + 5) // 2 * 2 ** 3) % 7)
```

Por supuesto, puedes obtener fácilmente la respuesta en un IDE, pero te recomendamos que no lo hagas, ya que el objetivo del ejercicio es que aprendas y recuerdes el orden de prioridad de las operaciones. Por tanto, sigue cuidadosamente los operadores e intenta obtener el resultado por ti mismo.

**Resultado: `4`**

## División entre cero

¿Qué ocurre si divides cualquier número entre cero en Python?

**Selecciona una opción de la lista:**

* `undefined`
* `0`
* `InvalidOperation` exception
* `ZeroDivisionError` exception ✅

## Una expresión compleja

Escribe un programa que reciba un único número entero ***n*** y realice las siguientes operaciones en el orden indicado:

* suma ***n*** consigo mismo;
* multiplica el resultado por ***n***;
* resta ***n*** del resultado;
* divide exactamente el resultado entre ***n*** (es decir, debes realizar una división entera).

Después, muestra el resultado de la división. A continuación se muestra un ejemplo:

* 8 + 8 = 16
* 16 * 8 = 128
* 128 - 8 = 120
* 120 // 8 = 15
* El resultado es 15

La variable ***n*** ya está definida.

**¡Utiliza paréntesis para especificar el orden de ejecución!**

**Entrada de ejemplo 1:**

```text
8
```

**Salida de ejemplo 1:**

```text
15
```

**Solución:**

```python
n = int(input())

print((((n + n) * n) - n) // n)
```

## Todas las operaciones

svg

svg **Informar de un error**

Relaciona cada nombre de una operación matemática con su símbolo correspondiente.

**Relaciona los elementos de las columnas izquierda y derecha:**

| Operación             | Símbolo |
| --------------------- | ------- |
| resta                 | `-`     |
| división              | `/`     |
| multiplicación        | `*`     |
| elevar a una potencia | `**`    |
| suma                  | `+`     |
| división entera       | `//`    |
| resto de la división  | `%`     |

## Una maravilla de la división por cero

Considera el siguiente código de Python:

```python
a = 8
b = 0
c = a / b
print(c)
```

¿Qué ocurrirá al ejecutar este código?

**Selecciona una opción de la lista:**

* **Lanza una excepción `ZeroDivisionError`**
* Muestra `0`
* Muestra `'Division not possible'`
* Imprime un valor infinito

### Respuesta correcta

✅ **Lanza una excepción `ZeroDivisionError`**

En Python, intentar dividir un número entre `0` provoca una excepción `ZeroDivisionError`. El programa se detiene antes de llegar a `print(c)`.

