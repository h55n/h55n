<h1 align="center">Hi, I'm Hassan Rehman 👋</h1>
<h3 align="center">Builder at the intersection of AI, product, and creative media.</h3>
<p align="center"><i>Most people learn about AI. I build with it.</i></p>

<p align="center">
  <a href="https://linkedin.com/in/hassan-rehman-h55n"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"></a>
  <a href="mailto:hassan0rehman@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white"></a>
  <img src="https://img.shields.io/badge/Location-Pune%2C%20India-blue?style=for-the-badge">
</p>

---

### 🧭 About Me

I design and ship systems where AI is the *architecture*, not a bolt-on feature — retrieval pipelines with real memory constraints, multi-agent systems with hard safety boundaries, and satellite-data ML models that run in production instead of sitting in a notebook. My work spans three fronts:

- 🧠 **GenAI application engineering** — multi-provider LLM abstraction, RAG-style tiered memory, agentic safety design, real-time ASR pipelines
- 🛰️ **Applied ML on real-world sensing data** — satellite/weather data fusion, physics-informed risk modeling, anomaly detection at production SLAs
- ⚙️ **Full-stack + MLOps discipline** — Docker, CI/CD, async pipelines, monitoring, and test coverage that treats ML services like real infrastructure, not demos

I care about **responsible, guard-railed AI** — systems that know what they don't know, escalate to humans when it matters, and never fabricate confidence they haven't earned.

---

### 🚀 Featured Projects

#### 🪨 [SlopeSense](https://github.com/h55n) — Landslide Risk Intelligence Platform
A real-time early-warning system that fuses **6 independent satellite/weather sources** (NASA GPM, NASA SMAP, ESA Copernicus DEM, Sentinel-2, NOAA GFS) into a probabilistic **Failure Probability Index (FPI)**, computed at **1 km² resolution** and refreshed every 6 hours with 24–48 hour forward forecasting.

- Physics-based risk model derived from **NASA LHASA v2**, calibrated with a **LightGBM** classifier and validated against 6 historic landslide events — **6/6 correctly flagged**
- **FastAPI + async SQLAlchemy + PostgreSQL** backend, **Celery**-scheduled satellite ingestion, **Redis** caching, **Next.js 14 + MapLibre GL** live dashboard over WebSockets
- Government-standard **CAP v1.2 XML alert feed** (NDMA Sachet-compatible) and **WhatsApp Business API** dispatch with HMAC-verified webhooks — alert-to-delivery in under 30 seconds
- **100+ pytest cases**, GitHub Actions CI/CD, Dockerized multi-service deployment behind Nginx, Prometheus metrics
- Sub-**120ms p95 API latency**; a full-India model run completes in **~4 minutes**

> Built to close the gap that cost 420 lives in the 2024 Wayanad disaster — a warning existed 16 hours prior but never reached the right channel. SlopeSense wires the model directly into the alert channel.

#### 🌊 [River Watch](https://github.com/h55n) — Satellite Anomaly Detection for Illegal Sand Mining
A dual-signal remote-sensing system that surfaces dated, defensible *anomalies* — never confirmed violations — along 4 monitored river hotspots (Chambal, Yamuna, Ken, Ganga), built for human-in-the-loop review by journalists, NGOs, and lawyers.

- **Sentinel-1 SAR** backscatter log-ratio change detection (`10·log10(incident/baseline)`, +3dB threshold) — works through cloud cover and at night
- **Sentinel-2 NDWI** sandbar-area differencing to estimate physical sand-volume loss, fused into a single anomaly scorer
- Rolling **12-month seasonal baseline** to correct for monsoon vs. dry-season bias
- Evidence-card **PDF/JSON export** pipeline for legal and journalistic use; static JS/HTML dashboard with 30s auto-polling plus a Streamlit interface
- **21 passing unit tests**; guardrails baked into the design — never claim "confirmed illegal," never fabricate numbers, always require human review

#### 🤖 [fumii](https://github.com/h55n) — AI Companion (Hardware + Desktop App)
*IEEE CodeBhoomi 2026 — Top 10 National Finalist, Agentic Autonomous Systems track.*
A palm-sized AI companion built around persistent memory and warmth instead of transactional Q&A.

- **Multi-provider LLM abstraction layer** (Mistral, OpenAI, Anthropic, fully local Ollama) behind a provider-agnostic interface, with secure OS-keychain credential storage (`keytar`)
- **Tiered, RAG-style memory architecture**: Layer 1 always-loaded core identity (~500 tokens) → Layer 2 keyword-retrieved episodic memory (top-3 matches/turn) → Layer 3 a 7-day rolling emotional-state window, assembled into a bounded ~800–1000 token context per request
- **Automated episodic summarization**: an LLM call at the end of every conversation extracts a structured summary, tags, and mood label back into SQLite — a self-updating knowledge base
- **Token-by-token streaming** over IPC from Electron's main process to renderer, driving a 9-state sentiment-aware sprite animation system
- Privacy-by-design: `better-sqlite3` local-only storage, strict `contextIsolation` + `sandbox: true`, no Node integration in the renderer

#### 💬 [DeTalks](https://github.com/h55n) — Multi-Agent Mental Wellness Platform
*IEEE CodeBhoomi 2026 — Top 10 National Finalist.*
A three-tier mental wellness platform (self-guided tools → anonymous peer support → licensed therapy), explicitly engineered against unhealthy parasocial dependency.

