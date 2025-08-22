# Ejercicios Individuales

Estos ejercicios están pensados para que los resuelvas por tu cuenta y afiances los conceptos aprendidos. ¡Ponte a prueba!

---

### Ejercicio 1: Suma de Números Pares en un Rango

**Objetivo:** Escribe una función que calcule la suma de todos los números pares en un rango dado (incluyendo los límites).

- **Función:** `sumar_pares(inicio, fin)`
- **Ejemplo:** `sumar_pares(1, 10)` debería devolver `30` (2 + 4 + 6 + 8 + 10).

---

### Ejercicio 2: Encontrar el Elemento Más Común

**Objetivo:** Crea una función que reciba una lista y devuelva el elemento que aparece con más frecuencia.

- **Función:** `mas_comun(lista)`
- **Ejemplo:** `mas_comun(['a', 'b', 'c', 'a', 'b', 'a'])` debería devolver `'a'`.
- **Pista:** Un diccionario puede ser muy útil para contar las apariciones de cada elemento.

---

### Ejercicio 3: Revertir las Palabras de una Frase

**Objetivo:** Escribe una función que tome una frase y la devuelva con el orden de las palabras invertido.

- **Función:** `revertir_frase(frase)`
- **Ejemplo:** `revertir_frase("Hola mundo")` debería devolver `"mundo Hola"`.
- **Pista:** Usa `.split()` y luego une las palabras en orden inverso.

---

### Ejercicio 4: Palíndromo

**Objetivo:** Crea una función que verifique si una palabra es un palíndromo (se lee igual de izquierda a derecha que de derecha a izquierda).

- **Función:** `es_palindromo(palabra)`
- **Ejemplo:** `es_palindromo("radar")` debería devolver `True`. `es_palindromo("python")` debería devolver `False`.
- **Pista:** Compara la palabra original con su versión invertida (`[::-1]`). No olvides pasar todo a minúsculas para que no afecten las mayúsculas.

---

### Ejercicio 5: Calculadora Simple

**Objetivo:** Crea un programa que pida al usuario dos números y un operador (`+`, `-`, `*`, `/`) y muestre el resultado de la operación.

- **Requisitos:**
  - Usa funciones para cada operación (`sumar`, `restar`, etc.).
  - Maneja el caso de la división por cero.

---

### Ejercicio 6: Eliminar Duplicados

**Objetivo:** Escribe una función que tome una lista y devuelva una nueva lista sin elementos duplicados.

- **Función:** `eliminar_duplicados(lista)`
- **Ejemplo:** `eliminar_duplicados([1, 2, 2, 3, 4, 4, 5])` debería devolver `[1, 2, 3, 4, 5]`.
- **Pista:** Puedes recorrer la lista original y añadir elementos a una nueva lista solo si no están ya en ella.

---

### Ejercicio 7: Conversor de Temperatura

**Objetivo:** Crea dos funciones: una para convertir de Celsius a Fahrenheit y otra para convertir de Fahrenheit a Celsius.

- **Fórmulas:**
  - Fahrenheit = (Celsius \* 9/5) + 32
  - Celsius = (Fahrenheit - 32) \* 5/9
- **Funciones:** `celsius_a_fahrenheit(celsius)` y `fahrenheit_a_celsius(fahrenheit)`.

---

### Ejercicio 8: Agenda de Contactos

**Objetivo:** Crea un programa para gestionar una agenda de contactos usando un diccionario.

- **Funcionalidades:**
  1.  Añadir un contacto (nombre y teléfono).
  2.  Buscar un contacto por nombre.
  3.  Mostrar todos los contactos.
  4.  Salir.
- **Requisitos:** Usa un bucle `while` para mostrar un menú al usuario y que elija una opción.

---

### Ejercicio 9: Adivina el Número

**Objetivo:** Crea un juego donde el programa elige un número aleatorio entre 1 y 100 y el usuario tiene que adivinarlo.

- **Requisitos:**
  - Usa el módulo `random`.
  - Después de cada intento, el programa debe decirle al usuario si el número secreto es más alto o más bajo.
  - El juego termina cuando el usuario adivina el número. Lleva la cuenta de cuántos intentos le ha costado.

---

### Ejercicio 10: Factorial de un Número

**Objetivo:** Escribe una función que calcule el factorial de un número. El factorial de `n` (escrito como `n!`) es el producto de todos los enteros positivos desde 1 hasta `n`.

- **Función:** `factorial(n)`
- **Ejemplo:** `factorial(5)` debería devolver `120` (porque 1 _ 2 _ 3 _ 4 _ 5 = 120).
- **Nota:** El factorial de 0 es 1.
