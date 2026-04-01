# HireLens

[![Python 3.11+](https://img.shields.io/badge/Python-3.11%2B-blue)](https://www.python.org/downloads/)
[![Streamlit](https://img.shields.io/badge/Built%20with-Streamlit-FF4B4B)](https://streamlit.io)
[![MIT License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Live Demo](https://img.shields.io/badge/Live%20Demo-thehirelens.streamlit.app-FF69B4)](https://thehirelens.streamlit.app)

**AI-powered resume intelligence platform** — analyse, score, rewrite, and export your resume using your choice of 5 AI providers.

Try the live demo: **https://thehirelens.streamlit.app**

---

## Table of Contents

- [What It Does](#what-it-does)
- [How It Works](#how-it-works)
- [Scoring System](#scoring-system)
- [Features](#features)
- [AI Providers](#ai-providers)
- [Industry Profiles](#industry-profiles)
- [Supported Languages](#supported-languages)
- [Export Formats](#export-formats)
- [Resume Themes](#resume-themes)
- [FAQ](#faq)
- [Roadmap](#roadmap)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [License](#license)

---

## What It Does

HireLens gives every job seeker access to professional-grade resume analysis — **completely free**.

Upload a resume (PDF/TXT) or paste your LinkedIn profile, and get instant AI feedback evaluating your resume across 7 critical dimensions. Get a numeric score, detailed category breakdowns, keyword gap analysis against job descriptions, ATS compatibility checks, and AI-powered suggestions for improvement.

**Key insight:** 75% of resumes are filtered out by Applicant Tracking Systems (ATS) before reaching a human. HireLens helps you make yours visible to recruiters.

---

## How It Works

### 1. **Choose Your AI Provider**
   - Pick from 5 LLM providers (or bring your own API key)
   - Start free with **Groq** or **Google Gemini** (no credit card needed)
   - Default: Groq's LLaMA 3.3 70B (fast, accurate, generous free tier)

### 2. **Set Your Context** (optional but recommended)
   - Pick an **industry profile** to weight scoring for your domain
   - Enter your **target job role** for tailored feedback
   - Paste a **job description** to enable keyword matching

### 3. **Upload Your Resume**
   - Single file: PDF or TXT
   - Batch upload: up to 10 resumes at once
   - Or paste your **LinkedIn profile text** directly
   - Live PDF preview before analysis

### 4. **Get Instant AI Analysis**
   - **Scores** across 7 categories (0–10 scale)
   - **Visual charts** (radar, bar, pie)
   - **Detailed feedback** with specific suggestions
   - **JD matching**: see your keyword overlap, gaps, and relevance %
   - **ATS simulation**: view what an automated screener extracts
   - **Per-section breakdown**: analysis by resume section

### 5. **Improve & Export**
   - **AI rewrite**: get bullet-point suggestions with explanations
   - **Cover letter**: auto-generate tailored letters
   - **Find jobs**: discover live listings matched to your resume
   - **Export**: PDF report, CSV, Excel, Markdown, Notion, Google Docs
   - **Track trends**: score evolution across multiple resume versions

---

## Scoring System

HireLens evaluates resumes on **7 dimensions**, each scored 1–10:

| Category | What It Measures | Color Coding |
|---|---|---|
| **Clarity** | How clearly your experience is communicated (jargon? vagueness?) | Green ≥8, Amber 5–7, Red <5 |
| **Impact** | Whether your contributions sound meaningful and valuable | Green ≥8, Amber 5–7, Red <5 |
| **Measurable Outcomes** | Use of numbers, percentages, and quantified achievements | Green ≥8, Amber 5–7, Red <5 |
| **Role Alignment** | How well your experience matches the target role/JD | Green ≥8, Amber 5–7, Red <5 |
| **Structure** | Layout, section order, readability, formatting | Green ≥8, Amber 5–7, Red <5 |
| **Skills** | Skill presentation, keyword prominence, relevance | Green ≥8, Amber 5–7, Red <5 |
| **ATS Compatibility** | Parseability by automated screening systems | Green ≥8, Amber 5–7, Red <5 |

**Overall Score** = weighted average of all 7 categories (adjusted by industry profile)

**Interpretation:**
- **8–10**: Excellent — strong resume, ready to submit
- **5–7**: Good but improvable — address red flags
- **<5**: Needs work — significant gaps or ATS issues

---

## Features

- → **7-category AI scoring** with composite score (1–10)
- → **Job description matching** — Required / Preferred / Nice-to-have keyword tiers with relevance %
- → **ATS simulation** — see extracted text, parsability score, formatting issues
- → **AI resume rewriting** — bullet-point suggestions side-by-side with originals + reasoning
- → **Cover letter generation** — auto-drafted, tailored to role + resume
- → **Integrated job search** — live listings from Jobicy, JSearch, Adzuna, ranked by relevance to your skills
- → **Multi-candidate comparison** — upload 2+ resumes, auto-rank by composite fit, get interview recommendations
- → **8 industry profiles** — scoring weights tailored to your domain (see below)
- → **Multilingual** — feedback auto-detected in 8+ languages, prompts localized
- → **Analysis history** — view all past analyses, score trends across resume versions
- → **Batch upload** — analyse up to 10 resumes in one go
- → **LinkedIn import** — paste full LinkedIn profile text instead of uploading a file
- → **6 export formats** — PDF Report, CSV, Excel, JSON, Markdown, Notion, Google Docs
- → **Responsive design** — optimized for desktop, tablet, mobile

---

## AI Providers

HireLens supports **5 leading AI providers** with bring-your-own-key architecture. **All API keys are user-provided and never stored by HireLens** — you maintain full control.

### Provider Comparison

| Provider | Tier | Models | Latency | Free Quota | Best For | Setup Link |
|---|---|---|---|---|---|---|
| **Groq** [Default] | Free | LLaMA 3.3 70B, Mixtral 8x7B | Very Fast (3–5s) | Unlimited* | → Start here — fastest, most generous | [console.groq.com](https://console.groq.com) |
| **Google Gemini** | Free | Gemini 2.0 Flash, Gemini 1.5 Flash | Fast (4–7s) | 15 req/min | All-rounder, good quality | [aistudio.google.com](https://aistudio.google.com) |
| **OpenAI** | Paid | GPT-4o, GPT-4o-mini, GPT-4 Turbo | Fast (5–9s) | — | Production, premium quality | [platform.openai.com](https://platform.openai.com) |
| **Anthropic** | Paid | Claude Sonnet 4.6, Claude Opus 4.6, Claude Haiku 4.5 | Moderate (6–10s) | — | Deep reasoning, nuance | [console.anthropic.com](https://console.anthropic.com) |
| **Mistral** | Paid | Mistral Large, Mistral Small, open-mistral-nemo | Fast (7–12s) | — | Cost-effective, fast | [console.mistral.ai](https://console.mistral.ai) |

*Groq's free tier has very generous limits (100s of analyses/day for personal use)

### Getting Started

<details>
<summary><strong>Option 1: Free (Recommended for trying HireLens)</strong></summary>

**Groq** is the best free option:
1. Go to [console.groq.com](https://console.groq.com)
2. Sign up with email
3. Copy your API key
4. Paste into HireLens (in the sidebar)
5. Start analyzing — no credit card, no limits

**Alternative:** Google Gemini if you prefer Google's models
</details>

<details>
<summary><strong>Option 2: Paid (For production/frequent use)</strong></summary>

Pick one:
- **OpenAI** — Most popular, excellent quality (costs ~$0.01–0.05 per analysis)
- **Anthropic** — Best reasoning, nuanced feedback (similar pricing)
- **Mistral** — Budget-friendly alternative (slightly cheaper)

Each provider has a free trial credit ($5–20) to test before paying.
</details>

### Why Multiple Providers?

- → **No lock-in** — Switch anytime, no rewrite needed
- → **Redundancy** — If one provider is down, use another
- → **Cost optimization** — Use free tier for development, paid for production
- → **Quality comparison** — Test which provider you prefer

---

## Industry Profiles

Scoring is weighted differently depending on your industry. Choose one to tailor feedback:

| Profile | Focus Areas | Best For |
|---|---|---|
| **General** | Balance across all categories | Default choice |
| **Software Engineering** | Technical skills, metrics (LOC, commits), architecture | SWE, DevOps, QA |
| **Data Science** | Projects, datasets, statistical rigor, model performance | Data scientists, analysts, ML engineers |
| **Marketing** | Campaign results, growth metrics, brand impact | Marketers, growth, product marketers |
| **Finance** | Risk analysis, compliance, financial metrics, ROI | Finance, accounting, investment roles |
| **Product Management** | Cross-functional leadership, roadmap, stakeholder management | PMs, associate PMs, strategy |
| **Design** | Visual communication, user-centric thinking, tools proficiency | Designers, UX/UI, design systems |
| **Healthcare** | Patient outcomes, regulations, certifications, specialization | Doctors, nurses, healthcare admin |

---

## Supported Languages

HireLens automatically detects your resume's language and provides feedback in the same language. Currently supported:

English · Spanish · French · German · Portuguese · Italian · Dutch · + auto-detect

Request additional languages via GitHub Issues.

---

## Export Formats

Analyse once, export anywhere. Download your results in:

| Format | Best For | Includes |
|---|---|---|
| **PDF Report** | Sharing with recruiters, printing | All scores, charts, feedback, professional layout |
| **CSV** | Spreadsheet analysis, tracking trends | Scores, category breakdown, job matches |
| **Excel** | Multiple analyses, pivot tables | Same as CSV, plus formatting |
| **JSON** | Custom processing, integrations | Raw data, all metadata |
| **Markdown** | Documentation, GitHub gists | Human-readable text + tables |
| **Notion** | Personal knowledge base | Direct push to Notion page |
| **Google Docs** | Collaboration with recruiters | Rich formatted document |

---

## Resume Themes

When generating a polished version of your resume, choose a theme:

| Theme | Description | Best For |
|---|---|---|
| **ATS Standard** | Minimal formatting, single column, no colors | Guaranteed ATS parseability |
| **Modern Professional** | Clean design, subtle colors, modern fonts | Tech, startups, creative roles |
| **Executive** | Spacious layout, professional formatting, subtle branding | Leadership, senior roles, C-suite |
| **Preserve Original** | Keep your existing formatting, just enhance content | If you've already got a design you love |

---

## Real-World Example: Before & After

### Before Analysis
```
Senior Software Engineer | 2020 – Present
• Worked on backend systems
• Improved performance
• Led team projects
• Handled deployment
```

**HireLens Score:** 5.2/10
- Clarity: 4 (vague language)
- Impact: 3 (no quantified results)
- Measurable Outcomes: 2 (no metrics)
- Role Alignment: 6 (generic skills)

---

### After AI Rewrite
```
Senior Software Engineer | 2020 – Present
• Architected and deployed microservices serving 2M+ daily requests,
  reducing API latency by 40% (450ms → 270ms)
• Led cross-functional team of 6 engineers through 3 major system migrations,
  achieving 99.99% uptime SLA
• Implemented automated deployment pipeline reducing release time from 2h to 8min,
  enabling 50+ weekly deployments
• Mentored 4 junior engineers to senior roles, conducting 100+ code reviews
```

**HireLens Score:** 8.7/10
- Clarity: 9 (specific, measurable)
- Impact: 9 (quantified business value)
- Measurable Outcomes: 9 (metrics: 40%, 99.99%, 50+)
- Role Alignment: 8 (technical leadership evident)

---

### The Difference
| Metric | Before | After | Improvement |
|---|---|---|---|
| ATS Score | 62 | 89 | +27 points |
| Word count | 38 | 89 | +135% (more substantive) |
| Quantified metrics | 0 | 7 | +700% |
| Action verbs | 2 | 12 | 6× more impactful |

**Why it matters:** The "after" version passes ATS filters, catches recruiter attention in 6 seconds, and clearly demonstrates business impact. Same role, dramatically better presentation.

---

## FAQ

**Q: Do you store my resume?**
A: No. All analysis happens in-memory. Resumes are not saved to any server. Only your analysis scores are optionally saved locally to your database for trend tracking.

**Q: Is HireLens really free?**
A: Yes. The app is free. You bring your own AI provider API key (Groq and Gemini have free tiers). No hidden costs, no premium lock-in.

**Q: Which provider should I start with?**
A: **Groq**. It's included in the app by default, has the most generous free tier, and is fastest (3–5 sec per analysis). No signup delays.

**Q: Can I use my own API key?**
A: Yes, all providers support bring-your-own-key. API keys are never stored by HireLens — only sent to the provider directly.

**Q: How accurate is the AI feedback?**
A: Very accurate for technical feedback (ATS simulation, keyword gaps, structure). For subjective feedback (impact, clarity), treat the AI as a starting point. Best practice: use HireLens to get initial feedback, then refine based on recruiter feedback.

**Q: Can I analyze multiple resumes at once?**
A: Yes, upload up to 10 files in a single batch. Great for comparing versions or analysing a team.

**Q: How do I compare resumes against a specific job?**
A: Paste or upload the job description in the "Job Description" field. HireLens will show keyword matches, gaps, and alignment % for each resume.

**Q: What's the difference between "Improve Resume" and "Cover Letter"?**
A: **Improve Resume** suggests bullet-point rewrites to your existing resume. **Cover Letter** generates a brand-new letter tailored to your resume and the job.

**Q: Is there a mobile app?**
A: Not yet. The web app is fully responsive (works great on mobile). Native apps are on the roadmap.

---

## Roadmap

Planned features for future versions:

- Native mobile app (iOS/Android)
- User accounts & cloud sync (analyses follow you across devices)
- Freemium tier (premium features like batch analysis jobs, priority support)
- Direct ATS integration (apply directly from HireLens)
- Voice resume input (dictate instead of upload)
- Interview prep (AI mock interviews, behavioral Q&A)
- Career analytics (salary benchmarking, role progression insights)

---

## Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| **Frontend** | Streamlit | Interactive web UI |
| **Frontend** | Plotly | Interactive radar, bar, pie charts |
| **Frontend** | Custom CSS | Responsive design, dark theme, animations |
| **Backend** | Python 3.11+ | Core logic, orchestration |
| **PDF Parsing** | PyMuPDF (fitz) | Extract text from PDFs |
| **Data** | SQLite | Local history + trend tracking |
| **Data** | Pydantic | Schema validation |
| **Documents** | ReportLab | PDF report generation |
| **Documents** | python-docx | DOCX export |
| **AI / LLM** | OpenAI SDK | GPT-4o, GPT-4o-mini |
| **AI / LLM** | Anthropic SDK | Claude Sonnet, Opus, Haiku |
| **AI / LLM** | google-genai | Gemini 2.0 Flash, Gemini 1.5 |
| **AI / LLM** | Groq SDK | LLaMA 3.3 70B, Mixtral |
| **AI / LLM** | Mistral SDK | Mistral Large, Small, Nemo |
| **Deployment** | Streamlit Community Cloud | Live hosting |
| **Version Control** | GitHub | Source control, CI/CD |

---

## Architecture

HireLens is built on a **provider-agnostic AI adapter pattern**:

- **Abstraction layer** decouples the app from specific AI providers
- **5 concrete adapters** (OpenAI, Anthropic, Gemini, Groq, Mistral) implement a common interface
- **Easy to add new providers** — just implement the interface
- **Provider-agnostic endpoints** — same analysis flow, different LLM backends

This design ensures:
- → No vendor lock-in
- → Resilience if one provider goes down
- → Freedom to switch providers without code changes
- → Clean, testable codebase

### System Flow

```
┌─────────────┐
│   User      │
│  (Browser)  │
└──────┬──────┘
       │ Resume (PDF/TXT)
       ▼
┌──────────────────────┐
│  Streamlit UI        │
│ (Upload, Settings)   │
└──────┬───────────────┘
       │ Provider selection
       │ + Job description
       ▼
┌──────────────────────┐
│  AI Provider Adapter │  ◄─── Groq, OpenAI, Anthropic, Gemini, Mistral
│ (Abstract Interface) │
└──────┬───────────────┘
       │ Structured prompt
       ▼
┌──────────────────────┐
│  LLM API Call        │
│ (Any provider)       │
└──────┬───────────────┘
       │ JSON response
       ▼
┌──────────────────────┐
│  Score Aggregation   │
│ (7 categories)       │
└──────┬───────────────┘
       │
       ├─► Charts (Plotly)
       ├─► Feedback text
       ├─► Keyword matches
       ├─► ATS simulation
       └─► Exports (PDF, CSV, Docs)
```

**Data persistence:** All analyses stored in SQLite for history & trend tracking

---

## Source Code Access

**The full source code is available for technical interviews and code review.**

The repository is currently private to protect proprietary prompt engineering techniques and system design details. However:

- → Recruiters & hiring managers — I'll grant access upon request
- → Interview preparation — Full codebase available before technical interviews
- → Architecture deep-dive — Walk through design decisions, trade-offs, and implementation

**Why private?** The prompt engineering, scoring logic, and multilingual adaptation techniques are proprietary. The value is in the *how*, not just the *what*.

---

## Contributing

Found a bug or have a feature idea?

- **Found a bug?** Open an issue on the [showcase repo](https://github.com/theshindesahil/hirelens-showcase/issues)
- **Have a feature idea?** [Submit a feature request](https://github.com/theshindesahil/hirelens-showcase/issues)
- **Want to help?** I'm open to partnerships — DM me

---

## License

HireLens is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

---

## About

Built by **[Sahil Shinde](https://github.com/theshindesahil)**.

**Live demo:** https://thehirelens.streamlit.app
**Showcase repo:** https://github.com/theshindesahil/hirelens-showcase

Got questions? Open an issue or reach out on GitHub.

---

<div align="center">

**Built for job seekers everywhere.**

© 2026 Sahil Shinde. All rights reserved.

</div>