- **Dual-agent architecture with strict separation of concerns**: "Disha," a conversational triage agent that runs a 3–5 minute open-ended Pulse Check and routes users across a 5-level severity scale *without diagnosing*, and "Kavach," a silent, real-time safety-monitoring agent watching for self-harm signals
- Kavach generates structured post-session learning briefs for student companions and warm-handoff summaries for licensed psychologists
- A concrete example of designing **safety-critical, role-separated multi-agent systems** rather than a single monolithic chatbot

#### 🎙️ [Mike](https://github.com/h55n) — AI Voice Dictation Tool
A Windows system-tray app for global voice dictation, transcribing speech to text anywhere on the OS.

- **Groq Whisper API** for near-instant ASR (**<500ms**), with an additional LLM polishing pass (Groq LLaMA) across three configurable output modes: Raw / Semi-formal / Polished
- Custom voice-activity detection (RMS threshold filtering) and a symbol-expansion text-normalization layer
- Python state-machine core orchestrating mic capture, global hotkeys, a PyQt6 dashboard, and `pyautogui` keystroke injection — packaged into a single self-contained Windows executable via PyInstaller

#### 📰 [EvrythingAI](https://github.com/h55n) — Automated AI/Tech Newsletter Pipeline
A fully automated, zero-infrastructure daily newsletter delivered to each subscriber's local 6am.

- RSS ingestion → **Mistral AI** multi-document curation/summarization across three categories (news, tools/models, funding) → a higher-order "Signal" step that synthesizes cross-category patterns → HTML email delivery
- Orchestrated by an hourly **GitHub Actions cron** job with timezone-aware logic, **Resend** for transactional email — fully serverless at **$0/month**

#### 🏆 [1ph](https://github.com/h55n) — One Place for Hackathons
A fast, aggregated directory of global and India-specific hackathons.

- **AI enrichment pipeline** (Mistral AI) that extracts structured fields — real deadlines, prize pools, descriptions — from raw hackathon listings: unstructured-to-structured extraction via LLM
- Turborepo monorepo: Next.js 14 frontend with SSG for near-instant loads, Prisma-backed shared DB package, a separate Python enrichment pipeline run via GitHub Actions, deployed on Vercel

---

### 🧰 Tech Stack & Skills

**GenAI / LLM Engineering**
![Mistral](https://img.shields.io/badge/Mistral-FA520F?style=flat-square) ![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white) ![Claude](https://img.shields.io/badge/Claude-D97757?style=flat-square) ![Ollama](https://img.shields.io/badge/Ollama-000000?style=flat-square)
Multi-provider LLM abstraction · RAG / retrieval-augmented architecture · agentic & multi-agent safety design · prompt engineering · context-window management · ASR (Whisper via Groq) · LLM-driven summarization & structured extraction

**Applied ML & Geospatial**
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white) ![LightGBM](https://img.shields.io/badge/LightGBM-018577?style=flat-square) ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
Model calibration · retrospective/backtest validation · anomaly detection · Google Earth Engine · Sentinel-1 SAR / Sentinel-2 optical processing · NDWI & SAR backscatter analysis · NASA GPM/SMAP · Copernicus DEM · physics-informed risk modeling (FPI / LHASA v2)

**Languages & Frameworks**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black) ![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=next.js&logoColor=white) ![Electron](https://img.shields.io/badge/Electron-47848F?style=flat-square&logo=electron&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
SQL (CTEs, window functions, joins) · Streamlit · Tailwind CSS · shadcn/ui

**Infra, Data & MLOps**
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white) ![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
SQLite (`better-sqlite3`) · Celery · Alembic · Nginx · Vercel · Firebase · Prisma · CI/CD pipelines & cron orchestration

**Testing & Analytics**
Pytest (100+ test suites on SlopeSense, 21 on River Watch) · unit/integration testing discipline · Power BI · Matplotlib · Seaborn · A/B testing · funnel & cohort analysis · revenue forecasting

**Creative Tools**
Premiere Pro · After Effects · Photoshop · Canva · ImageFX · Veo 3

---

### 💼 Experience

**Bluestock Fintech** — *Software Development Engineer Intern* (Feb 2026 – Apr 2026)
Full-stack development on a production-ready corporate blog platform — MERN stack, Next.js SSG/ISR, authentication, CMS features, SEO-structured metadata, database design, and CI/CD — in an Agile, remote team environment.

**SalesMonk.ai** — *Operations Management Intern* (May 2025 – Nov 2025)
Built internal dashboards and reporting pipelines; supported process optimization through data analysis.

**Jivika** — *Marketing Intern* (Jun 2025 – Aug 2025)
Analyzed marketing campaign performance and content engagement metrics; produced supporting video content.

---

### 🏅 Certifications & Recognition

- 🏆 **Top 10 National Finalist**, IEEE CodeBhoomi Tech for Good Hackathon 2026 — team "html," project *DeTalks*
- Responsible AI: Applying AI Principles — **Google**
- Data Analyst 101 — **Microsoft**
- Finalist, i-Hack Hackathon (E-Summit '25) — **E-Cell, IIT Bombay**
- Participant, Google Solution Challenge — **Google Developer Groups India**
- Participant, EUREKA 2024 — **IIT Bombay**

---

### 📊 GitHub Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=h55n&show_icons=true&theme=tokyonight&hide_border=true" height="165">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=h55n&theme=tokyonight&hide_border=true" height="165">
</p>

---

### 📫 Let's Connect

<p align="center">
  <a href="https://linkedin.com/in/hassan-rehman-h55n"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"></a>
  <a href="mailto:hassan0rehman@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white"></a>
</p>
