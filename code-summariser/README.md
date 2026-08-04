# 🤖 Code Summariser - n8n Workflow

An AI-powered n8n workflow that automatically summarises source code, generates inline comments for better understanding, and emails the results in a well-formatted HTML report. The workflow is triggered whenever a new email containing code is received.

## 🚀 Features

- 📧 Automatically triggers on new Gmail messages.
- 📝 Generates a simple-language summary of the code.
- 💬 Adds meaningful comments to the original code without changing its functionality.
- ⚡ Runs code summarisation and comment generation in parallel.
- 🔀 Merges both outputs into a single report.
- 🎨 Converts the report into HTML for a professional email format.
- 📤 Sends the final report back via Gmail.

## 🛠 Technologies Used

- n8n
- Google Gemini (LLM)
- Gmail Trigger
- Gmail Node
- Merge Node
- Aggregate Node
- Set Node

## 📋 Workflow

1. Gmail Trigger monitors for incoming emails containing code.
2. The code is sent simultaneously to two AI chains:
   - **Code Summary** – explains what the code does in simple language.
   - **Comments Generator** – inserts helpful comments into the code.
3. Both outputs are merged.
4. The combined result is formatted into HTML.
5. A formatted email containing:
   - Commented Code
   - Code Summary
   is sent back to the configured Gmail account.

## 📂 Files

```
code-summariser/
├── workflow-code-summariser.json   # n8n workflow
└── README.md
```

## ⚙️ Setup

1. Import the workflow into n8n.
2. Configure your Gmail OAuth credentials.
3. Configure your Google Gemini API credentials.
4. Update the email addresses if required.
5. Activate the workflow.

## 📧 Output

The workflow sends an email containing:

- ✅ Code with AI-generated comments
- ✅ Easy-to-understand code summary
- ✅ Clean HTML formatting for improved readability

## 💡 Use Cases

- Learning unfamiliar code
- Understanding open-source projects
- Reviewing Python scripts
- Educational demonstrations
- Developer productivity