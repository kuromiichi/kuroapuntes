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

```kotlin
val entero: Int = 10
val decimal: Double = 3.14
val caracter: Char = 'a'
val logico: Boolean = true
val texto: String = "Hola, mundo!"
```

También hay tipos de datos compuestos que permiten almacenar un conjunto de datos relacionados, como un array, una lista o un mapa.

```kotlin
val array: Array<Int> = arrayOf(1, 2, 3)
val lista: List<Int> = listOf(1, 2, 3)
val mapa: Map<String, Int> = mapOf("a" to 1, "b" to 2, "c" to 3)
val conjunto: Set<Int> = setOf(1, 2, 3)
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

```kotlin
val a = 10
val b = 5

val suma = a + b
val resta = a - b
val multiplicacion = a * b
val division = a / b
val modulo = a % b
val aumento = a++
val disminucion = a--
```

- Relacionales

```kotlin
val a = 10
val b = 5

val igual = a == b
val diferente = a != b
val mayor = a > b
val menor = a < b
val mayorIgual = a >= b
val menorIgual = a <= b
```

- Lógicas

```kotlin
val a = true
val b = false

val y = a && b
val o = a || b
val negacion = !a
```

- Asignación

```kotlin
var a = 10
a += 5
a -= 5
a *= 5
a /= 5
a %= 5
```

### Variables y constantes

Para almacenar los datos en memoria, debemos declarar una variable, que es un espacio de memoria que se reserva para almacenar un dato. Las variables son mutables, lo que significa que pueden cambiar su valor en el futuro. Si no queremos que el valor de la variable cambie, podemos declarar una constante, que es una variable que no puede ser modificada.

Para nombrar las variables, debemos seguir las reglas de estilo de cada lenguaje. En Kotlin, las variables se nombrarán usando lowerCamelCase, y las constantes usando UPPER_SNAKE_CASE.

```kotlin
var variable = 10 // Variable mutable
val constante = 10 // Variable inmutable
const val PI = 3.14159 // Constante
```

En Kotlin existe una diferencia entre variables inmutables y constantes propiamente dichas. Generalmente usaremos constantes cuando sean valores que no cambian en el tiempo y se usan en toda la aplicación, y variables inmutables cuando sean valores que se usan en el alcance local de una función.

## Programación estructurada

La programación estructurada es un paradigma de programación que se basa en la ejecución de un programa de forma secuencial, es decir, en el orden en que se escriben las instrucciones.

Los tres elementos básicos de este paradigma son:

- **Secuencias**: una secuencia de instrucciones que se ejecutan en el orden en que se escriben.

```kotlin
fun main() {
    println("Hola, mundo!")
    println("Soy un programa estructurado")
    println("Dime tu nombre: ")

    val nombre = readln()
    println("Hola, $nombre!")
}
```

- **Condicionales**: una secuencia de instrucciones que se ejecutan si una condición es verdadera, y otra secuencia de instrucciones que se ejecutan si la condición es falsa.

```kotlin
fun main() {
    val edad = 18

    if (edad >= 18) {
        println("Eres mayor de edad")
    } else {
        println("Eres menor de edad")
    }

    val diaDeLaSemana = 1

    when (diaDeLaSemana) {
        1 -> println("Lunes")
        2 -> println("Martes")
        3 -> println("Miércoles")
        4 -> println("Jueves")
        5 -> println("Viernes")
        6 -> println("Sábado")
        7 -> println("Domingo")
        else -> println("Día no válido")
    }
}
```

- **Bucles**: una secuencia de instrucciones que se ejecutan mientras una condición es verdadera.

```kotlin
fun main() {
    // Bucles definidos
    for (i in 1..10) {
        println("Iteración $i")
    }

    // Bucles indefinidos
    var i = 0
    while (i < 10) { // La condición se comprueba antes de empezar el bucle
        println("Iteración $i")
        i++
    }

    i = 0
    do {
        println("Iteración $i")
        i++
    } while (i < 10) // La condición se comprueba al final del bucle
}
```

También se usan comentarios para explicar el código de manera clara y entendible. Es importante no abusar de ellos, ya que pueden dificultar la lectura del código. El mejor código es aquel que se explica solo.

```kotlin
// Este es un comentario de una línea

/*
 * Este es un comentario de bloque
 * Puede abarcar varias líneas
 */
