## [[Permisos en programación C#]]


---

## [[List vs HashSet en C#]]


---

## [[Enum con Flags en C#]]

- `[Flags]` permite combinar múltiples opciones en una sola variable usando operaciones bitwise (`|`, `&`, `HasFlag`).
- Cada valor del enum debe ser una potencia de 2: `1, 2, 4, 8...`.
- Útil para representar varios permisos o días de la semana activados a la vez.

---

## [[DateTime vs TimeSpan en C#]]

- `DateTime` representa una fecha y hora completas.
- Si solo necesitas la hora (ej. 9:00 AM), puedes usar `DateTime.Today.AddHours(9)`.
- Para representar solo una hora sin fecha, lo ideal es usar `TimeSpan` (ej: `new TimeSpan(9, 0, 0)`).

---

## [[Buenas prácticas en nombramiento de clases]]

- Clases: **singular** (`Usuario`, `Producto`).
- Colecciones o listas: **plural** (`usuarios`, `productos`).
- Si la clase representa una agrupación de flags o booleans: se acepta el **plural** (`Permisos`, `Configuraciones`).

---

## [[Bitwise OR en enums con Flags]]

- El operador `|` combina múltiples valores de un enum marcado con `[Flags]`.
- Ejemplo:  
  ```csharp
  DiaSemana dias = DiaSemana.Lunes | DiaSemana.Miercoles;
  dias.HasFlag(DiaSemana.Lunes); // true
