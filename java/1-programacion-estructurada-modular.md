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

```java
int entero = 10;
double decimal = 3.14;
char caracter = 'a';
boolean logico = true;
String texto = "Hola, mundo!";
```

También hay tipos de datos compuestos que permiten almacenar un conjunto de datos relacionados, como un array, una lista o un mapa.

```java
int[] array = {1, 2, 3};
List<Integer> lista = List.of(1, 2, 3);
Map<String, Integer> mapa = Map.of("a", 1, "b", 2, "c", 3);
Set<Integer> conjunto = Set.of(1, 2, 3);
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

```java
int a = 10;
int b = 5;

int suma = a + b;
int resta = a - b;
int multiplicacion = a * b;
int division = a / b;
int modulo = a % b;
int aumento = ++a;
int disminucion = --a;
```

- Relacionales

```java
int a = 10;
int b = 5;

boolean igual = a == b;
boolean diferente = a != b;
boolean mayor = a > b;
boolean menor = a < b;
boolean mayorIgual = a >= b;
boolean menorIgual = a <= b;
```

- Lógicas

```java
boolean a = true;
boolean b = false;

boolean y = a && b;
boolean o = a || b;
boolean negacion = !a;
```

- Asignación

```java
int a = 10;
a += 5;
a -= 5;
a *= 5;
a /= 5;
a %= 5;
```

### Variables y constantes

Para almacenar los datos en memoria, debemos declarar una variable, que es un espacio de memoria que se reserva para almacenar un dato. Las variables son mutables, lo que significa que pueden cambiar su valor en el futuro. Si no queremos que el valor de la variable cambie, podemos declarar una constante, que es una variable que no puede ser modificada.

Para nombrar las variables, debemos seguir las reglas de estilo de cada lenguaje. En Java, las variables se nombrarán usando lowerCamelCase, y las constantes usando UPPER_SNAKE_CASE.

```java
int variable = 10; // Variable mutable
final int CONSTANTE = 10; // Variable inmutable
```

## Programación estructurada

La programación estructurada es un paradigma de programación que se basa en la ejecución de un programa de forma secuencial, es decir, en el orden en que se escriben las instrucciones.

Los tres elementos básicos de este paradigma son:

- **Secuencias**: una secuencia de instrucciones que se ejecutan en el orden en que se escriben.

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hola, mundo!");
        System.out.println("Soy un programa estructurado");
        System.out.print("Dime tu nombre: ");

        String nombre = System.console().readLine();
        System.out.println("Hola, " + nombre + "!");
    }
}
```

- **Condicionales**: una secuencia de instrucciones que se ejecutan si una condición es verdadera, y otra secuencia de instrucciones que se ejecutan si la condición es falsa.

```java
public class Main {
    public static void main(String[] args) {
        int edad = 18;

        if (edad >= 18) {
            System.out.println("Eres mayor de edad");
        } else {
            System.out.println("Eres menor de edad");
        }

        int diaDeLaSemana = 1;

        switch (diaDeLaSemana) {
            case 1 -> System.out.println("Lunes");
            case 2 -> System.out.println("Martes");
            case 3 -> System.out.println("Miércoles");
            case 4 -> System.out.println("Jueves");
            case 5 -> System.out.println("Viernes");
            case 6 -> System.out.println("Sábado");
            case 7 -> System.out.println("Domingo");
            default -> System.out.println("Día no válido");
        }
    }
}
```

- **Bucles**: una secuencia de instrucciones que se ejecutan mientras una condición es verdadera.

```java
public class Main {
    public static void main(String[] args) {
        // Bucles definidos
        for (int i = 1; i <= 10; i++) {
            System.out.println("Iteración " + i);
        }

        // Bucles indefinidos
        int i = 0;
        while (i < 10) { // La condición se comprueba antes de empezar el bucle
            System.out.println("Iteración " + i);
            i++;
        }

        i = 0;
        do {
            System.out.println("Iteración " + i);
            i++;
        } while (i < 10); // La condición se comprueba al final del bucle
    }
}
```

También se usan comentarios para explicar el código de manera clara y entendible. Es importante no abusar de ellos, ya que pueden dificultar la lectura del código. El mejor código es aquel que se explica solo.

```java
// Este es un comentario de una línea

/*
 * Este es un comentario de bloque
 * Puede abarcar varias líneas
 */
```

## Programación modular

### Funciones

La programación modular amplía sobre los conceptos de programación estructurada y permite dividir el código en diferentes archivos y funciones. Esto permite una mayor organización y mantenibilidad del código.

Una **función** (o **método** en Java) es un bloque de código que realiza una tarea concreta y se puede reutilizar en distintas partes del programa. Mi profe distingue entre funciones y procedimientos pero para el resto de los mortales es irrelevante.

