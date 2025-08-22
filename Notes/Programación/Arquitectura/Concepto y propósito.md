---
sr-due: 2025-08-25
sr-interval: 6
sr-ease: 230
---
 #review 
Enlaces: [[Notes/Programación/Arquitectura/Arquitectura Hexagonal (Ports & Adapters)]]

**Tema General**: [[Arquitectura de software]] de software y diseño de sistemas desacoplados

- **Concepto:**  
    Patrón de diseño que organiza una aplicación separando la **lógica de negocio** (dominio) de las **interfaces externas** (UI, base de datos, APIs). Utiliza **puertos** (interfaces) y **adaptadores** (implementaciones) para comunicar el dominio con el exterior sin acoplarlo.

- **Propósito:**
    - Mejorar la **mantenibilidad** del código.
    - Facilitar **tests unitarios** sin depender de infraestructura.
    - Permitir cambiar tecnologías externas (DB, UI, servicios) **sin afectar la lógica de negocio**.
    - Fomentar un diseño más **flexible y desacoplado**.
        
- **Ejemplo conceptual:**
    - Dominio define `IUserRepository` (puerto).
    - Infraestructura implementa `UserRepositorySql` (adaptador).
    - Aplicación usa `UserService` que depende de `IUserRepository`.