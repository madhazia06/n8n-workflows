# 📝 Simple Logger - n8n Workflow

A simple n8n workflow that collects customer feedback through a web form, determines whether a customer is eligible for a discount based on their feedback, and stores all responses in a Google Sheets spreadsheet.

## 🚀 Features

- 📋 Collects customer information using an n8n Form.
- 😊 Detects whether customer feedback is **Positive**, **Neutral**, or **Negative**.
- 🎁 Automatically marks customers with **Positive** feedback as eligible for a discount.
- 📊 Stores all responses in Google Sheets.
- ⚡ Fully automated with no manual intervention.

---

## 🛠 Technologies Used

- n8n
- n8n Form Trigger
- IF Node
- Set Node
- Google Sheets
- Google Sheets OAuth

---

## 📋 Workflow

1. A customer submits the feedback form.
2. The workflow receives:
   - Email Address
   - Name
   - Age
   - Feedback (Positive / Neutral / Negative)
3. An **IF** node checks the customer's feedback.
4. If the feedback is **Positive**, the workflow sets **Give_Discount = Yes**.
5. Otherwise, it sets **Give_Discount = No**.
6. The complete record is appended to a Google Sheets spreadsheet.

---

## 📂 Files

```
simple-logger/
├── workflow-simple-logger.json   # n8n workflow
└── README.md
```

---

## ⚙️ Setup

1. Import the workflow into n8n.
2. Connect your Google Sheets account using OAuth.
3. Replace the spreadsheet with your own (optional).
4. Activate the workflow.
5. Share the generated form URL with users.

---

## 📥 Form Fields

The workflow collects the following information:

| Field | Type |
|--------|------|
| Email_Id | Email |
| Name | Text |
| Age | Number |
| Feedback | Dropdown (Positive, Neutral, Negative) |

---

## 📊 Output

Each form submission is saved in Google Sheets with the following columns:

| Email_Id | Name | Age | Feedback | Give_Discount |
|----------|------|-----|----------|---------------|
| user@example.com | John | 24 | Positive | Yes |
| user@example.com | Sarah | 31 | Neutral | No |

---

## 💡 Use Cases

- Customer feedback collection
- Customer satisfaction surveys
- Discount eligibility tracking
- CRM data collection
- Simple lead management

---

## 🔮 Future Improvements

- Send an automatic thank-you email after form submission.
- Generate discount coupons for eligible customers.
- Notify administrators of new submissions.
- Display analytics using dashboards.
- Store data in a database instead of Google Sheets.