---
sr-due: 2025-08-17
sr-interval: 3
sr-ease: 210
---

#tipo-documento #review  #lectura
## Módulos (`NgModule`)**
- Cada app Angular tiene un módulo raíz
	-  (`AppModule`).
- Los módulos agrupan 
	- componentes, directivas, pipes y servicios relacionados.
- Permiten dividir la app en **módulos funcionales** 
	- (feature modules), 
	- **módulos compartidos** 
		- (`SharedModule`) 
	- y **módulos de routing** 
		- (`AppRoutingModule`).
- Soportan **lazy loading**, cargando módulos solo cuando se necesitan para optimizar rendimiento.
## Componentes (`Component`)**
- Son la unidad de construcción de la UI. Cada componente tiene:
    - **Template (HTML):** 
        - define la estructura visual.
    - **Style (CSS/SCSS):** 
        - define la apariencia.
    - **Class (TypeScript):**
        -  contiene la lógica, propiedades y métodos.
- Se comunican con otros componentes mediante:
    - **@Input():** 
        - recibe datos desde un componente padre.
    - **@Output():**
        -  emite eventos hacia un componente padre.
- Funcionan conceptualmente como un 
	- **ViewModel**, manejando datos que se muestran 
		- en la vista.
## **Servicios (`Service`)**
- Clases que encapsulan 
	- **lógica de negocio o acceso a datos** (APIs, almacenamiento local, manipulación de datos).
- Se registran en el **sistema de inyección de dependencias**
	-  (`providedIn: 'root'`)
	-  para que estén disponibles 
		- globalmente 
	- o en un 
		- módulo específico.
- Evitan duplicar lógica y permiten 
	- **reutilización** entre múltiples componentes.
	    
## **Rutas (`RouterModule`)**
- Permiten navegación declarativa dentro de la app.
- Cada ruta define:
    - **path:** URL asociada.
    - **component:** componente a renderizar.
    - Opcionalmente, **guards** para proteger rutas.
- Facilitan el **lazy loading**, cargando módulos solo al acceder a ciertas rutas.
## **Directivas y Pipes**
- **Directivas:** cambian la apariencia o comportamiento del DOM.
    - Estructurales (`*ngIf`, `*ngFor`) agregan/eliminan elementos.
    - Atributo (`[ngStyle]`, `[ngClass]`) modifican estilos o clases.
- **Pipes:** transforman datos en la vista, como formatear fechas, números o cadenas (`{{ fecha | date:'short' }}`).
## **Otros elementos importantes**
- **Environment files:** configuración según ambiente (desarrollo, producción).
- **Assets:** imágenes, fuentes y otros recursos estáticos.
- **Angular CLI files (`angular.json`, `tsconfig.json`):** configuran compilación, rutas y dependencias.