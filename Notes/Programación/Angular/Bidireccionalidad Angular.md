---
sr-due: 2025-08-15
sr-interval: 1
sr-ease: 230
---

#tipo-documento #review  
## Esencia semántica
+ La bidireccionalidad en Angular se refiere a la capacidad de 
	+ sincronizar automáticamente datos entre 
		+ la **vista** (HTML) 
	+ y el 
		+ **componente** (TypeScript), 
+ Cuando esto se realiza los cambios de uno se reflejan en el otro sin necesidad de 
	+ actualizar manualmente ambos. 
+ Este mecanismo se conoce como 
	+ **two-way data binding**.
## Puntos clave
- Permite que los datos fluyan en **dos direcciones**: 
	- del componente a la vista y de la vista al componente.
- Facilita la interacción con formularios y elementos del 
	- DOM de manera reactiva.
- Angular implementa la bidireccionalidad combinando
	-  **property binding**
		-  (`[propiedad]`)
	-  y **event binding** 
		- (`(evento)`), 
	- simplificado con 
		- `[(ngModel)]`.


## Características
- Angular detecta cambios y actualiza la vista o el modelo según corresponda.
	- Automática:
- Se usa principalmente a través de la directiva `ngModel`.
	- Integrada
- `ngModel` permite mantener estados como `valid`, `dirty`, `pristine` para formularios.
	- Validación y control: 
- funciona con inputs, selects, textareas y componentes personalizados que implementen `ControlValueAccessor`.
	 + Flexible
## Analogía
> *Es como un espejo: si cambias algo en el objeto real, el reflejo cambia; si cambias algo en el reflejo, el objeto real también cambia.*
## Ejemplos
### Sintaxis 
```c
<input [(ngModel)]="nombre">
```
### Uso
```c#
export class AppComponent {
  nombre = 'Robert';
}
<input [(ngModel)]="nombre" placeholder="Ingresa tu nombre">
<p>Hola, {{nombre}}!</p>
```

+ Si el usuario escribe "José", el `<p>` se actualiza automáticamente a "Hola, José!" sin intervención adicional.