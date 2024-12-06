# RAG Document Q&A with Groq and Llama3

This project demonstrates a **Retrieval-Augmented Generation (RAG)** system using **Groq API**, **Llama3**, and **Streamlit**. It allows users to query research papers stored in PDF format and receive accurate answers based on document embeddings and context.

## Features
- **Document Embedding**: Converts research papers into embeddings for efficient search.
- **Query Processing**: Answers user questions based on the context of the uploaded research papers.
- **Streamlit Integration**: Provides an interactive user interface for querying documents and exploring results.
- **Document Similarity Search**: Displays the most relevant sections of the documents that contributed to the response.

---

## Installation and Setup

### Prerequisites
- Python 3.8 or higher
- A Groq API key
- An OpenAI API key
- Streamlit installed in your environment
- Research papers in PDF format placed in a folder named `research_papers`

### Steps
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/your-repository.git
   cd your-repository
   ```

2. **Install Dependencies**:
   Install the required Python packages using:
   ```bash
   pip install -r requirements.txt
   ```

3. **Environment Variables**:
   Create a `.env` file and add your API keys:
   ```env
   OPENAI_API_KEY=your_openai_api_key
   GROQ_API_KEY=your_groq_api_key
   ```

4. **Run the Application**:
   Launch the Streamlit app:
   ```bash
   streamlit run app.py
   ```

---

## How It Works

1. **Load Research Papers**:
   - The `PyPDFDirectoryLoader` ingests PDF files from the `research_papers` folder.
   - Documents are split into smaller chunks using `RecursiveCharacterTextSplitter`.

2. **Create Embeddings**:
   - The `OpenAIEmbeddings` model generates embeddings for the document chunks.
   - A vector database is created using FAISS.

3. **Query and Retrieval**:
   - User inputs a query through the Streamlit interface.
   - A retrieval chain finds the most relevant chunks.
   - The `Llama3` model, via `ChatGroq`, generates an answer based on the retrieved context.

4. **Display Results**:
   - The most relevant sections of the documents are displayed alongside the generated answer.

---

## Folder Structure
```plaintext
.
├── app.py                 # Main Streamlit application script
├── research_papers/       # Folder containing PDF research papers
├── requirements.txt       # Python dependencies
├── .env                   # Environment variables (API keys)
└── README.md              # Project documentation
```

---

## Example Usage

1. Place research papers in the `research_papers/` folder.
2. Run the application and click **Document Embedding** to create the vector database.
3. Enter a query (e.g., "What is the conclusion of paper X?") in the input field.
4. View the response along with the relevant document excerpts.

---

## Key Dependencies
- **Streamlit**: For the user interface.
- **LangChain**: For document loading, embedding, and retrieval chains.
- **FAISS**: For vector storage and similarity search.
- **PyPDFLoader**: For processing PDF files.
- **OpenAI API**: For embedding generation.
- **Groq API**: For querying the Llama3 model.

---

## Future Enhancements
- Support for additional document formats.
- Integration with more language models.
- Improved performance for large document sets.

---

## Contributing
Contributions are welcome! Please fork the repository, create a feature branch, and submit a pull request.

---
