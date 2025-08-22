[[Conocimientos varios]]
Permite verificar si todos los elementos de una colección están presentes en otra. Útil para validar permisos, roles o condiciones de forma compacta.

```c#
// Colección de roles que el usuario tiene
List<string> rolesUsuario = new List<string> { "admin", "editor", "user" };

// Roles necesarios para acceder a un recurso
List<string> rolesRequeridos = new List<string> { "admin", "editor" };

// Validación: ¿el usuario tiene todos los roles requeridos?
bool accesoPermitido = rolesRequeridos.All(rol => rolesUsuario.Contains(rol));

// accesoPermitido será true si el usuario cumple con todos los roles requeridos
Console.WriteLine(accesoPermitido);
```

