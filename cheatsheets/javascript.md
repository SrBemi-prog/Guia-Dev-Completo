# 🟨 JavaScript Moderno Cheatsheet

## 📦 Variables

```javascript
let x = 5;          // Mutable
const PI = 3.14;    // Inmutable (USAR SIEMPRE que puedas)
// var: NO USAR. Heredado, scope confuso.
```

## 🔢 Tipos

```javascript
typeof "hola"      // "string"
typeof 42          // "number"
typeof true        // "boolean"
typeof undefined   // "undefined"
typeof null        // "object" (bug histórico)
typeof []          // "object"
typeof {}          // "object"
typeof function(){}// "function"
```

## 📝 Strings

```javascript
const nombre = "Cami";
const saludo = `Hola ${nombre}`;        // Template literal
const grita = "hola".toUpperCase();     // "HOLA"
const partes = "a,b,c".split(",");      // ["a","b","c"]
const unido = ["a","b"].join("-");      // "a-b"
const sub = "hola mundo".slice(0, 4);   // "hola"
"texto".includes("ex");                 // true
"  texto  ".trim();                     // "texto"
"texto".replace("e", "3");              // "t3xto"
"texto".replaceAll("t", "T");           // "TexTo"
```

## 🔢 Numbers / Math

```javascript
parseInt("42px")        // 42
parseFloat("3.14m")     // 3.14
Number("42")            // 42
+("42")                 // 42 (atajo)

Math.round(4.7)         // 5
Math.floor(4.9)         // 4
Math.ceil(4.1)          // 5
Math.max(1, 2, 3)       // 3
Math.random()           // 0-0.999...
Math.floor(Math.random() * 10)  // 0-9
```

## 📚 Arrays

```javascript
const arr = [1, 2, 3];

// Agregar / quitar
arr.push(4);              // [1,2,3,4] al final
arr.pop();                // sacar el último
arr.unshift(0);           // [0,1,2,3] al inicio
arr.shift();              // sacar el primero

// Inmutables (recomendados)
const nuevo = [...arr, 4];        // copiar + agregar
const sinPrimero = arr.slice(1);  // [2,3]
const filtrado = arr.filter(n => n > 1);  // [2,3]
const doblado = arr.map(n => n * 2);      // [2,4,6]
const suma = arr.reduce((acc, n) => acc + n, 0);  // 6

// Buscar
arr.find(n => n === 2);          // 2
arr.findIndex(n => n === 2);     // 1
arr.includes(2);                  // true
arr.indexOf(2);                   // 1
arr.some(n => n > 2);             // true (¿alguno?)
arr.every(n => n > 0);            // true (¿todos?)

// Ordenar
arr.sort((a, b) => a - b);  // ascendente
arr.sort((a, b) => b - a);  // descendente
arr.reverse();
```

## 🗂️ Objects

```javascript
const user = { nombre: "Cami", edad: 25 };

user.nombre              // "Cami"
user["nombre"]           // "Cami"
user.altura = 1.8        // Agregar
delete user.edad         // Borrar

// Destructuring
const { nombre, edad } = user;
const { nombre: n } = user;       // renombrar
const { x = 0 } = {};             // default

// Spread / merge
const copia = { ...user };
const merged = { ...user, ...otroObj };

// Iterar
Object.keys(user)         // ["nombre", "edad"]
Object.values(user)       // ["Cami", 25]
Object.entries(user)      // [["nombre","Cami"], ...]
for (const k in user) {}  // claves
```

## 🎯 Funciones

```javascript
// Declaración
function suma(a, b) { return a + b; }

// Arrow (moderna)
const suma = (a, b) => a + b;
const cuadrado = n => n * n;       // 1 param sin paréntesis
const log = () => console.log("hi");

// Default params
function saludar(nombre = "amigo") { ... }

// Rest params
function maximo(...nums) {
  return Math.max(...nums);
}
maximo(1, 5, 3);  // 5

// Async
async function fetchData() {
  const res = await fetch("/api");
  const data = await res.json();
  return data;
}
```

## 🔁 Loops

```javascript
// For clásico
for (let i = 0; i < 10; i++) {}

// For of (valores de array)
for (const item of arr) {}

// For in (claves de objeto — evitar para arrays)
for (const key in obj) {}

// While
while (condicion) {}

// Iteraciones funcionales (preferí estas)
arr.forEach(item => console.log(item));
arr.map(...);
arr.filter(...);
```

## ❓ Condicionales modernas

```javascript
// Ternario
const tipo = edad >= 18 ? "adulto" : "menor";

// Nullish coalescing
const valor = x ?? "default";    // default si x es null/undefined

// Optional chaining
const calle = user?.direccion?.calle;
const result = obj?.method?.();
arr?.[0];

// Logical assignment
x ??= "default";       // si x es null/undefined
x ||= "fallback";      // si x es falsy
x &&= nuevoValor;      // si x es truthy
```

## ⚡ Async / Promises

```javascript
// Async/await
async function getUser() {
  try {
    const res = await fetch("/api/user");
    if (!res.ok) throw new Error("Error");
    return await res.json();
  } catch (err) {
    console.error(err);
  }
}

// Promise.all (paralelo)
const [a, b, c] = await Promise.all([
  fetch1(), fetch2(), fetch3()
]);

// Promise.allSettled (sin fallar si uno revienta)
const results = await Promise.allSettled([...]);
```

## 🏛️ Classes

```javascript
class User {
  constructor(nombre) {
    this.nombre = nombre;
  }

  saludar() {
    return `Hola, soy ${this.nombre}`;
  }

  static crear(n) {
    return new User(n);
  }
}

const u = new User("Cami");
const u2 = User.crear("Pepe");
```

## 🧰 Snippets útiles

```javascript
// Copia profunda
const copia = structuredClone(obj);
const copia = JSON.parse(JSON.stringify(obj));  // limita a JSON

// Eliminar duplicados
const unicos = [...new Set([1, 1, 2, 3])];  // [1,2,3]

// Random entero
const rand = (min, max) =>
  Math.floor(Math.random() * (max - min + 1)) + min;

// Sleep
const sleep = ms => new Promise(r => setTimeout(r, ms));

// Debounce simple
const debounce = (fn, ms) => {
  let timer;
  return (...args) => {
    clearTimeout(timer);
    timer = setTimeout(() => fn(...args), ms);
  };
};

// Esperar element DOM
const $ = sel => document.querySelector(sel);
const $$ = sel => document.querySelectorAll(sel);
```

## 🌐 DOM

```javascript
// Seleccionar
document.getElementById("id")
document.querySelector(".clase")
document.querySelectorAll("div")

// Modificar
el.textContent = "texto"
el.innerHTML = "<b>html</b>"
el.classList.add("nueva")
el.classList.remove("vieja")
el.classList.toggle("activa")
el.setAttribute("href", "/")
el.style.color = "red"

// Eventos
el.addEventListener("click", e => {
  e.preventDefault();
  console.log(e.target);
});

// Crear element
const div = document.createElement("div");
div.textContent = "Hola";
document.body.appendChild(div);
```

## 🪤 Trampas comunes

```javascript
// == vs ===: USAR SIEMPRE ===
0 == ""         // true  (rara)
0 === ""        // false (sano)

// NaN
NaN === NaN     // false (sí, así)
Number.isNaN(NaN)  // true (usá esto)

// this en arrow vs regular
btn.addEventListener("click", function() {
  this  // el botón
});
btn.addEventListener("click", () => {
  this  // el scope externo
});
```
