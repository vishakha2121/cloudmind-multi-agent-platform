# ☁️ CloudMind — Multi-Agent Cloud Infrastructure Management Platform

> **An autonomous AI agent system that monitors, optimizes, secures, and scales cloud infrastructure — 24/7, without human intervention.**

![Status](https://img.shields.io/badge/status-active-brightgreen)
![Python](https://img.shields.io/badge/python-3.11+-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-0.110+-009688)
![React](https://img.shields.io/badge/React-18+-61DAFB)
![Gemini](https://img.shields.io/badge/AI-Google%20Gemini-orange)
![License](https://img.shields.io/badge/license-MIT-green)

---

## 🧠 What is CloudMind?

**CloudMind** is a **multi-agent AI orchestration platform** designed to autonomously manage cloud infrastructure. Instead of one monolithic AI, CloudMind uses **six specialized autonomous agents** that collaborate, share context, and make intelligent decisions — powered by **Google Gemini API**.

Each agent owns a domain, continuously observes its environment, reasons with LLMs, and takes action — just like an SRE team, but autonomous and 24/7.

---

## 🤖 The Six Autonomous Agents

| Agent | Icon | Responsibility | Example Decision |
|-------|------|----------------|------------------|
| **Monitoring Agent** | 📊 | Watches CPU, RAM, Disk, Network in real-time | "EC2-i-0042 CPU > 90% for 5 mins → trigger alert" |
| **Cost Optimizer Agent** | 💰 | Detects idle/wasteful resources | "RDS instance idle 7 days → suggest shutdown, save $142/mo" |
| **Security Agent** | 🛡️ | Detects threats, misconfigs, anomalies | "SSH port 22 open to 0.0.0.0 → critical risk, auto-block" |
| **Deployment Agent** | 🚀 | Handles CI/CD, rollout, rollback | "New v2.3.1 deployed → canary 10% → promote after health check" |
| **Recovery Agent** | 🔧 | Detects failures, self-heals services | "Pod crashed 3x → restart + isolate, escalate if 5x" |
| **Capacity Planner Agent** | 📈 | Predicts future load, plans scaling | "Traffic trending +40%/week → pre-scale 3 nodes by Friday" |

All six agents run **concurrently**, communicate via an **orchestrator**, and log every decision for auditability.

---

## 🎯 Why This Project?

Modern cloud environments are complex — too complex for manual management. Human SREs are expensive, slow, and burn out. **CloudMind demonstrates that agentic AI can:**

- ✅ Reduce cloud costs by **20-40%** (Cost Optimizer)
- ✅ Detect threats in **seconds**, not hours (Security)
- ✅ Auto-recover from **80% of common failures** (Recovery)
- ✅ Predict capacity needs **before** outages happen (Capacity Planner)
- ✅ Deploy safely with **zero-downtime** rollouts (Deployment)
- ✅ Provide **24/7 observability** without humans (Monitoring)

---

## 🏗️ Architecture Overview




---

## 🛠️ Tech Stack

### Backend
- **Python 3.11+** — Core language
- **FastAPI** — Async REST API framework
- **SQLAlchemy 2.0** — ORM
- **SQLite** — Practice database (PostgreSQL-ready)
- **Google Gemini API** — LLM reasoning for agents
- **WebSockets** — Real-time updates
- **APScheduler** — Agent scheduling loops
- **Pydantic v2** — Data validation

### Frontend
- **React 18** — UI library
- **Vite** — Fast build tool
- **Tailwind CSS** — Styling
- **Recharts** — Charts & graphs
- **React Router v6** — Routing
- **Zustand / Redux Toolkit** — State management
- **Axios** — HTTP client
- **Framer Motion** — Animations
- **Lucide React** — Icons

### DevOps
- **Docker + Docker Compose** — Containerization
- **Uvicorn** — ASGI server
- **Git + GitHub** — Version control

---

## ✨ Key Features

### 🎨 Frontend
- **Dark-themed dashboard** with glassmorphism cards
- **Live metrics** streamed via WebSocket
- **Agent control panel** — start/stop/pause each agent
- **AI Chat assistant** — ask Gemini anything about your infra
- **Interactive charts** — CPU, cost trends, forecasts
- **Animated status indicators** — see agents thinking live
- **Responsive design** — works on mobile, tablet, desktop
- **Real-time alerts feed** — toast notifications

### ⚙️ Backend
- **Async agent loops** — each agent runs independently
- **Shared context bus** — agents communicate via orchestrator
- **Gemini-powered reasoning** — every decision is LLM-backed
- **Mock cloud simulator** — realistic data without real AWS bills
- **REST + WebSocket API** — dual real-time capability
- **Auto-generated docs** — Swagger UI at `/docs`
- **Structured logging** — every agent action is traceable
- **Seed data script** — instant demo-ready database

---

## 📁 Project Structure



---

## 🚀 Quick Start

### Prerequisites

```bash
Python 3.11+
Node.js 18+
Google Gemini API Key (free at https://aistudio.google.com/apikey)

# Navigate to backend
cd backend

# Create virtual environment
python -m venv venv

# Activate it
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Setup environment
cp .env.example .env
# Now open .env and add your GEMINI_API_KEY

# Seed the database with demo data
python seed_data.py

# Run the server
uvicorn main:app --reload --port 8000


# Navigate to frontend
cd frontend

# Install dependencies
npm install

# Setup environment
cp .env.example .env

# Run dev server
npm run dev