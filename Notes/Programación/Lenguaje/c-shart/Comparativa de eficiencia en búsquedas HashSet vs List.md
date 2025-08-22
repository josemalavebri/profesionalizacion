---
sr-due: 2025-08-19
sr-interval: 3
sr-ease: 230
aliases:
---
#review   #bdd/modelado 

## Propiedades
**Tema General**: [[Estructuras de datos]] y complejidad algorítmica
**Etiquetas**: #review #cshart 
**Enlaces**: 


## Esencia semántica

+ El `HashSet` es una estructura de datos optimizada para realizar búsquedas rápidas mediante el uso de funciones hash
+ Esto le permite ubicar un elemento sin recorrer toda la colección.
+  En contraste, una `List` requiere recorrer sus elementos secuencialmente, resultando en un tiempo de búsqueda mayor conforme crece la cantidad de datos.
## Puntos clave

- `List` realiza una búsqueda lineal con complejidad **O(n)**.
- `HashSet` realiza una búsqueda promedio con complejidad **O(1)** gracias a la tabla hash.
- En casos con colisiones elevadas o mal uso de la función hash, un `HashSet` podría degradarse a **O(n)**, pero esto es poco común si la implementación de `GetHashCode()` es buena.
- La diferencia de rendimiento crece exponencialmente con el número de elementos y el número de búsquedas.

## Características

**List**
- Ordenada
- Permite elementos duplicados
- Acceso rápido por índice
- Búsqueda secuencial por valor
- Complejidad búsqueda: **O(n)**

**HashSet**
- No ordenada
- No permite elementos duplicados
- Usa `GetHashCode()` y `Equals()` para ubicar elementos
- Búsqueda directa por hash
- Complejidad búsqueda: **O(1)** promedio
## Analogía
> *Piensa en la `List` como un estante lleno de carpetas. Para saber si existe la carpeta de "Pedro", debes revisar carpeta por carpeta hasta encontrarla o llegar al final.  
> Un `HashSet` sería como un sistema de casilleros numerados, donde cada nombre tiene una llave que apunta directamente al casillero correcto. Abres el casillero y, en el peor de los casos, revisas unas pocas carpetas dentro de él si hay colisión.*
## Ejemplos

 **Escenario:** búsqueda de 10 000 veces sobre 1 000 registros
- **List**:
    - Promedio: 500 comparaciones por búsqueda → 2.5 segundos aprox.
- **HashSet**:
    - Promedio: 2 comparaciones por búsqueda → 0.01 segundos aprox.

La diferencia en este caso es de unas **250 veces más rápido** a favor del `HashSet`.

[[]]