[[Conocimientos varios]]
- El operador `|` combina múltiples valores de un enum marcado con `[Flags]`.
- Ejemplo:  
```csharp
  DiaSemana dias = DiaSemana.Lunes | DiaSemana.Miercoles;
  dias.HasFlag(DiaSemana.Lunes); // true
```
