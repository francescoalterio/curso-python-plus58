# Introducción a los Diccionarios en Python

¡Hola! Hoy vamos a explorar una de las estructuras de datos más potentes y flexibles de Python: los **diccionarios**. Si las listas nos permitían guardar una colección de elementos en un orden específico, los diccionarios nos permiten guardar datos de una forma más descriptiva, usando pares de "clave" y "valor".

---

## 1. ¿Qué es un Diccionario?

Un diccionario es una colección de elementos que, en lugar de estar ordenados por un índice numérico (como las listas), están organizados por una **clave** única. Cada clave está asociada a un **valor**.

Piensa en un diccionario real: buscas una palabra (la clave) y encuentras su definición (el valor). En Python, es exactamente igual.

-   **Clave (`key`)**: Es un identificador único (no puede haber claves repetidas). Suele ser una cadena de texto o un número.
-   **Valor (`value`)**: Es la información asociada a esa clave. Puede ser cualquier tipo de dato: un número, una cadena, una lista, ¡o incluso otro diccionario!

Los diccionarios se definen con llaves `{}`.

**Sintaxis:**
`mi_diccionario = {"clave1": valor1, "clave2": valor2}`

---

## 2. Creación y Acceso a Diccionarios

### Crear un diccionario

Puedes crear un diccionario vacío o con datos iniciales.

```python
# Diccionario vacío
diccionario_vacio = {}

# Diccionario con información de un usuario
usuario = {
    "nombre": "Ana",
    "edad": 25,
    "ciudad": "Madrid",
    "sabe_python": True
}

print(usuario)
```

### Acceder a los valores

Para acceder a un valor, usamos su clave entre corchetes `[]`.

```python
usuario = {
    "nombre": "Ana",
    "edad": 25,
    "ciudad": "Madrid"
}

# Accedemos al nombre
print(usuario["nombre"])  # Salida: Ana

# Accedemos a la edad
print(usuario["edad"])    # Salida: 25
```

**¡Cuidado!** Si intentas acceder a una clave que no existe, Python te dará un error (`KeyError`).

---

## 3. Modificar un Diccionario

Los diccionarios son **mutables**, lo que significa que podemos cambiarlos después de crearlos.

### Añadir o actualizar un elemento

Si la clave no existe, se añade un nuevo par clave-valor. Si ya existe, se actualiza su valor.

```python
usuario = {
    "nombre": "Ana",
    "edad": 25
}

# Añadir una nueva clave-valor
usuario["profesion"] = "Programadora"
print(usuario)  # {'nombre': 'Ana', 'edad': 25, 'profesion': 'Programadora'}

# Actualizar un valor existente
usuario["edad"] = 26
print(usuario)  # {'nombre': 'Ana', 'edad': 26, 'profesion': 'Programadora'}
```

### Eliminar un elemento

Podemos usar la palabra clave `del` o el método `.pop()` para eliminar un elemento por su clave.

```python
usuario = {
    "nombre": "Ana",
    "edad": 26,
    "profesion": "Programadora"
}

# Eliminar con del
del usuario["profesion"]
print(usuario)  # {'nombre': 'Ana', 'edad': 26}

# Eliminar con pop (devuelve el valor eliminado)
edad_eliminada = usuario.pop("edad")
print(f"La edad eliminada fue: {edad_eliminada}") # La edad eliminada fue: 26
print(usuario) # {'nombre': 'Ana'}
```

---

## 4. Iterar sobre un Diccionario

Podemos usar bucles `for` para recorrer los elementos de un diccionario.

### Recorrer las claves (comportamiento por defecto)

```python
usuario = {"nombre": "Ana", "edad": 25, "ciudad": "Madrid"}

print("Claves del diccionario:")
for clave in usuario:
    print(clave)
```
**Salida:**
```
Claves del diccionario:
nombre
edad
ciudad
```

### Recorrer los valores

Para obtener solo los valores, usamos el método `.values()`.

```python
print("\nValores del diccionario:")
for valor in usuario.values():
    print(valor)
```
**Salida:**
```
Valores del diccionario:
Ana
25
Madrid
```

### Recorrer claves y valores a la vez

La forma más común y útil es usar el método `.items()`, que nos da la clave y el valor en cada iteración.

```python
print("\nClave y valor:")
for clave, valor in usuario.items():
    print(f"{clave}: {valor}")
```
**Salida:**
```
Clave y valor:
nombre: Ana
edad: 25
ciudad: Madrid
```

---

## 5. Métodos útiles

-   `diccionario.get(clave, valor_por_defecto)`: Es una forma segura de acceder a una clave. Si la clave no existe, no da error, sino que devuelve `None` o el valor por defecto que le indiques.
-   `diccionario.keys()`: Devuelve una vista de todas las claves.
-   `diccionario.values()`: Devuelve una vista de todos los valores.
-   `diccionario.items()`: Devuelve una vista de todos los pares (clave, valor).

### Ejemplo con `.get()`

```python
usuario = {"nombre": "Ana", "edad": 25}

# La clave "ciudad" no existe
print(usuario.get("ciudad"))  # Salida: None
print(usuario.get("ciudad", "No especificada")) # Salida: No especificada

# La clave "nombre" sí existe
print(usuario.get("nombre")) # Salida: Ana
```

---

## ¡A practicar!

1.  **Mi Biografía:** Crea un diccionario que almacene tu nombre, edad y comida favorita. Luego, imprime cada uno de estos valores.
2.  **Agenda de Contactos:** Crea un diccionario donde las claves sean nombres de amigos y los valores sean sus números de teléfono. Añade un nuevo contacto y luego elimina uno.
3.  **Recorriendo un Producto:** Crea un diccionario para un producto (ej: `{"producto": "camiseta", "precio": 15, "stock": 100}`). Usa un bucle `for` con `.items()` para imprimir sus características en el formato "clave: valor".

¡Los diccionarios son fundamentales en Python, así que practica mucho con ellos!
