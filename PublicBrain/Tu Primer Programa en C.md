---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:49:00.858Z
modified: 2024-04-06T23:49:41.461Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 24
nav_primary: []
nav_secondary: []
tags: []
---
# Tu Primer Programa en C

[[Aprender el Lenguaje C desde Cero]]

Es emocionante comenzar a aprender un nuevo lenguaje de programación como C. Tu primer programa en C es una experiencia emocionante y fundamental. Aquí te guiaré a través de los pasos para crear tu primer programa en C, que generalmente es un programa "Hola Mundo".

El programa "Hola Mundo" es un programa simple que imprime "Hola Mundo" en la pantalla. Aquí está el código en C:

```c
#include <stdio.h>

int main() {
    // Imprime "Hola Mundo" en la pantalla
    printf("Hola Mundo\n");
    return 0;
}
```

Ahora, desglosemos este código:

1. `#include <stdio.h>`: Esta línea le dice al compilador que incluya el archivo de encabezado `stdio.h`, que contiene la definición de la función `printf()`. La función `printf()` se utiliza para imprimir texto en la pantalla.

2. `int main() { ... }`: Aquí comienza la función principal del programa, `main()`. Todos los programas en C deben tener una función `main()`, ya que es el punto de entrada del programa. La función `main()` devuelve un entero (`int`), que generalmente se utiliza para indicar si el programa se ejecutó correctamente (0 indica éxito).

3. `{ ... }`: Las llaves `{}` delimitan el bloque de código que forma el cuerpo de la función `main()`. En este caso, el cuerpo de `main()` contiene una sola instrucción.

4. `printf("Hola Mundo\n");`: Esta es la instrucción que imprime "Hola Mundo" en la pantalla. La función `printf()` es una función de salida formateada que imprime texto en la pantalla. El `\n` al final indica un salto de línea, por lo que después de imprimir "Hola Mundo", el cursor se moverá a la siguiente línea.

5. `return 0;`: Esta línea indica que la función `main()` ha terminado y devuelve 0, lo que generalmente significa que el programa se ejecutó correctamente.

Una vez que hayas escrito este código, puedes guardarlo en un archivo con extensión `.c` (por ejemplo, `hola_mundo.c`). Luego, puedes compilarlo utilizando un compilador de C, como GCC en sistemas Unix/Linux o MinGW en Windows.

Por ejemplo, si estás en un sistema Unix/Linux, puedes compilarlo desde la línea de comandos escribiendo:

```
gcc hola_mundo.c -o hola_mundo
```

Esto creará un archivo ejecutable llamado `hola_mundo`. Luego, puedes ejecutar el programa escribiendo:

```
./hola_mundo
```

Y deberías ver la salida "Hola Mundo" en la pantalla.

¡Y eso es! Has escrito y ejecutado tu primer programa en C. A partir de aquí, puedes comenzar a explorar más sobre la sintaxis y las características del lenguaje C para construir programas más complejos y poderosos. ¡Buena suerte en tu viaje de aprendizaje de C!