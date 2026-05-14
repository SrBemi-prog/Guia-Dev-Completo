# 🌳 Git Cheatsheet

## Setup inicial (una sola vez)
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
git config --global init.defaultBranch main
git config --global core.editor "code --wait"
```

---

## 📦 Comandos del día a día

```bash
git init                      # Inicializar repo
git status                    # ¿Qué cambió?
git add archivo.js            # Stagear un archivo
git add .                     # Stagear todo
git commit -m "mensaje"       # Confirmar
git push                      # Subir al remoto
git pull                      # Bajar cambios
git log --oneline -10         # Últimos 10 commits compactos
git diff                      # Ver cambios sin stagear
git diff --staged             # Ver cambios stageados
```

---

## 🌿 Branches

```bash
git branch                    # Listar ramas
git branch -a                 # Incluir remotas
git checkout -b nueva-rama    # Crear y cambiar
git switch otra-rama          # Cambiar (moderno)
git merge otra-rama           # Fusionar
git branch -d rama-vieja      # Borrar (segura)
git branch -D rama-vieja      # Borrar (forzada)
git push -u origin nueva-rama # Subir rama nueva
```

---

## 🆘 SITUACIONES DE PÁNICO

### "Hice cambios y quiero deshacerlos (sin commit)"
```bash
git restore archivo.js        # Un archivo
git restore .                 # Todo (CUIDADO: borra trabajo)
```

### "Stagee algo por error"
```bash
git restore --staged archivo.js
```

### "El último commit estuvo mal"
```bash
# Cambiar mensaje
git commit --amend -m "mensaje correcto"

# Agregar archivo olvidado
git add archivo-olvidado.js
git commit --amend --no-edit
```

### "Necesito deshacer el último commit pero mantener los cambios"
```bash
git reset --soft HEAD~1       # Mantiene cambios stageados
git reset HEAD~1              # Mantiene cambios sin stagear
```

### "Necesito BORRAR el último commit (peligroso)"
```bash
git reset --hard HEAD~1       # ⚠️ Pierde cambios para siempre
```

### "Pusheé algo que NO quería pushear"
```bash
# Si no lo vio nadie aún:
git reset --hard HEAD~1
git push --force-with-lease   # Más seguro que --force

# Si ya está en producción: NO hagas force. Hacé un revert:
git revert <commit-hash>
git push
```

### "Hay conflict de merge"
```bash
# Git te muestra qué archivos. Editás, dejás lo correcto, luego:
git add archivos-resueltos
git commit  # O sigue con git merge --continue
```

### "Quiero ver qué hice en un commit"
```bash
git show <hash>
git show HEAD                 # El último
git log -p archivo.js         # Historial con diff
```

### "Necesito recuperar trabajo borrado"
```bash
git reflog                    # Lista TODO lo que hiciste
git reset --hard <hash>       # Volver a ese estado
```

---

## 📡 Trabajar con remotos

```bash
git remote -v                          # Ver remotos
git remote add origin <url>            # Agregar remoto
git clone <url>                        # Clonar repo
git fetch                              # Bajar sin mergear
git pull --rebase                      # Pull sin merge commit
git push --tags                        # Subir tags
```

---

## 🏷️ Tags / versiones

```bash
git tag v1.0.0                # Tag local
git tag -a v1.0.0 -m "msg"    # Tag anotado
git push origin v1.0.0        # Subir tag
git push --tags               # Todos los tags
```

---

## 🔍 Stash (guardar cambios temporales)

```bash
git stash                     # Guardar cambios
git stash pop                 # Recuperar
git stash list                # Ver stashes
git stash apply stash@{1}     # Aplicar uno específico
git stash drop                # Borrar el último
```

---

## 💡 .gitignore esencial

```gitignore
# Sistema
.DS_Store
Thumbs.db

# IDEs
.vscode/
.idea/

# Node
node_modules/
*.log
.env
.env.local

# Python
__pycache__/
*.pyc
venv/
.venv/

# Build
dist/
build/
.next/
```

---

## ⚡ Aliases útiles

```bash
git config --global alias.s "status"
git config --global alias.co "checkout"
git config --global alias.br "branch"
git config --global alias.last "log -1 HEAD"
git config --global alias.lg "log --oneline --graph --all"
```

Después: `git s`, `git lg`, etc.

---

## 🧠 Regla mental

```
git add    →  poné en la mesa lo que vas a meter en la caja
git commit →  cerrá la caja con etiqueta
git push   →  mandala al depósito remoto
```
