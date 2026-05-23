# HuggingFace Pipeline Practice — IT Incident Analysis

> Hands-on practice with HuggingFace transformers pipelines 
> applied to real-world IT incident scenarios

---

## Project Overview

Explored 3 core HuggingFace pipelines using IT incident data 
— directly connected to 3+ years of AIOps experience at TCS. 
Built as part of my transition into AI/ML Engineering.

---

## Pipelines Used

| Pipeline | Task | Accuracy |
|---|---|---|
| sentiment-analysis | Classify incident severity | 99–100% confidence |
| zero-shot-classification | Categorise incident type | 67–91% confidence |
| text-generation | Attempted summarization (GPT2) | Limited — wrong model for task |

---

## Key Learnings

### 1. Sentiment Analysis
- Correctly classified all 5 IT incidents as POSITIVE or NEGATIVE
- 99–100% confidence on clear technical language
- Insight: general sentiment models work well on unambiguous IT text

### 2. Zero-shot Classification
- Classified incidents into: hardware, security, network, database, storage, application
- High confidence on specific incidents — security 80.9%, application 90.1%
- Low confidence on ambiguous incidents — hardware 29.2% for memory issue
- Insight: specific descriptive text = higher confidence scores

### 3. Text Generation (GPT2)
- Attempted incident summarization using GPT2
- Generated irrelevant text — hallucinated URLs and unrelated content
- Insight: GPT2 is a text completion model not a summarization model
- Better approach: use dedicated summarization model (BART/T5) or prompt Gemini

### 4. Combined Incident Analyser
- Chained sentiment + classification pipelines together
- Memory leak correctly classified as application (90.1%) with better prompt
- Insight: better input text = higher confidence = more accurate classification
- This is prompt engineering in action

---

## Results Summary

Incident 1 — Database crash
Sentiment: NEGATIVE (100%) | Category: database (66.8%)
Incident 2 — Failed login attempts
Sentiment: NEGATIVE (100%) | Category: security (80.9%)
Incident 3 — Memory leak
Sentiment: NEGATIVE (99.9%) | Category: application (90.1%)

---

## Tech Stack

| Component | Technology |
|---|---|
| Language | Python |
| ML Framework | HuggingFace Transformers |
| Sentiment Model | distilbert-base-uncased-finetuned-sst-2-english |
| Classification Model | facebook/bart-large-mnli |
| Text Generation | GPT2 |
| Environment | Google Colab |

---

## Real-world Connection

| My TCS Experience | This Project |
|---|---|
| Incident severity triage | Sentiment analysis on incidents |
| Incident categorisation | Zero-shot classification |
| AIOps alert management | Automated incident analysis pipeline |
| Production monitoring | Model confidence scoring |

---

## What I Would Do Differently in Production

- Replace GPT2 with Gemini API for summarization — already implemented in RAG project
- Add confidence threshold — flag incidents below 50% for human review
- Connect directly to ServiceNow API for real-time incident analysis
- Deploy as a FastAPI endpoint for integration with monitoring systems

---

## Related Project

Check out my main project — [AIOps Incident Analyser using RAG](https://github.com/Poojarao-analyst/aiops-incident-analyser-rag) — which builds a complete RAG pipeline on 120,000 real incident records using HuggingFace, FAISS, and Gemini API.

---

## Author

**Pooja Rao** — AI/ML Engineer | MLOps | AIOps | Production Systems
[LinkedIn](https://linkedin.com/in/pooja-rao-a3b2a8167) · Chennai, Tamil Nadu
