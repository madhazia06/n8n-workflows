# 📚 n8n RAG Chatbot

A Retrieval-Augmented Generation (RAG) chatbot built with n8n that answers questions from your documents using vector search and a Large Language Model.

## Features

* 📄 Load PDF documents from Google Drive
* 🧠 Generate embeddings using Google Gemini
* 🔍 Store vectors in Pinecone
* 💬 Ask questions through an n8n Chat Trigger
* 🤖 Retrieve relevant document chunks before generating answers
* ⚡ Powered by Groq Llama 3.3 70B

## Workflow

```text
Google Drive PDF
        │
        ▼
Document Loader
        │
        ▼
Gemini Embeddings
        │
        ▼
Pinecone Vector Store
──────────────────────────────────
User Question
        │
        ▼
Vector Retriever
        │
        ▼
Groq LLM
        │
        ▼
Answer
```

## Requirements

* n8n
* Google Drive OAuth
* Google Gemini API
* Pinecone
* Groq API

## Setup

1. Import the workflow into n8n.
2. Configure your Google Drive credentials.
3. Configure your Google Gemini API credentials.
4. Configure your Pinecone credentials.
5. Configure your Groq credentials.
6. Select your PDF document.
7. Run the indexing portion once to populate the vector database.
8. Start chatting with your knowledge base.

## Technologies

* n8n
* Pinecone
* Google Gemini Embeddings
* Groq
* Retrieval-Augmented Generation (RAG)