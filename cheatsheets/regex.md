# 🔣 Regex Cheatsheet

> Las expresiones regulares dan miedo. Acá las desmitificamos.

## 🧱 Bloques básicos

| Símbolo | Qué match | Ejemplo |
|---------|-----------|---------|
| `a` | la letra a | `a` → `a` |
| `.` | cualquier carácter | `a.c` → `abc`, `a3c` |
| `\d` | dígito (0-9) | `\d\d` → `42` |
| `\D` | NO dígito | `\D` → `a` pero no `5` |
| `\w` | letra/dígito/_ | `\w+` → `hola_123` |
| `\W` | NO \w | espacios, símbolos |
| `\s` | espacio en blanco | espacios, tabs, \n |
| `\S` | NO espacio | |
| `\b` | borde de palabra | `\bcat\b` → `cat` pero no `cats` |

---

## 🔢 Cuantificadores

| Símbolo | Significa |
|---------|-----------|
| `?` | 0 o 1 vez |
| `*` | 0 o más |
| `+` | 1 o más |
| `{3}` | exactamente 3 |
| `{2,4}` | entre 2 y 4 |
| `{2,}` | 2 o más |

```
a?      → "", "a"
a*      → "", "a", "aa", "aaa"...
a+      → "a", "aa", "aaa"...
\d{4}   → "1234"
```

---

## 📦 Grupos y alternativas

```
(abc)        → grupo: "abc" como unidad
(abc)+       → "abc", "abcabc", "abcabcabc"
a|b|c        → "a" o "b" o "c"
(gato|perro) → "gato" o "perro"
[abc]        → cualquier letra a, b o c
[a-z]        → cualquier minúscula
[A-Z]        → cualquier mayúscula
[0-9]        → dígito (igual que \d)
[^abc]       → CUALQUIER cosa que no sea a, b, c
```

---

## ⚓ Anclas (posición)

```
^abc     → empieza con "abc"
abc$     → termina con "abc"
^abc$    → la línea completa es "abc"
\bword\b → palabra entera
```

---

## 🎯 Ejemplos REALES

### Email (simplificado)
```
^[\w.+-]+@[\w-]+\.[a-zA-Z]{2,}$
```

### URL (simplificado)
```
https?://[\w.-]+(/\S*)?
```

### Teléfono internacional
```
\+?\d{1,3}[-.\s]?\d{1,14}
```

### Solo letras
```
^[a-zA-Z\s]+$
```

### Username (3-20 chars, letras/números/_)
```
^[a-zA-Z0-9_]{3,20}$
```

### Password fuerte (8+, 1 mayús, 1 minús, 1 dígito)
```
^(?=.*[a-z])(?=.*[A-Z])(?=.*\d).{8,}$
```

### Fecha YYYY-MM-DD
```
^\d{4}-\d{2}-\d{2}$
```

### Hex color
```
^#([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})$
```

---

## 🛠️ Uso en lenguajes

### JavaScript
```javascript
const r = /^\d+$/;
r.test("123");                    // true
"abc123".match(/\d+/);            // ["123"]
"abc123".replace(/\d+/, "X");     // "abcX"
"abc123".replace(/\d+/g, "X");    // "abcX" (global)
```

### Python
```python
import re

re.match(r"^\d+$", "123")        # Match al inicio
re.search(r"\d+", "abc123")       # Match en cualquier parte
re.findall(r"\d+", "ab1 cd2")    # ["1", "2"]
re.sub(r"\d+", "X", "abc123")    # "abcX"

# Compilar (más rápido si se usa varias veces)
pattern = re.compile(r"\d+")
pattern.findall("ab1 cd2")
```

### Grep en terminal
```bash
grep -E "regex" archivo.txt       # -E para regex extendida
grep -P "\d+" archivo.txt          # -P para Perl regex (más potente)
```

---

## 🎓 Conceptos avanzados

### Lookahead / Lookbehind
```
foo(?=bar)    → "foo" SEGUIDO de "bar" (no incluye "bar")
foo(?!bar)    → "foo" NO seguido de "bar"
(?<=bar)foo   → "foo" PRECEDIDO de "bar" (no incluye "bar")
(?<!bar)foo   → "foo" NO precedido de "bar"
```

### Grupos nombrados
```javascript
const r = /(?<año>\d{4})-(?<mes>\d{2})/;
"2026-05".match(r).groups   // {año: "2026", mes: "05"}
```

### Flags
| Flag | Significa |
|------|-----------|
| `g` | global (todas las matches) |
| `i` | case-insensitive |
| `m` | multilínea (^ y $ matchean cada línea) |
| `s` | `.` también matchea \n |
| `u` | unicode |

```javascript
/abc/gi    // global + case-insensitive
```

---

## 🛟 Tools para practicar

- **[regex101.com](https://regex101.com/)** ⭐ — explica cada parte
- **[regexr.com](https://regexr.com/)** — visual
- **[RegexLearn](https://regexlearn.com/es)** — tutorial interactivo en español
- **[Regex Crossword](https://regexcrossword.com/)** — puzzles

---

## 💡 Reglas mentales

1. **Siempre testealas en regex101.com antes de usarlas en producción.**
2. **Greedy vs lazy:** `.*` es greedy (todo). `.*?` es lazy (lo mínimo).
3. **No uses regex para HTML / JSON** — usá un parser específico.
4. **Cuando la regex parece imposible, divide:** match básico + validación adicional en código.
5. **Comentá las regex complejas** — vos del futuro va a agradecerte.
