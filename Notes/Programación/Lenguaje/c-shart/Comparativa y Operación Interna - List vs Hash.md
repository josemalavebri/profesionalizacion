## Tema general
**Estructuras de datos** – búsqueda, operación interna y casos de uso.
## Operación interna
**List**
- Recorre cada elemento secuencialmente hasta encontrar el deseado.
- Tiempo de búsqueda proporcional al número de elementos (**O(n)**).

**HashSet / Dictionary**
- Aplica una función hash a la clave para determinar un bucket.
- Accede directamente al bucket → búsqueda casi inmediata (**O(1)** promedio).
- Colisiones: si varias claves caen en el mismo bucket, se hace una mini-búsqueda dentro de él.
## Percepción práctica de la búsqueda
| Cantidad de elementos | List                       | Hash          |
| --------------------- | -------------------------- | ------------- |
| 10–100                | Imperceptible / Muy rápida | Imperceptible |
| 1,000                 | Notoria                    | Imperceptible |
| 10,000                | Lenta                      | Imperceptible |
| 100,000               | Muy lenta                  | Imperceptible |
| 1,000,000             | Extremadamente lenta       | Imperceptible |
## Casos de uso comunes

- Listas grandes (>1,000 elementos) son útiles para:
    - Catálogos de productos o usuarios.
    - Logs y auditorías de sistemas.
    - Datos científicos, geográficos o médicos.
    - Historiales de mensajes, publicaciones o notificaciones.
    - Archivos multimedia o procesamiento ETL.
- Hashes ideales para:
    - Acceso rápido por clave.
    - Conteo de elementos únicos.
    - Manejo de grandes volúmenes de datos sin degradar rendimiento.