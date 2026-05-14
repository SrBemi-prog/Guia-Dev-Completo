# 14 — Cloud y Serverless

> Donde corre todo el internet moderno.

## ☁️ Los 3 grandes (Big Cloud)

| Cloud | Fuerte en | Curva de aprendizaje |
|-------|-----------|----------------------|
| **AWS** (Amazon) | Todo. El más grande | Empinada |
| **GCP** (Google) | IA, BigData, Kubernetes | Media |
| **Azure** (Microsoft) | Empresas, integración Microsoft | Empinada |

> **Para arrancar:** No te tires a AWS de una. Empezá con Vercel/Railway/Cloudflare, después subís a AWS si lo necesitás.

---

## 🚀 Plataformas modernas (más fáciles)

### Vercel
- Optimizada para Next.js
- Deploy con `git push`
- Funciones serverless
- Edge network global
- 🔗 https://vercel.com/

### Cloudflare
- Cloudflare Workers (serverless ultra rápido)
- R2 (storage barato)
- D1 (SQLite en edge)
- Pages (hosting estático)
- 🔗 https://cloudflare.com/

### Railway
- Apps + BD en un solo lugar
- Estilo Heroku moderno
- $5 gratis/mes
- 🔗 https://railway.app/

### Fly.io
- Apps cerca de tus usuarios (edge)
- Postgres incluido
- 🔗 https://fly.io/

### Render
- Similar a Railway
- Web services + cron jobs
- 🔗 https://render.com/

---

## ⚡ Serverless / Functions

**Idea:** subís código → corre solo cuando se necesita → pagás por uso.

### Funciones
- **AWS Lambda** — el clásico
- **Cloudflare Workers** — más rápido, JS/TS
- **Vercel Functions** — integrado con Next.js
- **Deno Deploy** — TypeScript serverless

### Bases de datos serverless
- **Neon** — Postgres
- **PlanetScale** — MySQL
- **Turso** — SQLite distribuido
- **DynamoDB** — NoSQL AWS

---

## 📚 Recursos para aprender AWS

- 📺 [AWS desde cero - HolaMundo](https://www.youtube.com/@HolaMundoDev/search?query=AWS+desde+cero)
- 📖 [AWS Free Tier](https://aws.amazon.com/free/)
- 📖 [AWS Skill Builder](https://skillbuilder.aws/) (cursos gratis)
- 🎓 [acloud.guru](https://acloudguru.com/) (paga, pero el mejor)

### Servicios AWS clave para devs
- **S3** — storage
- **EC2** — servidores virtuales
- **Lambda** — funciones serverless
- **RDS** — bases de datos
- **CloudFront** — CDN
- **Route 53** — DNS
- **IAM** — permisos (esencial)

---

## 🔐 Conceptos clave de Cloud

- **IaaS / PaaS / SaaS** — niveles de abstracción
- **Region / AZ** — donde corre tu app
- **VPC** — red privada virtual
- **CDN** — servidores cercanos al usuario
- **Auto-scaling** — más servidores cuando hay tráfico
- **Load balancer** — distribuir tráfico
- **CI/CD** — deploy automático
- **IaC** (Infrastructure as Code) — Terraform, Pulumi

---

## 🐳 Containers + Kubernetes

### Docker
- Empaquetar app + dependencias
- Corre igual en todos lados

### Kubernetes (K8s)
- Orquestar muchos containers
- Auto-healing, scaling
- 📺 [K8s en español - HolaMundo](https://www.youtube.com/@HolaMundoDev/search?query=K8s+en+espa%C3%B1ol)

> **Cuándo aprenderlo:** Solo si trabajás en empresas grandes. Para indie/startup, suele ser overkill.

---

## 🛠️ Infrastructure as Code (IaC)

Definí tu infra en código.

- **Terraform** — el más usado
- **Pulumi** — IaC con TS/Python
- **AWS CDK** — IaC en código nativo
- **SST** — IaC moderno para apps web

---

## 🎯 Proyectos para practicar

1. Deployar una app Next.js a Vercel
2. Crear un Worker en Cloudflare que responde JSON
3. Subir una imagen a S3 y mostrarla
4. App con Postgres en Neon + auth con Clerk
5. Workflow CI/CD que testea + deploya
6. Función Lambda que procesa un webhook
