
# Guía de Programación en C# Por Campanella

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
int[] numeros = { 1, 2, 3, 4, 5 };//una forma de inicializarla

// Iterar sobre un array usando foreach , de igual forma podemos hacerlo con for
foreach (int numero in numeros)
{
    Console.WriteLine(numero);
}
```
```csharp
  // Declaramos e inicializamos un array
        int[] numeros = { 1, 2, 3, 4, 5 };

        // Usamos un bucle for para recorrer el array
        for (int i = 0; i < numeros.Length; i++)
        {
            Console.WriteLine($"Elemento en el índice {i}: {numeros[i]}");
        }
```

### Operaciones Comunes

1. **Acceso a Elementos**:
   ```csharp
   Console.WriteLine(numeros[0]); // Salida: 1
   ```

2. **Modificar un Elemento**:
   ```csharp
   numeros[2] = 10;
   ```

3. **Obtener la Longitud**:
   ```csharp
   Console.WriteLine(numeros.Length); // Salida: 5
   ```

---

## Arrays Multidimensionales

Los **arrays bidimensionales** permiten almacenar datos en una tabla (como una matriz).

```csharp
// Array bidimensional
int[,] matriz = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

// Acceso a elementos
Console.WriteLine(matriz[1, 2]); // Salida: 6
```

---

## Arrays Jagged (Dentados)

Los **arrays jagged** son arrays de arrays, donde cada sub-array puede tener un tamaño diferente.

```csharp
// Array de arrays
int[][] jaggedArray = new int[3][];
jaggedArray[0] = new int[] { 1, 2 };
jaggedArray[1] = new int[] { 3, 4, 5 };
jaggedArray[2] = new int[] { 6 };

Console.WriteLine(jaggedArray[1][2]); // Salida: 5
```

---

## Métodos

Un **método** en C# es una función que realiza una tarea específica. Puede aceptar parámetros y devolver un valor.

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
```

### Métodos con Parámetros Opcionales

```csharp
void MostrarMensaje(string mensaje = "Hola, mundo")
{
    Console.WriteLine(mensaje);
}

// Uso
MostrarMensaje();                // Salida: Hola, mundo
MostrarMensaje("C# es genial");  // Salida: C# es genial
```

### Métodos con Parámetros `ref` y `out`

1. **Uso de `ref`**: Permite pasar argumentos por referencia, lo que permite modificar el valor dentro del método.
   ```csharp
   void Incrementar(ref int numero)
   {
       numero++;
   }
   ```

2. **Uso de `out`**: Permite retornar múltiples valores desde un método.
   ```csharp
   void ObtenerValores(out int a, out int b)
   {
       a = 10;
       b = 20;
   }
   ```

---

# Formas de Retornar en C#

En C#, un **método** puede retornar valores de distintas maneras, dependiendo de la firma del método, ya sea con valores o sin valores. A continuación, se muestran varias formas de retornar desde un método, incluyendo ejemplos de métodos que retornan un valor, métodos `void` (sin valor de retorno), y métodos que usan `ref` o `out` para retornar valores de forma diferente.

## 1. Métodos con tipo de retorno (`return`)

Cuando un método tiene un tipo de retorno específico (como `int`, `string`, `bool`, etc.), debes usar la palabra clave `return` para devolver el valor correspondiente. El valor de retorno debe coincidir con el tipo del método.

### Ejemplo 1: Retornar un valor `int`

```csharp
using System;

class Program
{
    // Método que retorna un valor de tipo int
    static int Sumar(int a, int b)
    {
        return a + b;
    }

    static void Main()
    {
        int resultado = Sumar(3, 4);
        Console.WriteLine("La suma es: " + resultado);  // Salida: La suma es: 7
    }
}
```
En este ejemplo, el método `Sumar` retorna un valor de tipo `int` y usa `return` para devolver el resultado de la suma.

## 2. Métodos `void` (sin valor de retorno)

Un método `void` no tiene valor de retorno, lo que significa que no usa la palabra clave `return` para devolver nada. Aunque puedes usar `return` en un método `void` para salir del método anticipadamente, no retornará ningún valor.

### Ejemplo 2: Método `void` (sin valor de retorno)

```csharp
using System;

class Program
{
    // Método sin valor de retorno (void)
    static void MostrarMensaje(string mensaje)
    {
        Console.WriteLine(mensaje);
    }

    static void Main()
    {
        MostrarMensaje("¡Hola, Mundo!");  // Salida: ¡Hola, Mundo!
    }
}
```
El método `MostrarMensaje` no retorna ningún valor; simplemente imprime un mensaje.

## 3. Métodos con `ref` (referencia) para modificar el valor de una variable fuera del método

El modificador `ref` permite que un método modifique una variable fuera de su ámbito. El valor de la variable se pasa por referencia, lo que permite que el método modifique el valor original.

### Ejemplo 3: Método con `ref`

```csharp
using System;

class Program
{
    // Método que usa 'ref' para modificar el valor de la variable original
    static void Incrementar(ref int numero)
    {
        numero++;
    }

    static void Main()
    {
        int num = 5;
        Incrementar(ref num);
        Console.WriteLine("El valor incrementado es: " + num);  // Salida: El valor incrementado es: 6
    }
}
```
Aquí, `Incrementar` toma un parámetro por referencia (`ref int numero`), lo que permite modificar el valor de `num` en el método principal.

