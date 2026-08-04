# Personal AI Assistant with n8n, Ollama, and Google Workspace

A self-hosted personal assistant built in **n8n**. It uses a local **Ollama** model for reasoning and connects to Google services and SerpApi through AI tools.

The assistant accepts chat requests through a webhook, decides which tool to use, performs the requested action, and returns the result to the client.

## Features

### Web search
- Searches live information through **SerpApi Google Search**.
- Useful for current facts and information not available in the local model.

### Google Calendar
- Creates calendar events.
- Retrieves one event by ID.
- Retrieves multiple events within a date range.

### Gmail
- Retrieves one email by message ID.
- Retrieves multiple emails.
- Sends new emails and replies.

### Google Tasks
- Creates tasks.
- Retrieves one or multiple tasks.
- Deletes tasks when explicitly requested.

### Notes with Google Docs
- Creates a notes document.
- Reads an existing document.
- Appends new notes without intentionally overwriting existing content.

### Expense tracking
- Adds expense records to Google Sheets.
- Retrieves expense history.
- Uses a calculator tool for totals and budget calculations.

### Conversation memory
- Uses n8n Simple Memory.

## Architecture

```text
    n8n Webhook
        |
        v
      AI Agent
   /      |       \
Ollama   Memory   Tools
                  |
                  +-- SerpApi Google Search
                  +-- Google Calendar
                  +-- Gmail
                  +-- Google Tasks
                  +-- Google Docs
                  +-- Google Sheets
                  +-- Calculator
        |
        v
Respond to Webhook
```

## Technology stack

- [n8n](https://n8n.io/)
- [Ollama](https://ollama.com/)
- `qwen3:8b`
- Google Calendar API
- Gmail API
- Google Tasks API
- Google Docs API
- Google Sheets API
- SerpApi
- Docker

## Repository structure

```text
personal-assistant-n8n/
├── README.md
└── workflow-personal-assistant.json
```

## Prerequisites

Install the following before importing the workflow:

- Docker and Docker Desktop
- n8n running in Docker
- Ollama installed on the host machine
- A compatible Ollama model, such as `qwen3:8b`
- Google OAuth credentials for Calendar, Gmail, Tasks, Docs, and Sheets
- A SerpApi API key

## Known limitations

- The workflow currently creates events but does not include dedicated update or delete event tools.
- Gmail actions depend on the permissions granted to the connected Google account.
- Notes updates require the document ID or URL.
- Expense tracking uses Google Sheets rather than a dedicated finance database.
- The workflow is inactive after import until credentials are configured and the workflow is activated.

## Roadmap

- Add calendar update and deletion tools.
- Add Gmail draft support and confirmation before sending.
- Add task completion instead of only deletion.
- Add a proper user/session identifier.
- Add voice input and text-to-speech.
- Add authentication to the frontend.
- Add structured audit logs for tool actions.
- Add budget limits and monthly expense reports.