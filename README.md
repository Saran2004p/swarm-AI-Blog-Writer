# Swarm AI Blog Writer

A production-ready, multi-agent blog generation platform powered by **Pydantic AI structured validation** and **Groq (Llama 3.3 70B)**. Specialized AI agents collaborate through a coordinated workflow to generate research-driven, long-form blog posts and export them as professionally formatted PDF reports.

---

## Features

* **Multi-Agent Workflow**: Planner, Researcher, Writer, and Editor agents collaborate through a Pydantic-validated pipeline.
* **Powered by Llama 3.3 70B**: Utilizes Groq's high-speed inference for reliable reasoning and structured outputs.
* **Long-Form Blog Generation**: Produces detailed, research-backed articles with a structured five-section outline.
* **Modern SaaS Interface**: Built with Vue.js 3, Tailwind CSS, GSAP, and a clean bento-grid inspired design.
* **PDF Export**: Automatically converts Markdown content into polished PDF reports with temporary file cleanup.
* **Serverless Deployment**: Optimized for Vercel with a lightweight Flask backend and Vite frontend.

---

## Tech Stack

| Layer          | Technology                                           |
| -------------- | ---------------------------------------------------- |
| Frontend       | Vue.js 3, Vite 5, Tailwind CSS 3, GSAP 3, TypeScript |
| Icons          | Lucide VueNext                                       |
| Backend        | Flask (Python 3.10+)                                 |
| AI Model       | Groq API – Llama 3.3 70B                             |
| Validation     | Pydantic v2                                          |
| PDF Generation | FPDF2                                                |
| Environment    | python-dotenv                                        |

---

## Getting Started

### Prerequisites

* Python 3.10+
* Node.js 18+
* Groq API Key

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd Swarm-Agent-Orchestrator

# Install frontend dependencies
npm install

# Install backend dependencies
pip install -r requirements.txt
```

### Environment Setup

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key
```

### Run Locally

Start the frontend:

```bash
npm run dev
```

In another terminal, launch the backend:

```bash
python api/index.py
```

Open your browser at:

```
http://localhost:5173
```

### Production Build

```bash
npm run build
```

---

## Project Structure

```text
Swarm-Agent-Orchestrator/
├── api/
│   ├── index.py              # Flask serverless entry point
│   └── core/
│       ├── agents.py         # AI agent definitions
│       ├── models.py         # Pydantic schemas
│       ├── swarm_logic.py    # Multi-agent orchestration
│       └── pdf_generator.py  # PDF generation utility
├── src/
│   ├── components/
│   │   ├── Navbar.vue
│   │   ├── Hero.vue
│   │   ├── Features.vue
│   │   ├── AgentSwarm.vue
│   │   ├── Workspace.vue
│   │   └── Footer.vue
│   ├── App.vue
│   ├── main.ts
│   └── style.css
├── generated_docs/
├── dist/
├── tailwind.config.js
├── vercel.json
├── requirements.txt
└── package.json
```

---

## Multi-Agent Pipeline

```text
User Prompt
    │
    ▼
Planner Agent
    │
    ├── Creates a structured 5-section outline
    ▼
Researcher Agent
    │
    ├── Collects detailed information for each section
    ▼
Writer Agent
    │
    ├── Generates a comprehensive Markdown article
    ▼
Editor Agent
    │
    ├── Refines structure, clarity, and formatting
    ▼
PDF Generator
    │
    └── Exports the final blog as a professional PDF
```

---

## Deployment

The application is configured for **Vercel** using a serverless Flask backend and a Vite-built frontend.

```bash
vercel deploy
```

The `vercel.json` configuration routes all `/api/*` requests to `api/index.py`, while the compiled frontend is served directly from the `dist/` directory.
