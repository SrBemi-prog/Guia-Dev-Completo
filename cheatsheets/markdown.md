# 📝 Markdown Cheatsheet

> El formato universal para READMEs, docs y notas.

## 🅰️ Encabezados

```markdown
# H1 - Título principal
## H2 - Sección
### H3 - Subsección
#### H4
##### H5
###### H6
```

---

## ✏️ Énfasis

```markdown
*itálica* o _itálica_
**negrita** o __negrita__
***negrita itálica***
~~tachado~~
==resaltado== (no estándar)
`código en línea`
```

Resultado:
*itálica* — **negrita** — ***ambos*** — ~~tachado~~ — `código`

---

## 📋 Listas

### Sin orden
```markdown
- Item 1
- Item 2
  - Subitem
  - Otro subitem
- Item 3
```

### Ordenadas
```markdown
1. Primero
2. Segundo
3. Tercero
```

### Checkbox (GitHub)
```markdown
- [x] Completado
- [ ] Pendiente
- [ ] Otra cosa
```

---

## 🔗 Links e imágenes

```markdown
[Texto del link](https://url.com)
[Link con tooltip](https://url.com "tooltip")
[Link relativo](./otro-archivo.md)
[Link a sección](#encabezado)

![Texto alt de imagen](./imagen.png)
![Imagen con tooltip](./img.png "Mi imagen")

<!-- Imagen con tamaño (HTML) -->
<img src="./img.png" width="200" alt="texto" />
```

### Links reutilizables
```markdown
Acá hablo de [Claude][claude] y otra vez [Claude][claude].

[claude]: https://claude.ai
```

---

## 💻 Código

### Inline
```markdown
Acá hay `código` en medio del texto.
```

### Bloques
````markdown
```
Sin lenguaje
```

```javascript
console.log("con highlighting");
```

```python
print("Python")
```

```bash
ls -la
```
````

---

## 📊 Tablas

```markdown
| Columna 1 | Columna 2 | Columna 3 |
|-----------|-----------|-----------|
| dato 1    | dato 2    | dato 3    |
| más 1     | más 2     | más 3     |
```

### Alineación
```markdown
| Izquierda | Centro | Derecha |
|:----------|:------:|--------:|
| a         |   b    |       c |
```

---

## 💬 Citas (blockquote)

```markdown
> Esto es una cita.
> Sigue en la siguiente línea.
>
> > Cita anidada.
```

> Esto es una cita.

---

## ➖ Separadores

```markdown
---
o
***
o
___
```

---

## 🎨 GitHub Flavored Markdown (extra)

### Callouts (GitHub)
```markdown
> [!NOTE]
> Información útil

> [!TIP]
> Consejo

> [!IMPORTANT]
> Algo crucial

> [!WARNING]
> Cuidado con esto

> [!CAUTION]
> Peligroso
```

### Detalles colapsables
```markdown
<details>
<summary>Click para abrir</summary>

Contenido oculto.
- Puede tener listas
- Y más cosas

</details>
```

### Mention / Issue / Commit (en GitHub)
```markdown
@usuario          → menciona persona
#123              → link al issue 123
abc1234           → link al commit
```

### Emojis
```markdown
:rocket: :tada: :fire: :heart: :+1: :warning:
```
🚀 🎉 🔥 ❤️ 👍 ⚠️

---

## 🛠️ HTML válido en Markdown

```html
<br>          <!-- salto de línea forzado -->
<hr>          <!-- separador -->
<sub>x₂</sub>
<sup>x²</sup>
<kbd>Ctrl</kbd> + <kbd>C</kbd>

<details><summary>Title</summary>contenido</details>

<div align="center">
  centrado
</div>
```

---

## 🎯 Template de README profesional

```markdown
# Nombre del Proyecto

> Una línea de descripción.

![Banner](./banner.png)

[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)
[![Stars](https://img.shields.io/github/stars/usuario/repo)](https://github.com/usuario/repo)

## 🚀 Demo
[Ver en vivo](https://link.com)

## ✨ Features
- Feature 1
- Feature 2
- Feature 3

## 🛠️ Stack
- React
- TypeScript
- TailwindCSS

## 📦 Instalación
\`\`\`bash
git clone https://github.com/usuario/repo
cd repo
npm install
npm run dev
\`\`\`

## 📄 Licencia
[MIT](LICENSE)
```

---

## 💡 Tips finales

1. **Preview antes de publicar** — VS Code: `Cmd+Shift+V`
2. **Limpia líneas vacías** — exceso desorganiza
3. **Imágenes locales > links externos** — más estables
4. **Para mucho contenido**, usá un `<details>` para no abrumar
5. **Badges en shields.io** dan profesionalismo
6. **README es el frente de tu proyecto** — invertí tiempo en el primer pantallazo
