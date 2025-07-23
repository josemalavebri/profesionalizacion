---
sr-due: 2025-07-24
sr-interval: 1
sr-ease: 210
---

#tipo-documento #review  
## Puntos claves y Conceptos
Los **tipos de datos primitivos** son los bloques básicos con los que se construyen todas las variables en un lenguaje de programación. Representan valores simples que no se descomponen más: números, caracteres, booleanos, etc.
- **Simples**: No están compuestos por otros tipos de datos.
- **Eficientes**: Son gestionados directamente por el compilador o el hardware.
- **Base de otros tipos**: Muchos tipos complejos (como clases, structs, arrays) están formados a partir de tipos primitivos.
- **Inmutables** (en muchos [[lenguajes]]): No cambian su valor una vez asignados, sino que se reemplazan
## Características
- Se almacenan en **la pila (stack)**, lo que hace que su acceso sea rápido.
- Ocupan una **cantidad fija de memoria** dependiendo del tipo (por ejemplo, `int` ocupa 4 bytes en C#).
- Soportan operaciones básicas según el tipo: suma para números, comparación para booleanos, etc.
- Tienen **valores por defecto** al declararse sin inicializar (por ejemplo, `false` en un `bool`, `0` en un `int`).
## Analogía

> Piensa en los tipos primitivos como los **ingredientes básicos** de una receta: harina, azúcar, sal, etc. Aunque puedes hacer algo complejo como un pastel (una clase u objeto), sin estos ingredientes simples no podrías empezar a cocinar nada.
## Ejemplos
### Sintaxis
```c
int edad = 25;           // Entero
float altura = 1.75f;    // Decimal de menor precisión
double peso = 70.5;      // Decimal de mayor precisión
char inicial = 'S';      // Carácter
bool esEstudiante = true; // Booleano

```
### Uso
```c#
int a = 10;
int b = 20;
bool mayor = b > a;
Console.WriteLine("¿b es mayor que a? " + mayor);
```
