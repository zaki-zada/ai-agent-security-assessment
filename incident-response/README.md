# Incident Response

What the SOC does when an AI agent is manipulated or compromised. Each playbook follows the NIST 800-61 lifecycle (Detect & Analyze → Contain → Eradicate & Recover → Post-incident), adapted for agents — because an agent has a machine identity, persistent memory, and live tool access, so containment is a set of revocations, not a single process kill. Playbooks carry MITRE ATLAS technique tags and detection logic so AI incidents ride existing SOC tooling.

| ID | Playbook | Status |
|---|---|---|
| IR-01 | Prompt Injection — Incident Response | ✅ |
| IR-02 | Agent Compromise (general) | ⬜ planned |
| IR-03 | Data Leakage Investigation | ⬜ planned |
| IR-04 | Model Abuse Detection | ⬜ planned |
