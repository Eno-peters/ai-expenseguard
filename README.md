AI ExpenseGuard
AI-powered expense verification tool that flags duplicate, inflated, or policy-violating employee expense claims, assigns a risk score, and explains why in plain English.
Status: Week 1 of 7-Week AI Build Challenge | Build window: 6 days Owner: Eno Peters

The Problem
Businesses lose money through duplicate, inflated, or policy-violating employee expense claims. Finance teams spend hours manually reviewing receipts and checking whether expenses are legitimate.
What This Does
Ingests an expense claim, its receipt, and the relevant company policy
Runs deterministic checks (duplicates, spend thresholds, missing documentation)
Uses AI to reason over ambiguous cases and produce a risk score (0-100)
Explains, in plain English, why a claim was flagged
Surfaces flagged claims to finance in a review dashboard
Goal
Help finance teams catch costly expense leakage faster and cut manual review time.

Tech Stack
Layer
Tool
Claim intake
Airtable Form / Tally
Workflow orchestration
n8n / Make.com
OCR
Google Cloud Vision API
System of record
Airtable
AI reasoning
Claude API
Dashboard
Airtable Interface / Softr
Alerts
Slack / Email

Full architecture and diagrams: see docs/architecture.md Full product doc: see docs/product-doc.pdf

Repository Structure
ai-expenseguard/
├── README.md
├── docs/
│   ├── product-doc.pdf          # Full product document with diagrams
│   ├── architecture.md          # Architecture diagrams (renders on GitHub)
│   └── prompts/
│       └── risk-scoring-prompt.md
├── workflows/
│   └── n8n-expenseguard.json    # Exported automation workflow
├── data/
│   └── sample-claims.csv        # Test/seed data
└── src/
    └── duplicate-check.py       # Custom logic (if/when needed)

Status / Build Plan
Day
Focus
Status
Day 1
Product doc, policy rules, Airtable schema
⬜
Day 2
Claim intake form + OCR wiring
⬜
Day 3
Duplicate + policy rule checks
⬜
Day 4
Claude prompt for scoring + explanation
⬜
Day 5
Dashboard + alerts
⬜
Day 6
Test data, end-to-end run, demo prep
⬜

Non-Goals (Week 1)
No real payroll/ERP integration (Airtable is the system of record for now)
No multi-currency/multi-language receipt support
No mobile app
No fraud investigation or legal action — this tool flags, humans decide
Contributing
This is a solo/small-team build for the AI Build Challenge. If contributing:
Create a branch off main (e.g. day2-ocr-setup)
Commit changes with clear messages
Open a pull request into main for review before merging
License
Internal build — license TBD.

