# Hi, I'm Manikanta 👋

### GCP Data Engineer · AI Builder · Open Source Enthusiast

I build data pipelines, cloud infrastructure, and personal AI tools.  
Currently working with **GCP · BigQuery · Airflow . Python · SQL . Streamlit · Groq API · Supabase**.

---

## 🤖 Personal AI Agent — Featured Project

> A fully-featured personal AI assistant accessible from **any device via browser**.  
> Built completely with free tools. Zero hosting cost.

### 🔗 [Live Demo →](https://your-username.hf.space) &nbsp;|&nbsp; [Source Code →](https://github.com/your-username/your-repo)

---

### 💡 What It Does

| Feature | How It Works |
|---|---|
| 💬 Multi-session chat | Create & switch between multiple conversations |
| 🔐 Secure login | Signup/login with bcrypt-hashed passwords |
| 🧠 4 LLM models | Switch between Llama, Mixtral, Gemma via Groq API |
| 🔍 Auto web search | Detects keywords → fetches live DuckDuckGo results |
| 📄 File Q&A | Upload PDF/TXT/CSV → ask questions on it |
| 💾 Persistent memory | All chats saved in Supabase — never lost on refresh |
| 🗜️ Memory compression | Auto-summarises long chats to stay within token limits |
| ⬇️ Export chat | Download any conversation as `.txt` |

---

### 🏗️ How It Works — Architecture

```
Your Browser (any device)
        │
        ▼
┌─────────────────────────┐
│   Hugging Face Spaces   │  ← Free hosting, always online
│   (Streamlit Web App)   │
└────────────┬────────────┘
             │
      ┌──────┴──────┐
      │             │
      ▼             ▼
┌──────────┐  ┌──────────────┐
│ Groq API │  │   Supabase   │
│  (LLM)   │  │  (Postgres)  │
│          │  │              │
│ • Llama  │  │ • users      │
│ • Mixtral│  │ • memory     │
│ • Gemma  │  │              │
└──────────┘  └──────────────┘
```

**Request flow:**
1. User types a message in the browser
2. Streamlit checks if web search is needed (keyword detection)
3. If yes → fetches DuckDuckGo results → appends to prompt
4. If file uploaded → injects file content into prompt
5. Sends enriched prompt + chat history to Groq API
6. Streams response back with typing animation
7. Saves both messages to Supabase for persistence

---

### 🧩 Tech Stack

```
Frontend    →  Streamlit         (Python-based UI, works on mobile + desktop)
LLM API     →  Groq              (Fast inference — Llama 3, Mixtral, Gemma)
Database    →  Supabase          (PostgreSQL — stores users + chat memory)
Web Search  →  DuckDuckGo API    (Free, no key needed)
Auth        →  bcrypt            (Password hashing)
Hosting     →  Hugging Face Spaces  (Free, always-on)
```

---

### 📁 Key File — `app.py` Walkthrough

The entire app lives in one file. Here's how it's structured:

```
app.py
│
├── CONFIG & ENV VARS
│   └── Loads SUPABASE_URL, SUPABASE_KEY, GROQ_API_KEY from environment
│
├── AUTH  (signup / login)
│   ├── hash_password()     → bcrypt hash before storing
│   ├── verify_password()   → safe bytes comparison (fixes encoding issues)
│   ├── signup()            → checks duplicate username, saves hashed pw
│   └── login()             → fetches hash from Supabase, verifies
│
├── MEMORY  (chat persistence)
│   ├── load_memory()           → fetch all messages for a session
│   ├── save_memory()           → insert new message into Supabase
│   └── maybe_compress_memory() → summarise if chat > 24 messages
│
├── SESSION MANAGEMENT
│   ├── get_all_sessions()      → list all chat sessions for a user
│   ├── get_session_preview()   → first user message as chat title
│   ├── new_session_id()        → auto-increment session number
│   └── delete_session()        → remove all messages for a session
│
├── WEB SEARCH
│   ├── should_search()   → keyword detection ("news", "latest", "today"…)
│   └── web_search()      → DuckDuckGo fetch, returns formatted results
│
├── FILE EXTRACTION
│   └── extract_file_text()  → handles PDF / TXT / MD / CSV
│
├── GROQ API
│   ├── _call_groq_raw()  → low-level HTTP call to Groq endpoint
│   └── call_groq()       → public wrapper used by the UI
│
├── LOGIN / SIGNUP PAGE   (shown when not authenticated)
│   └── Two-tab UI: Login + Sign Up with validation
│
└── MAIN APP  (shown after login)
    ├── Sidebar   → model picker, chat list, file upload, export, logout
    ├── Header    → current chat title + active model
    ├── Messages  → renders full chat history from Supabase
    └── Input     → chat_input → enriches prompt → calls Groq → saves → reruns
```

---

### ⚙️ Supabase Tables

```sql
-- Stores user accounts
create table users (
  id         serial primary key,
  username   text unique not null,
  password   text not null,          -- bcrypt hashed, never plain text
  created_at timestamp default now()
);

-- Stores all chat messages
create table memory (
  id         serial primary key,
  username   text not null,
  session_id text not null,
  role       text not null,          -- 'user' or 'assistant'
  content    text not null,
  created_at timestamp default now()
);
```

---

### 🚀 Run It Yourself

```bash
# 1. Clone
git clone https://github.com/manisai901/data_python.git
cd your-repo

# 2. Install
pip install -r requirements.txt

# 3. Set env vars — create .env file
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_KEY=your-anon-key
GROQ_API_KEY=your-groq-key

# 4. Run
streamlit run app.py
``` 

Or deploy free on [Hugging Face Spaces](https://huggingface.co/spaces) — just add the 3 env vars as secrets.

---

## 🛠️ Tech I Work With

![GCP](https://img.shields.io/badge/Google_Cloud-4285F4?style=flat&logo=google-cloud&logoColor=white)
![BigQuery](https://img.shields.io/badge/BigQuery-4285F4?style=flat&logo=google-bigquery&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-F05032?style=flat&logo=git&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat&logo=supabase&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=flat&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)

---

## 📊 GitHub Stats

![Manikanta's GitHub stats](https://github.com/manisai901/data_python/blob/main/data/app.py)

---

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=your-username&color=blue&style=flat" alt="Profile views" />
</p>
