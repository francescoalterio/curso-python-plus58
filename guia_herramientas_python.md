# Guía de Herramientas de Python: Tu Caja de Herramientas para Resolver Problemas

El objetivo de esta guía no es solo listar lo que puedes hacer en Python, sino ayudarte a pensar como un programador. Cuando te enfrentes a un ejercicio, vuelve aquí y pregúntate: **"¿Qué herramienta de mi caja me sirve para resolver este paso?"**

---

## 1. Preparando el Entorno (Instalación)

Antes de empezar a programar, necesitas dos cosas fundamentales: el lenguaje (Python) y un editor de código (tu taller de trabajo).

### 1.1 Instalar Python (El Lenguaje)

Es el motor que ejecutará todo tu código.

Ve a la página oficial: python.org.
Descarga la última versión estable.
Durante la instalación (en Windows): ¡Muy importante! Marca la casilla que dice "Add Python to PATH". Esto permite que puedas ejecutar Python desde cualquier terminal.

### 1.2 Instalar Visual Studio Code (El Taller)

Es el programa donde escribirás, organizarás y probarás tu código. Es altamente recomendado por su versatilidad.

Ve a la página oficial: code.visualstudio.com.
Descarga e instala la versión para tu sistema operativo (Windows, macOS o Linux).
Instala la extensión de Python:
Abre VS Code.
Ve al icono de Extensiones en la barra lateral (parece un conjunto de cuadrados).
Busca "Python" (la de Microsoft) y haz clic en Instalar. Esto te dará superpoderes como autocompletado, depuración y más.

---

## 2. Herramientas para Operar (Las Acciones)

Ahora que sabes guardar información en tus "cajas" (variables), es hora de usar las herramientas que te permiten operar con ella. Estas son las acciones que te permiten transformar, comparar y combinar tus datos para obtener resultados. Son el motor de tu programa.

- **Operadores Aritméticos:** Para hacer matemáticas.

  - `+` (suma), `-` (resta), `*` (multiplicación), `/` (división).
  - `//` (división entera, sin decimales), `%` (módulo, el resto de la división), `**` (potencia).

- **Operadores de Comparación:** Permiten comparar dos valores para ver su relación. El resultado siempre es un booleano (`True` o `False`), lo cual es fundamental para tomar decisiones en el código.

  - `==` (Igual a): ¿Son los dos valores idénticos?
  - `!=` (Distinto de): ¿Son los dos valores diferentes?
  - `<` (Menor que): ¿Es el valor de la izquierda más pequeño que el de la derecha?
  - `>` (Mayor que): ¿Es el valor de la izquierda más grande que el de la derecha?
  - `<=` (Menor o igual que): ¿Es el de la izquierda más pequeño o igual que el de la derecha?
  - `>=` (Mayor o igual que): ¿Es el de la izquierda más grande o igual que el de la derecha?

  ```python
  saldo = 100
  edad = 20
  print(saldo > 50)      # True
  print(edad == 18)      # False
  print(edad != 20)      # False
  ```

- **Operadores Lógicos:** Se usan para combinar varias condiciones (`True`/`False`) y crear reglas más complejas. Son el cerebro de los condicionales.

  - `and`: Devuelve `True` solo si **ambas** condiciones son verdaderas.
  - `or`: Devuelve `True` si **al menos una** de las condiciones es verdadera.
  - `not`: Invierte el valor booleano. Lo que era `True` se convierte en `False` y viceversa.

  ```python
  edad = 25
  tiene_entrada = True

  # Para entrar al concierto, debe ser mayor de 18 Y tener una entrada.
  if edad >= 18 and tiene_entrada:
          print("Puedes pasar.")

  # Para descuento, debe ser estudiante O jubilado.
  es_estudiante = True
  es_jubilado = False
  if es_estudiante or es_jubilado:
          print("Tienes descuento.")

  # Si NO está lloviendo, salimos a pasear.
  esta_lloviendo = False
  if not esta_lloviendo:
          print("Vamos a dar un paseo.")
  ```

---

## 3. Herramientas de Control (Las Rutas y Repeticiones)

Un programa no siempre se ejecuta en línea recta. A veces necesita tomar decisiones, repetir acciones o cambiar de rumbo. Estas herramientas controlan el **flujo de ejecución** de tu código, como si fueran las señales de tráfico y los desvíos en una carretera.

