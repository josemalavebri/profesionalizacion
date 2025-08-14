---
sr-due: 2025-08-06
sr-interval: 5
sr-ease: 230
---

#tipo-documento 
## Puntos clave
**Variables y constantes**
- Toda variable comienza con `$`.
- No se declaran tipos explícitos (tipado dinámico).
- Se pueden definir constantes con `define()` o `const`.

**Tipos de datos**
- Primitivos: `string`, `int`, `float`, `bool`, `null`.
- Compuestos: `array`, `object`.
- Especiales: `resource`, `callable`.

**Operadores**

- Aritméticos: `+`, `-`, `*`, `/`, `%`.
- Asignación: ` = `, ` += `, ` -= `, etc.
-  Comparación = = ,= = =, `!=`, `!==`, `<`, `>`, `<=`, `>=`.
- Lógicos: `&&`, `||`, `!`.
- Incremento/Decremento: `++`, `--`.
- Concatenación: `.`

**Estructuras de control**
- Condicionales: `if`, `else`, `elseif`, `switch`.
- Bucles: `for`, `while`, `do...while`, `foreach`.
- Control de flujo: `break`, `continue`.

**Funciones definidas por el usuario**
- Se declaran con `function`.
- Pueden tener parámetros y valor de retorno.
- Admite parámetros por defecto y paso por referencia.

**Arrays**
- Indexados: índice numérico.
- Asociativos: índice tipo string.
- Multidimensionales: arrays dentro de arrays.
## Características


## Ejemplos
### Sintaxis 
```c
// Variables y constantes
$nombre = "Senior";
define("PI", 3.1416);

// Tipos de datos
$entero = 10;
$decimal = 2.5;
$booleano = true;
$nulo = null;

// Operadores
$suma = $entero + 5;
$igual = ($nombre == "Senior");

// Estructuras de control
if ($entero > 5) {
  echo "Mayor que cinco";
} elseif ($entero == 5) {
  echo "Igual a cinco";
} else {
  echo "Menor que cinco";
}

for ($i = 0; $i < 3; $i++) {
  echo $i;
}

switch ($nombre) {
  case "Senior":
    echo "Bienvenido";
    break;
  default:
    echo "Desconocido";
}

// Funciones
function saludar($persona = "Invitado") {
  return "Hola, $persona";
}
echo saludar($nombre);

// Arrays
$colores = ["rojo", "verde", "azul"];
$usuario = ["nombre" => "Senior", "edad" => 25];

foreach ($colores as $color) {
  echo $color;
}

echo $usuario["nombre"];

```
```