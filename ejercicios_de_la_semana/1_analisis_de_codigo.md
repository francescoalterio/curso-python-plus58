# Análisis de Código

A continuación, encontrarás varios fragmentos de código. Tu tarea es analizarlos sin ejecutarlos y tratar de deducir qué hacen. Las variables y funciones tienen nombres genéricos a propósito para que te centres en la lógica.

Una vez que tengas una idea, haz clic en el desplegable para ver la explicación detallada.

---

### Ejercicio 1

```python
class ProcesadorDatos:
    def __init__(self, lista_numeros):
        self.lista_numeros = lista_numeros
    
    def sumar_pares(self):
        resultado = 0
        for item in self.lista_numeros:
            if item % 2 == 0:
                resultado += item
        return resultado

datos = [10, 21, 30, 45, 50]
procesador = ProcesadorDatos(datos)
valor_final = procesador.sumar_pares()
print(valor_final)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código utiliza una clase `ProcesadorDatos` para calcular la suma de todos los números pares en una lista.

**Análisis paso a paso:**

1.  **`class ProcesadorDatos:`**: Define una clase que encapsula la funcionalidad de procesamiento de datos.
2.  **`def __init__(self, lista_numeros):`**: Constructor que inicializa el objeto con una lista de números.
3.  **`self.lista_numeros = lista_numeros`**: Almacena la lista como atributo de la instancia.
4.  **`def sumar_pares(self):`**: Define un método que calcula la suma de números pares.
5.  **`resultado = 0`**: Inicializa una variable `resultado` en 0. Esta variable actuará como un acumulador.
6.  **`for item in self.lista_numeros:`**: Inicia un bucle que recorre cada número (`item`) en la lista almacenada en el objeto.
7.  **`if item % 2 == 0:`**: Dentro del bucle, comprueba si el número actual (`item`) es par. El operador módulo (`%`) devuelve el resto de una división. Si un número dividido por 2 tiene un resto de 0, significa que es par.
8.  **`resultado += item`**: Si la condición es verdadera (el número es par), se añade ese número al valor actual de `resultado`.
9.  **`return resultado`**: Una vez que el bucle ha recorrido toda la lista, el método devuelve el valor final acumulado en `resultado`.
10. **`datos = [10, 21, 30, 45, 50]`**: Se crea una lista de ejemplo.
11. **`procesador = ProcesadorDatos(datos)`**: Se crea una instancia de la clase `ProcesadorDatos` con la lista `datos`.
12. **`valor_final = procesador.sumar_pares()`**: Se llama al método `sumar_pares()` del objeto y el valor devuelto se guarda en `valor_final`. En este caso, sumará 10 + 30 + 50.
13. **`print(valor_final)`**: Imprime el resultado final, que será `90`.

</details>

---

### Ejercicio 2

```python
class TransformadorTexto:
    def __init__(self, texto):
        self.texto = texto

    def transformar(self):
        nueva_cadena = ""
        vocales = "aeiouAEIOU"
        for caracter in self.texto:
            if caracter not in vocales:
                nueva_cadena += caracter
        return nueva_cadena

texto_original = "Hola Mundo, esto es una prueba"
transformador = TransformadorTexto(texto_original)
texto_modificado = transformador.transformar()
print(texto_modificado)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

El ejercicio 2 define una clase llamada TransformadorTexto que permite eliminar todas las vocales de una cadena de texto. Utiliza un método llamado transformar para procesar el texto original y devolver la versión sin vocales.


</details>

---

### Ejercicio 3

