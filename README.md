# RAG over GitHub Issues (Colab)

> A Retrieval‑Augmented Generation demo in Google Colab that pulls issues from a GitHub repo, chunks and embeds them with FAISS​, then answers natural‑language questions using a 4‑bit quantized Hugging Face LLM.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ibrahim1023/simple-rag/blob/main/RAG.ipynb)

## 🚀 Features

- **GitHub Issues Loader**: Pulls all issues (or PRs) from any public/private repo.  
- **Document Chunking**: Splits long texts into manageable 512‑token chunks with overlap.  
- **VectorStore**: Builds a FAISS index over Hugging Face sentence embeddings.  
- **Quantized LLM**: Uses a 4‑bit Zephyr‑7B model for fast, low‑memory inference.  
- **RAG Chain**: Retrieves the most relevant chunks and conditions LLM on that context for QA.  

## 📋 Prerequisites

1. **GitHub Access Token** (if you load private repos)  
2. **Hugging Face Token** (for model download & push)  
3. A free **Colab** account (GPU runtime recommended)  

## 🔄 Customization

Repo: change repo="owner/name".
Chunk size/overlap: tweak chunk_size & chunk_overlap.
Embedding model: swap BAAI/bge-base-en-v1.5 for any sentence‑transformers model.
LLM: point model_name to your preferred HF model (e.g. LLaMA, Mistral).
Prompt: rewrite the prompt_template for different behaviors (summaries, code, etc.).

## 📂 Notebook Overview

| Section                  | Description                                      |
|--------------------------|--------------------------------------------------|
| **1. Install & imports** | Installs libraries and sets up GPU runtime.      |
| **2. Auth & tokens**     | Logs into Hugging Face & sets GitHub token.      |
| **3. Load documents**    | Pulls issues/PRs from a GitHub repository.       |
| **4. Chunk & embed**     | Splits docs and creates a FAISS vector store.    |
| **5. LLM setup**         | Loads a quantized Zephyr 7B model.               |
| **6. RAG chain**         | Builds and composes the Retriever + LLM chain.   |
| **7. Inference**         | Runs example queries and displays answers.       |

