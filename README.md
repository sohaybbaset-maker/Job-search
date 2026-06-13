# Job Search Automation — Riyadh

Automated daily job search on **Michael Page** for senior-level roles in Riyadh, Saudi Arabia. Results are emailed daily to [sohaybbaset@gmail.com](mailto:sohaybbaset@gmail.com).

## Profile

- **Experience:** 13+ years
- **Current / Last Role:** VP @ Sahat Venture Studio
- **Expertise:** Business Development, Saudi market entry, soft-landing programme (35+ companies)
- **Notable Exit:** Ph Store
- **Education:** MBA Strategic Management — Grinta

## What This Does

| Step | Action |
|------|--------|
| 1 | Runs every day at 08:00 AST (05:00 UTC) |
| 2 | Searches Michael Page for VP / Director / GM roles in Riyadh |
| 3 | Filters by seniority and relevance to BD / Strategy |
| 4 | Saves a daily report in `reports/` |
| 5 | Emails the results to `sohaybbaset@gmail.com` |

## Files

```
.
├── README.md
├── reports/
│   └── YYYY-MM-DD_report.md      # Daily search results
├── automations/
│   ├── n8n_workflow.json          # n8n workflow definition
│   └── make_scenario.json         # Make (Integromat) scenario
└── .github/workflows/
    └── job-search-cv.yml          # GitHub Actions daily runner
```

## Setup

### Option A — GitHub Actions (no external tools needed)

1. Add the following secrets in **Settings → Secrets and variables → Actions**:

   | Secret | Value |
   |--------|-------|
   | `SMTP_HOST` | Your SMTP server (e.g. `smtp.gmail.com`) |
   | `SMTP_PORT` | `587` |
   | `SMTP_USER` | `sohaybbaset@gmail.com` |
   | `SMTP_PASS` | Your Gmail App Password |

2. The workflow in `.github/workflows/job-search-cv.yml` will run automatically every day.

### Option B — n8n

Import `automations/n8n_workflow.json` into your n8n instance and configure the Gmail credential.

### Option C — Make (Integromat)

Import `automations/make_scenario.json` and connect your Gmail account.

## Reports

Each run appends a new file under `reports/`. Format: `YYYY-MM-DD_report.md`.
