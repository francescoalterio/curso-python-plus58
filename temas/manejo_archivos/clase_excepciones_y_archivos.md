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

### 1.4) Catálogo de Excepciones Comunes en Python

Aquí tienes una guía de los errores más comunes que encontrarás en Python, divididos por categorías. Entenderlos te ayudará a depurar tu código mucho más rápido.

#### A) Errores de Sintaxis y Estructura

Estos errores ocurren cuando el código no sigue las reglas gramaticales de Python. El intérprete los detecta antes de empezar a ejecutar el programa y, por lo tanto, **no se pueden capturar con `try...except`**.

- **`SyntaxError`**:

  - **Qué es**: Es el error más básico. Significa que has escrito algo que Python no entiende.
  - **Causa común**: Olvidar dos puntos (`:`), paréntesis, comillas, o usar una palabra clave de forma incorrecta.
  - **Ejemplo**: `print("Hola"` (falta el paréntesis de cierre).
  - **Solución**: Revisa la línea que indica el error con mucho cuidado. El editor de código suele subrayar el problema.

- **`IndentationError`**:
  - **Qué es**: Un subtipo de `SyntaxError` específico de Python. Ocurre cuando la indentación (los espacios al inicio de una línea) no es correcta.
  - **Causa común**: Mezclar espacios y tabuladores, o no indentar el código que va dentro de un `if`, `for`, `def`, etc.
  - **Ejemplo**:
    ```python
    def mi_funcion():
    print("Esto está mal indentado")
    ```
  - **Solución**: Asegúrate de que todas las líneas dentro de un bloque de código tengan el mismo nivel de indentación (el estándar es 4 espacios).

#### B) Errores de Nombres y Atributos

Estos errores suceden en tiempo de ejecución cuando intentas usar una variable, función o atributo que no existe.

- **`NameError`**:

  - **Qué es**: Intentas usar una variable o función que no ha sido definida.
  - **Causa común**: Un error tipográfico en el nombre de una variable, o intentar usar una variable antes de asignarle un valor.
  - **Ejemplo**: `print(mi_variable)` sin haber hecho `mi_variable = 10` antes.
  - **Solución**: Verifica que el nombre esté bien escrito y que la variable haya sido creada antes de usarla.

- **`AttributeError`**:
  - **Qué es**: Intentas acceder a un método o atributo que no existe en un objeto.
  - **Causa común**: Confundir los métodos de un tipo de dato (ej: llamar a `.append()` en un string) o un error tipográfico al escribir el nombre del método.
  - **Ejemplo**:
    ```python
    cadena = "hola"
    cadena.add("!") # Los strings no tienen el método .add(), las listas sí
    ```
  - **Solución**: Consulta la documentación del tipo de dato o usa `dir(objeto)` para ver una lista de sus atributos y métodos válidos.

#### C) Errores de Tipos de Datos

Ocurren cuando una operación recibe un argumento del tipo correcto, pero con un valor inapropiado, o directamente un tipo de dato que no puede manejar.

- **`TypeError`**:

  - **Qué es**: Se lanza cuando una operación o función se aplica a un objeto de un tipo inadecuado.
  - **Causa común**: Intentar sumar un número y un string, llamar a `len()` sobre un número, o pasar un número incorrecto de argumentos a una función.
  - **Ejemplo**: `"Hola" + 5`
  - **Solución**: Asegúrate de que los tipos de datos son los que la operación espera. Realiza conversiones explícitas si es necesario (ej: `str(5)`).

- **`ValueError`**:
  - **Qué es**: Ocurre cuando una función recibe un argumento con un tipo correcto, pero un valor inválido.
  - **Causa común**: Intentar convertir un string que no es un número a entero (`int("hola")`) o buscar un elemento en una lista que no existe con `.index()`.
  - **Ejemplo**: `int("veinte")`
  - **Solución**: Valida los datos antes de pasarlos a la función, o usa un bloque `try...except ValueError` para manejar la conversión.

#### D) Errores de Colecciones e Índices

Estos errores son específicos del manejo de secuencias como listas, tuplas o diccionarios.

- **`IndexError`**:

  - **Qué es**: Intentas acceder a un índice de una secuencia (como una lista) que está fuera de rango.
  - **Causa común**: Olvidar que los índices empiezan en 0, o intentar acceder a un elemento en una lista vacía.
  - **Ejemplo**:
    ```python
    mi_lista = [1, 2, 3]
    print(mi_lista[3]) # El último índice válido es 2
    ```
  - **Solución**: Comprueba la longitud de la lista (`len(mi_lista)`) antes de acceder a un índice.

