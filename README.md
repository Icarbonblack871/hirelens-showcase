<div align="center">

# HireLens

**AI-powered resume intelligence platform**

Analyze, score, rewrite, and land interviews — faster.

[![Live App](https://img.shields.io/badge/Live%20App-www.hirelens.online-E8A020?style=for-the-badge)](https://www.hirelens.online)
[![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)](LICENSE)
[![Built with React](https://img.shields.io/badge/Frontend-React%2019-61DAFB?style=for-the-badge&logo=react)](https://react.dev)
[![Built with FastAPI](https://img.shields.io/badge/Backend-FastAPI-009688?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com)

</div>

---

## What is HireLens?

HireLens gives every job seeker access to professional-grade resume analysis — **completely free to start**.

Upload a resume (PDF or TXT), set your target role and job description, and get instant AI-powered feedback across 7 critical dimensions. Get numeric scores, detailed breakdowns, keyword gap analysis, ATS compatibility checks, and a fully rewritten resume — all in one place.

> **75% of resumes are filtered out by ATS before reaching a human recruiter.**
> HireLens helps you make sure yours isn't one of them.

**Try it live:** [www.hirelens.online](https://www.hirelens.online)

---

## Features

### Resume Analysis
- **7-dimension AI scoring** — Clarity, Impact, Measurable Outcomes, Role Alignment, Structure, Skills, ATS Compatibility
- **Job description matching** — keyword overlap, gap analysis, required vs. preferred tier breakdown
- **ATS simulation** — see what automated screeners extract from your resume
- **Per-section breakdown** — feedback on each section of your resume individually
- **Interactive charts** — visual radar and bar charts for score breakdown
- **PDF report download** — shareable analysis report in PDF format

### Resume Improvement
- **AI rewrite** — bullet-by-bullet suggestions with reasoning
- **Multiple formatting modes** — ATS Standard, Executive, Modern, Preserve Original
- **Tailor to job** — generate a version targeted to a specific job description
- **Download as PDF or DOCX**

### Career Tools
- **Cover Letter Generator** — tailored letters aligned to your resume and target role
- **Smart Job Search** — live listings from Jobicy, JSearch, and Adzuna ranked by resume relevance
- **Interview Prep** — STAR-format questions generated from your resume and target role
- **Offer Tracker** — manage applications from first contact to accepted offer

### Analytics & History
- **Analysis history** — every past analysis saved and searchable
- **Historical trend tracking** — score evolution across resume versions with interactive charts
- **HR Dashboard** — candidate pipeline, scoring analytics, and team-level insights (Professional tier)

---

## Scoring System

HireLens evaluates resumes across **7 dimensions**, each scored 1–10:

| Dimension | What It Measures |
|---|---|
| **Clarity** | Clear, jargon-free communication of experience |
| **Impact** | Whether contributions sound meaningful and valuable |
| **Measurable Outcomes** | Use of numbers, percentages, and quantified achievements |
| **Role Alignment** | How well experience matches the target role / JD |
| **Structure** | Layout, section order, readability, formatting |
| **Skills** | Keyword prominence, relevance, presentation |
| **ATS Compatibility** | Parseability by automated screening systems |

**Score interpretation:**
- **8–10** — Excellent, ready to submit
- **5–7** — Good but improvable, address flagged areas
- **<5** — Needs significant work

---

## Pricing

| Plan | Price | Best For |
|---|---|---|
| **Free** | ₹0 forever | Try HireLens — 5 analyses/month |
| **Student** | ₹29/month | Job seekers — 20 analyses + improvements + cover letters |
| **Professional** | ₹99/month | Power users + HR teams — unlimited everything |

All plans include AI analysis. Paid plans unlock Resume Improvement, Cover Letter, Interview Prep, Smart Job Search, Offer Tracker, PDF Reports, and HR Dashboard.

---

## AI Providers

HireLens supports **5 leading AI providers** with a bring-your-own-key architecture. All API keys are user-provided and never stored by HireLens.

| Provider | Models | Notes |
|---|---|---|
| **Groq** (default) | LLaMA 3.3 70B, Mixtral 8x7B | Fastest, generous free tier — start here |
| **Google Gemini** | Gemini 2.0 Flash, Gemini 1.5 Flash | Free tier, strong quality |
| **OpenAI** | GPT-4o, GPT-4o-mini, GPT-4 Turbo | Premium quality |
| **Anthropic** | Claude Sonnet 4.6, Opus 4.6, Haiku 4.5 | Best reasoning, nuanced feedback |
| **Mistral** | Mistral Large, Mistral Small, Nemo | Cost-effective alternative |

---

## Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | React 19 + TypeScript + Vite |
| **Styling** | Tailwind CSS v4 |
| **Animations** | Framer Motion |
| **Routing** | React Router v7 |
| **Auth** | Supabase Auth |
| **Database** | PostgreSQL (Supabase) |
| **Backend** | FastAPI (Python) |
| **PDF Extraction** | PyMuPDF + pdfplumber + PyPDF2 (triple fallback) |
| **PDF Generation** | ReportLab |
| **DOCX Generation** | python-docx |
| **Charts** | Plotly |
| **Payments** | Razorpay |
| **Deployment** | Render |

---

## Architecture

HireLens uses a **provider-agnostic AI adapter pattern** on a React + FastAPI stack:

```
┌─────────────────────────────────┐
│     React Frontend (Vite)       │
│  Analyze · Improve · Jobs       │
│  Interview · Offers · History   │
└────────────────┬────────────────┘
                 │ REST API (JSON)
                 ▼
┌─────────────────────────────────┐
│       FastAPI Backend           │
│  /api/analyze  /api/improve     │
│  /api/cover-letter  /api/jobs   │
│  /api/interview  /api/history   │
└────────────────┬────────────────┘
                 │
        ┌────────┴────────┐
        │                 │
        ▼                 ▼
┌──────────────┐  ┌──────────────────┐
│  AI Provider │  │   PostgreSQL      │
│  Adapter     │  │   (Supabase)      │
│              │  │                  │
│ Groq         │  │ Users · Analyses  │
│ OpenAI       │  │ History · Tiers   │
│ Anthropic    │  └──────────────────┘
│ Gemini       │
│ Mistral      │
└──────────────┘
```

**Key design decisions:**
- Provider-agnostic adapter layer — switch AI providers without touching business logic
- Triple-fallback PDF extraction (PyMuPDF → pdfplumber → PyPDF2) handles designed, image-heavy, and scanned PDFs
- Resume validation heuristic rejects non-resume uploads before consuming API tokens
- All API keys stored in sessionStorage only — never persisted to server

---

## Security

- API keys stored in **sessionStorage** (cleared on tab close, never sent to our servers)
- Resumes processed **in-memory only** — not persisted unless you opt into history
- Auth via **Supabase** (JWT, row-level security)
- Payments via **Razorpay** (PCI-compliant, card data never touches our servers)

---

## Source Code

The source code is **private** to protect proprietary prompt engineering, scoring logic, and system design.

However:
- **Recruiters & hiring managers** — access granted on request for technical review
- **Technical interviews** — full codebase walkthrough available before interviews
- **Architecture questions** — happy to discuss design decisions and trade-offs

Reach out: [hirelenshelp@gmail.com](mailto:hirelenshelp@gmail.com)

---

## About

Built by **[Sahil Shinde](https://github.com/theshindesahil)** — Full-stack developer building tools for job seekers.

- Live app: [https://www.hirelens.online](https://www.hirelens.online)
- Showcase repo: [github.com/theshindesahil/hirelens-showcase](https://github.com/theshindesahil/hirelens-showcase)
- Bugs / feature requests: [open an issue](https://github.com/theshindesahil/hirelens-showcase/issues)
- Contact: [hirelenshelp@gmail.com](mailto:hirelenshelp@gmail.com)

---

<div align="center">

© 2026 Sahil Shinde (https://github.com/theshindesahil). All rights reserved.
Source code is proprietary and confidential. See [LICENSE](LICENSE) for details.

</div>