```python
class ManipuladorLista:
    def __init__(self, elementos):
        self.elementos = elementos
    
    def invertir(self):
        final = []
        for i in range(len(self.elementos) - 1, -1, -1):
            final.append(self.elementos[i])
        return final

mi_lista = ["a", "b", "c", "d"]
manipulador = ManipuladorLista(mi_lista)
lista_invertida = manipulador.invertir()
print(lista_invertida)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código utiliza una clase `ManipuladorLista` para invertir el orden de los elementos en una lista sin usar el método `.reverse()` o slicing (`[::-1]`).

**Análisis paso a paso:**

1.  **`class ManipuladorLista:`**: Define una clase que encapsula las operaciones de manipulación de listas.
2.  **`def __init__(self, elementos):`**: Constructor que inicializa el objeto con una lista de elementos.
3.  **`self.elementos = elementos`**: Almacena la lista como atributo de la instancia.
4.  **`def invertir(self):`**: Define un método que invierte la lista.
5.  **`final = []`**: Crea una nueva lista vacía donde se guardará el resultado invertido.
6.  **`for i in range(len(self.elementos) - 1, -1, -1):`**: Este es el núcleo de la lógica.
    - `len(self.elementos)`: Obtiene la longitud de la lista almacenada en el objeto (en este caso, 4).
    - `len(self.elementos) - 1`: Calcula el índice del último elemento (en este caso, 3).
    - `range(start, stop, step)`: `range(3, -1, -1)` genera una secuencia de números hacia atrás: `3, 2, 1, 0`. Estos son los índices de la lista en orden inverso.
7.  **`final.append(self.elementos[i])`**: En cada paso del bucle, se toma el elemento de la lista original en la posición del índice inverso (`i`) y se añade a la nueva lista `final`.
    - Primera iteración: `i` es 3. `final.append(self.elementos[3])` -> `final` es `['d']`.
    - Segunda iteración: `i` es 2. `final.append(self.elementos[2])` -> `final` es `['d', 'c']`.
    - Y así sucesivamente.
8.  **`return final`**: Devuelve la nueva lista con los elementos en orden inverso.
9.  **`mi_lista = ["a", "b", "c", "d"]`**: Se crea una lista de ejemplo.
10. **`manipulador = ManipuladorLista(mi_lista)`**: Se crea una instancia de la clase con la lista.
11. **`lista_invertida = manipulador.invertir()`**: Se llama al método `invertir()` del objeto.
12. **`print(lista_invertida)`**: Imprime el resultado, que será `['d', 'c', 'b', 'a']`.

</details>

---

### Ejercicio 4

```python
class BuscadorValor:
    def __init__(self, datos):
        self.datos = datos
    
    def encontrar_maximo(self):
        maximo = self.datos[0]
        for n in self.datos:
            if n > maximo:
                maximo = n
        return maximo

numeros = [3, 11, 5, 8, 2]
buscador = BuscadorValor(numeros)
resultado = buscador.encontrar_maximo()
print(resultado)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código utiliza una clase `BuscadorValor` para encontrar el número más grande (el máximo) en una lista de números.

**Análisis paso a paso:**

1.  **`class BuscadorValor:`**: Define una clase que encapsula la funcionalidad de búsqueda de valores.
2.  **`def __init__(self, datos):`**: Constructor que inicializa el objeto con una lista de datos.
3.  **`self.datos = datos`**: Almacena la lista como atributo de la instancia.
4.  **`def encontrar_maximo(self):`**: Define un método que encuentra el valor máximo en la lista.
5.  **`maximo = self.datos[0]`**: Inicializa una variable `maximo` con el primer elemento de la lista almacenada en el objeto.
6.  **`for n in self.datos:`**: Recorre cada número `n` en la lista.
7.  **`if n > maximo:`**: Comprueba si el número actual `n` es mayor que el valor guardado en `maximo`.
8.  **`maximo = n`**: Si el número actual es mayor, actualiza `maximo` con el valor de `n`.
9.  **`return maximo`**: Después de revisar toda la lista, devuelve el valor más grande encontrado.
10. **`numeros = [3, 11, 5, 8, 2]`**: Se crea una lista de ejemplo.
11. **`buscador = BuscadorValor(numeros)`**: Se crea una instancia de la clase con la lista de números.
12. **`resultado = buscador.encontrar_maximo()`**: Se llama al método `encontrar_maximo()` del objeto.
13. **`print(resultado)`**: Imprime el resultado, que será `11`.

</details>

---

### Ejercicio 5

