# My Gen AI Career Journey 🚀

> A comprehensive documentation of my evolution in OCR, PDF Processing, and LLM Integration (2024-2025)

## 📊 Technology Evolution Timeline

```
2024 Early → Tesseract OCR (Traditional)
    ↓
2024 Sep → Enhanced Tesseract + Preprocessing
    ↓
2024 Oct → PaddleOCR Integration
    ↓
2024 Nov → DocTR Model Implementation
    ↓
2025 Jan → Gemini 2.0 Flash/Experimental API
    ↓
Current → Gemini 2.5 + Voice AI (Gemini 3-type API)
```

## 🎯 Core Competencies

### 1. OCR Evolution Journey

#### Phase 1: Traditional OCR (Early 2024)
- **Technology**: Tesseract OCR
- **Use Case**: Basic text extraction
- **Learnings**: Understanding OCR fundamentals

#### Phase 2: Enhanced Tesseract (September 2024)
- **Technology**: Tesseract with advanced preprocessing
- **Improvements**: 
  - Image preprocessing techniques
  - Confidence score analysis
  - Better accuracy for printed documents

#### Phase 3: PaddleOCR Integration (October 2024)
- **Technology**: PaddleOCR
- **Advantages**:
  - Multi-language support
  - Better performance on complex layouts
  - Faster processing speed

#### Phase 4: DocTR Model (November 2024)
- **Technology**: DocTR (Document Text Recognition)
- **Current Status**: Primary OCR engine
- **Features**:
  - Deep learning-based OCR
  - Superior accuracy
  - Better handling of document structures

### 2. PDF Processing Expertise

#### Text PDF Extraction Tools

**pdfplumber**
- **Purpose**: Initial exploration for text-based PDFs
- **Features**: 
  - Table extraction capabilities
  - Simple API for text extraction
  - Good for structured documents
- **Use Case**: Quick extraction from digital PDFs

**PyMuPDF (Fitz) - Primary Tool**
- **Purpose**: Advanced PDF text extraction with spatial awareness
- **Why Switched**: Superior handling of complex layouts and space preservation

**Key Features**:
- Bounding box extraction for precise text location
- Text module for structured PDF parsing
- Space preservation techniques to avoid text merging issues
- Coordinate-based extraction for targeted content
- Better performance on both text and scanned PDFs

**Use Cases**:
- **Text PDFs**: Direct extraction with pdfplumber for simple cases, PyMuPDF (Fitz) for complex layouts with space handling
- **Scanned PDFs**: DocTR + Fitz combination for space issue resolution
- **Keyword-based Extraction**: Cutting specific sections using coordinates
- **Hybrid Approach**: Using Fitz to identify regions, then processing with OCR/LLM for maximum accuracy

### 3. LLM Integration (2025)

#### Local Models
- **Llama 3B & 8B**: Lightweight inference modules
- **Mistral 7B**: Advanced reasoning tasks
- **Architecture**: Modular design for easy model swapping

#### Cloud APIs
- **Gemini 2.0 Flash**: Fast text extraction
- **Gemini 2.0 Experimental**: Advanced document understanding
- **Gemini 2.5**: Current production model for mapping tasks
- **Gemini Voice API**: Latest integration for voice-enabled AI

### 4. OCR Confidence Predictor
**Custom Module**: OCR quality assessment
- Calculates confidence levels across different OCR engines
- Helps select the best OCR method per document type
- Provides accuracy metrics for continuous improvement

## 📈 Accuracy Progression Graph

```
Tesseract (Traditional)     ████░░░░░░ 40%
    ↓
Enhanced Tesseract          ██████░░░░ 60%
    ↓
PaddleOCR                   ████████░░ 80%
    ↓
DocTR                       █████████░ 90%
    ↓
Gemini 2.0 Flash            ██████████ 95%
    ↓
Gemini 2.5 + Fitz Hybrid    ██████████ 98%
```

## 🔧 Published Projects

### Project 1: Automation Tool - RPA Prototype
**Repository**: [Link to repo]
**Description**: Robotic Process Automation tool for document processing workflows

### Project 2: Hybrid OCR - PaddleOCR + Gemini Coordinate Extractor
**Repository**: [Link to repo]
**Technology Stack**:
- PaddleOCR for initial detection
- Bounding box coordinate extraction
- Gemini API for text extraction from coordinates
**Use Case**: Click-based coordinate extraction with AI-powered text recognition

### Project 3: High-Accuracy PDF Extraction Pipeline
**Repository**: [Link to repo]
**Workflow**:
1. Extract text using traditional methods
2. Pass to Gemini for initial processing
3. Use PyMuPDF (Fitz) with keyword detection
4. Cut specific PDF sections based on coordinates
5. Re-process with Gemini for maximum accuracy
**Result**: 98%+ accuracy on complex documents

