# 📊 AI KPI Report Generator for n8n

Automatically generate beautiful weekly KPI reports from Google Sheets using AI and send them as HTML emails.

## Overview

This n8n workflow reads sales and dimension tables from Google Sheets, calculates key business metrics using JavaScript, generates a professional HTML report with an AI model, and emails the report automatically on a schedule.

## Features

* 📅 Weekly scheduled execution
* 📂 Reads data from multiple Google Sheets
* 📊 Calculates business KPIs using JavaScript
* 🤖 AI-generated executive summary and recommendations
* 🎨 Responsive HTML email report
* 📧 Automatic email delivery via Gmail
* 📈 Sales, customer, product, region, and trend analysis

## Workflow

```text
Schedule Trigger
      │
      ▼
Read Google Sheets
(Fact Sales + Dimension Tables)
      │
      ▼
Merge Data
      │
      ▼
Calculate KPIs
(JavaScript)
      │
      ▼
Generate HTML Report
(AI)
      │
      ▼
Extract HTML
      │
      ▼
Send Email
```

## KPIs Generated

* Total Revenue
* Total Profit
* Profit Margin
* Average Order Value
* Total Orders
* Total Quantity Sold
* Month-over-Month Growth
* Best & Worst Performing Months
* Top Products
* Top Customers
* Top Regions
* Quarterly Revenue
* AI-generated Business Recommendations

## Technologies Used

* n8n
* Google Sheets
* JavaScript
* Groq (Llama 3.3 70B)
* Gmail
* HTML Email Templates

## Requirements

Before running the workflow, configure:

* Google Sheets OAuth credentials
* Gmail OAuth credentials
* Groq API credentials
* Your Google Spreadsheet IDs
* Recipient email address

## How It Works

1. The workflow runs automatically every week.
2. Sales and dimension data are loaded from Google Sheets.
3. Business KPIs are calculated using JavaScript.
4. An AI model converts the KPIs into a professional HTML report.
5. The generated report is emailed to the configured recipient.