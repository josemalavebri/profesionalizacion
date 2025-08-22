#noEstructurado #bdd/modelado 
#### Tema: Normalización y Relaciones N:M

---

### **Esencia Semántica**

La **4ta forma normal (4FN)** busca eliminar dependencias multivaluadas. Cuando un empleado tiene varios lenguajes y varias habilidades (skills), si todo se guarda en una sola tabla, se generan redundancias y combinaciones innecesarias. Para resolverlo se utilizan **tablas puente** que permiten modelar relaciones muchos a muchos (N:M).

---

### **Concepto**

Las **tablas intermedias** o de relación existen para conectar entidades principales en relaciones N:M. En este caso:

- Un **Empleado** puede hablar varios **Lenguajes**, y un **Lenguaje** puede pertenecer a varios empleados.
    
- Un **Empleado** puede tener varias **Skills**, y una **Skill** puede pertenecer a varios empleados.  
    Esto obliga a usar tablas puente (`EmpleadoLenguaje`, `EmpleadoSkill`) con claves foráneas hacia las tablas principales.
    

---

### **Puntos Clave**

- Un **Empleado** no debe almacenar directamente todos sus lenguajes o skills en la misma fila.
    
- Se crean **catálogos** (`Lenguaje`, `Skill`).
    
- Se crean **tablas puente** para relacionar empleados con catálogos.
    
- Las **FK** van de la tabla puente hacia las tablas principales, nunca al revés.
    

---

### **Características**

- Las tablas puente suelen tener **PK compuesta** (`EmpleadoID`, `LenguajeID`) o un **ID artificial**.
    
- Evitan redundancia y mantienen independencia de atributos.
    
- Permiten escalar fácilmente cuando crecen los catálogos de lenguajes o skills.
    
- Garantizan integridad referencial entre empleados y sus atributos.
    

---

### **Analogía**

Piensa en un **estudiante** inscrito en **cursos** y **talleres**.

- Los cursos y talleres son listas separadas (catálogos).
    
- El estudiante no guarda directamente todo lo que toma.
    
- Lo que hace es **apuntarse** en listas de inscripción, que son las **tablas puente**.
### **Ejemplo de Sintaxis (Genérica/Abstracta)**
```sql
CREATE TABLE Empleado (
    EmpleadoID INT PRIMARY KEY,
    Nombre NVARCHAR(100)
);

CREATE TABLE Lenguaje (
    LenguajeID INT PRIMARY KEY,
    NombreLenguaje NVARCHAR(100)
);

CREATE TABLE EmpleadoLenguaje (
    EmpleadoID INT,
    LenguajeID INT,
    PRIMARY KEY (EmpleadoID, LenguajeID),
    FOREIGN KEY (EmpleadoID) REFERENCES Empleado(EmpleadoID),
    FOREIGN KEY (LenguajeID) REFERENCES Lenguaje(LenguajeID)
);

CREATE TABLE Skill (
    SkillID INT PRIMARY KEY,
    NombreSkill NVARCHAR(100)
);

CREATE TABLE EmpleadoSkill (
    EmpleadoID INT,
    SkillID INT,
    PRIMARY KEY (EmpleadoID, SkillID),
    FOREIGN KEY (EmpleadoID) REFERENCES Empleado(EmpleadoID),
    FOREIGN KEY (SkillID) REFERENCES Skill(SkillID)
);

```

```sql
-- Insertamos empleados
INSERT INTO Empleado VALUES (1, 'Juan'), (2, 'María');

-- Insertamos lenguajes
INSERT INTO Lenguaje VALUES (1, 'C#'), (2, 'Java');

-- Insertamos skills
INSERT INTO Skill VALUES (1, 'Liderazgo'), (2, 'Comunicación');

-- Relacionamos empleados con lenguajes
INSERT INTO EmpleadoLenguaje VALUES (1, 1), (1, 2), (2, 1);

-- Relacionamos empleados con skills
INSERT INTO EmpleadoSkill VALUES (1, 1), (1, 2), (2, 2);

```

Con estas inserciones:

- Juan (1) habla C# y Java, y tiene Liderazgo y Comunicación.
    
- María (2) habla C#, y tiene Comunicación.