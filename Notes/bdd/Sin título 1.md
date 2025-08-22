
## Modelado de Bases de Datos

El **modelo lógico** es la **traducción del modelo conceptual a un esquema que pueda implementarse en un sistema de gestión de bases de datos (SGBD)**, pero aún **independiente de la tecnología específica**.

### Definición y Propósito

+ Representa 
	+ **cómo se organizarán los datos en tablas**, 
+ Representa qué campos
	+  tendrán y cómo se relacionarán.
+ Permite **validar la consistencia, integridad y normalización** antes de crear físicamente la base de datos.
    
+ Sirve como **puente entre el modelo conceptual y el modelo físico**.

### Elementos Clave

1. **Tablas:** Correspondientes a entidades del modelo conceptual.
    
2. **Columnas:** Atributos de las entidades, con tipo de dato definido.
    
3. **Claves Primarias (PK):** Identificadores únicos de cada tabla.
    
4. **Claves Foráneas (FK):** Conectan tablas para reflejar relaciones.
    
5. **Restricciones:** Reglas de integridad (no nulo, único, etc.).

### Características

+ **Independiente de SGBD específico**, pero ya define estructuras y tipos de datos.
    
+ **Normalizado:** Reduce redundancia y mejora consistencia.
    
+ **Preparado para implementación:** Facilita pasar al modelo físico.

### Analogía

Es como dibujar **los planos técnicos de la casa**, ya con medidas, habitaciones y puertas definidas, pero sin elegir materiales ni colores.
