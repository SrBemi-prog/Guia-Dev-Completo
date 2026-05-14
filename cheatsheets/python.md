# 🐍 Python Cheatsheet

## 🏗️ Básico

```python
# Variables
nombre = "Cami"          # str
edad = 25                # int
altura = 1.80            # float
activo = True            # bool
nada = None              # None (como null)

# Print
print("Hola", nombre)
print(f"Hola {nombre}, tenés {edad}")  # f-string

# Input
nombre = input("Tu nombre: ")
```

## 🔢 Operaciones

```python
2 + 3       # 5
10 / 3      # 3.333...
10 // 3     # 3   (división entera)
10 % 3      # 1   (módulo)
2 ** 3      # 8   (potencia)

# Comparación
a == b, a != b, a < b, a > b, a <= b, a >= b

# Lógicos
a and b, a or b, not a
```

## 📝 Strings

```python
s = "Hola Mundo"

len(s)                  # 10
s.upper()               # "HOLA MUNDO"
s.lower()               # "hola mundo"
s.strip()               # quita espacios
s.replace("o", "0")     # "H0la Mund0"
s.split(" ")            # ["Hola", "Mundo"]
"-".join(["a", "b"])    # "a-b"
"Hola" in s             # True
s[0]                    # "H"
s[-1]                   # "o" (último)
s[0:4]                  # "Hola" (slice)
s[::-1]                 # invertido
f"{nombre}: {edad}"     # f-string
```

## 📚 Listas

```python
nums = [1, 2, 3]

nums.append(4)          # [1,2,3,4]
nums.insert(0, 0)       # [0,1,2,3,4]
nums.pop()              # quita el último
nums.remove(2)          # quita el primer 2
nums[0] = 10            # modificar
len(nums)               # 4
nums[::-1]              # invertido
sorted(nums)            # ordenado (nueva lista)
nums.sort()             # in-place

# Slicing
nums[1:3]               # del 1 al 2
nums[:3]                # primeros 3
nums[-2:]               # últimos 2

# Iterar
for n in nums: print(n)
for i, n in enumerate(nums): print(i, n)
```

## 🗂️ Diccionarios

```python
user = {"nombre": "Cami", "edad": 25}

user["nombre"]          # "Cami"
user.get("altura", 0)   # 0 si no existe
user["altura"] = 1.8    # agregar
del user["edad"]        # borrar

# Iterar
for key in user: ...
for key, val in user.items(): ...

# Comprehension
cuadrados = {n: n**2 for n in range(5)}

# Merge (3.9+)
nuevo = {**dict1, **dict2}
nuevo = dict1 | dict2
```

## 🎯 Sets (sin duplicados)

```python
s = {1, 2, 3}
s.add(4)
s.remove(2)
s | otro_set            # unión
s & otro_set            # intersección
s - otro_set            # diferencia

# Quitar duplicados de lista
unicos = list(set([1, 1, 2, 3]))
```

## 🔁 Loops

```python
for i in range(10):           # 0 a 9
for i in range(1, 11):        # 1 a 10
for i in range(0, 10, 2):     # pares

while x > 0:
    x -= 1
    if x == 3: continue
    if x == 1: break
```

## ⚡ Comprehensions (lo más Pythonico)

```python
# Listas
cuadrados = [n**2 for n in range(10)]
pares = [n for n in nums if n % 2 == 0]

# Diccionarios
d = {n: n**2 for n in range(5)}

# Sets
s = {n % 3 for n in range(10)}

# Generator (perezoso)
g = (n**2 for n in range(10))
```

## 🎯 Funciones

```python
def saludar(nombre, edad=18):
    """Docstring opcional."""
    return f"Hola {nombre}, {edad}"

# Args variables
def maximo(*nums):
    return max(nums)

# Kwargs
def config(**opts):
    print(opts)

config(color="rojo", tamano=10)

# Lambda
doblar = lambda x: x * 2

# Anotaciones de tipo
def suma(a: int, b: int) -> int:
    return a + b
```

## 🏛️ Clases

```python
class User:
    def __init__(self, nombre):
        self.nombre = nombre

    def saludar(self):
        return f"Hola {self.nombre}"

    @staticmethod
    def crear(n):
        return User(n)

u = User("Cami")
u.saludar()
```

## 📁 Archivos

```python
# Leer
with open("archivo.txt") as f:
    contenido = f.read()
    # o linea por linea:
    for linea in f:
        print(linea.strip())

# Escribir
with open("archivo.txt", "w") as f:
    f.write("hola\n")

# JSON
import json
with open("data.json") as f:
    data = json.load(f)

with open("out.json", "w") as f:
    json.dump(data, f, indent=2, ensure_ascii=False)

# CSV
import csv
with open("data.csv") as f:
    reader = csv.DictReader(f)
    for row in reader:
        print(row["nombre"])
```

## 🚨 Manejo de errores

```python
try:
    x = 10 / 0
except ZeroDivisionError as e:
    print(f"Error: {e}")
except (TypeError, ValueError):
    print("Otro tipo")
else:
    print("Todo bien")
finally:
    print("Siempre se ejecuta")

# Custom
raise ValueError("mensaje")
```

## 🛠️ Stdlib útil

```python
# Datetime
from datetime import datetime, timedelta
ahora = datetime.now()
ayer = ahora - timedelta(days=1)
ahora.strftime("%Y-%m-%d")

# Pathlib (moderno)
from pathlib import Path
p = Path("./archivos/data.txt")
p.exists()
p.read_text()
p.write_text("hola")
for f in Path(".").glob("*.py"): ...

# OS
import os
os.environ.get("API_KEY")
os.listdir(".")

# Subprocess
import subprocess
result = subprocess.run(["ls", "-la"], capture_output=True, text=True)
print(result.stdout)

# Requests (instalá: pip install requests)
import requests
r = requests.get("https://api.com/data")
data = r.json()
```

## 🎲 Snippets

```python
# Random
import random
random.randint(1, 10)
random.choice(["a", "b", "c"])
random.shuffle(lista)

# Contar elementos
from collections import Counter
Counter("hola").most_common()  # [('o',1),('h',1),...]

# Default dict
from collections import defaultdict
d = defaultdict(int)
d["x"] += 1  # no rompe aunque no exista

# Zip
nombres = ["a", "b", "c"]
edades = [1, 2, 3]
for n, e in zip(nombres, edades):
    print(n, e)

# Enumerate
for i, val in enumerate(["a","b","c"]):
    print(i, val)
```

## 📦 Entornos virtuales

```bash
# Crear
python3 -m venv venv

# Activar (Mac/Linux)
source venv/bin/activate

# Activar (Windows)
venv\Scripts\activate

# Instalar
pip install requests pandas

# Guardar deps
pip freeze > requirements.txt

# Instalar desde reqs
pip install -r requirements.txt

# Salir
deactivate
```
