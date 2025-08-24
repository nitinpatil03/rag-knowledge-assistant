# 📚 Multimodal RAG with Ollama + CLIP + FAISS

This project is a **Multimodal Retrieval-Augmented Generation (RAG) pipeline** that works **fully offline**.  
It extracts **text + images** from PDFs, embeds them with **CLIP**, stores them in a **FAISS vector database**, and queries them using **local LLMs via Ollama** (default = `phi`).

---

## 🚀 Features
- 📄 **Parse PDFs** (text + images) with [PyMuPDF](https://pymupdf.readthedocs.io/).  
- 🧠 **Embed text and images** using [OpenAI CLIP](https://huggingface.co/openai/clip-vit-base-patch32).  
- 🔍 **Vector search** using [FAISS](https://faiss.ai/).  
- 🤖 **Local LLM responses** using [Ollama](https://ollama.ai/) (default = `phi`, fallback = `mistral:q4_0`).  
- 💡 Works **offline** after downloading models.  

---

## 📦 Installation

### 1. Install dependencies
```bash
pip install --upgrade transformers huggingface_hub torch pillow scikit-learn python-dotenv pymupdf faiss-cpu langchain langchain-community
```

### 2. Install Ollama
Download Ollama from 👉 [https://ollama.ai/download](https://ollama.ai/download)

Then pull the model:
```bash
ollama pull phi
```

(Optional) Pull other models:
```bash
ollama pull mistral:q4_0
ollama pull llama2
```

---

## 📂 Project Structure
```
multimodal-rag/
│── 1-multimodelopenai.ipynb   # Main notebook (Ollama-based RAG pipeline)
│── multimodal_sample.pdf      # Example PDF (replace with your own)
│── README.md                  # Project documentation
```

---

## ▶️ Usage

1. Place your PDF inside the project folder and rename it:
   ```
   multimodal_sample.pdf
   ```

2. Open Jupyter Notebook:
   ```bash
   jupyter notebook 1-multimodelopenai.ipynb
   ```

3. Run all cells.

4. Example queries:
   ```python
   queries = [
       "What does the chart on page 1 show about revenue trends?",
       "Summarize the main findings from the document",
       "What visual elements are present in the document?"
   ]
   ```

---

## ✅ Example Output
```
❓ Query: Summarize the main findings from the document
--------------------------------------------------
Retrieved 3 documents:
- text (page 0)
- image (page 0)
- text (page 1)

💡 Answer: The document shows revenue grew steadily, with Q3 achieving the highest growth due to global expansion...
```

---

## 🛠️ Notes
- Default LLM = `phi` (lightweight, ~1.5GB).  
- If `phi` fails, it falls back to `mistral:q4_0`.  
- Requires at least **8GB RAM** (16GB recommended for bigger models).  
- You can swap the model in the code:
  ```python
  llm = ChatOllama(model="phi")  # or mistral, llama2, gemma
  ```

--
