# AI SEO Blog Agent

Python FastAPI + LangGraph agent that researches keyword opportunities, plans SEO articles, validates on-page quality, and saves server-rendered blog pages.

React (Vite) streams progress over SSE while Gemini produces structured plans and drafts. Postgres stores pages and run history.

## Stack

- **Backend:** Python 3.11+, FastAPI, LangGraph, Gemini
- **Frontend:** React + Vite
- **DB:** PostgreSQL
- **Runtime:** Docker Compose

## Features

- Keyword research with autocomplete + sitemap-aware shortlist
- Duplicate / cannibalisation checks against existing pages
- Plan → write → validate → optional repair agent loop
- Server-rendered `/blog/<slug>` pages with SEO meta and JSON-LD
- Rate limits to protect free-tier LLM quota

## Quick start

```bash
cp .env.example .env
# set GEMINI_API_KEY and Postgres settings
docker compose up --build
```

- Agent UI: http://localhost:5173
- API / blog: http://localhost:8000

```bash
cd backend && pip install -r requirements-dev.txt && pytest -q
```

## Author

Pooja Sharma — [PyGenix](https://github.com/PyGenix)
