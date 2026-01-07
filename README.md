# Agentic AI Toolkit (Agno + Groq + pgvector)

A small, practical **agentic AI playground** built in notebooks:
- 🔎 **Research Agent**: DuckDuckGo search + Newspaper4k extraction → structured report
- 📄 **Document Q&A (RAG)**: PDF → chunk → embeddings (SentenceTransformers) → **pgvector** similarity search
- 📈 **Stock Agent**: yfinance tools → market overview + analyst-style summary

> **Note:** This repo is a learning/demo project. It is **not** financial advice.

## Demo notebooks

| Notebook | What it shows |
|---|---|
| `notebooks/00_setup.ipynb` | Environment setup + API keys |
| `notebooks/01_research_agent.ipynb` | Web research agent + report formatting |
| `notebooks/02_document_qa_pgvector.ipynb` | PDF RAG with Postgres + pgvector |
| `notebooks/03_stock_agent.ipynb` | Stock analysis agent using yfinance tools |

## Quickstart (local)

### 1) Create environment & install deps
```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
source .venv/bin/activate

pip install -U pip
pip install -r requirements.txt
```

### 2) Add API keys
Copy `.env.example` → `.env` and fill in your keys:
```bash
cp .env.example .env
```

### 3) Start Postgres + pgvector (for the RAG notebook)
```bash
docker compose up -d
```

### 4) Run notebooks
```bash
jupyter lab
```

## Running in Google Colab
You can use the notebooks in Colab, but **Docker/pgvector won't run** in standard Colab runtimes.  
For the RAG notebook, either:
- run Postgres locally, or
- use a hosted Postgres with pgvector enabled.

## Security
- Never commit `.env`. It's already in `.gitignore`.
- Rotate keys if you accidentally leak them.

## License
MIT (see `LICENSE`)