```python
class ContadorElementos:
    def __init__(self, lista):
        self.lista = lista
    
    def contar_elemento(self, elemento_buscado):
        contador = 0
        for item in self.lista:
            if item == elemento_buscado:
                contador += 1
        return contador

items = ["a", "b", "a", "c", "a", "d"]
contador = ContadorElementos(items)
veces = contador.contar_elemento("a")
print(veces)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código utiliza una clase `ContadorElementos` para contar cuántas veces aparece un elemento específico dentro de una lista.

**Análisis paso a paso:**

1.  **`class ContadorElementos:`**: Define una clase que encapsula la funcionalidad de conteo de elementos.
2.  **`def __init__(self, lista):`**: Constructor que inicializa el objeto con una lista.
3.  **`self.lista = lista`**: Almacena la lista como atributo de la instancia.
4.  **`def contar_elemento(self, elemento_buscado):`**: Define un método que cuenta las ocurrencias de un elemento específico.
5.  **`contador = 0`**: Inicializa un contador en 0.
6.  **`for item in self.lista:`**: Itera sobre cada `item` en la lista almacenada en el objeto.
7.  **`if item == elemento_buscado:`**: Comprueba si el `item` actual es igual al `elemento_buscado`.
8.  **`contador += 1`**: Si son iguales, incrementa el `contador`.
9.  **`return contador`**: Devuelve el número total de veces que se encontró el elemento.
10. **`items = ["a", "b", "a", "c", "a", "d"]`**: Se crea una lista de ejemplo.
11. **`contador = ContadorElementos(items)`**: Se crea una instancia de la clase con la lista.
12. **`veces = contador.contar_elemento("a")`**: Se llama al método `contar_elemento()` del objeto.
13. **`print(veces)`**: Imprime el resultado, que será `3`.

</details>

---

### Ejercicio 6

```python
class CreadorMapa:
    def __init__(self, claves, valores):
        self.claves = claves
        self.valores = valores
    
    def crear_diccionario(self):
        mapa = {}
        for i in range(len(self.claves)):
            mapa[self.claves[i]] = self.valores[i]
        return mapa

lista_claves = ["uno", "dos", "tres"]
lista_valores = [1, 2, 3]
creador = CreadorMapa(lista_claves, lista_valores)
diccionario = creador.crear_diccionario()
print(diccionario)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código utiliza una clase `CreadorMapa` para crear un diccionario a partir de dos listas, una que contiene las claves y otra que contiene los valores.

**Análisis paso a paso:**

1.  **`class CreadorMapa:`**: Define una clase que encapsula la funcionalidad de creación de diccionarios.
2.  **`def __init__(self, claves, valores):`**: Constructor que inicializa el objeto con una lista de claves y una de valores.
3.  **`self.claves = claves`**: Almacena la lista de claves como atributo de la instancia.
4.  **`self.valores = valores`**: Almacena la lista de valores como atributo de la instancia.
5.  **`def crear_diccionario(self):`**: Define un método que crea el diccionario.
6.  **`mapa = {}`**: Crea un diccionario vacío.
7.  **`for i in range(len(self.claves)):`**: Itera usando un índice `i` desde 0 hasta la longitud de la lista de claves menos uno.
8.  **`mapa[self.claves[i]] = self.valores[i]`**: En cada iteración, usa el elemento en la posición `i` de `self.claves` como la nueva clave en el `mapa`, y le asigna el elemento en la misma posición `i` de la lista de `self.valores`.
9.  **`return mapa`**: Devuelve el diccionario completo.
10. **`lista_claves = ["uno", "dos", "tres"]`**: Se crea una lista de claves.
11. **`lista_valores = [1, 2, 3]`**: Se crea una lista de valores.
12. **`creador = CreadorMapa(lista_claves, lista_valores)`**: Se crea una instancia de la clase con ambas listas.
13. **`diccionario = creador.crear_diccionario()`**: Se llama al método `crear_diccionario()` del objeto.
14. **`print(diccionario)`**: Imprime el resultado, que será `{'uno': 1, 'dos': 2, 'tres': 3}`.

</details>

---

### Ejercicio 7

```python
def es_simetrico(texto):
    texto_limpio = ""
    for char in texto:
        if char != " ":
            texto_limpio += char.lower()

    return texto_limpio == texto_limpio[::-1]

palabra = "Anita lava la tina"
resultado = es_simetrico(palabra)
print(resultado)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código verifica si una cadena de texto es un palíndromo (se lee igual de izquierda a derecha que de derecha a izquierda), ignorando espacios y mayúsculas/minúsculas.

**Análisis paso a paso:**

1.  **`def es_simetrico(texto):`**: Define una función que recibe una cadena de texto.
2.  **`texto_limpio = ""`**: Inicializa una cadena vacía para guardar la versión "limpia" del texto.
3.  **`for char in texto:`**: Itera sobre cada caracter del texto original.
4.  **`if char != " ":`**: Comprueba si el caracter no es un espacio.
5.  **`texto_limpio += char.lower()`**: Si no es un espacio, lo convierte a minúscula y lo añade a `texto_limpio`. Al final del bucle, `texto_limpio` será `anitalavalatina`.
6.  **`return texto_limpio == texto_limpio[::-1]`**: Compara el texto limpio con su versión invertida (`[::-1]` es una forma de invertir una cadena). Devuelve `True` si son iguales, `False` si no.
7.  **`print(resultado)`**: Imprime el resultado, que será `True`.

</details>

---

### Ejercicio 8

```python
def generar_secuencia(limite):
    secuencia = []
    for i in range(1, limite + 1):
        secuencia.append(i * i)
    return secuencia

