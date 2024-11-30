# Conversational RAG with PDF Uploads and Chat History

This project is a **Conversational Retrieval-Augmented Generation (RAG) application** built using Streamlit. It allows users to upload PDF files, extract their content, and interact with the documents through a conversational chat interface. The application includes chat history for better context retention and uses the **Groq API** for language model operations.

## Features

- **Upload PDF Files**: Users can upload one or more PDF documents for processing.
- **Document Embedding and Retrieval**: The app splits document content into chunks and generates embeddings for efficient information retrieval.
- **Conversational Chat Interface**: Users can ask questions about the uploaded documents, and the system provides contextual, concise answers.
- **Chat History**: Tracks conversation history for improved contextual question answering.
- **Pre-configured API Key**: The Groq API key is set in the environment, eliminating the need for users to input their own.

---

## Setup Instructions

### Prerequisites
- Python 3.8 or later.
- A Groq API key.
- A HuggingFace account for embeddings.

### Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-repo/conversational-rag.git
   cd conversational-rag
   ```

2. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Environment Variables**
   Create a `.env.local` file in the project root and add the following:
   ```plaintext
   HF_TOKEN=your_huggingface_token
   GROQ_API_KEY=your_groq_api_key
   ```

4. **Run the Application**
   ```bash
   streamlit run app.py
   ```

---

## Usage

1. **Launch the Application**: Open the app in your browser using the URL displayed in the terminal.
2. **Upload PDFs**: Use the file uploader to select one or more PDF documents.
3. **Ask Questions**: Enter your questions in the chat box. The system retrieves relevant document sections and generates answers.
4. **View Chat History**: The chat history is displayed for better context in follow-up questions.

---

## Key Components

- **PDF Processing**: Extracts content from PDFs using `PyPDFLoader`.
- **Text Splitting**: Utilizes `RecursiveCharacterTextSplitter` to divide documents into smaller chunks for embedding.
- **Embeddings**: Powered by HuggingFace’s `all-MiniLM-L6-v2` model.
- **Vector Store**: Employs Chroma for document storage and retrieval.
- **Conversational Chain**: Combines retrieval and question-answering chains using Groq’s `Gemma2-9b-It` language model.

---

## Project Structure

```plaintext
├── app.py                   # Main application code
├── requirements.txt         # Python dependencies
├── .env.local               # Environment variables
├── README.md                # Documentation
├── temp.pdf                 # Temporary file for processing PDFs
```

---

## Environment Variables

The following variables should be set in the `.env.local` file:

- **HF_TOKEN**: HuggingFace API token for generating embeddings.
- **GROQ_API_KEY**: API key for the Groq language model.

---

## Limitations

- The system depends on the quality of the Groq language model and HuggingFace embeddings.
- Larger PDFs might take longer to process due to chunking and embedding generation.

---

## Future Enhancements

- Support for additional file formats (e.g., Word, text).
- Enhanced conversational capabilities with better multi-turn reasoning.
- Fine-tuned embeddings for domain-specific applications.

---

## Troubleshooting

- **Missing Environment Variables**: Ensure `.env.local` is correctly configured.
- **Dependency Errors**: Reinstall dependencies using `pip install -r requirements.txt`.

---

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

- [Streamlit](https://streamlit.io/)
- [HuggingFace](https://huggingface.co/)
- [Groq Language Models](https://groq.com/)
- [Chroma](https://docs.trychroma.com/)