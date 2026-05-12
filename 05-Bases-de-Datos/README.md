# 05 — Bases de Datos

> Donde se guarda TODA la información: usuarios, productos, mensajes, todo.

## 🗂️ Tipos de bases de datos

### 1. Relacionales (SQL)
Datos en tablas con filas y columnas. Como un Excel ordenado.

- **PostgreSQL** — la mejor opción gratuita y profesional ⭐
- **MySQL** — clásica, muy usada
- **SQLite** — archivo único, ideal para empezar

### 2. No Relacionales (NoSQL)
Datos como documentos JSON o pares clave-valor.

- **MongoDB** — la más popular
- **Redis** — para cache, súper rápida
- **Firebase** — Google, gratis con límites

---

## 📚 SQL — Lo BÁSICO que tenés que saber

```sql
-- Crear tabla
CREATE TABLE usuarios (
    id SERIAL PRIMARY KEY,
    nombre VARCHAR(100),
    email VARCHAR(100) UNIQUE
);

-- Insertar
INSERT INTO usuarios (nombre, email) VALUES ('Camilo', 'cami@mail.com');

-- Leer
SELECT * FROM usuarios WHERE id = 1;

-- Actualizar
UPDATE usuarios SET nombre = 'Cami' WHERE id = 1;

-- Borrar
DELETE FROM usuarios WHERE id = 1;
```

---

## 📺 Cursos recomendados

### SQL
- 📺 [SQL desde cero - Pildoras Informaticas](https://www.youtube.com/watch?v=Sue4CTFzNRk)
- 📺 [PostgreSQL - Fazt](https://www.youtube.com/watch?v=Mt3tFsfPV5w)
- 🎮 [SQLBolt](https://sqlbolt.com/) — tutorial interactivo
- 🎮 [SQL Murder Mystery](https://mystery.knightlab.com/) — aprendé resolviendo un crimen

### MongoDB
- 📺 [MongoDB - Fazt](https://www.youtube.com/watch?v=u5J0M3lTNa0)
- 📖 [MongoDB University](https://learn.mongodb.com/) (cursos gratis oficiales)

---

## 🛠️ Herramientas

| Herramienta | Para qué |
|-------------|---------|
| **DBeaver** | Cliente universal de BDs |
| **pgAdmin** | Específico de PostgreSQL |
| **MongoDB Compass** | GUI oficial de MongoDB |
| **TablePlus** | Cliente moderno (paga, pero hermoso) |

---

## ☁️ BDs en la nube (gratis para empezar)

- **Supabase** — PostgreSQL + auth + storage gratis
- **Neon** — PostgreSQL serverless gratis
- **PlanetScale** — MySQL serverless
- **MongoDB Atlas** — MongoDB en la nube, 512MB gratis

---

## 🔄 ORMs (te ahorran escribir SQL crudo)

Un ORM traduce código de tu lenguaje a SQL automáticamente.

### Para Node.js / TypeScript
- **Prisma** ⭐ (el más usado en 2026)
- **Drizzle** (más rápido y moderno)

### Para Python
- **SQLAlchemy**
- **Tortoise ORM** (async)

### Ejemplo con Prisma
```typescript
const usuario = await prisma.usuario.create({
  data: { nombre: 'Camilo', email: 'cami@mail.com' }
});
```

---

## 🎯 Ejercicios

1. Diseñá las tablas para una app de tareas (usuarios + tareas)
2. Hacé consultas tipo: "todos los usuarios que tienen tareas sin completar"
3. Modelá una mini red social: posts, likes, comentarios
4. Practicá JOINs en [SQLBolt](https://sqlbolt.com/)

---

## ⏭️ Siguiente paso

[06-Git-y-DevOps](../06-Git-y-DevOps/) para aprender control de versiones y deploy.
