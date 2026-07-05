# Account Health Agent — Universal Edition

An AI-powered account intelligence tool that works with **any customer dataset**. Import your own Excel or CSV file, map your columns, and instantly get churn risk analysis, renewal alerts, and recommended next actions — powered by Claude AI.

## 🚀 [Launch the live app →](https://necker44.github.io/account-health-agent-universal/)

No database required. No installation. Works in any browser.

---

## How it works

1. **Enter your Claude API key** on the setup screen
2. **Import any CSV or Excel file** with your customer data
3. **Map your columns** — the app auto-detects common column names and lets you confirm
4. **Ask questions** in plain English — the AI analyzes your data and returns scored results

> *"Which accounts haven't been contacted in 60+ days and have renewals coming up?"*

---

## What data it accepts

Any CSV or Excel file with customer/account data. Your column names don't need to match exactly — you'll map them after upload.

| Field | Required | Description |
|---|---|---|
| Account Name | ✅ | Company or customer name |
| Monthly Revenue | ✅ | MRR, ARR, or any revenue figure |
| Days Until Renewal | ✅ | Days until contract expires or renews |
| Days Since Contact | ✅ | Days since last outreach or activity |
| Industry | optional | Sector or vertical |
| Region / Territory | optional | Geographic or sales territory |
| Products / Services | optional | What the account uses |

---

## Churn risk scoring model

| Signal | Condition | Points |
|---|---|---|
| Renewal proximity | Within 30 days | +40 |
| Renewal proximity | Within 31–90 days | +20 |
| Contact gap | No contact in 90+ days | +35 |
| Contact gap | No contact in 60–89 days | +20 |
| Contact gap | No contact in 45–59 days | +10 |
| Product depth | Only 1 product | +15 |

**Risk tiers:** High (55+) · Medium (30–54) · Low (< 30)

The model adapts to whatever fields exist in your file — missing fields are skipped gracefully.

---

## Example questions to ask

- *"Which accounts are at churn risk?"*
- *"Who hasn't been contacted in 60+ days?"*
- *"Show renewals due in the next 90 days"*
- *"What's my total revenue at risk?"*
- *"Which accounts should I call first this week?"*
- *"Which single-product accounts should I upsell?"*

---

## Tech stack

| Layer | Technology |
|---|---|
| AI agent | [Claude API](https://anthropic.com) (`claude-sonnet-4-6`) |
| File parsing | [SheetJS](https://sheetjs.com) (Excel + CSV) |
| Frontend | Vanilla HTML / CSS / JS — zero dependencies |
| Hosting | GitHub Pages |

---

## Getting a Claude API key

1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign up for a free account
3. Click **API Keys → Create Key**
4. Copy the key (starts with `sk-ant-…`)
5. Paste it into the app setup screen

Your key is stored only in your browser session and clears when you close the tab. It is never stored or sent anywhere except directly to the Claude API.

---

## Running locally

Just download `index.html` and open it in any browser — no server or installation needed. Works offline for the UI, requires internet only for the Claude API call.

---

## Security and privacy

- Your API key lives only in browser memory — clears on tab close
- Your customer data never leaves your browser — it is processed locally and sent only to the Claude API for analysis
- No backend, no database, no tracking
- Nothing is committed to this repository except the app code

---

## Also see

[Account Health Agent — Databricks Edition](https://github.com/necker44/account-health-agent-v2) — the companion project that connects to live Databricks Delta Tables via the SQL Statement API, with architecture documentation on the CORS constraint and production proxy pattern.

---

## Author

Built by Nick — Account Manager transitioning into Sales Operations & Data Analytics

[GitHub](https://github.com/necker44) · [LinkedIn](https://linkedin.com/in/yourprofile)
