# Data Model

## Core tables

### documents

| Field | Purpose |
|---|---|
| id | Stable document id |
| title | Display name |
| source_type | markdown, text, pdf, csv |
| source_path | Original path or upload name |
| parsed_text_hash | Detect repeated imports |
| status | imported, parsed, indexed, failed |
| created_at | Import time |

### chunks

| Field | Purpose |
|---|---|
| id | Stable chunk id |
| document_id | Parent document |
| chunk_index | Order inside document |
| text | Chunk content |
| section_path | Heading or section reference |
| token_count | Approximate token count |
| char_start | Start offset |
| char_end | End offset |

### retrieval_runs

| Field | Purpose |
|---|---|
| id | Run id |
| question | User question |
| strategy | bm25, vector, hybrid, rerank |
| top_k | Number of returned chunks |
| latency_ms | Search time |
| created_at | Run time |

### retrieval_results

| Field | Purpose |
|---|---|
| id | Result id |
| run_id | Parent retrieval run |
| chunk_id | Returned chunk |
| rank | Result rank |
| score | Search score |
| source | bm25, vector, hybrid, rerank |

### answer_runs

| Field | Purpose |
|---|---|
| id | Answer run id |
| question | User question |
| answer | Generated answer |
| source_chunk_ids | Chunks used as sources |
| latency_ms | Generation time |
| cost_estimate | Optional cost estimate |

### saved_cases

| Field | Purpose |
|---|---|
| id | Case id |
| question | Repeatable question |
| expected_source | Expected source note |
| label | good, weak, failed |
| note | Human note |

## MVP rule

Keep the model small enough that every record can be inspected from the UI. The goal is not database complexity. The goal is visible retrieval quality.
