# AI Agent Security Assessment

A practical toolkit for reviewing the security of AI agents before they reach production — the review methodology, checklists, and incident-response playbooks I use when assessing an AI agent across eight security domains and mapping findings to recognized frameworks.

This is defensive security work: how to *review* and *respond*, not how to attack. Everything here uses safe sample data and assumes authorized environments only.

---

## Why this exists

AI agents are a new attack surface: they read untrusted input, hold context and memory, and call tools with real permissions. Reviewing one is not the same as reviewing a web app. This repo turns an open-ended "is this agent safe?" into a repeatable process — intake, an eight-domain review, a defensible risk tier, and a Go / No-Go recommendation — plus what the on-call analyst does when prevention fails.

## What's inside

### 📋 Methodology
- **[How to Review a New AI Agent](methodology/how-to-review-an-ai-agent.pdf)** — the end-to-end methodology: intake → 8 domains → two-axis risk tier → Go/No-Go.

### ✅ Review checklists
Hand-to-a-developer checklists, one per high-value area:
- **[Prompt Injection Checklist](playbooks/prompt-injection-checklist.pdf)** — the six injection surfaces, direct vs. indirect, controls, and tests.
- **[Secure RAG Checklist](playbooks/secure-rag-checklist.pdf)** — poisoning, permission bypass, and cross-user leakage.
- **[Logging Requirements](playbooks/logging-requirements.pdf)** — what to log, where it goes, and what the SOC must be able to do.
- **[Tool Approval Checklist](playbooks/tool-approval-checklist.pdf)** — semi-hostile tools, least privilege, and the actions that must be gated.

### 🚨 Incident response
Prevention checklists say how to *stop* an attack. These say what to do when it already happened:
- **[Prompt Injection — Incident Response](incident-response/prompt-injection-incident-response.pdf)** — NIST 800-61 lifecycle adapted for agents: classify, contain (an agent has an identity, memory, and live tools), collect evidence, and write the detection so it fires next time. Includes MITRE ATLAS technique tags and Sentinel-style detection logic.

## The eight security domains

1. LLM & Prompt Security · 2. RAG & Data Security · 3. Tool & API Security · 4. Agentic Risk · 5. Adversarial ML · 6. Identity & Access · 7. Runtime & Guardrails · 8. Observability & SOC Monitoring

## Frameworks referenced

OWASP LLM Top 10 · OWASP Agentic Top 10 · OWASP API Top 10 · MITRE ATLAS · NIST AI RMF · ISO/IEC 42001 — findings are mapped through a single crosswalk so one review addresses many obligations at once.

## Roadmap

See **[roadmap.md](roadmap.md)**. In progress: extending the incident-response set (agent compromise, data-leakage investigation, model-abuse detection) and adding worked sample assessments.

---

## Scope & disclaimers

- **Defensive only.** This is review and response guidance, not attack tooling.
- **Safe data only.** Never use real credentials, tokens, or customer data; never test production. Any dynamic testing is against explicitly authorized lab/staging environments.
- **Framework language.** Reports produced with this method state *"aligned with recognized frameworks as of [date]"* — never *"compliant."*
- **Not legal advice.**

## License

Documentation released under the MIT License — see [LICENSE](LICENSE).
