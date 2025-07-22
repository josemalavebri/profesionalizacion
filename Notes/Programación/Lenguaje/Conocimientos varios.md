+ [[Permisos en programación C#]]
+ [[List vs HashSet en C#]]
+ [[Enum con Flags en C#]]
+ [[DateTime vs TimeSpan en C#]]
+ [[Buenas prácticas en nombramiento de clases]]
+ [[Bitwise OR en enums con Flags]]

## ## Validación de pertenencia con `All` y `Contains`

Permite verificar si todos los elementos de una colección están presentes en otra. Útil para validar permisos, roles o condiciones de forma compacta.

---

## ## Uso de `params` en C#

Permite recibir un número variable de argumentos como un arreglo. Ideal cuando no se conoce cuántos parámetros se pasarán. Solo se puede usar con arrays, no con `HashSet`.

---

## ## Diferencia entre `HashSet` y `Array` para `params`

- `params` requiere un tipo de colección indexable (`T[]`).
    
- `HashSet` es más eficiente para búsquedas pero no funciona como argumento `params`.
    
- Se puede usar `params T[]` y convertir internamente a `HashSet` si es necesario.
    

---

## ## Contenedor `HashSet<T>`

Estructura que almacena elementos únicos sin orden específico. Muy eficiente para búsquedas (`O(1)` promedio en `Contains`). Ideal para validar pertenencias.

---

## ## Expresión `All(p => permisos.Contains(p))`

Evalúa si todos los elementos cumplen una condición.  
Se usa como: “¿Todos los permisos solicitados están contenidos en los permisos del usuario?”

---

## ## Sintaxis de expresión lambda

Una forma de representar funciones anónimas.  
`p => permisos.Contains(p)` significa: “por cada `p`, verifica si está en `permisos`”.

---

## ## Uso de `Contains` en colecciones

Disponible en casi todas las colecciones (`List`, `Array`, `HashSet`).  
Verifica si un elemento está presente.  
Internamente depende del método `Equals` y `GetHashCode`.

---

## ## Comparación de elementos en colecciones

Para que `Contains` funcione correctamente, el tipo (`Permiso`, por ejemplo) debe tener implementados `Equals()` y `GetHashCode()` si es clase.

---

## ## Principio de responsabilidad única aplicado a validación

Un método como `tienePermisos(params Permiso[] permisos)` se enfoca solo en validar permisos, manteniendo el diseño limpio y desacoplado.