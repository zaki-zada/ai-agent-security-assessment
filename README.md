# AI Agent Security Assessment

A practical toolkit for reviewing the security of AI agents before they reach production — the review methodology, checklists, and incident-response playbooks I use when assessing an AI agent across eight security domains and mapping findings to recognized frameworks.

This is defensive security work: how to *review* and *respond*, not how to attack. Everything here uses safe sample data and assumes authorized environments only.

---

## Why this exists

AI agents are a new attack surface: they read untrusted input, hold context and memory, and call tools with real permissions. Reviewing one is not the same as reviewing a web app. This repo turns an open-ended "is this agent safe?" into a repeatable process — intake, an eight-domain review, a defensible risk tier, and a Go / No-Go recommendation — plus what the on-call analyst does when prevention fails.

**Where to start:** reviewing an agent tomorrow? Begin with the [methodology](methodology/how-to-review-an-ai-agent.pdf). Working in a SOC? Begin with the [incident-response playbooks](incident-response/).

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
Prevention checklists say how to *stop* an attack. These say what to do when it already happened — covering the two fundamental agent incident types:
- **[Prompt Injection — Incident Response](incident-response/prompt-injection-incident-response.pdf)** — the agent that was *tricked*: injected instructions in content it read. NIST 800-61 lifecycle adapted for agents, MITRE ATLAS technique tags, and KQL-style detection logic.
- **[Agent Compromise — Incident Response](incident-response/agent-compromise-incident-response.pdf)** — the agent that is *owned*: stolen credentials, hijacked identity, implanted memory, or a trojaned tool/config. Five compromise classes, identity-blast-radius severity, and revocation-first containment.

## The eight security domains

| # | Domain | In one line |
|---|---|---|
| 1 | LLM & Prompt Security | Every channel that carries text into the model is an injection surface |
| 2 | RAG & Data Security | Poisoning, permission bypass, and cross-user leakage in retrieval |
| 3 | Tool & API Security | Treat every tool as semi-hostile; gate high-impact actions |
| 4 | Agentic Risk | Kill switch, memory poisoning, bounded blast radius |
| 5 | Adversarial ML | Jailbreaks, evasion, and multiturn / indirect manipulation |
| 6 | Identity & Access | One unique identity per agent, least privilege, JIT elevation |
| 7 | Runtime & Guardrails | Deterministic controls in code, human-in-the-loop for consequence |
| 8 | Observability & SOC | Logged to the SIEM; the SOC can identify, detect, and respond |

## Frameworks referenced

OWASP LLM Top 10 · OWASP Agentic Top 10 · OWASP API Top 10 · MITRE ATLAS · NIST AI RMF · NIST 800-61 (incident response) · ISO/IEC 42001 — findings are mapped through a single crosswalk so one review addresses many obligations at once.

---

## Scope & disclaimers

- **Defensive only.** This is review and response guidance, not attack tooling.
- **Safe data only.** Never use real credentials, tokens, or customer data; never test production. Any dynamic testing is against explicitly authorized lab/staging environments.
- **Framework language.** Reports produced with this method state *"aligned with recognized frameworks as of [date]"* — never *"compliant."*
- **Not legal advice.**

## License

Documentation released under the MIT License — see [LICENSE](LICENSE).
