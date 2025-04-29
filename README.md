# Pizza-Review-AI-agent-with-Ollama
An AI-powered question-answering agent that uses real restaurant reviews to answer questions about a pizza restaurant. It combines **LangChain**, **Ollama**, and **ChromaDB** to create a local Retrieval-Augmented Generation (RAG) pipeline.

---

## Overview

This project builds an interactive chatbot that:
- Embeds realistic restaurant reviews using **Ollama embeddings**
- Stores and retrieves them with **Chroma vector database**
- Answers questions using **LLaMA 3.2 model via Ollama**

---

## Key Components

- **Ollama + LangChain**: For LLM inference and embedding generation.
- **ChromaDB**: Persistent vector store for storing and retrieving reviews.
- **Interactive QA Interface**: CLI tool that takes user questions and provides LLM-generated answers based on retrieved reviews.

---

## Project Structure

```
Pizza-Review-AI-agent-with-chromadb/
│
├── realistic_restaurant_reviews.csv  # Dataset of reviews
├── requirements.txt  
├── vector.py         # Builds and loads the Chroma vector DB
├── main.py           # Command-line interface for Q&A
├── chrome_langchain_db/  # Vector store directory (auto-generated)
└── README.md
```

---

## Installation

### 1. Install Python dependencies

```bash
pip install langchain langchain-ollama langchain-chroma pandas
```

### 2. Install and run Ollama

Follow the instructions at: https://ollama.com

Make sure to pull the required models:

```bash
ollama pull llama3:2
ollama pull mxbai-embed-large
```

---

## Usage

Start the agent with:

```bash
python main.py
```

Sample interaction:

```
Ask your question (q to quit): What did customers say about the pizza crust?
```

---

## Notes

- On the first run, the system embeds and stores all reviews in a Chroma vector DB.
- The database is persisted in the `./chrome_langchain_db` directory.
- Subsequent runs load the prebuilt database for fast retrieval.

---

## License

MIT License

---

## 🙌 Credits

- https://www.youtube.com/watch?v=E4l91XKQSgw
- [LangChain](https://www.langchain.com/)
- [Ollama](https://ollama.com/)
- [ChromaDB](https://www.trychroma.com/)
