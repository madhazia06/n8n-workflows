# 📅 Meeting Management Automation - n8n Workflow

An automated meeting management workflow built with n8n that retrieves meetings, identifies upcoming and weekly meetings, sends reminder emails, and generates a professional weekly meeting digest.

## 🚀 Features

- 📆 Fetches events.
- ⏰ Identifies upcoming meetings automatically.
- 📧 Sends reminder emails before scheduled meetings.
- 📊 Generates a weekly meeting digest in HTML format.
- 👥 Includes meeting title, date/time, attendees, status, and summary.
- 🤖 Fully automated with scheduled execution.

---

## 🛠 Technologies Used

- n8n
- Google Sheets
- Gmail
- JavaScript Code Nodes
- HTML Email Templates

---

## 📋 Workflow

1. The workflow runs on a scheduled interval.
2. It retrieves meetings from Google Sheets.
3. Upcoming meetings are filtered for reminders.
4. Reminder emails are sent to participants.
5. Weekly meetings are collected.
6. A JavaScript node generates a formatted HTML digest.
7. The digest is emailed to the configured recipient.

---

## 📂 Files

```
meeting-management/
├── workflow-meeting-management-automation.json   # n8n workflow
└── README.md
```

---

## ⚙️ Setup

1. Import the workflow into n8n.
2. Connect your Google Sheets account.
3. Connect your Gmail account.
4. Configure the email recipient(s).
5. Adjust the schedule and reminder timing if required.
6. Activate the workflow.

---

## 📤 Output

### Meeting Reminder Email
- Meeting title
- Date and time
- Participants
- Meeting details

### Weekly Meeting Digest
The digest includes:

- 📅 Meeting title
- 🕒 Date & time
- 👥 Attendees
- ✅ Meeting status
- 📝 Meeting summary

---

## 💡 Use Cases

- Personal meeting management
- Team scheduling
- Project management
- Weekly productivity reports
- Executive meeting summaries

---

## 🔮 Future Improvements

- Microsoft Teams and Zoom integration.
- Slack or Microsoft Teams notifications.
- Automatic meeting minutes generation using AI.
- Calendar conflict detection.
- PDF export of weekly reports.