# Guía Rápida de Herramientas Python Vistas en el Curso

Esta guía te ayudará a recordar qué herramientas y conceptos puedes usar para resolver los ejercicios. No es una explicación profunda, sino un resumen para que sepas qué buscar y cuándo usarlo.

---

## Variables

Sirven para guardar información. Puedes guardar números, texto, listas, etc.

```python
nombre = "Ana"
edad = 20
```

## Tipos de datos básicos

- **int**: Números enteros (`5`, `-3`)
- **float**: Números decimales (`3.14`, `-0.5`)
- **str**: Cadenas de texto (`"hola"`)
- **bool**: Booleanos (`True`, `False`)

## Entrada y salida

- `input()`: Pide datos al usuario (siempre devuelve texto).
- `print()`: Muestra información en pantalla.

## Conversión de tipos

- `int()`, `float()`, `str()`: Convierte entre tipos de datos.

## Operadores

- **Aritméticos**: `+`, `-`, `*`, `/`, `//`, `%`, `**`
- **Comparación**: `==`, `!=`, `<`, `>`, `<=`, `>=`
- **Lógicos**: `and`, `or`, `not`

## Estructuras de control

- **if, elif, else**: Permiten tomar decisiones según condiciones.

```python
if edad >= 18:
    print("Eres mayor de edad")
else:
    print("Eres menor de edad")
```

- **for**: Repite un bloque de código para cada elemento de una secuencia (lista, string, etc).

```python
for letra in "python":
    print(letra)
```

- **while**: Repite un bloque de código mientras se cumpla una condición.

```python
contador = 0
while contador < 5:
    print(contador)
    contador += 1
```

- **break**: Sale del bucle antes de que termine.
- **continue**: Salta a la siguiente iteración del bucle.
- **range()**: Genera una secuencia de números para usar en bucles.

## Listas

Sirven para guardar varios valores en una sola variable.

```python
frutas = ["manzana", "pera", "uva"]
```

- Acceso por índice: `frutas[0]`
- Métodos útiles: `append()`, `remove()`, `pop()`, `insert()`, `count()`, `index()`
- Recorrer con `for`:

```python
for fruta in frutas:
    print(fruta)
```

## Diccionarios

Permiten guardar pares clave-valor.

```python
persona = {"nombre": "Ana", "edad": 20}
```

- Acceso por clave: `persona["nombre"]`
- Métodos útiles: `keys()`, `values()`, `items()`, `get()`, `pop()`
- Recorrer con `for clave in persona:` o `for clave, valor in persona.items():`

## Métodos de cadenas

Permiten modificar o analizar texto.

- `.upper()`, `.lower()`, `.strip()`, `.find()`, `.replace()`, `.count()`, `.startswith()`, `.endswith()`, `.capitalize()`, `.title()`, `.split()`, `.join()`, `.isalpha()`, `.isdigit()`, `.isalnum()`, `.isspace()`

## Comentarios

Sirven para explicar el código. No se ejecutan.

```python
# Esto es un comentario
```

---

**Consejo:**
Cuando tengas un problema, piensa:

- ¿Qué datos necesito guardar? (variables, listas, diccionarios)
- ¿Qué operaciones necesito hacer? (sumar, comparar, buscar, recorrer)
- ¿Qué estructura de control me ayuda? (if, for, while)
- ¿Qué métodos me facilitan el trabajo? (métodos de listas, cadenas, diccionarios)

---

## Operadores de asignación compuesta (`+=`, `-=`, `*=`, `/=`)

Permiten actualizar el valor de una variable de forma más corta y clara:

- `x += y` es igual a `x = x + y`
- `x -= y` es igual a `x = x - y`
- `x *= y` es igual a `x = x * y`
- `x /= y` es igual a `x = x / y`

Se usan mucho en bucles y acumuladores.

---

## Slicing de cadenas y listas

Permite obtener una parte (subsecuencia) de una cadena o lista usando la sintaxis:

- `secuencia[inicio:fin]` → desde el índice `inicio` hasta antes de `fin`.
- `secuencia[inicio:fin:paso]` → puedes saltar elementos.
- Puedes omitir `inicio` o `fin` para ir desde el principio o hasta el final.
- Los índices negativos cuentan desde el final.

Ejemplo:

```python
texto = "Hola mundo"
print(texto[0:4])    # 'Hola'
print(texto[-5:])    # 'mundo'
lista = [1,2,3,4,5]
print(lista[::2])    # [1,3,5]
```

El slicing es útil para extraer, invertir o copiar partes de secuencias.

---

¡Usa esta guía como referencia rápida cuando no sepas por dónde empezar!
