# New Slides — RAG on AWS (Continued)

---

## Slide 10 — Vector Dimensions

**Title:** Vector Dimensions  
**Subtitle:** More dimensions ≠ always better

**Layout:** 3 columns

| Low-dim (256) | Medium-dim (512) | High-dim (1024+) |
|---|---|---|
| Fast, low memory footprint | Balance between speed & quality | Captures the most semantic nuance |
| Suitable for simple search, FAQ bots | Most enterprise use cases | Complex technical docs, multilingual |
| Less distinction for subtle context | Recommended starting point | Higher storage cost & latency |

**Key insight (bottom of slide):**
> Dimensions = number of coordinates describing meaning. Choosing the right dimension is a trade-off between accuracy and operational cost.

**Small visual example (corner):**
- "The cat sat on the table" → [0.12, -0.45, 0.88, ... ×256]
- "The cat sat on the table" → [0.12, -0.45, 0.88, ... ×1024] — retains more nuance

---

## Slide 11 — Search Methods

**Title:** Lexical → Vector → Hybrid → Reranking  
**Subtitle:** The evolution of Information Retrieval

**Layout:** 4 columns (progressive flow)

| Lexical Search | Vector Search | Hybrid Search | Reranking |
|---|---|---|---|
| Exact keyword matching (BM25, TF-IDF) | Semantic similarity (cosine distance) | Combines both: keyword match + semantic understanding | Re-orders results by true relevance |
| ✅ Precise for proper nouns, product codes | ✅ Understands paraphrases & synonyms | ✅ Catches both cases | ✅ Removes noise, pushes best results to the top |
| ❌ Cannot understand synonyms | ❌ May miss exact keyword matches | Score = α×Vector + β×Keyword | Uses cross-encoder or specialized rerank model |

**Bottom summary:**
> Production RAG should use Hybrid Search + Reranking for the highest precision.

---

## Slide 12 — AWS Services for RAG: The Big Picture

**Title:** RAG on AWS — Service Map  
**Subtitle:** From data source to response, every step has a dedicated service

**Layout:** 3-column grid

| INGEST | RETRIEVE | GENERATE |
|---|---|---|
| Amazon S3 (store source documents) | Amazon OpenSearch Serverless (vector search) | Amazon Bedrock (Foundation Models) |
| Amazon Bedrock Knowledge Bases (orchestrate pipeline) | Amazon Aurora PostgreSQL + pgvector | Amazon Bedrock Agents (orchestration) |
| AWS Glue / Lambda (custom ETL) | Amazon Kendra (enterprise search) | Amazon Bedrock Guardrails (safety) |

**Speaker note:** This slide introduces the full landscape — each phase of RAG (Ingest → Retrieve → Generate) is covered by specialized AWS services. The central hub connecting everything is **Amazon Bedrock Knowledge Bases**.

---

## Slide 13 — Amazon Bedrock Knowledge Bases (Fully Managed RAG)

**Title:** Amazon Bedrock Knowledge Bases  
**Subtitle:** Fully managed RAG — from ingestion to retrieval in a single service

**Layout:** 2 sections — left is a vertical flow diagram, right is a feature list

**Left section (vertical flow):**
```
Data Sources → Parsing → Chunking → Embedding → Vector Store → Retrieval → Response
```

**Right section (bullet points):**
- Managed pipeline: no infrastructure to maintain
- 9+ data source connectors (S3, Confluence, SharePoint, Salesforce, Web Crawler, OneDrive, Google Drive…)
- Automatic sync when source data changes
- Built-in hybrid search (semantic + keyword)
- Integrated reranking model to boost relevance
- Multimodal support (text, image, audio, video)
- Chunking strategies: Fixed-size, Hierarchical, Semantic
- Native APIs: Retrieve, RetrieveAndGenerate, Agentic Retrieval

---

## Slide 14 — Data Sources & Connectors

**Title:** Connect Your Data  
**Subtitle:** Bedrock Knowledge Bases supports enterprise data sources out of the box

**Layout:** Icon grid (3×3)

| | | |
|---|---|---|
| **Amazon S3** — Documents, PDFs, CSV, HTML | **Confluence** — Internal wiki & documentation | **Microsoft SharePoint** — Enterprise documents |
| **Salesforce** — CRM knowledge articles | **Web Crawler** — Crawl content from any website | **Microsoft OneDrive** — Personal/team file storage |
| **Google Drive** — Google Workspace documents | **Custom (Lambda)** — Any source via Lambda transformation | **Amazon Redshift / Lakehouse** — Structured data |

**Speaker note:** You don't need to write your own crawlers. Configure a connector, and Bedrock will automatically crawl, parse, chunk, and index your content.

---

## Slide 15 — Vector Store Options

**Title:** Vector Store Options  
**Subtitle:** Where your embeddings live and get queried

**Layout:** Table — 6 rows

| Vector Store | When to Use | Key Characteristics |
|---|---|---|
| **Managed Vector Store** (Bedrock-managed) | Simplest option, zero configuration | Built-in, no infra to manage |
| **Amazon OpenSearch Serverless** | Need hybrid search (keyword + semantic) | Scalable, metadata filtering, most popular choice |
| **Amazon Aurora PostgreSQL (pgvector)** | Already using Aurora, want to consolidate | SQL-friendly, familiar for developers |
| **Amazon Neptune Analytics** | Need GraphRAG — complex entity relationships | Knowledge graph + vector search combined |
| **Amazon S3 Vectors** (new) | Large-scale vector storage at low cost | Cost-optimized for massive datasets |
| **Third-party (Pinecone, Redis Enterprise)** | Already invested in external vector DB | Integrate via custom configuration |

**Speaker note:** For most new projects, start with Managed Vector Store or OpenSearch Serverless. Move to specialized stores as requirements grow.

---
