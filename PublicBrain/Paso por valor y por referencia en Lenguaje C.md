# Paso por valor y por referencia en Lenguaje C

[[Aprender el Lenguaje C desde Cero]]

¡Claro! En C, cuando pasas argumentos a una función, puedes hacerlo por valor o por referencia. Aquí te explico la diferencia entre ambos:

1. **Paso por valor**:
   - Cuando pasas un argumento por valor a una función, se crea una copia del valor original y se utiliza esa copia dentro de la función. Esto significa que cualquier modificación que hagas en el parámetro dentro de la función no afectará al valor original fuera de la función.
   - Los tipos de datos simples como enteros, caracteres y flotantes se pasan por valor por defecto en C.
   - Aquí tienes un ejemplo:

    ```c
    #include <stdio.h>

    // Función que suma dos números y devuelve el resultado
    int sumar(int a, int b) {
        return a + b;
    }

    int main() {
        int x = 5, y = 7;
        int resultado = sumar(x, y);
        printf("El resultado de la suma es: %d\n", resultado);
        return 0;
    }
    ```

   - En este ejemplo, los valores de `x` y `y` se pasan por valor a la función `sumar()`. La función recibe copias de estos valores, los suma y devuelve el resultado. Sin embargo, los valores originales de `x` y `y` en la función `main()` no se modifican.

2. **Paso por referencia**:
   - Cuando pasas un argumento por referencia a una función, estás pasando una referencia o dirección de memoria al valor original en lugar de una copia del valor. Esto permite que la función modifique directamente el valor original fuera de la función.
   - En C, para pasar argumentos por referencia, puedes utilizar punteros.
   - Aquí tienes un ejemplo:

    ```c
    #include <stdio.h>

    // Función que intercambia los valores de dos variables
    void intercambiar(int *a, int *b) {
        int temp = *a;
        *a = *b;
        *b = temp;
    }

    int main() {
        int x = 5, y = 7;
        printf("Antes del intercambio: x = %d, y = %d\n", x, y);
        intercambiar(&x, &y);
        printf("Después del intercambio: x = %d, y = %d\n", x, y);
        return 0;
    }
    ```

   - En este ejemplo, los punteros a `x` y `y` se pasan por referencia a la función `intercambiar()`. La función utiliza estos punteros para acceder directamente a los valores originales de `x` y `y` y cambiarlos. Como resultado, los valores de `x` y `y` se intercambian correctamente fuera de la función `main()`.

Estas son las diferencias entre el paso por valor y por referencia en C. Cada enfoque tiene sus propias ventajas y se utiliza en diferentes situaciones según los requisitos del programa.