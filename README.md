# 🚀 NLP-as-a-Service — CLI-Based NLP Dashboard

An **interactive Natural Language Processing toolkit** built as a **menu-driven CLI application inside Google Colab**.

The system allows users to perform advanced NLP tasks such as **Named Entity Recognition**, **Emotion Analysis**, and **Language Detection**.

All NLP tasks are powered by **cloud-hosted AI models via NLPCloud APIs**.

This project demonstrates **API-based AI integration**, **CLI application design**, and **modular Python architecture**.

---

## 🚀 Features

- 🖥 **Interactive CLI dashboard**
- 🔐 **User authentication system**
- 🤖 **Multi-model NLP integration**
- 🌍 **Language detection for 50+ languages**
- 📊 **Emotion detection with confidence scoring**
- ⚡ **Cloud-based NLP model inference**
- 📦 **Structured JSON response processing**

---

## 🧠 What This Project Demonstrates

This project highlights the following **AI engineering and backend skills**:

- **Integration of multiple NLP models via APIs**
- **Command-line interface application design**
- **Object-Oriented Programming in Python**
- **Parsing structured JSON responses**
- **API-based AI services architecture**
- **Building modular AI-powered tools**

---

## 📂 Project Structure

```
NLP_CLI_APP/
│
├── nlp_app.py            # Main CLI application
├── auth.py               # User authentication system
├── nlp_models.py         # NLP API integration layer
├── utils.py              # Helper functions
│
├── .gitignore
└── README.md
```

---

## ⚙️ Architecture Overview

The system follows a **modular CLI architecture**.

```
User Input
      │
      ▼
CLI Menu Interface
      │
      ▼
Application Controller
(NLPAPP Class)
      │
      ▼
NLPCloud API
      │
      ▼
Response Processing
      │
      ▼
Formatted Output
Displayed to User
```

### Design Principles

- **Separation of Concerns**
- **Reusable NLP modules**
- **Clean API integration layer**
- **User-friendly CLI interaction**

---

## 📊 AI Models Used

### 🧠 GPT-OSS-120B — Named Entity Recognition

This model is used for **entity extraction tasks**.

Why this model?

- Large parameter size enables **strong contextual understanding**
- Accurate extraction of **complex entities**
- Performs better than lightweight local models

Entities detected include:

- Person
- Organization
- Location
- Custom entity queries

---

### 🤖 DistilBERT — Emotion Detection

Traditional sentiment analysis usually returns:

- Positive
- Negative

DistilBERT provides **fine-grained emotional classification** including:

- Joy
- Sadness
- Anger
- Fear
- Surprise
- Neutral

This provides **richer emotional insights**.

---

### 🌍 Python-LangDetect — Language Identification

This library was selected because it is:

- Lightweight
- Fast
- Optimized for **character-level language detection**

Supports **50+ languages**.

---

## ⚙ Core Logic — Dominant Emotion Extraction

Instead of printing raw JSON responses, the system extracts the **emotion with the highest confidence score**.

```python
scores = [i['score'] for i in response['scored_labels']]

index = sorted(list(enumerate(scores)), key=lambda x: x[1], reverse=True)[0][0]

print(response['scored_labels'][index]['label'])
```

This ensures **clear and interpretable output** for users.

---

## 🔌 API Endpoints Used

### Named Entity Recognition

```
client.entities(para, searched_entity=word)
```

---

### Emotion Detection

```
client.sentiment(para)
```

---

### Language Detection

```
client.langdetection(para)
```

---

## 🛠 Installation

### Open Google Colab

Create a new notebook.

---

### Install required library

```bash
!pip install nlpcloud
```

---

### Add application code

Copy the **NLPAPP class implementation** into a Colab cell.

---

### Add API key

Insert your **NLPCloud API token** when initializing the client.

---

### Run the application

```python
obj = NLPAPP()
```

Use the CLI prompts to interact with the NLP system.

---

## 🧪 Example Workflow

1. **User registers or logs into the system**
2. User selects an **NLP task from the CLI menu**
3. User submits **text for analysis**
4. System sends request to **NLPCloud API**
5. API response is **parsed and processed**
6. Clean NLP results are displayed to the user

---

## 📈 Potential Improvements

Future enhancements could include:

- Secure password masking using **getpass**
- Persistent user storage with **Google Drive**
- Export results to **CSV or TXT files**
- Convert CLI application into **Streamlit web interface**
- Add additional NLP tasks such as:
  - Text summarization
  - Translation
  - Keyword extraction

---

## 🧰 Tech Stack

| Technology | Purpose |
|-----------|---------|
| Python | Programming language |
| NLPCloud | NLP model API provider |
| DistilBERT | Emotion detection |
| GPT-OSS-120B | Named entity recognition |
| Python-LangDetect | Language detection |
| JSON | API response parsing |
| Google Colab | Development environment |
| CLI | User interface |

---

## 🎯 Learning Outcomes

This project helped build understanding of:

- **Object-Oriented Programming in Python**
- **API-based AI service integration**
- **Multi-model NLP system design**
- **CLI application architecture**
- **JSON response parsing and data processing**

---

## 👤 Author

**Rudra Tyagi**

B.Tech Final Year Student  
Aspiring **MLOps Engineer**
