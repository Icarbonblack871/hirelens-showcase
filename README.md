# HireLens

**AI-powered resume intelligence platform** — analyse, score, rewrite, and export your resume using your choice of 5 AI providers.

🔗 **Live Demo:** https://thehirelens.streamlit.app

---

## What It Does

HireLens gives every job seeker access to professional-grade resume analysis — for free.

Upload a resume (PDF/TXT) or paste your LinkedIn profile, and get instant AI feedback across 7 dimensions:

| Category | What It Evaluates |
|---|---|
| Clarity | How clearly your experience is communicated |
| Impact | Whether your contributions sound meaningful |
| Measurable Outcomes | Quantified achievements (numbers, %) |
| Role Alignment | Match with the target job description |
| Structure | Layout, section order, readability |
| Skills | Skill presentation and relevance |
| ATS Compatibility | Whether automated screeners can parse your resume |

---

## Features

- **7-category AI scoring** with an overall composite score (1–10)
- **Job description matching** — keyword gap analysis with Required / Preferred / Nice-to-have tiers
- **ATS simulation** — see what an automated screener extracts from your resume
- **AI resume rewriting** — improved bullet points side-by-side with originals
- **Cover letter generation** — tailored to your resume and target role
- **Integrated job search** — live listings from Jobicy, JSearch, and Adzuna, ranked by relevance to your resume
- **Multi-candidate comparison** — rank and shortlist multiple applicants for the same role
- **8 industry profiles** — General, Software Engineering, Data Science, Marketing, Finance, Product Management, Design, Healthcare
- **Multilingual** — feedback in 8+ languages, auto-detected from the resume
- **Analysis history** — score trend tracking across resume versions
- **Export** — PDF Report, CSV, Excel, Markdown, Notion, Google Docs

---

## Tech Stack

| Layer | Technology |
|---|---|
| UI | Streamlit + custom responsive CSS |
| Charts | Plotly |
| AI / LLM | OpenAI, Anthropic, Google Gemini, Groq, Mistral |
| PDF Parsing | PyMuPDF |
| Database | SQLite |
| Exports | ReportLab, python-docx |
| Deployment | Streamlit Community Cloud |
| Version Control | GitHub |

---

## AI Providers

| Provider | Models | Tier |
|---|---|---|
| Groq *(default)* | LLaMA 3.3 70B, Mixtral 8x7B | Free |
| Google Gemini | Gemini 2.0 Flash, Gemini 1.5 Flash | Free |
| OpenAI | GPT-4o, GPT-4o-mini, GPT-4 Turbo | Paid |
| Anthropic | Claude Sonnet 4.6, Claude Opus 4.6, Claude Haiku 4.5 | Paid |
| Mistral | Mistral Large, Mistral Small, open-mistral-nemo | Paid |

Bring your own API key — no keys are stored server-side.

---

## Screenshots

> *Coming soon — or try the live demo at https://thehirelens.streamlit.app*

---

## Built By

**Sahil Shinde** — [github.com/theshindesahil](https://github.com/theshindesahil)

---

*© 2026 Sahil Shinde. All rights reserved.*
