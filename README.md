# AI-Based Incident Intelligence System

## Overview

This project implements an AI-driven Incident Intelligence System that helps move IT operations from a reactive to a proactive approach.

The system predicts high-risk incidents, automatically identifies root causes using NLP, and retrieves similar historical incidents using vector similarity, enabling faster resolution and proactive alerting.

This project is inspired by real-world enterprise AI/ML use cases in IT Operations and Cloud Management.

---

## Key Capabilities

### 1. Incident Risk Prediction (Proactive Alerts)
- Predicts whether an incident is High Risk or Low Risk
- Uses enterprise-grade models (LightGBM / XGBoost)
- Handles class imbalance
- Focuses on recall for critical incidents
- Provides explainable feature importance

### 2. Root Cause Analysis using NLP
- Uses TF-IDF to convert incident text into numerical vectors
- Performs multi-class classification of root causes
- Automatically predicts probable root cause categories
- Provides keyword-level explainability

### 3. Similar Incident Retrieval (Vector Search)
- Uses vector similarity to retrieve semantically similar past incidents
- Built using FAISS for scalable vector search
- Enables faster troubleshooting by learning from historical data

### 4. RAG-style Reasoning (Without LLMs)
- Uses retrieved incidents to infer probable root causes
- Provides explainable, example-based reasoning
- Forms a foundation for future LLM-based RAG systems

---

## Project Architecture    
              +----------------------+
              |  Raw Incident Data   |
              +----------+-----------+
                         |
                         v
              +----------------------+
              | Curated Incident     |
              | Table                |
              +----------+-----------+
                         |
                         v
              +----------------------+
              | Feature Engineering  |
              +----------+-----------+
                         |
                         v
              +----------------------+
              | Risk Prediction      |
              | (LightGBM / XGBoost) |
              +----------+-----------+
                         |
                         v
              +----------------------+
              | Proactive Alerts     |
              +----------------------+

    ---------------------------------------------

              +----------------------+
              | Title + Description  |
              +----------+-----------+
                         |
                         v
              +----------------------+
              | TF-IDF Vectorization |
              +----------+-----------+
                         |
                         v
              +----------------------+
              | Root Cause           |
              | Classification       |
              +----------+-----------+
                         |
                         v
              +----------------------+
              | FAISS Vector Search  |
              +----------+-----------+
                         |
                         v
              +----------------------+
              | RAG-style Reasoning  |
              +----------------------+



## Technologies Used

- Python
- Pandas, NumPy
- Scikit-learn
- LightGBM, XGBoost
- TF-IDF (NLP)
- FAISS (Vector Search)
- Pickle (Persistence)

---

## How to Run

### 1. Clone Repository
```bash
git clone <your-repo-url>
cd incident-intelligence-ai

2. Install Dependencies
pip install -r requirements.txt

3. Run Notebook

Open:

notebooks/incident_ai_system.ipynb and execute all cells in order.