El uso de funciones facilita la legibilidad del código, permite su reutilización y hace más fácil el proceso de resolución de problemas.

Para dividir el código en funciones, es importante saber identificar las subtareas independientes que componen la solución al problema que queremos resolver.

Por ejemplo, el siguiente código escrito siguiendo programación estructurada:

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hola, mundo!");
        System.out.println("Soy un programa estructurado");
        System.out.print("Dime tu nombre: ");

        Scanner scanner = new Scanner(System.in);
        String nombre = scanner.nextLine();
        System.out.println("Hola, " + nombre + "!");
    }
}
```

Podemos dividirlo en tres métodos:

```java
public class Main {
    public static void main(String[] args) {
        saludar();
        String nombre = preguntarNombre();
        decirHola(nombre);
    }

    public static void saludar() {
        System.out.println("Hola, mundo!");
        System.out.println("Soy un programa modular");
    }

    public static String preguntarNombre() {
        System.out.print("Dime tu nombre: ");
        Scanner scanner = new Scanner(System.in);
        return scanner.nextLine();
    }

    public static void decirHola(String nombre) {
        System.out.println("Hola, " + nombre + "!");
    }
}
```

En este ejemplo, el método `main` es el método principal del programa. Llama a los métodos `saludar`, `preguntarNombre` y `decirHola` para realizar las acciones correspondientes.

Hay distintas formas de escribir un método. Por ejemplo, el método `saludar` no tiene ni entrada ni salida de datos, ya que solo imprime un mensaje por pantalla.

El método `preguntarNombre` tiene una salida de datos (el nombre del usuario), lo que se conoce como el **valor de retorno**. Es necesario declarar el tipo que tendrá este valor.

El método `decirHola` tiene una entrada de datos (el nombre del usuario), lo que se conoce como el **parámetro de entrada**. Al escribir el método se deben declarar todas las entradas que se vayan a necesitar y el tipo correspondiente.

### Paso por valor y paso por referencia

El paso de parámetros de un método se puede realizar de dos formas: paso por valor y paso por referencia.

En el paso por valor, las variables pasan una copia de su valor al método, de forma que el valor original no se modifica si cambiase en el método.

En el paso por referencia, las variables pasan la referencia al espacio de memoria que contiene su valor al método, por lo que los cambios en el método afectan a la variable original.

```java
public class Main {
    public static void main(String[] args) {
        int a = 10;
        incrementar(a);
        System.out.println(a); // Imprime 10

        StringBuilder sb = new StringBuilder();
        sb.append("Hola");
        unirTexto(sb, " Mundo");
        System.out.println(sb); // Imprime "Hola Mundo"
    }

    public static void incrementar(int a) {
        a++;
    }

    public static void unirTexto(StringBuilder sb, String texto) {
        sb.append(texto);
    }
}
```

### Ámbitos de las variables

Al declarar una variable se debe tener en cuenta el ámbito en el que será válida. Por ejemplo, una variable declarada dentro de un método solo podrá ser usada dentro del mismo. Una variable declarada como global (declarada como top-level, es decir, fuera de un método o clase) puede ser usada en cualquier parte del programa.

```java
// Esta variable es global y puede ser usada en cualquier parte del programa
int variableGlobal = 10;

public static void main(String[] args) {
    // Esta variable es local y solo puede ser usada dentro del método main
    int variableLocal = 5;

    while (variableLocal > 0) {
        // Esta variable es local y solo puede ser usada dentro del bucle while
        int variableWhile = 3;
        variableLocal--;
    }

    variableWhile = 4; // Error: variableWhile no es visible fuera del bucle
}

public static void otroMetodo() {
    variableLocal = 25; // Error: variableLocal no es visible fuera del método main
}
```

### Paquetes o módulos

Un paquete o módulo es un conjunto de clases y métodos que realizan tareas relacionadas. Los paquetes nos permiten organizar el código de manera modular y reutilizable, de forma que no tengamos que volver a escribir el mismo código en distintas partes del programa. Un ejemplo de paquete es aquel que contiene las operaciones matemáticas:

```java
// Paquete o módulo
import java.lang.Math; // Importa todas las funciones matemáticas

public class Main {
    public static void main(String[] args) {
        System.out.println(
            Math.sqrt(4.0) // Este método se encuentra en el paquete java.lang.Math
        );
    }
}
```

### Recursividad

La recursividad es una técnica de programación que consiste en ejecutar un método dentro de él mismo. Para ello, se debe fijar una condición o un caso base sobre el cual se pueda terminar la ejecución del mismo.

Un ejemplo de problema que se puede resolver con recursividad es el factorial de un número, dado que es igual al propio número más el factorial del número anterior.

```java
public static int factorial(int n) {
    if (n == 0) {
        return 1; // Caso base
    } else {
        return n * factorial(n - 1); // Llamada recursiva
    }
}
```
