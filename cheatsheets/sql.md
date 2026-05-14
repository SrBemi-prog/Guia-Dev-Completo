# 🗄️ SQL Cheatsheet

## 📖 Leer datos (SELECT)

```sql
-- Básico
SELECT * FROM usuarios;
SELECT nombre, email FROM usuarios;

-- Filtrar
SELECT * FROM usuarios WHERE edad > 18;
SELECT * FROM usuarios WHERE pais = 'AR' AND activo = TRUE;
SELECT * FROM usuarios WHERE nombre LIKE 'Cam%';     -- empieza con
SELECT * FROM usuarios WHERE nombre LIKE '%lo';      -- termina con
SELECT * FROM usuarios WHERE id IN (1, 2, 3);
SELECT * FROM usuarios WHERE edad BETWEEN 18 AND 30;
SELECT * FROM usuarios WHERE deleted_at IS NULL;

-- Ordenar
SELECT * FROM usuarios ORDER BY edad DESC;
SELECT * FROM usuarios ORDER BY pais, edad DESC;

-- Limitar
SELECT * FROM usuarios LIMIT 10;
SELECT * FROM usuarios LIMIT 10 OFFSET 20;  -- paginación

-- Distinct (sin duplicados)
SELECT DISTINCT pais FROM usuarios;

-- Contar
SELECT COUNT(*) FROM usuarios;
SELECT COUNT(DISTINCT pais) FROM usuarios;
```

---

## ➕ Insertar

```sql
INSERT INTO usuarios (nombre, email, edad)
VALUES ('Cami', 'cami@mail.com', 25);

-- Varios de una
INSERT INTO usuarios (nombre, email) VALUES
  ('Ana', 'ana@x.com'),
  ('Beto', 'beto@x.com');
```

---

## ✏️ Actualizar

```sql
UPDATE usuarios
SET edad = 26, activo = TRUE
WHERE id = 1;

-- ⚠️ SIN WHERE: actualiza TODA la tabla. CUIDADO.
```

---

## ❌ Borrar

```sql
DELETE FROM usuarios WHERE id = 1;

-- Borrar todo (CUIDADO)
DELETE FROM usuarios;

-- Vaciar tabla rápido
TRUNCATE TABLE usuarios;
```

---

## 🔗 JOINs

```
usuarios          pedidos
+----+------+    +----+-----------+--------+
| id | name |    | id | usuario_id| total  |
+----+------+    +----+-----------+--------+
```

### INNER JOIN (los que MATCH en ambas)
```sql
SELECT u.nombre, p.total
FROM usuarios u
INNER JOIN pedidos p ON p.usuario_id = u.id;
```

### LEFT JOIN (TODOS de la izquierda + match)
```sql
SELECT u.nombre, p.total
FROM usuarios u
LEFT JOIN pedidos p ON p.usuario_id = u.id;
-- Usuarios sin pedidos: p.total será NULL
```

### Visual rápido
```
INNER JOIN:  ●∩●   solo lo que está en ambos
LEFT JOIN:   ●●∩   todo lo de la izq + intersección
RIGHT JOIN:  ∩●●   todo lo de la der + intersección
FULL JOIN:   ●●∪●● todo de ambos lados
```

---

## 📊 Agrupar (GROUP BY)

```sql
-- Cantidad de usuarios por país
SELECT pais, COUNT(*) as cantidad
FROM usuarios
GROUP BY pais
ORDER BY cantidad DESC;

-- Total vendido por usuario
SELECT u.nombre, SUM(p.total) as total_gastado
FROM usuarios u
JOIN pedidos p ON p.usuario_id = u.id
GROUP BY u.nombre
HAVING SUM(p.total) > 1000;  -- HAVING = WHERE pero para agregados
```

### Funciones de agregación
```sql
COUNT(*)        -- contar filas
COUNT(col)      -- contar valores no-NULL
SUM(col)        -- sumar
AVG(col)        -- promedio
MIN(col)        -- mínimo
MAX(col)        -- máximo
```

