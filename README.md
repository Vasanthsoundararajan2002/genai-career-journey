# 🚀 My Gen AI Career Journey

> From Traditional OCR to Cutting-Edge AI Solutions - A Chronicle of Innovation in Document Intelligence & Automation

[![Python](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Experience](https://img.shields.io/badge/experience-1.4%20years-green.svg)](https://www.linkedin.com/in/vasanthsa/)
[![Role](https://img.shields.io/badge/role-Software%20Developer-orange.svg)](https://droidal.com)

---

## 👨‍💻 About Me

**Vasanth Soundararajan** | Software Developer @ Droidal  
**Experience**: 1.4 years in Python development, specializing in RPA and Gen AI  
**Current Role**: Product Team - Building enterprise automation tools

I work on **Droidal's flagship automation platform** - an all-in-one tool that combines:
- 🌐 **Web automation** (Selenium-based browser control)
- 🖥️ **Desktop automation** (UI element interaction)
- 📊 **Excel automation** (Advanced spreadsheet operations)
- 🤖 **Gen AI integration** (OCR, document processing, LLM workflows)

In parallel, I've been exploring cutting-edge AI technologies, building innovative solutions that push the boundaries of document intelligence and automated workflows.

---

## 📊 Technology Evolution Timeline

```
2023 Early → Enterprise RPA Development (Droidal Product Team)
    ↓
2024 Early → Traditional OCR (Tesseract)
    ↓
2024 Sep → Enhanced Tesseract + Preprocessing
    ↓
2024 Oct → PaddleOCR Integration
    ↓
2024 Nov → DocTR Model Implementation
    ↓
2024 Q4 → Hybrid OCR Architecture (PaddleOCR + Gemini Vision)
    ↓
2025 Jan → Gemini 2.0 Flash/Experimental API Integration
    ↓
2025 Jan → AI-Powered Medical Document Processing Pipeline
    ↓
Current → RAG Systems + Gemini 2.5 + Voice AI (Gemini 3-type API)
```

---

## 🎯 Core Competencies

### 1. Enterprise RPA Development (Droidal)

**Role**: Software Developer - Product Team  
**Duration**: 1.4 years  
**Tech Stack**: Python, Selenium, PyAutoGUI, openpyxl, PyMuPDF

**What I Build**:
- Multi-platform automation engine (Web + Desktop + Excel)
- Visual workflow designer for non-technical users
- Complex automation scenarios with conditional logic
- Error handling and robust execution pipelines

**Key Achievements**:
- Contributed to enterprise automation tool serving thousands of workflows
- Designed modular architecture for extensible automation steps
- Built visual tree-view workflow representation
- Implemented nested workflow support with variable management

### 2. OCR & Document Intelligence Evolution

#### Phase 1: Traditional OCR (Early 2024)
**Technology**: Tesseract OCR  
**Learning**: Understanding OCR fundamentals and basic text extraction

#### Phase 2: Enhanced Tesseract (September 2024)
**Technology**: Tesseract with advanced preprocessing  
**Improvements**:
- Image preprocessing techniques
- Confidence score analysis
- Better accuracy for printed documents (60% accuracy)

#### Phase 3: PaddleOCR Integration (October 2024)
**Technology**: PaddleOCR  
**Capabilities**:
- Multi-language OCR with 80%+ accuracy
- Bounding box extraction for spatial awareness
- Better performance on complex layouts
- Faster processing speed

#### Phase 4: DocTR Model (November 2024)
**Technology**: DocTR (Document Text Recognition)  
**Features**:
- Deep learning-based OCR
- Superior accuracy (90%)
- Better handling of document structures
- Table extraction from structured documents

#### Phase 5: Hybrid Intelligence (Late 2024)
**Technologies**: PaddleOCR + Google Gemini Vision  
**Innovation**: Authority Model Architecture
- **PaddleOCR** = Spatial Authority (coordinates, colors, layout)
- **Gemini Vision** = Text Authority (content accuracy)
- **Result**: 97-98% accuracy with pixel-perfect positioning

#### Phase 6: AI-Powered Pipelines (Current - January 2025)
**Technologies**: Gemini 2.0 Flash, Gemini 2.5, OpenCV, Advanced PDF processing  
**Applications**:
- Medical document classification and extraction
- Multi-patient record splitting
- Structured data export to Excel
- Context-aware field detection
- Voice AI integration with Gemini 3-type APIs

### 3. PDF Processing Expertise

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

### 4. RAG & Local LLM Integration

**Tech Stack**: Ollama, FAISS, sentence-transformers  
**Architecture**: Privacy-focused document Q&A

```
Documents → Embeddings (sentence-transformers)
    ↓
FAISS Vector Index (local storage)
    ↓
Query → Vector Search → Context Retrieval
    ↓
Context + Query → Ollama Llama 3.2 3B → Answer
    ↓
100% Local Processing (no cloud dependencies)
```

#### Local Models
- **Llama 3B & 8B**: Lightweight inference modules
- **Mistral 7B**: Advanced reasoning tasks
- **Architecture**: Modular design for easy model swapping

#### Cloud APIs
- **Gemini 2.0 Flash**: Fast text extraction (95% accuracy)
- **Gemini 2.0 Experimental**: Advanced document understanding
- **Gemini 2.5**: Current production model for mapping tasks (98% accuracy)
- **Gemini Voice API**: Latest integration for voice-enabled AI

**Use Cases**:
- Employee document search
- Internal knowledge bases
- Document Q&A without cloud exposure
- Fast retrieval (<1 second per query)

### 5. OCR Confidence Predictor
**Custom Module**: OCR quality assessment
- Calculates confidence levels across different OCR engines
- Helps select the best OCR method per document type
- Provides accuracy metrics for continuous improvement

---

## 📈 Accuracy Progression Graph

```
Tesseract (Traditional)        ████░░░░░░ 40%
    ↓
Enhanced Tesseract             ██████░░░░ 60%
    ↓
PaddleOCR                      ████████░░ 80%
    ↓
DocTR                          █████████░ 90%
    ↓
Gemini 2.0 Flash               ██████████ 95%
    ↓
Gemini 2.5 + Fitz Hybrid       ██████████ 98%
```

---

## 🔧 Published Projects

### Project 1: FlowBot Automation Builder
**Repository**: [flowbot-automation-builder](https://github.com/Vasanthsoundararajan2002/flowbot-automation-builder)  
**Type**: RPA Prototype inspired by enterprise development  
**Technologies**: Python, Tkinter, Selenium, PyAutoGUI, openpyxl

**What It Does**:
- Visual drag-and-drop workflow designer
- Multi-platform automation (Web, Desktop, Excel)
- Control flow (loops, conditionals, variables)
- Save/load workflows as JSON
- Real-time execution logging

**Why It Matters**:
Personal exploration of RPA concepts learned while building Droidal's production tool. Demonstrates understanding of workflow orchestration, user experience design, and modular architecture.

**Key Features**:
- ✅ 30+ automation actions across 4 platforms
- ✅ Tree-view workflow visualization
- ✅ Nested workflow support
- ✅ Error handling with configurable responses
- ✅ OCR integration for image-based automation

---

### Project 2: AI-Powered Medical PDF Processing Pipeline
**Repository**: [ai-powered-medical-pdf-processing-pipeline](https://github.com/Vasanthsoundararajan2002/ai-powered-medical-pdf-processing-pipeline)  
**Type**: Production-grade document intelligence system  
**Technologies**: Google Gemini 2.0, PyMuPDF, OpenCV, openpyxl

**What It Does**:
```
Input: Multi-patient PDF (50-100 pages)
    ↓
AI Classification → Separate patient records
    ↓
Page-by-page analysis → Extract demographics, insurance, clinical data
    ↓
Image enhancement → Better OCR and form detection
    ↓
Output: Structured Excel + Individual PDFs
```

**Technical Highlights**:
- 📄 Processes complex multi-document PDFs automatically
- 🤖 Gemini Vision for 95%+ extraction accuracy
- 🖼️ OpenCV preprocessing for image enhancement
- 📊 Clean data export to Excel (JSON → tabular format)
- 🗂️ Automatic archiving with version control

**Performance**:
- **Speed**: 2-3 seconds per page
- **Accuracy**: 90-95% on structured medical documents
- **Scalability**: Handles 100+ page documents
- **Batch processing**: Multiple PDFs in queue

**Real-World Impact**:
Transforms hours of manual data entry into minutes of automated processing. Designed with healthcare compliance considerations (though this is a sanitized demo version).

---

### Project 3: Hybrid OCR Architecture
**Repository**: [Hybrid-OCR-Architecture](https://github.com/Vasanthsoundararajan2002/Hybrid-OCR-Architecture)  
**Type**: Novel OCR solution using Authority Model  
**Technologies**: PaddleOCR, Google Gemini Vision, PyAutoGUI

**The Innovation**:
Instead of choosing one OCR engine, I designed a system where each engine serves as the "authority" for its strengths:

| Component | Authority | Responsibility |
|-----------|-----------|----------------|
| **PaddleOCR** | Spatial | Coordinates, colors, layout |
| **Gemini Vision** | Text | Content accuracy, context understanding |
| **Hybrid Matcher** | Integration | Maps Gemini text onto PaddleOCR positions |

**Architecture**:
```
┌─────────────────────────────────────┐
│     HYBRID OCR ORCHESTRATOR         │
├─────────────────────────────────────┤
│                                     │
│  PaddleOCR        Gemini Vision    │
│  (Fast & Local)   (Smart & Cloud)  │
│      │                   │          │
│      ▼                   ▼          │
│  Spatial Map      Text Content     │
│  (coordinates)    (high accuracy)  │
│      │                   │          │
│      └─────────┬─────────┘          │
│                ▼                    │
│         Hybrid Matcher              │
│    (Best text + Best position)     │
│                ▼                    │
│         Click Executor              │
│      (Pixel-perfect action)         │
└─────────────────────────────────────┘
```

**Use Case**: Financial Ledger Automation  
- Detect violet-highlighted rows (color authority from PaddleOCR)
- Match specific keywords accurately (text authority from Gemini)
- Click precise center of row (coordinate authority from PaddleOCR)

**Results**:
- **Accuracy**: 97% vs 87% with single-engine approach
- **Precision**: Pixel-perfect (<5px error)
- **Trade-off**: +4 seconds processing time, API costs of ~$0.002/image

**Why It Matters**:
Solved a production problem where PaddleOCR was misreading account numbers (O/0, S/5 confusion). The hybrid approach increased reliability significantly while maintaining automation speed.

---

### Project 4: Ollama FAISS RAG System
**Repository**: [ollama-faiss-rag](https://github.com/Vasanthsoundararajan2002/ollama-faiss-rag)  
**Type**: Privacy-focused RAG implementation  
**Technologies**: Ollama Llama 3.2 3B, FAISS, sentence-transformers

**What It Does**:
Local document Q&A system with zero cloud dependency:
1. Load employee PDF documents
2. Split into 500-character chunks (optimal for accuracy)
3. Create embeddings using sentence-transformers
4. Store in FAISS vector index
5. Query → Semantic search → Context retrieval
6. Context + Query → Local LLM → Answer

**Technical Stack**:
- **Vector DB**: FAISS (Facebook AI Similarity Search)
- **Embeddings**: sentence-transformers/all-MiniLM-L6-v2
- **LLM**: Ollama Llama 3.2 (3B parameters, runs locally)
- **PDF Processing**: PyPDF2
- **Pure Python**: No LangChain dependencies

**Why Pure Python?**:
To understand RAG fundamentals without abstraction layers. Built everything from scratch:
- PDF text extraction
- Chunk management
- Embedding generation
- Vector similarity search
- LLM prompt engineering

**Performance**:
- **Retrieval Speed**: <1 second per query
- **Accuracy**: 88%+ relevant context retrieval
- **Privacy**: 100% local processing
- **Memory**: Runs on 4GB RAM

**Key Learning**:
Understanding how RAG systems work under the hood - from vector embeddings to semantic search to context injection. No magic frameworks, just pure understanding.

---

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

### 6. FAISS for RAG

```bash
# Install FAISS
pip install faiss-cpu  # For CPU
# OR
pip install faiss-gpu  # For GPU

# Additional dependencies
pip install sentence-transformers
pip install chromadb  # Alternative vector DB

# Verify
python -c "import faiss; print('FAISS ready!')"
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
pip install pandas numpy matplotlib openpyxl

# Save requirements
pip freeze > requirements.txt
```

---

## 📚 Key Learnings & Insights

### 1. **Hybrid Approaches Win**
Single-tool solutions often have limitations. Combining complementary technologies (like PaddleOCR + Gemini) yields superior results. The Authority Model pattern is extensible to other domains.

### 2. **Local vs Cloud Trade-offs**
- **Local (Ollama, PaddleOCR)**: Privacy, no costs, full control, but limited by hardware
- **Cloud (Gemini API)**: Superior performance, scalability, but costs and latency
- **Best Practice**: Use local for development/testing, cloud for production accuracy

### 3. **Production vs Prototype**
Working on Droidal's enterprise tool taught me the difference:
- **Prototype**: Fast iteration, proof of concept
- **Production**: Error handling, edge cases, user experience, scalability
- Both skills are valuable for different contexts

### 4. **Understanding Fundamentals**
Building RAG from scratch (without LangChain) gave me deep understanding of:
- How embeddings capture semantic meaning
- Vector similarity search mechanics
- Context window management
- Prompt engineering for local LLMs

### 5. **Document Intelligence is Hard**
PDFs are deceptively complex:
- Scanned vs text-based require different approaches
- Space preservation is critical
- Layout understanding matters
- Multi-page documents need smart splitting logic
- Each document type (medical, financial, legal) has unique challenges

### 6. **OCR Best Practices**
1. **Preprocessing is crucial**: Image quality directly impacts OCR accuracy
2. **Hybrid approaches work best**: Combine multiple OCR engines based on document type
3. **Confidence scoring**: Always validate OCR output quality
4. **Space handling**: Critical for maintaining document structure

### 7. **PDF Processing Insights**
1. **Use Fitz for spatial awareness**: Bounding boxes preserve layout information
2. **Keyword-based extraction**: More accurate than full-page processing
3. **Scanned vs Text PDFs**: Different strategies required

### 8. **LLM Integration**
1. **Start local, scale to cloud**: Ollama for development, Gemini for production
2. **Context matters**: Better prompts = better results
3. **Cost optimization**: Use appropriate model sizes

---

## 📈 Skills Progression

### Document Processing Journey
```
pdfplumber (Basic extraction)
    ↓
PyMuPDF/Fitz (Spatial awareness + space handling)
    ↓
Tesseract OCR (Traditional OCR fundamentals)
    ↓
PaddleOCR (Deep learning OCR, 80% accuracy)
    ↓
DocTR (Advanced DL OCR, 90% accuracy)
    ↓
Gemini Vision (AI-powered extraction, 95% accuracy)
    ↓
Hybrid Systems (98% accuracy, combining best of both)
```

### LLM Integration Path
```
Prompt Engineering (Manual)
    ↓
Ollama Local Models (Llama 3.2 3B)
    ↓
RAG Architecture (FAISS + embeddings)
    ↓
Gemini API Integration (Vision models)
    ↓
Production Pipelines (Error handling, batch processing)
    ↓
Voice AI (Gemini 3-type APIs)
```

### Automation Evolution
```
Simple scripts
    ↓
Selenium web automation
    ↓
Multi-platform orchestration (Web + Desktop + Excel)
    ↓
Visual workflow designer
    ↓
Enterprise-grade RPA platform (Droidal)
```

---

## 🛠️ Technical Toolkit

### Languages & Frameworks
- **Python** (Primary): 1.4 years production experience
- **Libraries Mastered**: 
  - Automation: Selenium, PyAutoGUI, pywinauto
  - OCR: Tesseract, PaddleOCR, DocTR
  - PDF: PyMuPDF (Fitz), pdfplumber, PyPDF2
  - AI/ML: google-generativeai, sentence-transformers
  - Computer Vision: OpenCV, Pillow
  - Data: pandas, openpyxl, numpy
  - Vector DB: FAISS

### Cloud & APIs
- Google Gemini (2.0 Flash, 2.0 Experimental, 2.5, Vision models)
- Ollama (Local LLM deployment)
- REST API integration

### Development Practices
- Git version control
- Modular architecture design
- Error handling & logging
- Documentation
- Code review participation (Droidal team)

---

## 💼 Professional Experience

### Droidal - Software Developer (Product Team)
**Duration**: 1.4 years  
**Location**: India  
**Role**: Building enterprise RPA automation tool

**Responsibilities**:
- Develop automation engine supporting Web, Desktop, and Excel platforms
- Design and implement new automation capabilities
- Work with product team to translate requirements into features
- Maintain and optimize existing automation workflows
- Collaborate on architecture decisions for scalability

**Tech Stack Used Daily**:
- Python for backend logic
- Selenium for web automation
- PyAutoGUI for desktop UI interaction
- openpyxl for Excel automation
- PyMuPDF for PDF processing
- Tkinter for UI components

**Key Contributions**:
- Built modular automation step architecture
- Implemented visual workflow representation
- Designed error handling framework
- Contributed to multi-platform execution engine

**What I Learned**:
- Enterprise software design patterns
- Production-grade error handling
- User experience for non-technical users
- Working in collaborative development environment
- Code review and quality standards
- Balancing feature requests with technical debt

---

## 🎯 What Makes My Work Unique

### 1. **Real-World Production Experience**
Unlike many GitHub portfolios, my work is informed by 1.4 years building actual enterprise software at Droidal. I understand the gap between prototypes and production systems.

### 2. **Novel Architectures**
The Hybrid OCR Authority Model isn't a tutorial project - it's an original solution to a real problem I encountered. It demonstrates systems thinking.

### 3. **End-to-End Thinking**
My projects aren't just "call an API and display results":
- Image preprocessing for better OCR
- Multi-stage pipelines with error handling
- Data transformation and export
- User experience considerations
- Performance optimization

### 4. **Depth Over Breadth**
I prefer mastering one domain (document intelligence & automation) deeply rather than superficial knowledge across many areas. Each project builds on previous learnings.

### 5. **Production Mindset**
Even in personal projects, I consider:
- Error handling
- Logging and debugging
- Configuration management
- Documentation
- Scalability

---

## 📊 Impact & Metrics

### Enterprise Tool (Droidal)
- **Users**: Thousands of automation workflows running
- **Platforms**: 3 (Web, Desktop, Excel)
- **Automation Steps**: 30+ different action types
- **Uptime**: Production-grade reliability

### Personal Projects
- **FlowBot**: Prototype demonstrating RPA concepts
- **Medical Pipeline**: 90-95% extraction accuracy, 2-3s per page
- **Hybrid OCR**: 97% accuracy (vs 87% baseline)
- **RAG System**: <1s query latency, 100% local

---

## 🎓 Skills Developed

- ✅ OCR Engine Selection & Optimization
- ✅ PDF Processing & Text Extraction
- ✅ Deep Learning Model Integration
- ✅ LLM Prompt Engineering
- ✅ Vector Database Management
- ✅ API Integration (Gemini, OpenAI-compatible APIs)
- ✅ Accuracy Measurement & Optimization
- ✅ Production Pipeline Design
- ✅ Enterprise RPA Development
- ✅ Modular Architecture Design
- ✅ RAG System Implementation
- ✅ Hybrid AI/ML Approaches

---

## 🚀 Current Focus (January 2025)

1. **Deepening AI Integration**: Exploring Gemini 2.5 Flash capabilities
2. **Voice AI**: Integration with Gemini 3-type APIs
3. **Production RAG**: Scaling RAG systems for enterprise use
4. **Multimodal AI**: Combining vision, text, and structured data
5. **Workflow Optimization**: Making automation tools more intuitive
6. **Documentation Intelligence**: Advanced document understanding pipelines

---

## 🔮 Future Exploration

**Near-term** (Q1-Q2 2025):
- [ ] Voice AI integration (Gemini 3-type APIs)
- [ ] Advanced RAG architectures (hybrid search, re-ranking)
- [ ] Multi-agent workflows
- [ ] Fine-tuning smaller LLMs for specific tasks

**Medium-term** (2025):
- [ ] Real-time document processing pipelines
- [ ] Integration with enterprise systems (CRM, ERP)
- [ ] Automated workflow generation from natural language
- [ ] Custom OCR model training

**Long-term Vision**:
Building intelligent automation systems that combine the best of:
- Traditional RPA (speed, reliability)
- Computer Vision (visual understanding)
- LLMs (context, reasoning)
- Domain expertise (healthcare, finance, legal)

---

## 📫 Connect With Me

- 💼 **LinkedIn**: [linkedin.com/in/vasanthsa](https://www.linkedin.com/in/vasanthsa/)
- 📧 **Email**: [vasanthsoundararajan95@gmail.com](mailto:vasanthsoundararajan95@gmail.com)
- 🌐 **GitHub**: [github.com/Vasanthsoundararajan2002](https://github.com/Vasanthsoundararajan2002)
- 🏢 **Company**: [Droidal](https://droidal.com)

---

## 🙏 Acknowledgments

**Droidal Team**: For the opportunity to work on enterprise RPA and learn production software development

**Open Source Community**: 
- PaddleOCR developers
- DocTR project
- Google Gemini AI team
- Ollama project
- FAISS creators
- PyMuPDF maintainers

**Inspiration**: Enterprise automation platforms (UiPath, Automation Anywhere, Blue Prism) that showed what's possible with workflow orchestration

---

## 📜 License

All personal projects are released under MIT License - see individual repositories for details.

---

<div align="center">

**⭐ If my work interests you, consider starring my repositories!**

*"From traditional OCR to cutting-edge AI - building the future of intelligent automation"*

**Last Updated**: January 30, 2025  
**Status**: Actively Learning & Building 🔥

</div>