- **Condicionales (`if`, `elif`, `else`):** Son las bifurcaciones en el camino. Permiten que tu programa ejecute un bloque de código solo **si** se cumple una condición (`True`). Son la base para que tu programa pueda reaccionar de forma diferente a distintas situaciones.

  - `if`: La condición principal. "¿Se cumple esto?".
  - `elif`: Una condición alternativa. "Si lo anterior no se cumplió, ¿se cumple esto otro?".
  - `else`: El camino por defecto. "Si nada de lo anterior se cumplió, haz esto".

  ```python
  edad = 18
  if edad >= 18:
      print("Eres mayor de edad.")
  else:
      print("Eres menor de edad.")
  ```

```python
nota = 7.5
if nota >= 9:
        print("Sobresaliente")
elif nota >= 7:
        print("Notable")
elif nota >= 5:
        print("Aprobado")
else:
        print("Suspenso")
# Salida: Notable
```

- **Bucle `for`:** La herramienta principal para **iterar** (recorrer uno a uno) sobre los elementos de una secuencia (como una lista, un string o un `range`). Es tu mejor aliado cuando quieres realizar una acción para cada elemento de una colección. Su estructura es: `for elemento in coleccion:`.

  - **Recorrer una lista o tupla:** Ejecuta el bloque de código para cada ítem de la colección.

    ```python
    frutas = ["manzana", "plátano", "cereza"]
    for fruta in frutas:
            print(f"Me gusta la {fruta}")
    ```

  - **Repetir un número de veces con `range()`:** `range(n)` genera una secuencia de números de 0 a `n-1`, permitiéndote repetir un bloque de código un número exacto de veces.

    ```python
    for i in range(3): # Genera los números 0, 1, 2
            print(f"Esta es la repetición número {i + 1}")
    ```

  - **Recorrer un string:** Trata el string como una secuencia de caracteres.
    ```python
    for letra in "Python":
            print(letra.upper())
    ```
  - **Bucle `while`:** La herramienta para repetir un bloque de código **mientras** una condición se mantenga verdadera (`True`). A diferencia del `for`, que recorre una colección con un número de elementos definido, el `while` es perfecto para situaciones donde no sabes de antemano cuántas repeticiones necesitas. Es como un vigilante que pregunta "¿puedo seguir?" antes de cada vuelta.

    **¡Cuidado!** Si la condición nunca se vuelve `False`, crearás un **bucle infinito** que bloqueará tu programa.

    ```python
    # Ejemplo: Validar la entrada del usuario hasta que sea correcta.
    edad = 0
    while edad <= 0:
        try:
            edad_str = input("Introduce tu edad (debe ser un número positivo): ")
            edad = int(edad_str)
            if edad <= 0:
                print("Error: La edad debe ser un número mayor que cero.")
        except ValueError:
            print("Error: Eso no es un número válido.")

    print(f"Edad registrada: {edad} años.")
    ```

- **`break` y `continue` (Controles de emergencia para bucles):** Te dan un control más fino sobre el comportamiento de los bucles `for` y `while`.

  - **`break`:** Rompe el bucle y sale de él inmediatamente, sin importar si la condición del bucle se sigue cumpliendo. Es la "salida de emergencia".

    ```python
    # Buscar un número en una lista y parar en cuanto se encuentra.
    numeros = [1, 5, 12, 99, 8, 45]
    for numero in numeros:
        print(f"Buscando... ¿es {numero}?")
        if numero == 99:
            print("¡Lo encontré!")
            break # Salimos del bucle
    # El código continúa aquí después del break
    ```

  - **`continue`:** Salta el resto del código de la iteración actual y pasa directamente a la siguiente vuelta del bucle. Es como decir "a este no le hagas caso, siguiente".

    ```python
    # Imprimir solo los números impares de una lista.
    for i in range(1, 11): # Números del 1 al 10
        if i % 2 == 0: # Si el número es par...
            continue   # ...saltamos a la siguiente iteración.
        print(i) # Este print solo se ejecuta para los impares.
    # Salida: 1, 3, 5, 7, 9
    ```

---

## 4. Herramientas para Almacenar Datos (Las Cajas)

