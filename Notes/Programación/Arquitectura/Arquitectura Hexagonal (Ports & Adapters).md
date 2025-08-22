[[Arquitectura de software]]
# Temario
## Arquitectura Hexagonal (Ports & Adapters)
- [[Concepto y propósito]]
- [[Historia y evolución]]
- [[Comparación con capas tradicionales (MVC, N-tier)]]
## Dominio (Domain Layer)
- [[Definición y rol dentro del sistema]]
- [[Independencia de infraestructura y UI]]
- [[Encapsula la lógica de negocio]]
- [[Relación con entidades, servicios y puertos]]
## Entidades del Dominio
- [[Representación de objetos del negocio]]
- [[Propiedades y reglas básicas]]
- [[Ejemplos: User, Customer, Product, Order]]
- [[Inmutabilidad y consistencia]]
## Servicios de Dominio (Domain Services)
- [[Función de coordinar entidades y reglas de negocio]]
- [[Diferencia con entidades: comportamiento vs datos]]
- [[Casos de uso comunes]]
- [[Ejemplo: OrderService, UserService]]
## Puertos del Dominio (Interfaces / Ports)]]
- [[Puertos de entrada]]
- [[Puertos de salida]]
- [[Contratos y abstracciones]]
- [[Separación de responsabilidades y prueba unitaria]]
## Capa de Aplicación (Application Layer)
- [[Orquestación de casos de uso]]
- [[Coordinación entre servicios de dominio e infraestructura]]
- [[Exposición de servicios al mundo exterior (API, UI)]]
- [[Implementación de Dependency Injection]]
## Casos de Uso y Orquestación en la Aplicación
- [[Ejecución de flujos completos]]
- [[Coordinación de múltiples servicios de dominio]]
- [[Ejemplo: Crear orden, registrar usuario, procesar pago]]
## Infraestructura (Infrastructure Layer)
- [[Implementación concreta de los puertos del dominio]]
- [[Persistencia de datos: SQL, NoSQL, In-Memory]]
- [[Conexión con servicios externos: APIs, colas, correo]]
- [[Independencia de la lógica de negocio]]
## Implementación de Puertos por la Infraestructura
- [[Ejemplo de repositorios concretos]]
- [[Adaptadores que cumplen contratos del dominio]]
- [[Compatibilidad sin romper el dominio]]
## Flujo de Dependencias (Inversión de Dependencias)
- [[Principio de inversión de dependencias (DIP)]]
- [[Dominio no depende de infraestructura]]
- [[Aplicación decide qué adaptadores concretos usar]]
- [[Flujo conceptual: Infraestructura → Implementa puertos → Aplicación inyecta → Dominio usa]]
## [[Inyección de Dependencias]] en Arquitectura Hexagonal
- [[Constructor Injection vs Property Injection]]
- [[Contenedores de DI (Autofac, Microsoft.Extensions.DependencyInjection)]]
- [[Ventajas para pruebas unitarias y flexibilidad tecnológica]]
## Interacción entre Dominio, Aplicación e Infraestructura
- [[Flujo completo de un caso de uso]]
- [[Separación de responsabilidades y escalabilidad]]
- [[Aplicación como puente y coordinador]]

## Analogías para entender capas y dependencias

- [[Motor → Dominio]]
    
- [[Conductor → Aplicación]]
    
- [[Ruedas / Combustible / Carretera → Infraestructura]]
    
- [[Visualizar independencia y flujo de dependencias]]
    

## Coordinación de casos de uso desde la capa de Aplicación

- [[Ejecución secuencial de operaciones]]
    
- [[Validaciones y manejo de errores]]
    
- [[Orquestación de múltiples adaptadores y servicios de dominio]]
    

## Independencia tecnológica y testabilidad

- [[Cambiar bases de datos sin afectar la lógica de negocio]]
    
- [[Test unitarios sobre dominio sin infraestructura]]
    
- [[Simulación de adaptadores para pruebas]]