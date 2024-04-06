---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2023-09-13T02:31:03.000Z
modified: 2024-04-03T20:19:14.899Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 23
nav_primary: []
nav_secondary: []
tags: []
---
# AltoRouter (PHP Routing)

Altorouter es un sistema de routing simple y eficiente para PHP que permite definir rutas y asociarlas con controladores o acciones en tu aplicación web.

Entre las principales características de Altorouter se encuentran:

-   Fácil de integrar: No requiere de ninguna biblioteca externa y es muy fácil de integrar en cualquier proyecto PHP.
-   Routing flexible: Altorouter admite una amplia gama de patrones de URL, incluyendo expresiones regulares, cadenas literales y combinaciones de ambas.
-   Controladores y acciones: Puedes asociar rutas con controladores o acciones en tu aplicación web, lo que te permite manejar las solicitudes de forma estructurada y modular.
-   Generación de URL: Altorouter también ofrece una función para generar URL a partir de rutas definidas, lo que facilita la creación de enlaces y redirecciones dentro de tu aplicación.
-   Cacheo de rutas: Altorouter incluye un sistema de cacheo de rutas que mejora el rendimiento de tu aplicación al reducir el tiempo necesario para buscar la ruta correspondiente a una solicitud.

Altorouter es una excelente opción para proyectos de tamaño pequeño a mediano que requieren un sistema de routing simple y eficiente. Es fácil de usar y no requiere de una curva de aprendizaje muy pronunciada. Además, es muy rápido y no depende de ninguna biblioteca externa, lo que lo hace ideal para aplicaciones que necesitan una alta velocidad de respuesta.

### Ejemplo de Uso

Aquí te muestro un ejemplo básico de cómo usar Altorouter para definir rutas y asociarlas con controladores o acciones en tu aplicación PHP:

```php
<?php

require 'vendor/autoload.php';

$router = new AltoRouter();

// Definir una ruta para la página principal
$router->map('GET', '/', function() {
    echo 'Bienvenido a mi sitio web!';
});

// Definir una ruta para la página de contacto
$router->map('GET', '/contacto', function() {
    echo 'Ponte en contacto con nosotros en: info@mi-sitio-web.com';
});

// Definir una ruta para la página de productos
$router->map('GET', '/productos/[i:id]', function($id) {
    echo 'Detalles del producto con ID: ' . $id;
});

// Hacer coincidir la ruta con la solicitud actual
$match = $router->match();

// Ejecutar el controlador asociado a la ruta
if ($match && is_callable($match['target'])) {
    call_user_func_array($match['target'], $match['params']);
} else {
    // Mostrar una página de error 404 si la ruta no se encuentra
    header($_SERVER["SERVER_PROTOCOL"] . " 404 Not Found");
    echo 'Error 404: Página no encontrada';
}
```


En este ejemplo, estamos creando un nuevo objeto de `AltoRouter` y definiendo tres rutas diferentes:

-   La ruta para la página principal del sitio (`/`), que simplemente muestra un mensaje de bienvenida.
-   La ruta para la página de contacto (`/contacto`), que muestra información de contacto para el sitio web.
-   La ruta para la página de detalles del producto (`/productos/[i:id]`), que utiliza una expresión regular para capturar el ID del producto en la URL.

Luego, hacemos coincidir la ruta definida con la solicitud actual utilizando el método `match()` de Altorouter. Si la ruta coincide con la solicitud, ejecutamos el controlador asociado a la ruta y pasamos cualquier parámetro capturado a través de la URL.

Si la ruta no se encuentra, mostramos una página de error 404 al usuario.

Espero que este ejemplo te haya ayudado a comprender mejor cómo funciona Altorouter y cómo puedes usarlo en tus proyectos PHP.

### Capturar Ruta para sistema de documentos

Para capturar una ruta a partir de la raíz del sitio y usarla como ruta de archivo, puedes usar la siguiente configuración en Altorouter:

