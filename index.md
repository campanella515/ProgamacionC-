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
