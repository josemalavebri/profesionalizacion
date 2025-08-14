#tipo-documento #review #lectura
## Esencia semántica
+ MVVM 
	+ (Model-View-ViewModel) 
+ Es un patrón de diseño que separa 
	+ la lógica de negocio, 
	+ la interfaz de usuario 
	+ y la lógica de presentación. 
+ En Angular, el **componente funciona como 
	+ ViewModel**, 
	+ la plantilla HTML como 
		+ View,
	+ los servicios o clases de datos como 
		+ Model. 
+ Permite que la vista y los datos estén sincronizados mediante 
	+ **data binding bidireccional**, 
## Puntos clave
- **Separación de responsabilidades:** La vista no contiene lógica de negocio; el componente maneja el estado y los métodos.
- **Binding bidireccional:** Cambios en el modelo actualizan la vista automáticamente y viceversa (`[(ngModel)]`).
- **Componente = ViewModel:** Expone propiedades y comandos que la vista puede consumir.
- **Escalabilidad y testeo:** Permite unit tests más limpios, ya que la lógica está separada del DOM.
- **Uso de servicios:** Para la lógica de negocio compleja y persistencia de datos, el componente puede delegar al Model.

## Características
- Refleja cambios automáticamente entre modelo y vista.
    
- Reduce necesidad de controladores explícitos.
    
- Facilita la mantenibilidad en aplicaciones grandes.
    
- La vista es declarativa y el componente maneja toda la interacción con el modelo.
## Analogía
> *El televisor (View) muestra lo que ocurre.
> El control remoto (ViewModel) sabe qué canal o volumen pedir y gestiona la interacción.
> La señal de televisión (Model) es el contenido que llega. La vista no cambia el contenido por sí misma; solo lo refleja según el estado del ViewModel.*
