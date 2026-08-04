# Instagram Lead Generator (n8n)

An n8n workflow that collects a profession and location through a form, searches Google for matching Instagram profiles using Apify, structures the results with JavaScript, and saves the leads to Google Sheets.

## Workflow

1. **Form Trigger** – collects the profession and location.
2. **HTTP Request** – sends a dynamic Google search query to Apify:
   ```text
   site:instagram.com [profession] [location]
   ```
3. **Wait** – pauses briefly while results are prepared.
4. **Code Node** – extracts the name, Instagram handle, profile URL, description, and follower count.
5. **Google Sheets** – appends each lead as a new row.

## Requirements

- n8n
- Apify account and API token
- Google Sheets credentials
- A sheet with these headers:

```text
Name | Handle | URL | Description | Followers
```

## Setup

1. Import `workflow-instagram-lead-generator.json` into n8n.
2. Add your Apify API token securely.
3. Connect your Google Sheets account.
4. Select the destination spreadsheet and sheet.
5. Test the form and activate the workflow.

## Note

Follower counts are only available when Google includes them in the search result data, so some rows may have an empty follower value.
