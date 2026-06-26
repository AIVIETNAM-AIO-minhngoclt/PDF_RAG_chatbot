# PDF RAG Chatbot

A local Retrieval-Augmented Generation (RAG) chatbot that answers questions based on the content of any PDF document. Built with Python, Streamlit, ChromaDB, and Ollama — no internet or API keys required.

## How it works

1. **Upload** a PDF document
2. The app splits the text into chunks, converts them into vectors, and stores them in a local vector database
3. When you ask a question, the app finds the most relevant chunks and passes them to an LLM to generate an accurate answer

```
PDF → Chunking → Embedding → ChromaDB
                                 ↓
Question → Embedding → Search → Relevant Chunks → LLM → Answer
```

## Requirements

- Python 3.10+
- [Ollama](https://ollama.com) installed and running

## Setup

**1. Clone the repository**
```bash
git clone https://github.com/your-username/RAG_chatbot.git
cd RAG_chatbot
```

**2. Install Python dependencies**
```bash
pip install -r requirements.txt
```

**3. Pull the required Ollama models**
```bash
ollama pull bge-m3
ollama pull mistral
```

**4. Run the app**
```bash
streamlit run app.py
```

Open your browser at `http://localhost:8501`.

## Usage

1. Upload a PDF using the sidebar
2. Click **"Process PDF"** and wait for indexing to finish
3. Type your question in the chat box
4. Click **"Clear chat history"** to start a new conversation

## Tech Stack

| Component | Tool |
|---|---|
| UI | Streamlit |
| PDF parsing | pypdf |
| Embedding model | bge-m3 (via Ollama) |
| Vector database | ChromaDB |
| LLM | Mistral (via Ollama) |

## Project Structure

```
RAG_chatbot/
├── app.py            # Main application
├── requirements.txt  # Python dependencies
└── README.md
```
