# MultiAgent-AI

**Multi-Agent System for Autonomous Ceph Cluster Management**

This project implements an intelligent, multi-agent orchestration system for monitoring, analyzing, and managing Ceph storage clusters using [CrewAI](https://github.com/joaomdmoura/crewAI). At its core, a centralized `CephOrchestrator` agent coordinates a team of specialized agents to perform real-time cluster health checks, bug triage, documentation lookups, performance monitoring, and automated recommendations.

Key Features:
- 🔍 **Cluster Status Evaluation** via CephViz Agent  
- 📊 **Performance & Disk Analysis** via Observability Agent  
- 🐞 **Bug Monitoring** via BugIntelligence Agent (Bugzilla Integration)  
- 📚 **Ceph Docs Lookup** via Maverick Agent  
- 🧠 **Automated Health Recommendations** via CephPerf Agent  
- 🤖 **Hierarchical Task Planning** using CrewAI-style orchestration  


🧱 Built With:
- Python, [CrewAI](https://github.com/joaomdmoura/crewAI), LangChain Tools
- Ceph CLI + SSH, Metrics via PostgreSQL, Bugzilla API, Ceph Docs Search


## Support matrix
Python - 3.11

## Flowchart
<img width="1452" alt="Screenshot 2025-05-05 at 12 04 28 PM" src="https://github.com/user-attachments/assets/5252c489-80f3-47de-aea5-236fb8e08814" />


## Installation

1. Install `uv` package manager: https://docs.astral.sh/uv/getting-started/installation/

2. Sync dependencies:
```bash
uv sync
```
3. Optional - if you want to use python 3.11.x when you have multiple python versions installed.
    ``` bash
    uv venv -p 3.11
    source .venv/bin/activate
    ```

## Get the documentation

```bash
cd src/
uv run scripts/scrape_ceph_documentation.py
```

## Create FAISS index

```bash
cd src/
uv run agents/maverick/backend/parse_documentation.py
```


## Running the backend

```bash
cd src
uv run orchestration/flow.py
```

# Running the frontend

```bash
cd src
streamlit run frontend/app.py
```