numero_limite = 5
cuadrados = generar_secuencia(numero_limite)
print(cuadrados)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código genera una lista con los cuadrados de los números desde 1 hasta un límite especificado.

**Análisis paso a paso:**

1.  **`def generar_secuencia(limite):`**: Define una función que toma un número `limite` como argumento.
2.  **`secuencia = []`**: Crea una lista vacía para almacenar los resultados.
3.  **`for i in range(1, limite + 1):`**: Inicia un bucle que genera números desde 1 hasta `limite` (inclusive). Para `limite = 5`, el rango será `1, 2, 3, 4, 5`.
4.  **`secuencia.append(i * i)`**: En cada iteración, calcula el cuadrado del número `i` y lo añade a la lista `secuencia`.
5.  **`return secuencia`**: Devuelve la lista de cuadrados.
6.  **`print(cuadrados)`**: Imprime el resultado, que será `[1, 4, 9, 16, 25]`.

</details>

---

### Ejercicio 9

```python
def aplanar_estructura(lista_anidada):
    plana = []
    for sublista in lista_anidada:
        for item in sublista:
            plana.append(item)
    return plana

matriz = [[1, 2], [3, 4, 5], [6]]
lista_plana = aplanar_estructura(matriz)
print(lista_plana)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código "aplana" una lista de listas, es decir, convierte una lista de varias listas en una sola lista que contiene todos los elementos.

**Análisis paso a paso:**

1.  **`def aplanar_estructura(lista_anidada):`**: Define una función que toma una lista de listas.
2.  **`plana = []`**: Crea una lista vacía para el resultado.
3.  **`for sublista in lista_anidada:`**: El primer bucle itera sobre cada una de las listas internas (las `sublista`).
4.  **`for item in sublista:`**: El segundo bucle (anidado) itera sobre cada `item` dentro de la `sublista` actual.
5.  **`plana.append(item)`**: Añade cada `item` individual a la lista `plana`.
6.  **`return plana`**: Devuelve la lista aplanada.
7.  **`print(lista_plana)`**: Imprime el resultado, que será `[1, 2, 3, 4, 5, 6]`.

</details>

---

### Ejercicio 10

```python
def encontrar_comunes(lista1, lista2):
    comunes = []
    for item1 in lista1:
        if item1 in lista2:
            comunes.append(item1)
    return comunes

grupo_a = [1, 2, 3, 4, 5]
grupo_b = [4, 5, 6, 7, 8]
elementos_comunes = encontrar_comunes(grupo_a, grupo_b)
print(elementos_comunes)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código encuentra los elementos que son comunes a dos listas y los devuelve en una nueva lista.

**Análisis paso a paso:**

1.  **`def encontrar_comunes(lista1, lista2):`**: Define una función que acepta dos listas.
2.  **`comunes = []`**: Inicializa una lista vacía para guardar los elementos comunes.
3.  **`for item1 in lista1:`**: Itera sobre cada elemento en la primera lista (`lista1`).
4.  **`if item1 in lista2:`**: Para cada elemento de `lista1`, comprueba si también existe en `lista2`.
5.  **`comunes.append(item1)`**: Si el elemento está en ambas listas, se añade a la lista `comunes`.
6.  **`return comunes`**: Devuelve la lista de elementos comunes.
7.  **`print(elementos_comunes)`**: Imprime el resultado, que será `[4, 5]`.

</details>

---

### Ejercicio 11

