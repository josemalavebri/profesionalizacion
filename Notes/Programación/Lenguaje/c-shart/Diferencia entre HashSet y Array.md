---
sr-due: 2025-09-16
sr-interval: 33
sr-ease: 250
---

[[Conocimientos varios]]
#review 
Un `HashSet` es más eficiente para búsquedas y no permite duplicados. Un `array` #estado-investigar es una estructura lineal con posiciones fijas y puede tener elementos repetidos. Ambos se pueden recorrer y consultar, pero con diferentes rendimientos y comportamientos.

```c#
// Crear un array con duplicados
int[] numerosArray = { 1, 2, 3, 4, 5, 3, 2 };
// Crear un HashSet a partir del array
HashSet<int> numerosHashSet = new HashSet<int>(numerosArray);

Console.WriteLine("Contenido del array:");
foreach (var n in numerosArray)
	Console.Write(n + " "); // Puede repetir

Console.WriteLine("\nContenido del HashSet:");
foreach (var n in numerosHashSet)
	Console.Write(n + " "); // Sin duplicados

Console.WriteLine();

// Medimos tiempo de búsqueda
int buscar = 5;
Stopwatch sw = new Stopwatch();

sw.Start();
bool encontradoEnArray = Array.Exists(numerosArray, n => n == buscar);
sw.Stop();
Console.WriteLine($"\nBuscar en array: {encontradoEnArray}, tiempo: {sw.ElapsedTicks} ticks"); 

sw.Restart();
bool encontradoEnHashSet = numerosHashSet.Contains(buscar);
sw.Stop();
Console.WriteLine($"Buscar en HashSet: {encontradoEnHashSet}, tiempo: {sw.ElapsedTicks} ticks");
```
- El `array` permite duplicados y se recorre con `Array.Exists` (búsqueda lineal).
    
- El `HashSet` elimina duplicados automáticamente al construirlo y su búsqueda es mucho más rápida gracias a su estructura basada en _hashing_.
    
- Los tiempos (`ElapsedTicks`) ilustran que `HashSet.Contains` es generalmente más eficiente que `Array.Exists`
[[Comp]]