- **`KeyError`**:
  - **Qué es**: Es el equivalente de `IndexError` para los diccionarios. Ocurre cuando intentas acceder a una clave que no existe en el diccionario.
  - **Causa común**: Un error tipográfico en el nombre de la clave o suponer que una clave siempre estará presente.
  - **Ejemplo**:
    ```python
    mi_diccionario = {"nombre": "Ana"}
    print(mi_diccionario["edad"]) # La clave "edad" no existe
    ```
  - **Solución**: Usa el método `.get("clave", valor_por_defecto)` que devuelve `None` (o un valor por defecto) si la clave no existe, en lugar de lanzar un error. O comprueba la existencia con `if "clave" in mi_diccionario:`.

#### E) Errores de Lógica y Operaciones

- **`ZeroDivisionError`**:

  - **Qué es**: Intentas dividir un número por cero.
  - **Causa común**: Una variable que actúa como divisor toma el valor 0 en algún punto del programa.
  - **Ejemplo**: `10 / 0`
  - **Solución**: Antes de dividir, comprueba si el divisor es distinto de cero.

- **`RecursionError`**:
  - **Qué es**: Ocurre cuando una función se llama a sí misma (recursividad) demasiadas veces, superando el límite de profundidad de recursión de Python.
  - **Causa común**: Una función recursiva que no tiene un "caso base" para detener las llamadas, creando un bucle infinito.
  - **Ejemplo**:
    ```python
    def cuenta_atras(n):
        cuenta_atras(n - 1) # Nunca para
    ```
  - **Solución**: Asegúrate de que tu función recursiva tenga una condición de salida (caso base) que detenga las llamadas.

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

### 3.3. Manejo de errores en archivos

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

## 4) Ejemplo Práctico: Gestionando un Inventario de Productos en un Archivo .txt

Vamos a aplicar todo lo que hemos aprendido en un ejemplo práctico desde cero. Crearemos un pequeño sistema para gestionar un inventario de productos que se guardará en un archivo `inventario.txt`.

Usaremos un formato simple: cada línea representará un producto y tendrá el nombre y la cantidad separados por una coma.
**Formato:** `nombre_del_producto,cantidad_en_stock`

### Paso 1: Crear el archivo y guardar el primer producto

Para empezar, crearemos el archivo `inventario.txt` y añadiremos nuestro primer producto. Usaremos el modo `"w"` (escritura), que crea el archivo si no existe y sobrescribe su contenido si ya existe.

```python
# Definimos el nombre del archivo
nombre_archivo = "inventario.txt"
producto_inicial = "Laptop,10"

print(f"Creando el archivo '{nombre_archivo}' y guardando el primer producto...")
try:
    with open(nombre_archivo, "w", encoding="utf-8") as f:
        f.write(producto_inicial + "\n") # \n para añadir un salto de línea
    print("¡Archivo creado y producto guardado con éxito!")
except Exception as e:
    print(f"Ocurrió un error: {e}")
```

**Resultado:** Se creará un archivo llamado `inventario.txt` con el siguiente contenido:

```
Laptop,10
```

### Paso 2: Leer y mostrar todos los productos

Ahora, vamos a leer el archivo para ver qué productos tenemos. Usaremos el modo `"r"` (lectura).

```python
print("\nLeyendo el inventario...")
try:
    with open(nombre_archivo, "r", encoding="utf-8") as f:
        print("--- Inventario Actual ---")
        for linea in f:
            # Quitamos espacios en blanco y saltos de línea
            linea_limpia = linea.strip()
            if linea_limpia:
                # Separamos el nombre y la cantidad por la coma
                nombre, cantidad = linea_limpia.split(',')
                print(f"Producto: {nombre}, Stock: {cantidad}")
        print("-------------------------")
except FileNotFoundError:
    print(f"Error: El archivo '{nombre_archivo}' no existe.")
except Exception as e:
    print(f"Ocurrió un error: {e}")
```

### Paso 3: Agregar nuevos productos

Para añadir más productos sin borrar los existentes, usamos el modo `"a"` (append).

```python
nuevos_productos = ["Mouse,50", "Teclado,30"]

print("\nAgregando nuevos productos...")
try:
    with open(nombre_archivo, "a", encoding="utf-8") as f:
        for producto in nuevos_productos:
            f.write(producto + "\n")
    print("¡Nuevos productos agregados!")
except Exception as e:
    print(f"Ocurrió un error: {e}")
```

**Resultado:** El archivo `inventario.txt` ahora contendrá:

```
Laptop,10
Mouse,50
Teclado,30
```

_Puedes volver a ejecutar el código del Paso 2 para comprobarlo._