```python
def calcular_valor(n):
    if n == 0:
        return 1
    resultado = 1
    for i in range(1, n + 1):
        resultado *= i
    return resultado

numero = 5
factorial = calcular_valor(numero)
print(factorial)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código calcula el factorial de un número entero no negativo.

**Análisis paso a paso:**

1.  **`def calcular_valor(n):`**: Define una función que toma un número `n`.
2.  **`if n == 0:`**: Caso especial: el factorial de 0 es 1.
3.  **`resultado = 1`**: Inicializa el resultado en 1.
4.  **`for i in range(1, n + 1):`**: Itera desde 1 hasta `n`. Para `n=5`, los valores de `i` serán 1, 2, 3, 4, 5.
5.  **`resultado *= i`**: Multiplica el `resultado` actual por el número de la iteración `i`.
    - 1 \* 1 = 1
    - 1 \* 2 = 2
    - 2 \* 3 = 6
    - 6 \* 4 = 24
    - 24 \* 5 = 120
6.  **`return resultado`**: Devuelve el resultado final.
7.  **`print(factorial)`**: Imprime el resultado, que será `120`.

</details>

---

### Ejercicio 12

```python
def filtrar_unicos(lista_original):
    lista_unica = []
    for item in lista_original:
        if item not in lista_unica:
            lista_unica.append(item)
    return lista_unica

datos_repetidos = [1, 2, 2, 3, 4, 4, 4, 5]
datos_unicos = filtrar_unicos(datos_repetidos)
print(datos_unicos)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código elimina los elementos duplicados de una lista, conservando el orden de la primera aparición de cada elemento.

**Análisis paso a paso:**

1.  **`def filtrar_unicos(lista_original):`**: Define una función que toma una lista.
2.  **`lista_unica = []`**: Crea una nueva lista vacía que contendrá solo elementos únicos.
3.  **`for item in lista_original:`**: Itera sobre cada elemento de la lista original.
4.  **`if item not in lista_unica:`**: Comprueba si el elemento actual **no** ha sido añadido ya a `lista_unica`.
5.  **`lista_unica.append(item)`**: Si el elemento no está en `lista_unica`, lo añade. Si ya está, este paso se omite.
6.  **`return lista_unica`**: Devuelve la lista sin duplicados.
7.  **`print(datos_unicos)`**: Imprime el resultado, que será `[1, 2, 3, 4, 5]`.

</details>

---

### Ejercicio 13

```python
def invertir_diccionario(d):
    inverso = {}
    for clave, valor in d.items():
        inverso[valor] = clave
    return inverso

mapa_original = {"a": 1, "b": 2, "c": 3}
mapa_invertido = invertir_diccionario(mapa_original)
print(mapa_invertido)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código invierte un diccionario, intercambiando sus claves y valores. Asume que todos los valores del diccionario original son únicos.

**Análisis paso a paso:**

1.  **`def invertir_diccionario(d):`**: Define una función que toma un diccionario `d`.
2.  **`inverso = {}`**: Crea un nuevo diccionario vacío para el resultado.
3.  **`for clave, valor in d.items():`**: Itera sobre cada par clave-valor del diccionario original.
4.  **`inverso[valor] = clave`**: Asigna una nueva entrada en el diccionario `inverso` donde la clave es el `valor` original y el valor es la `clave` original.
5.  **`return inverso`**: Devuelve el diccionario invertido.
6.  **`print(mapa_invertido)`**: Imprime el resultado, que será `{1: 'a', 2: 'b', 3: 'c'}`.

</details>

---

### Ejercicio 14

```python
def verificar_unicidad(elementos):
    vistos = []
    for elemento in elementos:
        if elemento in vistos:
            return False
        vistos.append(elemento)
    return True

lista1 = [1, 2, 3, 4, 5]
lista2 = [1, 2, 3, 2, 4]
print(verificar_unicidad(lista1))
print(verificar_unicidad(lista2))
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código comprueba si todos los elementos de una lista son únicos. Devuelve `True` si no hay duplicados y `False` si encuentra al menos un duplicado.

**Análisis paso a paso:**

1.  **`def verificar_unicidad(elementos):`**: Define una función que toma una lista.
2.  **`vistos = []`**: Crea una lista para registrar los elementos que ya se han encontrado.
3.  **`for elemento in elementos:`**: Itera sobre cada `elemento` de la lista de entrada.
4.  **`if elemento in vistos:`**: Comprueba si el `elemento` actual ya está en la lista `vistos`.
5.  **`return False`**: Si el elemento ya ha sido visto, significa que es un duplicado, por lo que la función termina inmediatamente y devuelve `False`.
6.  **`vistos.append(elemento)`**: Si el elemento no es un duplicado, se añade a la lista `vistos`.
7.  **`return True`**: Si el bucle termina sin encontrar duplicados, significa que todos los elementos son únicos, y la función devuelve `True`.
8.  **`print(...)`**: Imprime los resultados de las llamadas, que serán `True` para `lista1` y `False` para `lista2`.

