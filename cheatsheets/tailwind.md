# 🎨 Tailwind CSS Cheatsheet

## 📦 Layout

### Display
```
block / inline-block / inline / flex / grid / hidden
```

### Flexbox
```html
<div class="flex items-center justify-between gap-4">
  <!-- items-center: vertical -->
  <!-- justify-between: horizontal spaced -->
</div>
```

| Clase | CSS |
|-------|-----|
| `flex` | display: flex |
| `flex-col` | flex-direction: column |
| `flex-row` | flex-direction: row |
| `flex-wrap` | flex-wrap: wrap |
| `flex-1` | flex: 1 1 0% |
| `items-center` | align-items: center |
| `items-start` / `end` | align-items: start/end |
| `justify-center` | justify-content: center |
| `justify-between` | justify-content: space-between |
| `justify-around` | space-around |
| `gap-4` | gap: 1rem |

### Grid
```html
<div class="grid grid-cols-3 gap-4">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

| Clase | CSS |
|-------|-----|
| `grid` | display: grid |
| `grid-cols-3` | grid-template-columns: repeat(3, ...) |
| `col-span-2` | col-span: 2 |
| `row-span-3` | row-span: 3 |

---

## 📏 Spacing

Escala: `0, 0.5, 1, 1.5, 2, 2.5, 3, 4, 5, 6, 8, 10, 12, 16, 20, 24, 32, 40, 48, 64, 80, 96`

Unidad: `1` = `0.25rem` = `4px`

### Padding
```
p-4    → padding en todos lados
px-4   → padding horizontal (left + right)
py-2   → padding vertical
pt-4   → padding-top
pr-4   → padding-right
pb-4   → padding-bottom
pl-4   → padding-left
```

### Margin (igual pero con `m`)
```
m-4, mx-auto, my-2, mt-4, mr-2, ...
-mt-4  → margin-top negativo
```

### Space between (entre hijos)
```html
<div class="space-y-4">
  <p>uno</p>
  <p>dos</p>  <!-- margin-top: 1rem -->
  <p>tres</p>
</div>
```

---

## 🔤 Tipografía

| Clase | CSS |
|-------|-----|
| `text-xs` | 12px |
| `text-sm` | 14px |
| `text-base` | 16px (default) |
| `text-lg` | 18px |
| `text-xl` | 20px |
| `text-2xl` → `text-9xl` | + |
| `font-thin` → `font-black` | weight 100-900 |
| `font-bold` | bold (700) |
| `text-left/center/right` | alineación |
| `uppercase / lowercase / capitalize` | case |
| `italic / not-italic` | |
| `underline / line-through / no-underline` | |
| `truncate` | una línea, con ... |
| `leading-tight / normal / loose` | line-height |
| `tracking-tight / wide` | letter-spacing |

---

## 🎨 Colores

Sintaxis: `<propiedad>-<color>-<intensidad>`

```
text-red-500
bg-blue-100
border-gray-300
ring-purple-500
```

### Colores principales (con 50-950)
- gray, slate, zinc, neutral, stone
- red, orange, amber, yellow
- lime, green, emerald, teal, cyan
- sky, blue, indigo, violet, purple, fuchsia, pink, rose

### Modo oscuro
```html
<div class="bg-white dark:bg-gray-900 text-black dark:text-white">
  Se adapta al tema
</div>
```

---

## 📐 Tamaños

### Width / Height
```
w-full        → 100%
w-screen      → 100vw
w-1/2         → 50%
w-1/3         → 33.33%
w-1/4         → 25%
w-64          → 16rem (256px)

h-full / h-screen / h-32 / etc.

max-w-md      → max-width: 28rem
max-w-7xl     → contenedor amplio
min-h-screen  → 100vh mínimo
```

---

## 🖼️ Bordes y sombras

```
border             → border 1px
border-2           → 2px
border-t           → solo top
border-gray-200    → color
border-dashed      → estilo

rounded            → 4px
rounded-lg         → 8px
rounded-xl         → 12px
rounded-2xl        → 16px
rounded-full       → círculo
rounded-t-lg       → solo arriba

shadow-sm
shadow             → sombra default
shadow-md
shadow-lg
shadow-xl
shadow-2xl
shadow-none
```

---

## 📍 Posicionamiento

```
relative / absolute / fixed / sticky / static

top-0 / right-0 / bottom-0 / left-0
inset-0           → top:0 right:0 bottom:0 left:0

z-0 / z-10 / z-50 / z-auto
```

---

## ✨ Efectos / Estados

### Hover, focus, etc.
```html
<button class="bg-blue-500 hover:bg-blue-600 active:bg-blue-700 focus:ring-2">
  Click
</button>
```

Prefijos comunes:
- `hover:`
- `focus:`
- `focus-within:`
- `active:`
- `disabled:`
- `group-hover:` (cuando un padre con clase `group` recibe hover)
- `peer-hover:`
- `first:` / `last:` / `odd:` / `even:`

---

## 📱 Responsive

Mobile first: clases sin prefijo aplican a TODO. Prefijos agregan a breakpoints más grandes.

| Prefijo | Min-width |
|---------|-----------|
| (none) | 0px |
| `sm:` | 640px |
| `md:` | 768px |
| `lg:` | 1024px |
| `xl:` | 1280px |
| `2xl:` | 1536px |

```html
<div class="text-base md:text-xl lg:text-2xl">
  Más grande en pantallas grandes
</div>

<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4">
  Columnas responsive
</div>
```

---

## 🎯 Patrones comunes

### Centrar horizontal y verticalmente
```html
<div class="min-h-screen flex items-center justify-center">
  centrado
</div>
```

### Card básica
```html
<div class="bg-white dark:bg-gray-800 rounded-lg shadow-md p-6">
  contenido
</div>
```

### Botón
```html
<button class="bg-blue-600 hover:bg-blue-700 text-white font-semibold px-4 py-2 rounded-lg transition-colors">
  Click
</button>
```

### Container con max-width
```html
<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
  contenido
</div>
```

### Grid responsive de cards
```html
<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
  <div>...</div>
</div>
```

### Texto truncado a N líneas
```html
<p class="line-clamp-3">texto muy largo...</p>
```

---

## 🎭 Animaciones

```
transition           → transition-all
transition-colors    → solo colores
duration-300         → 300ms
ease-in-out

animate-spin         → girar
animate-ping
animate-pulse        → loading
animate-bounce
```

```html
<button class="hover:scale-105 transition-transform duration-200">
  crece al hover
</button>
```

---

## 🛠️ Pro tips

1. **Usá [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)** en VS Code.
2. **Cmd+click en una clase** → te lleva al CSS generado.
3. **Si tu HTML es ilegible**, usá **@apply** en CSS o componentes.
4. **Para valores fuera de la escala**: `w-[123px]`, `text-[#ff5733]`.
5. **`prettier-plugin-tailwindcss`** ordena las clases automáticamente.
6. **Shadcn/ui** son componentes pre-armados con Tailwind.

---

## 🚀 Setup nuevo

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

En `tailwind.config.js`:
```javascript
module.exports = {
  content: ["./src/**/*.{js,jsx,ts,tsx,html}"],
  theme: { extend: {} },
  plugins: [],
  darkMode: 'class',
}
```

En tu CSS:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```
