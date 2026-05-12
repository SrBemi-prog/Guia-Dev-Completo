# 17 — Data Science y Machine Learning

> Programar para extraer conocimiento de datos.

## 🎯 Las 3 carreras de datos

| Rol | Qué hace |
|-----|---------|
| **Data Analyst** | SQL + Excel + dashboards. Reportes para negocio |
| **Data Engineer** | Pipelines, ETL, infraestructura de datos |
| **Data Scientist** | Modelos, estadística, ML |
| **ML Engineer** | Pone modelos en producción |
| **AI Researcher** | Crea modelos nuevos (papers) |

---

## 🐍 Stack base: Python

### Librerías que SÍ o SÍ tenés que conocer

| Librería | Para qué |
|----------|---------|
| **NumPy** | Operaciones matemáticas en arrays |
| **Pandas** | Manipular dataframes (tipo Excel) |
| **Matplotlib / Seaborn** | Gráficos |
| **Plotly** | Gráficos interactivos |
| **Scikit-learn** | Machine Learning clásico |
| **PyTorch** ⭐ | Deep Learning (lo usa todo el mundo en 2026) |
| **TensorFlow / Keras** | DL alternativa |
| **Jupyter** | Notebooks para experimentar |

```python
import pandas as pd
df = pd.read_csv('ventas.csv')
df.groupby('mes')['monto'].sum().plot()
```

---

## 📺 Cursos recomendados

### Empezar
- 📺 [Curso Python para Data Science - HolaMundo](https://www.youtube.com/watch?v=8Aj6OnH9PJI)
- 📺 [Pandas - codebasics (inglés)](https://www.youtube.com/playlist?list=PLeo1K3hjS3uuASpe-1LjfG5f14Bnozjwy)
- 📖 [Kaggle Learn](https://www.kaggle.com/learn) ⭐ — mini cursos gratis muy buenos

### ML / Deep Learning
- 📺 [Andrew Ng - Machine Learning (Coursera)](https://www.coursera.org/learn/machine-learning) — el clásico
- 📺 [DeepLearning.AI Short Courses](https://www.deeplearning.ai/short-courses/) ⭐ gratis
- 📺 [3Blue1Brown - Neural Networks](https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi) — visualizaciones únicas
- 📺 [fast.ai Practical Deep Learning](https://course.fast.ai/) — práctico, gratis
- 📺 [Karpathy - Neural Networks Zero to Hero](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ) ⭐⭐⭐

### Mathematics for ML
- 📖 [Mathematics for Machine Learning](https://mml-book.github.io/) — gratis, PDF

---

## 🤖 El stack de IA moderno (2026)

### Para usar modelos
- **Hugging Face** — biblioteca de modelos
- **Ollama** — correr LLMs local
- **LM Studio** — GUI para LLMs local
- **vLLM** — inference rápida

### Para apps con IA
- **LangChain / LangGraph** — orquestación
- **LlamaIndex** — RAG
- **Mastra** — agentes en TS
- **Vercel AI SDK** — IA en apps web

### Bases de datos vectoriales
- **Pinecone** — managed
- **Qdrant** — open source
- **Weaviate** — open source
- **pgvector** — Postgres extension
- **Chroma** — local

### Plataformas de inferencia
- **Anthropic API** (Claude)
- **OpenAI API**
- **Google Gemini API**
- **Groq** — ultra rápido
- **Together AI / Replicate** — modelos open

---

## 📊 SQL para Data

Tan o más importante que Python.

```sql
SELECT
  categoria,
  AVG(precio) as precio_promedio,
  COUNT(*) as cantidad
FROM productos
WHERE stock > 0
GROUP BY categoria
ORDER BY precio_promedio DESC;
```

---

## 🛠️ Herramientas del trade

### Notebooks
- **Jupyter Lab**
- **Google Colab** ⭐ — gratis, con GPU
- **Kaggle Notebooks** — gratis con GPU
- **VS Code + Python extension**

### Visualización profesional
- **Tableau / Power BI** — para empresa
- **Streamlit** — apps de datos rapido
- **Gradio** — demos de ML
- **Observable** — dataviz web

### Big Data
- **Spark** — distribuido
- **dbt** — transformaciones SQL
- **Airflow** — orquestación de pipelines
- **Snowflake / BigQuery** — data warehouses

---

## 🎯 Proyectos para portfolio

### Análisis
1. **EDA de un dataset de Kaggle** — Titanic, COVID, etc.
2. **Dashboard de tus gastos** — leer CSVs del banco
3. **Análisis de tu Spotify** — usar API

### Machine Learning
4. **Predictor de precios** (casas, autos)
5. **Clasificador de spam**
6. **Recomendador de películas**
7. **Detector de fraudes**

### Deep Learning
8. **Clasificador de imágenes** (perros vs gatos)
9. **Generador de texto** (con LLM pequeño)
10. **Análisis de sentimientos** en reviews

### Apps con IA (lo MÁS de moda en 2026)
11. **Chatbot personalizado con RAG** sobre tus PDFs
12. **Agente que automatiza emails**
13. **Generador de imágenes** usando APIs
14. **Buscador semántico** de documentos

---

## 🏅 Kaggle (la red social de data scientists)

- Competiciones reales
- Datasets gratis
- Notebooks de otros
- Plata real en algunas competencias
- 🔗 https://www.kaggle.com/

---

## 🎓 Camino sugerido

```
SQL básico  →  Python + Pandas  →  Estadística básica  →
Scikit-learn  →  Deep Learning (PyTorch)  →  LLMs + LangChain
```

Mes 1-2: SQL + Pandas
Mes 3-4: Stats + ML clásico
Mes 5-6: Deep Learning
Mes 7+: especialización (NLP, CV, RL, LLMs)