### Project 4: RAG-Based Search System
**Repository**: [Link to repo]
**Technology Stack**:
- FAISS for vector storage
- Ollama 3B for local inference
- Custom retrieval pipeline
**Features**: Fast, privacy-focused document Q&A system

## 🛠️ Installation Guides

### 1. Tesseract OCR Setup

```bash
# Ubuntu/Debian
sudo apt update
sudo apt install tesseract-ocr
sudo apt install libtesseract-dev

# Python wrapper
pip install pytesseract pillow

# Verify installation
tesseract --version
```

### 2. PaddleOCR Installation

```bash
# Install PaddlePaddle
pip install paddlepaddle-gpu  # For GPU
# OR
pip install paddlepaddle      # For CPU

# Install PaddleOCR
pip install paddleocr

# Quick test
python -c "from paddleocr import PaddleOCR; ocr = PaddleOCR(use_angle_cls=True, lang='en'); print('PaddleOCR Ready!')"
```

### 3. DocTR Installation

```bash
# Install PyTorch (check your CUDA version)
pip install torch torchvision

# Install DocTR
pip install python-doctr[torch]

# Or with TensorFlow backend
pip install python-doctr[tf]

# Verify
python -c "from doctr.models import ocr_predictor; print('DocTR Ready!')"
```

### 4. PyMuPDF (Fitz) Setup

```bash
# Install PyMuPDF
pip install PyMuPDF

# For advanced features
pip install PyMuPDF[extras]

# Quick test
python -c "import fitz; print(f'PyMuPDF version: {fitz.version}')"
```

### 5. Ollama Setup (Local LLM)

```bash
# Linux installation
curl -fsSL https://ollama.com/install.sh | sh

# Pull models
ollama pull llama3:3b
ollama pull llama3:8b
ollama pull mistral:7b

# Verify
ollama list
```

### 6. LangChain & FAISS for RAG

```bash
# Install LangChain
pip install langchain langchain-community

# Install FAISS
pip install faiss-cpu  # For CPU
# OR
pip install faiss-gpu  # For GPU

# Additional dependencies
pip install sentence-transformers
pip install chromadb  # Alternative vector DB

# Verify
python -c "import faiss; import langchain; print('RAG stack ready!')"
```

### 7. Gemini API Setup

```bash
# Install Google Generative AI library
pip install google-generativeai

# Set up API key (Linux/Mac)
export GOOGLE_API_KEY='your-api-key-here'

# Or in Python
import google.generativeai as genai
genai.configure(api_key='your-api-key-here')
```

### Complete Environment Setup

```bash
# Create virtual environment
python -m venv genai_env
source genai_env/bin/activate  # Linux/Mac
# genai_env\Scripts\activate   # Windows

# Install all dependencies
pip install pytesseract paddleocr python-doctr[torch] PyMuPDF
pip install google-generativeai langchain faiss-cpu
pip install sentence-transformers pillow opencv-python
pip install pandas numpy matplotlib

# Save requirements
pip freeze > requirements.txt
```

## 📚 Key Learnings

### OCR Best Practices
1. **Preprocessing is crucial**: Image quality directly impacts OCR accuracy
2. **Hybrid approaches work best**: Combine multiple OCR engines based on document type
3. **Confidence scoring**: Always validate OCR output quality
4. **Space handling**: Critical for maintaining document structure

### PDF Processing Insights
1. **Use Fitz for spatial awareness**: Bounding boxes preserve layout information
2. **Keyword-based extraction**: More accurate than full-page processing
3. **Scanned vs Text PDFs**: Different strategies required

### LLM Integration
1. **Start local, scale to cloud**: Ollama for development, Gemini for production
2. **Context matters**: Better prompts = better results
3. **Cost optimization**: Use appropriate model sizes

## 🎓 Skills Developed

- ✅ OCR Engine Selection & Optimization
- ✅ PDF Processing & Text Extraction
- ✅ Deep Learning Model Integration
- ✅ LLM Prompt Engineering
- ✅ Vector Database Management
- ✅ API Integration (Gemini, OpenAI-compatible APIs)
- ✅ Accuracy Measurement & Optimization
- ✅ Production Pipeline Design

## 🚀 Current Focus

- Gemini 2.5 Flash for production workloads
- Voice AI integration with Gemini 3-type APIs
- Advanced RAG architectures with hybrid search
- Real-time document processing pipelines

## 📬 Connect

Feel free to explore my projects and reach out for collaborations in Gen AI, OCR, and Document Processing!

---

**Last Updated**: January 2025  
**Status**: Actively Learning & Building 🔥
