# 🆚 VS Code Shortcuts Cheatsheet

> Estos atajos te van a multiplicar la velocidad por 5. En serio.

## 🍎 Mac / 🪟 Windows

> En Mac usá `Cmd`, en Windows/Linux `Ctrl`. Acá pongo `⌘` para Cmd.

---

## 📁 Manejar archivos

| Atajo Mac | Atajo Win | Acción |
|-----------|-----------|--------|
| `⌘ P` | `Ctrl+P` | **Quick Open** — abrir cualquier archivo |
| `⌘ Shift P` | `Ctrl+Shift+P` | **Command Palette** — todo, todo desde acá |
| `⌘ N` | `Ctrl+N` | Nuevo archivo |
| `⌘ W` | `Ctrl+W` | Cerrar pestaña |
| `⌘ Shift T` | `Ctrl+Shift+T` | Reabrir última cerrada |
| `⌘ K W` | `Ctrl+K W` | Cerrar todas las pestañas |
| `⌘ S` | `Ctrl+S` | Guardar |
| `⌘ K S` | `Ctrl+K S` | Guardar sin formatear |
| `⌘ Shift S` | `Ctrl+Shift+S` | Guardar como |

---

## 🧭 Navegación

| Atajo Mac | Atajo Win | Acción |
|-----------|-----------|--------|
| `⌘ B` | `Ctrl+B` | Toggle sidebar |
| `⌘ \` | `Ctrl+\` | Split editor |
| `⌘ 1/2/3` | `Ctrl+1/2/3` | Ir al editor 1, 2, 3 |
| `⌘ G` | `Ctrl+G` | Ir a línea N |
| `⌘ T` | `Ctrl+T` | Buscar símbolo en workspace |
| `⌘ Shift O` | `Ctrl+Shift+O` | Buscar símbolo en archivo |
| `⌘ F12` | `F12` | Ir a definición |
| `⌥ F12` | `Alt+F12` | Peek (mirar sin cambiar archivo) |
| `Shift F12` | `Shift+F12` | Mostrar referencias |
| `⌃ -` | `Alt+←` | Volver atrás |
| `⌃ Shift -` | `Alt+→` | Adelante |

---

## ✏️ Edición

| Atajo Mac | Atajo Win | Acción |
|-----------|-----------|--------|
| `⌘ D` | `Ctrl+D` | **Seleccionar siguiente ocurrencia** |
| `⌘ Shift L` | `Ctrl+Shift+L` | Seleccionar TODAS las ocurrencias |
| `⌘ ↑/↓` | `Alt+↑/↓` | Mover línea arriba/abajo |
| `⌘ Shift ↑/↓` | `Shift+Alt+↑/↓` | Duplicar línea |
| `⌘ /` | `Ctrl+/` | Comentar línea |
| `⌘ Shift /` | `Shift+Alt+A` | Comentar bloque |
| `⌘ ]` / `[` | `Ctrl+]` / `[` | Indentar / desindentar |
| `⌘ L` | `Ctrl+L` | Seleccionar línea |
| `⌘ Shift K` | `Ctrl+Shift+K` | Borrar línea |
| `⌘ Enter` | `Ctrl+Enter` | Nueva línea abajo |
| `⌘ Shift Enter` | `Ctrl+Shift+Enter` | Nueva línea arriba |
| `⌥ Click` | `Alt+Click` | **Multi cursor** |
| `⌘ ⌥ ↑/↓` | `Ctrl+Alt+↑/↓` | Multi cursor en líneas |

---

## 🔍 Búsqueda

| Atajo Mac | Atajo Win | Acción |
|-----------|-----------|--------|
| `⌘ F` | `Ctrl+F` | Buscar en archivo |
| `⌘ Shift F` | `Ctrl+Shift+F` | Buscar en TODO el proyecto |
| `⌘ ⌥ F` | `Ctrl+H` | Buscar y reemplazar |
| `⌘ Shift H` | `Ctrl+Shift+H` | Reemplazar en todo el proyecto |
| `F3` | `F3` | Siguiente match |
| `Shift F3` | `Shift+F3` | Anterior match |

---

## 💻 Terminal

| Atajo Mac | Atajo Win | Acción |
|-----------|-----------|--------|
| `⌃ \`` | `Ctrl+\`` | Toggle terminal |
| `⌃ Shift \`` | `Ctrl+Shift+\`` | Nueva terminal |
| `⌃ C` | `Ctrl+C` | Matar proceso |

---

## 🚀 Pro tips

### 1. Multi-cursor a fondo
- `⌘ D` repetido: agrega cada match
- `⌘ Shift L`: TODOS los matches de golpe
- `⌥ Click`: cursor manual en otro punto
- `⌘ ⌥ ↑/↓`: extender el cursor a línea arriba/abajo

### 2. Refactor rápido
- `F2`: renombrar símbolo en TODO el proyecto
- `⌘ .`: quick fix (importar, refactor, etc.)

### 3. Snippets
Escribí `tab` después de:
- `imp` → import
- `clg` → console.log()
- `for` → loop completo
- `try` → try/catch

### 4. Emmet (en HTML)
```
ul>li*3        →  <ul><li></li><li></li><li></li></ul>
div.card>h1+p  →  <div class="card"><h1></h1><p></p></div>
```

### 5. Zen mode (foco total)
`⌘ K Z` — pantalla limpia, sin distracciones

### 6. Buscar archivos por nombre + ir a línea
`⌘ P` → escribís: `nombre.js:42`

### 7. Comparar archivos
- Click derecho en archivo → "Select for compare"
- Click derecho en otro → "Compare with selected"

### 8. Sincronizar settings
`⌘ Shift P` → "Settings Sync" → te lleva los settings, atajos y extensiones a cualquier máquina con tu cuenta GitHub.

---

## 🎨 Extensions imprescindibles

| Extension | Para qué |
|-----------|----------|
| **Prettier** | Formatear código |
| **ESLint** | Linter JS/TS |
| **GitLens** | Git con superpoderes |
| **Tailwind CSS IntelliSense** | Autocomplete Tailwind |
| **Error Lens** | Errores inline |
| **Code Spell Checker** | Ortografía en código |
| **Path Intellisense** | Autocomplete de paths |
| **Auto Rename Tag** | Renombra `<div>` y cierra `</div>` |
| **Material Icon Theme** | Iconos lindos |
| **Live Server** | Servidor local con reload |
| **Thunder Client** | Probar APIs sin Postman |
| **Claude Code** | IA agente en CLI |
| **Continue** | IA inline (open source) |

---

## 🛠️ Settings recomendados

`⌘ Shift P` → "Open Settings (JSON)":

```json
{
  "editor.fontSize": 14,
  "editor.tabSize": 2,
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.minimap.enabled": false,
  "editor.bracketPairColorization.enabled": true,
  "editor.linkedEditing": true,
  "files.autoSave": "onFocusChange",
  "files.trimTrailingWhitespace": true,
  "files.insertFinalNewline": true,
  "workbench.startupEditor": "none",
  "terminal.integrated.fontSize": 13,
  "git.confirmSync": false,
  "git.autofetch": true,
  "explorer.confirmDelete": false
}
```

---

## 💡 Filosofía

**Si tu mano deja el teclado para usar el mouse, perdés segundos.**
**Esos segundos se acumulan en HORAS por semana.**
**Invertí 1 hora en aprender atajos → recuperás 100 hs al año.**
