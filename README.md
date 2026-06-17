# 🚀 LinkedIn AI Automation Engine

An end-to-end, fully automated content pipeline built entirely within Google Sheets using Google Apps Script. This engine leverages Generative AI to ideate, draft, design, and publish professional LinkedIn posts with a "Human-in-the-Loop" approval system.

## 🧠 The Concept
I built this project to automate the B2B content lifecycle while maintaining strict quality control. Instead of relying on expensive third-party SaaS tools, this system uses a lightweight Google Sheet as the database and UI, calling external APIs to handle the heavy lifting. 

Nothing goes live without human approval, making it a safe, scalable solution for personal branding or digital marketing agencies.

---

## 🛠️ Tech Stack
* **Core Language:** JavaScript (Google Apps Script)
* **Database & UI:** Google Sheets
* **AI & NLP:** Google Gemini 1.5 Flash API
* **Image Generation:** Pollinations.ai (Text-to-Image API)
* **Publishing:** LinkedIn API (UGC Posts)
* **Automation:** Google Apps Script Time-Driven Triggers

---

## ⚙️ Architecture & Workflow (The 5 Steps)

**1. 🤖 The Brainstormer**
The system uses Gemini 1.5 to generate a week’s worth of cutting-edge topics related to Data Science, AI, and Automation, inserting them directly into the spreadsheet.

**2. 📩 The Editor (Human-in-the-Loop)**
The script compiles pending topics and automatically emails the user via Google `MailApp`. The user clicks a dynamic web-app link to approve topics with a single click.

**3. ✍️ The Ghostwriter**
Once a topic is marked "Approved", Gemini AI acts as a professional copywriter, drafting a clean, jargon-free LinkedIn post complete with targeted hashtags.

**4. 🎨 The Designer**
The AI reads the drafted post copy and writes a prompt for a "cinematic background image." It then passes this prompt to an image-generation API, returning a dynamic `=IMAGE()` formula back to the spreadsheet.

**5. 🚀 The Publisher**
The script authenticates with the LinkedIn Developer API using OAuth 2.0. It formats the text and image into a JSON payload and publishes it directly to the user's feed.

---

## 🚀 Setup & Installation

If you want to deploy this system yourself, follow these steps:

1. **Create a Google Sheet:** Name it `Content Pipeline` and set up 7 columns: *Topic ID, Date, Topic Idea, Approval Status, Content Status, Post Copy, Image URL*.
2. **Access Apps Script:** Go to `Extensions > Apps Script`.
3. **Add the Code:** Paste the `Code.gs` file from this repository into your editor.
4. **Environment Variables:** Update the configuration section with your own credentials:
   * `GEMINI_API_KEY`: Get this from Google AI Studio.
   * `LINKEDIN_TOKEN`: Generate this from the LinkedIn Developer Portal.
   * `YOUR_EMAIL`: For approval notifications.
5. **Deploy the Web App:** Click `Deploy > New Deployment > Web App`. Copy the deployment URL and paste it into the `WEB_APP_URL` variable so your email approval buttons work.
6. **Set Triggers:** Use the Apps Script clock icon to set up daily/weekly time-driven triggers for the functions.

---

## 📈 Future Improvements
* Build a dashboard to track post impressions and engagement directly in the spreadsheet.
* Add a secondary AI pass to generate comments to reply to the audience.
* Integrate OAuth token refreshing to keep the LinkedIn connection alive indefinitely. 

---
*Built from scratch to streamline B2B workflows and eliminate repetitive manual tasks.*
