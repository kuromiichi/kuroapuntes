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

```csharp
int entero = 10;
double decimal = 3.14;
char caracter = 'a';
bool logico = true;
string texto = "Hola, mundo!";
```

También hay tipos de datos compuestos que permiten almacenar un conjunto de datos relacionados, como un array, una lista o un diccionario.

```csharp
int[] array = {1, 2, 3};
List<int> lista = new List<int> { 1, 2, 3 };
Dictionary<string, int> mapa = new Dictionary<string, int> { { "a", 1 }, { "b", 2 }, { "c", 3 } };
HashSet<int> conjunto = new HashSet<int> { 1, 2, 3 };
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

```csharp
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

```csharp
int a = 10;
int b = 5;

bool igual = a == b;
bool diferente = a != b;
bool mayor = a > b;
bool menor = a < b;
bool mayorIgual = a >= b;
bool menorIgual = a <= b;
```

- Lógicas

```csharp
bool a = true;
bool b = false;

bool y = a && b;
bool o = a || b;
bool negacion = !a;
```

- Asignación

```csharp
int a = 10;
a += 5;
a -= 5;
a *= 5;
a /= 5;
a %= 5;
```

### Variables y constantes

Para almacenar los datos en memoria, debemos declarar una variable, que es un espacio de memoria que se reserva para almacenar un dato. Las variables son mutables, lo que significa que pueden cambiar su valor en el futuro. Si no queremos que el valor de la variable cambie, podemos declarar una constante, que es una variable que no puede ser modificada.

Para nombrar las variables, debemos seguir las reglas de estilo de cada lenguaje. En C#, las variables se nombrarán usando lowerCamelCase si son locales, o UpperCamelCase si son públicas o protected, o _lowerCamelCase (así con la _ al principio) si son privadas, y las constantes y variables de solo lectura usando UpperCamelCase. Si te estás planteando dejar la programación, que sepas que esto es solo el principio. Bombardeen Microsoft.

```csharp
int variableLocal = 10;
private int _variablePrivada = 10;
public int VariablePublica { get; set; }
public const int Constante = 10;
public readonly int VariableDeSoloLectura = 10;
```

## Programación estructurada

La programación estructurada es un paradigma de programación que se basa en la ejecución de un programa de forma secuencial, es decir, en el orden en que se escriben las instrucciones.

Los tres elementos básicos de este paradigma son:

- **Secuencias**: una secuencia de instrucciones que se ejecutan en el orden en que se escriben.

```csharp
using System;

namespace Example
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hola, mundo!");
            Console.WriteLine("Soy un programa estructurado");
            Console.Write("Dime tu nombre: ");

            string nombre = Console.ReadLine();
            Console.WriteLine($"Hola, {nombre}!");
        }
    }
}
```

- **Condicionales**: una secuencia de instrucciones que se ejecutan si una condición es verdadera, y otra secuencia de instrucciones que se ejecutan si la condición es falsa.

```csharp
namespace Example
{
    class Program
    {
        static void Main(string[] args)
        {
            int edad = 18;

            if (edad >= 18)
            {
                Console.WriteLine("Eres mayor de edad");
            }
            else
            {
                Console.WriteLine("Eres menor de edad");
            }

            int diaDeLaSemana = 1;

            switch (diaDeLaSemana)
            {
                case 1:
                    Console.WriteLine("Lunes");
                    break;
                case 2:
                    Console.WriteLine("Martes");
                    break;
                case 3:
                    Console.WriteLine("Miércoles");
                    break;
                case 4:
                    Console.WriteLine("Jueves");
                    break;
                case 5:
                    Console.WriteLine("Viernes");
                    break;
                case 6:
                    Console.WriteLine("Sábado");
                    break;
                case 7:
                    Console.WriteLine("Domingo");
                    break;
                default:
                    Console.WriteLine("Día no válido");
                    break;
            }
        }
    }
}
```

- **Bucles**: una secuencia de instrucciones que se ejecutan mientras una condición es verdadera.

```csharp
namespace Example
{
    class Program
    {
        static void Main(string[] args)
        {
            // Bucles definidos
            for (int i = 1; i <= 10; i++)
            {
                Console.WriteLine("Iteración " + i);
            }

            // Bucles indefinidos
            int i = 0;
            while (i < 10) // La condición se comprueba antes de empezar el bucle
            {
                Console.WriteLine("Iteración " + i);
                i++;
            }

            i = 0;
            do
            {
                Console.WriteLine("Iteración " + i);
                i++;
            } while (i < 10); // La condición se comprueba al final del bucle
        }
    }
}
```

También se usan comentarios para explicar el código de manera clara y entendible. Es importante no abusar de ellos, ya que pueden dificultar la lectura del código. El mejor código es aquel que se explica solo.

```csharp
// Este es un comentario de una línea

/*
 * Este es un comentario de bloque
 * Puede abarcar varias líneas
 */
```

## Programación modular

### Funciones

La programación modular amplía sobre los conceptos de programación estructurada y permite dividir el código en diferentes archivos y funciones. Esto permite una mayor organización y mantenibilidad del código.

