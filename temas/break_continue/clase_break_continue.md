# Uso de `break` y `continue` en Bucles

¡Hola! En esta clase vamos a aprender sobre dos herramientas muy útiles para controlar el comportamiento de nuestros bucles `for` y `while`: las sentencias `break` y `continue`.

A veces, cuando estamos iterando sobre una secuencia, queremos detener el bucle por completo si se cumple una condición, o simplemente saltar a la siguiente iteración sin ejecutar todo el código del bucle. Para eso, usamos `break` y `continue`.

---

## 1. `break`: Rompiendo el bucle

La sentencia `break` se utiliza para **terminar un bucle inmediatamente**. Cuando Python encuentra un `break`, sale del bucle en el que se encuentra y continúa con la siguiente línea de código fuera del bucle.

Es como si dijeras: "¡He encontrado lo que buscaba, ya no necesito seguir!".

### Ejemplo con `for`

Imagina que queremos buscar el número 5 en una lista de números. Una vez que lo encontramos, no tiene sentido seguir buscando.

```python
numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

for numero in numeros:
    print(f"Buscando en el número: {numero}")
    if numero == 5:
        print("¡Lo encontré!")
        break  # Salimos del bucle aquí

print("Fin del programa.")
```

**Salida:**

```
Buscando en el número: 1
Buscando en el número: 2
Buscando en el número: 3
Buscando en el número: 4
Buscando en el número: 5
¡Lo encontré!
Fin del programa.
```

Como puedes ver, el bucle se detuvo en el `5` y no continuó hasta el `10`.

### Ejemplo con `while`

También funciona con bucles `while`. Este bucle se detendrá si el usuario escribe "salir".

```python
while True:  # Este es un bucle infinito
    entrada = input("Escribe algo (o 'salir' para terminar): ")
    if entrada == "salir":
        break  # Rompemos el bucle si el usuario quiere salir
    print(f"Has escrito: {entrada}")

print("¡Adiós!")
```

---

## 2. `continue`: Saltando a la siguiente iteración

La sentencia `continue` se utiliza para **saltar el resto del código de la iteración actual** y pasar directamente a la siguiente. No rompe el bucle, solo omite una parte de él.

Es como si dijeras: "Este elemento no me interesa, ¡siguiente!".

### Ejemplo con `for`

Supongamos que queremos imprimir solo los números pares de una lista. Si encontramos un número impar, lo saltamos.

```python
numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

for numero in numeros:
    if numero % 2 != 0:  # Si el número es impar
        continue  # Saltamos a la siguiente iteración

    # Este print solo se ejecuta si el número es par
    print(f"El número par es: {numero}")
```

**Salida:**

```
El número par es: 2
El número par es: 4
El número par es: 6
El número par es: 8
El número par es: 10
```

Como ves, cuando `numero` era impar, el `continue` hacía que el bucle saltara directamente a la siguiente iteración, ignorando el `print()`.

---

## Resumen

| Sentencia  | ¿Qué hace?                                     | ¿El bucle continúa? |
| :--------- | :--------------------------------------------- | :------------------ |
| `break`    | Termina el bucle por completo.                 | No.                 |
| `continue` | Salta la iteración actual y va a la siguiente. | Sí.                 |

## ¡A practicar!

Aquí tienes algunos ejercicios para que pongas a prueba tus nuevos conocimientos:

1.  **Buscador de nombres:** Crea una lista de nombres y un bucle que busque un nombre específico. Cuando lo encuentre, imprime un mensaje y detén el bucle.
2.  **Contador de vocales (sin 'i'):** Escribe un programa que recorra una frase y cuente todas las vocales, pero que ignore la vocal 'i'.
3.  **Juego de adivinanza:** Crea un bucle `while` que le pida al usuario adivinar un número secreto. Si lo adivina, felicítalo y usa `break` para terminar el juego.

¡Espero que esta lección te haya sido útil!
