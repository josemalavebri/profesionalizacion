---
sr-due: 2025-07-31
sr-interval: 3
sr-ease: 170
---

#tipo-problematica #review 
## Puntos clave
- [[JsonIgnore]] es una 
	- data annotation que indica 
		- al serializador JSON que omita la propiedad marcada.
- Evita la serialización de propiedades que puedan generar
	-  ciclos o datos no deseados.
- Pertenece al espacio de nombres 
	- `System.Text.Json.Serialization`.
- Se usa para 
	- controlar qué se incluye o excluye al convertir objetos a JSON.
## Características
- Se aplica directamente sobre 
	- propiedades o campos en clases.
- No afecta la base de datos ni el modelo EF Core, 
	- Solo la serialización JSON.
- Compatible con `System.Text.Json`, el serializador por defecto en .NET Core 3.0+.
- Facilita la ruptura de 
	- ciclos de referencias para evitar excepciones.
## Analogía

> Imagina que tienes un listado de amigos, y uno de ellos te pide que no menciones a cierta persona para evitar enredos o malentendidos. `[JsonIgnore]` es esa instrucción que haces para "callar" esa parte y evitar confusiones en la historia que cuentas.

---
## Problema:
`System.Text.Json.JsonException: A possible object cycle was detected.`
### Código del error o descripción del problema a detalle:

```json
System.Text.Json.JsonException: A possible object cycle was detected. This can either be due to a cycle or if the object depth is larger than the maximum allowed depth of 32. Consider using ReferenceHandler.Preserve on JsonSerializerOptions to support cycles. Path: $.Responsable.AreasResponsables.Responsable.AreasResponsables...
```

### Solución

```c#
using System.Text.Json.Serialization;

public class Usuario
{
    public int Id { get; set; }
    public string Nombre { get; set; }

    [JsonIgnore] // Evita que esta propiedad cause ciclos en la serialización
    public ICollection<Area> AreasResponsables { get; set; }
}

```