</details>

---

### Ejercicio 15

```python
def procesar_frase(frase):
    palabras = frase.split(' ')
    resultado = []
    for palabra in palabras:
        if palabra:
            palabra_modificada = palabra[0].upper() + palabra[1:]
            resultado.append(palabra_modificada)
    return ' '.join(resultado)

texto = "hola mundo desde python"
texto_capitalizado = procesar_frase(texto)
print(texto_capitalizado)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código capitaliza la primera letra de cada palabra en una frase.

**Análisis paso a paso:**

1.  **`def procesar_frase(frase):`**: Define una función que toma una frase (cadena de texto).
2.  **`palabras = frase.split(' ')`**: Divide la frase en una lista de palabras usando el espacio como separador.
3.  **`resultado = []`**: Crea una lista vacía para guardar las palabras modificadas.
4.  **`for palabra in palabras:`**: Itera sobre cada `palabra` en la lista de palabras.
5.  **`if palabra:`**: Comprueba que la palabra no esté vacía (esto puede ocurrir si hay múltiples espacios juntos).
6.  **`palabra_modificada = palabra[0].upper() + palabra[1:]`**: Crea una nueva palabra tomando el primer caracter (`palabra[0]`), convirtiéndolo a mayúscula (`.upper()`), y concatenándolo con el resto de la palabra (`palabra[1:]`).
7.  **`resultado.append(palabra_modificada)`**: Añade la palabra capitalizada a la lista `resultado`.
8.  **`return ' '.join(resultado)`**: Une las palabras de la lista `resultado` en una sola cadena, separándolas con un espacio.
9.  **`print(texto_capitalizado)`**: Imprime el resultado, que será `Hola Mundo Desde Python`.

</details>

---

### Ejercicio 16

```python
def encontrar_mas_larga(texto):
    palabras = texto.split()
    mas_larga = ""
    for palabra in palabras:
        if len(palabra) > len(mas_larga):
            mas_larga = palabra
    return mas_larga

frase = "encuentra la palabra mas larga aqui"
palabra_larga = encontrar_mas_larga(frase)
print(palabra_larga)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código encuentra y devuelve la palabra más larga en una frase.

**Análisis paso a paso:**

1.  **`def encontrar_mas_larga(texto):`**: Define una función que toma una cadena de texto.
2.  **`palabras = texto.split()`**: Divide el texto en una lista de palabras.
3.  **`mas_larga = ""`**: Inicializa una variable para guardar la palabra más larga encontrada hasta el momento. Se inicia como una cadena vacía.
4.  **`for palabra in palabras:`**: Itera sobre cada `palabra` de la lista.
5.  **`if len(palabra) > len(mas_larga):`**: Compara la longitud de la palabra actual con la longitud de la palabra más larga guardada.
6.  **`mas_larga = palabra`**: Si la palabra actual es más larga, se actualiza la variable `mas_larga`.
7.  **`return mas_larga`**: Devuelve la palabra más larga encontrada después de revisar toda la frase.
8.  **`print(palabra_larga)`**: Imprime el resultado, que será `encuentra`.

</details>

---

### Ejercicio 17

```python
def generar_serie(n):
    serie = []
    a, b = 0, 1
    while len(serie) < n:
        serie.append(a)
        a, b = b, a + b
    return serie

cantidad = 10
fibonacci = generar_serie(cantidad)
print(fibonacci)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código genera los primeros `n` números de la secuencia de Fibonacci.

**Análisis paso a paso:**

1.  **`def generar_serie(n):`**: Define una función que toma un número `n` que indica cuántos términos generar.
2.  **`serie = []`**: Crea una lista vacía para almacenar la secuencia.
3.  **`a, b = 0, 1`**: Inicializa las dos primeras variables de la secuencia de Fibonacci.
4.  **`while len(serie) < n:`**: El bucle continúa mientras la longitud de la `serie` sea menor que `n`.
5.  **`serie.append(a)`**: Añade el valor actual de `a` a la lista.
6.  **`a, b = b, a + b`**: Actualiza los valores. El nuevo `a` toma el valor de `b`, y el nuevo `b` toma el valor de la suma de los antiguos `a` y `b`. Esto genera el siguiente número de la secuencia.
7.  **`return serie`**: Devuelve la lista con la secuencia generada.
8.  **`print(fibonacci)`**: Imprime el resultado, que será `[0, 1, 1, 2, 3, 5, 8, 13, 21, 34]`.

</details>

---

### Ejercicio 18

```python
def sumar_valores_mapa(mapa):
    total = 0
    for clave in mapa:
        total += mapa[clave]
    return total

