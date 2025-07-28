# 🧾 Invoice Data Extraction with LLM RAG on CPU

This project is a **local Retrieval-Augmented Generation (RAG)** pipeline built with **LangChain**, **ChromaDB**, and **Ollama** to extract structured information from invoice PDFs using **LLaMA3.2\:latest** running on CPU.

✅ No GPU required.
✅ Entirely offline and private.
✅ Powered by **sentence-transformers** (`all-mpnet-base-v2`) for embeddings and **ChromaDB** for vector storage.

---

## ⚙️ Features

* Upload any **text-based PDF invoice**

* Ask structured or natural language questions like *"What is the invoice number?"* or *"Who is the client?"*

* Built on **LLaMA3.2\:latest** (7B model via Ollama)

* Uses **Sentence Transformers** for semantic chunking and vector similarity

* Full offline support, privacy-preserving, and works on CPU

* UI built with **Streamlit** for PDF upload and querying

---

## 🧪 Tech Stack

* 🧠 **LLM**: [LLaMA3.2\:latest](https://ollama.com/library/llama3) via [Ollama](https://ollama.com)

* 🧲 **Embedding Model**: `sentence-transformers/all-mpnet-base-v2`

* 📚 **LangChain**: For RAG pipeline and chaining

* 📦 **ChromaDB**: Fast and simple vector store

* 📄 **PDF Loader**: LangChain’s PyPDFLoader

* 🎛️ **Streamlit**: UI interface

---

## 🛠️ Setup Instructions

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Install and set up Ollama

Follow instructions at [https://ollama.com](https://ollama.com)
Then pull the model:

```bash
ollama pull llama3:latest
```
---

### 3. Prepare PDF data

Place your **text-based** invoice PDFs in the `data/` directory.

---

### 4. Generate vector store from PDF

```bash
python ingest.py
```

---

### 5. Run the app with question:

```bash
python main.py "What is the client name?"
```

---

## 📁 Folder Structure

```
.
├── data/                # Folder with PDF invoices
├── vectorstore/         # Persisted ChromaDB vectors
├── rag/
│   ├── pipeline.py      # RAG chain builder
├── app.py               # Streamlit interface
├── ingest.py            # PDF to vector processor
├── main.py              # CLI for querying
├── config.yml           # Config settings
├── requirements.txt
```

---

## 📌 Example Query

```bash
python main.py "What is the invoice date?"
```

**Output:**

```json
{
  "invoice_date": "2024-03-18"
}
```

---
