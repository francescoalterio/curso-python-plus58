# Análisis de Código: Sigue el Hilo del Programa

En cada ejercicio analiza el código, predice la salida y explica la lógica. La explicación está oculta bajo un bloque `<details>`.

---

### Código 1

```python
def funcion_1(lista):
    total = 0
    for n in lista:
        if n % 2 == 0:
            total += n
    return total

print(funcion_1([1, 2, 3, 4, 5, 6]))
```

<details>
  <summary>Haz clic aquí para ver la explicación</summary>
  Suma solo los números pares de la lista. Salida: 2+4+6=12
</details>

---

### Código 2

```python
def funcion_2(frase):
    palabras = frase.split()
    resultado = []
    for p in palabras:
        if len(p) > 3:
            resultado.append(p[::-1])
        else:
            resultado.append(p)
    return " ".join(resultado)

print(funcion_2("Hola a todos en clase"))
```

<details>
  <summary>Haz clic aquí para ver la explicación</summary>
  Invierte solo las palabras de más de 3 letras. Salida: "aloH a sodot en esalc"
</details>

---

### Código 3

```python
def funcion_3(d, valor_min):
    resultado = {}
    for k, v in d.items():
        if v >= valor_min:
            resultado[k] = v
    return resultado

print(funcion_3({'a': 3, 'b': 7, 'c': 2, 'd': 10}, 5))
```

<details>
  <summary>Haz clic aquí para ver la explicación</summary>
  Devuelve un nuevo diccionario solo con los valores mayores o iguales a 5. Salida: {'b': 7, 'd': 10}
</details>

---

### Código 4

```python
def funcion_4(texto):
    contador = 0
    for letra in texto.lower():
        if letra in "aeiou":
            contador += 1
    return contador

print(funcion_4("Python es divertido"))
```

<details>
  <summary>Haz clic aquí para ver la explicación</summary>
  Cuenta cuántas vocales hay en la frase. Salida: 6
</details>

---

### Código 5

```python
def funcion_5(lista):
    mayor = menor = lista[0]
    for n in lista:
        if n > mayor:
            mayor = n
        if n < menor:
            menor = n
    return mayor, menor

print(funcion_5([8, 3, 5, 1, 9, 2]))
```

<details>
  <summary>Haz clic aquí para ver la explicación</summary>
  Devuelve el mayor y menor de la lista. Salida: (9, 1)
</details>

---

### Código 6

```python
def funcion_6(palabra):
    palabra = palabra.lower().replace(" ", "")
    return palabra == palabra[::-1]

print(funcion_6("Anita lava la tina"))
```

<details>
  <summary>Haz clic aquí para ver la explicación</summary>
  Verifica si la frase es un palíndromo ignorando espacios y mayúsculas. Salida: True
</details>

---

### Código 7

```python
def funcion_7(lista, limite):
    contador = 0
    for n in lista:
        if n > limite:
            contador += 1
    return contador

print(funcion_7([2, 5, 8, 1, 10], 4))
```

<details>
  <summary>Haz clic aquí para ver la explicación</summary>
  Cuenta cuántos números son mayores que 4. Salida: 3
</details>

---

### Código 8

```python
def funcion_8(numero):
    total = 0
    for d in str(numero):
        total += int(d)
    return total

print(funcion_8(12345))
```

<details>
  <summary>Haz clic aquí para ver la explicación</summary>
  Suma los dígitos del número. Salida: 15
</details>

---

### Código 9

```python
def funcion_9(texto):
    resultado = ""
    for letra in texto:
        if letra.lower() in "aeiou":
            resultado += "*"
        else:
            resultado += letra
    return resultado

print(funcion_9("Python"))
```

<details>
  <summary>Haz clic aquí para ver la explicación</summary>
  Reemplaza las vocales por asteriscos. Salida: Pyth*n
</details>

---

### Código 10

```python
def funcion_10(frase):
    palabras = frase.split()
    return len(palabras)

print(funcion_10("Esto es un ejercicio de análisis"))
```

<details>
  <summary>Haz clic aquí para ver la explicación</summary>
  Cuenta cuántas palabras hay en la frase. Salida: 6
</details>
