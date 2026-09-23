# Capturando la entrada por teclado

A veces los programas necesitan interactuar con los usuarios, ya sea para recibir algunos datos o para proporcionar algún tipo de resultado. Y es aquí cuando la función `input()` se lleva todo el protagonismo.

## Lectura de datos introducidos por el usuario

Los datos de entrada que queremos obtener no son más que algún valor introducido por el usuario. La función `input()` lee este valor y lo devuelve al programa como una cadena de texto (`string`). Por ejemplo, el siguiente programa lee el nombre del usuario y muestra un saludo.

```python
user_name = input()
print('Hello, ' + user_name)
```

En la primera línea, el programa esperará a que el usuario introduzca algo como entrada. Asignaremos esta entrada a una variable para guardarla y utilizarla posteriormente. En la segunda línea, el programa añade el nombre introducido al final de la cadena `'Hello, '` y muestra la frase completa como resultado.

Si el usuario introduce `Sauron`, el programa mostrará:

```python
Hello, Sauron
```

Por tanto, el programa muestra un resultado que depende de la entrada del usuario (el nombre).

## Mensajes claros

Es muy recomendable indicar claramente qué tipo de entrada esperamos de nuestros usuarios. Para ello, la función `input()` puede recibir un argumento opcional, es decir, un mensaje:

```python
user_name = input('Please, enter your name: ')
print('Hello, ' + user_name)
```

El programa comienza, el usuario ve el mensaje, introduce su nombre y obtiene el siguiente resultado:

```text
Please, enter your name: Sauron
Hello, Sauron
```

Otra forma de hacerlo es mostrar el mensaje por separado:

```python
print('Enter your name: ')
user_name = input()
print('Hello, ' + user_name)
```

En realidad, no hay una gran diferencia: en el ejemplo anterior, la entrada se mostrará en la misma línea que el mensaje, mientras que en este caso se introducirá en la línea siguiente. Por tanto, puedes elegir la forma que prefieras.

Aunque se recomienda mostrar mensajes a los usuarios, **evítalos en nuestros ejercicios de programación educativos**, ya que de lo contrario tu código podría no superar nuestras pruebas.

## Detalles importantes

Vamos a profundizar en algunos detalles.

En primer lugar, ¿cuánto puede durar la entrada del usuario y cómo sabe el programa que la persona ha terminado de introducir todo lo que quería? Hay algo importante sobre la función `input()`: en cuanto el programa empieza a ejecutar esta función, se detiene y espera a que el usuario introduzca un valor y **pulse Enter**. Esto también significa que, si no hay ninguna entrada del usuario, el programa no continuará ejecutando las instrucciones siguientes.

¿Qué más debes recordar? Esto: **cualquier valor que introduzcas, la función lo considera una cadena de texto (`string`)**. No importa si introduces dígitos o letras; la entrada se convertirá en una cadena.

Si quieres que una entrada sea un **número**, debes indicarlo explícitamente:

```python
print("What's your favorite number?")
value = int(input())  # now value keeps an integer number
```

Sin embargo, ten cuidado: en estas circunstancias, si el usuario introduce un valor que no es un entero, aparecerá un `Error`.

Para leer varias entradas, debes llamar a la función más de una vez:

```python
day = int(input())  # 4
month = input()     # October
```

¡Genial! ¿Por qué esta fecha? Es sencillo:

```python
print('Cinnamon roll day is celebrated on', month, day)
# Cinnamon roll day is celebrated on October 4
```

## Conclusión

¡Enhorabuena! Ahora sabes cómo trabajar con `input()`, una función que te permite interactuar con el usuario. Créenos, es algo que sin duda apreciarás cuando programes.

Esto es lo que has aprendido:

* No hay un límite para la longitud de los datos de entrada; la función esperará hasta que el usuario pulse **Enter**.
* Puedes añadir un mensaje al usuario junto con la solicitud de entrada.
* La función interpreta cualquier valor introducido como una **cadena de texto (`string`)**.
* Los datos de entrada pueden convertirse posteriormente al tipo de datos que necesites.

Puedes leer más sobre este tema en [Qué es el *data scraping* y cómo hacerlo correctamente](https://hyperskill.org/blog/post/what-is-data-scraping-and-how-to-do-it-right), en el blog de Hyperskill.

## Probando la entrada de datos

Veamos cómo funciona. Copia el siguiente código y pégalo debajo. Después, **cambia** una de las líneas para que el programa muestre cualquier dato que introduzca el usuario **sin realizar ninguna operación sobre él**.

```python
data = ...
print(data)
```

**Ejemplo de entrada 1:**

```text
10
```

**Ejemplo de salida 1:**

```text
10
```

Escribe un programa en Python 3.

### Solución

```python
data = input()
print(data)
```

## Calcular el año de nacimiento a partir de la edad actual

Escribe un programa que reciba como entrada la edad de una persona y muestre el año en que nació. Supón que el año actual es **2023**.

El programa debe:

* Recibir como entrada la edad actual del usuario (un número entero).
* Calcular el año de nacimiento restando su edad al año actual.
* Mostrar como salida el año de nacimiento calculado.

**Ejemplo de entrada 1:**

```text
25
```

**Ejemplo de salida 1:**

```text
1998
```

**Ejemplo de entrada 2:**

```text
50
```

**Ejemplo de salida 2:**

```text
1973
```

Escribe un programa en Python 3.

### Solución

```python
# Introduce la edad actual del usuario
current_age = int(input())

# Año actual
current_year = 2023

# Calcula el año de nacimiento
birth_year = current_year - current_age

# Muestra el año de nacimiento
print(birth_year)
```

## En una sola línea

A veces, en los programas, no quieres crear variables adicionales, sino utilizar directamente el resultado de la función `input()` como argumento de otras funciones. Vamos a crear un programa de una sola línea en el que nos presentamos a nuestro programa y este se presenta a nosotros.

Completa los huecos para que la ejecución del programa pueda ser así:

```text
Your name: > Alex
Bot name: > Bob
Hello, Alex! I'm Bob!
```

**Rellena los huecos con los elementos correspondientes.**

```python
print("Hello, " + input("Your name: > ") + "! I'm " + input("Bot name: > ") + "!")
```

La clave es utilizar `input()` directamente dentro de la expresión, sin necesidad de crear variables adicionales.
