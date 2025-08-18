# Desestructuración en Python: Asignación Múltiple y Desempaquetado

La "desestructuración" (más comúnmente conocida en Python como **desempaquetado** o **asignación múltiple**) es una forma muy conveniente y legible de extraer valores de colecciones como listas, tuplas o diccionarios y asignarlos a variables individuales en una sola línea.

---

### 1. Desempaquetado Básico con Tuplas y Listas

La forma más simple de desestructuración es asignar los elementos de una tupla o lista a múltiples variables. El número de variables a la izquierda del `=` debe coincidir exactamente con el número de elementos en la colección.

#### Ejemplo con una tupla:

```python
# Creamos una tupla con coordenadas
coordenadas = (10, 20, 30)

# Desempaquetamos la tupla en tres variables
x, y, z = coordenadas

print(f"La coordenada X es: {x}") # Salida: La coordenada X es: 10
print(f"La coordenada Y es: {y}") # Salida: La coordenada Y es: 20
print(f"La coordenada Z es: {z}") # Salida: La coordenada Z es: 30
```

#### Ejemplo con una lista:

El comportamiento es idéntico con las listas.

```python
# Creamos una lista con datos de un usuario
datos_usuario = ["Ana", 28, "ana@email.com"]

# Desempaquetamos la lista
nombre, edad, email = datos_usuario

print(f"Nombre: {nombre}") # Salida: Nombre: Ana
print(f"Edad: {edad}")     # Salida: Edad: 28
```

**Error común**: Si el número de variables no coincide con el número de elementos, Python lanzará un `ValueError`.

```python
# Esto dará un error: ValueError: too many values to unpack (expected 2)
punto = (10, 20, 30)
x, y = punto
```

---

### 2. Desempaquetado Extendido con el Operador `*`

¿Qué pasa si solo te interesan los primeros y los últimos elementos, y quieres agrupar el resto? Para esto, puedes usar el operador `*` (conocido como "starred expression"). Este operador captura todos los elementos "sobrantes" y los guarda en una nueva lista.

```python
numeros = [1, 2, 3, 4, 5, 6]

# Capturamos el primer y el último elemento, y el resto en una lista intermedia
primero, *intermedios, ultimo = numeros

print(f"Primero: {primero}")         # Salida: Primero: 1
print(f"Intermedios: {intermedios}") # Salida: Intermedios: [2, 3, 4, 5]
print(f"Último: {ultimo}")           # Salida: Último: 6

# También puedes capturar los primeros y el resto
primero, segundo, *resto = numeros
print(f"Resto: {resto}") # Salida: Resto: [3, 4, 5, 6]
```

---

### 3. Ignorando Valores con `_`

A veces, no te interesan todos los valores de la colección que estás desempaquetando. Por convención, se utiliza el guion bajo (`_`) como nombre de variable para aquellos valores que quieres ignorar.

```python
# Solo nos interesa el nombre y el email, no la edad
datos_usuario = ["Carlos", 35, "carlos@web.com"]

nombre, _, email = datos_usuario

print(f"Usuario: {nombre}, Contacto: {email}") # Salida: Usuario: Carlos, Contacto: carlos@web.com
```

Puedes combinar `_` con el operador `*` para ignorar múltiples valores.

```python
# Solo nos interesa el primer y último valor
calificaciones = [10, 8, 9, 7, 10]

primera, *_, ultima = calificaciones

print(f"Primera calificación: {primera}") # Salida: Primera calificación: 10
print(f"Última calificación: {ultima}")   # Salida: Última calificación: 10
```

---

### 4. Desempaquetado en Bucles `for`

La desestructuración es extremadamente útil al iterar sobre listas de listas o listas de tuplas.

```python
# Lista de tuplas, donde cada tupla es (producto, precio)
productos = [("Manzana", 1.5), ("Plátano", 0.75), ("Naranja", 1.0)]

# Desempaquetamos directamente en el bucle for
for producto, precio in productos:
    print(f"El precio de '{producto}' es ${precio}")

# Salida:
# El precio de 'Manzana' es $1.5
# El precio de 'Plátano' es $0.75
# El precio de 'Naranja' es $1.0
```

Esto es mucho más legible que acceder a los elementos por su índice (`item[0]`, `item[1]`).

---

### 5. Desempaquetado de Diccionarios

Aunque no es tan directo como con las secuencias, también puedes desempaquetar diccionarios.

- Iterar sobre `.keys()` (comportamiento por defecto):

  ```python
  mi_diccionario = {"a": 1, "b": 2}
  for clave in mi_diccionario:
      print(clave) # Salida: a, b
  ```

- Iterar sobre `.values()`:

  ```python
  for valor in mi_diccionario.values():
      print(valor) # Salida: 1, 2
  ```

- Iterar sobre `.items()` (el más común para desestructurar):
  El método `.items()` devuelve una vista de tuplas `(clave, valor)`, que es perfecta para desempaquetar en un bucle `for`.

  ```python
  configuracion = {"host": "localhost", "port": 8080, "user": "admin"}

  for clave, valor in configuracion.items():
      print(f"Configuración '{clave}': {valor}")

  # Salida:
  # Configuración 'host': localhost
  # Configuración 'port': 8080
  # Configuración 'user': admin
  ```

---

### 6. Usos Prácticos

#### Intercambio de Variables (Swapping)

La forma clásica de intercambiar dos variables requiere una variable temporal. Con desestructuración, es una sola línea.

```python
a = 10
b = 20

# La forma clásica
# temp = a
# a = b
# b = temp

# La forma con Python
a, b = b, a

print(f"a ahora es {a} y b ahora es {b}") # Salida: a ahora es 20 y b ahora es 10
```

#### Funciones que Devuelven Múltiples Valores

Las funciones en Python pueden devolver una tupla, que luego puede ser desempaquetada por quien la llama.

```python
def dividir_con_resto(dividendo, divisor):
    cociente = dividendo // divisor
    resto = dividendo % divisor
    return cociente, resto # Python crea automáticamente una tupla (cociente, resto)

# Desempaquetamos el resultado directamente
resultado, sobrante = dividir_con_resto(10, 3)

print(f"10 dividido por 3 es {resultado} con un resto de {sobrante}")
# Salida: 10 dividido por 3 es 3 con un resto de 1
```
