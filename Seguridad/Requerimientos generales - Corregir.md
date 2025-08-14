---
sr-due: 2025-08-07
sr-interval: 8
sr-ease: 230
---

### Revisión - Módulo de Gestión de Áreas
**Funcionalidad clave:**
- Registrar y editar áreas de la facultad 
	- nombre, descripción, ubicación funcional.
- Asignar responsables o coordinadores.
- Listado de todas las áreas con su estado de evaluación 
	- encuesta respondida o pendiente.

**Nota**:
+ Esto se puede hacer con la base de datos de la universidad que seguramente ya tiene esos datos
### Módulo de Creación Dinámica de Preguntas para Evaluación de Riesgos por Área
**Funcionalidad clave:**
+ Cada **área registrada** puede tener una o más **categorías temáticas** 
+ Se agrupan las preguntas según el tipo de tratamiento que realizan. 
+ Creación de Preguntas por Categoría
+ Se pueden reciclar las categorías 
+ Las preguntas son **dinámicas** y específicas para cada combinación de área + categoría.
### Módulo de Aplicación de Encuesta
**Funcionalidad clave:**
- Mostrar las preguntas ya definidas y permitir que el responsable del área responda el cuestionario o el coordinador de la auditoría.
- Registrar cada respuesta vinculada al área.
- Permitir revisión solo antes de enviar.
- Asociar automáticamente puntajes de riesgo o porcentaje general a las respuestas para procesarlos luego.

**Extensión**
- Controlar que cada área solo responda una encuesta por período o de forma completa
	- Esto permitirá un bloqueo de duplicados
### Sub-Módulo de Resultados y Cálculo de Riesgo**
**Funcionalidad clave:**
- Procesar las respuestas para calcular un **puntaje total**.
- Clasificar el riesgo en niveles: Bajo, Medio, Alto.
	- Esta clasificación puede variar o puede no estar
- Guardar y vincular el resultado con el área evaluada.
- Mostrar resumen por área: 
	- Número de respuestas, puntaje total, nivel de riesgo.

**Extensión**:
- Soporte para múltiples evaluaciones por área en diferentes fechas (historial).
	- Esto requerirá que el area vaya mejorando su infraestructura de manejo de los datos 
		- Esto provocará también cambios en como se gestionan las encuestas ya que ahí si requerirá que se hagan encuestas periódicamente o en fechas establecidas
### **Módulo de Reportes e Indicadores**
**Funcionalidad clave:**
- Visualización de resultados por área (gráfico de barras, colores de semáforo, listas ordenadas por riesgo).
- Filtros por nivel de riesgo, área, o estado (evaluada/no evaluada).
- Exportar resultados por área en PDF o Excel.
- Generar comparativos por períodos si se hacen evaluaciones periódicas.
- Visualizar evolución de riesgo en un área específica a lo largo del tiempo.