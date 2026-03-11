NLP-as-a-Service: Google Colab CLI Application


📌 Project Overview:
This project is an interactive NLP dashboard built inside a Google Colab environment. It allows users to perform high-level NLP tasks like Named Entity Recognition, Language Detection, and Emotion Analysis through a structured command-line interface.

Key Highlights:
Interactive CLI: Designed a menu-driven interface optimized for the Colab input console.
Secure Auth Simulation: Implemented a private database within the class to manage user registration and sessions.
Multi-Model Integration: Leveraged three distinct AI models via NLPCloud for specialized tasks.
Advanced Data Parsing: Developed logic to extract the dominant emotion from multi-label API responses.

🎯 Why These AI Models?

GPT-OSS-120B

Why this model?
High-parameter count makes it exceptionally good at understanding context for NER.
It handles complex entity extraction better than smaller, local models.

DistilBERT (Emotion)

Why not standard Sentiment Analysis?
Standard analysis only gives "Positive/Negative."
DistilBERT provides 6-7 specific emotions (joy, sadness, etc.), making the app's output far more insightful for the user.

Python-LangDetect

Why this?
It is lightweight and specifically optimized for fast character-level identification across 50+ languages.

🔧 Tech Stack
Tool/Library Purpose
Google Colab Development and execution environment
NLPCloud Python SDK API wrapper for model interaction
JSON/Dict Parsing Handling API response payloads
Python OOP Class-based architecture for state management

🏗 Architecture & Logic
The project is encapsulated in a single class NLPAPP.
Key Logic: Top-Emotion Extraction
Instead of printing raw JSON, the app calculates the maximum confidence score to return the most likely emotion:
python

# Extract scores, enumerate to keep track of index, and sort

L = [i['score'] for i in response['scored_labels']]
index = sorted(list(enumerate(L)), key=lambda x: x[1], reverse=True)[0][0]
print(response['scored_labels'][index]['label'])
Use code with caution.

📝 API Implementation Examples
NER Endpoint: client.entities(para, searched_entity=word)
Sentiment Endpoint: client.sentiment(para)
Language Endpoint: client.langdetection(para)

🚀 How to Run in Google Colab
Open Colab: Create a new notebook.
Install Library: In the first cell, run:
python
!pip install nlpcloud
Use code with caution.

Paste Code: Copy the NLPAPP class into a cell.
Insert API Key: Ensure your NLPCloud token is correctly placed in the client initialization.
Initialize:
python
obj = NLPAPP()
Use code with caution.

Interact: Use the input box at the top of the cell to navigate the menus.
🎓 Key Learning Outcomes
Mastered Object-Oriented Programming (OOP) in Python (Private variables/methods).
Learned to integrate and manage multiple REST API endpoints within a single application.
Gained experience in JSON data manipulation and algorithmic sorting.

🚀 Future Improvements
Password Masking: Integrating getpass for secure password entry in Colab.
Export Results: Adding functionality to save NLP results into a .txt or .csv file in Google Drive.


Would you like me to help you write a Google Drive Integration code snippet so you can save your user database permanently?
