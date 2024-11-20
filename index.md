# Guía Completa de Programación en C#

¡Bienvenido a esta guía de referencia sobre C#! Aquí exploraremos varios temas fundamentales con ejemplos prácticos y explicaciones detalladas. Este documento está diseñado para ayudarte a comprender y dominar conceptos como **arrays**, **métodos**, **strings**, **StringBuilder**, **bucles** y más.

---

## Tabla de Contenidos
1. [Arrays](#arrays)
2. [Métodos](#métodos)
3. [Strings](#strings)
4. [StringBuilder](#stringbuilder)
5. [Bucles `for`](#bucles-for)
6. [Condicional `switch`](#condicional-switch)

---

## Arrays

Un **array** en C# es una estructura que almacena múltiples valores del mismo tipo. Son ideales para manejar colecciones de datos.

### Declaración y Uso Básico
```csharp
// Declaración y asignación de un array
int[] numeros = { 1, 2, 3, 4, 5 };

// Iterar sobre un array
foreach (int numero in numeros)
{
    Console.WriteLine(numero);
}
### Operaciones Comunes
```csharp
Console.WriteLine(numeros[0]); // Salida: 1 Acceso a Elementos:
numeros[2] = 10;//Modificar un Elemento
Console.WriteLine(numeros.Length); // Salida: 5 Obtener la Longitud:

## Arrays Multidimensionales
```csharp
// Array bidimensional
int[,] matriz = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

// Acceso a elementos
Console.WriteLine(matriz[1, 2]); // Salida: 6
##  Arrays Jagged (Dentados)
```csharp
// Array de arrays
int[][] jaggedArray = new int[3][];
jaggedArray[0] = new int[] { 1, 2 };
jaggedArray[1] = new int[] { 3, 4, 5 };
jaggedArray[2] = new int[] { 6 };

Console.WriteLine(jaggedArray[1][2]); // Salida: 5
## Métodos
Un método en C# es una función que realiza una tarea específica. Puede aceptar parámetros y devolver un valor.
### Declaración y Uso Básico
```csharp
// Método que suma dos números
int Sumar(int a, int b)
{
    return a + b;
}

// Llamar al método
int resultado = Sumar(3, 4);
Console.WriteLine(resultado); // Salida: 7

### Métodos con Parámetros Opcionales
```csharp

void MostrarMensaje(string mensaje = "Hola, mundo")
{
    Console.WriteLine(mensaje);
}

// Uso
MostrarMensaje();                // Salida: Hola, mundo
MostrarMensaje("C# es genial");  // Salida: C# es genial
### Métodos con Parámetros ref y out
```csharp
// Uso de ref
void Incrementar(ref int numero)
{
    numero++;
}

// Uso de out
void ObtenerValores(out int a, out int b)
{
    a = 10;
    b = 20;
}
## Strings
Los strings son cadenas de caracteres. En C#, se manejan como objetos de la clase String.

### Métodos Comunes de Strings
Concatenación:
```csharp
string saludo = "Hola" + " " + "Mundo";
Console.WriteLine(saludo); // Salida: Hola Mundo
Interpolación:
csharp
Copiar código
string nombre = "C#";
Console.WriteLine($"Aprendiendo {nombre}"); // Salida: Aprendiendo C#
### Operaciones:
```csharp
string texto = "Programación en C#";
Console.WriteLine(texto.ToUpper()); // Salida: PROGRAMACIÓN EN C#
Console.WriteLine(texto.ToLower()); // Salida: programación en c#
Console.WriteLine(texto.Contains("C#")); // Salida: True
## StringBuilder
La clase StringBuilder es ideal para manejar cadenas de texto dinámicamente sin crear múltiples instancias en memoria.

### Uso Básico
```csharp
using System.Text;

StringBuilder sb = new StringBuilder("Hola");
sb.Append(" Mundo");
sb.AppendLine("!");
sb.Insert(5, ",");
sb.Replace("Mundo", "C#");

Console.WriteLine(sb.ToString()); // Salida: Hola, Mundo C#!
## Bucles for
El bucle for se usa para iteraciones controladas.

Ejemplo Básico
```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine($"Iteración {i}");
}
### Anidados
```csharp
for (int i = 0; i < 3; i++)
{
    for (int j = 0; j < 3; j++)
    {
        Console.WriteLine($"Posición: ({i}, {j})");
    }
}
## Condicional switch
El condicional switch simplifica múltiples comparaciones.

###  Uso Básico
```csharp
int dia = 3;
switch (dia)
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
    default:
        Console.WriteLine("Día no válido");
        break;
}
###  Con Expresiones de Patrones
```csharp
object valor = 10;
switch (valor)
{
    case int numero when numero > 0:
        Console.WriteLine("Número positivo");
        break;
    case string texto:
        Console.WriteLine($"Es un texto: {texto}");
        break;
    default:
        Console.WriteLine("Tipo desconocido");
        break;
}

