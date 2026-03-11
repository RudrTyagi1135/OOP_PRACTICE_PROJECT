NLP-as-a-Service — CLI-Based NLP Dashboard

An interactive Natural Language Processing (NLP) toolkit built as a menu-driven CLI application inside Google Colab, enabling users to perform advanced text analysis tasks such as Named Entity Recognition, Language Detection, and Emotion Analysis using cloud-hosted AI models.

Project Overview

This project demonstrates how multiple NLP models can be integrated into a single interactive system using external AI APIs.

The application runs inside Google Colab and provides a structured command-line interface (CLI) where users can:

register and authenticate

submit text for analysis

receive structured NLP insights

The system simulates a mini NLP platform, showcasing API integration, OOP architecture, and response parsing logic.

Key Features

Interactive CLI Dashboard
Menu-driven NLP interface designed for the Google Colab console.

User Authentication Simulation
In-memory user database with registration and login logic.

Multi-Model NLP Processing

Named Entity Recognition

Emotion Detection

Language Identification

Intelligent Output Processing
Parses model responses and extracts the most probable emotion label rather than displaying raw JSON.

Why These AI Models?
GPT-OSS-120B — Named Entity Recognition

Reason for selection:

Large parameter size improves contextual understanding

More accurate extraction of complex entities compared to lightweight models

Handles ambiguous phrases effectively

Used for identifying:

organizations

locations

persons

domain-specific entities

DistilBERT Emotion Model

Standard sentiment analysis typically returns only:

Positive

Negative

This model provides fine-grained emotional classification, including:

Joy

Sadness

Anger

Fear

Surprise

Neutral

This produces richer psychological interpretation of text.

Python-LangDetect

Selected because it is:

lightweight

fast

optimized for character-level language detection

Supports 50+ languages with minimal computational overhead.

Tech Stack
Layer	Technology
Programming Language	Python
Development Environment	Google Colab
NLP API Provider	NLPCloud
Architecture	Object-Oriented Python
Data Handling	JSON / Dictionary Parsing
Interface	CLI-based interaction
Application Architecture

The entire application is encapsulated in a single class architecture.

Core Class
NLPAPP

Responsibilities:

user authentication

menu navigation

API interaction

response processing

result display

System workflow:

User Input
   ↓
CLI Menu Interface
   ↓
NLPAPP Controller
   ↓
NLPCloud API
   ↓
Response Processing
   ↓
Structured Output
Core Logic — Dominant Emotion Extraction

Instead of returning raw API output, the application extracts the emotion with the highest confidence score.

# Extract emotion scores
scores = [i['score'] for i in response['scored_labels']]

# Identify highest score index
index = sorted(list(enumerate(scores)), key=lambda x: x[1], reverse=True)[0][0]

# Print dominant emotion
print(response['scored_labels'][index]['label'])

This improves user readability and application usability.

API Implementation

The project integrates multiple NLPCloud endpoints.

Named Entity Recognition
client.entities(para, searched_entity=word)
Emotion Detection
client.sentiment(para)
Language Detection
client.langdetection(para)
How to Run the Project
1. Open Google Colab

Create a new notebook.

2. Install Required Library
!pip install nlpcloud
3. Paste Application Code

Copy the NLPAPP class implementation into a Colab cell.

4. Configure API Key

Insert your NLPCloud API token during client initialization.

5. Run the Application
obj = NLPAPP()

Follow the CLI prompts in the input box to interact with the system.

Key Learning Outcomes

This project demonstrates practical skills in:

Object-Oriented Programming in Python

REST API integration

Multi-model AI system design

JSON response parsing and data manipulation

CLI application development

Future Improvements

Planned enhancements include:

Secure password entry using getpass

Persistent user storage via Google Drive integration

Result export to CSV / TXT files

Deployment as a web application using Streamlit

Support for additional NLP tasks such as summarization and translation

Author

Rudra
AWS ML Engineer | AI Systems Builder

License

This project is released under the MIT License.