# RAG Reliability Lab

A reliability workbench for RAG systems: inspect chunks, compare retrieval strategies, validate answer sources, and turn weak questions into repeatable checks.

This project is not a generic knowledge-base chatbot. It is a small engineering console for understanding whether a RAG system is finding the right evidence, using it correctly, and improving after each retrieval change.

## Why this project exists

Many RAG demos produce fluent answers without showing enough evidence. In real work, that is not enough. A useful internal knowledge assistant must make the search path visible.

A reliable RAG system should answer:

1. What content was indexed?
2. How was the content split into chunks?
3. Which retrieval method found the relevant evidence?
4. Are answer sources visible and useful?
5. Did a new setting improve or weaken quality?

## Product shape

The product should feel like a compact RAG quality console, not a chat app first.

Core screens:

| Screen | What it shows |
|---|---|
| Documents | Imported files, source type, parsed size, index status |
| Chunk Inspector | Chunk text, source reference, section path, token count |
| Search Comparison | BM25, vector, hybrid, and reranked results side by side |
| Answer With Sources | Final answer next to the chunks that support it |
| Metrics | Recall@5, MRR, citation coverage, latency, and cost estimate |
| Saved Cases | Questions that should be checked again after changes |

## MVP target

Build a local RAG lab that can ingest documents, compare BM25/vector/hybrid retrieval, generate cited answers, and report basic quality metrics.

```text
documents -> chunks -> search comparison -> answer sources -> metrics -> saved cases
```

The first useful demo should let a reviewer understand why an answer was produced in under three minutes.

## Prioritized roadmap

| Priority | Workstream | Outcome |
|---|---|---|
| P0 / MVP | Document ingestion and chunk preview | Retrieval quality can be debugged before embeddings |
| P0 / MVP | Vector and BM25 retrieval | Two strong baselines are visible |
| P0 / MVP | Hybrid retrieval and rerank | The project demonstrates real retrieval tuning |
| P0 / MVP | Showcase path | One demo path from documents to answer sources and metrics |
| P1 | Evidence panel and citation validation | Answers become inspectable and source-linked |
| P1 | Eval dataset and metrics | Quality can be measured after each retrieval change |
| P1 | Saved case board | Weak questions become reusable checks |
| P2 | Interview notes and demo script | The project is easy to explain to hiring teams |

## Repository documents

- [Business Context](docs/business-context.md)
- [Architecture](docs/architecture.md)
- [Data Model](docs/data-model.md)
- [Roadmap](docs/roadmap.md)
- [Showcase Plan](docs/showcase-plan.md)
- [Design Gallery](docs/design-gallery.md)

## Demo narrative

1. Import a small document pack.
2. Inspect chunks before retrieval.
3. Ask a realistic question.
4. Compare search methods.
5. Show the answer and sources.
6. Save the question as a repeatable case.
7. Show a small metrics table.

## What this project demonstrates

- Practical RAG engineering beyond embedding calls.
- Understanding of retrieval failure modes.
- Product judgment around trust and evidence.
- Clear presentation of quality, latency, and cost trade-offs.
- English technical documentation suitable for remote interviews.

## Status

Planning and scaffolding. Issues are used as the implementation roadmap. The next build target is the P0 MVP showcase path.
