# 07 — IA y Prompt Engineering para Devs

> En 2026, un dev que no usa IA bien es como un escritor que no usa procesador de texto.

## 🎯 Objetivos

- [ ] Saber qué IA usar para cada cosa
- [ ] Escribir prompts efectivos
- [ ] Usar IA como **par programador**, no como reemplazo del pensamiento
- [ ] Entender los límites: alucinaciones, contexto, costos

---

## 🤖 Las herramientas que tenés que conocer

### 1. Chats (asistentes generales)

| IA | Mejor para | Precio |
|----|-----------|--------|
| **Claude** (Anthropic) | Código largo, razonamiento, escritura | Gratis + paga |
| **ChatGPT** (OpenAI) | Multipropósito, imágenes | Gratis + paga |
| **Gemini** (Google) | Integración con Google, búsqueda | Gratis + paga |
| **DeepSeek** | Open source, gratis, muy bueno | Gratis |

### 2. IDEs con IA integrada ⭐

| Herramienta | Qué hace |
|-------------|---------|
| **Claude Code** | CLI agéntico, ejecuta tareas completas |
| **Cursor** | VS Code con IA integrada — el más usado |
| **Windsurf** | Alternativa a Cursor |
| **GitHub Copilot** | Autocompletado de código |
| **Zed** | Editor moderno con IA |

### 3. Para diseño / UI

- **v0.dev** (Vercel) — genera componentes React
- **Bolt.new** — apps completas desde un prompt
- **Lovable** — apps full-stack con IA
- **Midjourney / DALL-E** — imágenes

---

## ✍️ Cómo escribir BUENOS prompts

### ❌ Prompt malo
> "Hazme una app"

### ✅ Prompt bueno
> "Necesito una app web con React + Tailwind que liste tareas. Cada tarea tiene título, descripción, fecha y estado (pendiente/completada). Guardar en localStorage. Diseño minimalista en oscuro. Mostrame primero la estructura de componentes antes de escribir código."

### Las 6 reglas del prompt efectivo

1. **Contexto** — ¿Para qué? ¿Qué tecnología?
2. **Tarea específica** — Qué querés que haga, paso a paso
3. **Restricciones** — Qué NO debe hacer
4. **Formato esperado** — ¿Código? ¿Lista? ¿Explicación?
5. **Ejemplos** — Si podés, mostrale qué esperás
6. **Iterá** — La primera respuesta nunca es la final

---

## 🎓 Cursos de IA y prompts

- 📺 [Prompt Engineering - DotCSV](https://www.youtube.com/@DotCSV)
- 📖 [Anthropic Prompt Engineering Guide](https://docs.anthropic.com/claude/docs/prompt-engineering)
- 📖 [OpenAI Cookbook](https://cookbook.openai.com/)
- 📺 [Cursor para devs - midudev](https://www.youtube.com/@midudev/search?query=Cursor+para+devs)

---

## 🛠️ Casos de uso reales para devs

### Programando

```
"Soy nuevo en React. Explicame qué hace este código línea por línea:
[pegás el código]
y dame 3 formas alternativas de hacerlo."
```

### Debugging

```
"Este error me aparece: [error]
Acá está el código: [código]
Esperaba que [X] pero pasa [Y].
¿Cuál es la causa? Dame las 3 hipótesis más probables ordenadas."
```

### Aprendiendo

```
"Explicame qué es un closure en JavaScript como si tuviera 10 años,
luego de manera técnica, y dame 3 ejemplos de uso real."
```

### Code review

```
"Revisá este código y dame: 1) bugs, 2) problemas de seguridad,
3) mejoras de performance, 4) cosas que harías diferente.
[código]"
```

---

## 🧠 Construyendo apps CON IA

### APIs principales
- **Anthropic API** (Claude)
- **OpenAI API** (GPT)
- **Google Gemini API**
- **Groq** — inferencia ultra rápida
- **Replicate / HuggingFace** — modelos open source

### Frameworks
- **LangChain** — orquestación de LLMs
- **LlamaIndex** — RAG (búsqueda + LLM)
- **Vercel AI SDK** — IA en apps web fácil
- **Mastra** — agentes en TypeScript

### Conceptos a aprender
- **Tokens** y costos
- **Prompt caching** (clave para apps con IA — abarata enormemente)
- **Tool use / function calling**
- **RAG** (Retrieval Augmented Generation)
- **Agents** (IA que ejecuta tareas)
- **Embeddings** y bases de datos vectoriales (Pinecone, Qdrant, pgvector)

---

## ⚠️ Errores comunes con IA

| ❌ Error | ✅ Solución |
|---------|-----------|
| Copiar código sin entenderlo | Pedile que lo explique y reescribilo vos |
| Confiar ciegamente en lo que dice | Verificar con docs oficiales |
| Pedir todo de una sola vez | Dividir en pasos pequeños |
| No darle contexto | Mostrale archivos, errores, intenciones |
| Usar IA para problemas que ya sabés resolver | No te atrofies, alterná |

---

## 🎯 Proyectos con IA para tu portfolio

1. **Chatbot personalizado** con la API de Claude/OpenAI
2. **Resumidor de PDFs** usando RAG
3. **Buscador semántico** con embeddings
4. **Agente** que automatiza una tarea repetitiva
5. **App full-stack** integrando IA (ej: generador de quizzes)

---

## ⏭️ Siguiente paso

[08-Videos-y-Cursos](../08-Videos-y-Cursos/) — el catálogo completo de recursos.
