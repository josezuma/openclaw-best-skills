# OpenClaw Best Skills

A curated list of the best **skills** for [OpenClaw](https://openclaw.nousresearch.com) — the autonomous AI agent that runs locally on your machine.

This repo helps you get started fast: each skill solves a real problem, and they're all community-tested.

---

## Table of Contents

- [What is a skill in OpenClaw?](#what-is-a-skill-in-openclaw)
- [How to install a skill](#how-to-install-a-skill)
- [Skills by category](#skills-by-category)
  - [Coding & Software Development](#coding--software-development)
  - [Git & GitHub](#git--github)
  - [Web & Frontend](#web--frontend)
  - [DevOps & Cloud](#devops--cloud)
  - [Browser & Automation](#browser--automation)
  - [Productivity & Tasks](#productivity--tasks)
  - [AI & LLMs](#ai--llms)
  - [Search & Research](#search--research)
  - [Marketing & Sales](#marketing--sales)
  - [Communication](#communication)
  - [Notes & PKM](#notes--pkm)
  - [Image & Video Generation](#image--video-generation)
  - [PDF & Documents](#pdf--documents)
- [Essential skills to start](#essential-skills-to-start)
- [Where to find more skills](#where-to-find-more-skills)
- [Contributing](#contributing)

---

## What is a skill in OpenClaw?

A **skill** in OpenClaw is a markdown file — or a directory with multiple files — that teaches the agent how to do something specific. Think of it as "plug-and-play" for capabilities:

- You tell OpenClaw _"use the `plan` skill"_ and it automatically knows how to structure action plans.
- You say _"load `test-driven-development`"_ and it applies TDD without you explaining the RED-GREEN-REFACTOR cycle.

Skills are OpenClaw's main extensibility mechanism. They live in `~/.openclaw/skills/` and are installed from [ClawHub](https://clawhub.ai), the official public registry, or from individual repositories.

OpenClaw is the **autonomous fork** of Hermes Agent: same open-source DNA, same skill concept, but operated as a fully independent CLI agent with its own ecosystem, registry, and community.

---

## How to install a skill

```bash
# 1. Install from ClawHub (recommended)
openclaw skills install <skill-slug>

# 2. Or use ClawHub CLI
npx clawhub install <skill-slug>

# 3. Clone this repo (or download individual skills)
git clone https://github.com/josezuma/openclaw-best-skills.git
cd openclaw-best-skills
cp -r skills/<name> ~/.openclaw/skills/
```

To load a skill in a session, OpenClaw detects it automatically by name. If you need to view its content:

```bash
cat ~/.openclaw/skills/<name>/SKILL.md
```

---

## Skills by category

### Coding & Software Development

| Skill | What it does | Why use it |
|-------|----------|----------------|
| [plan](https://clawhub.ai/voltagent/plan) | Writes actionable plans in markdown. Small tasks, exact paths, complete code. | Prevents the agent from coding without direction. Use it BEFORE writing code. |
| [test-driven-development](https://clawhub.ai/voltagent/tdd) | Enforces RED-GREEN-REFACTOR cycle. Writes tests before code. | Eliminates false positives. The agent can't claim "it works" without green tests. |
| [systematic-debugging](https://clawhub.ai/voltagent/debug) | 4-phase debugging: reproduce, isolate, understand, fix. | The agent doesn't guess. Follows a real forensic process. |
| [spike](https://clawhub.ai/voltagent/spike) | Throwaway experiments to validate an idea before building. | Saves hours building in the wrong direction. |
| [code-review](https://clawhub.ai/voltagent/code-review) | Automated pre-commit review: security scan, quality gates, auto-fix. | Catches bugs, secrets, and code smells before push. |
| [simplify-code](https://clawhub.ai/voltagent/simplify) | Multi-agent refactoring of recent code. | Safe refactoring. Each agent reviews the others' work. |
| [node-debug](https://clawhub.ai/voltagent/node-debug) | Debug Node.js with `--inspect` + DevTools Protocol from the agent. | When the stack trace isn't enough — inspect live variables. |
| [python-debug](https://clawhub.ai/voltagent/python-debug) | Debug Python with pdb REPL + remote breakpoints. | Same but for Python. |
| [code-indexer](https://clawhub.ai/voltagent/code-indexer) | Indexes the codebase and answers architecture questions. | For large codebases where grep isn't enough. |
| [agent-audit](https://clawskills.sh/skills/sharbelayy-agent-audit) | Audits your agent setup: performance, cost, ROI. | Know if your configuration is optimized. |

### Git & GitHub

| Skill | What it does | Why use it |
|-------|----------|----------------|
| [github-auth](https://clawhub.ai/voltagent/github-auth) | Auth setup: tokens, SSH, gh CLI login. | The first thing you need for any GitHub operation. |
| [pr-workflow](https://clawhub.ai/voltagent/pr-workflow) | Complete lifecycle: branch, commit, open PR, CI, merge. | Without this skill the agent doesn't know the correct order. |
| [github-issues](https://clawhub.ai/voltagent/github-issues) | Create, triage, label, assign issues from the agent. | Issue management without leaving the terminal. |
| [auto-pr-merger](https://clawskills.sh/skills/autogame-17-auto-pr-merger) | Automates checkout, merge, and push of GitHub PRs. | For automatic merges when checks pass. |
| [bitbucket-automation](https://clawskills.sh/skills/sohamganatra-bitbucket-automation) | Automates repos, PRs, and pipelines on Bitbucket. | GitHub alternative for teams on Bitbucket. |
| [gitops-deploy](https://clawhub.ai/voltagent/gitops) | GitOps deploy: push to branch = auto deploy. | Declarative infrastructure from the agent. |
| [azure-devops](https://clawskills.sh/skills/pals-software-azure-devops) | Lists projects, repos, branches; creates PRs; checks builds. | For teams on Azure DevOps. |

### Web & Frontend

| Skill | What it does | Why use it |
|-------|----------|----------------|
| [design-mockup](https://clawhub.ai/voltagent/design-mockup) | Throwaway HTML mockups: 2-3 variants to compare. | Validate visual design in 5 minutes, not 2 hours. |
| [architecture-diagram](https://clawhub.ai/voltagent/arch-diagram) | Dark-mode SVG architecture diagrams as HTML. | Technical documentation that looks great in docs. |
| [svg-builder](https://clawhub.ai/voltagent/svg-builder) | Programmatic SVG generation from the agent. | Vector graphics without external tools. |
| [react-component-gen](https://clawhub.ai/voltagent/react-component) | Generates React components with tests and stories. | For teams using React who want consistency. |
| [api-mock-server](https://clawhub.ai/voltagent/api-mock) | Spins up a mock server from an OpenAPI spec. | Frontend without waiting for the backend. |
| [agent-dashboard](https://clawskills.sh/skills/tahseen137-agent-dashboard) | Real-time dashboard for OpenClaw. | Visual monitoring of agent operations. |

### DevOps & Cloud

| Skill | What it does | Why use it |
|-------|----------|----------------|
| [docker-manager](https://clawhub.ai/voltagent/docker) | Manages containers, images, volumes, networks. | Docker operations from the agent without writing commands. |
| [kubernetes](https://clawhub.ai/voltagent/kubernetes) | Manages pods, deployments, services on K8s. | For teams running Kubernetes. |
| [ci-pipeline](https://clawhub.ai/voltagent/ci-pipeline) | Configures and monitors CI/CD pipelines. | Check builds without leaving the agent. |
| [terraform](https://clawhub.ai/voltagent/terraform) | Plans and applies infrastructure as code. | IaC managed by the agent. |
| [agentic-devops](https://clawskills.sh/skills/tkuehnl-agentic-devops) | Complete DevOps toolkit: Docker, processes, logs, health checks. | Production-grade for agents. |
| [server-monitor](https://clawhub.ai/voltagent/server-monitor) | Monitors CPU, RAM, disk, processes on servers. | Alerts and diagnostics from the agent. |
| [nginx-config](https://clawhub.ai/voltagent/nginx) | Configures virtual hosts, SSL, reverse proxy. | Web server management from the agent. |

### Browser & Automation

| Skill | What it does | Why use it |
|-------|----------|----------------|
| [web-scraper](https://clawhub.ai/voltagent/web-scraper) | Scrapes websites with anti-bot and CAPTCHA handling. | Extract structured data from any site. |
| [form-filler](https://clawhub.ai/voltagent/form-filler) | Fills web forms automatically. | Automate repetitive tasks. |
| [browser-test](https://clawhub.ai/voltagent/browser-test) | Runs E2E tests in the browser. | Frontend testing without manual setup. |
| [rss-watcher](https://clawhub.ai/voltagent/rss-watcher) | Monitors RSS/Atom feeds and alerts on changes. | Content tracking without social media. |
| [airtable-automation](https://clawskills.sh/skills/sohamganatra-airtable-automation) | Automates Airtable tasks via MCP (Composio). | CRUD for visual databases from the agent. |
| [activecampaign](https://clawskills.sh/skills/kesslerio-activecampaign) | ActiveCampaign CRM integration. | Lead and campaign management. |
| [calendar-automation](https://clawhub.ai/voltagent/calendar) | Reads and writes calendars (Google Calendar, etc.). | Scheduling and organization from the agent. |

### Productivity & Tasks

| Skill | What it does | Why use it |
|-------|----------|----------------|
| [todo-manager](https://clawhub.ai/voltagent/todo) | Manages task lists with priorities and deadlines. | Personal organization from the agent. |
| [daily-planner](https://clawskills.sh/skills/gpunter-agent-daily-planner) | Structured daily planning and execution tracking. | Start each day with a clear plan. |
| [obsidian-vault](https://clawhub.ai/voltagent/obsidian) | Reads, searches, creates, edits notes in Obsidian. | The agent accesses your personal knowledge base. |
| [notion-manager](https://clawhub.ai/voltagent/notion) | Notion API: pages, databases, markdown, Workers. | Direct Notion integration. |
| [apple-reminders](https://clawskills.sh/skills/nftechie-apple-health-skill) | Creates natural language reminders in Apple Reminders. | Native reminders on macOS/iOS. |
| [pdf-editor](https://clawhub.ai/voltagent/pdf-editor) | Edits text, fixes typos, modifies titles in PDFs. | Quick fixes without heavy tools. |
| [ocr-tool](https://clawhub.ai/voltagent/ocr) | Extracts text from scanned PDFs and images. | Document digitization. |
| [meeting-notes](https://clawhub.ai/voltagent/meeting-notes) | Takes structured notes and generates summaries. | Meetings without missing details. |

### AI & LLMs

| Skill | What it does | Why use it |
|-------|----------|----------------|
| [prompt-engineer](https://clawhub.ai/voltagent/prompt-engineer) | Optimizes prompts for any LLM. | Improves response quality from any model. |
| [model-benchmark](https://clawhub.ai/voltagent/model-benchmark) | Runs benchmarks (MMLU, GSM8K, etc.) on local models. | Objective model performance evaluation. |
| [rag-pipeline](https://clawhub.ai/voltagent/rag) | Builds RAG pipelines with embeddings and vector search. | Augmented context for more accurate responses. |
| [fine-tune-prep](https://clawhub.ai/voltagent/fine-tune) | Prepares datasets for LLM fine-tuning. | Automates training data curation. |
| [obliteratus](https://clawhub.ai/voltagent/obliteratus) | LLM abliteration: remove refusal patterns. | For fine-tuning models without artificial restrictions. |
| [ollama-manager](https://clawhub.ai/voltagent/ollama) | Manages models in Ollama: pull, run, customize. | Run models locally with a single command. |
| [add-top-openrouter-models](https://clawskills.sh/skills/chunhualiao-add-top-openrouter-models) | Syncs OpenRouter models in your config. | Keep your config up to date with the best models. |

### Search & Research

| Skill | What it does | Why use it |
|-------|----------|----------------|
| [academic-search](https://clawhub.ai/voltagent/academic-search) | Searches papers on arXiv, Semantic Scholar, CrossRef. | Direct access to academic literature. |
| [deep-research](https://clawhub.ai/voltagent/deep-research) | Autonomous multi-source research with synthesis. | When you need a complete research assistant. |
| [web-search](https://clawskills.sh/skills/wd041216-bit-openclaw-free-web-search) | Private web search with SearXNG + multi-source validation. | No API keys, no tracking. |
| [arxiv-collector](https://clawskills.sh/skills/xukp20-arxiv-search-collector) | Collects arXiv papers with category filters. | Systematic literature reviews. |
| [analytics-dashboard](https://clawhub.ai/voltagent/analytics) | Queries GA4, Search Console, Stripe and generates reports. | Business intelligence from the agent. |
| [aeo-analytics](https://clawskills.sh/skills/psyduckler-aeo-analytics-free) | Measures visibility in AI assistants (Gemini, ChatGPT, Perplexity). | Know if your brand is cited by AIs. |
| [aeo-content](https://clawskills.sh/skills/psyduckler-aeo-content-free) | Creates content optimized for AI assistant citations. | The sister skill to AEO analytics. |

### Marketing & Sales

| Skill | What it does | Why use it |
|-------|----------|----------------|
| [lead-scraper](https://clawhub.ai/voltagent/lead-scraper) | Extracts leads from LinkedIn, Crunchbase, web directories. | Automated prospecting without expensive tools. |
| [email-campaign](https://clawhub.ai/voltagent/email-campaign) | Builds email marketing sequences with personalization. | Automated outreach with intelligent templates. |
| [seo-audit](https://clawhub.ai/voltagent/seo-audit) | Audits on-page SEO, backlinks, speed, Core Web Vitals. | Complete technical SEO diagnosis. |
| [social-scheduler](https://clawhub.ai/voltagent/social-scheduler) | Schedules posts on social networks. | Multi-channel content management. |
| [ads-manager](https://clawskills.sh/skills/amekala-ads-manager-agent) | Manages campaigns on Google Ads, Meta, LinkedIn. | Paid advertising automation. |
| [abm-outbound](https://clawskills.sh/skills/dru-ca-abm-outbound) | Multi-channel ABM automation from LinkedIn URLs. | Account-based marketing at scale. |

### Communication

| Skill | What it does | Why use it |
|-------|----------|----------------|
| [slack-bot](https://clawhub.ai/voltagent/slack) | Reads and sends Slack messages from the agent. | Team communication without context switching. |
| [discord-bot](https://clawhub.ai/voltagent/discord) | Discord integration: messages, channels, roles. | Community management from the agent. |
| [email-agent](https://clawhub.ai/voltagent/email) | Full IMAP/SMTP client from the agent. | For traditional email accounts. |
| [telegram-bot](https://clawhub.ai/voltagent/telegram) | Sends and receives Telegram messages. | Notifications and commands from the agent. |
| [agentmail](https://clawskills.sh/skills/synesthesia-wav-agentmail-integration) | Gives the agent its own email inbox. | The agent can send and receive emails autonomously. |
| [x-twitter](https://clawskills.sh/skills/kriptoburak-xquik-x-twitter-scraper) | X/Twitter client: post, search, DM, media, v2 API. | Manage Twitter/X from terminal. |

### Notes & PKM

| Skill | What it does | Why use it |
|-------|----------|----------------|
| [obsidian-vault](https://clawhub.ai/voltagent/obsidian) | Full access to your Obsidian vault. | The agent reads/writes your knowledge base. |
| [notion-manager](https://clawhub.ai/voltagent/notion) | Pages, databases, markdown, Workers on Notion. | Direct integration with your second brain. |
| [apple-notes](https://clawskills.sh/skills/swancho-mac-notes-agent) | Apple Notes integration on macOS. | Native Apple notes from the agent. |
| [2nd-brain](https://clawskills.sh/skills/coderaven-2nd-brain) | Personal knowledge base for people, places, tech. | Lightweight PKM without a specific app. |
| [drafts](https://clawskills.sh/skills/nerveband-drafts) | Manages notes in Drafts.app on macOS. | For Drafts + macOS ecosystem users. |

### Image & Video Generation

| Skill | What it does | Why use it |
|-------|----------|----------------|
| [ai-image-gen](https://clawhub.ai/voltagent/image-gen) | Generates images with Stable Diffusion, DALL-E, etc. | Visual creation from the agent. |
| [ai-video-gen](https://clawskills.sh/skills/rhanbourinajd-ai-video-gen) | End-to-end video generation from text. | Complete videos from a description. |
| [ascii-art](https://clawhub.ai/voltagent/ascii-art) | Generates ASCII art: pyfiglet, image-to-ascii. | Banners and terminal decoration. |
| [canva-connect](https://clawskills.sh/skills/coolmanns-canva-connect) | Manages designs, assets, and folders in Canva. | Graphic design from the agent. |
| [music-gen](https://clawskills.sh/skills/fspecii-ace-music) | Generates music with ACE-Step. | Music composition from the agent. |

### PDF & Documents

| Skill | What it does | Why use it |
|-------|----------|----------------|
| [pdf-editor](https://clawhub.ai/voltagent/pdf-editor) | Edits text, fixes typos, modifies titles in PDFs. | Quick fixes without heavy tools. |
| [ocr-tool](https://clawhub.ai/voltagent/ocr) | Extracts text from scanned PDFs and images. | Document digitization. |
| [presentation-maker](https://clawhub.ai/voltagent/presentation) | Creates .pptx presentations with professional design. | Auto-generate slide decks. |
| [document-merger](https://clawhub.ai/voltagent/doc-merger) | Combines multiple documents into one. | Report and documentation unification. |

---

## Essential skills to start

If you're new to OpenClaw, install these 5 first:

```bash
# 1. Plan before coding
openclaw skills install plan

# 2. Don't code without tests
openclaw skills install test-driven-development

# 3. Debug systematically
openclaw skills install systematic-debugging

# 4. GitHub without process errors
openclaw skills install pr-workflow

# 5. Private web search
openclaw skills install web-search
```

With these 5 skills you cover 80% of daily problems: planning, quality coding, debugging, publishing on GitHub, and researching.

### For advanced developers

```bash
# Full productivity stack
openclaw skills install todo-manager daily-planner docker-manager

# AI/ML stack
openclaw skills install ollama-manager prompt-engineer rag-pipeline

# Content stack
openclaw skills install seo-audit social-scheduler aeo-analytics
```

---

## Where to find more skills

OpenClaw has a massive skill ecosystem. Here are the best places to explore:

| Source | Link | Skills |
|--------|--------|--------|
| **ClawHub** (official registry) | [clawhub.ai](https://clawhub.ai) | 5,400+ published skills |
| **Awesome OpenClaw Skills** | [VoltAgent/awesome-openclaw-skills](https://github.com/VoltAgent/awesome-openclaw-skills) | 5,000+ filtered and categorized |
| **ClawSkills.sh** | [clawskills.sh](https://clawskills.sh) | Visual skill browser |

---

## How to create your own skill

OpenClaw skills follow the same format as Hermes Agent skills. Use these guidelines:

1. **Required frontmatter**: `name`, `description`, `category`
2. **Structure**: trigger conditions, numbered steps, verification
3. **Pitfalls**: common mistakes we already know about
4. **Clear instructions**: each step must be executable, not descriptive

Golden rules:
- Minimum 2000 characters of useful content
- Each step must be executable, not descriptive
- Include a verification section (how do I know it worked?)
- Document pitfalls so others don't waste time

To publish your skill on ClawHub:
```bash
# Follow the official publishing guide at
# https://clawhub.ai/docs/publish
```

---

## Contributing

1. Fork the repo
2. Add your recommended skill in the corresponding category table in the README
3. Include the link to ClawHub or the skill's repo
4. Open a PR

**Acceptance criteria:**
- The skill must be published on [ClawHub](https://clawhub.ai) or have a public repo
- It must solve a real problem and be proven
- Clear description of "What it does" and "Why use it"
- Skills in all languages are welcome

---

## License

MIT — do whatever you want with this.

---

_Created by [José Zuma](https://github.com/josezuma) for the global OpenClaw community._
