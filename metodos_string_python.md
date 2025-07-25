## 1. lower()

La función `lower()` convierte todos los caracteres de una cadena a minúsculas.

**Parámetros:**

- No recibe parámetros.

**Retorno:** `str` - La cadena en minúsculas.

**Ejemplo:**

```python
cadena = "Hola Mundo"
print(cadena.lower())  # hola mundo
```

## 2. upper()

La función `upper()` convierte todos los caracteres de una cadena a mayúsculas.

**Parámetros:**

- No recibe parámetros.

**Retorno:** `str` - La cadena en mayúsculas.

**Ejemplo:**

```python
cadena = "Hola Mundo"
print(cadena.upper())  # HOLA MUNDO
```

## 3. capitalize()

La función `capitalize()` convierte el primer carácter de la cadena a mayúscula y el resto a minúscula.

**Parámetros:**

- No recibe parámetros.

**Retorno:** `str` - La cadena con la primera letra en mayúscula.

**Ejemplo:**

```python
cadena = "hola mundo"
print(cadena.capitalize())  # Hola mundo
```

## 4. title()

La función `title()` convierte la primera letra de cada palabra en mayúscula.

**Parámetros:**

- No recibe parámetros.

**Retorno:** `str` - La cadena con cada palabra iniciando en mayúscula.

**Ejemplo:**

```python
cadena = "hola mundo"
print(cadena.title())  # Hola Mundo
```

## 5. strip()

La función `strip()` elimina los espacios en blanco al inicio y al final de la cadena.

**Parámetros:**

- `chars` (tipo: `str`, opcional): Caracteres a eliminar. Por defecto, elimina espacios.

**Retorno:** `str` - La cadena sin espacios al inicio ni al final.

**Ejemplo:**

```python
cadena = "  Hola Mundo  "
print(cadena.strip())  # Hola Mundo
```

## 6. replace()

La función `replace()` se utiliza para reemplazar todas las apariciones de una subcadena en una cadena por otra subcadena.

**Parámetros:**

- `old` (tipo: `str`): La subcadena que se desea reemplazar.
- `new` (tipo: `str`): La subcadena por la que se reemplazará.
- `count` (tipo: `int`, opcional): Número máximo de reemplazos a realizar. Por defecto es -1, lo que significa reemplazar todas las apariciones.

**Retorno:** `str` - La cadena resultante después de realizar los reemplazos.

**Ejemplo:**

```python
cadena = "Hola Mundo"
cadena = cadena.replace("Mundo", "Python")
print(cadena)  # Hola Python
```

## 7. split()

La función `split()` divide una cadena en una lista usando un separador.

**Parámetros:**

- `sep` (tipo: `str`, opcional): Separador. Por defecto, cualquier espacio en blanco.
- `maxsplit` (tipo: `int`, opcional): Número máximo de divisiones. Por defecto es -1 (todas).

**Retorno:** `list` - Lista de subcadenas.

**Ejemplo:**

```python
cadena = "uno,dos,tres"
print(cadena.split(","))  # ['uno', 'dos', 'tres']
```

## 8. join()

La función `join()` une los elementos de un iterable en una sola cadena, usando la cadena como separador.

**Parámetros:**

- `iterable` (tipo: `iterable`): Elementos a unir.

**Retorno:** `str` - Cadena resultante de la unión.

**Ejemplo:**

```python
lista = ["uno", "dos", "tres"]
print(",".join(lista))  # uno,dos,tres
```

## 9. find()

La función `find()` busca una subcadena y devuelve el índice de su primera aparición, o -1 si no se encuentra.

**Parámetros:**

- `sub` (tipo: `str`): Subcadena a buscar.
- `start` (tipo: `int`, opcional): Índice inicial.
- `end` (tipo: `int`, opcional): Índice final.

**Retorno:** `int` - Índice de la primera aparición o -1.

**Ejemplo:**

```python
cadena = "Hola Mundo"
print(cadena.find("Mundo"))  # 5
```

## 10. count()

La función `count()` cuenta cuántas veces aparece una subcadena en la cadena.

**Parámetros:**

- `sub` (tipo: `str`): Subcadena a contar.
- `start` (tipo: `int`, opcional): Índice inicial.
- `end` (tipo: `int`, opcional): Índice final.

**Retorno:** `int` - Número de apariciones.

**Ejemplo:**

```python
cadena = "banana"
print(cadena.count("a"))  # 3
```

## 11. startswith()

La función `startswith()` verifica si la cadena comienza con una subcadena.

**Parámetros:**

- `prefix` (tipo: `str` o `tuple`): Prefijo a comprobar.
- `start` (tipo: `int`, opcional): Índice inicial.
- `end` (tipo: `int`, opcional): Índice final.

**Retorno:** `bool` - True si comienza con el prefijo, False en caso contrario.

**Ejemplo:**

```python
cadena = "Hola Mundo"
print(cadena.startswith("Hola"))  # True
```

## 12. endswith()

La función `endswith()` verifica si la cadena termina con una subcadena.

**Parámetros:**

- `suffix` (tipo: `str` o `tuple`): Sufijo a comprobar.
- `start` (tipo: `int`, opcional): Índice inicial.
- `end` (tipo: `int`, opcional): Índice final.

**Retorno:** `bool` - True si termina con el sufijo, False en caso contrario.

**Ejemplo:**

```python
cadena = "Hola Mundo"
print(cadena.endswith("Mundo"))  # True
```

## 13. isdigit()

La función `isdigit()` verifica si todos los caracteres de la cadena son dígitos.

**Parámetros:**

- No recibe parámetros.

**Retorno:** `bool` - True si todos los caracteres son dígitos, False en caso contrario.

**Ejemplo:**

```python
cadena = "12345"
print(cadena.isdigit())  # True
```

## 14. isnumeric()

La función `isnumeric()` verifica si todos los caracteres de la cadena son numéricos.

**Parámetros:**

- No recibe parámetros.

**Retorno:** `bool` - True si todos los caracteres son numéricos, False en caso contrario.

**Ejemplo:**

```python
cadena = "Ⅻ"
print(cadena.isnumeric())  # True
```

## 15. isalpha()

La función `isalpha()` verifica si todos los caracteres de la cadena son letras.

**Parámetros:**

- No recibe parámetros.

**Retorno:** `bool` - True si todos los caracteres son letras, False en caso contrario.

**Ejemplo:**

```python
cadena = "Hola"
print(cadena.isalpha())  # True
```

## 16. isalnum()

La función `isalnum()` verifica si todos los caracteres de la cadena son alfanuméricos.

**Parámetros:**

- No recibe parámetros.

**Retorno:** `bool` - True si todos los caracteres son alfanuméricos, False en caso contrario.

**Ejemplo:**

```python
cadena = "Hola123"
print(cadena.isalnum())  # True
```

## 17. zfill()

La función `zfill()` rellena la cadena con ceros a la izquierda hasta alcanzar una longitud especificada.

**Parámetros:**

- `width` (tipo: `int`): Longitud deseada.

**Retorno:** `str` - Cadena rellenada con ceros a la izquierda.

**Ejemplo:**

```python
cadena = "42"
print(cadena.zfill(5))  # 00042
```
