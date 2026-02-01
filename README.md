AI-Assisted VAPT Pipeline (Burp → n8n → AI)
An experimental but practical AI-assisted VAPT workflow that parses Burp Suite XML exports, converts HTTP traffic into deterministic JSON, and uses AI agents to generate manual security testing hypotheses mapped to OWASP Top 10.

⚠️ This tool does not exploit vulnerabilities. It assists human testers with triage, reasoning, and test planning.

🎯 Goals
Parse real Burp Suite traffic (XML → JSON)

Normalize and clean HTTP request data

Detect security-relevant patterns (auth gaps, sensitive paths, IDOR hints)

Generate safe, manual test hypotheses

Reduce noise during VAPT and bug bounty testing


🔧 Tech Stack
Burp Suite – HTTP traffic capture

n8n – Workflow orchestration

JavaScript – Deterministic parsing & triage

AI Agents (LLMs) – Security reasoning & reporting

Webhook-based architecture – SaaS-ready

🧪 What the AI Does (and Does NOT)
✅ AI DOES:
Map findings to OWASP Top 10

Suggest manual test ideas

Highlight potential risks (IDOR, BAC, misconfig)

Explain why something is risky

❌ AI DOES NOT:
Exploit vulnerabilities

Bypass authentication

Perform active attacks

Replace a human pentester

📄 Sample Output (Simplified)
{
  "risk_summary": "Medium",
  "owasp_categories": [
    "A01:2021 - Broken Access Control"
  ],
  "key_findings": [
    "Sensitive endpoint accessed without authentication",
    "User-controlled identifier in query parameter"
  ],
  "test_hypotheses": [
    "Test IDOR by swapping user identifiers",
    "Verify access control without authentication headers"
  ]
}
⚠️ Known Limitations
XML edge cases vary across Burp versions

AI output depends on input quality

Empty or truncated requests reduce confidence

Not suitable for automated exploitation

See docs/limitations.md

🔮 Future Work
Confidence scoring per finding

Token-aware AI gating

Auth-flow correlation

Multi-request session analysis

Export to PDF / Markdown reports

🤝 Who Is This For?
VAPT analysts

Bug bounty hunters

Security consultants

AppSec teams

Students learning AI × Security
