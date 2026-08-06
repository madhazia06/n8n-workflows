# Slack AI Knowledge Bot

An AI-powered Slack chatbot built with **n8n**, **Google Gemini**, and **Pinecone** that answers questions using Retrieval-Augmented Generation (RAG). The workflow maintains conversation memory and retrieves relevant information from a Pinecone vector database before generating responses.

---

## Features

- 💬 Responds to Slack messages and mentions
- 🤖 Powered by Google Gemini
- 🧠 Conversation memory for contextual replies
- 🔍 Retrieval-Augmented Generation (RAG) using Pinecone
- ⚡ Built entirely in n8n with minimal configuration
- 📚 Easily adaptable to any knowledge base

---

## Workflow Overview

```
Slack Trigger
      │
      ▼
AI Agent
 ├── Google Gemini Chat Model
 ├── Conversation Memory
 └── Pinecone Vector Store
      │
      ▼
Send Response to Slack
```

---

## Technologies

- n8n
- Slack API
- Google Gemini
- Pinecone Vector Database

---

## Prerequisites

Before importing the workflow, configure the following credentials in n8n:

- Slack API
- Google Gemini API
- Pinecone API

---

## Setup

1. Import the workflow into n8n.
2. Configure all required credentials.
3. Replace the Slack Channel ID with your own.
4. Update the Pinecone Index and Namespace.
5. Activate the workflow.
6. Mention the bot or send a message in Slack.

---

## Customization

You can easily adapt this workflow by:

- Changing the system prompt
- Using OpenAI, Groq, or Anthropic instead of Gemini
- Connecting another vector database
- Replacing the knowledge base with your own documents
- Adding external tools and APIs

---

## Use Cases

- Internal company knowledge assistant
- Documentation chatbot
- FAQ assistant
- Technical support bot
- Team productivity assistant
