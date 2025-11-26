# 📘 Intelligent Document Search System (Vector Database with FAISS)

An AI-powered **semantic document search system** built using **FAISS**, **SentenceTransformers**, and **Streamlit**.  
This project lets you:

✓ Upload PDFs or text files  
✓ Convert them into embeddings  
✓ Store vectors in a FAISS index  
✓ Perform similarity search  
✓ Optionally use RAG (Retrieval-Augmented Generation) with an LLM like OpenAI  

Perfect for learning vector databases, similarity search, and real-world GenAI pipelines.

---

## 🚀 Features

- Document ingestion (PDF / TXT)
- Text chunking with overlap
- Embedding generation using `all-MiniLM-L6-v2`
- FAISS vector index storage & retrieval
- Streamlit frontend for:
  - Uploading documents
  - Running semantic search
  - (Optional) RAG answer generation with OpenAI
- Simple metadata storage (JSON)
- Fully local search (no cloud required)

---

## 🗂 Project Structure

```
vector-search-faiss/
├─ README.md
├─ requirements.txt
├─ build_index.py
├─ app.py
├─ utils.py
├─ data/           # put your PDFs / TXT files here
└─ store/          # FAISS index + metadata will be stored here
```

---

## ⚙️ Installation

### 1️⃣ Clone the repository
```
git clone https://github.com/your-username/vector-search-faiss.git
cd vector-search-faiss
```

### 2️⃣ Create a virtual environment (recommended)
```
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
```

### 3️⃣ Install dependencies
```
pip install -r requirements.txt
```

---

## 📥 Add Documents

Put your files into:
```
./data/
```

Supports:
- `.pdf`
- `.txt`

---

## 🏗 Build the FAISS Index

Run:
```
python build_index.py --data_dir ./data --store_dir ./store
```

This will:

- Extract text  
- Chunk text  
- Generate embeddings  
- Build FAISS index  
- Save metadata  

---

## 🖥 Run the Streamlit App

```
streamlit run app.py
```

Then open the local URL shown in the terminal.

---

## 🔍 How Semantic Search Works

1. Upload documents  
2. System extracts + chunks text  
3. SentenceTransformer converts each chunk → embedding  
4. FAISS stores embeddings in vector index  
5. At query time:
   - Convert user query → embedding  
   - Search FAISS for top-k similar chunks  
6. Optionally send retrieved text to an LLM to generate final answers (RAG)

---

## 🤖 Optional: Enable RAG with OpenAI

In the Streamlit app, toggle **"Generate final answer with OpenAI"**.

Then enter your API key:
```
sk-xxxx
```

You can easily replace this with:
- Groq Llama 3
- Ollama (local)
- Mistral
- LM Studio
- HuggingFace Inference

Just tell me and I’ll update the code for you.

---

## 📦 Requirements

```
streamlit
sentence-transformers
faiss-cpu
pypdf
numpy
openai
```

---

## 🧱 Future Enhancements (You can request any)

- LangChain-based RAG pipeline
- ChromaDB version
- Dockerfile + Docker Compose
- LlamaIndex integration
- Local LLM (Ollama) support
- HNSW / IVF FAISS indexes for faster search on large datasets

---

## ⭐ Show Your Support

If you find this useful, **give the repo a star** on GitHub!

---

Want me to **generate the GitHub repository description**, **badges**, or **screenshots**?

