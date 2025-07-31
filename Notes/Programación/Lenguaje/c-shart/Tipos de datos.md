## **Tipos de Datos en C#**

En C#, los tipos de datos son categorías que definen qué tipo de valor puede almacenar una variable y qué operaciones se pueden realizar sobre ese valor. Comprender los tipos de datos es clave para escribir código correcto, eficiente y seguro, ya que cada tipo tiene un tamaño en memoria y comportamiento específico.

---

## Puntos clave para entenderlos

+ Son la base de toda variable: 
	+ cada variable en C# debe tener un tipo definido.
+ Se dividen en **tipos por valor** y **tipos por referencia**, 
	+ lo que afecta cómo se almacenan y se pasan a métodos.
+ Algunos tipos tienen alias
	+  (como `int` para `System.Int32`) para hacerlos más legibles.
+ Todos los tipos derivan, directa o indirectamente, del tipo base `object`.
---

## Características

+ **Tipos por valor** almacenan directamente los datos y se copian al asignarse. Ejemplo: `int`, `bool`, `float`, `char`, `struct`.
    
+ **Tipos por referencia** almacenan una dirección a un valor en memoria. Ejemplo: `string`, `class`, `array`, `object`.
    
+ Existen tipos **primitivos** como `int`, `float`, `bool`, y tipos **complejos** como `DateTime`, `List<T>`, `Stream`.
    
+ También existen los tipos **nullable**, como `int?`, que permiten representar un valor o `null`.

---

## Analogía simple

> Imagina que cada tipo de dato es una caja con una forma específica: una caja para números enteros, otra para letras, otra para fechas. No puedes guardar una pelota (texto) en una caja diseñada para tornillos (números). Además, algunas cajas (tipos por valor) contienen el objeto directamente, mientras que otras solo tienen una nota con la dirección de dónde está guardado (tipos por referencia).

---

## Sintaxis general

```c#
// Declaración de variables con tipos
int numero = 10;
float temperatura = 36.6f;
bool estaActivo = true;
char letra = 'A';
string mensaje = "Hola mundo";
```