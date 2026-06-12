# RAG Reliability Lab

A RAG reliability lab that compares retrieval strategies, diagnoses failed queries, and measures citation faithfulness.

This project is not a generic knowledge-base chatbot. It is a practical lab for understanding whether a RAG system is finding the right evidence, citing it correctly, and improving after each retrieval change.

## Why this project exists

Many RAG systems generate plausible answers without proving that the answer is grounded in the retrieved evidence. In production, that is not enough.

A reliable RAG system must answer three questions:

1. Did retrieval find the right evidence?
2. Does the answer cite the evidence that supports it?
3. Did the new retrieval strategy improve quality or introduce regressions?

## MVP target

Build a local RAG lab that can ingest documents, compare BM25/vector/hybrid retrieval, generate cited answers, and report basic quality metrics.

```text
documents -> chunks -> BM25 + vector -> hybrid retrieval -> cited answer -> eval report -> hard cases
```

## Prioritized roadmap

| Priority | Workstream | Outcome |
|---|---|---|
| P0 / MVP | Document ingestion and chunk preview | Retrieval quality can be debugged before embeddings |
| P0 / MVP | Vector and BM25 retrieval | Two strong baselines are visible |
| P0 / MVP | Hybrid retrieval and rerank | The project demonstrates real retrieval tuning |
| P1 | Evidence panel and citation validation | Answers become inspectable and source-linked |
| P1 | Eval dataset and metrics | Quality can be measured after each retrieval change |
| P1 | Hard-case board | Failures become regression assets |
| P2 | Interview notes and demo | The project is easy to explain to hiring teams |

## Core features

| Feature | Purpose |
|---|---|
| Document ingestion | PDF, Markdown, text, CSV samples |
| Chunk preview | Make chunking visible and debuggable |
| Hybrid retrieval | Combine lexical and semantic search |
| Rerank comparison | Show whether reranking improves top-k quality |
| Evidence panel | Show retrieved chunks and scores |
| Citation validation | Check whether the answer is supported by sources |
| Hard-case board | Keep failed questions as regression assets |
| Eval report | Track recall@k, citation accuracy, faithfulness, latency, and cost |

## Interview value

This project helps answer real interview questions about retrieval failure modes, hybrid search, chunking trade-offs, citation quality, and RAG regression testing.

## Status

Planning and scaffolding. Issues are used as the implementation roadmap.
