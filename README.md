🌌 Kubeflow Docs-Agent Autonomous Agentic RAG Orchestrator for Cloud-Native ML

An advanced, full-stack Agentic RAG system designed to solve knowledge fragmentation in the Kubeflow ecosystem, bridging static documentation with real-time ML infrastructure.

📑 Table of Contents

Overview

Architecture

Prerequisites

Installation

a. Milvus Installation

b. KServe Inference Pipelines

c. API Server

d. Frontend

Usage

Configuration

Troubleshooting

GSoC 2026 Objectives

License

📌 Overview

Kubeflow Docs-Agent is a stateful reasoning system that:

Performs multi-hop retrieval

Integrates vector search + live code fetching

Generates context-aware responses with code snippets

It eliminates the friction of navigating fragmented Kubeflow documentation.

🏗️ Architecture 🔷 High-Level Architecture High Level Architecture 🔶 Client-Side Architecture Client Architecture ⚙️ Core Components 🧠 Stateful Reasoning Graph

Built using LangGraph

Enables:

Multi-step reasoning

Tool orchestration

Context tracking

🔍 Retrieval Layer

Milvus Vector DB

Semantic embedding search

🔄 Live Retrieval

Git-based dynamic fetching for latest SDK updates

⚡ Async Backend

FastAPI + WebSockets for:

Streaming tokens

Real-time telemetry

📦 Prerequisites

Python 3.11+

Node.js 18+

Docker

Kubernetes (K3s / Minikube)

Ollama

🚀 Installation a. Milvus Installation docker run -d
--name milvus-standalone
-p 19530:19530
-p 9091:9091
milvusdb/milvus:v2.3.0 b. KServe Inference Pipelines kubectl apply -f https://github.com/kserve/kserve/releases/latest/download/kserve.yaml

kubectl apply -f kserve/inference.yaml c. API Server cd server python -m venv .venv311

Windows
.venv311\Scripts\activate

Linux/Mac
source .venv311/bin/activate

pip install -r requirements.txt python app.py d. Frontend cd client npm install npm run dev ▶️ Usage

Start backend

Start frontend

Open: http://localhost:5173

Example Queries

Kubeflow Pipelines DAG execution

KServe YAML configs

Katib tuning examples

⚙️ Configuration OLLAMA_MODEL=llama3.2 MILVUS_HOST=localhost MILVUS_PORT=19530 API_PORT=8000 🛠️ Troubleshooting CUDA Error set OLLAMA_NO_GPU=1 Milvus Issues

Check container running

Verify port 19530

WebSocket Errors

Check backend running

Verify ports & CORS

🎯 GSoC 2026 Objectives

Phase I: Hierarchical indexing

Phase II: Re-ranking pipeline

Phase III: Auth + multi-user support

📄 License

Apache 2.0 License

👨‍💻 Author

Shivam Singh Rawat 📌 In Development (GSoC 2026 Proposal Phase)
