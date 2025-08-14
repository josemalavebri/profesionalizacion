---
sr-due: 2025-08-16
sr-interval: 2
sr-ease: 190
---

#tipo-documento #review #lectura  
## Esencia semántica
Determinar en qué capa —procedimiento almacenado (SP) o capa de servicio— debe ubicarse la lógica de filtrado de datos, según su naturaleza, alcance y contexto de uso dentro de una aplicación.
En una arquitectura de software que utiliza procedimientos almacenados para el acceso a datos, el filtrado de registros puede implementarse en dos niveles:
1. **En el SP**: se ejecuta directamente en la base de datos, devolviendo solo los registros que cumplen condiciones específicas.
2. **En la capa de servicio**: el SP devuelve un conjunto más amplio de datos y el filtrado se realiza en la aplicación, antes de que la información sea utilizada o presentada.
## Puntos clave
- **Filtro universal** → corresponde a la definición base de los datos y se debe aplicar en el SP.
- **Filtro contextual** → varía según el caso de uso y se debe aplicar en la capa de servicio.
- SP más filtrado = menor tráfico de datos y más rendimiento.
- Filtros en la capa de servicio = mayor flexibilidad y reutilización del SP para múltiples escenarios.
- Una decisión incorrecta de ubicación del filtro puede provocar duplicación de lógica o pérdida de flexibilidad.

## Características
- **SP con filtrado universal**
    - Menos datos enviados a la aplicación.
    - Filtros consolidados y consistentes en todos los puntos de acceso.
    - Modificar el filtro implica cambios en la base de datos y despliegue del SP.
- **Servicio con filtrado contextual**
    - Posibilidad de aplicar múltiples combinaciones de filtros según el módulo.
    - Independencia de cambios en reglas de negocio respecto a la base de datos.
    - Potencial mayor consumo de memoria si el conjunto base es grande.
## Analogía
> *Piensa en un restaurante que recibe pedidos:
- **SP con filtro universal**: el chef ya sabe que el plato siempre se sirve sin sal y cocina así desde la cocina. No importa quién lo pida, siempre será sin sal.
- **Filtro en servicio**: el chef cocina el plato estándar y el mesero decide en cada pedido si añadir sal o no, según el cliente.*
## Ejemplo Contextual
**Filtro universal en SP**:
- Regla: “Un cliente válido siempre debe estar activo y con suscripción pagada.”
- SP :
```sql
SELECT * 
FROM Users
WHERE IsActive = 1
  AND SubscriptionPaid = 1

```
**Filtro contextual en servicio**:
- SP devuelve todos los usuarios activos:
```sql
SELECT * 
FROM Users
WHERE IsActive = 1
```
+ Servicio aplica regla adicional solo para cierto módulo:
```c#
var activos = _userRepository.GetActiveUsers();
var conPago = activos.Where(u => u.SubscriptionPaid);
```