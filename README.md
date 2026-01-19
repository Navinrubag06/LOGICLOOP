# **EduGuard – AI-Driven Personalized Learning Platform**

EduGuard is an AI-driven personalized learning platform designed to **assist teachers without replacing them**.
The system generates lessons, quizzes, and learning materials **strictly from teacher-uploaded curriculum documents**, ensuring safety, transparency, and full teacher control.

---

## **Key Highlights**

* Curriculum-grounded AI (no hallucinations)
* Teacher-in-the-loop approval workflow
* AI Decision Trace for transparency
* AI Pre-Mortem (Failure Simulation Mode)
* Personalized quizzes and feedback
* Student cognitive load monitoring
* AI misuse and safety detection
* OCR support for scanned documents
* Video and audio learning content generation

---

## **System Requirements**

* Windows 10 / 11 (64-bit)
* Python 3.10 or 3.11
* Minimum 8 GB RAM (16 GB recommended)
* Stable internet connection

---

## **Installation (Clean Setup on New Laptop)**

### **1. Install Python**

Download and install Python from:
[https://www.python.org/downloads/](https://www.python.org/downloads/)

During installation:

* ✔ Add Python to PATH
* ✔ Install for all users

Verify:

```powershell
python --version
pip --version
```

---

### **2. Clone Repository**

```powershell
git clone <your-repository-url>
cd <your-project-folder>
```

---

### **3. Create and Activate Virtual Environment**

```powershell
python -m venv lagai_env
lagai_env\Scripts\activate
```

---

### **4. Install Python Dependencies**

```powershell
pip install --upgrade pip
pip install streamlit groq numpy
pip install pymupdf python-docx python-pptx
pip install pytesseract pdf2image pillow
pip install moviepy edge-tts
pip install aiofiles requests
```

---

### **5. Install System-Level Dependencies**

#### **Tesseract OCR**

Download:
[https://github.com/UB-Mannheim/tesseract/wiki](https://github.com/UB-Mannheim/tesseract/wiki)

* Install English language
* ✔ Add to PATH

Verify:

```powershell
tesseract --version
```

---

#### **Poppler (Required for PDF OCR)**

Download:
[https://github.com/oschwartz10612/poppler-windows/releases](https://github.com/oschwartz10612/poppler-windows/releases)

Steps:

1. Extract to:

```
C:\poppler
```

2. Add to PATH:

```
C:\poppler\Library\bin
```

Verify:

```powershell
pdftoppm -h
```

---

#### **FFmpeg (Required for Video Generation)**

Download:
[https://www.gyan.dev/ffmpeg/builds/](https://www.gyan.dev/ffmpeg/builds/)

* Download **ffmpeg-8.0.1-essentials_build**
* Extract to:

```
C:\ffmpeg
```

* Add to PATH:

```
C:\ffmpeg\bin
```

Verify:

```powershell
ffmpeg -version
```

---

### **6. Environment Variable**

Set your Groq API key:

```powershell
setx GROQ_API_KEY "your_api_key_here"
```

Restart terminal after setting.

---

### **7. Optional Safety Fallback**

Add this in code if PATH issues occur:

```python
import pytesseract
pytesseract.pytesseract.tesseract_cmd = r"C:\Program Files\Tesseract-OCR\tesseract.exe"
```

---

### **8. Run the Application**

```powershell
streamlit run app.py
```

---

## **Notes**

* OCR enables reading scanned or image-based curriculum files.
* AI will refuse to generate content if curriculum information is missing.
* Teachers must approve AI-generated content before use.

---

## **Project Philosophy**

> This is not AI that replaces teachers.
> This is AI that explains itself, respects curriculum boundaries, and knows when to step back.

---

## **License**

This project is intended for educational and hackathon demonstration purposes.
