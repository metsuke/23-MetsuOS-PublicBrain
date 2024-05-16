---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-07T19:04:57.137Z
modified: 2024-05-15T21:38:39.568Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: []
nav_secondary: []
tags: []
---
# Estructuras de Control

[[Aprender el Lenguaje C desde Cero ⚫①]]

¡Claro! Las estructuras de control en el lenguaje C son esenciales para controlar el flujo de ejecución de un programa. Permiten tomar decisiones, ejecutar bloques de código repetidamente y controlar el comportamiento de un programa. Aquí tienes una descripción de las principales estructuras de control en C:

### 1. **Estructuras de Control Condicionales:**

   - **if-else:** Permite ejecutar un bloque de código si una condición es verdadera y otro bloque si la condición es falsa.
   
   ```c
   if (condición) {
       // Bloque de código si la condición es verdadera
   } else {
       // Bloque de código si la condición es falsa
   }
   ```

   - **else if:** Permite evaluar múltiples condiciones después de un if inicial.
   
   ```c
   if (condición1) {
       // Bloque de código si la condición1 es verdadera
   } else if (condición2) {
       // Bloque de código si la condición2 es verdadera
   } else {
       // Bloque de código si ninguna de las condiciones anteriores es verdadera
   }
   ```

### 2. **Estructuras de Control de Bucle:**

   - **for:** Ejecuta un bloque de código un número específico de veces.
   
   ```c
   for (inicialización; condición; incremento) {
       // Bloque de código a ejecutar
   }
   ```

   - **while:** Ejecuta un bloque de código mientras una condición sea verdadera.
   
   ```c
   while (condición) {
       // Bloque de código a ejecutar
   }
   ```

   - **do-while:** Similar a while, pero garantiza que el bloque de código se ejecute al menos una vez antes de evaluar la condición.
   
   ```c
   do {
       // Bloque de código a ejecutar
   } while (condición);
   ```

### 3. **Estructuras de Control de Salto:**

   - **break:** Termina la ejecución de un bucle o una estructura switch.
   - **continue:** Salta a la siguiente iteración de un bucle.
   - **return:** Devuelve un valor de una función y termina su ejecución.

Estas estructuras de control son fundamentales para construir la lógica de cualquier programa en lenguaje C. Al comprender cómo funcionan y cuándo usarlas, podrás escribir programas más complejos y funcionales.

---

Las estructuras de control en programación son herramientas que nos permiten modificar el flujo de ejecución de un programa. En el lenguaje C, tenemos tres tipos principales de estructuras de control: las estructuras de selección (if-else), las estructuras de repetición (for, while, do-while) y las estructuras de control de flujo (break, continue, goto).

1. **Estructuras de selección (if-else)**: Permiten ejecutar un bloque de código si se cumple una condición específica. Por ejemplo:


2. **Estructuras de repetición (for, while, do-while)**: Permiten ejecutar un bloque de código de manera repetida mientras se cumpla una condición específica. Por ejemplo, en un bucle for:


3. **Estructuras de control de flujo (break, continue, goto)**: Permiten controlar de forma más detallada el flujo de ejecución de un programa. Por ejemplo, la sentencia  se utiliza para salir de un bucle,  se utiliza para saltar a la siguiente iteración de un bucle y  se utiliza para saltar a una etiqueta específica en el código.

Es importante comprender cómo y cuándo utilizar estas estructuras de control en un programa en lenguaje C, ya que nos permiten diseñar programas más eficientes y claros. Además, es recomendable practicar con ejercicios y problemas que involucren la utilización de estas estructuras para familiarizarse con su funcionamiento y aplicaciones.
