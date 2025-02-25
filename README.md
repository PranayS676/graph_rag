# **Graph-Based Retrieval-Augmented Generation (Graph RAG) System**  

## 🚀 **Overview**  
This project integrates **graph-based retrieval-augmented generation (Graph RAG)** using **Neo4j** and **LangChain** to enhance structured information retrieval for **LLMs**. It enables **entity extraction, full-text search, and hybrid retrieval** using **Neo4j Vector Search** and **LLMs like Ollama** for better contextual responses.  

## 🧠 **Key Features**  
✔ **Graph-Based Information Retrieval** – Uses **Neo4j** for structured knowledge extraction  
✔ **Hybrid Retrieval** – Combines **vector search** (Ollama embeddings) and **graph traversal** for relevant responses  
✔ **Entity Recognition & Full-Text Indexing** – Extracts entities from text and builds a **full-text search index** in Neo4j  
✔ **LLM Integration** – Leverages **LangChain** and **Ollama** for reasoning over retrieved knowledge  
✔ **Automatic Text Chunking** – Splits text into structured graph documents for better information processing  

---

## 🔧 **Installation**  

### **Prerequisites**  
Ensure you have the following installed:  
- **Python 3.11+**  
- **Neo4j** (with active database instance)  
- **Ollama** (LLM execution)  

### **Setup Instructions**  
1. **Clone the repository**  
   ```bash
   git clone https://github.com/your-repo/graph-rag.git
   cd graph-rag
   ```

2. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up environment variables** (replace with your credentials)  
   ```bash
   export NEO4J_URI="bolt://localhost:7687"
   export NEO4J_USERNAME="neo4j"
   export NEO4J_PASSWORD="your_password"
   ```

4. **Run the script**  
   ```bash
   python main.py
   ```

---

## ⚙️ **How It Works**  

1. **Text Preprocessing & Chunking**  
   - Uses **LangChain's RecursiveCharacterTextSplitter** to split documents into **chunks**  
   - Stores these **chunked documents** into Neo4j **Graph Database**  

2. **Entity Extraction & Graph Construction**  
   - **LLM extracts named entities** (people, organizations)  
   - Entities are stored as **nodes** in Neo4j with **relationship edges**  

3. **Hybrid Retrieval Process**  
   - **Full-text search query** retrieves related entities from Neo4j  
   - **Vector retrieval** fetches semantically relevant documents  
   - **Final Context Aggregation** combines both results  

4. **Response Generation**  
   - Uses **LangChain and Ollama LLM** to generate responses based on retrieved context  

---

## 🛠 **Technologies Used**  

- **Python** – Core programming language  
- **LangChain** – Framework for LLM-based applications  
- **Neo4j** – Graph database for structured retrieval  
- **Ollama** – Local LLM execution  
- **Neo4jVector** – Hybrid retrieval combining full-text search and embeddings  
- **Pydantic** – Data validation for extracted entities  
- **RecursiveCharacterTextSplitter** – Text chunking for graph storage  

---

## 📌 **Example Usage**  

```python
from graph_rag import chain

response = chain.invoke(input="Who is Nonna Lucia? Did she teach anyone about restaurants or cooking?")
print(response)
```

**Expected Output:**  
*"Nonna Lucia is the matriarch of the Caruso family, a culinary sage who taught her grandchildren, including Amico, the art of Sicilian cooking. She's also the owner of Bella Vita."*

---

