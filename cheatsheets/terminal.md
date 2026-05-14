# 💻 Terminal Cheatsheet (Bash / Zsh)

## 🧭 Moverse por carpetas

```bash
pwd                  # ¿Dónde estoy?
ls                   # Listar archivos
ls -la               # Incluir ocultos + detalles
ls -lh               # Tamaños humanos (K, M, G)
cd carpeta           # Entrar
cd ..                # Subir un nivel
cd ~                 # Home
cd -                 # Carpeta anterior
```

## 📁 Crear / borrar

```bash
mkdir nueva                    # Crear carpeta
mkdir -p ruta/larga/anidada    # Crear con subcarpetas
touch archivo.txt              # Crear archivo vacío
rm archivo.txt                 # Borrar archivo
rm -rf carpeta                 # Borrar carpeta y todo dentro (CUIDADO)
cp origen destino              # Copiar
cp -r carpeta destino          # Copiar carpetas
mv origen destino              # Mover o renombrar
```

## 👀 Ver contenido

```bash
cat archivo.txt              # Mostrar todo
less archivo.txt             # Paginado (q para salir)
head -20 archivo.txt         # Primeras 20 líneas
tail -20 archivo.txt         # Últimas 20 líneas
tail -f log.txt              # Seguir en vivo (útil para logs)
wc -l archivo.txt            # Contar líneas
```

## 🔍 Buscar

```bash
# Buscar archivos por nombre
find . -name "*.js"
find . -type d -name "node_*"     # Carpetas
find . -size +10M                  # Archivos +10MB

# Buscar texto dentro de archivos
grep "palabra" archivo.txt
grep -r "palabra" .                # Recursivo
grep -ri "palabra" .               # Sin distinguir mayús
grep -n "palabra" archivo.txt      # Con número de línea

# ripgrep (más rápido, instalá con: brew install ripgrep)
rg "palabra"
```

## 🔗 Encadenar comandos

```bash
cmd1 && cmd2          # Ejecutar cmd2 SOLO si cmd1 tuvo éxito
cmd1 || cmd2          # Ejecutar cmd2 SOLO si cmd1 falló
cmd1 ; cmd2           # Ejecutar ambos sin importar
cmd1 | cmd2           # Pipe: output de 1 → input de 2
cmd1 > archivo.txt    # Sobrescribir archivo con output
cmd1 >> archivo.txt   # Anexar
cmd1 2> errores.txt   # Capturar errores
cmd1 &> todo.txt      # Capturar todo (output + errores)
```

### Ejemplos prácticos
```bash
# Contar archivos .js en el proyecto
find . -name "*.js" | wc -l

# Buscar TODO en el código y guardar a archivo
grep -rn "TODO" . > todos.txt

# Procesos que consumen RAM
ps aux | sort -k 4 -rn | head -5
```

## ⌨️ Atajos de teclado

| Atajo | Qué hace |
|-------|---------|
| `Ctrl + C` | Cancelar comando |
| `Ctrl + D` | Cerrar terminal / salir |
| `Ctrl + R` | Buscar en historial (incremental) |
| `Ctrl + A` | Ir al inicio de línea |
| `Ctrl + E` | Ir al fin de línea |
| `Ctrl + U` | Borrar desde cursor hasta inicio |
| `Ctrl + K` | Borrar desde cursor hasta fin |
| `Ctrl + W` | Borrar palabra anterior |
| `Ctrl + L` | Limpiar pantalla |
| `↑` / `↓` | Navegar historial |
| `Tab` | Autocompletar |
| `!!` | Repetir último comando |
| `!sudo` | Último comando que empezó con "sudo" |

## 🔐 Permisos

```bash
chmod +x script.sh          # Hacer ejecutable
chmod 755 archivo           # rwx r-x r-x
chmod 644 archivo           # rw- r-- r--
chown usuario archivo       # Cambiar dueño
sudo comando                # Como administrador
```

## 📊 Información del sistema

```bash
df -h                  # Espacio en disco
du -sh carpeta         # Tamaño de una carpeta
free -h                # RAM (linux)
top                    # Procesos en vivo
htop                   # top mejorado
ps aux                 # Lista de procesos
kill -9 <pid>          # Matar proceso
which comando          # ¿Dónde está instalado?
uname -a               # Info del SO
```

## 🌐 Network

```bash
ping google.com              # ¿Hay internet?
curl https://api.com         # GET request
curl -X POST -d "x=1" url    # POST
curl -O https://url.com/file # Descargar archivo
wget https://url             # Descargar (alternativa)
ifconfig                     # IPs del sistema (mac/linux)
nslookup google.com          # Resolver DNS
```

## 📦 Variables de entorno

```bash
echo $HOME              # Imprimir variable
export VAR=valor        # Definir variable (sesión)
env                     # Ver todas

# Persistir en ~/.zshrc o ~/.bashrc
echo 'export API_KEY=xyz' >> ~/.zshrc
source ~/.zshrc         # Recargar
```

## 🪄 Trucos pro

```bash
# Reemplazar parte del último comando
git config --global user.name "Camilo"
^Camilo^Cami            # Cambia Camilo por Cami y re-ejecuta

# Expansión de llaves
mkdir -p src/{components,pages,utils}
touch test{1,2,3}.txt

# Ejecutar comando en background
sleep 60 &              # Sigue corriendo, te devuelve la terminal
jobs                    # Ver jobs en background
fg %1                   # Traerlo al frente
```

## 🛠️ Tools modernos (instalables vía brew)

```bash
brew install bat        # cat con highlighting
brew install eza        # ls bonito
brew install fzf        # fuzzy finder
brew install ripgrep    # grep rápido
brew install fd         # find rápido
brew install jq         # parsear JSON
brew install httpie     # curl bonito
brew install tldr       # man pages para humanos
```
