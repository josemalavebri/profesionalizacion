### Módulo de Gestión de Auditorías Institucionales

**Funcionalidad clave:**

- Crear y administrar auditorías por institución o área académica.
    
    - Se vincula con la ubicación institucional, el catálogo de evaluación y la fecha.
        
- Asociar ubicación institucional con facultad, departamento y ubicación física.
    
- Registrar información general de la auditoría (nombre, objetivos, fecha).
    

**Nota**:

- Se recomienda conectar con datos institucionales existentes (facultades, departamentos, ubicaciones) si ya existen en la base de datos universitaria.
    

---

### Módulo de Gestión de Catálogo y Secciones de Evaluación

**Funcionalidad clave:**

- Registrar y gestionar catálogos de auditoría.
    
    - Cada catálogo incluye secciones temáticas.
        
- Registrar secciones dentro de un catálogo.
    
- Asociar preguntas a secciones.
    
- Asociar ítems de respuesta a cada pregunta.
    
    - Se permiten ítems como: opciones múltiples, escala de valor, etc.
        

**Extensión**:

- Se pueden mantener catálogos históricos reutilizables por futuras auditorías.
    

---

### Módulo de Gestión de Personas y Roles

**Funcionalidad clave:**

- Registrar personas involucradas en el proceso de auditoría.
    
    - Datos mínimos: nombre, correo.
        
- Asignar roles (Supervisor, Responsable, Evaluador, etc.).
    
- Control de acceso o validación de funciones en el sistema según rol.
    

**Nota**:

- El mismo usuario podría tener múltiples roles dependiendo del contexto (auditor, evaluador, supervisor).
    

---

### Módulo de Aplicación de Encuestas por Auditoría

**Funcionalidad clave:**

- Asociar una encuesta a una auditoría y persona.
    
- Mostrar las preguntas del catálogo vinculado a la auditoría.
    
- Registrar respuestas por cada ítem seleccionado.
    
- Validación de respuestas antes del envío final.
    

**Extensión**:

- Controlar que una persona solo complete una encuesta por auditoría.
    
    - Evita duplicidad en registros.
        
- Registro de fecha y trazabilidad del llenado.
    

---

### Módulo de Seguimiento a Respuestas Críticas

**Funcionalidad clave:**

- Permite crear un plan de seguimiento para respuestas específicas.
    
    - Estado del tratamiento: Aceptar, Mitigar, Evitar.
        
- Registrar responsables de tratamiento e implementación.
    
- Describir el plan de acción, observaciones y evidencia del avance.
    
- Fechas de inicio y fin del seguimiento.
    

**Extensión**:

- El seguimiento puede derivar en un reporte de cumplimiento que se alimenta desde esta información.
    

---

### Módulo de Reportes y Resultados de Auditoría

**Funcionalidad clave:**

- Generar reportes vinculados a seguimientos.
    
    - Resumen de acciones tomadas, observaciones, responsables y estado.
        
- Reporte general por auditoría:
    
    - Total de encuestas aplicadas.
        
    - Número de seguimientos abiertos o cerrados.
        
    - Indicadores generales de cumplimiento.
        

**Extensión**:

- Exportar los reportes en formatos como PDF o Excel.
    
- Visualización de datos por filtros: facultad, departamento, período.