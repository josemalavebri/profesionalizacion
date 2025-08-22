---
sr-due: 2025-08-20
sr-interval: 4
sr-ease: 190
---
 #review
**Tema general:** [[Arquitectura de software]] de software y manejo eficiente de datos
## **Filtrado en SP (Procedimiento Almacenado)**
- **Qué es:** Lógica de filtrado que siempre se aplica, directamente en la base de datos.
- **Ventajas:** Menos datos transferidos, consistencia en todos los puntos de acceso.
- **Desventajas:** Menos flexible, cambios requieren redeploy del SP.
- **Ejemplo:** Solo clientes activos con suscripción pagada:

```sql
SELECT * FROM Users
WHERE IsActive = 1
  AND SubscriptionPaid = 1

```

## **Filtrado en la capa de servicio**
- **Qué es:** Lógica de filtrado que depende del contexto o módulo, aplicada en la aplicación.
- **Ventajas:** Alta flexibilidad, reutilización del mismo SP para distintos escenarios.
- **Desventajas:** Puede consumir más memoria si el conjunto base es grande, riesgo de duplicar reglas.
- **Ejemplo:** SP devuelve todos los activos, la aplicación filtra según módulo:

```sql
SELECT * FROM Users WHERE IsActive = 1

```

```c#
var activos = _userRepository.GetActiveUsers();
var conPago = activos.Where(u => u.SubscriptionPaid);
```
## **Regla práctica:**
- Reglas universales → SP
- Reglas contextuales → capa de servicio