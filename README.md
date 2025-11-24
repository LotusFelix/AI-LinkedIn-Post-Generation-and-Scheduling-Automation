# AI-LinkedIn-Post-Generation-and-Scheduling-Automation
This repository contains an end-to-end automation workflow built in n8n.
It generates LinkedIn posts using LLMs, creates AI images, sends them for review, uploads assets to Google Drive, and schedules approved posts inside Google Sheets.

It is designed for creators, AI engineers, and founders who want to scale high-quality LinkedIn content with human oversight.

🚀 What This Workflow Does

Generates full LinkedIn posts using an AI agent.

Creates custom images with OpenAI’s image API.

Sends posts and images for human review using GoToHuman.

Uploads the final assets to Google Drive.

Writes post + image + scheduled date into Google Sheets.

Automatically repeats until your post quota is completed.

📁 Workflow File

The file linkedin_automation.json in this repository is the complete n8n workflow export.

🛠️ How to Use This Workflow
1. Import the Workflow

Open n8n.

Go to Workflows → Import.

Upload the JSON file or paste its contents.

Save.

2. Add Your Own Credentials

You must add your own credentials for:

OpenAI API

OpenRouter (or chosen LLM provider)

Google Drive

Google Sheets

GoToHuman API

n8n will show “credentials missing” on nodes until you configure them.

3. Replace IDs and File References

Before running the workflow, replace the following:

Google Drive folder IDs

Google Sheets document ID

GoToHuman template IDs

Any hard-coded URLs

Search for patterns like:

folderId: "1xxxxxxx"
documentId: "1yyyyyyy"
webhookId: "zzzzzzzz"


Replace them with your own IDs.

🧠 Workflow Logic Overview

PostSessionId: Creates a unique post ID.

PostGenerator: LLM generates a full LinkedIn post.

PostReview: Human approval or feedback.

ImageGenerator: AI creates an illustration based on the post.

Image Review: Another human approval loop.

Google Drive Upload: Stores images and retrieves share links.

Google Sheets Update: Writes final post info and schedule date.

Repeat Logic: Continues generating multiple posts.

🔐 Security Note

This workflow does not include any API keys.
However, it contains some resource IDs (Drive folder IDs, Sheet IDs).
Replace them if you want to avoid exposing internal document identifiers.

📬 Author

Felix Egbine
Maven Machine Learning Engineer and Automation Specialist
