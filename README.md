# 🔍 Phishing Analyzer

An AI-powered phishing email analyzer built with the Claude API. Paste a suspicious email and get an instant threat assessment — social engineering tactics, spoofed senders, credential harvesting patterns, urgency manipulation, and more.

**Live demo → [gaston-dev-web.github.io/phishing-analyzer](https://gaston-dev-web.github.io/phishing-analyzer/phishing-analyzer-v1.html)**

---

## What it does

Paste any suspicious email into the tool. It sends the content to Claude (Anthropic's AI) with a carefully engineered security prompt, then parses the response and displays:

- **Threat score** — 0 to 100, color-coded green / yellow / red
- **Threat level** — Low, Medium, or High
- **Plain English verdict** — a 2–3 sentence summary of what the email is and why it's suspicious
- **Indicator breakdown** — each finding listed with severity (high / medium / low / info)
- **Copy report** — exports a formatted plain-text report you can paste anywhere

---


---

## How it works

```
User pastes email
      ↓
Prompt is built with specific threat detection instructions
      ↓
POST request to Anthropic /v1/messages API (claude-sonnet-4-6)
      ↓
Response parsed as JSON { score, level, verdict, findings[] }
      ↓
UI renders score bar, verdict, and findings list
```

The key insight is **prompt engineering** — the model is instructed to look for specific phishing indicators and return structured JSON only, which the app then parses and renders. The prompt covers:

1. Urgency and fear tactics
2. Spoofed or lookalike sender domains
3. Credential harvesting attempts
4. Suspicious links and URL patterns
5. Social engineering and impersonation
6. Grammar anomalies common in phishing
7. Unusual attachment or download requests

---

## What I learned building this

- How to call the Anthropic Claude API from a frontend app
- Prompt engineering for structured JSON output
- Parsing and error-handling AI responses
- Translating real SOC analyst thinking into automated detection logic
- Building a tool that mirrors actual security workflows

---

## Tech stack

| Layer | Technology |
|---|---|
| Frontend | HTML, CSS, Vanilla JavaScript |
| AI | Anthropic Claude API (`claude-sonnet-4-6`) |
| Hosting | GitHub Pages |
| Dependencies | None — single HTML file, no frameworks |

---

## Try it yourself

Paste this test email to see the tool in action:

```
Subject: URGENT: Your account has been suspended

Dear Customer,

We detected unusual activity on your PayPal account. Your account has been
temporarily limited. To restore full access, please verify your identity
within 24 hours or your account will be permanently closed.

Click here to verify: http://paypa1-secure-login.com/verify

Please provide your full name, password, and card number to complete
verification.

PayPal Security Team
```

---

## Part of my cybersecurity portfolio

This project was built as part of my journey into cybersecurity. I'm currently:

- 📚 Studying on TryHackMe.
- 🎯 Preparing for CompTIA Security+
- 🔐 Specializing in Identity & Access Management (IAM)
- 🛠 Building hands-on projects to document real skills

**GitHub:** [github.com/gaston-dev-web](https://github.com/gaston-dev-web)  
**LinkedIn:** https://www.linkedin.com/in/gaston-garcia-45383815b/?locale=en

---

*Built with Claude by Anthropic · 2026*
