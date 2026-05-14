# 🚀 Templates / Starters

> Comandos para arrancar un proyecto en 30 segundos. Probados, actualizados a 2026.

---

## 🟢 Para principiantes

### HTML / CSS / JS puro
```bash
mkdir mi-proyecto && cd mi-proyecto
touch index.html style.css script.js
code .
```

O usá un starter listo:
```bash
npx create-vite mi-proyecto --template vanilla
cd mi-proyecto
npm install
npm run dev
```

### React desde cero (Vite)
```bash
npm create vite@latest mi-app -- --template react-ts
cd mi-app
npm install
npm run dev
```

---

## 🟡 Frontend moderno

### Next.js 15 + TypeScript + Tailwind
```bash
npx create-next-app@latest mi-app \
  --typescript \
  --tailwind \
  --eslint \
  --app \
  --src-dir \
  --import-alias "@/*"

cd mi-app
npm run dev
```

### Next.js + Shadcn/ui (UI hermosa de una)
```bash
npx create-next-app@latest mi-app --typescript --tailwind --app
cd mi-app
npx shadcn@latest init
npx shadcn@latest add button card input
```

### Astro (sitio web rápido)
```bash
npm create astro@latest mi-sitio
```

### Vite + React + TS + Tailwind manual
```bash
npm create vite@latest mi-app -- --template react-ts
cd mi-app
npm install -D tailwindcss@latest postcss autoprefixer
npx tailwindcss init -p
npm install
```

---

## 🟠 Backend

### Node.js + Express (clásico)
```bash
mkdir api && cd api
npm init -y
npm install express
npm install -D @types/node @types/express typescript tsx nodemon
npx tsc --init
```

`src/index.ts`:
```typescript
import express from 'express';
const app = express();
app.get('/', (req, res) => res.json({ hello: 'mundo' }));
app.listen(3000, () => console.log('http://localhost:3000'));
```

### Node.js + Hono (moderno y rápido)
```bash
npm create hono@latest mi-api
cd mi-api
npm install
npm run dev
```

### Python + FastAPI
```bash
mkdir api && cd api
python3 -m venv venv
source venv/bin/activate
pip install fastapi uvicorn[standard]
```

`main.py`:
```python
from fastapi import FastAPI
app = FastAPI()

@app.get("/")
def root():
    return {"hello": "mundo"}
```

Correr: `uvicorn main:app --reload`

### Bun (todo-en-uno ultra rápido)
```bash
bun create hono mi-api
cd mi-api
bun install
bun run dev
```

---

## 🔴 Full-stack

### T3 Stack (Next.js + tRPC + Prisma + NextAuth)
```bash
npm create t3-app@latest mi-app
```

### Next.js + Drizzle + Postgres + Clerk
```bash
npx create-next-app@latest mi-app --typescript --tailwind --app
cd mi-app
npm install drizzle-orm pg @clerk/nextjs
npm install -D drizzle-kit @types/pg
```

### Remix
```bash
npx create-remix@latest mi-app
```

### SvelteKit
```bash
npm create svelte@latest mi-app
```

---

## 📱 Mobile

### Expo (React Native)
```bash
npx create-expo-app mi-app
cd mi-app
npx expo start
```

Escaneás el QR con la app **Expo Go** en tu celu → corre sin compilar.

### Expo + Router + NativeWind
```bash
npx create-expo-app@latest mi-app --template tabs
cd mi-app
npx expo install nativewind tailwindcss
```

### Flutter
```bash
flutter create mi_app
cd mi_app
flutter run
```

---

## 🤖 Apps con IA

### Chatbot con Vercel AI SDK
```bash
npx create-next-app@latest mi-chat --typescript --tailwind --app
cd mi-chat
npm install ai @ai-sdk/anthropic
```

Crear `.env.local`:
```
ANTHROPIC_API_KEY=tu-key
```

`app/api/chat/route.ts`:
```typescript
import { anthropic } from '@ai-sdk/anthropic';
import { streamText } from 'ai';

export async function POST(req: Request) {
  const { messages } = await req.json();
  const result = streamText({
    model: anthropic('claude-sonnet-4-6'),
    messages,
  });
  return result.toDataStreamResponse();
}
```

---

## 🎮 Game Dev

### Godot 4
1. Descargá: https://godotengine.org/download
2. Es UN solo binario, abrilo
3. New Project → 2D o 3D → Create

### Phaser.js (juego web)
```bash
npm create vite@latest mi-juego -- --template vanilla-ts
cd mi-juego
npm install phaser
```

### Bevy (Rust)
```bash
cargo new mi-juego
cd mi-juego
cargo add bevy
```

---

## 🐳 Docker básico

`Dockerfile`:
```dockerfile
FROM node:22-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

`docker-compose.yml`:
```yaml
services:
  app:
    build: .
    ports:
      - "3000:3000"
  db:
    image: postgres:16
    environment:
      POSTGRES_PASSWORD: secret
    ports:
      - "5432:5432"
```

Correr: `docker compose up`

---

## 🚢 Deploy en 1 comando

### Vercel
```bash
npx vercel
```

### Cloudflare Pages
```bash
npx wrangler pages deploy ./dist
```

### Railway
```bash
npm install -g @railway/cli
railway login
railway up
```

---

## 📂 Estructura recomendada de proyecto

```
mi-app/
├── public/              # archivos estáticos
├── src/
│   ├── app/             # Next.js App Router
│   ├── components/      # componentes UI
│   │   └── ui/          # primitivos (shadcn)
│   ├── lib/             # utilities
│   ├── hooks/           # custom hooks
│   ├── server/          # server-side code
│   └── types/           # TypeScript types
├── .env.local           # secrets (gitignored)
├── .env.example         # plantilla pública
├── .gitignore
├── README.md
├── package.json
└── tsconfig.json
```

---

## 🛡️ Setup esencial de TODO proyecto

### .gitignore base
```gitignore
# Sistema
.DS_Store
Thumbs.db

# IDEs
.vscode/
.idea/

# Dependencies
node_modules/
venv/
.venv/

# Env
.env
.env.local
.env.*.local

# Build
dist/
build/
.next/
out/

# Logs
*.log
npm-debug.log*
```

### README.md inicial
```markdown
# Nombre del Proyecto

> Descripción en 1 línea.

## Stack
- Tech 1
- Tech 2

## Setup
\`\`\`bash
git clone <url>
cd proyecto
npm install
cp .env.example .env.local
npm run dev
\`\`\`

## Scripts
- `npm run dev` — desarrollo
- `npm run build` — producción
- `npm test` — tests
```