### Paso 4: Actualizar la cantidad de un producto

Actualizar una línea específica en un archivo de texto es más complejo, ya que no podemos editar una línea directamente. El proceso es:

1. Leer todas las líneas del archivo y guardarlas en una lista en memoria.
2. Modificar la línea deseada en esa lista.
3. Reescribir el archivo completo desde cero con la lista actualizada, usando el modo `"w"`.

```python
producto_a_actualizar = "Laptop"
nueva_cantidad = "8"

print(f"\nActualizando el stock de '{producto_a_actualizar}'...")
lineas_actualizadas = []
try:
    # 1. Leemos todo el archivo
    with open(nombre_archivo, "r", encoding="utf-8") as f:
        for linea in f:
            nombre, cantidad = linea.strip().split(',')
            # 2. Si es el producto que buscamos, cambiamos la cantidad
            if nombre == producto_a_actualizar:
                lineas_actualizadas.append(f"{nombre},{nueva_cantidad}\n")
                print(f"-> Stock de '{nombre}' actualizado a {nueva_cantidad}.")
            else:
                lineas_actualizadas.append(linea)

    # 3. Reescribimos el archivo con las líneas actualizadas
    with open(nombre_archivo, "w", encoding="utf-8") as f:
        f.writelines(lineas_actualizadas)

    print("¡Actualización completada!")

except FileNotFoundError:
    print(f"Error: El archivo '{nombre_archivo}' no existe.")
except Exception as e:
    print(f"Ocurrió un error: {e}")
```

_Vuelve a ejecutar el código del Paso 2. Verás que el stock de "Laptop" ahora es 8._

### Paso 5: Eliminar un producto

Eliminar un producto sigue una lógica muy parecida a la de actualizar:

1. Leer todas las líneas y guardarlas en una nueva lista.
2. Omitir (no añadir a la lista) la línea que corresponde al producto que queremos eliminar.
3. Reescribir el archivo con la nueva lista que ya no contiene el producto.

```python
producto_a_eliminar = "Mouse"

print(f"\nEliminando el producto '{producto_a_eliminar}'...")
lineas_filtradas = []
try:
    # 1. Leemos y filtramos
    with open(nombre_archivo, "r", encoding="utf-8") as f:
        for linea in f:
            nombre, _ = linea.strip().split(',')
            # 2. Añadimos a la nueva lista solo si NO es el producto a eliminar
            if nombre != producto_a_eliminar:
                lineas_filtradas.append(linea)
            else:
                print(f"-> Producto '{nombre}' encontrado y omitido.")

    # 3. Reescribimos el archivo
    with open(nombre_archivo, "w", encoding="utf-8") as f:
        f.writelines(lineas_filtradas)

    print("¡Eliminación completada!")

except FileNotFoundError:
    print(f"Error: El archivo '{nombre_archivo}' no existe.")
except Exception as e:
    print(f"Ocurrió un error: {e}")
```

_Si ejecutas el código del Paso 2 una última vez, verás que "Mouse" ya no está en el inventario._

---

## 3.1) Errores Comunes y Cómo Manejarlos

Al trabajar con excepciones, es crucial capturar los errores específicos para poder dar una respuesta adecuada. Aquí tienes una lista de las excepciones más comunes que encontrarás, con una explicación y un ejemplo de cómo manejarlas.

### `FileNotFoundError`

- **¿Qué es?** Ocurre cuando intentas abrir un archivo en modo lectura (`"r"`) que no existe en la ruta especificada.
- **¿Cómo manejarlo?** Informa al usuario que el archivo no se encontró y, si es apropiado, ofrécele crearlo.

```python
try:
    with open("archivo_inexistente.txt", "r") as f:
        contenido = f.read()
except FileNotFoundError:
    print("Error: El archivo no se ha encontrado. Verifica la ruta o el nombre.")
```

### `PermissionError`

- **¿Qué es?** Se lanza cuando tu programa no tiene los permisos del sistema operativo para realizar una acción, como leer un archivo protegido o escribir en un directorio de solo lectura.
- **¿Cómo manejarlo?** Notifica al usuario que no tiene los permisos necesarios.

```python
try:
    # Suponiendo que 'C:/Windows/System32/config/SAM' es un archivo protegido
    with open("C:/Windows/System32/config/SAM", "r") as f:
        contenido = f.read()
except PermissionError:
    print("Error: No tienes permisos para acceder a este archivo.")
```

### `IsADirectoryError` / `NotADirectoryError`

