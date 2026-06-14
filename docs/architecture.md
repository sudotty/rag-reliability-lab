# Architecture

## Goal

Build a small RAG quality workbench that makes document preparation, retrieval, answer sources, and quality checks visible.

## System boundary

The first version should be local-first and demo-friendly. It does not need accounts, teams, billing, or enterprise permissions.

## Components

| Component | Responsibility |
|---|---|
| Web UI | Documents, chunks, search comparison, answer sources, metrics, saved cases |
| API layer | Document import, chunking, search, answer generation, metrics endpoints |
| Ingestion worker | Parse text, normalize content, split chunks, store metadata |
| Retrieval engine | BM25, vector search, hybrid search, optional rerank |
| Answer service | Generate answer from selected chunks and attach sources |
| Eval runner | Run saved cases and produce simple quality metrics |
| Storage | Documents, chunks, embeddings, questions, runs, metrics |

## MVP flow

```text
Import documents
  -> parse text
  -> create chunks
  -> build search indexes
  -> ask question
  -> compare search results
  -> generate answer with sources
  -> save case
  -> run small metric report
```

## Recommended first stack

- Frontend: React / Next.js / Tailwind
- Backend: FastAPI or Spring Boot
- Search: SQLite FTS or Tantivy-style BM25 first; vector search with pgvector, Qdrant, or local embedding store
- Database: SQLite for demo speed, PostgreSQL when the project grows
- Worker: simple background task first

## Design principle

Do not hide the retrieval path. The product is valuable because it shows the evidence trail before users trust the answer.
