**🚀 NLP-as-a-Service — CLI-Based NLP Dashboard**


An interactive Natural Language Processing toolkit built as a menu-driven CLI application inside Google Colab.

The system allows users to perform advanced NLP tasks such as:

Named Entity Recognition

Emotion Analysis

Language Detection

All powered by cloud-hosted AI models via NLPCloud APIs.

**📌 Project Overview**

This project demonstrates how multiple NLP models can be integrated into a single interactive system.

The application runs inside Google Colab and provides a structured command-line interface (CLI) where users can:

🔐 register and authenticate

📝 submit text for analysis

🤖 receive structured NLP insights

The project simulates a mini NLP platform, showcasing:

API integration

Object-Oriented Programming

Response parsing logic

**✨ Key Features**

| Feature                 | Description                                              |
| ----------------------- | -------------------------------------------------------- |
| 🖥 Interactive CLI      | Menu-driven NLP interface inside Google Colab            |
| 🔐 User Authentication  | Simulated login/register system using in-memory database |
| 🤖 Multi-Model NLP      | NER, Emotion Detection, and Language Identification      |
| 📊 Smart Output Parsing | Extracts the dominant emotion from model responses       |


**🧠 AI Models Used**
**GPT-OSS-120B — Named Entity Recognition**

Why this model?

Large parameter size enables better contextual understanding

Accurate extraction of complex entities

Performs better than lightweight local NER models

Entities detected include:

Person

Organization

Location

Custom entity queries

**DistilBERT — Emotion Detection**

Traditional sentiment analysis only outputs:

Positive

Negative

DistilBERT enables fine-grained emotional classification such as:

Joy

Sadness

Anger

Fear

Surprise

Neutral

This provides richer emotional insights from text.

**Python-LangDetect — Language Identification**

Chosen because it is:

lightweight

fast

optimized for character-level language detection

Supports detection across 50+ languages.

**🧰 Tech Stack**
| Layer                   | Technology                  |
| ----------------------- | --------------------------- |
| Programming             | Python                      |
| Development Environment | Google Colab                |
| NLP API Provider        | NLPCloud                    |
| Architecture            | Object-Oriented Programming |
| Data Handling           | JSON Parsing                |
| Interface               | CLI                         |


**🏗 Application Architecture**

User Input
     │
     ▼
CLI Menu Interface
     │
     ▼
NLPAPP Controller (Python Class)
     │
     ▼
NLPCloud API
     │
     ▼
Response Processing
     │
     ▼
User-Friendly Output


**⚙ Core Logic — Dominant Emotion Extraction**

Instead of printing raw JSON responses, the application extracts the emotion with the highest confidence score.

scores = [i['score'] for i in response['scored_labels']]

index = sorted(list(enumerate(scores)), key=lambda x: x[1], reverse=True)[0][0]

print(response['scored_labels'][index]['label'])


This ensures clear and interpretable output for the user.


**🔌 API Endpoints Used**

**Named Entity Recognition**
client.entities(para, searched_entity=word)

**Emotion Detection**
client.sentiment(para)

**Language Detection**
client.langdetection(para)


**🚀 How to Run the Project**

1️⃣ Open Google Colab

Create a new notebook.

2️⃣ Install Required Library

!pip install nlpcloud

3️⃣ Paste Application Code

Copy the NLPAPP class implementation into a notebook cell.

4️⃣ Add Your API Key

Insert your NLPCloud API token when initializing the client.

5️⃣ Start the Application

obj = NLPAPP()


Use the CLI input prompts to navigate the system.


**📚 Key Learning Outcomes**

This project demonstrates practical experience in:

Object-Oriented Programming in Python

REST API integration

Multi-model AI system design

JSON response parsing

CLI application development

**🔮 Future Improvements**

Planned upgrades:

🔐 Password masking using getpass

💾 Persistent user storage with Google Drive

📁 Export results to CSV / TXT

🌐 Convert CLI tool into Streamlit web app

➕ Add NLP tasks like text summarization and translation

**👨‍💻 Author**

Rudra Tyagi

AI / ML Engineer
AWS & Machine Learning Enthusiast

📄 License

This project is licensed under the MIT License.