---

## 🏗️ Crear / modificar tablas

```sql
CREATE TABLE usuarios (
  id SERIAL PRIMARY KEY,
  nombre VARCHAR(100) NOT NULL,
  email VARCHAR(100) UNIQUE NOT NULL,
  edad INT CHECK (edad >= 0),
  pais VARCHAR(2) DEFAULT 'AR',
  created_at TIMESTAMP DEFAULT NOW()
);

-- Foreign key
CREATE TABLE pedidos (
  id SERIAL PRIMARY KEY,
  usuario_id INT REFERENCES usuarios(id) ON DELETE CASCADE,
  total DECIMAL(10, 2),
  fecha DATE
);

-- Modificar tabla
ALTER TABLE usuarios ADD COLUMN telefono VARCHAR(20);
ALTER TABLE usuarios DROP COLUMN telefono;
ALTER TABLE usuarios RENAME COLUMN nombre TO name;
ALTER TABLE usuarios ALTER COLUMN edad SET DEFAULT 18;

-- Borrar tabla
DROP TABLE usuarios;
```

---

## ⚡ Índices (acelerar queries)

```sql
-- Crear índice
CREATE INDEX idx_usuarios_email ON usuarios(email);
CREATE INDEX idx_usuarios_compuesto ON usuarios(pais, edad);

-- Único
CREATE UNIQUE INDEX idx_email_unique ON usuarios(email);

-- Ver índices (Postgres)
\d usuarios

-- Borrar
DROP INDEX idx_usuarios_email;
```

**Cuándo usar índices:**
- Columnas que aparecen mucho en `WHERE`
- Foreign keys
- Columnas de `ORDER BY`

**Cuándo NO:**
- Tablas chicas
- Columnas que se actualizan mucho

---

## 🪟 Window Functions (avanzado pero útil)

```sql
-- Ranking
SELECT
  nombre,
  edad,
  RANK() OVER (ORDER BY edad DESC) as posicion
FROM usuarios;

-- Promedio por grupo sin GROUP BY
SELECT
  nombre,
  pais,
  edad,
  AVG(edad) OVER (PARTITION BY pais) as edad_promedio_pais
FROM usuarios;

-- Total acumulado
SELECT
  fecha,
  monto,
  SUM(monto) OVER (ORDER BY fecha) as acumulado
FROM pedidos;
```

---

## 🔄 Subqueries

```sql
-- En WHERE
SELECT * FROM usuarios
WHERE id IN (SELECT usuario_id FROM pedidos WHERE total > 1000);

-- En SELECT
SELECT
  nombre,
  (SELECT COUNT(*) FROM pedidos WHERE usuario_id = u.id) as pedidos
FROM usuarios u;

-- CTE (Common Table Expression) — más legible
WITH usuarios_top AS (
  SELECT * FROM usuarios WHERE edad > 30
)
SELECT * FROM usuarios_top WHERE pais = 'AR';
```

---

## 💡 Trampas comunes

```sql
-- NULL no se compara con =
WHERE col = NULL          -- ❌ siempre falso
WHERE col IS NULL         -- ✅

-- COUNT ignora NULLs
SELECT COUNT(email) FROM users  -- no cuenta NULLs
SELECT COUNT(*) FROM users      -- cuenta todas las filas

-- UPDATE/DELETE sin WHERE: borra/modifica TODO
DELETE FROM users;        -- ⚠️ borra TODOS

-- LIKE es case-sensitive en algunos DBs
WHERE nombre ILIKE 'cami%'  -- Postgres: case insensitive
```

---

## 🔐 SQL injection — NUNCA hagas esto

```python
# ❌ INSEGURO
sql = f"SELECT * FROM users WHERE name = '{input}'"

# ✅ Seguro (parametrizado)
cursor.execute("SELECT * FROM users WHERE name = %s", (input,))
```
