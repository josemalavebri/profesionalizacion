+ No corregido

```SQL
Table Ubicacion {
  IdUbicacion int [pk, increment]
  Nombre nvarchar(100)
}

Table Facultad {
  IdFacultad int [pk, increment]
  Nombre nvarchar(100)
}

Table Departamento {
  IdDepartamento int [pk, increment]
  Nombre nvarchar(100)
  IdFacultad int [ref: > Facultad.IdFacultad]
}

Table UbicacionInstitucional {
  IdUbicacionInstitucional int [pk, increment]
  IdUbicacion int [ref: > Ubicacion.IdUbicacion]
  IdFacultad int [ref: > Facultad.IdFacultad]
  IdDepartamento int [ref: > Departamento.IdDepartamento]
}

Table Rol {
  IdRol int [pk, increment]
  Nombre nvarchar(50)
}

Table Persona {
  IdPersona int [pk, increment]
  Nombre nvarchar(100)
  Correo nvarchar(100)
  IdRol int [ref: > Rol.IdRol]
}

Table Seccion {
  IdSeccion int [pk, increment]
  Nombre nvarchar(100)
}
  
Table Pregunta {
  IdPregunta int [pk, increment]
  Texto nvarchar(300)
  IdSeccion int [ref: > Seccion.IdSeccion]
}

Table Item {
  IdItem int [pk, increment]
  Descripcion nvarchar(200)
  IdPregunta int [ref: > Pregunta.IdPregunta]
}

Table Catalogo {
  IdCatalogo int [pk, increment]
  Titulo nvarchar(100)
  FechaCreacion date
}

Table Auditoria {
  IdAuditoria int [pk, increment]
  Titulo nvarchar(100)
  IdCatalogo int [ref: > Catalogo.IdCatalogo]
  IdUbicacionInstitucional int [ref: > UbicacionInstitucional.IdUbicacionInstitucional]
  Fecha date
}

Table Encuesta {
  IdEncuesta int [pk, increment]
  IdAuditoria int [ref: > Auditoria.IdAuditoria]
  IdPersona int [ref: > Persona.IdPersona]
  FechaRealizacion date
}

Table Respuesta {
  IdRespuesta int [pk, increment]
  IdEncuesta int [ref: > Encuesta.IdEncuesta]
  IdItem int [ref: > Item.IdItem]
  Valor nvarchar(50)
}

Table Seguimiento {
  IdSeguimiento int [pk, increment]
  IdRespuesta int [ref: > Respuesta.IdRespuesta]
  Estado nvarchar(50)
  Descripcion nvarchar(500)
  Supervisor nvarchar(100)
  ResponsableTratamiento nvarchar(100)
  ResponsableImplementacion nvarchar(100)
  Evidencia nvarchar(500)
  FechaInicio date
  FechaFin date
  ObservacionEstado nvarchar(500)
}

Table Reporte {
  IdReporte int [pk, increment]
  IdSeguimiento int [ref: > Seguimiento.IdSeguimiento]
  Titulo nvarchar(100)
  Detalles nvarchar(4000)
  FechaReporte date
}
```