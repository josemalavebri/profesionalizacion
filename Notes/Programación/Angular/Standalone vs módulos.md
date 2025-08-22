---
sr-due: 2025-08-25
sr-interval: 6
sr-ease: 150
---
#review  
## Esencia semántica
+ En Angular, los **módulos (`NgModule`)** y los **componentes standalone** representan 
	+ Dos formas de organizar y estructurar la aplicación.
+ Los módulos actúan como contenedores que agrupan componentes, directivas, pipes y servicios, controlando su 
	+ visibilidad y dependencias.
+  Los componentes standalone son componentes independientes que **no necesitan estar dentro de un módulo**, simplificando 
	+ la estructura y facilitando la reutilización y carga perezosa.
---

## Puntos clave
+ Los **módulos (`NgModule`)** agrupan y encapsulan 
	+ componente directivas, pipes y servicios.
+ Un **componente encapsulado en un módulo** solo es visible dentro de 
	+ ese módulo, salvo que 
		+ se exporte explícitamente.
- Los **componentes standalone** se declaran con
	-  `standalone: true` 
- Los componentes standalone pueden importar directamente
	-  otros módulos o standalone components.
- Standalone permite arrancar la aplicación sin necesidad de un
	-  `AppModule`, usando `bootstrapApplication`.
- Modularización clásica protege y organiza el código; los standalone facilitan 
	- reutilización y simplificación de la estructura.
---

## Características
- contenedor, organiza y encapsula, controla exportaciones, depende de la declaración explícita de componentes.
	- módulo
- independiente, reutilizable, más fácil de importar en distintos contextos, no requiere módulos.
	- componente standalone
- controla qué componentes del módulo son visibles fuera de él.
	- **Encapsulación:** 
- tanto módulos como standalone components pueden importar otros módulos o componentes necesarios para funcionar.
	- imports
## Analogía
> *Piensa en los módulos como **cajas organizadoras**. Los componentes dentro de la caja están protegidos y ordenados; solo salen si los exportas. Un componente standalone es como **una herramienta independiente**, que puedes usar directamente donde quieras, sin depender de cajas.*
## Ejemplos
### Standalone 
```ts
import { Component } from '@angular/core';
import { CommonModule } from '@angular/common';

@Component({
  selector: 'app-ejemplo',
  templateUrl: './ejemplo.component.html',
  styleUrls: ['./ejemplo.component.css'],
  standalone: true,
  imports: [CommonModule]
})
export class EjemploComponent {}

```
### NgModule
```ts
@NgModule({
  declarations: [ComponenteA, ComponenteB],
  imports: [CommonModule],
  exports: [ComponenteA] // solo ComponenteA es visible fuera del módulo
})
export class MiModulo {}

```