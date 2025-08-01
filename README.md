# PDF Chat with Gemini AI
The PDF Chat with Gemini AI is a Streamlit application that allows users to upload PDF documents and interact with them using Google's Gemini AI. This project combines PDF text extraction, vector embeddings, and natural language processing to provide intelligent question-answering capabilities based on document content.

## Table of Content
- [Project Structure](#Project_Structure)
- [Prerequisites & Installation](#Prerequisites_and_Installation)
- [Usage](#Usage)
- [Technical Details](#Technical_Details)
- [Results](#Results)

## Project_Structure
```Bash
PDF-Chat-Gemini/
├── app.py                    # Main Streamlit application
├── requirements.txt          # Python dependencies
├── .env                     # Environment variables (API key)
├── .gitignore              # Git ignore rules
├── README.md               # Project documentation
├── faiss_index/            # Vector store (auto-generated)
└── venv/                   # Virtual environment (not in repo)
```

## Prerequisites_and_Installation
### Prerequisites
- Python 3.8 or higher
- Google API key for Gemini AI
- pip package manager

### Installation
1. Clone the repository:
```bash
git clone https://github.com/your-username/pdf-chat-gemini.git
cd pdf-chat-gemini
```
2. Create and activate a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```
3. Install dependencies:
```bash
pip install -r requirements.txt
```
4. Set up your API key:
```bash
echo 'GOOGLE_API_KEY="your_api_key_here"' > .env
```

## Usage
### Web Interface
1. Start the Streamlit application:
```bash
streamlit run app.py
```
2. Open your browser and navigate to `http://localhost:8501`
3. Upload PDF files using the sidebar file uploader
4. Click "Submit & Process" to extract and process the text
5. Ask questions about your PDF content in the text input field

### Processing Pipeline
1. **PDF Upload**: Select one or more PDF files
2. **Text Extraction**: PyPDF2 extracts text from all pages
3. **Text Chunking**: RecursiveCharacterTextSplitter creates manageable chunks
4. **Vector Embeddings**: Google's embedding-001 model creates vector representations
5. **FAISS Storage**: Vectors are stored locally for fast similarity search
6. **Question Answering**: Gemini 2.0 Flash provides AI-powered responses

## Technical_Details
### PDF Processing
- **Library**: PyPDF2 for text extraction
- **Chunk Size**: 10,000 characters per chunk
- **Chunk Overlap**: 1,000 characters for context continuity

### Vector Embeddings
- **Model**: Google's embedding-001
- **Purpose**: Semantic similarity search
- **Storage**: FAISS vector store for fast retrieval

### AI Model
- **Model**: Gemini 2.0 Flash
- **Temperature**: 0.3 (balanced creativity and accuracy)
- **Context Window**: Processes relevant document chunks
- **Response Type**: Detailed answers based on document content

### Architecture Components
- **Frontend**: Streamlit web interface
- **Backend**: Python with LangChain framework
- **Vector Store**: FAISS for similarity search
- **AI Integration**: Google Generative AI API

## Results
The application provides:
- **Intelligent Q&A**: AI-powered answers based on PDF content
- **Semantic Search**: Finds relevant document sections
- **Real-time Processing**: Instant responses to user questions
- **Multi-PDF Support**: Process and query multiple documents
- **Local Storage**: FAISS index for fast retrieval
- **Error Handling**: Clear guidance for common issues
- **Security**: API keys protected in environment variables

### Key Features
- Upload multiple PDF files simultaneously
- Process large documents efficiently
- Get contextual answers from document content
- Modern, responsive web interface
- Secure API key management
- Comprehensive error handling and user guidance
