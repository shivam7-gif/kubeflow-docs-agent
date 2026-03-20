🌌 Kubeflow Docs-Agent
Autonomous Agentic RAG Orchestrator for Cloud-Native ML

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

🏗️ Architecture
🔷 High-Level Architecture

(Add your diagram here — recommended: draw.io / Excalidraw / Whimsical)

![High Level Architecture](./assets/indexing.svg)
🔶 Client-Side Architecture

(Frontend flow: React → WebSocket → Streaming UI → Charts)

![Client Architecture](./assets/quering.svg)
⚙️ Core Components
🧠 Stateful Reasoning Graph

Built using LangGraph

Enables:

Tool selection

Multi-step reasoning

Context tracking

🔍 Retrieval Layer

Milvus Vector DB
Semantic search via embeddings

🔄 Live Retrieval

Git-based dynamic fetching for latest SDK updates

⚡ Async Backend

FastAPI + WebSockets for:
Streaming tokens
Real-time telemetry

📦 Prerequisites

Python 3.11+

Node.js 18+

Docker (for Milvus)

Kubernetes (K3s / Minikube)

Ollama (for local LLM inference)
OpenAI GPT Models
ANthropic Claude

🚀 Installation
a. Milvus Installation
# Run Milvus standalone using Docker
docker run -d \
  --name milvus-standalone \
  -p 19530:19530 \
  -p 9091:9091 \
  milvusdb/milvus:v2.3.0

Verify:

docker ps
b. KServe Inference Pipelines
# Apply KServe CRDs
kubectl apply -f https://github.com/kserve/kserve/releases/latest/download/kserve.yaml

# Example inference service
kubectl apply -f kserve/inference.yaml
c. API Server
cd server

python -m venv .venv311

# Activate
# Windows
.venv311\Scripts\activate

# Linux/Mac
source .venv311/bin/activate

pip install -r requirements.txt

# Run server
python app.py
d. Frontend
cd client

npm install
npm run dev
▶️ Usage

Start backend server
Start frontend
Open browser at: http://localhost:5173

Example Queries
 1)“Explain Kubeflow Pipelines DAG execution”
 2) “Latest KServe deployment YAML”
 3) “Katib hyperparameter tuning example”

⚙️ Configuration
Environment Variables
# LLM
OLLAMA_MODEL=llama3.2
OPENAI_MODEL=gpt-4o-mini
CLAUDE_MODEL=claude-3-haiku-20240307

# Vector DB
MILVUS_HOST=localhost
MILVUS_PORT=19530

# API
API_PORT=8000
Customization Options

🔧 Embedding model swap

🔧 Milvus collection schema tuning

🔧 LangGraph node modification

🔧 Prompt engineering

🛠️ Troubleshooting
❌ CUDA / Ollama Errors
set OLLAMA_NO_GPU=1
❌ Milvus Not Connecting

Check container is running

Verify port 19530

Restart Docker

❌ WebSocket Issues

Ensure backend is running

Check CORS settings

Verify correct port

❌ Slow Retrieval

Optimize:

Embeddings

Index type (IVF_FLAT / HNSW)

Chunk size

🎯 GSoC 2026 Objectives
🧩 Phase I

Hierarchical indexing in Milvus

🧩 Phase II

Re-ranking layer for precision

🧩 Phase III

Multi-user + Kubeflow auth integration

📄 License

Distributed under the Apache 2.0 License.

👨‍💻 Author

Shivam Singh Rawat
📌 Status: In Development (GSoC 2026 Proposal Phase)

🔥 Next Level Upgrade (optional)

If you want, I can next:

Add badges (build, stars, license, GSoC ready)

Create actual architecture diagrams (top-tier visuals)

Convert this into a winning GSoC proposal doc

Just tell me 👍

yes add badges also

Here’s your final polished README with professional badges added (top-tier GitHub style) 🚀

🌌 Kubeflow Docs-Agent
Autonomous Agentic RAG Orchestrator for Cloud-Native ML
















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

🏗️ Architecture
🔷 High-Level Architecture
![High Level Architecture](./assets/high-level-architecture.png)
🔶 Client-Side Architecture
![Client Architecture](./assets/client-architecture.png)
⚙️ Core Components
🧠 Stateful Reasoning Graph

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

🚀 Installation
a. Milvus Installation
docker run -d \
  --name milvus-standalone \
  -p 19530:19530 \
  -p 9091:9091 \
  milvusdb/milvus:v2.3.0
b. KServe Inference Pipelines
kubectl apply -f https://github.com/kserve/kserve/releases/latest/download/kserve.yaml

kubectl apply -f kserve/inference.yaml
c. API Server
cd server
python -m venv .venv311

# Windows
.venv311\Scripts\activate

# Linux/Mac
source .venv311/bin/activate

pip install -r requirements.txt
python app.py
d. Frontend
cd client
npm install
npm run dev
▶️ Usage

Start backend

Start frontend

Open: http://localhost:5173

Example Queries

Kubeflow Pipelines DAG execution

KServe YAML configs

Katib tuning examples

⚙️ Configuration
OLLAMA_MODEL=llama3.2
MILVUS_HOST=localhost
MILVUS_PORT=19530
API_PORT=8000
🛠️ Troubleshooting
CUDA Error
set OLLAMA_NO_GPU=1
Milvus Issues

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

Shivam Singh Rawat
📌 In Development (GSoC 2026 Proposal Phase)
