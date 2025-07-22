## Enunciado del ejercicio
Vas a simular el **sistema de acceso a un edificio corporativo**.
El sistema verifica los siguientes aspectos antes de permitir el ingreso:
- ¿Es empleado? → `esEmpleado`
- ¿Tiene pase de acceso? → `tienePase`
- ¿Llega fuera del horario laboral? → `fueraHorario`
- ¿Tiene autorización especial para ingresar fuera de horario? → `tienePermisoEspecial`

## Resolución

```c#
TimeSpan horaEntrada = new TimeSpan(6, 0, 0);
TimeSpan horaSalida = new TimeSpan(15, 0, 0);
DiaSemana diasLaborales = DiaSemana.Lunes | DiaSemana.Miercoles | DiaSemana.Viernes;

Permiso[] permisos = new Permiso[] { Permiso.PaseAcceso, Permiso.FueraHorarioLaboral };
Horario horario = new Horario(horaEntrada, horaSalida, diasLaborales);
Empleado empleado = new Empleado(horario, permisos);

if (empleado.TienePermisos(Permiso.FueraHorarioLaboral, Permiso.PaseAcceso))
{
    Console.WriteLine("Tiene los permisos");
}
else
{
    Console.WriteLine("No tienes los permisos");
}

class Empleado
{
    public Horario Horario { get; }
    private HashSet<Permiso> permisos;

    public Empleado(Horario horario, Permiso[] permisos)
    {
        Horario = horario;
        this.permisos = new HashSet<Permiso>(permisos);
    }

    public bool TienePermisos(params Permiso[] permisosSolicitados)
    {
        return permisosSolicitados.All(p => permisos.Contains(p));
    }
}

class Horario
{
    public TimeSpan HoraEntrada { get; }
    public TimeSpan HoraSalida { get; }
    public DiaSemana DiasLaborales { get; }

    public Horario(TimeSpan horaEntrada, TimeSpan horaSalida, DiaSemana diasLaborales)
    {
        HoraEntrada = horaEntrada;
        HoraSalida = horaSalida;
        DiasLaborales = diasLaborales;
    }
}

[Flags]
enum DiaSemana
{
    Ninguno = 0,
    Lunes = 1,
    Martes = 2,
    Miercoles = 4,
    Jueves = 8,
    Viernes = 16,
    Sabado = 32,
    Domingo = 64
}

enum Permiso
{
    PaseAcceso,
    FueraHorarioLaboral,
}
```