# 06 — Git, GitHub y DevOps

> Git es el control de versiones que TODO dev usa. GitHub es donde vive tu código.

## 🐙 Git — Lo esencial

### Comandos del día a día

```bash
git init                    # Crear repo
git status                  # Ver cambios
git add .                   # Agregar todos los cambios
git commit -m "mensaje"     # Confirmar cambios
git push                    # Subir al servidor
git pull                    # Bajar cambios
git clone <url>             # Clonar un repo
git branch                  # Ver ramas
git checkout -b nueva-rama  # Crear y cambiar de rama
git merge otra-rama         # Fusionar ramas
git log                     # Ver historial
```

---

## 📺 Cursos de Git

- 📺 [Git y GitHub - midudev](https://www.youtube.com/watch?v=3GymExBkKjE)
- 📺 [Curso Git - Fazt](https://www.youtube.com/watch?v=HiXLkL42tMU)
- 🎮 [Learn Git Branching](https://learngitbranching.js.org/?locale=es_AR) ⭐ — interactivo
- 📖 [Pro Git Book (gratis)](https://git-scm.com/book/es/v2)

---

## 🐱 GitHub — Tu portfolio público

### Lo que hay que aprender
- Crear repos
- README.md decentes (con badges, screenshots)
- Pull Requests
- Issues
- GitHub Actions (CI/CD básico)
- GitHub Pages (hostear webs gratis)

### Tu perfil = tu CV
- Subí TODOS tus proyectos.
- Hacé un README de perfil bonito (buscá "GitHub profile README" para inspirarte).
- Contribuí a proyectos open source.

---

## 🚢 Deploy / Hosting gratis

| Servicio | Para qué | Tier gratis |
|----------|---------|-------------|
| **Vercel** | Frontend, Next.js | Generoso |
| **Netlify** | Frontend, JAMstack | Bueno |
| **GitHub Pages** | HTML/CSS/JS estático | Ilimitado |
| **Railway** | Backend + BD | $5 gratis/mes |
| **Render** | Backend completo | Limitado pero útil |
| **Cloudflare Pages** | Frontend + Workers | Muy generoso |
| **Fly.io** | Apps completas | Tier gratis |

---

## 🐳 Docker (intermedio)

Empaqueta tu app para que corra igual en cualquier lado.

- 📺 [Docker desde cero - Fazt](https://www.youtube.com/watch?v=4Dko5W96WHg)
- 📖 [docker.com](https://docs.docker.com/)

### Comandos básicos
```bash
docker build -t mi-app .
docker run -p 3000:3000 mi-app
docker ps
docker stop <id>
```

---

## ⚙️ CI/CD con GitHub Actions

Automatizá: tests, deploy, etc.

```yaml
# .github/workflows/test.yml
name: Tests
on: [push]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: npm install
      - run: npm test
```

---

## ☁️ Conceptos de DevOps

- **CI/CD** — integración y despliegue continuo
- **Contenedores** — Docker, Kubernetes
- **Cloud providers** — AWS, GCP, Azure
- **Serverless** — funciones sin servidor (Lambda, Vercel Functions)
- **Monitoring** — Sentry, Datadog, Grafana

---

## 🎯 Tareas para esta sección

1. ✅ Crear cuenta de GitHub
2. ✅ Subir tu primer repo
3. ✅ Hacer un README bonito
4. ✅ Deployar algo en Vercel
5. ✅ Hacer un Pull Request a un proyecto open source

---

## ⏭️ Siguiente paso

[07-IA-y-Prompt-Engineering](../07-IA-y-Prompt-Engineering/) — la habilidad MÁS importante del dev moderno.
