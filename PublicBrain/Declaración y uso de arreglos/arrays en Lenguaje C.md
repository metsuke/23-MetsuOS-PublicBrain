---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-14T21:06:45.963Z
modified: 2024-04-14T21:13:33.344Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 3
ver_rev: 1
nav_primary: []
nav_secondary: []
tags: []
---
# arrays en Lenguaje C

[[Aprender el Lenguaje C desde Cero]]

¡Por supuesto! Los arreglos (también conocidos como arrays) son una estructura de datos fundamental en C que te permite almacenar una colección de elementos del mismo tipo bajo un solo nombre. Aquí te explico cómo declarar y usar arreglos en C:

1. **Declaración de arreglos**:
   - Para declarar un arreglo en C, necesitas especificar el tipo de datos de los elementos del arreglo y el número de elementos que contendrá el arreglo.
   - La sintaxis básica para declarar un arreglo es la siguiente:
     ```c
     tipo nombre_arreglo[tamaño];
     ```
   - Por ejemplo, para declarar un arreglo de enteros con 5 elementos:
     ```c
     int numeros[5];
     ```
   - Esto declara un arreglo llamado `numeros` que puede almacenar 5 enteros.

2. **Inicialización de arreglos**:
   - Puedes inicializar los elementos de un arreglo al momento de la declaración utilizando una lista de valores entre llaves `{}`.
   - Por ejemplo, para inicializar un arreglo de enteros con algunos valores:
     ```c
     int numeros[5] = {1, 2, 3, 4, 5};
     ```
   - También puedes omitir el tamaño del arreglo y dejar que el compilador infiera el tamaño automáticamente a partir del número de elementos en la lista de inicialización:
     ```c
     int numeros[] = {1, 2, 3, 4, 5}; // El tamaño del arreglo será 5
     ```

3. **Acceso a elementos de arreglos**:
   - Puedes acceder a los elementos individuales de un arreglo utilizando corchetes `[]` y el índice del elemento.
   - Los índices de los elementos de un arreglo comienzan desde 0 y van hasta el tamaño del arreglo menos 1.
   - Por ejemplo, para acceder al tercer elemento de un arreglo:
     ```c
     int valor = numeros[2]; // Accede al tercer elemento (índice 2) del arreglo 'numeros'
     ```

4. **Modificación de elementos de arreglos**:
   - Puedes modificar los elementos de un arreglo asignando un nuevo valor al elemento correspondiente.
   - Por ejemplo, para cambiar el valor del segundo elemento de un arreglo:
     ```c
     numeros[1] = 10; // Cambia el valor del segundo elemento (índice 1) del arreglo 'numeros' a 10
     ```

5. **Recorrido de arreglos**:
   - Puedes recorrer los elementos de un arreglo utilizando bucles como `for` o `while`.
   - Por ejemplo, para imprimir todos los elementos de un arreglo:
     ```c
     for (int i = 0; i < 5; i++) {
         printf("%d ", numeros[i]); // Imprime cada elemento del arreglo 'numeros'
     }
     printf("\n");
     ```

Los arreglos son una herramienta poderosa en C para manejar conjuntos de datos de manera eficiente y compacta. Con un buen entendimiento de cómo declarar, inicializar y acceder a los elementos de los arreglos, podrás utilizar esta estructura de datos de manera efectiva en tus programas en C.