## Puntos clave
+ Es un tipo de valor 
+ Permite agrupar varios datos bajo un mismo nombre
+ Se usa para representar objetos como:
	+ Pequeños
	+ Ligeros
	+ Que cambian mucho
## Características
+ Se almacenan en el stack, no en el heap
+ No admiten herencia
+ Tienen constructores pero
	+ No se puede definir uno sin parámetro
		+ El compilador lo genera por defecto
+ Su cuerpo puede estar compuesto de:
	+ Campos
	+ Propiedades
	+ Métodos
	+ Constructores
+ Se copian por valor, no por referencia
+ Son inmutables por convención aunque
	+ No es obligatorio
## Analogía

> *Usar un `struct` es como anotar un dato en una libreta que tienes en el bolsillo: lo escribes, lo lees y lo tiras rápido si ya no lo necesitas. Todo está contigo, no depende de nadie. En cambio, usar una clase (`class`) es como guardar ese mismo dato en una caja fuerte en otro cuarto: tienes que ir, pedir la llave, abrirla, y cuando ya no lo necesitas, alguien más debe encargarse de borrarlo. Así, los `struct` son ideales para datos pequeños que necesitas manejar rápido y sin complicaciones.*
## Ejemplo
### Creación
```c
public struct Punto2D
{
    public int X;
    public int Y;

    public Punto2D(int x, int y)
    {
        X = x;
        Y = y;
    }

    public double DistanciaAlOrigen()
    {
        return Math.Sqrt(X * X + Y * Y);
    }
}

```
### Uso
```c#
// Uso
Punto2D p1 = new Punto2D(3, 4);
double distancia = p1.DistanciaAlOrigen();  // Resultado: 5.0
```