Una **función** (o **método** en C#) es un bloque de código que realiza una tarea concreta y se puede reutilizar en distintas partes del programa. Mi profe distingue entre funciones y procedimientos pero para el resto de los mortales es irrelevante.

El uso de funciones facilita la legibilidad del código, permite su reutilización y hace más fácil el proceso de resolución de problemas.

Para dividir el código en funciones, es importante saber identificar las subtareas independientes que componen la solución al problema que queremos resolver.

Por ejemplo, el siguiente código escrito siguiendo programación estructurada:

```csharp
namespace Example
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hola, mundo!");
            Console.WriteLine("Soy un programa estructurado");
            Console.Write("Dime tu nombre: ");

            string nombre = Console.ReadLine();
            Console.WriteLine($"Hola, {nombre}!");
        }
    }
}
```

Podemos dividirlo en tres métodos:

```csharp
namespace Example
{
    class Program
    {
        static void Main(string[] args)
        {
            Saludar();
            string nombre = PreguntarNombre();
            DecirHola(nombre);
        }

        static void Saludar()
        {
            Console.WriteLine("Hola, mundo!");
            Console.WriteLine("Soy un programa modular");
        }

        static string PreguntarNombre()
        {
            Console.Write("Dime tu nombre: ");
            return Console.ReadLine();
        }

        static void DecirHola(string nombre)
        {
            Console.WriteLine($"Hola, {nombre}!");
        }
    }
}
```

En este ejemplo, el método `Main` es el método principal del programa. Llama a los métodos `Saludar`, `PreguntarNombre` y `DecirHola` para realizar las acciones correspondientes.

Hay distintas formas de escribir un método. Por ejemplo, el método `Saludar` no tiene ni entrada ni salida de datos, ya que solo imprime un mensaje por pantalla.

El método `PreguntarNombre` tiene una salida de datos (el nombre del usuario), lo que se conoce como el **valor de retorno**. Es necesario declarar el tipo que tendrá este valor.

El método `DecirHola` tiene una entrada de datos (el nombre del usuario), lo que se conoce como el **parámetro de entrada**. Al escribir el método se deben declarar todas las entradas que se vayan a necesitar y el tipo correspondiente.

### Paso por valor y paso por referencia

El paso de parámetros de un método se puede realizar de dos formas: paso por valor y paso por referencia.

En el paso por valor, las variables pasan una copia de su valor al método, de forma que el valor original no se modifica si cambiase en el método.

En el paso por referencia, las variables pasan la referencia al espacio de memoria que contiene su valor al método, por lo que los cambios en el método afectan a la variable original.

```csharp  
namespace Example
{
    class Program
    {
        static void Main(string[] args)
        {
            int a = 10;
            Incrementar(a);
            Console.WriteLine(a); // Imprime 10

            StringBuilder sb = new StringBuilder();
            sb.Append("Hola");
            UnirTexto(sb, " Mundo");
            Console.WriteLine(sb); // Imprime "Hola Mundo"
        }

        static void Incrementar(int a)
        {
            a++;
        }

        static void UnirTexto(StringBuilder sb, string texto)
        {
            sb.Append(texto);
        }
    }
}
```

### Ámbitos de las variables

Al declarar una variable se debe tener en cuenta el ámbito en el que será válida. Por ejemplo, una variable declarada dentro de un método solo podrá ser usada dentro del mismo. Una variable declarada como global (declarada como top-level, es decir, fuera de un método o clase) puede ser usada en cualquier parte del programa. C# es especial y no tiene 

Por cierto, C# no tiene variables declaradas en top-level ya que todo el código debe estar dentro de una clase. En su lugar se usa la palabra reservada `static` para declarar variables globales (no son exactamente eso pero sirven para lo que queremos).

```csharp
namespace Example
{
    class Program
    {
        // Esta variable es global y puede ser usada en cualquier parte del programa
        static int variableGlobal = 10;

        static void Main(string[] args)
        {
            // Esta variable es local y solo puede ser usada dentro del método Main
            int variableLocal = 5;

            while (variableLocal > 0)
            {
                // Esta variable es local y solo puede ser usada dentro del bucle while
                int variableWhile = 3;
                variableLocal--;
            }

            variableWhile = 4; // Error: variableWhile no es visible fuera del bucle
        }

        static void otroMetodo()
        {
            variableLocal = 25; // Error: variableLocal no es visible fuera del método main
        }
    }
}
```

### Paquetes o módulos

Un paquete o módulo es un conjunto de clases y métodos que realizan tareas relacionadas. Los paquetes nos permiten organizar el código de manera modular y reutilizable, de forma que no tengamos que volver a escribir el mismo código en distintas partes del programa. Como siempre, C# es especial y no tiene paquetes sino espacios de nombres. Un ejemplo de espacio de nombre es aquel que contiene las operaciones matemáticas:

```csharp
// Espacio de nombres externo
using System; // Importa todas las funciones del sistema, incluyendo las operaciones matemáticas

// Espacio de nombres interno
namespace Example
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine(
                Math.Sqrt(4.0) // Este método se encuentra en el espacio de nombres System
            );
        }
    }
}
```

### Recursividad

La recursividad es una técnica de programación que consiste en ejecutar un método dentro de él mismo. Para ello, se debe fijar una condición o un caso base sobre el cual se pueda terminar la ejecución del mismo.

Un ejemplo de problema que se puede resolver con recursividad es el factorial de un número, dado que es igual al propio número más el factorial del número anterior.

```csharp
public static int Factorial(int n) {
    if (n == 0) {
        return 1; // Caso base
    } else {
        return n * Factorial(n - 1); // Llamada recursiva
    }
}
```
