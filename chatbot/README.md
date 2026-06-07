# 🧠 Local RAG Chatbot with Ollama

A lightweight Retrieval-Augmented Generation (RAG) chatbot built entirely in Python using Ollama, local embeddings, and vector similarity search.

---

## ✨ Features

* 🔍 Semantic search using embedding vectors
* 🧠 Retrieval-Augmented Generation (RAG)
* 📚 Local knowledge base from text files
* ⚡ Fast cosine similarity retrieval
* 🏠 Fully local execution with Ollama
* 🔒 No external API keys required
* 🌊 Streaming LLM responses
* 🐍 Pure Python implementation

---

## 🏗️ Architecture

```text
User Question
      │
      ▼
Generate Query Embedding
      │
      ▼
Compare Against Stored Embeddings
      │
      ▼
Retrieve Most Relevant Chunks
      │
      ▼
Inject Context Into Prompt
      │
      ▼
Generate Answer Using LLM
      │
      ▼
Stream Response To User
```

---

## 📂 Project Structure

```text
.
├── chatbot.py
├── cat-facts.txt
├── README.md
└── requirements.txt
```

---

## 🚀 Models Used

### Embedding Model

```python
hf.co/CompendiumLabs/bge-base-en-v1.5-gguf
```

### Language Model

```python
hf.co/bartowski/Llama-3.2-1B-Instruct-GGUF
```

---

## ⚙️ Installation

### Install Ollama

```bash
ollama --version
```

### Pull Required Models

```bash
ollama pull hf.co/CompendiumLabs/bge-base-en-v1.5-gguf
```

```bash
ollama pull hf.co/bartowski/Llama-3.2-1B-Instruct-GGUF
```

### Install Dependencies

```bash
pip install ollama
```

---

## 📖 Example Usage

```bash
python chatbot.py
```

Example:

```text
Ask me a question:
Why do cats sleep so much?

Retrieved knowledge:
- Cats sleep for around 13–16 hours a day.

Chatbot response:
Cats sleep for around 13–16 hours a day because...
```

---

## 🧠 How It Works

1. Load text data from a local file
2. Generate embeddings for every chunk
3. Store embeddings in an in-memory vector database
4. Convert the user query into an embedding
5. Compute cosine similarity scores
6. Retrieve the most relevant chunks
7. Send retrieved context to the LLM
8. Stream the generated response

