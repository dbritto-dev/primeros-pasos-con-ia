---
theme: default
title: IA 101 - Primeros Pasos con Inteligencia Artificial
info: Tu guía para entender y usar IA
highlighter: shiki
transition: slide-left
mdc: true
---

# IA 101

## Primeros Pasos con Inteligencia Artificial

Tu guía para entender y usar IA

---

# Agenda

1. **Conceptos Básicos** — Qué es la IA, ML y Deep Learning
2. **Términos Importantes** — El vocabulario clave
3. **Tipos de Modelos** — Non-thinking vs Thinking
4. **Capacidades de Modelos** — Embedding, Vision, Tools, Thinking
5. **Ollama y Herramientas** — Corre modelos localmente
6. **Tips y Mejores Prácticas** — Qué hacer y qué NO hacer
7. **Q&A** — Preguntas y respuestas

---
layout: section
---

# Conceptos Básicos

---
layout: two-cols-header
---

# ¿Qué es la Inteligencia Artificial?

La IA es la capacidad de una máquina para realizar tareas que normalmente requieren inteligencia humana.

::left::

### 🤖 Inteligencia Artificial

Campo amplio: visión, lenguaje, robótica, planificación, sistemas expertos...

### 📊 Machine Learning

Subconjunto de IA: algoritmos que aprenden de datos sin programación explícita.

::right::

### 🧠 Deep Learning

Subconjunto de ML: redes neuronales profundas (GPT, DALL·E, Whisper).

### 🧠 Deep Learning

ChatGPT, Claude, Llama... son modelos de Deep Learning entrenados con cantidades masivas de texto.

::bottom::

🧠 Deep Learning > 🧠 Deep Learning > 📊 Machine Learning > 🤖 Inteligencia Artificial

---

# ¿Qué es un LLM?

**Large Language Model** — un modelo entrenado con enormes cantidades de texto para entender y generar lenguaje.

| Etapa                      | Descripción                     |
| -------------------------- | ------------------------------- |
| **Datos de entrenamiento** | Libros, web, código, papers     |
| **Proceso**                | GPUs durante semanas o meses    |
| **Resultado**              | Miles de millones de parámetros |
| **Output**                 | Texto, código, análisis         |

**Ejemplos:** `GPT-4o` · `Claude` · `Gemini` · `Llama 3` · `Mistral` · `DeepSeek` · `Qwen`

---
layout: section
---

# Términos Importantes

---

# Términos Importantes

| Término            | Definición                                                                      |
| ------------------ | ------------------------------------------------------------------------------- |
| **Prompt**         | La instrucción que le das al modelo. Calidad del prompt = calidad de respuesta. |
| **Token**          | Unidad mínima de texto que procesa un LLM. Una palabra ≈ 1-3 tokens.            |
| **Context Window** | Máximo de tokens que un modelo puede procesar en una conversación.              |
| **Temperature**    | Controla la creatividad. Bajo (0) = preciso. Alto (1+) = más creativo.          |
| **Alucinación**    | Información falsa generada con confianza. Uno de los mayores riesgos.           |

---

# Más Términos Clave

| Término           | Definición                                                          |
| ----------------- | ------------------------------------------------------------------- |
| **Fine-tuning**   | Re-entrenar un modelo con datos específicos para especializarlo.    |
| **RAG**           | Conectar el modelo a fuentes externas para respuestas más precisas. |
| **Embedding**     | Representación numérica de texto como vectores. Búsqueda semántica. |
| **Inferencia**    | Usar un modelo entrenado para generar respuestas.                   |
| **System Prompt** | Instrucciones iniciales que definen el comportamiento del modelo.   |

---
layout: section
---

# Tipos de Modelos

---
layout: two-cols
---

# 💬 Non-thinking

Responden directamente sin razonamiento interno explícito.

Incluye modelos base (completan texto) e instruct (siguen instrucciones vía RLHF/DPO).

Rápidos y los más usados para chat y generación de contenido.

**Ejemplos:** GPT-4o, Claude Sonnet, Llama 3 Instruct, Mistral

::right::

# 🧠 Thinking

Razonan paso a paso (cadena de pensamiento) antes de dar la respuesta final.

Más lentos pero superiores en lógica, matemáticas, código complejo y análisis profundo.

**Ejemplos:** o1/o3, Claude Opus, DeepSeek-R1, QwQ

---

# Versus: Non-thinking vs Thinking

