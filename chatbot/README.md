🧠 Local RAG Chatbot with Ollama

A lightweight Retrieval-Augmented Generation (RAG) chatbot built entirely in Python using Ollama, local embeddings, and vector similarity search.

This project demonstrates the core concepts behind modern AI assistants such as ChatGPT, Perplexity, and enterprise knowledge bots—without requiring external vector databases or cloud APIs.

✨ Features
🔍 Semantic search using embedding vectors
🧠 Retrieval-Augmented Generation (RAG)
📚 Local knowledge base from text files
⚡ Fast cosine similarity retrieval
🏠 Fully local execution with Ollama
🔒 No external API keys required
🌊 Streaming LLM responses
🐍 Pure Python implementation
🏗️ Architecture
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
📂 Project Structure
.
├── chatbot.py
├── cat-facts.txt
├── README.md
└── requirements.txt
🚀 Models Used
Embedding Model
hf.co/CompendiumLabs/bge-base-en-v1.5-gguf

Used to convert text chunks and user queries into vector embeddings.

Language Model
hf.co/bartowski/Llama-3.2-1B-Instruct-GGUF

Used to generate responses based on retrieved context.

⚙️ Installation
1. Install Ollama

Download and install Ollama:

https://ollama.com

Verify installation:

ollama --version
2. Pull Required Models
ollama pull hf.co/CompendiumLabs/bge-base-en-v1.5-gguf
ollama pull hf.co/bartowski/Llama-3.2-1B-Instruct-GGUF
3. Install Python Dependencies
pip install ollama
📖 Knowledge Base

The chatbot loads information from:

cat-facts.txt

Each line is treated as a separate knowledge chunk.

Example:

Cats sleep for around 13–16 hours a day.
A group of kittens is called a kindle.
Cats can rotate their ears 180 degrees.
🧮 Vector Database

For simplicity, embeddings are stored in memory:

VECTOR_DB = [
    (chunk, embedding),
    ...
]

This makes the project easy to understand while demonstrating the core mechanics of semantic retrieval.

🔍 Retrieval Process

When a user asks a question:

Generate an embedding for the query
Compute cosine similarity against all stored embeddings
Rank chunks by similarity score
Retrieve the top matching results
Inject them into the prompt

Example:

Question:
Why do cats sleep so much?

Retrieved Context:
- Cats sleep for around 13–16 hours a day.
- Cats conserve energy because they are natural predators.
💬 Example Usage
python chatbot.py

Output:

Ask me a question:
Why do cats sleep so much?

Retrieved knowledge:
- (similarity: 0.91) Cats sleep for around 13–16 hours a day.
- (similarity: 0.84) Cats conserve energy because they are predators.

Chatbot response:
Cats sleep for around 13–16 hours a day and conserve energy because they are natural predators.
🧠 Why RAG?

Traditional LLMs:

Question → LLM → Answer

RAG Systems:

Question
    ↓
Retrieve Relevant Knowledge
    ↓
Provide Context
    ↓
LLM Generates Answer

Benefits:

More accurate answers
Uses custom/private data
Reduces hallucinations
Keeps knowledge up to date
No retraining required
