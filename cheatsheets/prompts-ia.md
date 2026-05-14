# 🤖 Prompts para IA — Templates probados

> Copy-paste. Reemplazá `[corchetes]` con lo tuyo.

## 🎓 Aprender un concepto nuevo

```
Soy un dev [junior/intermedio] y quiero entender [concepto].

Por favor:
1. Explicámelo como si tuviera 12 años (analogía simple)
2. Después, explicámelo técnicamente
3. Dame 3 ejemplos de uso real
4. ¿Cuándo NO debería usarlo?
5. ¿Cuáles son las trampas más comunes?
```

---

## 🐛 Debugging

```
Estoy intentando hacer [objetivo].

Acá está el código relevante:
[código]

El error que recibo es:
[error completo, stack trace]

Esperaba [comportamiento X] pero pasa [Y].

Cosas que ya probé:
- [intento 1]
- [intento 2]

Dame las 3 hipótesis más probables, ordenadas por probabilidad,
y para cada una explicá cómo verificarla antes de probar el fix.
```

---

## 📝 Code review

```
Revisá este código:
[código]

Dame feedback estructurado:
1. 🐛 Bugs (si los hay)
2. 🔐 Problemas de seguridad
3. ⚡ Mejoras de performance
4. 📖 Legibilidad / mantenibilidad
5. 🎯 Edge cases que no maneja

Prioridad: bugs > seguridad > resto. No me digas obviedades.
```

---

## 🏗️ Arrancar un proyecto nuevo

```
Quiero construir [descripción del proyecto].

Stack que pensé: [React/Next.js/etc] + [BD] + [hosting].

Antes de tocar código:
1. ¿Está bien el stack para este caso? Justificá.
2. Cuáles son los 3-5 componentes/módulos principales?
3. Modelá las tablas/colecciones de la BD.
4. Listame las 5 features mínimas para un MVP.
5. ¿Qué riesgos/problemas anticipás?

NO escribas código todavía. Quiero alinearme en el diseño primero.
```

---

## 🔄 Refactorizar

```
Quiero refactorizar este código:
[código]

Objetivos (en orden):
1. [Legibilidad / performance / testabilidad / etc]
2. [otro]

Restricciones:
- No cambiar la API pública (firma de funciones)
- Mantener compatibilidad con [X]

Mostrame primero el plan de refactor (qué vas a tocar y por qué),
después el código nuevo.
```

---

## 📚 Documentar código

```
Documentá este código:
[código]

Estilo: [JSDoc / docstrings / README]

Incluí:
- Qué hace cada función (1 línea)
- Parámetros con tipos
- Valor de retorno
- Ejemplos de uso (mínimo 2)
- Edge cases o advertencias

No agregues comentarios obvios como "incrementa i en 1".
```

---

## 🧪 Generar tests

```
Generá tests para este código:
[código]

Framework: [Vitest / Jest / pytest]

Cubrí:
1. Happy path (caso normal)
2. Edge cases (vacío, null, números negativos, etc.)
3. Errores esperados
4. Casos límite del dominio del negocio

Apuntá a 80%+ de coverage. Tests claros y aislados.
```

---

## 🌐 Traducir entre lenguajes/stacks

```
Convertí este código de [JavaScript/React] a [Python/Vue]:
[código]

Mantené:
- La misma lógica de negocio
- Los mismos nombres semánticos (adaptados al estilo del lenguaje)

Adaptá:
- A las convenciones idiomáticas del lenguaje destino
- A los paradigmas habituales (no traducción literal)
```

---

## 🎨 Diseñar API

```
Diseñá una API REST para [dominio].

Recursos: [usuarios, productos, etc]

Para cada endpoint dame:
- Método HTTP y path
- Path params / query params
- Body request (con tipos)
- Response (200, 4xx, 5xx)
- Autenticación necesaria

Seguí convenciones REST estándar. Avisame si algún recurso
encaja mejor como GraphQL o WebSocket.
```

---

