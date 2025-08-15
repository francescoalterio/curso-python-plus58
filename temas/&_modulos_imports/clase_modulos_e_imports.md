# Módulos e Importaciones en Python

En esta clase verás cómo usar módulos estándar como `math` y `random`, y cómo crear tus propios módulos para organizar código y reutilizar funciones.

---

## 1) ¿Qué es un módulo?

Un módulo es simplemente un archivo `.py` que contiene código Python (funciones, variables, clases) que puedes reutilizar en otros archivos mediante `import`.

Ventajas:

- Organización: separa responsabilidades por archivos.
- Reutilización: evita duplicar código.
- Mantenibilidad: facilita pruebas y cambios.

---

## 2) Importando módulos estándar

### 2.1. `math`: funciones matemáticas

El módulo `math` proporciona acceso a funciones matemáticas definidas por el estándar de C. No funciona con números complejos; si los necesitas, usa el módulo `cmath`.

```python
import math

# Ejemplo de uso
raiz = math.sqrt(16)      # 4.0
potencia = math.pow(2, 3) # 8.0 (float)
pi_valor = math.pi        # 3.14159...
```

**Funciones y constantes principales:**

- **`math.pi`**:

  - **Descripción**: Una constante que representa el número Pi (π ≈ 3.14159...).
  - **Retorno**: `float`.
  - **Ejemplo**: `print(math.pi)` devuelve `3.141592653589793`.

- **`math.sqrt(x)`**:

  - **Descripción**: Calcula la raíz cuadrada de un número.
  - **Parámetros**: `x` (tipo: `int` o `float`) - Un número no negativo.
  - **Retorno**: `float` - La raíz cuadrada de `x`.
  - **Lanza**: `ValueError` si `x` es negativo.
  - **Ejemplo**: `math.sqrt(64)` devuelve `8.0`.

- **`math.pow(x, y)`**:

  - **Descripción**: Calcula `x` elevado a la potencia `y` (`x**y`).
  - **Parámetros**: `x` (base), `y` (exponente).
  - **Retorno**: `float` - El resultado de `x` elevado a `y`.
  - **Ejemplo**: `math.pow(5, 2)` devuelve `25.0`.

- **`math.floor(x)`**:

  - **Descripción**: Redondea un número hacia abajo al entero más cercano.
  - **Parámetros**: `x` (un número).
  - **Retorno**: `int` - El entero más grande que es menor o igual a `x`.
  - **Ejemplo**: `math.floor(3.7)` devuelve `3`.

- **`math.ceil(x)`**:

  - **Descripción**: Redondea un número hacia arriba al entero más cercano.
  - **Parámetros**: `x` (un número).
  - **Retorno**: `int` - El entero más pequeño que es mayor o igual a `x`.
  - **Ejemplo**: `math.ceil(3.1)` devuelve `4`.

- **`math.factorial(x)`**:
  - **Descripción**: Calcula el factorial de un número entero no negativo.
  - **Parámetros**: `x` (un entero no negativo).
  - **Retorno**: `int` - El factorial de `x`.
  - **Lanza**: `ValueError` si `x` no es un entero o es negativo.
  - **Ejemplo**: `math.factorial(5)` (es decir, 5 _ 4 _ 3 _ 2 _ 1) devuelve `120`.

**Formas comunes de importar:**

- `import math`: usas el nombre del módulo: `math.sqrt(...)`.
- `import math as m`: alias corto: `m.sqrt(...)`.
- `from math import sqrt, pi`: importa nombres puntuales: `sqrt(9)`, `pi`.
- `from math import *`: desaconsejado; contamina el espacio de nombres y dificulta leer/depurar.

Buenas prácticas:

- Importa al inicio del archivo.
- Prefiere `import modulo` o `from modulo import nombre1, nombre2` explícito.

### 2.2. `random`: números aleatorios

Este módulo implementa generadores de números pseudoaleatorios para varias distribuciones.

```python
import random

# Ejemplo de uso
entero_aleatorio = random.randint(1, 6)
loteria = random.choice(["rojo", "verde", "azul"])
```

**Funciones principales:**

