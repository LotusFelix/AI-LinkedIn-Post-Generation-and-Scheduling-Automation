# 🤖 AI LinkedIn Post Generation & Scheduling (n8n Workflow)

AI-powered automation that **writes, reviews, illustrates, and schedules LinkedIn posts** using n8n, LLMs, AI image generation, and Google Workspace.

This workflow turns your LinkedIn content into a **semi-automated production line** with human approval where it matters.

---

## 🚀 What This Workflow Does

- ✍️ **Generates LinkedIn posts** with a focused AI prompt (ML / AI engineering themes)  
- 🧠 **Uses memory & feedback** to refine posts based on human review  
- 🖼️ **Creates custom images** via OpenAI image generation and optional image edits  
- ☁️ **Uploads images to Google Drive** and returns shareable links  
- 📊 **Updates a Google Sheets content calendar** with post, image link, schedule date, and status  
- 🔁 **Repeats the process** to generate multiple scheduled posts automatically  

---

## 🧱 High-Level Architecture

- **n8n** – Orchestrates the full workflow  
- **LLM (via OpenRouter)** – Generates LinkedIn post copy  
- **OpenAI Images API** – Creates and edits post illustrations  
- **GoToHuman** – Human-in-the-loop review for posts and images  
- **Google Drive** – Stores final images and provides URLs  
- **Google Sheets** – Acts as the content calendar and schedule tracker  

---

## 📂 What’s in This Repo

- `linkedin_automation.json`  
  Exported n8n workflow that you can **import directly** into your own n8n instance.

---

## 🛠️ How to Use This Workflow

### 1️⃣ Import into n8n

1. Open your n8n instance  
2. Go to **Workflows → Import**  
3. Upload `linkedin_automation.json`  
4. Save the workflow  

---

### 2️⃣ Connect Your Own Credentials

In n8n, edit the workflow and attach your own credentials for:

- 🔑 **OpenAI HTTP Header Auth** – for image generation and edits  
- 🔑 **OpenRouter API** – for the LLM chat model  
- 🔑 **Google Drive OAuth2** – for file uploads and links  
- 🔑 **Google Sheets OAuth2** – for content calendar updates  
- 🔑 **GoToHuman API** – for review templates and approvals  

Any node with a ⚠️ icon likely needs a credential attached.

---

### 3️⃣ Replace Resource IDs

Update IDs in the nodes to match **your** environment:

- Google Drive folder IDs  
- Google Sheets document + sheet IDs  
- GoToHuman review template IDs  
- Any hard-coded URLs or webViewLinks  

Look for fields like:

```json
"folderId": "1i1DihjdnPBcE8RKvXXp5IepcNLBEM3mV"
"documentId": "1sywAEp2VEyvJG5Eyl-oLlN..."
"sheetName": "November"
"reviewTemplateID": "ITgIyUodUx4Y2moxhwlD"
