# Incident Response

What the SOC does when an AI agent is manipulated or compromised. Each playbook follows the NIST 800-61 lifecycle (Detect & Analyze → Contain → Eradicate & Recover → Post-incident), adapted for agents — because an agent has a machine identity, persistent memory, and live tool access, so containment is a set of revocations, not a single process kill. Playbooks carry MITRE ATLAS technique tags and detection logic so AI incidents ride existing SOC tooling.

| ID | Playbook | Covers |
|---|---|---|
| IR-01 | [Prompt Injection — Incident Response](prompt-injection-incident-response.pdf) | The agent that was *tricked* — injected instructions in content it read |
| IR-02 | [Agent Compromise — Incident Response](agent-compromise-incident-response.pdf) | The agent that is *owned* — stolen credentials, hijacked identity, implanted memory, trojaned tool/config |

Together they cover the two fundamental agent incident types: a **content** incident (IR-01) and an **identity-and-state** incident (IR-02). IR-02 classifies compromises across five classes and orders containment revocation-first — kill the identity before cleaning the state.
