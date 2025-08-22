#review 
**Enlaces**: [[Notes/Programación/Arquitectura/Arquitectura Hexagonal (Ports & Adapters)|Arquitectura Hexagonal (Ports & Adapters)]]
**Tema General**: Arquitectura de software y diseño orientado a dominio

- **Desacoplamiento del dominio:**  
    La lógica de negocio no depende de la infraestructura (base de datos, UI, servicios externos). Esto reduce el riesgo de cambios disruptivos.
    
- **Facilidad de pruebas unitarias:**  
    Se pueden crear _mocks_ o implementaciones simuladas de adaptadores sin tocar el dominio, haciendo pruebas más rápidas y confiables.
    
- **Flexibilidad tecnológica:**  
    Puedes cambiar la base de datos, servicios externos o interfaces de usuario sin afectar la lógica central.
    
- **Mantenibilidad y evolución:**  
    La separación de responsabilidades hace que el código sea más fácil de entender, mantener y extender.
    
- **Reutilización de la lógica de negocio:**  
    La misma lógica puede ser usada por diferentes canales: web, móvil, APIs, sistemas externos.
    
- **Promueve buenas prácticas de diseño:**  
    Fomenta SOLID y principios de diseño orientado a dominio, evitando dependencias circulares o acoplamientos fuertes.