Para guardar conjuntos de datos de forma organizada. Cada tipo de "caja" tiene sus propias reglas y superpoderes.

- **Listas `[]`:** Tu contenedor de datos más versátil y común. Son colecciones **ordenadas** (cada elemento tiene una posición o índice fijo) y **mutables** (puedes añadir, eliminar o cambiar sus elementos después de crearla).

  - **Características clave:**

    - **Ordenadas:** El orden en que añades los elementos se mantiene. Puedes acceder a ellos por su posición (índice), que empieza en `0`.
    - **Mutables:** Son flexibles. Puedes hacerlas crecer, encogerlas o modificar su contenido en cualquier momento.
    - **Permiten duplicados:** Una lista puede contener el mismo valor varias veces.

  - **Cuándo usarlas:** Son tu primera opción para guardar una secuencia de elementos, especialmente si necesitas modificarla. Ejemplos: una lista de tareas pendientes, las notas de un estudiante, los nombres de los participantes en un sorteo.

  - **Operaciones y Métodos Comunes:**
    - **Acceder:** `mi_lista[0]` (primer elemento), `mi_lista[-1]` (último elemento).
    - **Añadir:** `.append(elemento)` (al final), `.insert(indice, elemento)` (en una posición específica).
    - **Eliminar:** `.remove(valor)` (la primera aparición de un valor), `.pop(indice)` (por posición, y te devuelve el elemento).
    - **Modificar:** `mi_lista[indice] = nuevo_valor`.
    - **Tamaño:** `len(mi_lista)`.
    - **Ordenar:** `.sort()` (ordena la lista original).

  ```python
  # Creación de una lista de tareas
  tareas = ["Lavar la ropa", "Comprar pan"]

  # Añadir elementos
  tareas.append("Estudiar Python") # Añade al final
  tareas.insert(1, "Pasear al perro") # Añade en la posición 1

  # Acceder y modificar
  print(f"La primera tarea es: {tareas[0]}") # Lavar la ropa
  tareas[0] = "Lavar los platos" # Cambiamos el valor

  # Eliminar un elemento
  tareas.pop(2) # Elimina "Comprar pan"

  print(f"Lista de tareas actualizada: {tareas}")
  # Salida: ['Lavar los platos', 'Pasear al perro', 'Estudiar Python']
  ```

- **Tuplas `()`:** La "hermana gemela de solo lectura" de la lista. Son colecciones **ordenadas** e **inmutables**, lo que significa que una vez que las creas, no puedes cambiar su contenido. Son como una foto de tus datos en un momento concreto.

  - **Características clave:**

    - **Ordenadas:** Al igual que las listas, mantienen el orden de los elementos.
    - **Inmutables:** Su principal rasgo. No puedes añadir, eliminar ni modificar elementos. Esto las hace más seguras y eficientes para datos que no deben alterarse.
    - **Eficientes:** Ocupan menos memoria y son más rápidas de procesar que las listas.

  - **Cuándo usarlas:** Cuando necesites guardar una colección de datos que sabes que no va a cambiar. Son perfectas para constantes.

    - **Ejemplos:** Coordenadas `(x, y)`, colores RGB `(255, 100, 50)`, los días de la semana.
    - **Como claves de diccionario:** A diferencia de las listas, las tuplas pueden usarse como claves en un diccionario gracias a su inmutabilidad.

  - **Superpoder: El Desempaquetado**
    - Su característica más potente es la capacidad de asignar sus elementos a variables de forma directa y elegante.

  ```python
  # Creación y desempaquetado de una tupla
  punto_3d = (10, 20, 5)
  x, y, z = punto_3d

  print(f"Coordenada X: {x}") # Salida: 10
  print(f"Coordenada Y: {y}") # Salida: 20

  # Intentar modificar una tupla dará un error
  # punto_3d[0] = 15  # TypeError: 'tuple' object does not support item assignment
  ```

