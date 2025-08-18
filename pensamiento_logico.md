### El Arte de Pensar como un Programador: Tu Plan de Ataque

Programar no es solo escribir código; es, sobre todo, resolver problemas. El código es la herramienta, pero tu mente es el verdadero motor. Antes de tocar el teclado, los buenos programadores siguen un plan de ataque mental. Aquí te lo desglosamos paso a paso, como si fueras un detective resolviendo un caso.

#### Paso 1: Conviértete en un Detective (Entender el Problema a Fondo)

Imagina que te entregan un sobre con una misión. No puedes empezar a actuar sin leer las instrucciones. Lo mismo pasa con un problema de programación. Tu primer trabajo es interrogar al problema hasta que no te queden dudas.

Hazte estas tres preguntas fundamentales:

1.  **¿Qué información necesito? (Las Entradas)**

    - ¿Qué datos me da el problema desde el principio?
    - ¿Qué datos debo pedirle al usuario?
    - ¿De qué tipo son esos datos? (¿un nombre?, ¿un número entero?, ¿un precio con decimales?).
    - _Ejemplo:_ Para una calculadora de descuentos, necesito el `precio original` (un número) y el `porcentaje de descuento` (otro número).

2.  **¿Qué debo entregar? (Las Salidas)**

    - ¿Cuál es el resultado final que el programa debe mostrar?
    - ¿Debe ser un mensaje en pantalla?, ¿un número?, ¿un archivo guardado?
    - ¿Cómo debe ser el formato? (Ej: "El total es: 120.50€").
    - _Ejemplo:_ Debo entregar un mensaje claro que muestre el `precio final` después del descuento.

3.  **¿Cuáles son las reglas del juego? (Las Restricciones y Condiciones)**
    - ¿Hay alguna condición que cambie el resultado? (Ej: "Si el cliente es VIP, el descuento es mayor").
    - ¿Hay alguna limitación? (Ej: "La contraseña debe tener más de 8 caracteres", "el número no puede ser negativo").
    - Estas reglas son las que te llevarán a usar herramientas como los `if`.
    - _Ejemplo:_ La regla es la fórmula matemática: `precio_final = precio_original - (precio_original * descuento / 100)`. Otra regla podría ser que el descuento no puede ser mayor al 100%.

#### Paso 2: Dibuja el Mapa (Divide y Vencerás)

Un problema grande y complejo puede ser intimidante. La estrategia clave es **dividirlo en pasos muy pequeños y sencillos**. Escribe estos pasos en tu idioma, como si le estuvieras dando instrucciones a una persona que no sabe nada de programación. A esto se le llama **pseudocódigo**.

**Misión de ejemplo:** "Crear un programa que salude a un usuario por su nombre y le diga si es mayor de edad para entrar a un sitio web".

**Tu Mapa (la receta en lenguaje humano):**

1.  Saludar al usuario y explicarle qué hace el programa.
2.  Preguntarle su nombre.
3.  Guardar el nombre que ha escrito.
4.  Preguntarle su edad.
5.  Guardar la edad que ha escrito.
6.  **Revisar la edad:** ¿Es 18 o más?
7.  **Si la respuesta es SÍ:** Preparar un mensaje que diga "¡Bienvenido/a! Puedes pasar."
8.  **Si la respuesta es NO:** Preparar un mensaje que diga "Lo siento, no tienes la edad suficiente."
9.  Mostrar el saludo final, usando su nombre y el mensaje que hemos preparado.

Fíjate que todavía no hemos escrito ni una línea de código. Solo hemos creado un plan lógico y fácil de seguir.

#### Paso 3: Elige tus Herramientas (Asocia el Plan con el Código)

Ahora, con tu mapa en mano, repasa cada paso y piensa: **"¿Qué herramienta de Python me sirve para hacer esto?"**. Es como un carpintero que mira los planos y elige el serrucho, el martillo y los clavos.

- **Pasos 1, 2 y 4 ("Saludar", "Preguntar"):**

  - _Pensamiento:_ Necesito mostrar texto en pantalla y pedirle algo al usuario.
  - _Herramienta:_ `print()` para mostrar, `input()` para pedir.

- **Pasos 3 y 5 ("Guardar"):**

  - _Pensamiento:_ Necesito un lugar para almacenar el nombre y la edad para usarlos después. El nombre es texto, la edad es un número.
  - _Herramienta:_ `variables`. Para la edad, necesitaré convertir el texto de `input()` a un número con `int()`.

- **Paso 6 ("Revisar la edad"):**

  - _Pensamiento:_ Aquí hay una decisión. El camino del programa cambia según una condición (edad >= 18).
  - _Herramienta:_ Un condicional `if...else...`. Esta es la herramienta para tomar decisiones.

- **Pasos 7 y 8 ("Preparar un mensaje"):**

  - _Pensamiento:_ Necesito guardar el mensaje apropiado en otra "caja".
  - _Herramienta:_ Otra `variable`.

- **Paso 9 ("Mostrar el saludo final"):**
  - _Pensamiento:_ Necesito combinar el nombre del usuario con el mensaje final y mostrarlo.
  - _Herramienta:_ `print()` usando un f-string para mezclar texto y variables de forma sencilla.

#### Paso 4: Construye la Solución (Traduce el Plan a Código)

Esta es la parte que muchos creen que es "programar", pero como ves, es el resultado de todo el trabajo anterior. Ahora solo tienes que traducir tu plan y tus herramientas al lenguaje Python.

```python
# Paso 1: Saludar y explicar
print("Hola, vamos a verificar si tienes la edad para entrar.")

# Pasos 2 y 3: Pedir y guardar el nombre
nombre_usuario = input("Por favor, dime tu nombre: ")

# Pasos 4 y 5: Pedir y guardar la edad (convirtiendo a número)
edad_usuario_texto = input("Ahora, dime tu edad: ")
edad_usuario_numero = int(edad_usuario_texto)

# Pasos 6, 7 y 8: Tomar la decisión con if/else
if edad_usuario_numero >= 18:
    mensaje_final = "¡Bienvenido/a! Puedes pasar."
else:
    mensaje_final = "Lo siento, no tienes la edad suficiente."

# Paso 9: Mostrar el resultado final
print(f"Hola, {nombre_usuario}. {mensaje_final}")
```

#### Paso 5: Realiza el Control de Calidad (Prueba y Mejora)

Ningún programa es perfecto a la primera. Ahora te pones el sombrero de "tester" y tratas de "romper" tu propio código para encontrar fallos (bugs).

- **El caso feliz:** Prueba con datos que sabes que deberían funcionar. (Ej: Nombre: "Ana", Edad: `25`). ¿Funciona? Perfecto.
- **Los casos límite:** Prueba justo en el borde de las reglas. (Ej: Edad: `18`, Edad: `17`). ¿Se comporta como esperas en ambos casos?
- **Los casos de error:** ¿Qué pasa si el usuario hace algo inesperado?
  - ¿Si deja el nombre en blanco?
  - ¿Si en la edad escribe `"hola"` en vez de un número? ¡El programa se romperá con un `ValueError`!
  - Descubrir esto te lleva a mejorar tu código, por ejemplo, usando un `try...except` para manejar errores y pedirle al usuario que introduzca un número válido.

Cada error que encuentras y solucionas no es un fracaso, es una lección que te hace un programador más fuerte y previsor.
