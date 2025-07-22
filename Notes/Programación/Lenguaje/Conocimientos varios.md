+ [[Permisos en programación C#]]
+ [[List vs HashSet en C#]]
+ [[Enum con Flags en C#]]
+ [[DateTime vs TimeSpan en C#]]
+ [[Buenas prácticas en nombramiento de clases]]
+ [[Bitwise OR en enums con Flags]]
+ [[Validación de pertenencia con All y Contains]]  
- [[HashSet en C#]] 
    
    
- [[params en métodos de C#]]  
- [[Método Contains en colecciones]]
    
    
- `[[Expresión lambda en LINQ]]`  
    Sintaxis abreviada para definir funciones anónimas. En `p => permisos.Contains(p)`, se usa como una función que recibe `p` y devuelve si está en `permisos`. Es clave para recorrer y evaluar colecciones de forma declarativa.
    
- `[[All de LINQ]]`  
    Método que verifica si **todos** los elementos de una colección cumplen con una condición. En el contexto de permisos, sirve para validar que todos los permisos requeridos están en el conjunto actual del usuario.
    
- `[[Diferencia entre HashSet y Array]]`  
    Un `HashSet` es más eficiente para búsquedas y no permite duplicados. Un `array` es una estructura lineal con posiciones fijas y puede tener elementos repetidos. Ambos se pueden recorrer y consultar, pero con diferentes rendimientos y comportamientos.
    
- `[[Chequeo de permisos con HashSet]]`  
    Estrategia en la que se define un conjunto de permisos actuales (`HashSet`) y se comparan contra un conjunto de permisos requeridos, usando `All` para asegurar que todos estén presentes. Representa una validación completa de roles o accesos.
    
- `[[Métodos con argumentos variables]]`  
    Permiten crear funciones flexibles, donde se puede pasar cualquier cantidad de valores. `params` lo logra encapsulando los argumentos en un array, permitiendo escribir llamadas como `tienePermisos(p1, p2, p3)` sin armar manualmente una colección.
    
- `[[Analogía: permisos como llaves]]`  
    Imagina que los permisos son llaves que te permiten abrir ciertas puertas. Tener todas las llaves necesarias (permisos) permite el acceso completo. La validación con `All()` sería como verificar si tienes todas las llaves que te pidieron.
    
- `[[Colecciones eficientes para validación]]`  
    Usar estructuras como `HashSet` permite validaciones de pertenencia (`Contains`) rápidas, ideales para sistemas de roles, etiquetas, categorías o cualquier lógica basada en conjuntos no duplicados.