- **Diccionarios `{}`:** El "Índice" de tus Datos. Son tu herramienta para guardar información de forma asociativa, como un diccionario de verdad o una agenda de contactos. En lugar de acceder a los datos por su posición (índice numérico), los buscas por una **clave** única que tú defines.

  - **Características clave:**

    - **Asociativos:** Cada elemento es un par `clave: valor`. La clave es la etiqueta y el valor es el dato.
    - **Mutables:** Puedes añadir, modificar y eliminar pares `clave: valor` después de su creación.
    - **Ordenados (desde Python 3.7):** Mantienen el orden en que se insertaron los elementos.
    - **Claves únicas:** No puede haber dos claves iguales. Si añades una clave que ya existe, su valor se sobrescribirá.

  - **Cuándo usarlos:** Cuando necesites describir un objeto o mapear un identificador a un dato. Son perfectos para representar entidades del mundo real.

    - **Ejemplos:** Un perfil de usuario (`{'nombre': 'Ana', 'id': 123}`), la configuración de una aplicación (`{'tema': 'oscuro', 'notificaciones': True}`), un inventario de productos (`{'manzanas': 50, 'platanos': 30}`).

  - **Operaciones y Métodos Comunes:**
    - **Acceder y Modificar:** `mi_diccionario['clave']` y `mi_diccionario['clave'] = nuevo_valor`.
    - **Añadir:** `mi_diccionario['nueva_clave'] = valor`.
    - **Eliminar:** `del mi_diccionario['clave']` o `.pop('clave')`.
    - **Acceso Seguro:** `.get('clave', 'valor_por_defecto')`. Evita errores si la clave no existe.
    - **Iterar:** `.keys()` (para las claves), `.values()` (para los valores), `.items()` (para pares clave-valor).

  ```python
  # Creación de un diccionario para un producto
  producto = {
      "nombre": "Laptop Pro",
      "precio": 1200,
      "stock": 15
  }

  # Acceder a un valor
  print(f"Precio: {producto['precio']}€") # Salida: Precio: 1200€

  # Añadir un nuevo dato
  producto["marca"] = "TechCorp"

  # Modificar un dato existente
  producto["stock"] = 10

  # Acceso seguro a una clave que no existe
  print(f"Descuento: {producto.get('descuento', 'No disponible')}")

  # Iterar para mostrar todos los detalles
  print("\nDetalles del producto:")
  for clave, valor in producto.items():
      print(f"- {clave.capitalize()}: {valor}")
  ```

---

## 5. Herramientas para Texto, Organización y Errores

- **Métodos de Strings:** Métodos especiales para manipular texto.

  - `.upper()`, `.lower()`: Cambiar a mayúsculas/minúsculas.
  - `.strip()`: Quitar espacios al inicio y al final.
  - `.split('delimitador')`: Convertir un string en una lista.
  - `'delimitador'.join(lista)`: Unir una lista de strings en un solo string.
  - `.find('texto')`: Buscar si un texto está dentro de otro.
  - `.replace('viejo', 'nuevo')`: Reemplazar texto.

- **Slicing (`[inicio:fin:paso]`):** Para "rebanar" strings y listas.

  ```python
  palabra = "Python"
  print(palabra[0:2]) # "Py"
  print(palabra[2:])  # "thon"
  print(palabra[::-1]) # "nohtyP" (invertir)
  ```

