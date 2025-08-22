# Ejercicios en Grupo 1

Estos ejercicios están diseñados para ser resueltos en equipo. La idea es que discutan las posibles soluciones, dividan las tareas si es necesario y comparen los resultados. ¡La colaboración es clave!

---

### Ejercicio 1: Calculadora de Estadísticas de Notas

**Objetivo:** Crear un programa que pida al usuario que ingrese una serie de notas (números del 1 al 10). El programa debe parar de pedir notas cuando el usuario ingrese un `0`. Al final, debe mostrar:

- La cantidad total de notas ingresadas.
- La nota media (el promedio).
- La nota más alta.
- La nota más baja.

**Requisitos:**

- Utiliza un bucle `while` para pedir las notas hasta que se ingrese un `0`.
- Guarda las notas en una lista.
- No consideres el `0` como una nota válida para los cálculos.
- Si no se ingresa ninguna nota válida, el programa debe indicarlo y no intentar hacer cálculos que den error (como dividir por cero).

---

### Ejercicio 2: Generador de Nombres de Usuario

**Objetivo:** Crear una función que reciba el nombre completo de una persona (nombre y apellido) y genere un nombre de usuario único.

**Reglas para el nombre de usuario:**

1.  Debe estar en minúsculas.
2.  Debe consistir en la primera letra del nombre, seguido del apellido completo.
3.  Al final, debe añadir un número aleatorio de 3 cifras (entre 100 y 999) para asegurar que sea único.

**Requisitos:**

- Crea una función `generar_usuario(nombre_completo)` que reciba el nombre como un string.
- Utiliza métodos de string como `.lower()`, `.split()` y slicing para separar y formatear las partes del nombre.
- Utiliza el módulo `random` para generar el número aleatorio.

---

### Ejercicio 3: Validador de Contraseñas

**Objetivo:** Crear una función que verifique si una contraseña cumple con ciertos criterios de seguridad.

**Criterios de seguridad:**

1.  Debe tener al menos 8 caracteres de longitud.
2.  Debe contener al menos una letra mayúscula.
3.  Debe contener al menos un número.

**Requisitos:**

- Crea una función `validar_contrasena(pwd)` que devuelva `True` si la contraseña es válida y `False` si no lo es.
- Utiliza un bucle `for` para recorrer los caracteres de la contraseña y verificar las condiciones.
- Puedes usar métodos de string como `.isupper()` y `.isdigit()`.

---

### Ejercicio 4: Adivina el Número

**Objetivo:** Crear un juego donde el programa elige un número secreto y el usuario debe adivinarlo.

**Requisitos:**

- Genera un número aleatorio entre 1 y 100 al inicio del juego.
- Pide al usuario que ingrese un número en cada intento.
- Proporciona pistas como "Demasiado alto" o "Demasiado bajo".
- El juego termina cuando el usuario adivina el número.
- Al final, muestra cuántos intentos le tomó al usuario adivinar.

---

### Ejercicio 5: Contador de Frecuencia de Palabras

**Objetivo:** Crear una función que reciba un texto y devuelva un diccionario con la frecuencia de cada palabra.

**Requisitos:**

- La función `contar_palabras(texto)` debe recibir un string.
- Convierte el texto a minúsculas para que "Hola" y "hola" cuenten como la misma palabra.
- Elimina los signos de puntuación básicos (como `,` y `.`) antes de contar.
- La función debe devolver un diccionario donde cada palabra es una clave y su frecuencia es el valor.

---

### Ejercicio 6: Verificador de Palíndromos

**Objetivo:** Crear una función que determine si una palabra o frase es un palíndromo.

**Definición:** Un palíndromo es una palabra o frase que se lee igual de izquierda a derecha que de derecha a izquierda, ignorando espacios, mayúsculas y puntuación. Ejemplo: "Anita lava la tina".

**Requisitos:**

- Crea una función `es_palindromo(frase)` que devuelva `True` o `False`.
- La función debe procesar el string de entrada para que solo contenga letras minúsculas.
- Compara el string procesado con su versión invertida.

---

### Ejercicio 7: Calculadora de Factorial

**Objetivo:** Crear una función que calcule el factorial de un número entero no negativo.

**Definición:** El factorial de un número `n` (denotado como `n!`) es el producto de todos los enteros positivos desde 1 hasta `n`. El factorial de 0 es 1.

**Requisitos:**

- Crea una función `factorial(n)`.
- Si `n` es negativo, la función debería indicar que no es válido (por ejemplo, devolviendo `None` o un mensaje).
- Utiliza un bucle para calcular el producto.

---

### Ejercicio 8: Conversor de Temperatura

**Objetivo:** Crear una función que convierta temperaturas entre Celsius y Fahrenheit.

**Requisitos:**

- Crea una función `convertir_temp(valor, unidad_origen)`.
- `unidad_origen` será 'C' para Celsius o 'F' para Fahrenheit.
- La función debe devolver la temperatura convertida en la otra unidad.
- **Fórmulas:**
  - De Celsius a Fahrenheit: `F = (C * 9/5) + 32`
  - De Fahrenheit a Celsius: `C = (F - 32) * 5/9`
- La función debe devolver un string con la unidad de destino, por ejemplo: `"32.0°F"` o `"10.0°C"`.

---

### Ejercicio 9: Lista de Tareas Simple

**Objetivo:** Crear un programa simple de lista de tareas (To-Do list) que permita al usuario añadir, ver y eliminar tareas.

**Requisitos:**

- Usa una lista para almacenar las tareas.
- Crea un bucle principal que muestre un menú de opciones: `1. Añadir tarea`, `2. Ver tareas`, `3. Eliminar tarea`, `4. Salir`.
- **Añadir:** Pide al usuario el nombre de la tarea y la agrega a la lista.
- **Ver:** Muestra todas las tareas en la lista, numeradas.
- **Eliminar:** Pide al usuario el número de la tarea a eliminar y la quita de la lista.
- El programa termina cuando el usuario elige la opción de salir.

---

### Ejercicio 10: Simulador de Lanzamiento de Dados

**Objetivo:** Crear una función que simule el lanzamiento de uno o más dados de 6 caras.

**Requisitos:**

- Crea una función `lanzar_dados(numero_de_dados)` que reciba cuántos dados se deben lanzar.
- La función debe generar un número aleatorio entre 1 y 6 para cada dado.
- Debe devolver la suma total de los resultados de todos los dados.
- Utiliza el módulo `random`.