```php
<?php

require 'vendor/autoload.php';

$router = new AltoRouter();

// Definir una ruta para todas las solicitudes a partir de la raíz
$router->map('GET', '/[*]', function($path) {
    $file = __DIR__ . $path;
    if (is_file($file)) {
        // Si el archivo existe, mostrarlo
        require $file;
    } else {
        // Si el archivo no existe, mostrar una página de error 404
        header($_SERVER["SERVER_PROTOCOL"] . " 404 Not Found");
        echo 'Error 404: Página no encontrada';
    }
});

// Hacer coincidir la ruta con la solicitud actual
$match = $router->match();

// Ejecutar el controlador asociado a la ruta
if ($match && is_callable($match['target'])) {
    call_user_func_array($match['target'], $match['params']);
} else {
    // Mostrar una página de error 404 si la ruta no se encuentra
    header($_SERVER["SERVER_PROTOCOL"] . " 404 Not Found");
    echo 'Error 404: Página no encontrada';
}

```
En este ejemplo, estamos definiendo una sola ruta para todas las solicitudes a partir de la raíz del sitio (`/[*]`). El asterisco `*` indica que cualquier cosa después de la raíz debe ser capturada y pasada como parámetro `$path` al controlador asociado con la ruta.

Dentro del controlador, estamos comprobando si el archivo correspondiente a la ruta existe en el servidor. Si el archivo existe, lo requerimos y lo mostramos al usuario. De lo contrario, mostramos una página de error 404.

Es importante tener en cuenta que esta configuración puede presentar ciertos riesgos de seguridad si no se usa correctamente. Asegúrate de verificar siempre que la ruta solicitada es segura y no presenta posibles vulnerabilidades en tu aplicación.

### Añadiendo seguridad al ejemplo anterior

Aquí te muestro un ejemplo de cómo añadir algunas medidas de seguridad adicionales para evitar posibles vulnerabilidades en la configuración de Altorouter que propuse anteriormente:

```php
<?php

require 'vendor/autoload.php';

$router = new AltoRouter();

// Definir una ruta para todas las solicitudes a partir de la raíz
$router->map('GET', '/[*]', function($path) {
    // Eliminar cualquier caracter peligroso en la ruta
    $path = preg_replace('/[^a-zA-Z0-9\/\-\_\.]/', '', $path);

    $file = __DIR__ . $path;

    // Verificar que el archivo existe en la ruta esperada
    if (is_file($file) && strpos(realpath($file), realpath(__DIR__)) === 0) {
        // Si el archivo existe y está en el directorio permitido, mostrarlo
        require $file;
    } else {
        // Si el archivo no existe, mostrar una página de error 404
        header($_SERVER["SERVER_PROTOCOL"] . " 404 Not Found");
        echo 'Error 404: Página no encontrada';
    }
});

// Hacer coincidir la ruta con la solicitud actual
$match = $router->match();

// Ejecutar el controlador asociado a la ruta
if ($match && is_callable($match['target'])) {
    // Verificar que la ruta no incluya '../' o '..\' para evitar saltos de directorio
    if (strpos($match['params'][0], '../') === false && strpos($match['params'][0], '..\\') === false) {
        call_user_func_array($match['target'], $match['params']);
    } else {
        // Si se detecta un salto de directorio, mostrar una página de error 403
        header($_SERVER["SERVER_PROTOCOL"] . " 403 Forbidden");
        echo 'Error 403: Acceso no permitido';
    }
} else {
    // Mostrar una página de error 404 si la ruta no se encuentra
    header($_SERVER["SERVER_PROTOCOL"] . " 404 Not Found");
    echo 'Error 404: Página no encontrada';
}

```

En este ejemplo, hemos agregado algunas medidas de seguridad adicionales para proteger contra posibles vulnerabilidades.

Primero, hemos utilizado una expresión regular para eliminar cualquier carácter peligroso en la ruta, como caracteres especiales o comandos de shell.

Luego, hemos agregado una verificación adicional para asegurarnos de que el archivo solicitado realmente existe en la ruta esperada y no en un directorio externo.

Finalmente, hemos agregado otra verificación para evitar saltos de directorio al verificar que la ruta no incluya `../` o `..\\`.

Estas medidas adicionales ayudarán a prevenir posibles ataques de inyección de código malicioso o de intentos de acceder a archivos fuera del directorio permitido.

