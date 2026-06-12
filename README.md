# RAG Reliability Lab

A RAG reliability lab that compares retrieval strategies, diagnoses failed queries, and measures citation faithfulness.

This project is not a generic knowledge-base chatbot. It is a practical lab for understanding whether a RAG system is finding the right evidence, citing it correctly, and improving after each retrieval change.

## Why this project exists

Many RAG systems generate plausible answers without proving that the answer is grounded in the retrieved evidence. In production, that is not enough.

A reliable RAG system must answer three questions:

1. Did retrieval find the right evidence?
2. Does the answer cite the evidence that supports it?
3. Did the new retrieval strategy improve quality or introduce regressions?

## Core workflow

```text
Upload documents
  ↓
Parse and clean text
  ↓
Chunk with metadata
  ↓
Build BM25 + vector indexes
  ↓
Ask a question
  ↓
Compare vector, BM25, hybrid, and reranked results
  ↓
Generate answer with citations
  ↓
Evaluate recall, faithfulness, latency, and cost
  ↓
Save hard cases for regression tests
```

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
