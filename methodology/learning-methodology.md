# Review Methodology (how these artifacts are meant to be used)

Each artifact answers four questions about a security area:
1. **What is it?** — the risk, in plain language.
2. **How do I secure it?** — the engineering controls.
3. **How do I review it?** — the questions an assessor asks.
4. **How do I explain it?** — a 30-second, 2-minute, and 10-minute version.

## How to use this repo in a review
1. Start with **How to Review a New AI Agent** for the overall flow.
2. For each relevant domain, run the matching **checklist**.
3. Record findings and map them to the frameworks (one finding → many frameworks).
4. Assign a two-axis risk tier (data sensitivity × autonomy) and a Go / No-Go.
5. If an incident occurs, switch to the **incident-response** playbooks.

## Guardrails
Safe sample data only. Never real credentials/tokens. Never production. Authorized lab/staging only; results labeled as authorized testing. "Aligned as of [date]," never "compliant." Not legal advice.
