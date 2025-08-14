---
sr-due: 2025-08-15
sr-interval: 1
sr-ease: 210
---

#tipo-documento #review  #lectura

En Angular, cuando se habla de “Angular Way” se refiere a **hacer las cosas siguiendo la filosofía y las buenas prácticas propias de Angular**, en lugar de implementar soluciones “a la antigua” o copiadas de otros frameworks. Es una forma de decir: “hazlo como Angular espera que lo hagas”.

Algunos puntos clave del Angular Way:
- **Componentes y modularidad**: 
	- separar la UI en componentes pequeños y reutilizables. Cada componente tiene su TS (lógica), HTML (vista) y CSS (estilo). Esto mantiene el código limpio y mantenible.
- **Data binding y directivas**: 
	- usar correctamente `@Input`, `@Output`, `ngModel`, `ngIf`, `ngFor` en lugar de manipular el DOM manualmente.
- **Servicios e inyección de dependencias**: 
	- lógica compartida y acceso a datos se hace mediante servicios, no dentro de los componentes directamente.
- **Reactive forms y observables**: 
	- para formularios y flujos de datos, usar `ReactiveFormsModule` y `RxJS` en lugar de manejar datos manualmente o con jQuery.
- **Routing y lazy loading**: 
	- usar el router de Angular para navegar entre vistas y cargar módulos bajo demanda.
## Lista de recomendaciones del tipo angular way
- Separar la lógica en **componentes** pequeños y reutilizables.
- Mantener la **vista (HTML)**, la **lógica (TS)** y el **estilo (CSS/SCSS)** separados.
- Usar **servicios** para toda la lógica de negocio y acceso a datos.
- Aprovechar la **inyección de dependencias** para pasar servicios a componentes.
- Utilizar **data binding declarativo** (`[property]`, `(event)`, `[(ngModel)]`) en lugar de manipular el DOM.
- Usar **observables y RxJS** para manejar datos asincrónicos y flujos de eventos.
- Implementar **formularios reactivos** (`ReactiveFormsModule`) para validaciones complejas.
- Crear **módulos** (`CoreModule`, `SharedModule`, módulos de características) para organizar el proyecto.
- Aplicar **lazy loading** en módulos grandes para optimizar el rendimiento.
- Gestionar la navegación con **Angular Router** y mantener rutas limpias y coherentes.
- Evitar manipular elementos directamente con `document` o `jQuery`.
- Mantener **estilo consistente** y nomenclatura clara en nombres de archivos, componentes y servicios.
- Hacer **tests unitarios y de integración** para componentes y servicios.