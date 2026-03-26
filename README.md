
# E-Commerce SWOT Deep Research Agent
> *Replacing hours of manual auditing with a 60-second AI-powered execution*

![n8n](https://img.shields.io/badge/n8n-v2.13-orange?style=flat-square&logo=n8n)
![Grok](https://img.shields.io/badge/Grok_API-Free_Tier-black?style=flat-square)
![Serper](https://img.shields.io/badge/Serper.dev-Free_2500%2Fmo-blue?style=flat-square)
![Status](https://img.shields.io/badge/Status-Live-brightgreen?style=flat-square)

---

##  What This Does

Drop any e-commerce store URL → Get a full **SWOT Analysis** in under 60 seconds.

This AI agent autonomously:
1. **Scrapes** the store's homepage content
2. **Researches** the brand across the web (competitors, reviews, positioning)
3. **Analyzes** everything using Grok AI
4. **Outputs** a structured JSON with Strengths, Weaknesses, Opportunities, Threats + audit scores

**No manual auditing. No copy-pasting. Just results.**

---

## Agent Architecture

```
URL Input
    ↓
HTTP Request → Fetch Homepage HTML
    ↓
Code Node → Extract Clean Text + Domain
    ↓              ↓
Serper Search    Page Data
(Web Intel)         ↓
    ↓           Merge Node
    └─────────────┘
              ↓
    Build Prompt Node
              ↓
    Grok AI (grok-3)
    [System: Senior E-com Consultant]
              ↓
    Parse & Format Output
              ↓
    Structured SWOT Data On Excel Sheet
```

---

## Output Format

```json
{
  "store": "brand-name.com",
  "summary": "Executive summary of the store...",
  "strengths": [
    { "point": "Strong Brand Identity", "detail": "..." }
  ],
  "weaknesses": [
    { "point": "No Live Chat Support", "detail": "..." }
  ],
  "opportunities": [
    { "point": "Untapped SEO Potential", "detail": "..." }
  ],
  "threats": [
    { "point": "Rising Ad Costs", "detail": "..." }
  ],
  "quick_wins": [
    "Add trust badges on checkout page",
    "Optimize product images for mobile"
  ],
  "audit_score": {
    "overall": 7,
    "ux": 6,
    "seo": 5,
    "trust": 7,
    "content": 6
  }
}
```

---

## Tech Stack

| Tool | Purpose | Cost |
|------|----------|------|
| **n8n** (v2.13) | Workflow automation engine | Free (self-hosted) |
| **Grok API** (grok-3) | AI analysis & SWOT generation | Free tier ($25 credit) |
| **Serper.dev** | Google search API for web intel | Free (2,500/month) |
| **HTTP Request Node** | Website scraping | Built-in |

**Total cost to run: $0** ✅

---

## Quick Setup (10 minutes)

### 1. Prerequisites
- n8n instance running (Hugging Face / Railway / local)
- [Grok API key](https://console.x.ai) — free
- [Serper.dev API key](https://serper.dev) — free

### 2. Import Workflow
```
n8n → Workflows → Import from File → upload swot_agent_workflow.json
```

### 3. Add Your Keys
- **Grok node** → Replace `YOUR_GROK_API_KEY_HERE` with your key
- **Serper node** → Credentials → Header Auth → `X-API-KEY` = your Serper key

### 4. Run It
1. Open `Start — Enter URL` node
2. Set `url` to any e-com store (e.g. `https://gulahmedshop.com`)
3. Hit **Execute Workflow**
4. Done ✅

---

## Files in This Repo

```
📂 ecom-swot-agent/
├── 📄 swot_agent_workflow.json   ← Import this into n8n
└── 📄 README.md                  ← You are here
```

---

## How to Update This Project

When you improve the workflow in n8n:
1. In n8n → open workflow → **⋮ menu → Download**
2. Replace `swot_agent_workflow.json` in this repo
3. Push to GitHub (see commands below)

```bash
git add swot_agent_workflow.json
git commit -m "update: improved SWOT prompt for better output"
git push
```

---

## Roadmap

- [ ] Add Notion output integration
- [ ] Slack notification when analysis is done
- [ ] Batch mode — analyze multiple URLs at once
- [ ] PDF report generation
- [ ] Competitor comparison mode (2 URLs → side-by-side SWOT)

---

## Author

Built as part of my **AI Automation Portfolio** — learning to build real agentic workflows with n8n, LLMs, and no-code tools.

> *"Automate the boring. Focus on the brilliant."*

---

## License

MIT — use it, fork it, build on it.
