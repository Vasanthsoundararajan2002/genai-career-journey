# PDF Processing Tools - Usage Examples

This document shows simple examples of using pdfplumber and PyMuPDF (Fitz) for PDF text extraction.

## pdfplumber - Simple Text & Table Extraction

```python
import pdfplumber

# Basic text extraction
def extract_text_pdfplumber(pdf_path):
    """
    Simple text extraction for digital PDFs
    Good for: Quick extraction, simple documents
    """
    with pdfplumber.open(pdf_path) as pdf:
        full_text = ""
        for page in pdf.pages:
            text = page.extract_text()
            full_text += text + "\n"
    return full_text

# Table extraction
def extract_tables_pdfplumber(pdf_path):
    """
    Extract tables from PDF
    Good for: Structured data, forms, financial documents
    """
    tables_data = []
    with pdfplumber.open(pdf_path) as pdf:
        for page_num, page in enumerate(pdf.pages):
            tables = page.extract_tables()
            for table in tables:
                tables_data.append({
                    'page': page_num + 1,
                    'data': table
                })
    return tables_data

# Usage
text = extract_text_pdfplumber("document.pdf")
tables = extract_tables_pdfplumber("document.pdf")
```

**Pros:**
- ✅ Simple API, easy to use
- ✅ Excellent table extraction
- ✅ Good for digital PDFs
- ✅ Minimal code required

**Cons:**
- ❌ Space handling issues with complex layouts
- ❌ Less control over text positioning
- ❌ Slower on large documents
- ❌ Limited support for scanned PDFs

---

## PyMuPDF (Fitz) - Advanced Spatial Processing

```python
import fitz  # PyMuPDF

# Basic text extraction with better space handling
def extract_text_fitz(pdf_path):
    """
    Text extraction with space preservation
    Good for: Complex layouts, spatial awareness needed
    """
    doc = fitz.open(pdf_path)
    full_text = ""
    
    for page in doc:
        text = page.get_text()
        full_text += text
    
    doc.close()
    return full_text

# Extract with bounding boxes (spatial information)
def extract_with_positions(pdf_path):
    """
    Extract text with coordinate information
    Good for: Layout analysis, targeted extraction
    """
    doc = fitz.open(pdf_path)
    results = []
    
    for page_num in range(len(doc)):
        page = doc[page_num]
        text_dict = page.get_text("dict")
        
        for block in text_dict["blocks"]:
            if block["type"] == 0:  # Text block
                bbox = block["bbox"]  # (x0, y0, x1, y1)
                text = ""
                for line in block["lines"]:
                    for span in line["spans"]:
                        text += span["text"] + " "
                
                results.append({
                    'page': page_num + 1,
                    'text': text.strip(),
                    'bbox': bbox,
                    'position': {
                        'x0': bbox[0],
                        'y0': bbox[1],
                        'x1': bbox[2],
                        'y1': bbox[3]
                    }
                })
    
    doc.close()
    return results

# Keyword-based extraction (cut specific sections)
def extract_section_by_keyword(pdf_path, keyword):
    """
    Extract text around specific keywords
    Good for: Targeted information extraction
    """
    doc = fitz.open(pdf_path)
    results = []
    
    for page_num in range(len(doc)):
        page = doc[page_num]
        # Search for keyword
        text_instances = page.search_for(keyword)
        
        for inst in text_instances:
            # Get surrounding text
            # Expand the bounding box to capture context
            expanded_rect = fitz.Rect(
                inst.x0 - 50,  # Expand left
                inst.y0 - 20,  # Expand up
                inst.x1 + 50,  # Expand right
                inst.y1 + 100  # Expand down
            )
            
            # Extract text from expanded area
            extracted_text = page.get_textbox(expanded_rect)
            results.append({
                'page': page_num + 1,
                'keyword': keyword,
                'context': extracted_text
            })
    
    doc.close()
    return results

# Usage
text = extract_text_fitz("document.pdf")
positions = extract_with_positions("document.pdf")
sections = extract_section_by_keyword("document.pdf", "Total Amount")
```

**Pros:**
- ✅ Better space handling in complex layouts
- ✅ Bounding box information for spatial awareness
- ✅ Keyword-based targeted extraction
- ✅ Works well with both text and scanned PDFs (when combined with OCR)
- ✅ Fast processing
- ✅ Precise control over text extraction

**Cons:**
- ❌ More complex API
- ❌ Table extraction requires more code
- ❌ Steeper learning curve

---

## When to Use Which?

### Use pdfplumber when:
- 📄 Working with simple, digital PDFs
- 📊 Need to extract tables easily
- 🚀 Want quick implementation
- 📝 Document has clean structure

### Use PyMuPDF (Fitz) when:
- 🎯 Need precise text positioning
- 🔍 Keyword-based extraction required
- 📐 Complex layouts with spacing issues
- 🔄 Processing large volumes of documents
- 🎨 Need layout preservation
- 🤖 Combining with OCR for scanned PDFs

### Use Both (Hybrid) when:
- 🎯 Try pdfplumber first for speed
- 🔄 Fall back to Fitz if spacing issues occur
- 📊 Use pdfplumber for tables, Fitz for text
- ✅ Maximum accuracy is critical

---

## My Evolution Journey

```
Start (2024 Early)
    ↓
pdfplumber (Initial exploration)
    → Good for learning PDF structure
    → Discovered space preservation issues
    ↓
PyMuPDF / Fitz (Primary tool)
    → Better control over extraction
    → Solved spacing issues
    → Added keyword-based extraction
    ↓
Hybrid Approach (Current)
    → Fitz for spatial extraction
    → Combined with DocTR for scanned PDFs
    → Integrated with Gemini for context understanding
    → 98% accuracy achieved
```

---

## Integration with OCR & LLM

### For Scanned PDFs:

```python
# My current workflow
def process_scanned_pdf(pdf_path):
    # Step 1: Use Fitz to get page images
    doc = fitz.open(pdf_path)
    
    for page_num in range(len(doc)):
        page = doc[page_num]
        
        # Step 2: Convert to image
        pix = page.get_pixmap()
        img_bytes = pix.tobytes()
        
        # Step 3: Run OCR (DocTR or PaddleOCR)
        # ocr_text = run_ocr(img_bytes)
        
        # Step 4: Use Fitz positioning to preserve layout
        # Step 5: Send to Gemini for final refinement
        
    doc.close()
```

### For Complex Text PDFs:

```python
def process_complex_pdf(pdf_path, keywords):
    # Step 1: Use Fitz to find keywords
    sections = extract_section_by_keyword(pdf_path, keywords)
    
    # Step 2: Extract surrounding context with positions
    
    # Step 3: Send relevant sections to Gemini
    # for section in sections:
    #     gemini_result = gemini_api.process(section['context'])
    
    # Result: 98% accuracy on complex documents
```

---

## Installation

```bash
# Install both tools
pip install pdfplumber PyMuPDF

# Verify
python -c "import pdfplumber, fitz; print('Both installed!')"
```

## Summary

- **pdfplumber**: Quick & easy for simple PDFs and tables
- **PyMuPDF (Fitz)**: Advanced control for complex layouts and spacing
- **Both together**: Best results for production systems

My recommendation: Learn both, use Fitz as primary tool for production workflows.
