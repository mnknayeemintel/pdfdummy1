# 📄 AI-Powered RAG-Based PDF Q&A System with Local LLM 🚀

## 🛠 Problem Statement
In today's fast-paced world, retrieving relevant information from large PDF documents can be tedious and time-consuming. Traditional keyword-based search often fails to provide context-aware answers. A more intelligent approach is needed to extract meaningful insights from documents effectively.

## ❓ Why RAG (Retrieval-Augmented Generation)?
RAG combines **retrieval-based** and **generation-based** approaches to enhance the accuracy of responses. Instead of relying solely on a pre-trained model's knowledge, RAG fetches relevant document sections and generates context-aware answers. This improves:

✅ **Precision** – Only relevant text is used for responses.  
✅ **Scalability** – Works well with large document collections.  
✅ **Flexibility** – Can be integrated with various LLMs for local/private deployment.  

---

# 🔧 Tools Used
- **Streamlit** – For building an interactive web-based UI  
- **LangChain** – For document loading, text splitting, retrieval, and LLM integration  
- **PDFPlumber** – To extract text from PDF documents  
- **Ollama** – For running local LLMs  
- **InMemoryVectorStore** – To store and retrieve document embeddings  
- **DeepSeek / Any Local LLM** – As the language model for answering queries  

---

# 🔄 Query-to-Response Workflow

## 📂 1. Upload PDF
Users can upload a PDF document via the **Streamlit** interface. The uploaded file is saved to a designated directory for processing.

## 📑 2. Load & Parse PDF
Using **PDFPlumber**, the system extracts text content from the document and converts it into a structured format.

## ✂ 3. Text Splitting
The extracted text is split into smaller, manageable chunks using **RecursiveCharacterTextSplitter**. This ensures that each chunk is of optimal length for embedding and retrieval.

## 🧠 4. Embedding & Vector Storage
Each text chunk is converted into a numerical representation using **OllamaEmbeddings** (or any local embedding model). The embeddings are stored in an **InMemoryVectorStore** for efficient retrieval.

## 🔍 5. Query Processing & Retrieval
When a user inputs a query, the system performs a similarity search in the vector database to retrieve the most relevant text chunks.

## 🤖 6. Response Generation
The retrieved context is passed to an **Ollama LLM** (or any local model). A structured prompt template ensures the model generates concise, context-aware responses.

## 💬 7. Display Answer
The generated response is displayed in a **Streamlit chat interface**, allowing users to interact dynamically with the system.

---

# 🖥 Using a Local LLM
This system is designed to work with **local LLMs** using [Ollama](https://ollama.com/), ensuring privacy and offline accessibility.  
### Steps to Run with a Local LLM:
1️⃣ Install **Ollama** and download a compatible model (e.g., `deepseek-r1:7b`).  
2️⃣ Configure the LLM within the LangChain pipeline.  
3️⃣ Run the Streamlit app and start querying your PDFs! 🎉  

---

# 📌 Important Notes
- This system can be extended to use other **LLMs** like Llama, Mistral, or GPT-based models.
- Future enhancements may include **multi-document support**, **database-backed storage**, and **improved UI**.
- Ensure that your local model is optimized for **inference speed** to maintain a smooth user experience.

---

🚀 **Ready to revolutionize how you search PDFs? Try it now!** 🎯

