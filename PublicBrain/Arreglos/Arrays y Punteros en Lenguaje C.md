---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-14T21:07:58.048Z
modified: 2024-05-15T21:38:38.798Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 3
ver_rev: 2
nav_primary: []
nav_secondary: []
tags: []
---
# Arrays y Punteros en Lenguaje C

[[Aprender el Lenguaje C desde Cero ⚫①]]

¡Claro! Los arreglos (arrays) y los punteros son conceptos fundamentales en C y están estrechamente relacionados. Aquí te explico cómo interactúan los arreglos y los punteros en C:

1. **Relación entre arreglos y punteros**:
   - En C, los arreglos y los punteros están muy interrelacionados. De hecho, en muchos casos, un arreglo se comporta como un puntero constante a la dirección de memoria del primer elemento del arreglo.
   - Cuando declaras un arreglo en C, el nombre del arreglo actúa como un puntero al primer elemento del arreglo.
   - Por ejemplo:
     ```c
     int numeros[5] = {1, 2, 3, 4, 5};
     int *ptr = numeros; // 'ptr' apunta al primer elemento del arreglo 'numeros'
     ```
   - En este ejemplo, `ptr` es un puntero que apunta al primer elemento del arreglo `numeros`.

2. **Acceso a elementos de arreglos mediante punteros**:
   - Puedes acceder a los elementos de un arreglo utilizando aritmética de punteros.
   - Por ejemplo:
     ```c
     printf("El primer elemento es: %d\n", *ptr); // Imprime el primer elemento del arreglo 'numeros'
     printf("El segundo elemento es: %d\n", *(ptr + 1)); // Imprime el segundo elemento del arreglo 'numeros'
     ```
   - Aquí, `*(ptr + 1)` accede al segundo elemento del arreglo `numeros` sumando 1 al puntero `ptr`.

3. **Iteración a través de arreglos con punteros**:
   - Puedes usar punteros para iterar a través de los elementos de un arreglo.
   - Por ejemplo:
     ```c
     for (int i = 0; i < 5; i++) {
         printf("%d ", *(ptr + i)); // Imprime cada elemento del arreglo 'numeros' usando punteros
     }
     printf("\n");
     ```

4. **Arreglos y punteros como argumentos de funciones**:
   - Cuando pasas un arreglo a una función, en realidad pasas un puntero al primer elemento del arreglo.
   - Por lo tanto, cualquier modificación que hagas en el arreglo dentro de la función afectará al arreglo original.
   - Por ejemplo:
     ```c
     void modificarArreglo(int *arr, int tam) {
         for (int i = 0; i < tam; i++) {
             arr[i] *= 2; // Multiplica cada elemento del arreglo por 2
         }
     }

     int main() {
         int numeros[5] = {1, 2, 3, 4, 5};
         modificarArreglo(numeros, 5);
         // 'numeros' ahora contendrá {2, 4, 6, 8, 10}
         return 0;
     }
     ```

Los arreglos y los punteros son conceptos esenciales en C y entender cómo interactúan te ayudará a escribir código más efectivo y eficiente.