---
sr-due: 2025-09-08
sr-interval: 26
sr-ease: 210
---


#tipo-documento #review  

## Puntos clave
- Un **objeto** es una **instancia concreta** de una clase definida.
- Se accede a las propiedades con `->`, no con punto como en otros lenguajes.
- Los objetos se construyen con `new`, utilizando el constructor definido o implícito.
- PHP admite **herencia**, **encapsulamiento** y **polimorfismo**.
- Los objetos no son necesarios para todas las tareas, pero son esenciales en diseños complejos o grandes sistemas.
## Ejemplos
### Sintaxis 
```c
// Declaración de clase
class Persona {
  public $nombre;

  public function saludar() {
    return "Hola, soy $this->nombre";
  }
}

// Instanciación de objeto
$persona = new Persona();
$persona->nombre = "Senior";

// Uso del método
echo $persona->saludar();

```
