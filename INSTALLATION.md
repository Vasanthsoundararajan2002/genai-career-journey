# Complete Installation Guide for Gen AI Stack

## Table of Contents
1. [System Requirements](#system-requirements)
2. [Tesseract OCR](#tesseract-ocr)
3. [PaddleOCR](#paddleocr)
4. [DocTR](#doctr)
5. [PyMuPDF (Fitz)](#pymupdf-fitz)
6. [Ollama & Local LLMs](#ollama--local-llms)
7. [FAISS & Vector Databases](#faiss--vector-databases)
8. [Gemini API](#gemini-api)
9. [Complete Environment Setup](#complete-environment-setup)
10. [Troubleshooting](#troubleshooting)

---

## System Requirements

### Minimum Requirements
- **OS**: Ubuntu 20.04+, macOS 10.15+, or Windows 10+
- **RAM**: 8GB (16GB recommended)
- **Storage**: 20GB free space
- **Python**: 3.8 or higher

### Recommended for Deep Learning
- **GPU**: NVIDIA GPU with 6GB+ VRAM
- **CUDA**: 11.7 or higher
- **cuDNN**: 8.5 or higher
- **RAM**: 16GB+

---

## 1. Tesseract OCR

### Ubuntu/Debian
```bash
# Update package list
sudo apt update

# Install Tesseract OCR
sudo apt install tesseract-ocr

# Install development libraries
sudo apt install libtesseract-dev

# Install additional language packs (optional)
sudo apt install tesseract-ocr-eng tesseract-ocr-spa
```

### macOS
```bash
# Using Homebrew
brew install tesseract

# Install additional languages
brew install tesseract-lang
```

### Windows
```bash
# Download installer from: https://github.com/UB-Mannheim/tesseract/wiki
# Or use Chocolatey
choco install tesseract
```

### Python Wrapper
```bash
pip install pytesseract pillow
```

### Verify Installation
```python
import pytesseract
from PIL import Image

# Check version
print(pytesseract.get_tesseract_version())

# Test OCR
img = Image.new('RGB', (100, 30), color='white')
text = pytesseract.image_to_string(img)
print("Tesseract is working!")
```

---

## 2. PaddleOCR

### Prerequisites
```bash
# Install OpenCV
pip install opencv-python opencv-python-headless
```

### Install PaddlePaddle

#### For CPU
```bash
pip install paddlepaddle==2.6.0
```

#### For GPU (CUDA 11.7)
```bash
pip install paddlepaddle-gpu==2.6.0.post117 -f https://www.paddlepaddle.org.cn/whl/linux/mkl/avx/stable.html
```

#### For GPU (CUDA 12.0)
```bash
pip install paddlepaddle-gpu==2.6.0.post120 -f https://www.paddlepaddle.org.cn/whl/linux/mkl/avx/stable.html
```

### Install PaddleOCR
```bash
pip install paddleocr
```

### Verify Installation
```python
from paddleocr import PaddleOCR

# Initialize with English language
ocr = PaddleOCR(use_angle_cls=True, lang='en')

print("PaddleOCR installed successfully!")
```

### Download Additional Language Models
```bash
# The models will be downloaded automatically on first use
# Or manually download from:
# https://github.com/PaddlePaddle/PaddleOCR/blob/release/2.7/doc/doc_en/models_list_en.md
```

---

## 3. DocTR

### Prerequisites
Install PyTorch first (recommended) or TensorFlow

#### PyTorch Installation (Recommended)

**For CPU**:
```bash
pip install torch torchvision torchaudio
```

**For GPU (CUDA 11.8)**:
```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```

**For GPU (CUDA 12.1)**:
```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
```

#### TensorFlow Installation (Alternative)
```bash
pip install tensorflow==2.13.0
```

### Install DocTR

**With PyTorch backend**:
```bash
pip install python-doctr[torch]
```

**With TensorFlow backend**:
```bash
pip install python-doctr[tf]
```

### Additional Dependencies
```bash
pip install matplotlib shapely
```

### Verify Installation
```python
from doctr.models import ocr_predictor
from doctr.io import DocumentFile

# Load predictor
model = ocr_predictor(pretrained=True)

print(f"DocTR loaded successfully!")
print(f"Available architectures: {model.det_predictor.model.__class__.__name__}")
```

---

## 4. PDF Processing Tools

### pdfplumber

**Purpose**: Text extraction from digital PDFs with table support

```bash
# Install pdfplumber
pip install pdfplumber
```

**Verify Installation**:
```python
import pdfplumber

# Test with a simple PDF
with pdfplumber.open("sample.pdf") as pdf:
    first_page = pdf.pages[0]
    text = first_page.extract_text()
    print("pdfplumber is working!")
```

**Common Use Cases**:
```python
import pdfplumber

# Extract text
with pdfplumber.open("document.pdf") as pdf:
    for page in pdf.pages:
        text = page.extract_text()
        print(text)

# Extract tables
with pdfplumber.open("document.pdf") as pdf:
    for page in pdf.pages:
        tables = page.extract_tables()
        for table in tables:
            print(table)
```

### PyMuPDF (Fitz)

**Purpose**: Advanced PDF processing with spatial awareness and better space handling

### Installation
```bash
# Basic installation
pip install PyMuPDF

# With all optional features
pip install PyMuPDF[extras]
```

### Verify Installation
```python
import fitz

print(f"PyMuPDF version: {fitz.version}")
print(f"PyMuPDF is ready!")

# Test basic functionality
doc = fitz.open()  # Create empty PDF
print(f"Empty PDF created successfully")
```

### Common Use Case Example
```python
import fitz

def extract_text_with_positions(pdf_path):
    doc = fitz.open(pdf_path)
    for page_num in range(len(doc)):
        page = doc[page_num]
        text_dict = page.get_text("dict")
        blocks = text_dict["blocks"]
        print(f"Page {page_num + 1}: {len(blocks)} blocks found")
    doc.close()
```

---

## 5. Ollama & Local LLMs

### Install Ollama

#### Linux
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

#### macOS
```bash
# Download from https://ollama.com/download
# Or use Homebrew
brew install ollama
```

#### Windows
```bash
# Download installer from https://ollama.com/download
```

### Start Ollama Service
```bash
# Linux/macOS
ollama serve

# Windows - it starts automatically
```

### Pull LLM Models
```bash
# Llama 3 - 3B (Fast, lightweight)
ollama pull llama3:3b

# Llama 3 - 8B (Balanced)
ollama pull llama3:8b

# Mistral 7B (Excellent reasoning)
ollama pull mistral:7b

# Check installed models
ollama list
```

### Test Models
```bash
# Interactive chat
ollama run llama3:3b

# Single query
ollama run llama3:3b "What is OCR?"
```

### Python Integration
```bash
pip install ollama
```

```python
import ollama

response = ollama.chat(model='llama3:3b', messages=[
    {'role': 'user', 'content': 'Explain OCR in simple terms'}
])

print(response['message']['content'])
```

---

## 6. FAISS & Vector Databases

### Install FAISS

**For CPU**:
```bash
pip install faiss-cpu
```

**For GPU**:
```bash
pip install faiss-gpu
```

### Install Supporting Libraries
```bash
# Sentence transformers for embeddings
pip install sentence-transformers

# LangChain for RAG
pip install langchain langchain-community

# Alternative vector databases
pip install chromadb  # ChromaDB
pip install qdrant-client  # Qdrant
```

### Verify Installation
```python
import faiss
import numpy as np

# Create a simple index
d = 128  # dimension
nb = 1000  # database size
xb = np.random.random((nb, d)).astype('float32')

index = faiss.IndexFlatL2(d)
index.add(xb)

print(f"FAISS index created with {index.ntotal} vectors")
```

### Install Embedding Models
```python
from sentence_transformers import SentenceTransformer

# Download a model (first time only)
model = SentenceTransformer('all-MiniLM-L6-v2')
print("Embedding model ready!")
```

---

## 7. Gemini API

### Install Google Generative AI
```bash
pip install google-generativeai
```

### Get API Key
1. Go to [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Create an API key
3. Save it securely

### Set Up API Key

**Linux/macOS**:
```bash
# Add to ~/.bashrc or ~/.zshrc
export GOOGLE_API_KEY='your-api-key-here'

# Reload shell
source ~/.bashrc
```

**Windows**:
```bash
# PowerShell
$env:GOOGLE_API_KEY='your-api-key-here'

# Command Prompt
set GOOGLE_API_KEY=your-api-key-here
```

### Python Configuration
```python
import google.generativeai as genai

# Option 1: Use environment variable
import os
genai.configure(api_key=os.environ['GOOGLE_API_KEY'])

# Option 2: Direct configuration (not recommended for production)
genai.configure(api_key='your-api-key-here')
```

### Test Gemini API
```python
import google.generativeai as genai

genai.configure(api_key='your-api-key')

# Test with Gemini 2.5 Flash
model = genai.GenerativeModel('gemini-2.0-flash-exp')
response = model.generate_content("What is OCR?")

print(response.text)
```

### Available Models
```python
# List all available models
for model in genai.list_models():
    print(f"{model.name}: {model.description}")
```

---

## 8. Complete Environment Setup

### Create Project Structure
```bash
mkdir genai-project
cd genai-project

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Linux/macOS:
source venv/bin/activate
# Windows:
venv\Scripts\activate
```

### Install All Dependencies
```bash
# Create requirements.txt
cat > requirements.txt << EOF
# OCR Engines
pytesseract==0.3.10
paddleocr==2.7.0
python-doctr[torch]==0.8.1

# PDF Processing
PyMuPDF==1.23.8
pdfplumber==0.10.3

# Image Processing
opencv-python==4.8.1.78
pillow==10.1.0

# Deep Learning
torch==2.1.0
torchvision==0.16.0

# LLM & RAG
google-generativeai==0.3.1
langchain==0.1.0
langchain-community==0.0.10
sentence-transformers==2.2.2
faiss-cpu==1.7.4
ollama==0.1.6

# Utilities
numpy==1.24.3
pandas==2.0.3
matplotlib==3.7.2
tqdm==4.66.1
EOF

# Install all packages
pip install -r requirements.txt
```

### Verify Complete Installation
```python
# test_installation.py
import sys

def test_imports():
    tests = {
        'Tesseract': lambda: __import__('pytesseract'),
        'PaddleOCR': lambda: __import__('paddleocr'),
        'DocTR': lambda: __import__('doctr'),
        'PyMuPDF': lambda: __import__('fitz'),
        'pdfplumber': lambda: __import__('pdfplumber'),
        'PyTorch': lambda: __import__('torch'),
        'FAISS': lambda: __import__('faiss'),
        'LangChain': lambda: __import__('langchain'),
        'Gemini': lambda: __import__('google.generativeai'),
        'Ollama': lambda: __import__('ollama'),
    }
    
    print("Testing installations...\n")
    for name, test_func in tests.items():
        try:
            test_func()
            print(f"✅ {name}: OK")
        except ImportError as e:
            print(f"❌ {name}: FAILED - {e}")
    
    print("\n--- GPU Availability ---")
    try:
        import torch
        print(f"CUDA available: {torch.cuda.is_available()}")
        if torch.cuda.is_available():
            print(f"GPU: {torch.cuda.get_device_name(0)}")
    except:
        print("PyTorch not available")

if __name__ == "__main__":
    test_imports()
```

Run the test:
```bash
python test_installation.py
```

---

## 9. Troubleshooting

### Common Issues

#### Issue 1: CUDA Not Found
```bash
# Check CUDA installation
nvcc --version

# Install CUDA toolkit
# Ubuntu:
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-ubuntu2204.pin
sudo mv cuda-ubuntu2204.pin /etc/apt/preferences.d/cuda-repository-pin-600
sudo apt-get install cuda-toolkit-11-8
```

#### Issue 2: PaddleOCR Model Download Fails
```bash
# Set proxy if needed
export HTTP_PROXY=http://proxy.example.com:8080
export HTTPS_PROXY=http://proxy.example.com:8080

# Or download models manually from:
# https://github.com/PaddlePaddle/PaddleOCR/blob/release/2.7/doc/doc_en/models_list_en.md
```

#### Issue 3: Tesseract Not Found
```bash
# Add Tesseract to PATH
# Windows: Add C:\Program Files\Tesseract-OCR to PATH
# Linux: export PATH=$PATH:/usr/local/bin

# Or set in Python
import pytesseract
pytesseract.pytesseract.tesseract_cmd = r'C:\Program Files\Tesseract-OCR\tesseract.exe'
```

#### Issue 4: Out of Memory (GPU)
```python
# Reduce batch size
import torch
torch.cuda.empty_cache()

# Use CPU for some operations
device = 'cpu' if not torch.cuda.is_available() else 'cuda'
```

#### Issue 5: Ollama Connection Error
```bash
# Check if Ollama is running
curl http://localhost:11434/api/tags

# Start Ollama service
ollama serve

# Check logs
journalctl -u ollama -f
```

---

## Quick Start Commands

### All-in-One Installation (Linux/macOS)
```bash
#!/bin/bash

# Install system packages
sudo apt update
sudo apt install -y tesseract-ocr libtesseract-dev python3-pip

# Install Python packages
pip install --upgrade pip
pip install pytesseract paddleocr python-doctr[torch] PyMuPDF pdfplumber
pip install google-generativeai langchain faiss-cpu sentence-transformers
pip install torch torchvision opencv-python pillow numpy pandas

# Install Ollama
curl -fsSL https://ollama.com/install.sh | sh
ollama pull llama3:3b

echo "Installation complete!"
```

### Verify Everything
```bash
python -c "import pytesseract, paddleocr, doctr, fitz, pdfplumber, faiss, torch; print('All packages installed!')"
```

---

## Next Steps

1. ✅ Verify all installations
2. ✅ Configure API keys
3. ✅ Test with sample data
4. ✅ Start building your pipelines!

For more help, refer to official documentation:
- [Tesseract](https://tesseract-ocr.github.io/)
- [PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR)
- [DocTR](https://mindee.github.io/doctr/)
- [PyMuPDF](https://pymupdf.readthedocs.io/)
- [pdfplumber](https://github.com/jsvine/pdfplumber)
- [Ollama](https://ollama.com/docs)
- [Gemini API](https://ai.google.dev/docs)
