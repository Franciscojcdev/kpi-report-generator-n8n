# 📊 KPI Operations Report Generator

Automated workflow that reads operational KPI data from Google Sheets, analyzes it with Claude AI, and delivers a professional executive report to your inbox — on demand.

## 📌 What it does

With a single click, this workflow:

1. Reads monthly KPI data from a Google Sheet
2. Aggregates all rows into a single dataset
3. Sends the data to Claude AI for deep analysis
4. Generates a structured executive HTML report
5. Delivers it directly to your email

No manual analysis. No copy-pasting. Just actionable insights from your data.

## 🛠️ Tech Stack

| Tool | Role |
|---|---|
| **n8n** | Workflow orchestration (self-hosted on Railway) |
| **Google Sheets** | Data source (KPI input) |
| **Claude AI (Haiku)** | Data analysis and report generation |
| **Gmail API** | Email delivery |
| **Railway** | Cloud hosting (PostgreSQL + Redis + n8n) |

## 🔄 Workflow Architecture

```
Manual Trigger
      ↓
Google Sheets (Get Rows)
      ↓
Aggregate (All Item Data)
      ↓
Claude AI Analysis
  - Executive Summary
  - Top Performing Months
  - Critical Issues Detected
  - KPI Trends Analysis
  - Actionable Recommendations
      ↓
Gmail Delivery (HTML Report)
```

## 📧 Report Structure

The generated report includes:

1. **Executive Summary** — Annual overview in 3-4 sentences
2. **Top Performing Months** — Best 3 months with detailed breakdown
3. **Critical Issues** — Worst months, anomalies and red flags
4. **KPI Trends Analysis** — Revenue vs Target, Orders, Customer Satisfaction, On-Time Delivery
5. **Actionable Recommendations** — 3-5 concrete actions with priority and timeline

## 📊 KPI Data Schema

| Column | Description |
|---|---|
| Month | Period (e.g. Jan-2026) |
| Revenue_USD | Actual revenue |
| Target_Revenue_USD | Revenue target |
| Orders_Completed | Completed orders |
| Orders_Pending | Pending orders |
| Orders_Cancelled | Cancelled orders |
| Avg_Processing_Time_Days | Average processing time |
| Customer_Satisfaction_Score | Score 1-5 |
| Team_Headcount | Team size |
| Cost_Per_Order_USD | Cost efficiency metric |
| On_Time_Delivery_Pct | Delivery performance % |

## ⚙️ Setup

### Prerequisites
- n8n instance (self-hosted or cloud)
- Anthropic API key
- Google Sheets with KPI data
- Gmail OAuth2 credentials (Google Cloud Console)

### APIs Required (Google Cloud Console)
- Gmail API
- Google Sheets API

### Environment Variables
```
N8N_ENCRYPTION_KEY=your_key
ANTHROPIC_API_KEY=your_key
```

### Deployment
This workflow runs on a self-hosted n8n instance deployed on **Railway** with:
- PostgreSQL for workflow persistence
- Redis for queue management
- Automatic HTTPS via Railway

## 📁 Files

- `KPI Operations Report Generator.json` — n8n workflow export (importable directly into n8n)
- `kpi_operations.csv` — Sample KPI dataset (12 months, 2026)

## 🚀 Author

**Francisco Castro** — Business Analyst | Automation & AI  
[Portfolio](https://franciscojcdev.github.io) · [LinkedIn](https://linkedin.com/in/francisco-castro-126122191)
