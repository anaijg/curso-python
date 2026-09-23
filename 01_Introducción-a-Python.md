# Introducción a Python

Python se ha convertido en el lenguaje de referencia para todo tipo de proyectos, desde pequeñas startups hasta gigantes tecnológicos como Google y NASA, ya que permite un desarrollo rápido y ofrece soluciones escalables. Al finalizar este tema, tendrás las habilidades necesarias para leer y escribir tus primeros programas en Python y formar parte de la creciente comunidad mundial de programadores de Python. ¡Empecemos!

## ¿Qué es Python?

Desarrollado por Guido van Rossum en 1991, Python ha ganado popularidad tanto entre principiantes como entre expertos en programación. Su filosofía principal hace hincapié en la legibilidad del código, mientras que su sintaxis permite a los programadores expresar ideas de forma concisa. El nombre del lenguaje procede del programa de humor *Monty Python*, reflejando la intención de su creador de hacer que la programación fuera divertida y accesible.

[Logotipo de Python](https://ucarecdn.com/33368eeb-d6f0-4356-90d4-c5aab4126fbc/)

**Logotipo de Python**

Python se utiliza en una amplia variedad de ámbitos, entre ellos:

* **Desarrollo web** – Con frameworks como Django, FastAPI y Flask, Python es una herramienta potente para crear sitios web dinámicos y API de backend.
* **Ciencia de datos y aprendizaje automático (ML)** – Bibliotecas como NumPy, pandas y TensorFlow convierten a Python en uno de los principales lenguajes para el análisis de datos, el aprendizaje automático y la experimentación con modelos.
* **Inteligencia artificial (IA)** – Python se utiliza ampliamente para crear e integrar aplicaciones basadas en inteligencia artificial, incluidos sistemas basados en grandes modelos de lenguaje.
* **Scripting (automatización de tareas)** – Python se utiliza habitualmente para automatizar tareas, coordinar flujos de trabajo y crear herramientas internas que reducen el trabajo manual.

## ¿Hablas Python?

Dado el énfasis de Python en la sencillez, ya estás preparado para comprender y reproducir programas básicos con facilidad.

Vamos a crear el clásico programa `"Hello, World!"`, un saludo amistoso de tu ordenador:

```python
print("Hello, world!")
```

¡Puedes sustituir la frase que aparece entre paréntesis para crear tu propio programa en Python!

Las funciones y métodos incorporados de Python tienen nombres intuitivos, lo que facilita su comprensión. Así se utiliza `input()` para solicitar datos al usuario:

```python
age = input("How old are you? ")
print("I know, that you're " + age + " years old")
```

El uso de la **indentación** para estructurar el código, en lugar de las llaves `{}` o los puntos y comas utilizados en muchos otros lenguajes, es otra característica que encontrarás sencilla. Observa cómo la indentación ayuda a delimitar los elementos de la [**sentencia if-else**](https://hyperskill.org/learn/step/5204 "En Python, una sentencia if-else es una estructura de programación que permite ejecutar un bloque de código si una condición determinada es verdadera y otro bloque de código si la condición es falsa. La sentencia if va seguida de una expresión booleana que puede tener un valor true o false. Si la condición es verdadera, se ejecuta el bloque de código que aparece inmediatamente después de la sentencia if. Si la condición es falsa, se ejecuta el bloque de código situado bajo la sentencia else. Una indentación correcta es fundamental para que la sentencia if-else funcione correctamente."):

```python
age = input("How old are you? ")
if age > 18:
    print("You're adult")
else:
    print("You're minor")
```

Para facilitar la comprensión del código, también podemos utilizar `#comments`. Estas líneas no se ejecutan y sirven para describir el objetivo del código:

```python
# Define a function that acts like a parrot
# Which repeats the things you say back to you
def parrot():
    answer = input()
    print(answer)

# Call the parrot function
parrot()
```

Por ahora, no necesitas entender cómo funcionan todas estas líneas de código: simplemente aprecia su elegante sintaxis, que no está demasiado alejada del inglés cotidiano. No tengas miedo de experimentar y cometer errores; ¡así es como se aprende!

## Conclusión

¡Bienvenido a la comunidad de Python! Acabas de comenzar tu camino con Python. A medida que avances en el curso que hayas elegido, comenzarás resolviendo pequeños **problemas** relacionados con los temas estudiados. Después aplicarás tus conocimientos en **proyectos**, creando un **portafolio** sólido que muestre tus conocimientos y habilidades a posibles empleadores.

Promovemos el aprendizaje mediante la práctica. Cada fragmento de código, incluso una sola línea, es un paso hacia el dominio de Python. Por eso, te animamos a practicar desde ahora, experimentar, cometer errores y pedir ayuda a la comunidad si te quedas atascado.

## Crear una función para sumar dos números enteros

De vez en cuando, es posible que necesites adaptar el código de otra persona para un propósito diferente. Es en estos casos cuando resulta útil saber leer código. ¡Vamos a intentarlo!

Lee los `#comments` y el código que aparece a continuación y, después, complétalo rellenando los huecos. Puede que todavía no entiendas todas las líneas de código, pero sin duda puedes utilizarlo basándote en tu intuición sobre el lenguaje.

**Rellena los huecos con los elementos correspondientes:**

```python
# Define una función que suma dos números enteros
def add_numbers(num1, num2):
    return num1 + num2

# Llama a la función con dos números enteros y almacena el resultado en una variable
result = add_numbers(3, 4)

# Imprime el resultado en la consola
("La suma de los números es: " + str(result)) 
```
## ¿Es tu cumpleaños?

El siguiente programa pregunta al usuario si hoy es su cumpleaños y muestra un mensaje de felicitación si lo es. Completa los huecos para terminar el programa y no te preocupes por las cosas que todavía no conozcas; las aprenderás más adelante.

**Rellena los huecos con los elementos correspondientes:**

```python
cumple_usuario = input("¿Es hoy tu cumpleaños? ")
if  cumple_usuario== "sí":
    print("¡Feliz cumpleaños!")
```
## La tradición de los programadores

Si hay una tradición que a los programadores les gusta seguir cuando comienzan su camino, es decirle ¡hola al mundo! Completa los huecos para terminar el programa.

**Rellena los huecos con los elementos correspondientes:**

```python
print(Hello, world!)
```
