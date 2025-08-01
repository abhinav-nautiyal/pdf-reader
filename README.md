# 📄 Chat with PDF using Gemini AI

A powerful Streamlit application that allows you to chat with your PDF documents using Google's Gemini AI. Upload PDF files, process them, and ask questions to get intelligent answers based on the document content.

## ✨ Features

- **📄 PDF Upload**: Upload multiple PDF files simultaneously
- **🤖 AI-Powered Q&A**: Ask questions about your PDF content using Gemini 2.0 Flash
- **🔍 Smart Search**: Uses vector embeddings for semantic similarity search
- **💾 Local Storage**: FAISS vector store for fast and efficient retrieval
- **🎨 Modern UI**: Clean Streamlit interface with dark theme
- **⚡ Real-time Processing**: Instant answers to your questions

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- Google API key for Gemini AI

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/pdf-chat-gemini.git
   cd pdf-chat-gemini
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up your API key**
   - Get your Google API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
   - Create a `.env` file in the project directory:
   ```bash
   echo 'GOOGLE_API_KEY="your_api_key_here"' > .env
   ```

4. **Run the application**
   ```bash
   streamlit run app.py
   ```

5. **Open your browser**
   - Navigate to `http://localhost:8501`
   - Start chatting with your PDFs!

## 📖 How to Use

1. **Upload PDF Files**
   - Use the file uploader in the sidebar
   - Select one or more PDF files
   - Click "Submit & Process"

2. **Wait for Processing**
   - The app will extract text from your PDFs
   - Create vector embeddings for semantic search
   - Store them locally for fast retrieval

3. **Ask Questions**
   - Type your questions in the text input
   - Get AI-powered answers based on your PDF content
   - The AI will only answer based on the uploaded documents

## 🛠️ Technical Details

### Architecture

- **Frontend**: Streamlit web interface
- **PDF Processing**: PyPDF2 for text extraction
- **Text Chunking**: RecursiveCharacterTextSplitter (10k chunks, 1k overlap)
- **Embeddings**: Google's embedding-001 model
- **Vector Store**: FAISS for similarity search
- **AI Model**: Gemini 2.0 Flash for question answering

### Key Components

- `app.py`: Main application logic
- `requirements.txt`: Python dependencies
- `.env`: Environment variables (API key)
- `faiss_index/`: Local vector store (auto-generated)

## 🔧 Configuration

### Environment Variables

Create a `.env` file with:
```
GOOGLE_API_KEY=your_google_api_key_here
```

### Customization

You can modify these parameters in `app.py`:
- **Chunk size**: `chunk_size=10000` (line 28)
- **Chunk overlap**: `chunk_overlap=1000` (line 28)
- **AI model**: `model="gemini-2.0-flash"` (line 47)
- **Temperature**: `temperature=0.3` (line 47)

## 📁 Project Structure

```
pdf-chat-gemini/
├── app.py                 # Main application
├── requirements.txt       # Python dependencies
├── .env                  # Environment variables (not in repo)
├── .gitignore           # Git ignore rules
├── README.md            # This file
└── faiss_index/         # Vector store (auto-generated)
```

## 🔒 Security

- API keys are stored in `.env` file (not committed to repo)
- `.gitignore` excludes sensitive files
- No data is sent to external servers except for AI processing

## 🐛 Troubleshooting

### Common Issues

1. **API Key Error**
   - Ensure your Google API key is valid and not expired
   - Check that the `.env` file is in the project root

2. **Import Errors**
   - Make sure all dependencies are installed: `pip install -r requirements.txt`
   - Use Python 3.8+ for compatibility

3. **PDF Processing Issues**
   - Ensure PDF files are not corrupted
   - Check that PDFs contain extractable text (not just images)

4. **Memory Issues**
   - Large PDFs may require more memory
   - Consider splitting very large documents

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Commit your changes: `git commit -am 'Add feature'`
4. Push to the branch: `git push origin feature-name`
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Streamlit](https://streamlit.io/) for the web framework
- [Google Gemini AI](https://ai.google.dev/) for the AI capabilities
- [LangChain](https://langchain.com/) for the AI framework
- [FAISS](https://github.com/facebookresearch/faiss) for vector similarity search

## 📞 Support

If you encounter any issues or have questions:
- Open an issue on GitHub
- Check the troubleshooting section above
- Ensure all dependencies are properly installed

---

**Made with ❤️ using Streamlit and Gemini AI** 