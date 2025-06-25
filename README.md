
# Document Metadata Generator

## Project Overview
  (open using colab i suggest)
  https://colab.research.google.com/drive/1gIeQc1k3fDgkqo39cVqQSpPbEic8yhPQ?authuser=1
  
*Document Metadata Generator* is an advanced Python-based document processing system that automatically extracts comprehensive metadata from various document formats including PDF, DOCX, and TXT files. The system features intelligent OCR capabilities for scanned documents and provides detailed semantic analysis including sentiment analysis, entity recognition, and automated summarization.

---

## Project Vision

To revolutionize document processing by providing an intelligent, accessible, and comprehensive metadata extraction system that transforms unstructured documents into actionable insights through advanced semantic analysis technologies.

---

## Core Features

### Document Processing Capabilities

- *Multi-format Support*: Processes PDF, DOCX, and TXT files seamlessly  
- *Intelligent OCR Integration*: Automatic fallback to OCR for scanned or image-based documents when regular text extraction yields insufficient content (less than 30 words)  
- *Smart Content Detection*: Automatically determines if a document needs OCR processing based on extracted text quality  

###  Advanced Text Extraction

- *PDF Processing*: Uses pdfplumber for digital PDF text extraction  
- *Word Document Processing*: Handles .docx files using python-docx library  
- *OCR Processing*: Uses pytesseract with pdf2image for scanned documents, limited to first 3 pages for performance  
- *Encoding Support*: Handles UTF-8 text files with proper encoding detection  

###  Comprehensive Semantic Analysis

- *Named Entity Recognition*: Extracts persons, organizations, locations, dates, monetary values, and events using spaCy NLP  
- *Keyword Extraction*: Identifies most relevant keywords using lemmatization and frequency analysis  
- *Document Summarization*: Generates concise summaries using extractive summarization with sentence ranking  
- *Sentiment Analysis*: Rule-based sentiment detection with confidence scoring (Positive / Negative / Neutral)  

###  Web Interface & User Experience

- *Flask Web Application*: User-friendly web interface for document upload and processing  
- *Real-time Processing*: Immediate metadata generation upon file upload  
- *File Size Validation*: Supports files up to 16MB  
- *Progress Feedback*: Detailed console output showing processing steps  

---

## Technological and System Architecture

###  System Architecture


Web Interface Layer  
(Flask Application + HTML UI)  
      │  
Processing Orchestration  
(Enhanced Metadata Generator)  
      │  
Document Extraction Layer │ Semantic Analysis Layer │ Metadata Generation Layer


---

###  Technology Stack

- *Document Processing*: pdfplumber, python-docx  
- *OCR Engine*: pytesseract, pdf2image  
- *NLP Processing*: spaCy (en_core_web_sm), NLTK  
- *Web Framework*: Flask  
- *Image Processing*: OpenCV, Pillow  
- *Data Storage*: JSON, File System  

---

## Web Application Structure

ngrok is a globally distributed reverse proxy that secures, protects, and accelerates applications by creating secure tunnels from public URLs to local development servers. It acts as your application's front door, making local services accessible over the internet.

The Flask application is initialized with:

python
app = Flask(__name__)


It provides a streamlined web interface for document processing. It handles secure file uploads with a 16MB size limit, processes documents through dedicated endpoints, delivers real-time feedback during analysis, and returns structured JSON responses for both web users and API integrations.