| Característica    | Non-thinking                   | Thinking                                        |
| ----------------- | ------------------------------ | ----------------------------------------------- |
| **Velocidad**     | ⚡️ Rápido                      | 🐢 Más lento — razona antes                     |
| **Razonamiento**  | Coincidencia de patrones       | Cadena de pensamiento paso a paso               |
| **Instrucciones** | Sigue instrucciones directas   | Entiende qué necesitas, aun si no lo dices bien |
| **Matemáticas**   | Falla en problemas multi-paso  | Excelente en problemas complejos                |
| **Código**        | Fragmentos simples             | Refactorizaciones y arquitectura                |
| **Costo**         | Más barato, menos VRAM         | Más costoso, más VRAM                           |
| **Cuándo usarlo** | Tareas rutinarias, chat rápido | Análisis profundo, depuración compleja          |

---

# Capacidades de Modelos

Se pueden filtrar en plataformas como Ollama:

| Capacidad     | Qué hace                                                                    | Modelos ejemplo                         |
| ------------- | --------------------------------------------------------------------------- | --------------------------------------- |
| **Embedding** | Convierte texto en vectores numéricos. Búsqueda semántica, RAG, agrupación. | `nomic-embed-text`, `mxbai-embed-large` |
| **Vision**    | Procesa imágenes además de texto. OCR, analizar gráficos, revisión de UI.   | `llava`, `llama3.2-vision`, `moondream` |
| **Tools**     | Invoca funciones externas (APIs, bases de datos). Agentes autónomos.        | `llama3.1`, `mistral`, `qwen2.5`        |
| **Thinking**  | Razona paso a paso antes de responder. Lógica compleja, código avanzado.    | `deepseek-r1`, `qwq`, `phi4-reasoning`  |

---
layout: section
---

# Ollama y Herramientas

---
layout: two-cols
---

# ollama.com: IA Local

Corre modelos en tu computadora — sin APIs, sin internet, sin suscripciones.

- 🔒 **Privado** — Datos nunca salen de tu máquina
- 💰 **Gratis** — Sin costos de API
- ⚡ **Simple** — Un comando para correr
- 📦 **Ecosistema** — Llama 3, Mistral, DeepSeek, Phi...

::right::

### Primeros Pasos

```bash
# Instalar
curl -fsSL https://ollama.com/install.sh | sh

# Descargar un modelo
ollama pull llama3.2

# Chatear
ollama run llama3.2
```

También disponible para Mac y Windows.

---

# canirun.ai — ¿Puede mi PC correr este modelo?

Analiza tu hardware desde el navegador (sin enviar datos a ningún servidor).

| Qué analiza         | Detalle                                                                                |
| ------------------- | -------------------------------------------------------------------------------------- |
| **GPU / VRAM**      | La memoria de tu GPU determina qué modelos caben. Apple Silicon usa memoria unificada. |
| **RAM del sistema** | Un modelo 7B en 4-bit necesita ~4GB. Un 70B puede requerir 40GB+.                      |
| **Ancho de banda**  | La velocidad de memoria (GB/s) determina los tokens por segundo.                       |

---
layout: section
---

# Tips y Mejores Prácticas

---

# ✅ Qué HACER al trabajar con IA

| Tip                         | Ejemplo                                                                       |
| --------------------------- | ----------------------------------------------------------------------------- |
| **Sé específico**           | "Escribe un email profesional para declinar una reunión" > "escribe un email" |
| **Da contexto y rol**       | "Actúa como un senior developer revisando este código en Python 3.12..."      |
| **Itera y refina**          | No esperes perfección al primer intento. Ajusta, pide cambios.                |
| **Verifica la información** | Siempre valida datos, cifras y código. La IA puede equivocarse con confianza. |
| **Usa ejemplos**            | Muestra 2-3 ejemplos del formato o estilo que esperas.                        |
| **Divide tareas complejas** | En vez de un mega-prompt, divide en pasos: primero planifica, luego ejecuta.  |

---

# ❌ Qué NO HACER al trabajar con IA

| Tip                              | Por qué                                                                  |
| -------------------------------- | ------------------------------------------------------------------------ |
| **No confíes ciegamente**        | La IA alucina. Siempre verifica información crítica.                     |
| **No compartas datos sensibles** | Evita contraseñas, tokens o datos de clientes en chats de IA en la nube. |
| **No uses prompts vagos**        | "Ayúdame con mi código" no da contexto. Sé preciso sobre el error.       |
| **No ignores el contexto**       | Sin contexto adecuado, las respuestas serán genéricas.                   |
| **No copies sin entender**       | Especialmente código: entiende qué hace antes de implementarlo.          |
| **No reemplaces tu criterio**    | La IA es herramienta, no sustituto. Tu expertise sigue siendo esencial.  |

---
layout: section
---

# Demo

---
layout: center
class: text-center
---

# Q & A

¿Preguntas? ¿Dudas? ¿Ideas?

_Gracias por asistir_ 🎉
