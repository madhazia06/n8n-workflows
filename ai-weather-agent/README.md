# n8n Local AI Weather Agent

A modular AI weather chatbot built with n8n, Ollama, Qwen 3, and OpenWeatherMap.

The project uses two connected workflows:

* **AI Weather Chatbot:** Receives chat messages and decides when to use the weather tool.
* **Weather Lookup Tool:** Retrieves current weather information and converts it into a simple English response.

## Features

* Natural-language weather questions
* Local AI processing with Ollama
* Qwen 3 8B language model
* Live weather data from OpenWeatherMap
* Short-term conversation memory
* Parent-and-child workflow architecture
* Reusable AI tool workflow

## Requirements

* n8n
* Ollama
* OpenWeatherMap API key
* Qwen 3 8B model

## Installation

1. Import `weather-lookup-tool.json` into n8n.
2. Import `ai-weather-chatbot.json`.
3. Add your OpenWeatherMap credentials to the weather tool workflow.
4. Add your Ollama credentials to both workflows.
5. Open the Weather tool node in the parent workflow.
6. Select the imported Weather Lookup Tool workflow.
7. Make sure Ollama is running.
8. Test the workflows before activating the chatbot.

Example question:

```text
What is the weather in Lahore?
```

## Workflow Structure

```text
Chat Trigger
    ↓
AI Agent
    ↓
Weather Workflow Tool
    ↓
OpenWeatherMap
    ↓
Qwen 3 through Ollama
    ↓
Simple weather response
```