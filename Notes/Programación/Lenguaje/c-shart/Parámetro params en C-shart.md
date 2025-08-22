---
sr-due: 2025-09-11
sr-interval: 29
sr-ease: 250
---
[[Conocimientos varios]]
 #review  
## Esencia semántica
+ Permitir que un método reciba un número variable de 
	+ argumentos
+ Trata los argumentos como si se tratara de 
	+ un array,
+ Mantiene la flexibilidad sin necesidad de 
	+ múltiples sobrecargas.
+ Permite a un método aceptar un número indefinido de 
	+ argumentos del mismo tipo. 
+ Los argumentos se agrupan en un 
	+ array. 
+ Evita la necesidad de definir varias versiones (sobrecargas) del 
	+ mismo método para diferentes cantidades de
		+  parámetros.
## Puntos clave
- Solo puede haber un parámetro `params` por método y debe ser 
	- el último en la lista de parámetros.
- Los argumentos pueden pasarse separados por 
	- comas o como 
		- un array explícito.
- Si no se pasan argumentos, el parámetro `params` será 
	- un array vacío.
- Es útil cuando se quiere permitir entradas múltiples sin obligar al usuario a crear explícitamente 
	- un array.
## Características
- Mejora la legibilidad del código del lado del consumidor.
- Compatible con tipos genéricos, por ejemplo: `params HashSet<T>[]`.
- Internamente todo se trata como un array del tipo especificado.
- Permite al método trabajar con cero o más entradas sin sobrecargar el método manualmente.

## Analogía
> Imagínate que estás construyendo un formulario que puede aceptar desde cero hasta muchos correos electrónicos. En lugar de crear varios formularios para 1, 2, 3 o más correos, simplemente colocas un campo que permita agregar todos los correos que quieras: ese campo es `params`.
## Ejemplos
### Sintaxis 
```c
public void MiMetodo(params TipoDato[] argumentos) {
    // Uso de argumentos como arreglo
}
```
### Uso
```c#
public void MostrarNombres(params string[] nombres) {
    foreach (var nombre in nombres) {
        Console.WriteLine(nombre);
    }
}

// Uso
MostrarNombres("Juan", "Ana", "Luis");
MostrarNombres(); // también es válido
```
