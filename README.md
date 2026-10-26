# 🛡️ FreelanceShield AI — Local Open-Weight Scope Creep Detector & TabPFN-3.5 Invoice Forecaster

> **Official Submission for the [DEV Hacktoberfest Open-Source AI Challenge Week 2: Side Hustle](https://dev.to/challenges/hacktoberfest-week2-2026-10-12)**  
> **Live Interactive Web App:** **[https://robinamirbahar.github.io/freelanceshield-open-ai-side-hustle/](https://robinamirbahar.github.io/freelanceshield-open-ai-side-hustle/)**

![FreelanceShield AI Architecture Banner](assets/freelanceshield_hf26_banner.jpg)

---

## 💡 What Problem Does It Solve? (Why Freelancers Pay $19/mo)

Independent developers, designers, and boutique agencies lose **22% of their annual income** to unbilled **"quick favors" (scope creep)** and **late-paying invoices**.

Yet freelancers **cannot paste confidential client Statements of Work (SOWs), NDAs, or private Slack threads into proprietary cloud LLMs** without violating strict client confidentiality clauses.

**FreelanceShield AI** is a local-first, open-source AI micro-SaaS side hustle that runs **100% on the freelancer's machine (or private self-hosted container)**:

1. **🦙 Local Open-Weight Scope Creep Radar (`Gemma 4 4B` / `Llama 3.2` via Ollama & In-Browser Clause Engine)**: Compares incoming client Slack/email requests against the signed SOW clause-by-clause—flagging out-of-scope deliverables with zero bytes of NDA leakage.
2. **📄 1-Click Polite Counter-Proposal & Change Order PDF Generator**: Automatically calculates billable hours at the freelancer's hourly rate and drafts a warm, high-converting Change Order (#CO-2026-089) with a printable PDF addendum.
3. **📊 Prior Labs `TabPFN-3.5` Zero-Shot Tabular Invoice Risk Forecaster**: Feeds the freelancer's small historical invoice table (5–50 rows—where traditional XGBoost overfits!) into **Prior Labs' `TabPFNClassifier`** to predict the exact probability of a `>14-day payment delay` and recommend whether to require a **50% or 100% upfront milestone deposit**.

---

## 🏗️ System Architecture

```mermaid
flowchart LR
    subgraph ClientInputs["🔒 100% Local NDA-Safe Inputs"]
        SOW["📜 Signed SOW Clauses\n(Markdown / PDF)"]
        MSG["💬 Sneaky Client Email\n('Quick free mobile app?')"]
        CSV["📋 Historical Invoice Ledger\n(Small Tabular CSV)"]
    end

    subgraph OpenSourceAI["🧠 Open-Weight & Foundation Models"]
        LLM["🦙 Local Ollama (gemma4:4b)\n+ Browser Clause-Diff Engine"]
        TAB["📊 Prior Labs TabPFN-3.5\nZero-Shot Tabular Risk Classifier"]
    end

    subgraph SideHustleOutputs["💰 Revenue Recovery Outputs"]
        DIFF["🚨 Clause Violation Breakdown\n(+29 hrs / +$3,625 Caught)"]
        CO["📄 1-Click Change Order PDF\n& Polite Counter-Proposal"]
        RISK["📈 Late-Payment Risk Score\n& Q4 Cashflow Forecast"]
    end

    SOW --> LLM
    MSG --> LLM
    CSV --> TAB
    LLM --> DIFF
    DIFF --> CO
    DIFF --> TAB
    TAB --> RISK
```

---

## 🚀 Quickstart (Run Locally in 60 Seconds)

### Option 1: Instant Browser UI (Zero Install)
Open **[https://robinamirbahar.github.io/freelanceshield-open-ai-side-hustle/](https://robinamirbahar.github.io/freelanceshield-open-ai-side-hustle/)** or open `index.html` directly in any modern browser. If you have **Ollama** running locally on `http://localhost:11434`, switch the top-bar dropdown to **🦙 Local Ollama API**!

### Option 2: Run the Python FastAPI + Ollama (`gemma4:4b`) + `TabPFN` Backend
```bash
git clone https://github.com/RobinaMirbahar/freelanceshield-open-ai-side-hustle.git
cd freelanceshield-open-ai-side-hustle

# 1. Pull open-weight Gemma 4 4B via Ollama
ollama pull gemma4:4b

# 2. Install FastAPI + Prior Labs TabPFN
pip install -r requirements.txt

# 3. Start the local API server
uvicorn agent_backend:app --reload --port 8000
```

---

## 📜 License
MIT License — Built with ❤️ by **Robina Mirbahar** for Hacktoberfest 2026 (`#hf26challenge`).


---

### 🚀 Featured Google Cloud & Agentic AI Portfolio by Robina Mirbahar

| Repository | Architecture & Focus | Live Status |
| :--- | :--- | :--- |
| **[gemma4-multilora-adk-eval](https://github.com/RobinaMirbahar/gemma4-multilora-adk-eval)** | Dynamic Multi-LoRA Hot-Swapping & CI/CD Agent Evaluation (`adk eval`) on Cloud Run GPUs with Gemma 4 & vLLM | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/gemma4-multilora-adk-eval?style=flat-square&color=4285F4) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/gemma4-multilora-adk-eval?style=flat-square) |
| **[slothsre-napops](https://github.com/RobinaMirbahar/slothsre-napops)** | SlothSRE ("NapOps") — Overnight Gemma 4 & Google ADK Incident Digest Agent with OpenTelemetry & Sentry AI Monitoring | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/slothsre-napops?style=flat-square&color=34A853) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/slothsre-napops?style=flat-square) |
| **[streamforge-event-adk](https://github.com/RobinaMirbahar/streamforge-event-adk)** | Real-Time Event-Driven Multi-Agent Pipelines on Google Cloud with ADK (`ParallelAgent` & `LoopAgent`), Eventarc & Pub/Sub | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/streamforge-event-adk?style=flat-square&color=FBBC04) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/streamforge-event-adk?style=flat-square) |
| **[a2a-mcp-mesh-cloudrun](https://github.com/RobinaMirbahar/a2a-mcp-mesh-cloudrun)** | Agent-to-Agent (A2A) & Multi-MCP Mesh on Cloud Run with Gemma 4, Google ADK, Spanner Graph & AlloyDB | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/a2a-mcp-mesh-cloudrun?style=flat-square&color=EA4335) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/a2a-mcp-mesh-cloudrun?style=flat-square) |
| **[cloudguard-gemma-agent](https://github.com/RobinaMirbahar/cloudguard-gemma-agent)** | 6-Part Production Gemma Enterprise Agent Series (ADK, Cloud Run L4 GPU, Firestore, Model Armor, Vertex AI QLoRA) | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/cloudguard-gemma-agent?style=flat-square&color=4285F4) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/cloudguard-gemma-agent?style=flat-square) |
| **[Comic-Studio-Ai](https://github.com/RobinaMirbahar/Comic-Studio-Ai)** | Multi-Agent Comic Generator powered by Google Gemini API & FastAPI deployed on Google Cloud Run | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/Comic-Studio-Ai?style=flat-square&color=EA4335) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/Comic-Studio-Ai?style=flat-square) |
| **[vertex-ai-imagen3](https://github.com/RobinaMirbahar/vertex-ai-imagen3)** | Generate AI-powered product & editorial images using Google Vertex AI Imagen 3 in Google Colab | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/vertex-ai-imagen3?style=flat-square&color=34A853) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/vertex-ai-imagen3?style=flat-square) |
| **[Python-Learning-Assistant](https://github.com/RobinaMirbahar/Python-Learning-Assistant)** | AI-powered Python tutor covering 50+ interactive exercises with real-time feedback built with Streamlit + Gemini API | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/Python-Learning-Assistant?style=flat-square&color=FBBC04) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/Python-Learning-Assistant?style=flat-square) |
| **[cozy-ai-agent-cafe-game](https://github.com/RobinaMirbahar/cozy-ai-agent-cafe-game)** | Prompt Paws: 60 FPS Cozy AI Agent Bakery Simulation Game teaching RAG, Guardrails, Context Caching & Multi-Agent Loops | ![Stars](https://img.shields.io/github/stars/RobinaMirbahar/cozy-ai-agent-cafe-game?style=flat-square&color=7928CA) ![Last Commit](https://img.shields.io/github/last-commit/RobinaMirbahar/cozy-ai-agent-cafe-game?style=flat-square) |

<div align="center">
  <img src="https://raw.githubusercontent.com/RobinaMirbahar/RobinaMirbahar/main/ProfileImages/GithubBanner.svg" alt="Robina Mirbahar Banner" width="100%" />
</div>
