# Plates (PHP Templating)

[Plates - Native PHP Templates (platesphp.com)](https://platesphp.com/)

Plates es un sistema de plantillas PHP que se enfoca en ser simple, fácil de usar y eficiente en términos de rendimiento. Algunas de sus características principales son:

-   No tiene dependencias externas, lo que significa que puede ser utilizado en cualquier proyecto PHP sin necesidad de instalar librerías adicionales.
-   Utiliza una sintaxis clara y fácil de leer, lo que lo hace especialmente adecuado para proyectos pequeños o medianos en los que se busca una solución simple.
-   Soporta la extensión de plantillas, lo que significa que puedes crear plantillas base y luego extenderlas en otras plantillas para ahorrar tiempo en la creación de plantillas repetitivas.
-   Posee una interfaz fácil de usar para agregar variables, bucles y condiciones, lo que lo hace muy fácil de aprender incluso para aquellos que no están familiarizados con los sistemas de plantillas en PHP.

Además, Plates también ofrece algunas características más avanzadas, como el soporte de funciones personalizadas y la capacidad de asignar variables en bloques de plantillas.

En resumen, Plates es una excelente opción para aquellos que buscan una solución de plantilla PHP simple, liviana y fácil de aprender, que no sacrifique la funcionalidad. Si necesitas una solución más avanzada y poderosa, existen otras opciones disponibles, pero si buscas algo simple y efectivo, definitivamente vale la pena considerar Plates.

### Ejemplo de Uso de Plates

Aquí te muestro un ejemplo básico de cómo usar Plates en PHP:

Primero, necesitarás instalar Plates en tu proyecto. Puedes hacerlo mediante Composer, utilizando el siguiente comando en la terminal:

```bash
composer require league/plates
```

Una vez que hayas instalado Plates, puedes comenzar a utilizarlo en tus archivos PHP. Aquí te muestro un ejemplo simple de cómo crear y renderizar una plantilla con Plates:

```php

// Incluir el autoloader de Composer
require 'vendor/autoload.php';

// Crear un nuevo objeto de plantilla de Plates
$templates = new League\Plates\Engine('/ruta/a/tus/plantillas');

// Renderizar una plantilla con una variable
echo $templates->render('miPlantilla', ['nombre' => 'Juan']);
```

En este ejemplo, estamos utilizando la clase `Engine` de Plates para crear un nuevo objeto de plantilla. La ruta que le pasamos al constructor indica dónde se encuentran nuestras plantillas en el sistema de archivos.

Luego, estamos renderizando la plantilla llamada `miPlantilla` y pasándole una variable llamada `nombre`. Dentro de la plantilla, podemos acceder a esta variable utilizando la sintaxis `<?= $nombre ?>`.

Aquí te muestro el contenido de un archivo de plantilla básico (`miPlantilla.php`) que podrías usar con el ejemplo anterior:

```php
<!DOCTYPE html>
<html>
<head>
	<title>Mi Página</title>
</head>
<body>
	<h1>Bienvenido <?= $nombre ?>!</h1>
</body>
</html>
```


Este archivo de plantilla simplemente muestra un mensaje de bienvenida utilizando la variable `nombre` que le pasamos al renderizar la plantilla. Cuando ejecutes el código PHP, deberías ver algo como esto en la salida:

```php
<!DOCTYPE html>
<html>
<head>
	<title>Mi Página</title>
</head>
<body>
	<h1>Bienvenido Juan</h1>
</body>
</html>
```


Espero que este ejemplo te haya sido útil para comenzar a utilizar Plates en tu proyecto PHP.