- **Funciones (`def`): Tu Propia Herramienta Personalizada**

  Imagina que tienes una tarea que repites constantemente, como calcular el IVA de un producto o saludar a un usuario. En lugar de escribir el mismo código una y otra vez, puedes empaquetar esa lógica en una **función**.

  Una función es como crear tu propia herramienta o una receta: le das un nombre, le dices qué "ingredientes" necesita (**parámetros**) y qué debe producir al final (**valor de retorno**). Son la clave para escribir código **DRY** (**D**on't **R**epeat **Y**ourself - No te repitas), haciendo tu programa más legible, reutilizable y fácil de mantener.

  - **`def`**: La palabra clave para definir una función.
  - **Parámetros**: Los datos de entrada que la función necesita para trabajar.
  - **`return`**: El resultado que la función devuelve al código que la llamó.

  ```python
  # Definimos una función que calcula el precio final con IVA
  def calcular_precio_final(precio_base, tasa_iva):
          """
          Calcula el precio final sumando el IVA al precio base.
          - precio_base: El precio del producto sin impuestos.
          - tasa_iva: La tasa de IVA en decimal (ej: 0.21 para 21%).
          """
          iva = precio_base * tasa_iva
          precio_final = precio_base + iva
          return precio_final

  # Usamos nuestra nueva herramienta
  precio_laptop = 1000
  precio_con_iva = calcular_precio_final(precio_laptop, 0.21)

  print(f"El precio base es {precio_laptop}€.")
  print(f"El precio final con IVA es {precio_con_iva}€.") # Salida: 1210.0
  ```

- **Módulos (`import`): La Caja de Herramientas Extendida**

  Python viene con un conjunto de herramientas básicas, pero su verdadero poder reside en su capacidad para importar "kits de herramientas" adicionales llamados **módulos**. Un módulo es simplemente un archivo de Python con código listo para usar (funciones, variables, etc.) que puedes incorporar a tu programa. Esto te permite acceder a funcionalidades avanzadas sin tener que escribirlas desde cero.

  - **Biblioteca Estándar:** Python incluye una vasta colección de módulos listos para usar, como `math` para operaciones matemáticas complejas, `random` para generar aleatoriedad o `datetime` para trabajar con fechas.
  - **Módulos de Terceros:** La comunidad de Python ha creado miles de módulos para casi cualquier tarea imaginable (desde análisis de datos con `pandas` hasta desarrollo web con `Flask`), que puedes instalar y usar.

  ```python
  # Importamos el módulo 'math' para acceder a herramientas matemáticas
  import math
  raiz_cuadrada = math.sqrt(25) # Calcula la raíz cuadrada
  print(f"La raíz cuadrada de 25 es {raiz_cuadrada}") # Salida: 5.0

  # Importamos el módulo 'random' para generar números al azar
  import random
  numero_suerte = random.randint(1, 100) # Elige un entero entre 1 y 100
  print(f"Tu número de la suerte es: {numero_suerte}")
  ```

- **Manejo de Errores (`try...except`): Tu Red de Seguridad**

  ¿Qué pasa si tu programa pide un número y el usuario escribe "hola"? ¿O si intentas leer un archivo que no existe? Sin un plan, tu programa se detendrá con un error. El bloque `try...except` es tu **plan de contingencia** para manejar estas situaciones inesperadas de forma elegante.

  - **`try`**: Aquí pones el código que podría fallar (el "Plan A").
  - **`except`**: Este bloque solo se ejecuta si ocurre un error en el `try` (el "Plan B"). Te permite capturar el error, mostrar un mensaje amigable y continuar la ejecución del programa en lugar de que se rompa.

  Esto hace que tu código sea **robusto** y a prueba de fallos.

  ```python
  # Ejemplo: Evitar que el programa se rompa si la entrada no es un número.
  try:
          edad_str = input("Introduce tu edad: ")
          edad = int(edad_str) # Esta línea puede fallar si se introduce texto
          print(f"El año que viene tendrás {edad + 1} años.")
  except ValueError:
          # Este código solo se ejecuta si int() falla.
          print("Error: Eso no parece un número válido. Por favor, inténtalo de nuevo.")
  ```

- **Manejo de Archivos (`with open(...)`): Guardando y Leyendo Información Permanente**

  Tus programas no viven en una burbuja. A menudo necesitan guardar resultados para usarlos más tarde, leer datos de configuración o generar informes. Esta herramienta te permite conectar tu código con los archivos de tu ordenador, haciendo que la información sea **persistente** (que sobreviva después de que el programa se cierre).

  La forma más segura y recomendada de trabajar con archivos es usando la estructura `with open(...)`. Esta sintaxis se encarga de abrir el archivo y, lo más importante, de **cerrarlo automáticamente** cuando terminas, incluso si ocurre un error.

  - **`open("nombre_archivo", "modo")`**: La función que abre el archivo.
    - **`"r"` (read)**: Para leer el contenido. El programa dará error si el archivo no existe.
    - **`"w"` (write)**: Para escribir. **¡Cuidado!** Si el archivo existe, borra todo su contenido. Si no existe, lo crea.
    - **`"a"` (append)**: Para añadir contenido al final del archivo sin borrar lo que ya hay. Si no existe, lo crea.

  ```python
  # 1. Escribir en un archivo (modo 'w')
  # Esto creará 'mi_lista_compras.txt' o lo sobrescribirá si ya existe.
  with open("mi_lista_compras.txt", "w") as archivo:
          archivo.write("Manzanas\n")
          archivo.write("Leche\n")

  # 2. Añadir a un archivo (modo 'a')
  # Esto añade una nueva línea sin borrar las anteriores.
  with open("mi_lista_compras.txt", "a") as archivo:
          archivo.write("Pan\n")

  # 3. Leer un archivo (modo 'r')
  # Leemos todo el contenido y lo mostramos.
  with open("mi_lista_compras.txt", "r") as archivo:
          contenido = archivo.read()
          print("Lista de la compra:")
          print(contenido)
  ```

## 6. Programación Orientada a Objetos (POO): Creando Tus Propias Herramientas

Hasta ahora, has usado herramientas y tipos de datos que Python te da. La POO te permite dar un paso más allá y **crear tus propios tipos de datos complejos**, con sus propias características y comportamientos. Es como pasar de usar herramientas prefabricadas a diseñar y construir las tuyas.

La idea central es agrupar datos (atributos) y las funciones que operan sobre esos datos (métodos) en una sola unidad llamada **objeto**.

- **Clase:** Es la **receta** o el **molde**. Define cómo será un objeto. Por ejemplo, una clase `Perro`.
- **Objeto:** Es la **instancia** creada a partir de la clase. Es el perro real que construyes con la receta. Puedes crear muchos objetos (`firulais`, `chispita`) a partir de una sola clase.

### 6.1 Bloques de Construcción: Clases, Atributos y Métodos

- **`class`**: La palabra clave para definir una nueva "receta".
- **Constructor (`__init__`)**: Un método especial que se ejecuta automáticamente al crear un nuevo objeto. Su trabajo es inicializar los atributos.
- **`self`**: Se refiere al objeto específico que se está creando o usando. Es la forma que tiene un objeto de acceder a "sus propios" datos.
- **Atributos**: Las variables que pertenecen a un objeto (`self.nombre`, `self.raza`). Son sus características.
- **Métodos**: Las funciones que pertenecen a un objeto (`self.ladrar()`). Son sus acciones.

```python
# Esta es nuestra "receta" o "molde" para crear perros.
class Perro:
    # 1. El constructor: se ejecuta al crear un nuevo perro.
    # 'self' se refiere al objeto específico que estamos creando.
    def __init__(self, nombre_perro, raza_perro):
        # 2. Atributos: guardamos los datos que nos dan en el objeto.
        self.nombre = nombre_perro  # 'self.nombre' es "el nombre de ESTE perro".
        self.raza = raza_perro      # 'self.raza' es "la raza de ESTE perro".

    # 3. Un método: una acción que el perro puede hacer.
    def ladrar(self):
        return f"¡Guau! Soy {self.nombre}, un {self.raza}."

# --- Ahora, usemos nuestra receta para crear objetos ---

# Creamos nuestro primer objeto Perro. Esto llama a __init__.
perro1 = Perro("Firulais", "Pastor Alemán")
perro2 = Perro("Chispita", "Chihuahua")

# Llamamos a sus métodos para que realicen acciones.
print(perro1.ladrar())  # Salida: ¡Guau! Soy Firulais, un Pastor Alemán.
print(perro2.ladrar())  # Salida: ¡Guau! Soy Chispita, un Chihuahua.
```

### 6.2 Los 4 Pilares de la POO

Estos son los conceptos que le dan todo su poder a la POO.

#### 1. Encapsulamiento: Protegiendo tus Datos

La idea es simple: **proteger los datos de un objeto para que no se modifiquen por accidente**. Imagina una cuenta bancaria: no querrías que cualquiera pudiera cambiar tu saldo directamente. Querrías que solo se pudiera hacer a través de métodos seguros como `depositar()` o `extraer()`.

En Python, usamos una convención: si un atributo empieza con un guion bajo (ej: `_saldo`), es una señal que dice: "Oye, esto es interno, por favor no lo toques directamente desde fuera".

```python
class CuentaBancaria:
    def __init__(self, titular, saldo_inicial=0):
        self.titular = titular
        # Ponemos un guion bajo para indicar que es un atributo "protegido".
        self._saldo = saldo_inicial

    # Método público para depositar (la forma correcta de cambiar el saldo).
    def depositar(self, cantidad):
        if cantidad > 0:
            self._saldo += cantidad
            print(f"Depósito exitoso. Nuevo saldo: {self._saldo}")
        else:
            print("Error: la cantidad debe ser positiva.")

    # Método público para ver el saldo de forma segura.
    def ver_saldo(self):
        return f"El saldo de {self.titular} es: ${self._saldo}"

# --- Uso correcto de la clase ---
mi_cuenta = CuentaBancaria("Ana", 1000)
mi_cuenta.depositar(500)
print(mi_cuenta.ver_saldo())

# Aunque Python te deja hacer esto, ¡es una mala práctica!
# mi_cuenta._saldo = 999999 # ¡No hagas esto! Ignoras la protección.
```

#### 2. Herencia: Creando Clases a partir de Otras

La herencia te permite crear una nueva clase (**clase hija**) que "hereda" todos los atributos y métodos de otra clase (**clase padre**). Esto es genial para reutilizar código.

```python
# --- Clase Padre (la más general) ---
class Animal:
    def __init__(self, nombre):
        self.nombre = nombre

    def comer(self):
        return f"{self.nombre} está comiendo."

# --- Clases Hijas (heredan de Animal) ---
class Perro(Animal):
    # Hereda nombre y el método comer() de Animal.
    # Añadimos un método que solo los perros tienen.
    def ladrar(self):
        return "¡Guau!"

class Gato(Animal):
    # Hereda de Animal y añade su propio método.
    def maullar(self):
        return "¡Miau!"

# --- Creamos objetos de las clases hijas ---
mi_perro = Perro("Rocky")
mi_gato = Gato("Pelusa")

# Pueden usar métodos de la clase padre (Animal)
print(mi_perro.comer())  # Salida: Rocky está comiendo.
# Y también pueden usar sus propios métodos
print(mi_perro.ladrar()) # Salida: ¡Guau!
```

#### 3. Polimorfismo: Mismo Nombre, Diferente Acción

El polimorfismo significa "muchas formas". Se refiere a que objetos de diferentes clases pueden responder al mismo método de maneras distintas. Esto hace tu código súper flexible.

```python
# Añadimos el método hacer_sonido a nuestras clases hijas
class Perro(Animal):
    def hacer_sonido(self):
        return "¡Guau!"

class Gato(Animal):
    def hacer_sonido(self):
        return "¡Miau!"

class Vaca(Animal):
    def hacer_sonido(self):
        return "¡Muuu!"

# --- La magia del polimorfismo ---
# Esta función no sabe qué tipo de animal recibe, solo que puede .hacer_sonido()
def imprimir_sonido(animal_objeto):
    print(animal_objeto.hacer_sonido())

# Creamos objetos de diferentes clases
perro = Perro("Toby")
gato = Gato("Mishi")
vaca = Vaca("Lola")

# Llamamos a la misma función con objetos diferentes
imprimir_sonido(perro)  # Salida: ¡Guau!
imprimir_sonido(gato)   # Salida: ¡Miau!
imprimir_sonido(vaca)   # Salida: ¡Muuu!
```

#### 4. Abstracción: Ocultando la Complejidad

La abstracción consiste en ocultar los detalles complejos y mostrar solo las funcionalidades esenciales. En POO, podemos crear "clases plantilla" que definen qué métodos **deben** tener las clases hijas, actuando como un "contrato".

```python
# Creamos un "contrato": cualquier 'Figura' DEBE tener un método para calcular su área.
class Figura:
    def calcular_area(self):
        # Si una clase hija no implementa este método, dará un error.
        raise NotImplementedError("Las clases hijas deben implementar 'calcular_area'")

# --- Ahora creamos clases concretas que cumplen el contrato ---
class Circulo(Figura):
    def __init__(self, radio):
        self.radio = radio

    # Cumplimos el contrato implementando el método.
    def calcular_area(self):
        return 3.14159 * (self.radio ** 2)

class Cuadrado(Figura):
    def __init__(self, lado):
        self.lado = lado

    # También cumplimos el contrato.
    def calcular_area(self):
        return self.lado * self.lado

# --- Uso ---
mi_circulo = Circulo(10)
mi_cuadrado = Cuadrado(5)

print(f"Área del círculo: {mi_circulo.calcular_area()}")
print(f"Área del cuadrado: {mi_cuadrado.calcular_area()}")
```
