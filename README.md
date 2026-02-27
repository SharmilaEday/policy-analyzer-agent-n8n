Policy Analyzer Agent — n8n Workflow

> An agentic n8n workflow that fetches real-time policy data, runs AI-powered sentiment analysis and summarization via Gemini, and delivers structured results to Google Sheets and email — automatically.

---

## Overview

This workflow is a fully automated **policy intelligence agent** built in n8n. It monitors and analyzes policies (regulatory, corporate, government, etc.) in real time, uses **Google Gemini** to generate sentiment scores and plain-language summaries, and pushes the output to a **Google Sheets dashboard** while simultaneously sending a **formatted email report** to relevant stakeholders.

No manual reading. No copy-pasting. Just actionable policy insights on autopilot.

---

## What It Does

| Step | Action |
|------|--------|
| 1. **Trigger** | Scheduled or webhook-based trigger initiates the workflow |
| 2. **Data Fetch** | Pulls real-time policy content from web sources or APIs |
| 3. **Gemini AI Analysis** | Sends policy text to Gemini for sentiment analysis + summarization |
| 4. **Structured Output** | Parses AI response into clean, structured fields |
| 5. **Google Sheets** | Appends results (title, summary, sentiment, source, date) to a live sheet |
| 6. **Email Report** | Sends a formatted digest email with key findings to specified recipients |

---

## AI Capabilities (Powered by Gemini)

- **Sentiment Analysis** — Classifies policy tone as Positive / Neutral / Negative with a confidence score
- **Executive Summary** — Generates a concise, plain-language summary of each policy
- **Key Highlights** — Extracts the most important clauses or implications
- **Real-Time Grounding** — Uses Gemini's live data access to contextualize policies against current events

---

## Tech Stack

- **[n8n](https://n8n.io/)** — Workflow automation engine
- **Google Gemini API** — LLM for analysis and summarization
- **Google Sheets API** — Structured data output and dashboard
- **Gmail / SMTP** — Automated email delivery
- **HTTP Request Node** — Real-time policy data fetching

---

## Google Sheets Output Schema

| Column | Description |
|--------|-------------|
| `Date` | Timestamp of analysis |
| `Policy Title` | Name or headline of the policy |
| `Source` | URL or origin of the document |
| `Summary` | AI-generated plain-language summary |
| `Sentiment` | Positive / Neutral / Negative |
| `Confidence Score` | Sentiment confidence (0–100%) |
| `Key Highlights` | Bullet points of critical clauses |

---

## Email Output

Each run sends an auto-formatted email containing:
- **Subject:** `Policy Intelligence Report — [Date]`
- Summary of all policies analyzed in the run
- Sentiment breakdown at a glance
- Direct link to the full Google Sheets dashboard

---

## Getting Started

### Prerequisites
- n8n instance (self-hosted or cloud)
- Google Gemini API key
- Google Sheets & Gmail credentials configured in n8n

### Setup

1. **Import the workflow**
   - Download `policy-analyzer-agent.json` from this repo
   - In n8n, go to **Workflows → Import** and upload the file

2. **Configure credentials**
   - Add your **Gemini API key** in n8n credentials
   - Connect your **Google account** for Sheets and Gmail access

3. **Set your targets**
   - Update the HTTP Request node with the policy sources you want to monitor
   - Set your recipient email address in the Gmail node
   - Link your Google Sheet ID in the Sheets node

4. **Activate**
   - Toggle the workflow to **Active**
   - Trigger manually or wait for the schedule to kick in

---

## Repository Structure

```
├── policy-analyzer-agent.json   # n8n workflow export (import this)
├── README.md                    
└── sample-output/
    └── sample-sheet.png         
```

---

## Use Cases

- **Compliance teams** tracking regulatory changes in real time
- **Legal teams** monitoring policy shifts across jurisdictions
- **Researchers** analyzing sentiment trends in public policy
- **Businesses** staying ahead of industry-specific policy updates

---

## 🔮 Planned Improvements

- [ ] Multi-source aggregation with deduplication
- [ ] Slack notification integration
- [ ] Historical sentiment trend charts in Sheets
- [ ] Support for PDF policy documents via OCR

---

## Author

**Sharmila Eday**
[GitHub Profile]([https://github.com/yourusername](https://github.com/SharmilaEday)) • [LinkedIn]([https://linkedin.com/in/yourprofile](https://www.linkedin.com/in/sharmilaeday/))

---

## License

MIT License — free to use, modify, and share.

