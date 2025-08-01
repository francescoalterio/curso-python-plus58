# Ejercicios Individuales: ¡Ahora te toca a ti!

Estos ejercicios son para que los resuelvas por tu cuenta. El objetivo es que apliques lo que hemos visto y te enfrentes al desafío de estructurar la solución. ¡No te preocupes si no sale a la primera! Lo importante es intentarlo.

---

### Ejercicio 1: Adivina la Palabra

**Objetivo:** Crear un programa que pida al usuario adivinar una palabra secreta.

1. Define una palabra secreta en una variable (ej: `"python"`).
2. Pide al usuario que escriba una palabra.
3. Si la palabra es igual a la palabra secreta, muestra un mensaje de felicitación.
4. Si no es igual, muestra un mensaje diciendo que no acertó.

---

### Ejercicio 2: Calculadora de Promedios

**Objetivo:** Crear un programa que permita al usuario ingresar notas(float) hasta que escriba "fin". Luego, el programa debe calcular y mostrar el promedio de las notas ingresadas.

1.  Crea una lista vacía para guardar las notas.
2.  Usa un bucle `while True` para pedir notas continuamente.
3.  Pide al usuario que ingrese una nota o escriba "fin".
4.  Si el usuario escribe "fin", rompe el bucle con `break`.
5.  Si no, convierte la entrada a un número (`float`) y añádelo a la lista de notas.
6.  Cuando el bucle termine, calcula el promedio: la suma de todas las notas dividida por la cantidad de notas.
7.  Muestra el promedio al usuario.

---

### Ejercicio 3: Inversor de Frases

**Objetivo:** Pedir al usuario una frase y devolverle la frase con el orden de las palabras invertido.

**Ejemplo:**

- Entrada: `"Python es un lenguaje genial"`
- Salida: `"genial lenguaje un es Python"`

**Pistas:**

- Usa `.split()` para convertir la frase en una lista de palabras.
- Hay un método de las listas que te permite invertir el orden de sus elementos.
- Usa `.join()` para volver a unir la lista en una cadena.

---

### Ejercicio 4 (Más complejo): Registro de Gastos

**Objetivo:** Crear un programa que permita registrar gastos. El usuario podrá agregar un gasto con su descripción y monto, ver todos los gastos y calcular el total.

1.  Usa una lista de diccionarios para guardar los gastos. Cada diccionario podría tener las claves `"descripcion"` y `"monto"`.
2.  Crea un bucle `while True` para el menú principal.
3.  Ofrece al usuario las opciones: `1. Agregar gasto`, `2. Ver gastos`, `3. Calcular total`, `4. Salir`.
4.  **Si elige 1:** Pide la descripción y el monto del gasto. Crea un diccionario con esa información y añádelo a la lista de gastos.
5.  **Si elige 2:** Recorre la lista de gastos e imprime cada uno de forma clara.
6.  **Si elige 3:** Recorre la lista, suma todos los montos y muestra el total.
7.  **Si elige 4:** Termina el programa.
