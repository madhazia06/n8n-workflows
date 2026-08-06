# n8n AI Video Generator

An automated text-to-video workflow built with **n8n**, **Groq**, **Magic Hour**, **Google Drive**, and **Google Sheets**.

Users submit a video idea through an n8n form. The workflow converts the idea into a short scene, optimizes it into a video-generation prompt, generates the video through Magic Hour, waits for processing to finish, downloads the completed video, uploads it to Google Drive, and records the result in Google Sheets.

## Features

* Collects video ideas through an n8n form
* Generates short video scenes with Groq
* Converts scenes into detailed AI-video prompts
* Creates videos through the Magic Hour API
* Polls the generation status automatically
* Downloads completed video files
* Uploads generated videos to Google Drive
* Records video information in Google Sheets

## Workflow Overview

```text
Form Submission
      ↓
Generate Video Scene
      ↓
Create Video Prompt
      ↓
Submit to Magic Hour
      ↓
Wait and Check Status
      ↓
Video Complete?
   ├── No → Wait and Check Again
   └── Yes
          ↓
     Download Video
       ├── Upload to Google Drive
       └── Save URL to Google Sheets
```

## Technologies Used

* n8n
* Groq API
* Magic Hour API
* Google Drive
* Google Sheets
* Llama 3.3 70B

## Prerequisites

Before using this workflow, you need:

* A running n8n instance
* A Groq API account
* A Magic Hour API account
* Google Drive OAuth credentials
* Google Sheets OAuth credentials
* A Google Sheet for storing video information

## Setup

### 1. Import the workflow

Download the workflow JSON file and import it into n8n:

1. Open n8n.
2. Select **Import from File**.
3. Choose the workflow JSON.
4. Save the imported workflow.

### 2. Configure Groq

Create a Groq credential in n8n and connect it to both Groq Chat Model nodes.

The workflow currently uses:

```text
llama-3.3-70b-versatile
```

You may replace it with another supported Groq model.

### 3. Configure Magic Hour

Create a new Magic Hour API key.

Do not paste API keys directly into workflow JSON files committed to GitHub.

Store the key as an environment variable:

```env
MAGIC_HOUR_API_KEY=your_api_key
```

Use this authorization header in the Magic Hour HTTP Request nodes:

```text
Bearer {{$env.MAGIC_HOUR_API_KEY}}
```

### 4. Configure Google Drive

Create or select a Google Drive OAuth credential in n8n.

In the Google Drive node:

* Select the destination drive.
* Select a destination folder.
* Set the binary input property to `data`.

A dedicated folder such as `AI Generated Videos` is recommended.

### 5. Configure Google Sheets

Create a Google Sheet with columns. Select the spreadsheet and sheet inside the Google Sheets node.

### 6. Configure video download

In the video download HTTP Request node, set:

```text
Response Format: File
Binary Property: data
```

### 7. Test the workflow

Run the workflow in test mode and submit an idea such as:

```text
A small robot discovers a glowing flower in a dark futuristic forest.
```

Confirm that:

1. Groq creates a video scene.
2. Groq creates a generation prompt.
3. Magic Hour returns a project ID.
4. The workflow checks the generation status.
5. The completed video is downloaded.
6. The video is uploaded to Google Drive.
7. Video details are added to Google Sheets.

## Customization

You can customize the workflow by:

* Changing the video duration
* Changing the aspect ratio
* Disabling generated audio
* Replacing Groq with another LLM provider
* Saving files to another storage service
* Sending completed videos through Slack, email, or Telegram
* Adding approval before video generation
* Adding prompt moderation
* Adding usage and cost tracking