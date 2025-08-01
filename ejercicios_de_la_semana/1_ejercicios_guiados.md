# Ejercicios Guiados: ¡Tú dictas, yo programo!

El objetivo de estos ejercicios es que trabajemos en equipo. Ustedes me dirán, línea por línea, qué debo escribir en el código para resolver el problema. ¡Vamos a pensar como programadores juntos!

---

### Ejercicio 1: Contador de Palabras

**Objetivo:** Crear un programa que pida al usuario una frase y cuente cuántas palabras tiene.

**Pistas:**

- ¿Cómo pedimos una frase al usuario?
- Una vez que tenemos la frase, ¿qué método de las cadenas nos puede ayudar a separar las palabras?
- ¿En qué tipo de dato se guardan esas palabras separadas?
- ¿Qué función nos permite saber cuántos elementos hay en una lista?

---

### Ejercicio 2: Suma de Números Pares

**Objetivo:** Calcular la suma de todos los números pares del 1 al 20.

**Pistas:**

- ¿Cómo podemos generar una secuencia de números del 1 al 20?
- Necesitaremos un bucle para recorrer cada número.
- Dentro del bucle, ¿cómo sabemos si un número es par? (Pista: operador módulo `%`).
- Necesitaremos una variable "acumuladora" que empiece en 0 y a la que le iremos sumando los números pares que encontremos.

---

### Ejercicio 3: Creador de Nombres de Usuario

**Objetivo:** Crear un programa que pida al usuario su nombre, apellido y año de nacimiento, y genere un nombre de usuario uniendo el nombre, el apellido y el año, todo en minúsculas y sin espacios.

**Ejemplo:**

- Nombre: `Ana`
- Apellido: `Pérez`
- Año: `1995`
- Nombre de usuario generado: `anaperez1995`

**Pistas:**

- ¿Cómo convertimos todo a minúsculas?
- ¿Cómo eliminamos los espacios de las cadenas?
- ¿Cómo unimos varias cadenas para formar una sola?

---

### Ejercicio 4 (Más complejo): Sistema de Login Simple

**Objetivo:** Simular un sistema de inicio de sesión. El programa debe tener un nombre de usuario y una contraseña guardados. Pedirá al usuario que ingrese sus credenciales y le dará 3 intentos. Si acierta, le dará la bienvenida. Si falla 3 veces, le dirá que su cuenta está bloqueada.

**Pistas:**

- Necesitaremos guardar el usuario y la contraseña correctos en variables.
- Necesitaremos un contador para los intentos, que empiece en 0.
- Un bucle `while` que se ejecute mientras los intentos sean menores que 3.
- Dentro del bucle, pediremos al usuario su nombre y contraseña.
- Usaremos un `if` para comparar si lo que ingresó es correcto.
- Si es correcto, mostramos un mensaje de bienvenida y usamos `break` para salir del bucle.
- Si no es correcto, aumentamos el contador de intentos y le decimos cuántos le quedan.
- Después del bucle, un `if` puede comprobar si el usuario agotó sus intentos.
