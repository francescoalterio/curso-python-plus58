# Excepciones y Manejo de Archivos en Python

En esta clase aprenderás a manejar errores con `try`, `except`, `finally` y a trabajar con archivos de manera segura usando `with`.

---

## 1) Excepciones: `try`, `except`, `finally`

Las excepciones son errores que ocurren durante la ejecución. Con `try/except` puedes capturarlas y responder sin que el programa se detenga.

### 1.1. Estructura básica

```python
try:
    # Código que podría fallar
    x = int("123")
except ValueError:
    # Qué hacer si ocurre ese error
    print("No se pudo convertir a entero")
finally:
    # Este bloque SIEMPRE se ejecuta
    print("Fin del bloque try/except/finally")
```

### 1.2. Múltiples except y excepción genérica

```python
try:
    resultado = 10 / 0
except ZeroDivisionError:
    print("No puedes dividir entre cero")
except (TypeError, ValueError):
    print("Error de tipo o de valor")
except Exception as e:
    # Evita usar Exception salvo para logging/último recurso
    print("Ocurrió un error inesperado:", e)
```

### 1.3. `else` con try/except

```python
try:
    datos = [1, 2, 3]
    media = sum(datos) / len(datos)
except ZeroDivisionError:
    print("La lista está vacía")
else:
    # Se ejecuta solo si no hubo excepción en try
    print("La media es:", media)
finally:
    print("Listo")
```

---

## 2) Lanzando excepciones (`raise`)

Además de _manejar_ excepciones que Python genera, también puedes _lanzar_ tus propias excepciones usando la palabra clave `raise`. Esto es muy útil para señalar errores en tus propias funciones cuando los argumentos no son válidos.

```python
def dividir(a, b):
    if b == 0:
        raise ValueError("El divisor no puede ser cero. No se puede completar la operación.")
    return a / b

try:
    resultado = dividir(10, 0)
except ValueError as e:
    print(f"Error: {e}")

# Salida: Error: El divisor no puede ser cero. No se puede completar la operación.
```

---

## 3) Trabajando con archivos

Python ofrece funciones integradas para leer y escribir archivos. Siempre que abras un archivo, asegúrate de cerrarlo. La forma recomendada y más segura de hacerlo es con la declaración `with`, que cierra el archivo automáticamente, incluso si ocurren errores.

### 3.1. Abrir y leer archivos

```python
# Lectura completa del archivo
with open("datos.txt", mode="r", encoding="utf-8") as f:
    contenido = f.read() # Lee todo el contenido en una sola cadena
    print(contenido)

# Leer línea por línea (eficiente para archivos grandes)
total = 0
with open("numeros.txt", mode="r", encoding="utf-8") as f:
    for linea in f:
        linea_limpia = linea.strip() # Quita espacios y saltos de línea
        if linea_limpia: # Nos aseguramos de que la línea no esté vacía
            total += int(linea_limpia)
print(f"La suma total es: {total}")

# Leer todas las líneas en una lista
with open("datos.txt", mode="r", encoding="utf-8") as f:
    lineas = f.readlines() # Devuelve una lista de strings, cada una es una línea
    print(lineas)
```

### 3.2. Escribir archivos

```python
# Sobrescribir el archivo si existe, o crearlo si no
with open("salida.txt", mode="w", encoding="utf-8") as f:
    f.write("Hola\n")
    f.write("Mundo\n")

# Agregar contenido al final del archivo (append)
with open("salida.txt", mode="a", encoding="utf-8") as f:
    f.write("Esta es una nueva línea añadida.\n")
```

**Modos de apertura comunes:**

- `"r"`: **Leer** (Read). El archivo debe existir. Es el modo por defecto.
- `"w"`: **Escribir** (Write). Crea el archivo si no existe. Si existe, **borra todo su contenido** y escribe desde cero.
- `"a"`: **Añadir** (Append). Crea el archivo si no existe. Si existe, añade el nuevo contenido al final.
- `"x"`: **Creación exclusiva**. Crea el archivo, pero falla con un error `FileExistsError` si ya existe.
- Añadir `"+"` a un modo (ej: `"r+"`, `"w+"`) permite leer y escribir a la vez.
- Añadir `"b"` (ej: `"rb"`, `"wb"`) abre el archivo en **modo binario**, para imágenes, ejecutables, etc.

### 3.3. Controlando el cursor del archivo: `seek` y `tell`

Puedes controlar en qué parte del archivo lees o escribes con `seek()` y `tell()`.

- `f.tell()`: Te dice la posición actual del cursor (en bytes).
- `f.seek(offset)`: Mueve el cursor a la posición `offset` (en bytes).

```python
with open("salida.txt", "r+", encoding="utf-8") as f:
    contenido = f.read()
    print(f"Posición después de leer: {f.tell()}") # Al final del archivo
    f.seek(0) # Volvemos al inicio
    print(f"Posición después de seek(0): {f.tell()}") # En el byte 0
    f.write("INICIO: ") # Sobrescribimos el inicio del archivo
```

### 3.4. Manejo de errores en archivos

```python
ruta = "archivo_que_no_existe.txt"
try:
    with open(ruta, "r", encoding="utf-8") as f:
        print(f.read())
except FileNotFoundError:
    print(f"Error: El archivo en la ruta '{ruta}' no fue encontrado.")
except PermissionError:
    print("Error: No tienes los permisos necesarios para leer este archivo.")
except Exception as e:
    print(f"Ha ocurrido un error inesperado: {e}")
```

---

## 4) Buenas prácticas

- **Usa `with` siempre**: Garantiza que los archivos se cierren correctamente, liberando recursos del sistema.
- **Sé específico con las excepciones**: Captura los errores que esperas (`FileNotFoundError`, `ValueError`) en lugar de un `except Exception` genérico.
- **Especifica el `encoding`**: Usa `encoding="utf-8"` para asegurar que tu código funcione correctamente con textos que contienen acentos, emojis y otros caracteres especiales.
- **Valida las entradas**: Antes de operar con un archivo, comprueba si la ruta es válida o si tienes los permisos necesarios, si es posible.

---

## 5) Ejercicios propuestos

1.  **Contador de palabras**: Escribe una función que reciba una ruta de archivo y devuelva el número de palabras que contiene. Maneja el `FileNotFoundError`.
2.  **Log de eventos**: Crea una función `log(mensaje)` que abra un archivo `eventos.log` en modo `append` (`a`) y añada una línea con la fecha y hora actual seguida del `mensaje`.
3.  **Copia de archivos mejorada**: Escribe un script que copie un archivo a otro. Pide al usuario la ruta de origen y de destino. Usa `try/except` para manejar errores como que el archivo de origen no exista o no tengas permisos de escritura en el destino.
4.  **Validador de contraseñas**: Crea una función que valide una contraseña. Debe lanzar una excepción `ValueError` con mensajes específicos si la contraseña tiene menos de 8 caracteres o si no contiene al menos un número. Usa `try/except` para probarla.