```

## Programación modular

### Funciones

La programación modular amplía sobre los conceptos de programación estructurada y permite dividir el código en diferentes archivos y funciones. Esto permite una mayor organización y mantenibilidad del código.

Una **función** es un bloque de código que realiza una tarea concreta y se puede reutilizar en distintas partes del programa. Mi profe distingue entre funciones y procedimientos pero para el resto de los mortales es irrelevante.

El uso de funciones facilita la legibilidad del código, permite su reutilización y hace más fácil el proceso de resolución de problemas.

Para dividir el código en funciones, es importante saber identificar las subtareas independientes que componen la solución al problema que queremos resolver.

Por ejemplo, el siguiente código escrito siguiendo programación estructurada:

```kotlin
fun main() {
    println("Hola, mundo!")
    println("Soy un programa estructurado")
    println("Dime tu nombre: ")

    val nombre = readln()
    println("Hola, $nombre!")
}
```

Podemos dividirlo en tres funciones:

```kotlin
fun main() {
    saludar()
    val nombre = preguntarNombre()
    decirHola(nombre)
}

fun saludar() {
    println("Hola, mundo!")
    println("Soy un programa modular")
}

fun preguntarNombre(): String {
    println("Dime tu nombre: ")
    return readln()
}

fun decirHola(nombre: String) {
    println("Hola, $nombre!")
}
```

En este ejemplo, la función `main` es la función principal del programa. Llama a las funciones `saludar`, `preguntarNombre` y `decirHola` para realizar las acciones correspondientes.

Hay distintas formas de escribir una función. Por ejemplo, la función `saludar` no tiene ni entrada ni salida de datos, ya que solo imprime un mensaje por pantalla.

La función `preguntarNombre` tiene una salida de datos (el nombre del usuario), lo que se conoce como el **valor de retorno**. Es necesario declarar el tipo que tendrá este valor.

La función `decirHola` tiene una entrada de datos (el nombre del usuario), lo que se conoce como el **parámetro de entrada**. Al escribir la función se deben declarar todas las entradas que se vayan a necesitar y el tipo correspondiente.

### Paso por valor y paso por referencia

El paso de parámetros de una función se puede realizar de dos formas: paso por valor y paso por referencia.

En el paso por valor, las variables pasan una copia de su valor a la función, de forma que el valor original no se modifica si cambiase en la función.

En el paso por referencia, las variables pasan la referencia al espacio de memoria que contiene su valor a la función, por lo que los cambios en la función afectan a la variable original.

```kotlin
fun main() {
    val a = 10
    incrementar(a)
    println(a) // Imprime 10

    val sb = StringBuilder()
    sb.append("Hola")
    unirTexto(sb, " Mundo")
    println(sb) // Imprime "Hola Mundo"
}

fun incrementar(a: Int) {
    var mutableA = a
    mutableA++
}

fun unirTexto(sb: StringBuilder, texto: String) {
    sb.append(texto)
}
```

### Ámbitos de las variables

Al declarar una variable se debe tener en cuenta el ámbito en el que será válida. Por ejemplo, una variable declarada dentro de una función solo podrá ser usada dentro de la misma. Una variable declarada como global (declarada como top-level, es decir, fuera de una función o clase) puede ser usada en cualquier parte del programa.

```kotlin
// Esta variable es global y puede ser usada en cualquier parte del programa
var variableGlobal = 10

fun main() {
    // Esta variable es local y solo puede ser usada dentro de la función main
    var variableLocal = 5

    while (variableLocal > 0) {
        // Esta variable es local y solo puede ser usada dentro del bucle while
        var variableWhile = 3 
        variableLocal--
    }

    variableWhile = 4 // Error: variableWhile no es visible fuera del bucle
}

fun otraFuncion() {
    variableLocal = 25 // Error: variableLocal no es visible fuera de la función main
}
```

### Paquetes o módulos

Un paquete o módulo es un conjunto de clases y funciones que realizan tareas relacionadas. Los paquetes nos permiten organizar el código de manera modular y reutilizable, de forma que no tengamos que volver a escribir el mismo código en distintas partes del programa. Un ejemplo de paquete es aquel que contiene las operaciones matemáticas:

```kotlin
// Paquete o módulo
import kotlin.math.* // Importa todas las funciones matemáticas

fun main() {
    println(
        sqrt(4.0) // Esta función se encuentra en el paquete kotlin.math
    )
}
```

### Recursividad

La recursividad es una técnica de programación que consiste en ejecutar una función dentro de ella misma. Para ello, se debe fijar una condición o un caso base sobre el cual se pueda terminar la ejecución de la misma.

Un ejemplo de problema que se puede resolver con recursividad es el factorial de un número, dado que es igual al propio número más el factorial del número anterior.

```kotlin
fun factorial(n: Int): Int {
    if (n == 0) {
        return 1 // Caso base
    } else {
        return n * factorial(n - 1) // Llamada recursiva
    }
}
```
