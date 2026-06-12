# Roadmap

## Phase 1: Dataset and ingestion

- Prepare sample enterprise-style documents.
- Build upload and parsing pipeline.
- Implement chunking with metadata.
- Add chunk preview UI or JSON endpoint.

## Phase 2: Retrieval strategies

- Implement vector search.
- Implement BM25 keyword retrieval.
- Implement hybrid retrieval.
- Add rerank comparison.

## Phase 3: Evidence and citation

- Build evidence panel.
- Generate answers with citations.
- Validate whether citations support the answer.

## Phase 4: Evaluation

- Create 30-50 eval cases.
- Track Recall@5, MRR, citation accuracy, faithfulness, latency, and cost.
- Save failed queries into a hard-case board.

## Phase 5: Interview package

- Add screenshots, demo workflow, and eval report.
- Write interview notes for retrieval failure modes and production trade-offs.
