 #review  

Enlaces: [[Diagramas]] | [[Diagrama de Secuencia]] | [[Diagrama de flujo]]
**Tema General**: Diagramación de Procesos y Comunicación
## Esencia Semántica
+ La elección entre usar `alt` en un [[diagrama de secuencia]] o un [[diagrama de flujo]] depende de si se quiere enfatizar la interacción entre actores/sistemas o solo la lógica interna del proceso. 
+ El `alt` permite mostrar decisiones que afectan la comunicación entre participantes, mientras que un diagrama de flujo representa la lógica de manera abstracta y secuencial.
- **Diagrama de Secuencia con `alt`**: Representa interacciones entre actores o sistemas, destacando decisiones que cambian el flujo de mensajes según condiciones.
- **Diagrama de Flujo**: Muestra la lógica interna de un algoritmo o proceso sin necesidad de detallar quién envía o recibe información.
## Puntos Clave
- `alt` se usa para condiciones que afectan la interacción entre actores.
- Diagrama de flujo se usa para decisiones internas del proceso.
- `alt` se visualiza como bloques condicionales en la secuencia de comunicación.
- Diagramas de flujo utilizan rombos y flechas para representar decisiones y ramificaciones.
## Características
| Aspecto        | Diagrama de Secuencia (alt)                          | Diagrama de Flujo                                            |
| -------------- | ---------------------------------------------------- | ------------------------------------------------------------ |
| Propósito      | Mostrar interacción según condiciones                | Mostrar secuencia de decisiones internas                     |
| Cuándo usar    | Decisión afecta quién envía o recibe mensajes        | Decisión solo interna del sistema                            |
| Visual         | Bloques condicionales (alt/else)                     | Rombos y flechas                                             |
| Ejemplo típico | Cliente → Sistema → BaseDeDatos según disponibilidad | Stock > 0 → descontar → enviar factura; sino → mostrar error |

## Analogía
> *Es como una conversación:

- **Diagrama de secuencia con `alt`**: Muestra cómo cada persona responde según la situación.
- **Diagrama de flujo**: Solo muestra qué pasos tomarías tú internamente sin que otros intervengan.*
## Ejemplos
**Secuencia con `alt`**
```json
sequenceDiagram
Actor1->>Actor2: Acción
alt Condición verdadera
    Actor2-->>Actor1: Respuesta 1
else Condición falsa
    Actor2-->>Actor1: Respuesta 2
end

```
**Diagrama de flujo**
```json
flowchart TD
A[Inicio] --> B{Condición?}
B -->|Sí| C[Acción 1]
B -->|No| D[Acción 2]
C --> E[Fin]
D --> E

```
### Ejemplo en Uso (Dominio)

+ **Secuencia con `alt`**  
	+ Visualiza cómo un Cliente solicita un servicio, el Sistema consulta disponibilidad en la BaseDeDatos, y la respuesta varía según la condición.

+ **Diagrama de flujo**  
	+ Representa la lógica interna: si hay disponibilidad se confirma el servicio; si no, se muestra un error, sin detallar quién envía o recibe mensajes.