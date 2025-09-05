# 📚 Multimodal PDF Q&A

An **AI-powered application** that lets you upload a PDF and ask questions about both **text and images inside the document**.  
It uses **CLIP embeddings**, **LangChain**, **FAISS**, and **Ollama LLMs** to retrieve multimodal context and generate answers.  
The interface is built with **Gradio** for an easy-to-use web UI.  

---

## 🚀 Features  
- 🔎 Extracts **text and images** from PDF documents  
- 🖼️ Embeds both **text & images** with CLIP  
- 📖 Splits text into manageable chunks for better retrieval  
- 📊 Stores embeddings in **FAISS vector database**  
- 💬 Answers questions using **Ollama LLMs** (phi / mistral)  
- 🌐 Interactive **Gradio UI**  

---

## 🛠️ Installation  

### 1️⃣ Clone the repository  
```bash
git clone https://github.com/your-username/multimodal-pdf-qa.git
cd multimodal-pdf-qa
```

### 2️⃣ Create a virtual environment  
```bash
python -m venv venv
source venv/bin/activate   # On Linux/Mac
venv\Scripts\activate    # On Windows
```

### 3️⃣ Install dependencies  
```bash
pip install -r requirements.txt
```

Or manually:  
```bash
pip install gradio transformers huggingface_hub torch pillow scikit-learn python-dotenv pymupdf faiss-cpu langchain langchain-community
```

### 4️⃣ Setup environment variables  
Create a `.env` file in the project root if needed for API keys or custom configs. Example:  
```
OLLAMA_HOST=http://localhost:11434
```

---

## ▶️ Usage  

Run the app:  
```bash
python app.py
```

This will launch a **local Gradio UI** in your browser.  

1. 📄 Upload a PDF file  
2. ❓ Ask a question about the content or images inside  
3. 🤖 Get context-aware answers powered by LLM  

---

## 📂 Project Structure  
```
multimodal-pdf-qa/
│── app.py                # Main application script
│── requirements.txt      # Python dependencies
│── .env                  # Environment variables (optional)
│── README.md             # Project documentation
```

---

## ⚡ Example Workflow  
1. Upload a research paper or report PDF.  
2. Ask: *"What does the chart on page 3 represent?"*  
3. The system retrieves text + image embeddings.  
4. The LLM provides a context-aware answer.  

---

## 🧰 Tech Stack  
- **Python**  
- **Gradio** (UI)  
- **Transformers (CLIP)** (embeddings)  
- **FAISS** (vector search)  
- **LangChain** (document & LLM integration)  
- **Ollama** (LLM inference)  

---

## 📌 Notes  
- Requires [Ollama](https://ollama.ai) installed locally to run LLM models like `phi` or `mistral`.  
- Works best on PDFs containing both text and images.  
- Large PDFs may take time to process.  

---

## 🏗️ Future Improvements  
- Support for **multi-page image previews**  
- Add **chat history memory**  
- Support for **more embedding models**  
- Deploy on **Streamlit / Hugging Face Spaces**  

---

## 📜 License  
This project is licensed under the **MIT License**.  
