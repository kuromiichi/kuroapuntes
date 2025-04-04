# Programación estructurada y modular

## Contenidos

- [Programación estructurada y modular](#programación-estructurada-y-modular)
  - [Contenidos](#contenidos)
  - [Representación de la información](#representación-de-la-información)
    - [Tipos de datos](#tipos-de-datos)
    - [Clasificación de lenguajes por su manejo de los tipos](#clasificación-de-lenguajes-por-su-manejo-de-los-tipos)
    - [Operaciones](#operaciones)
    - [Variables y constantes](#variables-y-constantes)
  - [Programación estructurada](#programación-estructurada)
  - [Programación modular](#programación-modular)
    - [Funciones](#funciones)
    - [Paso por valor y paso por referencia](#paso-por-valor-y-paso-por-referencia)
    - [Ámbitos de las variables](#ámbitos-de-las-variables)
    - [Paquetes o módulos](#paquetes-o-módulos)
    - [Recursividad](#recursividad)

## Representación de la información

### Tipos de datos

Un programa informático es una colección de instrucciones que se ejecutan en el orden en que se escriben. Su objetivo es transformar un conjunto de datos de entrada en otro conjunto de datos de salida.

Para representar dichos datos, existen los **tipos de datos**. Un tipo define cuánto espacio se debe reservar en memoria para almacenar un dato, y los comportamientos que puede tener.

Existen tipos de datos simples que permiten representar valores primitivos como un número, un carácter, un valor lógico, entre otros.

```python
entero = 10  # Integer
decimal = 3.14  # Double
caracter = 'a'  # Character
logico = True  # Boolean
texto = "Hola, mundo!"  # String
```

También hay tipos de datos compuestos que permiten almacenar un conjunto de datos relacionados, como un array, una lista o un diccionario.

```python
lista = [1, 2, 3]
diccionario = {"a": 1, "b": 2, "c": 3}
conjunto = {1, 2, 3}
```

### Clasificación de lenguajes por su manejo de los tipos

Los lenguajes de programación se pueden clasificar según cómo tratan los tipos de datos.

Respecto a la forma de declarar los tipos:

- Lenguajes de **tipado estático**: este tipo de lenguajes requieren que el tipo de cada variable se declare explícitamente en el código, de tal forma que el compilador o intérprete puedan comprobar que los tipos de las variables sean correcto e invariables. Ejemplos de estos lenguajes son Java, C++, C#, etc.

```java
// Java
int numero = 10; // int es necesario para especificar el tipo
```

- Lenguajes de **tipado dinámico**: a diferencia de los anteriores, estos lenguajes no obligan a las variables a tener un tipo determinado, por lo que el compilador o intérprete se encarga de inferir el tipo de cada variable en base a los datos que almacena. Ejemplos de estos lenguajes son Python, Ruby, JavaScript, etc.

```python
# Python
numero = 10 # no es necesario especificar el tipo
```

Respecto a la forma de operar con los tipos:

- Lenguajes **fuertemente tipados**: estos lenguajes implementan un control muy estricto sobre los tipos de las variables y sus operaciones, impidiendo que cambien de forma implícitamente al interactuar con ellas. Evitan realizar operaciones entre tipos incompatibles y lanzan errores cuando un tipo no puede realizar una operación en tiempo de compilación. Ejemplos de estos lenguajes son Java, Python, C++, etc.

```java
// Java
int numero = 10;
String texto = "Hello, world!";

int resultado = numero + texto; // Error: tipos incompatibles
```

- Lenguajes **débilmente tipados**: estos lenguajes son mucho más flexibles, ya que permiten realizar operaciones entre tipos potencialmente incompatibles y permiten la conversión implícita de los tipos de datos cuando es necesario. Sin embargo, su comportamiento es más impredecible. Ejemplos de estos lenguajes son JavaScript, PHP, Perl, etc.

```javascript
// JavaScript
let numero = 10;
let texto = "Hello, world!";

let resultado = numero + texto; // Resultado: "10Hello, world!"
// El número se convierte en texto de forma implícita
```

### Operaciones

Cada tipo de dato permite realizar una serie de operaciones para transformar y manipular los datos que almacena. A rasgos generales, las operaciones se pueden clasificar en:

- Aritméticas

```python
a = 10
b = 5

suma = a + b
resta = a - b
multiplicacion = a * b
division = a / b
modulo = a % b
```

- Relacionales

```python
a = 10
b = 5

igual = a == b
diferente = a != b
mayor = a > b
menor = a < b
mayor_igual = a >= b
menor_igual = a <= b
```

- Lógicas

```python
a = True
b = False

y = a and b
o = a or b
negacion = not a
```

- Asignación

```python
a = 10
a += 5
a -= 5
a *= 5
a /= 5
a %= 5
```

### Variables y constantes

Para almacenar los datos en memoria, debemos declarar una variable, que es un espacio de memoria que se reserva para almacenar un dato. Las variables son mutables, lo que significa que pueden cambiar su valor en el futuro. Si no queremos que el valor de la variable cambie, podemos declarar una constante, que es una variable que no puede ser modificada.

Para nombrar las variables, debemos seguir las reglas de estilo de cada lenguaje. En Python, las variables se nombrarán usando snake_case, y las constantes usando UPPER_SNAKE_CASE.

```python
variable = 10  # Variable mutable
CONSTANTE = 10  # Variable inmutable
```

## Programación estructurada

La programación estructurada es un paradigma de programación que se basa en la ejecución de un programa de forma secuencial, es decir, en el orden en que se escriben las instrucciones.

Los tres elementos básicos de este paradigma son:

- **Secuencias**: una secuencia de instrucciones que se ejecutan en el orden en que se escriben.

```python
print("Hola, mundo!")
print("Soy un programa estructurado")
nombre = input("Dime tu nombre: ")
print(f"Hola, {nombre}!")
```

- **Condicionales**: una secuencia de instrucciones que se ejecutan si una condición es verdadera, y otra secuencia de instrucciones que se ejecutan si la condición es falsa.

```python
edad = 18

if edad >= 18:
    print("Eres mayor de edad")
else:
    print("Eres menor de edad")

dia_de_la_semana = 1

match dia_de_la_semana:
    case 1:
        print("Lunes")
    case 2:
        print("Martes")
    case 3:
        print("Miércoles")
    case 4:
        print("Jueves")
    case 5:
        print("Viernes")
    case 6:
        print("Sábado")
    case 7:
        print("Domingo")
    case _:
        print("Día no válido")
```

- **Bucles**: una secuencia de instrucciones que se ejecutan mientras una condición es verdadera.

```python
# Bucles definidos
for i in range(1, 11):
    print("Iteración", i)

# Bucles indefinidos
i = 1
while i <= 10:
    print("Iteración", i)
    i += 1
```

También se usan comentarios para explicar el código de manera clara y entendible. Es importante no abusar de ellos, ya que pueden dificultar la lectura del código. El mejor código es aquel que se explica solo.

```python
# Este es un comentario de una línea

"""
Este es un comentario de bloque
Puede abarcar varias líneas
"""
```

## Programación modular

### Funciones

La programación modular amplía sobre los conceptos de programación estructurada y permite dividir el código en diferentes archivos y funciones. Esto permite una mayor organización y mantenibilidad del código.

Una **función** es un bloque de código que realiza una tarea concreta y se puede reutilizar en distintas partes del programa. Mi profe distingue entre funciones y procedimientos pero para el resto de los mortales es irrelevante.

El uso de funciones facilita la legibilidad del código, permite su reutilización y hace más fácil el proceso de resolución de problemas.

Para dividir el código en funciones, es importante saber identificar las subtareas independientes que componen la solución al problema que queremos resolver.

Por ejemplo, el siguiente código escrito siguiendo programación estructurada:

```python
def saludar():
    print("Hola, mundo!")
    print("Soy un programa estructurado")
    nombre = input("Dime tu nombre: ")
    print(f"Hola, {nombre}!")
```

Podemos dividirlo en tres funciones:

```python
def main():
    saludar()
    nombre = preguntar_nombre()
    decir_hola(nombre)

def saludar():
    print("Hola, mundo!")
    print("Soy un programa modular")

def preguntar_nombre():
    nombre = input("Dime tu nombre: ")
    return nombre

def decir_hola(nombre):
    print(f"Hola, {nombre}!")

if __name__ == "__main__":
    main()
```

En este ejemplo, la función `main` es la función principal del programa. Llama a las funciones `saludar`, `preguntar_nombre` y `decir_hola` para realizar las acciones correspondientes.

Hay distintas formas de escribir una función. Por ejemplo, la función `saludar` no tiene ni entrada ni salida de datos, ya que solo imprime un mensaje por pantalla.

La función `preguntar_nombre` tiene una salida de datos (el nombre del usuario), lo que se conoce como el **valor de retorno**. Es necesario declarar el tipo que tendrá este valor.

La función `decir_hola` tiene una entrada de datos (el nombre del usuario), lo que se conoce como el **parámetro de entrada**. Al escribir la función se deben declarar todas las entradas que se vayan a necesitar y el tipo correspondiente.

### Paso por valor y paso por referencia

El paso de parámetros de una función se puede realizar de dos formas: paso por valor y paso por referencia.

En el paso por valor, las variables pasan una copia de su valor a la función, de forma que el valor original no se modifica si cambiase en la función.

En el paso por referencia, las variables pasan la referencia al espacio de memoria que contiene su valor a la función, por lo que los cambios en la función afectan a la variable original.

```python
def main():
    a = 10
    incrementar(a)
    print(a)  # Imprime 10

    lista = []
    agregar_elemento(lista, "Hola")
    agregar_elemento(lista, " Mundo")
    print("".join(lista))  # Imprime "Hola Mundo"

def incrementar(a):
    a += 1

def agregar_elemento(lista, elemento):
    lista.append(elemento)

if __name__ == "__main__":
    main()
```

### Ámbitos de las variables

Al declarar una variable se debe tener en cuenta el ámbito en el que será válida. Por ejemplo, una variable declarada dentro de una función solo podrá ser usada dentro de la misma. Una variable declarada como global (declarada como top-level, es decir, fuera de una función o clase) puede ser usada en cualquier parte del programa.

```python
# Esta variable es global y puede ser usada en cualquier parte del programa
variable_global = 10

def main():
    # Esta variable es local y solo puede ser usada dentro de la función main
    variable_local = 5

    while variable_local > 0:
        # Esta variable es local y solo puede ser usada dentro del bucle while
        variable_while = 3
        variable_local -= 1

    variable_while = 4  # Error: variable_while no es visible fuera del bucle

def otra_funcion():
    variable_local = 25  # Error: variable_local no es visible fuera de la función main
```

### Paquetes o módulos

Un paquete o módulo es un conjunto de clases y funciones que realizan tareas relacionadas. Los paquetes nos permiten organizar el código de manera modular y reutilizable, de forma que no tengamos que volver a escribir el mismo código en distintas partes del programa. Un ejemplo de paquete es aquel que contiene las operaciones matemáticas:

```python
# Paquete o módulo
import math  # Importa todas las funciones matemáticas

print(
    math.sqrt(4.0)  # Esta función se encuentra en el paquete math
)
```

### Recursividad

La recursividad es una técnica de programación que consiste en ejecutar una función dentro de ella misma. Para ello, se debe fijar una condición o un caso base sobre el cual se pueda terminar la ejecución de la misma.

Un ejemplo de problema que se puede resolver con recursividad es el factorial de un número, dado que es igual al propio número más el factorial del número anterior.

```python
def factorial(n):
    if n == 0:
        return 1  # Caso base
    else:
        return n * factorial(n - 1)  # Llamada recursiva
```
