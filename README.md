# 🚀 SEO Content Gap Analyzer  
AI-Powered Competitive Content Intelligence (n8n + Gemini)

Automate SEO competitor research and generate structured content strategy reports in under 60 seconds.

---

## 🎯 Overview

This n8n workflow performs automated SEO content gap analysis by:

- Fetching top-ranking Google results
- Extracting competitor page structure
- Aggregating SEO elements
- Using Google Gemini AI to identify:
  - Common ranking topics
  - Content gaps
  - Competitor strengths
  - Prioritized recommendations
  - Suggested content outline

Output: Downloadable structured text report.

---

## 🏗 Workflow Architecture

Form Trigger  
↓  
SerpAPI (Google Results)  
↓  
Extract Top 5 URLs  
↓  
Fetch HTML Content  
↓  
Extract SEO Elements (Title, H1, H2, Meta, Body)  
↓  
Aggregate Data  
↓  
Gemini AI Analysis  
↓  
Generate Report File  

---

## 🔌 Data Sources

- **User Input** – Keyword via form trigger  
- **SerpAPI** – Top Google organic results  
- **Competitor Pages** – HTML scraping  
- **Google Gemini (models/gemini-2.5-flash)** – AI analysis  

---

## ⚙️ Setup Instructions

### 1. Prerequisites

- n8n (Cloud or Self-hosted)
- SerpAPI API key
- Google AI API key

---

### 2. Add Credentials in n8n

**SerpAPI**
- Credentials → New → SerpAPI
- Add API key

**Google AI**
- Credentials → New → Google AI
- Add API key

---

### 3. Import Workflow

- Import `seo-content-gap-analyzer-n8n.json`
- Save

---

### 4. Assign Credentials

- Select SerpAPI credential in SerpAPI node
- Select Google AI credential in Gemini node

---

### 5. Run Workflow

Option A – Web Form  
- Open Form Trigger URL  
- Enter keyword  
- Wait ~30–60 seconds  
- Download report  

Option B – API Call

```bash
curl -X POST "YOUR_FORM_URL" \
  -H "Content-Type: application/json" \
  -d '{"keyword":"content marketing strategy"}'
