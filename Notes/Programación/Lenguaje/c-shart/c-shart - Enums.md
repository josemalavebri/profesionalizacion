### Esencia semántica de los Enums en C#

+ Los _enums_ (enumeraciones) en C# representan un conjunto de 
	+ **constantes simbólicas nombradas**. 
+ Encapsulan un **grupo cerrado de posibles valores** para 
	+ una variable.
+ Facilita la legibilidad del código, minimizando errores por uso de 
	+ valores mágicos o literales. 
+ Un `enum` hace explícito el dominio posible de una
	+  categoría específica de datos.

---

### Concepto

+ Un `enum` es un tipo de 
	+ valor definido por el usuario 
+ Está compuesto por un 
	+ conjunto de constantes con nombre 
+  Se asocian internamente a 
	+ valores numéricos enteros. 
+ Sirve para representar 
	+ estados, 
	+ opciones  o categorías 
+  Tienen nombres legibles en lugar de 
	+ números.

---

### Puntos claves

- Por defecto, cada valor de un `enum` es de tipo `int` y comienza en `0`, aunque puede ser modificado.
    
- Los `enum` son estáticos y se usan como tipos en variables.
    
- Se pueden convertir a su valor numérico (cast) y viceversa.
    
- Mejoran la legibilidad del código y reducen errores lógicos.
    
- Se puede usar cualquier tipo entero (`byte`, `short`, `int`, `long`, etc.) como base del enum.
    

---

### Características

- Son tipos por valor (`struct`) y no admiten herencia.
    
- Permiten asociar un nombre a un valor constante.
    
- Se pueden usar con `switch`, `if` y otras estructuras de control.
    
- Soportan atributos como `[Flags]` para representar combinaciones binarias.
    
- Pueden ser definidos fuera o dentro de una clase/struct, pero no dentro de un método.
    

---

### Analogía

Piensa en un semáforo: tiene **rojo**, **amarillo** y **verde**. Internamente podrías usar 0, 1 y 2, pero usando un `enum` puedes escribir `ColorSemaforo.Rojo`, `ColorSemaforo.Verde`, etc., haciendo el código mucho más claro. El `enum` sería como el cartel en la caja del semáforo que dice qué color representa cada valor eléctrico.

---
### Ejemplo de la sintaxis (genérica o abstracto)

```c#

enum NombreEnum
{
    Valor1,
    Valor2,
    Valor3 = 5,
    Valor4
}
```

Esto genera:
- Valor1 = 0
- Valor2 = 1
- Valor3 = 5
- Valor4 = 6

---

### Ejemplo en uso (dominio)
```c#
enum Turno
{
    Mañana = 1,
    Tarde = 2,
    Noche = 3
}

class Cita
{
    public string Paciente { get; set; }
    public Turno TurnoAsignado { get; set; }
}

// Uso
Cita cita = new Cita();
cita.Paciente = "Carlos Pérez";
cita.TurnoAsignado = Turno.Tarde;

if (cita.TurnoAsignado == Turno.Tarde)
{
    Console.WriteLine("El paciente tiene una cita en la tarde.");
}

```

Esto evita usar valores como `1`, `2`, o `3` directamente, lo que mejora la claridad, facilita el mantenimiento y evita errores en el sistema.