- **`random.seed(a=None)`**:

  - **Descripción**: Inicializa el generador de números aleatorios. Al usar la misma semilla (`a`), obtendrás la misma secuencia de números aleatorios, lo cual es útil para que tus resultados sean reproducibles.
  - **Parámetros**: `a` (opcional) - El valor de la semilla. Puede ser un `int`, `str`, `bytes` o `bytearray`. Si se omite o es `None`, se usa una semilla impredecible (ej: la hora actual).
  - **Ejemplo**:
    ```python
    random.seed(10)
    print(random.random()) # 0.5714025946899135
    random.seed(10)
    print(random.random()) # 0.5714025946899135 (mismo resultado)
    ```

- **`random.random()`**:

  - **Descripción**: Devuelve un número de punto flotante aleatorio en el intervalo `[0.0, 1.0)`.
  - **Parámetros**: Ninguno.
  - **Retorno**: `float`.
  - **Ejemplo**: `random.random()` puede devolver `0.89...`.

- **`random.randint(a, b)`**:

  - **Descripción**: Devuelve un número entero aleatorio `N` tal que `a <= N <= b`. Es inclusivo en ambos extremos.
  - **Parámetros**: `a` (límite inferior), `b` (límite superior).
  - **Retorno**: `int`.
  - **Ejemplo**: `random.randint(1, 6)` puede devolver `4`.

- **`random.uniform(a, b)`**:

  - **Descripción**: Devuelve un número de punto flotante aleatorio `N` tal que `a <= N <= b` o `b <= N <= a`.
  - **Parámetros**: `a` (límite inferior), `b` (límite superior).
  - **Retorno**: `float`.
  - **Ejemplo**: `random.uniform(1, 1.5)` puede devolver `1.34...`.

- **`random.choice(seq)`**:

  - **Descripción**: Devuelve un elemento aleatorio de una secuencia no vacía.
  - **Parámetros**: `seq` - Una secuencia (lista, tupla, string).
  - **Retorno**: Un elemento del tipo de los contenidos en la secuencia.
  - **Lanza**: `IndexError` si la secuencia está vacía.
  - **Ejemplo**: `random.choice(['cara', 'cruz'])` puede devolver `'cruz'`.

- **`random.shuffle(x)`**:

  - **Descripción**: Mezcla la secuencia `x` en su lugar (la modifica directamente). No devuelve nada.
  - **Parámetros**: `x` - Una secuencia mutable (como una lista).
  - **Retorno**: `None`.
  - **Ejemplo**:
    ```python
    cartas = ['As', 'Rey', 'Reina']
    random.shuffle(cartas)
    # la lista 'cartas' ahora podría ser ['Reina', 'As', 'Rey']
    ```

- **`random.sample(population, k)`**:
  - **Descripción**: Devuelve una lista de longitud `k` con elementos únicos elegidos de la secuencia `population`. No modifica la secuencia original.
  - **Parámetros**: `population` (la secuencia de origen), `k` (el número de elementos a elegir).
  - **Retorno**: `list` - Una nueva lista con los elementos seleccionados.
  - **Ejemplo**: `random.sample(range(1, 50), 6)` puede devolver `[25, 1, 42, 13, 30, 11]` (una selección para la lotería).

---

## 3) Creando tus propios módulos

Supón esta estructura de proyecto:

```
mi_proyecto/
  ├─ main.py
  └─ utils.py
```

Contenido de `utils.py`:

```python
# utils.py

def es_par(n):
    return n % 2 == 0

def promedio(numeros):
    if not numeros:
        return 0
    return sum(numeros) / len(numeros)

if __name__ == "__main__":
    # Este bloque se ejecuta solo si corres utils.py directamente
    print("Prueba rápida:", es_par(4), promedio([1, 2, 3]))
```

Uso en `main.py`:

```python
# main.py
import utils

print(utils.es_par(10))
print(utils.promedio([10, 20, 30]))
```

O importando nombres puntuales:

```python
from utils import es_par, promedio

print(es_par(7))
print(promedio([5, 5]))
```

Consejos:

- Evita nombres de archivo que choquen con módulos estándar (p. ej., no llames a tu archivo `random.py`).
- Usa `__name__ == "__main__"` para incluir tests rápidos dentro del módulo sin afectar a quien lo importe.

