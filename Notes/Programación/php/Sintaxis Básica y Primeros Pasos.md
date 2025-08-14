---
sr-due: 2025-09-07
sr-interval: 24
sr-ease: 150
---

#tipo-documento #review  

## Puntos clave
- Todo código PHP se encierra entre `<?php` y `?>`.
- Las variables inician con `$` y no necesitan declaración de tipo.
- `echo` y `print` se usan para mostrar datos.
- Soporta comentarios de línea y de bloque.
- Los tipos de datos principales incluyen string, int, float, boolean, null, array y objeto.
- Admite estructuras de control como `if`, `for`, `foreach`.
- Se integra fácilmente con HTML.
- La concatenación se hace con `.` (punto).
- Puede ejecutarse en servidores locales o con `php -S`.

## Características
- Interpretado (no requiere compilación).
- De tipado dinámico.
- Compatible con múltiples servidores web (Apache, Nginx).
- Gran comunidad y documentación.
- Integración sencilla con bases de datos (MySQL, PostgreSQL, etc.).
- Admite orientación a objetos
## Analogía
> *PHP funciona como el cocinero en la cocina de un restaurante: antes de servir el plato (la página web), prepara todos los ingredientes (procesa la lógica del servidor), y luego entrega al cliente solo el resultado final, no cómo se hizo.*
## Ejemplos
### Sintaxis 
```php
<?php
  // Comentario
  echo "Hola mundo";

  $nombre = "Senior";
  echo "Hola, $nombre";

  $suma = 5 + 3;

  if ($suma > 5) {
    echo "Mayor a cinco";
  }

  for ($i = 0; $i < 3; $i++) {
    echo $i;
  }

  $colores = ["rojo", "verde"];
  foreach ($colores as $color) {
    echo $color;
  }
?>

```

## Temas Relacionados
[[Procesamiento del Código PHP y Generación de Contenido Dinámico]]