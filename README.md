# 🇧🇩 Bangla FAQ Bot using RAG (Retrieval-Augmented Generation)

---

## 🚀 Project Overview

This project demonstrates a Bangla-language FAQ assistant built using Retrieval-Augmented Generation (RAG) inside a Google Colab notebook.

The system retrieves relevant Bangla FAQ content using semantic embeddings + FAISS, applies metadata-based filtering, and generates grounded responses using an LLM — preventing hallucinations and improving answer relevance for a low-resource language.

🎯 Primary Goal:
Build a proof-of-concept RAG system that supports Bangla queries with topic-aware routing and safe fallback behavior.

---

## 🌍 Why This Project Matters

- Most RAG examples focus on English

- Bangla is a low-resource language in AI

- Hallucination is risky in FAQ and helpdesk systems

- This project shows how to ground LLMs using retrieval + metadata

### Applicable Use Cases

- Bangla customer support bots

- Educational assistants

- Government or NGO information systems

- Domain-specific knowledge assistants

---

## 🧩 Key Features

✅ Bangla input & output support

🧠 LLM-based topic routing

🗂️ Metadata filtering before vector search

🔎 FAISS-powered semantic similarity search

🧱 Retrieval-Augmented Generation (RAG)

🚫 Safe fallback when no relevant context is found

💻 Fully implemented inside a single Colab notebook

---

## 🏗️ System Architecture

```
User Question (Bangla)
        |
        v
[ LLM Category Router ]
        |
        v
[ Metadata-Based Filtering ]
        |
        v
[ FAISS Similarity Search ]
        |
        v
[ RAG Answer Generation ]
```
Design Goal: Ensure the LLM never answers beyond retrieved Bangla knowledge.

---

## 🛠️ Tech Stack

```
| Component     | Technology                                 |
| ------------- | ------------------------------------------ |
| Language      | Python                                     |
| Notebook      | Google Colab                               |
| Embeddings    | Bengali SBERT (`l3cube-pune`)              |
| Vector Store  | FAISS                                      |
| RAG Framework | LangChain                                  |
| LLM           | OpenAI GPT-4.1-Nano (GitHub Inference API) |
```

---

## ⚙️ How to Run (Google Colab)

1. Open the notebook:
```
notebooks/bangla_faq_rag.ipynb
```

2. Set API token in Colab:
```
os.environ["GITHUB_TOKEN"] = "your_api_key"
```

3. Run cells sequentially:

- Install dependencies

- Load and embed Bangla FAQ data

- Build FAISS vector store

- Ask questions interactively

---

## ▶️ Example Interaction

```
👩🏻‍💻 আপনার প্রশ্নটি বলুন: পরিবারের সাথে ভ্রমণের সুবিধা কী?
[LLM Router] Category: ভ্রমণ

[User Question] পরিবারের সাথে ভ্রমণের সুবিধা কী?

[Metadata Filtering] Category: ভ্রমণ

🕵🏻 [Similarity Search Results for Query] পরিবারের সাথে ভ্রমণের সুবিধা কী?
 >> পরিবারের সাথে ভ্রমণ আনন্দ বাড়ায়।
 >> ভ্রমণ মানুষকে নতুন অভিজ্ঞতা দেয়।
 >> ভ্রমণ জীবনের একঘেয়েমি দূর করে।

💡প্রত্যাশিত উত্তর: পরিবারের সাথে ভ্রমণের সুবিধা হলো এটি আনন্দ বাড়ায়, নতুন অভিজ্ঞতা দেয় এবং জীবনের একঘেয়েমি দূর করে।
```
If no relevant context exists:
```
দুঃখিত, এই বিষয়ে আমার উত্তরটি জানা নেই।
```
---

## 📊 Demo & Output

### 🎥 Demo Video:
👉 https://drive.google.com/file/d/1esH30Cl80EC0Y_Rs6qH8HvHFda2DvjhN/view

### 📌 Output Characteristics:

- Grounded answers

- Topic-aware retrieval

- No hallucinated responses

---

## 🧠 Learning & Engineering Highlights

- Implemented Retrieval-Augmented Generation from scratch

- Used metadata-aware vector filtering

- Applied LLM-based reasoning for intent classification

- Worked with low-resource Bangla embeddings

- Designed a safe, explainable AI assistant

---

## 🔮 Future Improvements

- Convert notebook into FastAPI service

- Add automatic evaluation metrics (Recall@K)

- Persist FAISS index to disk

- Add document ingestion from PDFs / web

- Deploy as a lightweight web app

---
