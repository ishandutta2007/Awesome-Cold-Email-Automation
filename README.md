# Awesome-Cold-Email-Automation

# Top Cold Email Automation Platforms Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**
*Focused on Outreach Sequences, Email Warmup, Deliverability Optimization & Lead Enrichment*
**Last updated: September 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Cold Email Automation**. These tools help sales teams, agencies, and founders run multi-step outreach campaigns, warm up sending mailboxes, rotate inboxes to avoid spam filters, and track engagement metrics like opens, clicks, and replies.

**Examples** include Lemlist, Instantly, Smartlead, Mailshake, QuickMail, Woodpecker, Reply.io, Snov.io, GMass, and YAMM (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, custom outreach logic, and transparent deliverability data — ideal for teams that need full control over their sending infrastructure without per-seat SaaS fees or vendor lock-in.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[lemlist](https://lemlist.com/)**
  Personalized cold outreach platform with multichannel sequences (email + LinkedIn), image personalization, and built-in email warmup (Lemwarm). Known for its "emails that get replies" positioning and strong founder-led sales community.

- **[Instantly](https://instantly.ai/)**
  Cold email platform focused on deliverability and scale. Provides unlimited email accounts, automated warmup, inbox rotation, and a unified master inbox. Popular with agencies managing multiple client campaigns.

- **[Smartlead](https://smartlead.ai/)**
  All-in-one cold email infrastructure platform. Features unlimited mailbox rotation, AI-powered warmup, unified master inbox, and white-label agency capabilities. Strong focus on deliverability and scale for agencies and high-volume senders.

- **[Mailshake](https://mailshake.com/)**
  Sales engagement platform for cold email, social selling, and phone outreach. Provides mail merge, auto-follow-ups, and lead catcher for reply management.

- **[QuickMail](https://quickmail.com/)**
  Cold email platform designed for agencies and consultants. Provides inbox rotation, automated follow-ups, and a centralized inbox for managing multiple client accounts.

- **[Woodpecker](https://woodpecker.co/)**
  Cold email automation for B2B sales and agencies. Features A/B testing, condition-based sequences, and a "cold email academy" for best practices.

- **[Reply.io](https://reply.io/)**
  Multichannel sales engagement platform with email, LinkedIn, and calling capabilities. Features AI-powered email writing, B2B database, and meeting booking integration.

- **[Snov.io](https://snov.io/)**
  All-in-one cold outreach platform combining email finding, verification, drip campaigns, and CRM. Includes a Chrome extension for finding emails on websites.

- **[GMass](https://gmass.co/)**
  Cold email and mail merge tool that works inside Gmail. Provides mass email, follow-ups, and tracking without leaving the Gmail interface.

- **[YAMM](https://yamm.com/)**
  Yet Another Mail Merge — Google Sheets add-on for sending personalized mass emails through Gmail. Simple, spreadsheet-driven approach to cold outreach.

## Open-Source GitHub Projects

### Full Outreach Platforms

- **[Warmbly](https://github.com/warmbly/warmbly)**
  **The largest open-source B2B cold outreach and email warmup platform.** Apache License 2.0. Runs campaigns from your own mailboxes with a **shared dashboard** for opens, clicks, and replies. **Warmup uses a pool of monitored mailboxes** — not throwaway accounts — with automatic spam rescue and realistic engagement patterns. Features multi-step sequences, unified inbox, CRM (contacts, pipelines, deals, tasks), visual reply playbooks with AI steps, and integrations (HubSpot, Slack, Zapier, REST API, webhooks). **Self-hosting with zero cloud dependencies**: one command (`curl -fsSL https://warmbly.com/install.sh | sh`) brings up the full stack on local open-source pieces — no AWS, GCP, Stripe, or Kafka required. Workers are interchangeable Go services that send mail through each mailbox's own provider, not the worker's IP .

- **[Pigeon](https://github.com/tarinagarwal/Pigeon)**
  **Open-source cold email outreach and deliverability platform.** Features multi-step sequences with per-step delays, A/B testing with auto-selected winner (scored 60% on reply rate, 40% on open rate), **inbox rotation** mixing Gmail and SMTP mailboxes, scheduling with timezone and weekday control, and **three layers of volume control** (campaign daily cap, per-inbox cap hard-limited to 50/day, ramp-up tier by inbox age). **Mailbox warmup** with multi-turn threaded conversations using correct `In-Reply-To` and `References` headers. **Automatic spam rescue** opens messages, marks them important, and moves them out of spam. **Pairing risk scoring** evaluates how artificial a sender-receiver pairing looks (weights: recent pair reuse 0.45, reciprocity cap 0.20, provider concentration 0.20, domain concentration 0.15) and ships in `shadow` mode. **DNS automation** writes SPF, DKIM, DMARC to Cloudflare, GoDaddy, Namecheap, or Google Cloud DNS. Per-recipient AI writing with your own API key (OpenAI, Anthropic, Gemini, DeepSeek, Grok, Groq). Tech stack: Next.js 16, React 19, TypeScript, MongoDB, Docker Compose .

- **[Emareach](https://github.com/ritik-prog/emareach)**
  **Production-grade open-source AI email marketing platform** with automation, campaigns, deliverability, analytics, and self-hosting. Features campaigns (sequences, scheduling, per-inbox limits, A/B templates), **mailbox warmup with LLM-generated threads**, spam→inbox recovery, SPF/DKIM/DMARC checks, Gmail/Outlook OAuth, contacts enrichment and email validation, open/click tracking with custom tracking domains, and a support bot using ChromaDB RAG. **Billing** includes Razorpay (India) and Lemon Squeezy (international). **Admin panel** for user, plan, warmup, and infrastructure management. Tech stack: FastAPI (Python 3.12), Next.js 16, MongoDB 7, ChromaDB, Groq LLM, Serper, SendGrid. **Monorepo with Terraform for AWS deployment** (EC2/ALB/ECR/IAM/SSM) .

### AI-Powered Outreach Agents

- **[free_outbound_agent](https://github.com/Dumebii/free_outbound_agent)**
  **Open-source AI-powered outbound email agent.** Finds prospects on GitHub and Dev.to, writes personalized emails with Claude or GPT-4, and sends via any SMTP provider. Features configurable **ICP segments** (matched against lead bios), GitHub search queries, Dev.to tag search, Product Hunt topics, multi-step follow-up sequences (configurable delays and subject hints), and daily send limits. **LinkedIn pipeline** generates personalized messages at volume while keeping you in control of actual sending (copy-paste queue, ~30 seconds per lead) to avoid account flags. Config uses YAML with `provider: claude` or `openai`, tone control, and banned words. **Python-based** .

- **[gtm-mcp](https://github.com/impecablemee/gtm-mcp)**
  **Open-source B2B cold outreach pipeline for Claude Code.** One `/launch` command orchestrates: find companies (Apollo), classify with AI, extract contacts, write deeply personalized sequences, push to SmartLead. **Zero LLM calls inside the server** — all reasoning stays in Claude Code using domain knowledge encoded as markdown skills. Features **strategy approval** and **activation** checkpoints where you decide. **49 tools** for config, Apollo search, website scraping, contact extraction, and campaign creation. **Via negativa classification** (exclude non-targets, not define targets) achieves 97% accuracy. **Max 200 Apollo credits** per run (default). **Python-based with stdio transport** for Claude Code integration .

- **[cold-outreach-agent](https://github.com/jordan-jakisa/cold-outreach-agent)**
  **Simple cold outreach email agent for salespeople.** Generates sales emails based on product, user profile, pain points, and description using GPT-3.5. Sends emails to people listed in a CSV file. **Streamlit app** with LangChain and smtplib. Minimal setup: `.env` file with `USER_EMAIL` and `EMAIL_PASSWORD` (app password), then `streamlit run src/main.py` .

- **[Automated-Outreach-Pipeline](https://github.com/AnanyaGubba/Automated-Outreach-Pipeline)**
  **Fully autonomous cold-outreach system** using multiple third-party APIs. Starting from a single seed company domain, executes four stages: lookalike company discovery (Ocean.io), decision-maker identification (Prospeo), verified work email resolution (Eazyreach), and personalized outreach sending (Brevo). **Safety checkpoint** displays summary before sending. Handles API failures, rate limits, and missing data gracefully. **Python 3.13+** .

### Sending Infrastructure & Libraries

- **[elxmail](https://www.npmjs.com/package/elxmail)**
  **Cold email sending SDK with built-in warmup, rotation, and deliverability controls.** Features **bulk send with intelligent spacing** (accepts 5,000 emails immediately, spaces over hours respecting rate limits, warmup curves, provider rules), **DNS validation** (SPF, DKIM, DMARC, rDNS), **content spam scoring** (0-100), **suppression management**, **queue control** (pause/resume/drain), **warmup status tracking** (per-domain current limits and health), **analytics** (by domain, provider, IP, time series), and **DKIM key generation**. **Event system** for every lifecycle stage: sent, delivered, bounced (hard/soft auto-suppressed), complained (auto-suppressed), opened, throttle limits, warmup limits, DNS warnings. **Node.js SDK**. The README includes a **deliverability playbook** covering infrastructure setup (domains, IPs, SMTP servers), DNS configuration, and phased warmup .

### LinkedIn Outreach (Self-Hosted)

- **[Linki](https://github.com/moaljumaa/linki)**
  **Self-hosted AI SDR for B2B outreach** — LinkedIn sequences, cold email, and lead enrichment. **No per-seat pricing, no SaaS middleman.** Features multichannel campaigns (LinkedIn + email in one sequence), **server-side LinkedIn login** (headless, handles email/SMS codes and mobile-app device approval, captures httpOnly Sales Navigator cookies), Sales Navigator import, CSV import, Apollo.io enrichment, unified inbox with email + LinkedIn reply detection, **pinned browser fingerprint** (eliminates forced logouts), and **email account ramp-up**. **Go-based runner** with Docker deployment .

### Additional Strong Open-Source Options

- **Full Platforms**: **Warmbly** (largest, Apache 2.0, zero cloud deps), **Pigeon** (comprehensive, Next.js/MongoDB), **Emareach** (production-grade, FastAPI/Next.js) .
- **AI Agents**: **free_outbound_agent** (GitHub/Dev.to sourcing), **gtm-mcp** (Claude Code pipeline), **cold-outreach-agent** (Streamlit) .
- **Sending SDK**: **elxmail** (Node.js, warmup, DNS, analytics) .
- **LinkedIn + Email**: **Linki** (self-hosted, server-side auth) .
- **Pipeline Integration**: **SmartLead Activepieces piece** (MIT, open source, self-hostable) .

**Frameworks for building custom systems**: Combine **Warmbly** for the complete outreach platform with warmup and CRM, **Pigeon** for multi-inbox rotation and deliverability automation, **elxmail** for the sending SDK with warmup and DNS validation, and **Linki** for LinkedIn + email multichannel sequences. Add **MongoDB/PostgreSQL** for persistence and **Docker** for deployment.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Cold email platforms handle sensitive prospect data; ensure compliance with GDPR, CAN-SPAM, and relevant anti-spam regulations.
- **Open-source reality**: The open-source ecosystem for cold email automation is **mature and production-ready**. **Warmbly** provides a complete platform with zero cloud dependencies and one-command self-hosting . **Pigeon** offers comprehensive deliverability features including pairing risk scoring and DNS automation . **Emareach** delivers production-grade AI marketing with billing and admin panels . **elxmail** provides a sending SDK with warmup, DNS validation, and content scoring . For teams wanting the deepest control over their sending infrastructure without per-seat fees, these open-source options are **genuinely viable alternatives** to commercial platforms like Smartlead and Instantly.

---

**Made for sales teams, agencies, founders, and growth operators.**
Let's make cold email automation more open, transparent, and deliverable.
