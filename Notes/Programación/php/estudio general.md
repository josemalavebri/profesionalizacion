---
sr-due: 2025-08-07
sr-interval: 4
sr-ease: 270
---

+ Estudiarlo siempre en dificil para repasar constantemente
```php
//funciones
function saludar($nombre) {
  return "Hola, $nombre";
}

echo saludar("Senior"); // Muestra: Hola, Senior

//cadenas
$nombre = "Senior";
echo "Hola, $nombre"; // Interpreta variable
echo 'Hola, $nombre'; // Literal, no interpreta variable

$saludo = "Hola, " . $nombre; // Concatenación
echo strlen($saludo); // Longitud de la cadena


// Si el formulario usa método GET y tiene un campo "nombre"
$nombre = $_GET['nombre'] ?? 'Invitado';

// Si el formulario usa método POST y tiene un campo "email"
$email = $_POST['email'] ?? '';

// Captura el valor enviado por POST o asigna un valor por defecto
$nombre = $_POST['nombre'] ?? 'Invitado';
$email = $_POST['email'] ?? 'No proporcionado';

// Mostrar mensaje
echo "Hola, $nombre, tu email es $email";

// Sanitizar datos de formulario usando filter_input y filtros
$nombre = filter_input(INPUT_POST, 'nombre', FILTER_SANITIZE_STRING);
$email = filter_input(INPUT_POST, 'email', FILTER_SANITIZE_EMAIL);

// Validar que el email sea válido
if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
    echo "Email no válido";
    exit;
}

echo "Nombre: $nombre <br>";
echo "Email: $email";
?>

// Escribir en un archivo
$file = fopen("archivo.txt", "w");
fwrite($file, "Hola Senior");
fclose($file);

// Leer contenido de un archivo
$contenido = file_get_contents("archivo.txt");
echo $contenido;


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