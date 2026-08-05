# Basic AI Chatbot with Real-Time Search

A simple n8n chatbot workflow powered by a locally hosted Qwen 3 model through Ollama.

The AI Agent uses SerpAPI to search for current information before answering user questions and includes short-term conversation memory.

## Features

* Chat interface using n8n Chat Trigger
* Local `qwen3:8b` model through Ollama
* Real-time web search using SerpAPI
* Conversation memory using Simple Memory
* AI Agent for tool selection and response generation

## Requirements

* n8n
* Ollama
* Qwen 3 8B model
* SerpAPI account and API key

Install the Ollama model:

```bash
ollama pull qwen3:8b
```

## Setup

1. Import the workflow JSON into n8n.
2. Configure your Ollama credentials.
3. Configure your SerpAPI credentials.
4. Confirm that the Ollama server is running.
5. Activate the workflow and open the chat.