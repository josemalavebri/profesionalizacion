---
sr-due: 2025-08-02
sr-interval: 7
sr-ease: 250
---

#review 
## hola 
Método que verifica si **todos** los elementos de una colección cumplen con una condición. En el contexto de permisos, sirve para validar que todos los permisos requeridos están en el conjunto actual del usuario.
```c#
using System;
using System.Collections.Generic;
using System.Linq;

List<string> permisosUsuario = new() { "VER", "EDITAR", "CREAR", "ELIMINAR" };
List<string> permisosRequeridos = new() { "VER", "EDITAR" };

bool tieneTodos = permisosRequeridos.All(p => permisosUsuario.Contains(p));

Console.WriteLine(tieneTodos ? "Acceso concedido" : "Acceso denegado");

```