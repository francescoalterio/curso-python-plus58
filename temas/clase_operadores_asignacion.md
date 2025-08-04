# Clase: Operadores de Asignación Compuesta (`+=`, `-=`, `*=`, `/=`)

## ¿Qué son los operadores de asignación compuesta?

Los operadores `+=`, `-=`, `*=`, `/=` son atajos en Python (y en muchos otros lenguajes) para actualizar el valor de una variable realizando una operación y asignando el resultado a la misma variable.

En vez de escribir:

```python
x = x + 1
```

Puedes escribir:

```python
x += 1
```

Esto es equivalente, pero más corto y legible.

---

## Ejemplos de uso

### Suma acumulativa (`+=`)

```python
contador = 0
contador += 5  # Ahora contador vale 5
contador += 2  # Ahora contador vale 7
```

### Resta acumulativa (`-=`)

```python
saldo = 100
saldo -= 30  # Ahora saldo vale 70
saldo -= 10  # Ahora saldo vale 60
```

### Multiplicación acumulativa (`*=`)

```python
factor = 3
factor *= 4  # Ahora factor vale 12
factor *= 2  # Ahora factor vale 24
```

### División acumulativa (`/=`)

```python
numero = 20
numero /= 5  # Ahora numero vale 4.0
numero /= 2  # Ahora numero vale 2.0
```

---

## ¿Dónde se usan estos operadores?

- En bucles para acumular sumas, restas, productos, etc.
- Para actualizar contadores o acumuladores.
- Para modificar variables de manera más concisa y clara.

---

## Ejemplo práctico: Suma de una lista

```python
numeros = [1, 2, 3, 4, 5]
suma = 0
for n in numeros:
    suma += n  # Suma acumulativa
print(suma)  # Salida: 15
```

---

## Resumen

- `x += y` es igual a `x = x + y`
- `x -= y` es igual a `x = x - y`
- `x *= y` es igual a `x = x * y`
- `x /= y` es igual a `x = x / y`

Estos operadores hacen tu código más limpio y fácil de leer.