- **¿Qué son?**
  - `IsADirectoryError`: Ocurre cuando intentas tratar un directorio como si fuera un archivo (ej: `open("mi_carpeta/", "r")`).
  - `NotADirectoryError`: Ocurre cuando una parte de la ruta que debería ser un directorio no lo es (ej: `open("mi_archivo.txt/otro.txt", "w")`).
- **¿Cómo manejarlos?** Verifica que la ruta apunte a un archivo y que la estructura de directorios sea correcta.

```python
try:
    with open("mi_carpeta/", "w") as f: # Suponiendo que 'mi_carpeta' es un directorio
        f.write("hola")
except IsADirectoryError:
    print("Error: La ruta especificada es un directorio, no un archivo.")
```

### `io.UnsupportedOperation`

- **¿Qué es?** Se produce cuando intentas realizar una operación que no está permitida por el modo en que abriste el archivo. Por ejemplo, intentar escribir (`.write()`) en un archivo abierto en modo solo lectura (`"r"`).
- **¿Cómo manejarlo?** Asegúrate de que el modo de apertura (`"r"`, `"w"`, `"a"`, `"r+"`, etc.) sea el correcto para la operación que quieres realizar.

```python
try:
    with open("mi_archivo.txt", "r") as f:
        f.write("Intentando escribir algo...")
except io.UnsupportedOperation:
    print("Error: No se puede escribir en un archivo abierto en modo solo lectura.")
# Nota: Necesitarás 'import io' para capturar esta excepción explícitamente.
```

### `UnicodeDecodeError` / `UnicodeEncodeError`

- **¿Qué son?**
  - `UnicodeDecodeError`: Ocurre al leer un archivo si el `encoding` especificado no puede decodificar un byte del archivo. Es común si intentas leer un archivo UTF-8 como si fuera 'ascii'.
  - `UnicodeEncodeError`: Ocurre al escribir si intentas guardar un carácter (como 'á' o '€') que no es compatible con el `encoding` especificado (ej: 'ascii').
- **¿Cómo manejarlos?** La solución casi siempre es usar el encoding correcto, que generalmente es `encoding="utf-8"`.

```python
try:
    # Suponiendo que 'datos.txt' contiene caracteres como 'ñ' o '€'
    with open("datos.txt", "r", encoding="ascii") as f:
        contenido = f.read()
except UnicodeDecodeError:
    print("Error de decodificación: El archivo no parece ser ASCII. Intenta con UTF-8.")
```

### `ValueError` y `TypeError`

- **¿Qué son?** Aunque no son errores de archivo directamente, son muy comunes al procesar los datos leídos.
  - `ValueError`: Ocurre al intentar una conversión de tipo con un valor inapropiado (ej: `int("hola")`).
  - `TypeError`: Ocurre al intentar una operación en un tipo de dato incorrecto (ej: `len(123)`).
- **¿Cómo manejarlos?** Valida los datos después de leerlos y antes de procesarlos.

```python
linea = "producto,cantidad"
try:
    nombre, stock_str = linea.split(',')
    stock = int(stock_str) # Esta línea puede lanzar ValueError
    print(f"Stock de {nombre}: {stock}")
except ValueError:
    print(f"Error: No se pudo convertir '{stock_str}' a un número entero.")
```

---

## 5) Buenas prácticas

- **Usa `with` siempre**: Garantiza que los archivos se cierren correctamente, liberando recursos del sistema.
- **Sé específico con las excepciones**: Captura los errores que esperas (`FileNotFoundError`, `ValueError`) en lugar de un `except Exception` genérico.
- **Especifica el `encoding`**: Usa `encoding="utf-8"` para asegurar que tu código funcione correctamente con textos que contienen acentos, emojis y otros caracteres especiales.
- **Valida las entradas**: Antes de operar con un archivo, comprueba si la ruta es válida o si tienes los permisos necesarios, si es posible.

---

## 6) Ejercicios propuestos

1.  **Contador de palabras**: Escribe una función que reciba una ruta de archivo y devuelva el número de palabras que contiene. Maneja el `FileNotFoundError`.
2.  **Log de eventos**: Crea una función `log(mensaje)` que abra un archivo `eventos.log` en modo `append` (`a`) y añada una línea con la fecha y hora actual seguida del `mensaje`.
3.  **Copia de archivos mejorada**: Escribe un script que copie un archivo a otro. Pide al usuario la ruta de origen y de destino. Usa `try/except` para manejar errores como que el archivo de origen no exista o no tengas permisos de escritura en el destino.
4.  **Validador de contraseñas**: Crea una función que valide una contraseña. Debe lanzar una excepción `ValueError` con mensajes específicos si la contraseña tiene menos de 8 caracteres o si no contiene al menos un número. Usa `try/except` para probarla.
