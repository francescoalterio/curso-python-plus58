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

```python
import math

raiz = math.sqrt(16)      # 4.0
potencia = math.pow(2, 3) # 8.0 (float)
pi = math.pi              # 3.14159...
entero_abajo = math.floor(3.7)  # 3
entero_arriba = math.ceil(3.1)  # 4
```

Formas comunes de importar:

- `import math`: usas el nombre del módulo: `math.sqrt(...)`.
- `import math as m`: alias corto: `m.sqrt(...)`.
- `from math import sqrt, pi`: importa nombres puntuales: `sqrt(9)`, `pi`.
- `from math import *`: desaconsejado; contamina el espacio de nombres y dificulta leer/depurar.

Buenas prácticas:

- Importa al inicio del archivo.
- Prefiere `import modulo` o `from modulo import nombre1, nombre2` explícito.

### 2.2. `random`: números aleatorios

```python
import random

random.random()      # float en [0.0, 1.0)
random.randint(1, 6) # entero entre 1 y 6 (incluye extremos)
random.choice(["rojo", "verde", "azul"]) # un elemento de la lista

nums = [1, 2, 3, 4, 5]
random.shuffle(nums) # mezcla la lista in-place

random.seed(42)      # fija la semilla -> resultados reproducibles
```

Notas:

- Usa `seed` cuando quieras reproducibilidad en ejercicios/demos.
- Evita usar aleatoriedad en pruebas sin fijar semilla (las pruebas se vuelven inestables).

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