## 4. Métodos con `out` (salida) para retornar múltiples valores

El modificador `out` permite que un método retorne más de un valor. A diferencia de `ref`, las variables pasadas como `out` no necesitan ser inicializadas antes de pasar al método, ya que el método debe asignar un valor a esas variables.

### Ejemplo 4: Método con `out`

```csharp
using System;

class Program
{
    // Método con 'out' que retorna dos valores
    static void ObtenerValores(out int x, out int y)
    {
        x = 10;
        y = 20;
    }

    static void Main()
    {
        int a, b;
        ObtenerValores(out a, out b);
        Console.WriteLine($"Valor de a: {a}, Valor de b: {b}");  // Salida: Valor de a: 10, Valor de b: 20
    }
}
```
En este caso, el método `ObtenerValores` usa `out` para asignar valores a las variables `a` y `b`. Estas no necesitan ser inicializadas antes de la llamada al método.

## 5. Métodos con `return` y tipos complejos (como Tuplas o Objetos)

Puedes retornar tipos complejos, como tuplas u objetos, utilizando `return`.

### Ejemplo 5: Retornar una tupla

```csharp
using System;

class Program
{
    // Método que retorna una tupla
    static (int, int) ObtenerSumaYResta(int a, int b)
    {
        return (a + b, a - b);
    }

    static void Main()
    {
        var (suma, resta) = ObtenerSumaYResta(10, 5);
        Console.WriteLine($"Suma: {suma}, Resta: {resta}");  // Salida: Suma: 15, Resta: 5
    }
}
```
En este ejemplo, el método `ObtenerSumaYResta` retorna una tupla con dos valores: la suma y la resta de `a` y `b`.

## 6. Métodos que retornan `null` (en caso de tipos referencia)

En C#, los tipos de referencia pueden retornar `null` si no tienen valor asignado. Esto es útil para representar un estado vacío o no asignado.

### Ejemplo 6: Método que retorna `null`

```csharp
using System;

class Program
{
    // Método que retorna null en caso de no encontrar un valor
    static string ObtenerValor(bool existe)
    {
        if (existe)
        {
            return "Valor encontrado";
        }
        else
        {
            return null;
        }
    }

    static void Main()
    {
        string resultado = ObtenerValor(false);
        if (resultado != null)
        {
            Console.WriteLine(resultado);
        }
        else
        {
            Console.WriteLine("No se encontró el valor.");
        }
    }
}
```
Aquí, el método `ObtenerValor` retorna `null` si la condición no se cumple, y el código que llama al método puede manejar este caso con una comprobación.

---
## Strings

Los **strings** en C# son secuencias de caracteres. Son inmutables, lo que significa que no puedes cambiar su valor directamente.

### Métodos Comunes de Strings

1. **Concatenación**:
   ```csharp
   string saludo = "Hola" + " " + "Mundo";
   Console.WriteLine(saludo); // Salida: Hola Mundo
   ```

2. **Interpolación**:
   ```csharp
   string nombre = "C#";
   Console.WriteLine($"Aprendiendo {nombre}"); // Salida: Aprendiendo C#
   ```

3. **Operaciones Comunes**:
   ```csharp
   string texto = "Programación en C#";
   Console.WriteLine(texto.ToUpper()); // Salida: PROGRAMACIÓN EN C#
   Console.WriteLine(texto.ToLower()); // Salida: programación en c#
   Console.WriteLine(texto.Contains("C#")); // Salida: True
   ```

---

## StringBuilder

La clase **StringBuilder** es ideal para manejar cadenas de texto dinámicamente sin crear múltiples instancias en memoria. Es útil cuando necesitas modificar cadenas de forma frecuente.

### Uso Básico

```csharp
using System.Text;

StringBuilder sb = new StringBuilder("Hola");
sb.Append(" Mundo");
sb.AppendLine("!");
sb.Insert(5, ",");
sb.Replace("Mundo", "C#");

Console.WriteLine(sb.ToString()); // Salida: Hola, Mundo C#!
```

---

## Bucles `for`

El bucle `for` se usa cuando sabes cuántas veces deseas repetir un bloque de código.

### Ejemplo Básico

```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine($"Iteración {i}");
}
```

### Bucles `for` Anidados

```csharp
for (int i = 0; i < 3; i++)
{
    for (int j = 0; j < 3; j++)
    {
        Console.WriteLine($"Posición: ({i}, {j})");
    }
}
```

---

## Condicional `switch`

El condicional `switch` es útil cuando tienes múltiples opciones y deseas comparar una variable contra diferentes valores.

### Uso Básico

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
```

### Con Expresiones de Patrones

En C# 7.0 y versiones posteriores, puedes usar **expresiones de patrones** para realizar comparaciones más complejas.

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
```

---

## Conclusión

Esta guía proporciona una introducción sólida a algunos conceptos clave de C#. 

Se trata de una guia facil para temario primer timestre DAM colaboradora Dayana.



Este archivo a sido creado por campanella
