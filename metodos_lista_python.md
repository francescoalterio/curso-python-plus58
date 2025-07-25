## 1. append()

La función `append()` agrega un elemento al final de la lista.

**Parámetros:**

- `element` (tipo: cualquier): Elemento a agregar.

**Retorno:** `None` - Modifica la lista en su lugar.

**Ejemplo:**

```python
lista = [1, 2, 3]
lista.append(4)
print(lista)  # [1, 2, 3, 4]
```

## 2. extend()

La función `extend()` agrega los elementos de un iterable al final de la lista.

**Parámetros:**

- `iterable` (tipo: iterable): Elementos a agregar.

**Retorno:** `None` - Modifica la lista en su lugar.

**Ejemplo:**

```python
lista = [1, 2, 3]
lista.extend([4, 5])
print(lista)  # [1, 2, 3, 4, 5]
```

## 3. insert()

La función `insert()` inserta un elemento en una posición específica de la lista.

**Parámetros:**

- `index` (tipo: `int`): Posición donde insertar.
- `element` (tipo: cualquier): Elemento a insertar.

**Retorno:** `None` - Modifica la lista en su lugar.

**Ejemplo:**

```python
lista = [1, 2, 4]
lista.insert(2, 3)
print(lista)  # [1, 2, 3, 4]
```

## 4. remove()

La función `remove()` elimina la primera aparición de un elemento en la lista.

**Parámetros:**

- `element` (tipo: cualquier): Elemento a eliminar.

**Retorno:** `None` - Modifica la lista en su lugar. Lanza un error si el elemento no existe.

**Ejemplo:**

```python
lista = [1, 2, 3, 2]
lista.remove(2)
print(lista)  # [1, 3, 2]
```

## 5. pop()

La función `pop()` elimina y retorna el elemento en la posición dada. Si no se especifica, elimina el último elemento.

**Parámetros:**

- `index` (tipo: `int`, opcional): Índice del elemento a eliminar. Por defecto, el último.

**Retorno:** Elemento eliminado.

**Ejemplo:**

```python
lista = [1, 2, 3]
valor = lista.pop()
print(valor)  # 3
print(lista)  # [1, 2]
```

## 6. clear()

La función `clear()` elimina todos los elementos de la lista.

**Parámetros:**

- No recibe parámetros.

**Retorno:** `None` - Modifica la lista en su lugar.

**Ejemplo:**

```python
lista = [1, 2, 3]
lista.clear()
print(lista)  # []
```

## 7. index()

La función `index()` devuelve el índice de la primera aparición de un elemento.

**Parámetros:**

- `element` (tipo: cualquier): Elemento a buscar.
- `start` (tipo: `int`, opcional): Índice inicial.
- `end` (tipo: `int`, opcional): Índice final.

**Retorno:** `int` - Índice del elemento. Lanza un error si no existe.

**Ejemplo:**

```python
lista = [1, 2, 3, 2]
print(lista.index(2))  # 1
```

## 8. count()

La función `count()` cuenta cuántas veces aparece un elemento en la lista.

**Parámetros:**

- `element` (tipo: cualquier): Elemento a contar.

**Retorno:** `int` - Número de apariciones.

**Ejemplo:**

```python
lista = [1, 2, 2, 3]
print(lista.count(2))  # 2
```

## 9. sort()

La función `sort()` ordena los elementos de la lista en su lugar.

**Parámetros:**

- `key` (tipo: función, opcional): Función de clave para ordenar.
- `reverse` (tipo: `bool`, opcional): Si es True, ordena de mayor a menor.

**Retorno:** `None` - Modifica la lista en su lugar.

**Ejemplo:**

```python
lista = [3, 1, 2]
lista.sort()
print(lista)  # [1, 2, 3]
```

## 10. reverse()

La función `reverse()` invierte el orden de los elementos de la lista.

**Parámetros:**

- No recibe parámetros.

**Retorno:** `None` - Modifica la lista en su lugar.

**Ejemplo:**

```python
lista = [1, 2, 3]
lista.reverse()
print(lista)  # [3, 2, 1]
```

## 11. copy()

La función `copy()` devuelve una copia superficial de la lista.

**Parámetros:**

- No recibe parámetros.

**Retorno:** `list` - Nueva lista con los mismos elementos.

**Ejemplo:**

```python
lista = [1, 2, 3]
copia = lista.copy()
print(copia)  # [1, 2, 3]
```
