---
sr-due: 2025-08-19
sr-interval: 1
sr-ease: 230
---

#review 
**Tema general:** Arquitectura de software y flujo de dependencias:

La arquitectura hexagonal difiere de los modelos tradicionales como MVC o N-tier principalmente en **dependencias y flexibilidad**:

- **Flujo de dependencias:**
    - **MVC/N-tier:** La capa superior depende de la inferior (UI → Aplicación → Datos). Cambiar la base de datos o la UI puede afectar el dominio.
    - **Hexagonal:** La capa de dominio es independiente; define _interfaces_ (_puertos_) y no conoce la infraestructura. Los adaptadores externos implementan estas interfaces.
        
- **Acoplamiento:**
    - **MVC/N-tier:** Alto acoplamiento entre capas; el dominio puede depender de la base de datos o de la UI indirectamente.
    - **Hexagonal:** Bajo acoplamiento; la lógica de negocio se mantiene aislada y testeable.
        
- **Pruebas:**
    - **MVC/N-tier:** Más complejo, requiere configurar la infraestructura para pruebas unitarias.
    - **Hexagonal:** Se pueden usar adaptadores simulados para pruebas unitarias sin depender de infraestructura real.
        
- **Flexibilidad tecnológica:**
    - **MVC/N-tier:** Cambios en tecnologías externas (DB, UI, servicios) pueden requerir modificar la lógica de negocio.
    - **Hexagonal:** Cambios en adaptadores no afectan la lógica central; puedes reemplazar tecnologías fácilmente.
        
- **Reutilización de la lógica:**
    - **MVC/N-tier:** Limitada a la misma aplicación o capa superior.
    - **Hexagonal:** La misma lógica puede exponerse a distintos canales (web, móvil, API).
