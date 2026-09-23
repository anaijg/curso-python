# Programas multi-línea

Esperamos que hayas aprendido a escribir programas sencillos de Python de una sola línea que muestran [**texto**](https://hyperskill.org/learn/step/7130 "En Python, un texto se denomina cadena de caracteres o string, que es una secuencia de caracteres utilizada para representar información textual. Las cadenas pueden organizarse en varias líneas, lo que facilita su lectura y comprensión. En el contexto de escribir una lista de nombres en un archivo, cada nombre iría seguido de un carácter de nueva línea, haciendo que cada nombre aparezca en una línea independiente del archivo. Además, Python utiliza secuencias de escape, como el carácter de nueva línea (n) y el retorno de carro (r), para dar formato y manipular cadenas de texto de formas específicas."). Sin embargo, los programas reales contienen muchas líneas: desde decenas o cientos de líneas en pequeños scripts hasta miles e incluso más en proyectos grandes. Por eso, en esta lección escribirás programas que muestran varias líneas.

## Formas de mostrar varias líneas

Veamos un ejemplo. El siguiente código muestra exactamente tres cadenas, cada una en una línea nueva:

```python
print("I")
print("know")
print("Python")
```

La salida es:

```python
I
know
Python
```

Puedes ejecutar este ejemplo utilizando [esta página web](https://repl.it/languages/python3) o localmente si tienes Python instalado en tu ordenador.

Existen diferentes formas de mostrar el texto anterior utilizando una sola llamada a una función. Las veremos en los siguientes temas.

La función `print` también permite mostrar una línea vacía sin especificar ninguna cadena:

```python
print("I")
print()
print("know")
print("")
print("Python")
```

Esta es la salida:

```python
I

know

Python
```

Observa que `print()` y `print("")` producen el mismo resultado.

Sin embargo, dejar una línea en blanco en el código no tendrá ningún efecto.

```python
print("And")

print("you?")
```

La salida del código anterior es:

```text
And
you?
```

## Conclusión

En esta breve lección hemos aprendido a trabajar con textos de varias líneas utilizando `print()`. Ahora es el momento de resolver algunos problemas.

## EJERCICIOS

## Cuenta las líneas vacías

¿Cuántas líneas **vacías** mostrará este código?

```python
print("hello")
print("")
print()

print("bye")
```

La respuesta esperada es un número.

**Introduce un número:** `2`

## ¡Arriba, abajo!

Escribe un programa que muestre el resultado que aparece a continuación. Completa los huecos para terminar el programa.

```text
Up here!


Down there!
```

**Rellena los huecos con los elementos correspondientes:**

```python
print('Up here!')
print()
print()
print('Down there!')
```

## Una semana

Escribe un código que muestre los días de la semana ideales para practicar Python. En otras palabras, muestra todos los días desde el domingo hasta el sábado.

Asegúrate de que cada día comienza con **mayúscula** e incluye **líneas vacías** entre los días, tal y como se muestra en la salida.

**Entrada de ejemplo 1:**

```text
```

**Salida de ejemplo 1:**

```text
Sunday

Monday

Tuesday

Wednesday

Thursday

Friday

Saturday
```

**Escribe un programa en Python 3:**

```python
print("Sunday")
print()
print("Monday")
print()
print("Tuesday")
print()
print("Wednesday")
print()
print("Thursday")
print()
print("Friday")
print()
print("Saturday")
```

## Líneas

¿Cuántas líneas mostrará este código?

```python
print()
print("Monday")
print("Tuesday Wednesday")
print()
print("Thursday")
```

¡Las líneas vacías también cuentan como líneas!

**Introduce un número:** `5`

## Cuadrado

svg

svg **Informar de un error**

Escribe un programa que muestre este cuadrado formado por símbolos `*`. ¡No olvides los **espacios** entre los asteriscos para obtener el cuadrado correctamente!

```text
* * * *
*     *
*     *
* * * *
```

**Escribe un programa en Python 3:**

```python
print("* * * *")
print("*     *")
print("*     *")
print("* * * *")
```
