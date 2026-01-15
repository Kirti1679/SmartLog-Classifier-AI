# 🚀 Log Classification System: Hybrid AI-Powered Framework

Welcome to the Log Classification System! This project is a robust, production-ready solution for classifying log messages using a hybrid approach that combines Regex, Machine Learning (BERT + Logistic Regression), and Large Language Models (LLMs). It features a modern React + Vite frontend, a scalable FastAPI backend, and is fully containerized with Docker for easy deployment.

## 📹 Video Demo
Watch the demo here: [SmartLog Classifier AI - Demo]((https://drive.google.com/file/d/1bb_JI3DcNXefgUKthANVY5fGdQGy3zDH/view?usp=sharing))  
*(Replace with actual video URL)*

---

## 🏛️ Architecture

This diagram illustrates the hybrid decision-making process for classifying log messages using Regex, BERT, and LLMs:

- **Frontend**: React + Vite + TailwindCSS for a fast, interactive dashboard.
- **Backend**: FastAPI serving REST endpoints for log classification and file handling.
- **Classification Engine**: Hybrid pipeline (Regex, BERT+LogReg, LLM).
- **Model Storage**: Pre-trained models and resources. - **Dockerized**: One-command deployment.

---

## 🧠 Classification Pipeline

The system uses a three-stage hybrid approach for maximum accuracy and flexibility:

### 🔍 Regex-based Classification
Fast, rule-based matching for simple, predictable log patterns.  
**Example:**  
`User User123 logged in.` → **User Action**

---

### 🤖 Machine Learning (BERT + Logistic Regression)
For complex patterns with sufficient labeled data.  
Uses Sentence Transformers to embed log messages, then classifies with Logistic Regression.  
**Example:**  
`IP 192.168.1.1 blocked due to potential attack` → **Security Alert**

---

### 🦾 LLM-based Classification (Gemini)
For rare/ambiguous logs or when labeled data is insufficient.  
Uses Google Gemini LLM via API for fallback classification.  
**Example:**  
`The 'BulkEmailSender' feature is no longer supported.` → **Deprecation Warning**

---

### 🔀 Decision Flow
- If the log source is **LegacyCRM**, always use **LLM**.  
- Else, try **Regex**.  
- If no match, use **BERT+LogReg**.  
- If still unclassified, fallback to **LLM**.


---

## 💼 Tech Stack

| Layer       | Technology                                      |
|-------------|--------------------------------------------------|
| Frontend    | React, Vite, TailwindCSS, Chart.js, Lucide       |
| Backend     | FastAPI, Python 3.11, Pandas, Uvicorn            |
| ML Models   | Sentence Transformers (BERT), scikit-learn       |
| LLM         | Google Gemini API                                |
| DevOps      | Docker, Git                                      |


---

## 📁 Project Structure

log-classification/
│
├── log-classfication-frontend/   # React + Vite frontend
│   └── ...                      # UI, charts, dashboard
│
├── server.py                    # FastAPI backend
├── classify.py                  # Hybrid classification logic
├── processor_regex.py           # Regex rules
├── processor_bert.py            # BERT + Logistic Regression
├── processor_llm.py             # Gemini LLM integration
├── models/                      # Saved ML models
├── resources/                   # Test data, outputs, architecture image
├── requirements.txt             # Python dependencies
├── Dockerfile                   # Multi-stage Docker build
└── .env                         # API keys and secrets
