# 04 — Desarrollo Backend

> Backend = lo que pasa "detrás de cámaras". Servidores, bases de datos, APIs.

## 🎯 Qué hace un backend

- Recibir peticiones del frontend (login, comprar, postear)
- Guardar datos en bases de datos
- Verificar permisos / seguridad
- Enviar emails, procesar pagos, generar reportes

---

## 🛣️ Ruta recomendada

```
Bases de redes  →  HTTP/APIs  →  Node.js o Python  →  Express/FastAPI  →  Bases de datos  →  Autenticación  →  Deploy
```

---

## 🟢 Node.js (JavaScript en el servidor)

**Por qué:** Si ya sabés JS del frontend, no aprendés un lenguaje nuevo.

### Recursos
- 📺 [Node.js desde cero - midudev](https://www.youtube.com/watch?v=fmwAOvjRDdQ)
- 📺 [Node.js + Express - Fazt](https://www.youtube.com/watch?v=jZHwA-rO61g)
- 📖 [Node.js docs](https://nodejs.org/es/docs/)

### Framework: Express.js
```javascript
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hola Mundo');
});

app.listen(3000);
```

### Alternativas modernas
- **Hono** — más rápido que Express
- **Fastify** — alta performance
- **NestJS** — para apps grandes (estilo Angular)

---

## 🐍 Python Backend

### FastAPI (recomendado en 2026)
- 📺 [FastAPI - Fazt Code](https://www.youtube.com/watch?v=_y9qQZXE24A)
- 📖 [fastapi.tiangolo.com](https://fastapi.tiangolo.com/es/)

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def saludar():
    return {"mensaje": "Hola Mundo"}
```

### Django
- 📺 [Django - Fazt](https://www.youtube.com/watch?v=T1intZyhXDU)

---

## 📡 APIs REST — Lo más importante de saber

| Método | Para qué |
|--------|---------|
| GET | Obtener datos |
| POST | Crear |
| PUT/PATCH | Actualizar |
| DELETE | Borrar |

### Recursos
- 📺 [APIs REST explicadas - midudev](https://www.youtube.com/watch?v=4Yt46X8tIyE)
- 🛠️ [Postman](https://www.postman.com/) — para probar APIs
- 🛠️ [Insomnia](https://insomnia.rest/) — alternativa a Postman

---

## 🔐 Autenticación

- **JWT** (JSON Web Tokens)
- **OAuth** (login con Google, GitHub, etc.)
- **Sessions + cookies**

📺 [JWT explicado - midudev](https://www.youtube.com/watch?v=_PnD06qrTOA)

### Servicios listos para usar
- **Clerk** — login bonito y fácil
- **Auth0** — el clásico
- **Supabase Auth** — gratis y open source

---

## 🚀 Deploy (subir tu backend a internet)

| Servicio | Mejor para | Precio |
|----------|-----------|--------|
| **Railway** | Apps pequeñas/medianas | Gratis con límites |
| **Render** | Similar a Railway | Tier gratis |
| **Vercel** | Next.js, serverless | Tier gratis generoso |
| **Fly.io** | Cualquier app | Tier gratis |
| **AWS/GCP** | Empresas grandes | Complejo, pero potente |

---

## 🎯 Proyectos para practicar

1. **API de tareas** (CRUD completo)
2. **URL shortener** (como bit.ly)
3. **API de blog** con autenticación
4. **Bot de Telegram/Discord**
5. **Scraper** que guarda datos en una BD

---

## ⏭️ Siguiente paso

Pasá a [05-Bases-de-Datos](../05-Bases-de-Datos/) — un backend sin BD es como un auto sin motor.
