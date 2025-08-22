---
sr-due: 2025-08-23
sr-interval: 4
sr-ease: 270
---
 #review  

**Tema General**: [[Arquitectura de software]] de Aplicaciones y [[Lógica de Presentación]]
## Esencia semántica
+ El patrón **MVVM (Model-View-ViewModel)** es una arquitectura de software que separa la lógica de presentación de la interfaz de usuario, facilitando la mantenibilidad, testeo y escalabilidad de aplicaciones. 
+ Su existencia busca **organizar responsabilidades**: los datos y reglas de negocio en el modelo, la UI en la vista y la lógica que conecta ambos en el ViewModel. MVVM surge para **automatizar la comunicación bidireccional** entre UI y datos mediante binding, especialmente en entornos como WPF, Xamarin y Blazor.

+ **MVVM divide una aplicación en tres componentes:**
	- **Model**: Representa los datos y la lógica de negocio. Es independiente de la UI.
	- **View**: Interfaz de usuario, únicamente muestra datos y recibe interacciones. No contiene lógica de negocio.
	- **ViewModel**: Puente entre Model y View. Contiene **la lógica de presentación**, comandos, validaciones y preparación de datos para la UI. Permite que la vista se actualice automáticamente cuando los datos cambian.
## Puntos clave
- Separación clara de responsabilidades.
- Facilita pruebas unitarias de la lógica de presentación sin depender de la UI.
- Soporta binding bidireccional: cambios en la UI actualizan el ViewModel y viceversa.
- La vista se mantiene simple, delegando toda la manipulación y validación al ViewModel.
- Ideal para aplicaciones ricas en UI, donde los datos cambian dinámicamente.
## Características
- **Binding automático** entre View y ViewModel.
- **Comandos y notificaciones** que reemplazan los eventos directos de UI.
- **Testable**: la lógica de presentación puede testearse sin instanciar la vista.
- **Escalable y mantenible**: separar lógica evita código monolítico en la U
## Analogía
> *MVVM es como un restaurante:

- **Modelo**: la cocina, donde se preparan los platos (datos y reglas).
- **Vista**: el comensal, que solo ve y disfruta la comida (UI).
- **ViewModel**: el camarero, que traduce pedidos, organiza los platos y se asegura de que todo llegue correctamente, adaptando la presentación según el cliente.*
## Ejemplos

- Una aplicación de inventario:
    
    - **View**: Muestra un formulario con campos para ingresar producto.
        
    - **ViewModel**: Valida que los nombres no estén vacíos, calcula descuentos y prepara los datos para guardar.
        
    - **Model**: Almacena productos en la base de datos.
        
- Si el usuario cambia el nombre del producto en la UI, el ViewModel recibe la actualización automáticamente y puede habilitar o deshabilitar botones según las reglas de negocio.
