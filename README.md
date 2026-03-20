 Kubeflow Docs-Agent
Autonomous Agentic RAG Orchestrator for Cloud-Native ML
An advanced, full-stack Agentic RAG system designed to solve knowledge fragmentation in the Kubeflow ecosystem.
This project acts as a specialized reasoning engine, bridging the gap between static documentation and real-time ML infrastructure.

🏗️ Architectural Core
⚡ Asynchronous Orchestration

Built with Python 3.11 + FastAPI + WebSockets to enable:

Non-blocking request handling

Real-time bidirectional communication

Streaming LLM tokens with live system telemetry

🧠 Stateful Reasoning Graph

Powered by LangGraph, enabling:

Multi-hop reasoning

Intelligent decision-making between:

📦 Milvus vector search

🔄 Live Git-based retrieval for latest updates

🔍 Vector Space Management

Semantic search over Kubeflow components:

Pipelines

Katib

KServe

Built using:

LangChain

all-MiniLM-L6-v2 embeddings

🧪 Advanced Engineering Features
📊 Real-Time Telemetry Dashboard

Custom React (TypeScript) dashboard featuring:

Live p50 latency tracking

Token usage visualization

RAG confidence scoring

🔗 Dynamic Pipeline Visualization

SVG-based Reasoning Graph

Provides transparency into:

Agent decisions

Tool usage

Execution flow

🧾 Context-Aware Synthesis

Generates production-ready code:

Python

YAML

Features:

Syntax highlighting via Prism.js

Verified source citations

🛠️ Tech Stack
Layer	Technologies
Frontend	React 18, TypeScript, Tailwind CSS, Chart.js, Prism.js
Backend	Python 3.11, FastAPI, WebSockets, Uvicorn
AI Layer	LangChain, LangGraph, Ollama (Llama 3.2)
Vector DB	Milvus (Standalone / Cluster)
Infra	Docker, Kubernetes (K3s / Minikube)
🚀 Getting Started
1️⃣ Prerequisites

Python 3.11+

Node.js 18+

Docker (for Milvus)

2️⃣ Backend Setup
cd server
python -m venv .venv311

# Activate environment
# Windows:
.venv311\Scripts\activate

# Linux/Mac:
source .venv311/bin/activate

pip install -r requirements.txt
python app.py
3️⃣ Frontend Setup
cd client
npm install
npm run dev
🎯 GSoC 2026 Objectives

This repository serves as the core development sandbox for a Google Summer of Code 2026 proposal.

🧩 Roadmap

Phase I
Optimize Milvus schema for hierarchical documentation indexing

Phase II
Implement Re-Ranker pipeline for improved retrieval precision

Phase III
Integrate:

Kubeflow-native authentication

Multi-user isolation

📄 License

Distributed under the Apache 2.0 License.
See LICENSE for more information.

👨‍💻 Author

Shivam Singh Rawat

📌 Status: In Development (GSoC 2026 Proposal Phase)
