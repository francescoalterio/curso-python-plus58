# Clase 10: Slicing (Rebanado) de Cadenas y Listas

## ¿Qué es el Slicing?

El "slicing" (o rebanado) es una característica increíblemente poderosa de Python que te permite acceder a partes o subconjuntos de una secuencia, como una cadena de texto o una lista. En lugar de obtener un solo elemento por su índice, el slicing te permite obtener una "rebanada" completa de la secuencia.

La sintaxis básica es `secuencia[inicio:fin]`, donde:

- `inicio`: Es el índice donde comienza la rebanada (incluido).
- `fin`: Es el índice donde termina la rebanada (NO incluido).

¡Piénsalo como si estuvieras cortando una rebanada de pan!

---

## Slicing en Cadenas de Texto

El slicing funciona de la misma manera para cadenas y listas. Veamos primero con cadenas.

```python
saludo = "Hola, Mundo"
# Índices: 012345678910

# Obtener la palabra "Hola"
# Empieza en el índice 0 y termina ANTES del índice 4
rebanada_hola = saludo[0:4]
print(rebanada_hola)  # Salida: "Hola"

# Obtener la palabra "Mundo"
# Empieza en el índice 6 y termina ANTES del índice 11
rebanada_mundo = saludo[6:11]
print(rebanada_mundo) # Salida: "Mundo"
```

### Atajos para el Slicing

Python nos ofrece atajos para hacer el slicing más fácil:

**1. Omitir el `inicio`:** Si omites el índice de `inicio`, Python asumirá que quieres empezar desde el principio (índice 0).

```python
saludo = "Hola, Mundo"

# Obtener desde el principio hasta el índice 4 (no incluido)
rebanada = saludo[:4]
print(rebanada) # Salida: "Hola"
```

**2. Omitir el `fin`:** Si omites el índice de `fin`, Python asumirá que quieres ir hasta el final de la secuencia.

```python
saludo = "Hola, Mundo"

# Obtener desde el índice 6 hasta el final
rebanada = saludo[6:]
print(rebanada) # Salida: "Mundo"
```

**3. Índices Negativos:** También puedes usar índices negativos. Recuerda que `-1` es el último elemento.

```python
saludo = "Hola, Mundo"

# Obtener los últimos 5 caracteres ("Mundo")
# Empieza en el 5to caracter desde el final y va hasta el final
rebanada = saludo[-5:]
print(rebanada) # Salida: "Mundo"

# Obtener todo excepto el último caracter
rebanada = saludo[:-1]
print(rebanada) # Salida: "Hola, Mund"
```

---

## Slicing en Listas

El slicing en listas funciona **exactamente igual** que en las cadenas.

```python
numeros = [10, 20, 30, 40, 50, 60]
# Índices:  0   1   2   3   4   5

# Obtener los elementos 20, 30, 40
# Empieza en el índice 1 y termina ANTES del índice 4
sub_lista = numeros[1:4]
print(sub_lista) # Salida: [20, 30, 40]

# Obtener los primeros tres elementos
primeros_tres = numeros[:3]
print(primeros_tres) # Salida: [10, 20, 30]

# Obtener los últimos dos elementos usando índices negativos
ultimos_dos = numeros[-2:]
print(ultimos_dos) # Salida: [50, 60]
```

### ¡Importante! El Slicing crea una copia

Cuando haces un slicing en una lista, Python crea una **nueva lista** (una copia superficial). La lista original no se modifica.

```python
colores = ["rojo", "verde", "azul", "amarillo"]
sub_colores = colores[1:3] # Crea una nueva lista -> ["verde", "azul"]

# Modificamos la sub-lista
sub_colores[0] = "morado"

print(sub_colores) # Salida: ['morado', 'azul']
print(colores)     # Salida: ['rojo', 'verde', 'azul', 'amarillo'] (La original no cambió)
```

---

## El Tercer Parámetro: `paso` (step)

El slicing tiene un tercer parámetro opcional llamado `paso` (step). La sintaxis completa es `secuencia[inicio:fin:paso]`.

- `paso`: Indica cuántos elementos saltar. Por defecto es 1.

```python
numeros = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

# Obtener todos los números de 2 en 2 (los pares)
pares = numeros[::2] # inicio y fin omitidos, paso = 2
print(pares) # Salida: [0, 2, 4, 6, 8]

# Obtener los números impares
impares = numeros[1::2] # empieza en 1, hasta el final, de 2 en 2
print(impares) # Salida: [1, 3, 5, 7, 9]
```

### El truco para invertir una secuencia

Un uso muy común del `paso` es usar `-1` para invertir una cadena o una lista.

```python
frase = "Python es genial"
frase_invertida = frase[::-1]
print(frase_invertida) # Salida: "laing se nohtyP"

mi_lista = [1, 2, 3, 4, 5]
lista_invertida = mi_lista[::-1]
print(lista_invertida) # Salida: [5, 4, 3, 2, 1]
```

---

## Resumen

- **Slicing Básico:** `secuencia[inicio:fin]`
- **Desde el principio:** `secuencia[:fin]`
- **Hasta el final:** `secuencia[inicio:]`
- **Conteo de pasos:** `secuencia[inicio:fin:paso]`
- **Invertir:** `secuencia[::-1]`
- El slicing crea una **copia** de la rebanada, no modifica el original.
- Funciona de la misma manera para cadenas, listas y otros tipos de secuencias.
