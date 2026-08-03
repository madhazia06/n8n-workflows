# n8n Workflows

A collection of my n8n workflow automations, exported as JSON for backup and version control.

## 📋 Workflows

### 1. Simple Logger (Google Sheets)
Logs data automatically into a Google Sheet.

- **Trigger:** _(add your trigger type here)_
- **Integration:** Google Sheets
- **File:** `sheets-logger.json`

### 2. Code Summarizer
Triggers on incoming Gmail messages and uses **Google Gemini** to process/classify the content, routing it through an LLM chain for further action.

- **Trigger:** Gmail Trigger
- **AI Model:** Google Gemini (2.5 Flash / 3 Flash)
- **Key nodes:** `Gmail Trigger` → `Comments_Addition` / `Basic LLM Chain` → `Google Gemini Chat Model`
- **File:** `gmail-comment-classifier.json`


## 🚀 How to Use

1. Open your n8n instance.
2. Go to **Workflows** → **Import from File** (or copy-paste the JSON via **Import from URL/Clipboard**).
3. Select the `.json` file you want to import.
4. Reconnect your own credentials — API keys are **not** included in these exports for security. You'll need to set up your own:
   - Gmail OAuth2 credential
   - Google Gemini API credential
   - Google Sheets OAuth2 credential
5. Activate the workflow and test it.

## 🛠️ Built With

- [n8n](https://n8n.io) — workflow automation tool (self-hosted via Docker)
- [Google Gemini API](https://aistudio.google.com) — free-tier LLM for AI processing
- Google Sheets API
- Gmail API

## 📝 Notes

- These workflows were built while learning n8n and workflow automation fundamentals.
- Credentials/API keys are intentionally excluded from all exported JSON files. Each workflow will need credentials reconnected after import.
- Some nodes use free-tier models (Google Gemini Flash) which are subject to Google's rate limits.

## 📄 License

Feel free to use or adapt these workflows for your own learning.
