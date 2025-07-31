---
sr-due: 2025-08-08
sr-interval: 9
sr-ease: 230
---

#review 
#### 1. **Definición de Categorías por Área**
Cada **área registrada** puede tener una o más **categorías temáticas** que agrupan las preguntas según el tipo de tratamiento que realizan. 
+ Ejemplo de categorías:
	- Seguridad de almacenamiento digital
	- Manejo de documentos físicos

**Acciones del módulo:**
- Crear categorías personalizadas para un área específica.
- Reutilizar categorías existentes en otras áreas si son aplicables.
- Asignar un orden a las categorías para mostrarlas secuencialmente en el formulario.
#### 2. **Creación de Preguntas por Categoría**
Las preguntas son **dinámicas** y específicas para cada combinación de área + categoría.
**Elementos configurables por pregunta:**
- Texto de la pregunta.
- Subpreguntas
- Tipo de respuesta:
    - Sí/No.
    - Colapsar las preguntas que se relacionan al no o al sí

**Acciones del módulo:**
- Agregar preguntas a cualquier categoría de un área.
- Editar, eliminar o desactivar preguntas.
- Repetir categorías de preguntas si son similares
- Permitir añadir Subpreguntas en caso de ser necesario
- Definir valores de riesgo para cada opción de respuesta (por ejemplo, "Sí" = 0 puntos, "No" = 5 puntos).
	- En caso de que todas las preguntas tengan un puntaje similar estás se evaluarán de forma porcentual

**Extensión**:
- Guardar borradores y activar oficialmente la versión solo cuando esté lista
#### 3. **Visualización previa por área**
Antes de habilitar una encuesta, los administradores pueden:
- Ver cómo se mostrará la encuesta completa según el área.
### Relaciones clave (lógicas)
- Un **área** tiene muchas **categorías**.
- Una **categoría** pertenece a un área y tiene muchas **preguntas**.
- Cada **pregunta** tiene 2 **respuestas posibles**.
	- Pueden tener valores de riesgos o estar divididas en porcentaje

**Ejemplo de flujo de uso:**
1. Se crea el área **"Departamento Médico y facultad "** esto se tiene que realizar antes y en otro módulo
2. Se agregan las categorías:
    - “Consentimiento informado”
    - “Acceso a historiales”
3. Para cada categoría, se crean preguntas con sus posibles respuestas y valores de riesgo.
4. Se activa la versión 1 de la encuesta.
5. El responsable del área responde según su operación actual.
6. Se calcula y almacena el riesgo con base en las respuestas de esa versión.