### ¿Cómo funciona `if __name__ == "__main__"`?

Python asigna un valor a la variable especial `__name__` para cada script.

- Si ejecutas el script directamente (ej: `python utils.py`), Python asigna `__name__ = "__main__"`.
- Si importas el script como un módulo (ej: `import utils`), Python asigna el nombre del archivo como un string a `__name__` (ej: `__name__ = "utils"`).

Esta distinción permite que el código dentro del bloque `if` solo se ejecute cuando el archivo es el punto de entrada principal del programa.

---

## 4) Paquetes (carpetas con módulos)

Un paquete es una carpeta que contiene módulos (archivos `.py`). Para que Python trate una carpeta como un paquete, debe contener un archivo `__init__.py`. Aunque en versiones modernas de Python puede estar vacío, este archivo es fundamental para inicializar el paquete y controlar las importaciones.

Ejemplo:

```
mi_proyecto/
  ├─ main.py
  └─ utilidades/
      ├─ __init__.py       # Puede estar vacío o definir la API pública del paquete.
      ├─ numeros.py
      └─ cadenas.py
```

`numeros.py`:

```python
def es_primo(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True
```

`cadenas.py`:

```python
def invertir(texto):
    return texto[::-1]
```

### Simplificando importaciones con `__init__.py`

Puedes usar `__init__.py` para "exponer" funciones de los módulos internos, haciendo que parezcan parte del paquete principal.

Contenido de `utilidades/__init__.py`:

```python
# "Promocionamos" estas funciones al nivel del paquete 'utilidades'
from .numeros import es_primo
from .cadenas import invertir
```

Ahora, en `main.py`, la importación es más limpia:

```python
# main.py
from utilidades import es_primo, invertir

print(es_primo(11))   # True
print(invertir("hola"))  # aloh
```

En lugar de `from utilidades.numeros import es_primo`, importamos directamente desde `utilidades`.

### Importaciones relativas (dentro del paquete)

Si un módulo dentro de un paquete necesita importar otro módulo del mismo paquete, se usan importaciones relativas con `.`

```python
# dentro de utilidades/cadenas.py
from .numeros import es_primo  # El '.' significa "desde el paquete actual"
```

---

## 5) ¿Cómo encuentra Python los módulos? `sys.path`

Cuando haces `import mi_modulo`, Python no busca en todo tu ordenador. Sigue un orden estricto:

1.  **Directorio actual**: La carpeta desde donde se ejecuta el script principal.
2.  **Variables de entorno `PYTHONPATH`**: (Uso avanzado) Una lista de directorios que puedes definir.
3.  **Directorios de instalación estándar**: Donde Python guarda sus librerías y paquetes de terceros.

Esta lista de rutas está disponible en el módulo `sys`:

```python
import sys
print(sys.path)
```

Entender `sys.path` es clave para diagnosticar errores de `ModuleNotFoundError`.

---

## 6) Errores comunes y cómo evitarlos

- **Conflictos de nombres**: No nombres tus archivos como módulos estándar (ej: `math.py`, `random.py`).
- **Rutas de ejecución**: Si tienes problemas con importaciones relativas, intenta ejecutar tu script como un módulo desde la carpeta raíz de tu proyecto con el flag `-m`. Ejemplo: `python -m mi_proyecto.main`.
- **Importaciones circulares**: Si `a.py` importa `b.py` y `b.py` importa `a.py`, se produce un error. Para solucionarlo, reorganiza tu código, por ejemplo, moviendo las funciones compartidas a un tercer módulo `c.py`.

---

## 7) Ejercicios rápidos

1.  Crea un módulo `geometria.py` con funciones `area_circulo(r)` y `perimetro_circulo(r)` usando `math.pi`. Impórtalo desde `main.py` y muestra resultados.
2.  Crea un paquete `juego/` con `dados.py` (usa `random.randint`) y `cartas.py` (usa `random.choice`). Usa `__init__.py` para poder importar `tirar_dado()` y `sacar_carta()` directamente desde `juego`.
3.  Añade en cada módulo un bloque `if __name__ == "__main__":` con pruebas mínimas.
