---
sr-due: 2025-08-28
sr-interval: 9
sr-ease: 230
---
#review  

En Angular, cuando se habla de “Angular Way” se refiere a **hacer las cosas siguiendo la filosofía y las buenas prácticas propias de Angular**, en lugar de implementar soluciones “a la antigua” o copiadas de otros frameworks. Es una forma de decir: “hazlo como Angular espera que lo hagas”.
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