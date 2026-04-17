# Hi, I'm Manikanta 👋

I'm a GCP Data Engineer who builds data pipelines and ships working AI tools that anyone can use right away.

Most of my work is hands-on: real code, clear architecture, and production-ready setups for data engineering workflows, cloud infrastructure, and personal AI agents.

I enjoy turning complex ideas into simple, deployable apps — whether it's a BigQuery pipeline at work or a personal AI assistant running free on the cloud.

---

## What I work on

- **Data Engineering** — GCP, BigQuery, Airflow, Dataflow, Cloud Storage, ETL pipelines, Python, SQL
- **AI Agents** — Personal assistants with memory, web search, and file understanding
- **Python tooling** — Automation scripts, Streamlit apps, REST APIs
- **Cloud infra** — GCP services, IAM, service accounts, deployment pipelines
- **Free-tier deployments** — Hugging Face Spaces, Supabase, Groq API — zero cost

---

## Featured Project — Personal AI Agent 🤖

I built a fully-featured personal AI assistant that runs as a web app, accessible from any device.

**What it does:**
- Secure login with encrypted passwords stored in Supabase
- Multiple chat sessions with full persistent memory
- Automatically searches the web when you ask about current events
- Upload a PDF, CSV, or text file and ask questions on it
- Switch between 4 LLM models (Llama, Mixtral, Gemma) on the fly
- Export or delete any conversation
- Deployed free on Hugging Face Spaces — always online

**Stack:** Streamlit · Groq API · Supabase · DuckDuckGo Search · bcrypt · Python

🔗 [Live Demo](https://your-username.hf.space) &nbsp;·&nbsp; [Source Code](https://github.com/manisai901/your-repo-name)

---

## How the AI Agent works

```
Browser (any device)
       │
       ▼
Hugging Face Spaces  ←  free hosting, always online
(Streamlit app)
       │
       ├──────────────────────┐
       ▼                      ▼
  Groq API               Supabase
  (LLM response)         (users + memory)
       │
  DuckDuckGo
  (web search, auto-triggered)
```

1. You type a message → app checks if web search is needed
2. If yes → fetches live results and injects into the prompt
3. If a file is uploaded → file content is injected into the prompt
4. Enriched prompt + chat history sent to Groq API
5. Response streams back with typing animation
6. Both messages saved to Supabase for persistence across sessions

---

## About Me

- 💼 GCP Data Engineer with experience at **Boeing** and **British Telecom**
- 🛠️ I build things that are free to run and easy to deploy
- 🌱 Currently exploring AI agents, LLM tooling, and personal productivity apps
- 📍 Based in Bangalore, India
- 🧘 Outside work: yoga, meditation, and personal finance

---

## Tech I use daily

![GCP](https://img.shields.io/badge/Google_Cloud-4285F4?style=flat&logo=google-cloud&logoColor=white)
![BigQuery](https://img.shields.io/badge/BigQuery-4285F4?style=flat&logo=google-bigquery&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-3776AB?style=flat&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat&logo=supabase&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=flat&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)

---

## Connect with me


[![Email](https://img.shields.io/badge/Gmail-D14836?style=flat&logo=gmail&logoColor=white)](mailto:manikantasaivootla@gmail.com)

---

![Profile views](https://komarev.com/ghpvc/?username=manisai901&color=blue&style=flat)