## 🔍 Explicar código que no entendés

```
No entiendo este código:
[código]

Explicámelo:
1. Línea por línea (las complejas)
2. Cuál es el patrón / concepto que usa
3. Reescribilo en una versión más simple/explícita
4. Mostrame un caso donde fallaría
```

---

## ⚡ Optimizar performance

```
Este código es lento:
[código]

Contexto:
- Se ejecuta [cuántas veces / con qué inputs]
- Tarda actualmente [X ms]
- Objetivo: [Y ms]

Análisis:
1. ¿Cuál es la complejidad actual?
2. Dónde está el cuello de botella probable
3. Plan de optimización (en orden de impacto/esfuerzo)
4. Código optimizado

Antes de proponer cosas exóticas, agotá las opciones simples
(menos llamadas, mejor algoritmo, cache).
```

---

## 📖 Aprender de un repo

```
Quiero entender el repo [URL o descripción].

Por favor:
1. ¿Cuál es el propósito general?
2. Estructura de carpetas: qué hay en cada una
3. Punto de entrada del código (por dónde empezar a leer)
4. Conceptos clave que necesito entender primero
5. ¿Hay patrones inusuales que me van a confundir?
```

---

## 🎯 Decidir entre tecnologías

```
Tengo que elegir entre [A] y [B] para [caso de uso].

Contexto:
- Equipo: [tamaño, experiencia]
- Carga esperada: [X usuarios/mes]
- Plazo: [Y meses]
- Presupuesto: [Z]

Comparalas en:
- Curva de aprendizaje
- Performance
- Ecosistema / comunidad
- Costos
- Riesgos de lock-in

Hacé una recomendación opinionada al final, con el razonamiento.
NO digas "depende" sin pesar los pros y contras.
```

---

## 💼 Preparar entrevista

```
Tengo entrevista de [rol] en [tipo de empresa].
Stack: [React/Node/etc].

Hacé una simulación de entrevista técnica:
1. Hacéme una pregunta de [coding / system design / behavioral]
2. Esperá mi respuesta
3. Hacé preguntas de seguimiento como un entrevistador real
4. Al final, dame feedback honesto sobre mi respuesta

Empezá con una pregunta de dificultad [easy/medium/hard].
```

---

## 🎤 Explicar tu código a otros

```
Tengo que presentar este código a mi equipo:
[código]

Generá:
1. Un resumen ejecutivo (2-3 oraciones)
2. Diagrama de flujo en texto (ASCII art o steps)
3. Las 3 decisiones de diseño más importantes y su justificación
4. Posibles preguntas que me pueden hacer + respuestas
5. Lo que cambiarías si tuvieras más tiempo
```

---

## 🛡️ Auditoría de seguridad

```
Auditá este código pensando en seguridad:
[código]

Buscá:
- SQL injection / NoSQL injection
- XSS (cross-site scripting)
- CSRF
- Manejo inseguro de tokens / secrets
- Validación de input insuficiente
- Logging que filtre datos sensibles
- Race conditions
- Manejo inseguro de archivos

Priorizá críticos. Para cada problema: dame el riesgo + el fix.
```

---

## 💡 Reglas de oro para prompts

1. **Empezá con el rol / contexto** ("Soy un dev junior...")
2. **Decí el objetivo explícito** ("Quiero que X haga Y")
3. **Pegá el código relevante** (no parafraseés)
4. **Especificá el formato esperado** ("dame en bullets", "tabla", "código")
5. **Iterá** — la primera respuesta nunca es la final
6. **Pedile que pregunte** si algo no está claro
7. **No le creas todo** — verificá con docs oficiales

---

## ⚠️ Cosas que evitar

- ❌ "Hazme algo" (sin contexto)
- ❌ "¿Qué opinás de mi código?" (sin pegarlo)
- ❌ Aceptar la primera respuesta sin entenderla
- ❌ Pedir 10 features en un solo prompt
- ❌ Usar IA para algo que ya sabés hacer (no te atrofies)
