# Multiuser RAG Chatbot
This project is a **multi-user chatbot** powered by a **Retrieval-Augmented Generation (RAG)** pipeline. Users can upload their own documents (PDF, TXT, DOCX, CSV, etc.) and chat with an LLM that answers queries based solely on the uploaded content.



https://github.com/user-attachments/assets/ab600231-50b0-415f-a41c-83bcfca97393



## Features
- Upload multiple documents (PDF, DOCX, TXT, CSV)
- Ask natural language questions based on uploaded content
- Uses LangChain with **Ollama** LLMs
- Supports multi-user sessions with isolated vector stores
- Web UI built with **Gradio**
- Fast document indexing with **ChromaDB**
- Embeddings via `nomic-embed-text` (Ollama)


## Tech Stack

| Component       | Technology                     |
|----------------|---------------------------------|
| Backend LLM     | [Ollama](https://ollama.com)   |
| Framework       | LangChain                      |
| Embeddings      | nomic-embed-text (Ollama)      |
| Vector DB       | Chroma                         |
| Interface       | Gradio                         |
| File Parsing    | PyMuPDF, unstructured, pandas  |

## Folder Structure
<img width="338" height="169" alt="Screenshot 2025-07-11 at 4 27 11 PM" src="https://github.com/user-attachments/assets/9904bea6-c695-4a7b-85e9-31cdf3183b46" />

## Setup

1. Clone the repository
```bash
git clone https://github.com/Jai-Ritvik/Multiuser-Chatbot.git
```
2. Go to the project directory
```bash
cd Multiuser-Chatbot
```

3. Create and Activate a Virtual Environment:
```bash
python -m venv venv
source venv/bin/activate
```
> Note: On Windows, use: venv\Scripts\activate

4. Install Dependencies
```bash
pip install -r requirements.txt
```

5. Run
```bash
python multiuser-chatbot.py
```

## How It Works?
1. Documents are parsed and chunked using RecursiveCharacterTextSplitter.
2. Chunks are embedded with OllamaEmbeddings using nomic-embed-text.
3. ChromaDB stores the vectorized content per user session.
4. Questions are passed to the LLM.
5. Only answers based on document context are allowed.