datos_mapa = {"item1": 10, "item2": 25, "item3": 15}
suma_total = sumar_valores_mapa(datos_mapa)
print(suma_total)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código calcula la suma de todos los valores numéricos en un diccionario.

**Análisis paso a paso:**

1.  **`def sumar_valores_mapa(mapa):`**: Define una función que toma un diccionario.
2.  **`total = 0`**: Inicializa una variable `total` para acumular la suma.
3.  **`for clave in mapa:`**: Itera sobre las claves del diccionario.
4.  **`total += mapa[clave]`**: Para cada `clave`, accede a su valor correspondiente en el `mapa` (`mapa[clave]`) y lo suma al `total`.
5.  **`return total`**: Devuelve la suma total de los valores.
6.  **`print(suma_total)`**: Imprime el resultado, que será `50` (10 + 25 + 15).

</details>

---

### Ejercicio 19

```python
def filtrar_numeros(lista, umbral):
    filtrados = []
    for numero in lista:
        if numero > umbral:
            filtrados.append(numero)
    return filtrados

numeros = [1, 10, 5, 25, 15, 30]
mayores_que_12 = filtrar_numeros(numeros, 12)
print(mayores_que_12)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código filtra una lista de números, devolviendo una nueva lista que contiene solo aquellos números que son mayores que un `umbral` especificado.

**Análisis paso a paso:**

1.  **`def filtrar_numeros(lista, umbral):`**: Define una función que toma una lista de números y un valor `umbral`.
2.  **`filtrados = []`**: Crea una lista vacía para almacenar los números que pasen el filtro.
3.  **`for numero in lista:`**: Itera sobre cada `numero` en la lista de entrada.
4.  **`if numero > umbral:`**: Comprueba si el `numero` actual es estrictamente mayor que el `umbral`.
5.  **`filtrados.append(numero)`**: Si la condición es verdadera, añade el `numero` a la lista `filtrados`.
6.  **`return filtrados`**: Devuelve la lista con los números filtrados.
7.  **`print(mayores_que_12)`**: Imprime el resultado, que será `[25, 15, 30]`.

</details>

---

### Ejercicio 20

```python
def combinar_mapas(mapa1, mapa2):
    combinado = mapa1.copy()
    for clave, valor in mapa2.items():
        combinado[clave] = valor
    return combinado

dicc1 = {'a': 1, 'b': 2}
dicc2 = {'b': 3, 'c': 4}
resultado_final = combinar_mapas(dicc1, dicc2)
print(resultado_final)
```

<details>
<summary>Haz clic aquí para ver la explicación</summary>

**¿Qué hace el código?**

Este código combina o fusiona dos diccionarios en uno nuevo. Si una clave existe en ambos diccionarios, el valor del segundo diccionario prevalece.

**Análisis paso a paso:**

1.  **`def combinar_mapas(mapa1, mapa2):`**: Define una función que toma dos diccionarios.
2.  **`combinado = mapa1.copy()`**: Crea una copia del primer diccionario (`mapa1`) para no modificar el original.
3.  **`for clave, valor in mapa2.items():`**: Itera sobre los pares clave-valor del segundo diccionario (`mapa2`).
4.  **`combinado[clave] = valor`**: Asigna el par clave-valor del `mapa2` al diccionario `combinado`. Si la `clave` ya existe en `combinado`, su valor será sobrescrito. Si no existe, se añadirá como una nueva entrada.
    - `combinado` empieza como `{'a': 1, 'b': 2}`.
    - Primera iteración de `mapa2`: `clave='b'`, `valor=3`. `combinado` se convierte en `{'a': 1, 'b': 3}`.
    - Segunda iteración de `mapa2`: `clave='c'`, `valor=4`. `combinado` se convierte en `{'a': 1, 'b': 3, 'c': 4}`.
5.  **`return combinado`**: Devuelve el diccionario fusionado.
6.  **`print(resultado_final)`**: Imprime el resultado, que será `{'a': 1, 'b': 3, 'c': 4}`.

</details>
