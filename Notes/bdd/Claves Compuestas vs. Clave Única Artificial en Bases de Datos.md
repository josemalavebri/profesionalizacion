
#noEstructurado
#### Tema: Modelado de Claves Primarias

---

**Esencia Semántica:**  
Las claves primarias existen para identificar de forma única cada registro en una tabla. Existen dos enfoques principales: usar **claves compuestas (naturales)** o un **ID único artificial (surrogate key)**.

---

**Concepto:**  
Una **clave compuesta** se forma combinando dos o más columnas que, juntas, garantizan unicidad. Una **clave surrogate** usa un campo artificial (generalmente un número autoincremental o GUID) como identificador único.

---

**Puntos Clave:**

- Las claves compuestas reflejan la **realidad natural del negocio**.
    
- Las surrogate keys simplifican las relaciones y mejoran el **rendimiento en joins**.
    
- Lo ideal en diseño moderno: **usar surrogate key como PK y UNIQUE en la combinación natural**.
    

---

**Características:**

- **Clave compuesta:** múltiple, dependiente de atributos naturales, puede volver más pesados los índices y complicar las relaciones.
    
- **Surrogate key:** artificial, liviana, eficiente en consultas, pero necesita restricciones adicionales para evitar duplicados lógicos.
    

---

**Analogía:**  
Imagina un torneo de fútbol:

- Una **clave compuesta** sería identificar un partido por “Equipo A + Equipo B + Fecha”.
    
- Una **clave surrogate** sería darle un **número de partido (ID)**, y aparte imponer una regla para que no se repita la misma combinación de equipos en la misma fecha.
    

---

**Ejemplo de Sintaxis (Genérica):**

```sql
-- Con surrogate key (recomendado)
CREATE TABLE Matricula (
    id INT PRIMARY KEY IDENTITY,
    idAlumno INT NOT NULL,
    idCurso INT NOT NULL,
    fecha DATE NOT NULL,
    CONSTRAINT UQ_Matricula UNIQUE (idAlumno, idCurso)
);

-- Con clave compuesta
CREATE TABLE Matricula (
    idAlumno INT NOT NULL,
    idCurso INT NOT NULL,
    fecha DATE NOT NULL,
    PRIMARY KEY (idAlumno, idCurso)
);

```

**Ejemplo en Uso (Dominio):**  
En un sistema académico, la matrícula de un alumno en un curso puede identificarse de dos formas:

- **Clave compuesta:** `(idAlumno, idCurso)` = identifica la matrícula.
    
- **Surrogate key:** `id = 12345` como PK, y restricción `UNIQUE (idAlumno, idCurso)` para garantizar unicidad lógica.