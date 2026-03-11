# TruthLens# FactChk – RAG Based Fact Checking System

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Streamlit](https://img.shields.io/badge/streamlit-1.28-red.svg)](https://streamlit.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## Overview

**FactChk** is an AI-powered fact-checking system that verifies claims using **Retrieval-Augmented Generation (RAG)**.

The system retrieves similar fact-checked statements from a dataset and uses a **Large Language Model (LLM)** to generate a final verdict.

Output includes:

* Verdict: **TRUE / FALSE / UNCERTAIN**
* Confidence score
* Supporting explanation

Dataset used: **LIAR Dataset (PolitiFact)** containing **12.8K fact-checked claims**.

---

## Architecture

```
User Claim
    ↓
Sentence Embedding
    ↓
Vector Search (Qdrant)
    ↓
Top Retrieved Claims
    ↓
LLM Reasoning (Gemini)
    ↓
Verdict + Confidence
```

---

## Tech Stack

* **Frontend:** Streamlit
* **Embeddings:** Sentence Transformers (`all-MiniLM-L6-v2`)
* **Vector Database:** Qdrant
* **LLM:** Google Gemini 2.5 Flash
* **Dataset:** LIAR (PolitiFact)

---

## Installation

Clone the repository:

```
git clone https://github.com/yourusername/FactChk.git
cd FactChk
```

Create virtual environment:

```
python -m venv venv
```

Activate environment:

Windows

```
venv\Scripts\activate
```

Linux / Mac

```
source venv/bin/activate
```

Install dependencies:

```
pip install -r requirements.txt
```

Add API key:

Create `.env`

```
GOOGLE_API_KEY=your_api_key_here
```

Run the application:

```
streamlit run src/app.py
```

---

## Project Structure

```
FactChk/
│
├── src/
│   ├── app.py
│   ├── search.py
│   └── explain.py
│
├── data/
│   └── liar_train.tsv
│
├── qdrant_db/
├── requirements.txt
├── README.md
```

---

## Results

* **Accuracy:** ~94% on LIAR dataset
* **Response Time:** 3–7 seconds per query
* **Retrieval:** Top 5 similar claims

---


