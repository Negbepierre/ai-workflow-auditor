# Recruiter Manual
## AI Workflow Auditor

**Live URL:** https://aiworkfloauditor.netlify.app  
**GitHub:** https://github.com/Negbepierre/ai-workflow-auditor  
**Built by:** Inegbenose Pierre

---

## What This Tool Does

The AI Workflow Auditor analyses a business's manual workflows and produces a prioritised report of automation opportunities using Claude AI. Each opportunity is rated by impact and effort so businesses know exactly where to start.

---

## How to Test It (Under 2 Minutes)

**Step 1** — Go to https://aiworkfloauditor.netlify.app

**Step 2** — Fill in the form:
- Business Name: any company name
- Industry: e.g. Marketing, Legal, HR, Finance
- Team Size: select from dropdown
- Workflows: describe 2-3 manual tasks the team does regularly

Example workflows to paste in:
> "We manually copy leads from emails into a spreadsheet every morning. We write the same weekly report every Friday by hand. We send individual welcome emails to every new client manually."

**Step 3** — Click **Run Workflow Audit**

**Step 4** — Wait 10-15 seconds for Claude AI to analyse the workflows

**Step 5** — Review the formatted report showing automation opportunities with impact and effort ratings

---

## What Happens Behind the Scenes

1. Form submits data via HTTP POST to an n8n webhook
2. n8n passes the data to the Claude API with a structured prompt
3. Claude analyses the workflows and returns a JSON report
4. A JavaScript code node formats the JSON into HTML cards
5. The report is returned to the browser and displayed
6. The audit is automatically logged to an Airtable database

---

## Technical Concepts Demonstrated

| Concept | Implementation |
|---------|---------------|
| LLM API integration | Anthropic Claude API via n8n |
| Prompt engineering | Structured JSON output prompting |
| Workflow automation | n8n with 5 connected nodes |
| RESTful APIs | HTTP POST webhook, JSON responses |
| Database logging | Airtable auto-logging every audit |
| Frontend development | HTML, Tailwind CSS, async JavaScript |
| Deployment | Netlify continuous deployment from GitHub |
| Version control | Git, GitHub with commit history |

---

## Database

Every audit run is automatically logged to Airtable with:
- Business name and industry
- Date and time of audit
- Number of opportunities identified
- Full HTML report

---

## Interview Talking Points

**What problem does it solve?**
SMEs don't know which of their workflows are worth automating or where to start. This tool gives them an AI-generated, prioritised answer in under 15 seconds.

**Why n8n instead of building a custom backend?**
n8n allowed faster prototyping while still demonstrating API connectivity, data transformation, and multi-step automation — the same concepts that underpin any backend service.

**What would you improve in version 2?**
Email delivery of reports, a dashboard showing trends across all audits, Slack notifications, and user accounts so businesses can track their automation progress over time.