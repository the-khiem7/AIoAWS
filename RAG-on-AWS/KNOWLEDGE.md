# RAG on AWS — Verified Knowledge Base

## 1. Purpose and Authority

This file is the verified content foundation for the Cloud Mastery **RAG with
Amazon Bedrock** presentation module. It converts official AWS documentation
into beginner-safe explanations, claim-level evidence, and wording constraints
for later script and slide authoring.

Authority rules:

- AWS-specific claims come from the AI Agents on AWS plugin and
  `awsknowledge` results.
- Official AWS user guides and prescriptive guidance take priority over blogs.
- Teaching analogies are labeled as analogies, not AWS product guarantees.
- Current model lists, Region availability, pricing, quotas, and implementation
  prerequisites are outside the locked scope and must not be inferred from this
  file.
- `RAG-on-AWS/SCOPE.md` remains the authority for what belongs in the 20-minute
  presentation.

## 2. Executive Knowledge Summary

Retrieval-Augmented Generation (RAG) addresses a gap between what a foundation
model learned during training and the external information an application needs
at request time. AWS describes this gap as including proprietary data,
domain-specific knowledge, and recent changes that may not be represented in the
model's training data. RAG retrieves relevant information from an external
knowledge source, adds that information to the model context, and then asks the
model to generate a response. This gives the model access to selected external
knowledge without retraining it. [S1][S2][S3]

For unstructured data, a common RAG workflow has two high-level phases:

1. **Preparation/ingestion:** convert content to text where necessary, split it
   into manageable chunks, create numerical vector embeddings, and store those
   embeddings in a vector index while retaining links to the original source.
2. **Runtime:** represent the user's query as a vector, compare it with stored
   embeddings, retrieve semantically similar chunks, add those chunks to the
   model context, and generate a response. [S4][S5]

Amazon Bedrock Knowledge Bases can simplify or manage important parts of this
workflow. Depending on the knowledge-base type and configuration, AWS provides
managed capabilities for connectors, parsing, chunking, embeddings, vector
storage, retrieval, prompt augmentation, and generated responses. The
presentation should say that it **simplifies and manages key RAG steps**, not
that every possible RAG design decision disappears. [S4][S6][S7]

Within this event's agenda, Amazon OpenSearch Serverless and Amazon Aurora
PostgreSQL-Compatible Edition are two possible vector-store backends. They are
alternatives in an architecture, not sequential stages that every RAG pipeline
must use together. [S8][S9][S10]

RAG can improve grounding, relevance, transparency, and access to private or
updated data, but it does not guarantee correctness. AWS describes RAG and
citations as reducing or minimizing hallucination risk, and AWS provides
separate evaluation of retrieval relevance and generated-response quality. The
safe teaching conclusion is: **RAG can reduce hallucination risk; it does not
eliminate hallucinations.** [S11][S12][S13]

## 3. Beginner Mental Model

### 3.1 The problem

A foundation model can be capable and still lack the information needed for a
specific question. The required information might be:

- Private to an organization.
- Specific to a domain or event.
- Created or updated after the model's training.
- Stored in documents or systems outside the model.

This is an information-access problem, not automatically a model-quality
problem. [S1][S2][S3]

### 3.2 RAG in one sentence

> RAG retrieves relevant external information, adds it to the model's context,
> and then lets the model generate an answer.

Beginner shorthand:

> **Retrieve first, generate second.**

### 3.3 What RAG changes—and what it does not

RAG changes the input available to the model at request time. It does not
permanently teach the model the retrieved documents and does not require
retraining the model. [S1]

Keep these three objects separate:

| Object | Meaning | Example in the Cloud Mastery scenario |
|---|---|---|
| Source data | Original external information | Agenda and workshop documents |
| Retrieved context | Selected passages relevant to the question | The paragraph describing the RAG session |
| Generated response | Natural-language output created by the foundation model | “The RAG session lasts 20 minutes.” |

The generated response is not the same thing as the retrieved source passage.
The foundation model still performs generation.

## 4. Core Concepts

### 4.1 Source data

Source data is information outside the foundation model's original training
knowledge that the RAG application can search. AWS examples include document
repositories, databases, APIs, internal documents, manuals, and case logs.
[S1][S2][S3]

Beginner-safe explanation:

> The source data is the library that RAG is allowed to search.

Do not say:

> RAG uploads all company knowledge into the model.

### 4.2 Chunk

A chunk is a manageable piece of source content used for retrieval. Amazon
Bedrock documentation describes splitting documents or content into manageable
chunks for efficient retrieval, then maintaining a mapping back to the original
document. [S4][S5]

Why chunking exists:

- A complete document may be too broad for a focused query.
- Smaller pieces let retrieval select the passages most related to the
  question.
- The chunk must still contain enough context to remain meaningful.

Beginner-safe explanation:

> Instead of searching and sending an entire handbook, RAG searches smaller
> passages that can be matched to the question.

Do not imply:

- Smaller chunks are always better.
- One chunk size is correct for every document.
- Chunking quality has no effect on retrieval.

AWS guidance treats chunking strategy as an important part of retrieval quality.
[S5][S12]

### 4.3 Embedding

AWS describes a vector embedding as a series of numbers representing content so
that it can be mathematically or quantitatively compared. Embeddings support
semantic similarity between a query and source content. [S4][S5]

Beginner-safe explanation:

> An embedding turns the meaning of a passage or question into numbers that a
> system can compare.

Teaching analogy—not a literal implementation description:

> Think of an embedding as coordinates on a “map of meaning.” Content with
> related meaning tends to be closer on that map.

Do not say:

- An embedding is a summary humans can read.
- The vector contains the original sentence in encrypted form.
- Similar embeddings guarantee identical meaning.

### 4.4 Vector store / vector index

A vector store holds embeddings and supports retrieval based on vector
similarity. Amazon Bedrock documentation describes writing chunk embeddings to a
vector index and comparing a query vector with stored embeddings to find
semantically similar content. [S4][S5][S8]

Beginner-safe explanation:

> The vector store is the searchable index that helps find chunks whose meaning
> is close to the user's question.

The vector store:

- Stores/indexes embeddings and related metadata.
- Supports similarity retrieval.
- Does not write the final natural-language answer.

### 4.5 Semantic retrieval

Semantic retrieval attempts to find content related by meaning rather than only
matching the exact words. At runtime, AWS describes converting the query to a
vector and comparing it with stored embeddings to find semantically similar
content. [S4]

Beginner example:

- Question: “How long is the RAG session?”
- Relevant source text: “RAG with Bedrock — 20 minutes.”

The words are not identical, but their meanings are related.

Do not say that semantic retrieval always returns the correct passage. AWS
provides RAG retrieval evaluation precisely because relevance and coverage must
be measured. [S13]

### 4.6 Augmentation

Augmentation means adding retrieved information to the model input as context.
It does not permanently modify the model. [S1][S2]

Beginner-safe explanation:

> The system gives the model selected reference material together with the
> user's question.

### 4.7 Generation

Generation is the step in which the foundation model produces the final
natural-language response using the user question, retrieved context, and its
existing learned capabilities. [S1][S6]

Do not describe generation as a direct database lookup. Retrieval returns
source material; the model generates the answer.

## 5. End-to-End RAG Flow

### 5.1 Phase A — Prepare the knowledge source

```text
Source documents
      ↓
Parse or extract text where needed
      ↓
Split content into chunks
      ↓
Create an embedding for each chunk
      ↓
Write embeddings to a vector index
      ↓
Maintain mapping to original source content
```

Evidence: AWS Bedrock documentation explicitly describes text conversion,
chunking, embeddings, vector indexing, and source mapping. [S4][S5]

Important nuance:

- “Updated data” is not magic or automatic in every architecture. The external
  repository and its embeddings must be synchronized or updated according to
  the chosen workflow. [S2][S6]

### 5.2 Phase B — Answer a user question

```text
User question
      ↓
Represent the query for semantic comparison
      ↓
Search the vector index
      ↓
Retrieve relevant source chunks
      ↓
Add chunks to the model context
      ↓
Foundation model generates a response
      ↓
Return response and source references when supported/configured
```

Evidence: Amazon Bedrock documentation describes query embedding, vector
comparison, relevant chunk retrieval, prompt augmentation, generation, and
citations in supported retrieval-and-generation flows. [S4][S6][S7]

### 5.3 The two flows must not be collapsed

Preparation happens before a question can retrieve indexed content. Runtime
retrieval happens when the user asks a question. Mixing the two makes it appear
that documents are re-embedded from scratch on every user query, which is not
the intended beginner mental model.

## 6. Cloud Mastery Knowledge Assistant Walkthrough

### 6.1 Preparation

1. Cloud Mastery agenda and workshop documents are selected as source data.
2. The content is split into manageable chunks.
3. An embedding model converts each chunk into a vector representation.
4. The embeddings are stored in a vector store with references to the original
   documents.

### 6.2 Runtime

1. An attendee asks: “How long is the RAG session?”
2. The system represents the question for semantic comparison.
3. The vector store returns the chunk containing the RAG agenda entry.
4. That chunk is added to the model context.
5. The foundation model generates a concise answer based on the retrieved
   context.
6. A supported Bedrock retrieval-and-generation flow can return source
   attribution to the relevant source chunk. [S7]

### 6.3 What this example teaches

- The agenda remains external data; it is not retrained into the model.
- Retrieval selects context before generation.
- The vector store finds content; it does not generate prose.
- The model can still produce a poor answer if retrieval or generation quality
  is poor.

Do not present this scenario as an implemented or measured Cloud Mastery system.
It is a teaching example only.

## 7. Amazon Bedrock Knowledge Bases

### 7.1 Beginner-safe role

> Amazon Bedrock Knowledge Bases helps implement and manage important parts of
> the RAG workflow, from preparing source content through retrieving context and
> supporting generated responses.

AWS documentation describes capabilities across ingestion, parsing, chunking,
embedding generation, vector storage, retrieval, and prompt augmentation. The
exact degree of management depends on the knowledge-base type and configuration.
[S4][S6]

### 7.2 Why this matters to the audience

Without a managed capability, teams must integrate data ingestion, chunking,
embeddings, vector storage, retrieval, prompt construction, generation, and
source tracing themselves. Bedrock Knowledge Bases can reduce that integration
work and provide a consistent AWS workflow. [S6]

### 7.3 Retrieval and generation remain conceptually separable

Amazon Bedrock documentation distinguishes retrieval of relevant source chunks
from retrieval plus foundation-model generation. This is strong evidence for
teaching RAG as two conceptual actions even when a managed API combines them.
[S7]

Do not put API names or implementation code on the slides; API detail is outside
scope. The distinction is useful only to support the mental model.

### 7.4 Source attribution

AWS documentation states that supported retrieval-and-generation responses can
include citations to specific source chunks. This improves transparency and can
help users inspect where context came from. [S7][S11]

Safe wording:

> Bedrock Knowledge Bases can return source attribution with supported
> retrieval-and-generation flows.

Avoid the broader claim:

> Every custom RAG response always has perfect citations.

## 8. Agenda-Relevant Vector Stores

### 8.1 Shared role

Both Amazon OpenSearch Serverless and Amazon Aurora PostgreSQL-Compatible
Edition can serve as vector-store backends for Amazon Bedrock Knowledge Bases.
The vector store holds/indexes embeddings and supports similarity retrieval.
[S8][S9][S10]

The presentation must show them as choices:

```text
Amazon Bedrock Knowledge Bases
            ↓
     Choose a vector store
        ↙             ↘
OpenSearch        Aurora PostgreSQL
Serverless        Compatible Edition
```

Do not show this incorrect sequence:

```text
OpenSearch Serverless → Aurora PostgreSQL → Foundation Model
```

### 8.2 Amazon OpenSearch Serverless

Relevant beginner-level role:

- Can provide a vector search collection/index for a Bedrock knowledge base.
- Stores vector embeddings in a vector field/index.
- Supports vector similarity retrieval. [S8][S9]

Safe wording:

> OpenSearch Serverless is one AWS-native option for storing and searching the
> vector embeddings used by the knowledge base.

Out of scope:

- Collection configuration.
- Network access.
- Index engine, dimensions, capacity, and pricing.
- Comparison with OpenSearch managed clusters.

### 8.3 Amazon Aurora PostgreSQL-Compatible Edition

Relevant beginner-level role:

- Aurora PostgreSQL can use `pgvector` capabilities to store, index, search,
  and query vector embeddings.
- Aurora PostgreSQL can be configured as the vector store for Amazon Bedrock
  Knowledge Bases. [S10][S14]

Safe wording:

> Aurora PostgreSQL is another AWS option when vector search needs to live in a
> PostgreSQL-compatible database context.

The second sentence is presentation guidance inferred from Aurora's relational
database nature and vector capability; it is not a universal service-selection
rule.

Out of scope:

- `pgvector` installation or SQL.
- Cluster configuration and versions.
- Data API, permissions, Secrets Manager, and networking.
- Performance, scale, cost, and product-selection recommendations.

### 8.4 Selection boundary

The 20-minute presentation should not recommend one option over the other. It
should teach only:

1. A knowledge base needs a retrieval store/index appropriate to its design.
2. OpenSearch Serverless and Aurora PostgreSQL are two agenda-listed AWS
   choices.
3. They occupy the same conceptual slot in the simplified architecture.

## 9. Benefits and Limitations

### 9.1 Supported benefits

| Benefit | Safe explanation | Evidence |
|---|---|---|
| External knowledge | RAG can ground a response in selected proprietary, domain-specific, or recent information | [S1][S3] |
| No retraining requirement | The model can use retrieved context without retraining on that data | [S1][S4] |
| Relevance | Semantic retrieval aims to provide content related to the user query | [S4][S5] |
| Transparency | Supported Bedrock flows can provide source attribution/citations | [S7][S11] |
| Managed workflow | Bedrock Knowledge Bases can simplify ingestion, retrieval, and augmentation work | [S4][S6] |

### 9.2 Required limitations

| Limitation | Why it matters | Evidence type |
|---|---|---|
| Retrieval can be incomplete or irrelevant | AWS provides retrieval evaluation for relevance and coverage | Direct: [S13] |
| Data quality and freshness matter | RAG depends on the external repository and update lifecycle | Direct: [S2][S12] |
| Chunking and embedding choices affect retrieval | AWS guidance treats these as quality-sensitive design decisions | Direct: [S5][S12] |
| The model still generates the answer | Retrieval provides context; generation remains probabilistic | Direct: [S1][S6]; synthesis |
| RAG does not eliminate hallucinations | AWS says reduce/minimize risk, and recommends evaluation/oversight | Safe inference from [S11][S13][S15] |
| Citations improve traceability, not truth by themselves | A citation shows the retrieved source relationship; response quality still requires evaluation | Safe inference from [S7][S13] |

### 9.3 The exact hallucination wording

Allowed:

- “RAG can reduce hallucination risk by grounding responses in external
  sources.”
- “RAG can make answers more grounded and traceable.”
- “Retrieved context improves the information available to the model.”
- “RAG still requires evaluation.”

Not allowed:

- “RAG prevents hallucinations.”
- “RAG eliminates hallucinations.”
- “RAG guarantees accurate answers.”
- “If a citation exists, the answer must be correct.”

## 10. Common Misconceptions to Correct

| Misconception | Correction |
|---|---|
| RAG trains the model on company data | RAG supplies retrieved context at request time; it does not require retraining |
| Embeddings are readable summaries | Embeddings are numerical representations used for comparison |
| The vector store generates the answer | The vector store retrieves related content; the foundation model generates the response |
| RAG sends every document to the model | Retrieval selects relevant chunks rather than treating the whole collection as prompt context |
| More context is always better | Context should be relevant and sufficient; retrieval quality must be evaluated |
| OpenSearch and Aurora are both mandatory | They are alternative vector-store choices in this agenda |
| RAG guarantees current information | The source repository and embeddings must be updated or synchronized |
| Citations guarantee truth | Citations improve traceability; retrieval and generation quality still need evaluation |
| RAG eliminates hallucinations | AWS frames RAG as reducing or minimizing risk, not eliminating it |

## 11. Vocabulary for Slide and Script Authors

| English term | Vietnamese speaking explanation | Usage note |
|---|---|---|
| Retrieval-Augmented Generation | Sinh câu trả lời có bổ sung thông tin được truy xuất | Introduce full term once, then use RAG |
| Retrieve | Truy xuất phần thông tin liên quan | Prefer over “search everything” |
| Generate | Foundation model tạo câu trả lời | Keep distinct from retrieval |
| Source data | Dữ liệu nguồn bên ngoài model | Examples: agenda, event documents |
| Chunk | Một đoạn dữ liệu đủ nhỏ để truy xuất | Avoid deep token discussion |
| Embedding | Biểu diễn ý nghĩa thành dãy số/vector | Use “map of meaning” only as analogy |
| Vector | Dãy số biểu diễn nội dung | No mathematics required |
| Vector store | Nơi lưu và tìm kiếm các vector | Clarify that it does not generate prose |
| Semantic similarity | Mức độ gần nhau về ý nghĩa | Contrast gently with exact keyword matching |
| Context | Thông tin tham chiếu được đưa vào model cho yêu cầu hiện tại | Not permanent model memory |
| Grounding | Gắn câu trả lời với nguồn thông tin được cung cấp | Do not translate as a correctness guarantee |
| Source attribution | Thông tin cho biết nội dung được truy xuất từ nguồn nào | Prefer this over “proof” |
| Amazon Bedrock Knowledge Bases | Khả năng của Amazon Bedrock giúp quản lý các bước quan trọng trong RAG | Preserve official product name on slide |
| Amazon OpenSearch Serverless | Một lựa chọn vector store cho knowledge base | Do not compare pricing/performance |
| Amazon Aurora PostgreSQL-Compatible Edition | Một lựa chọn vector store dựa trên PostgreSQL | Do not generalize to every Aurora configuration |

## 12. Presentation-Safe Claims

The following claims are approved for later script and slide planning, subject
to concise audience-facing wording:

| Claim ID | Approved claim | Evidence |
|---|---|---|
| C01 | Foundation models may lack proprietary, domain-specific, or recently changed information | [S1][S3] |
| C02 | RAG retrieves relevant external information and adds it as context before generation | [S1][S2] |
| C03 | RAG can use external knowledge without retraining the foundation model | [S1][S4] |
| C04 | RAG keeps source data, retrieved context, and generated response conceptually distinct | Synthesis of [S1][S6][S7] |
| C05 | Documents are commonly divided into manageable chunks for retrieval | [S4][S5] |
| C06 | Embeddings are numerical vector representations that support semantic comparison | [S4][S5] |
| C07 | A vector index/store holds embeddings and supports similarity retrieval | [S4][S5][S8] |
| C08 | Runtime retrieval compares a query representation with stored embeddings to find semantically similar content | [S4] |
| C09 | Retrieved chunks are added to model context before the final response is generated | [S1][S4][S6] |
| C10 | Amazon Bedrock Knowledge Bases can simplify or manage key RAG workflow steps | [S4][S6] |
| C11 | Retrieval and generation are conceptually separable even when a managed operation combines them | [S7] |
| C12 | Supported Bedrock retrieval-and-generation flows can return citations/source attribution | [S7][S11] |
| C13 | Amazon OpenSearch Serverless can serve as a vector store for Amazon Bedrock Knowledge Bases | [S8][S9] |
| C14 | Amazon Aurora PostgreSQL-Compatible Edition can serve as a vector store for Amazon Bedrock Knowledge Bases | [S9][S10][S14] |
| C15 | OpenSearch Serverless and Aurora PostgreSQL are alternative choices in the simplified agenda architecture | Synthesis of [S8][S9][S10] |
| C16 | RAG can reduce hallucination risk but does not guarantee correctness | Direct “reduce/minimize” wording plus safe inference from [S11][S13][S15] |
| C17 | Retrieval relevance and generated-response quality should be evaluated separately | [S13] |
| C18 | External data and embeddings must be updated or synchronized to reflect changes | [S2][S6] |

## 13. Claims Requiring Careful Qualification

| Topic | Safe boundary |
|---|---|
| “Fully managed” | Use only when referring to a documented managed knowledge-base configuration; prefer “manages or simplifies key steps” in the beginner deck |
| “Up to date” | Say RAG can use updated external data after the data/index is synchronized; do not imply automatic real-time freshness |
| “Accurate” | Say more grounded, relevant, or context-specific; never guarantee accuracy |
| “Citations” | Tie citations to supported Bedrock retrieval-and-generation flows; do not generalize to every custom RAG workflow |
| “Vector database” | Use interchangeably with vector store only at beginner level; avoid claiming identical product behavior |
| “Semantic search” | Say it retrieves based on meaning/similarity; do not claim perfect understanding |
| “Aurora” | Use the full name Amazon Aurora PostgreSQL-Compatible Edition when discussing the agenda vector-store option |
| “OpenSearch” | Use Amazon OpenSearch Serverless for this agenda; do not silently broaden to every OpenSearch deployment type |
| “Knowledge base” | Prefer Amazon Bedrock Knowledge Bases when referring to the AWS capability; lowercase for the generic concept |

## 14. Source Catalog

### S1 — Grounding and Retrieval Augmented Generation

- URL: https://docs.aws.amazon.com/prescriptive-guidance/latest/agentic-ai-serverless/grounding-and-rag.html
- Authority: AWS Prescriptive Guidance.
- Supports: proprietary/recent-data gap, retrieve/generate definition, external
  context, no retraining.

### S2 — What is RAG?

- URL: https://aws.amazon.com/what-is/retrieval-augmented-generation/
- Authority: AWS service explainer.
- Supports: external data, retrieval, prompt augmentation, query vectors, and
  updating external data/embeddings.

### S3 — RAG options and architectures on AWS

- URL: https://docs.aws.amazon.com/prescriptive-guidance/latest/retrieval-augmented-generation-options/introduction.html
- Authority: AWS Prescriptive Guidance.
- Supports: custom-document problem and referencing authoritative external data
  before generation.

### S4 — How Amazon Bedrock knowledge bases work

- URL: https://docs.aws.amazon.com/bedrock/latest/userguide/kb-how-it-works.html
- Authority: Amazon Bedrock User Guide.
- Supports: preprocessing/runtime phases, chunks, embeddings, vector index,
  semantic similarity, generated responses, and reduced retraining need.

### S5 — How content chunking works for knowledge bases

- URL: https://docs.aws.amazon.com/bedrock/latest/userguide/kb-chunking.html
- Authority: Amazon Bedrock User Guide.
- Supports: manageable chunks, embeddings, vector index, source mapping, and
  quantitative comparison.

### S6 — Knowledge bases for Amazon Bedrock

- URL: https://docs.aws.amazon.com/prescriptive-guidance/latest/retrieval-augmented-generation-options/rag-fully-managed-bedrock.html
- Authority: AWS Prescriptive Guidance.
- Supports: ingestion-to-augmentation workflow, synchronization, retrieval,
  generation, vector-store options, and source traceability.

### S7 — Retrieving information using Amazon Bedrock Knowledge Bases

- URL: https://docs.aws.amazon.com/bedrock/latest/userguide/kb-how-retrieval.html
- Authority: Amazon Bedrock User Guide.
- Supports: retrieval of relevant source chunks, combined retrieval/generation,
  citations, and separation/customization of RAG steps.

### S8 — Prerequisites for a vector store created for a knowledge base

- URL: https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base-setup.html
- Authority: Amazon Bedrock User Guide.
- Supports: OpenSearch Serverless vector search collection/index and vector
  embedding fields.

### S9 — Knowledge bases for Amazon Bedrock — vector databases

- URL: https://docs.aws.amazon.com/prescriptive-guidance/latest/retrieval-augmented-generation-options/rag-fully-managed-bedrock.html
- Authority: AWS Prescriptive Guidance.
- Supports: supported vector-store choices, including OpenSearch Serverless and
  Aurora PostgreSQL-Compatible Edition.

### S10 — Using Aurora PostgreSQL as a Knowledge Base for Amazon Bedrock

- URL: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/AuroraPostgreSQL.VectorDB.html
- Authority: Amazon Aurora User Guide.
- Supports: Aurora PostgreSQL as a Bedrock Knowledge Bases vector backend and
  storage of chunks/vectors.

### S11 — Amazon Bedrock FAQs

- URL: https://aws.amazon.com/bedrock/faqs/
- Authority: Official Amazon Bedrock FAQ.
- Supports: source attribution/citations and AWS's “minimizing risk” wording.

### S12 — Data lifecycle in generative AI

- URL: https://docs.aws.amazon.com/prescriptive-guidance/latest/strategy-data-considerations-gen-ai/lifecycle.html
- Authority: AWS Prescriptive Guidance.
- Supports: data quality/update lifecycle, chunking strategies, embedding-model
  selection, and retrieval-quality dependencies.

### S13 — Evaluate the performance of RAG sources

- URL: https://docs.aws.amazon.com/bedrock/latest/userguide/evaluation-kb.html
- Authority: Amazon Bedrock User Guide.
- Supports: separate retrieve-only and retrieve-and-generate evaluations,
  retrieval relevance, and generated-response effectiveness.

### S14 — Amazon Aurora FAQs

- URL: https://aws.amazon.com/rds/aurora/faqs/
- Authority: Official Amazon Aurora FAQ.
- Supports: pgvector storage, indexing, querying, and semantic similarity search
  for embeddings.

### S15 — Security considerations for data in generative AI

- URL: https://docs.aws.amazon.com/prescriptive-guidance/latest/strategy-data-considerations-gen-ai/security.html
- Authority: AWS Prescriptive Guidance.
- Supports: hallucinations arise from missing grounding data and probabilistic
  model behavior; RAG is one mitigation that can reduce hallucinations.

## 15. Source-to-Claim Coverage Matrix

| Source | Covered claim IDs |
|---|---|
| S1 | C01, C02, C03, C04, C09 |
| S2 | C02, C18 |
| S3 | C01 |
| S4 | C03, C05, C06, C07, C08, C09, C10 |
| S5 | C05, C06, C07 |
| S6 | C04, C09, C10, C18 |
| S7 | C04, C11, C12 |
| S8 | C07, C13, C15 |
| S9 | C13, C14, C15 |
| S10 | C14, C15 |
| S11 | C12, C16 |
| S12 | C05, C06, C18 |
| S13 | C16, C17 |
| S14 | C14 |
| S15 | C16 |

## 16. Phase 3 Deferral Resolution

The deferrals recorded in `SCOPE.md` are resolved as follows:

| Deferred topic | Resolution |
|---|---|
| Exact claim that RAG does not guarantee correctness | Approved as a safe inference because AWS uses reduce/minimize language and separately requires retrieval/generation evaluation; use the wording in Section 9.3 |
| Source attribution wording | Approved only for supported Bedrock retrieval-and-generation flows; use C12 |
| Benefit wording | Approved claims listed in Section 9.1; avoid absolute accuracy claims |
| Limitation wording | Required limitations listed in Section 9.2 |
| OpenSearch Serverless role | Verified as a vector-store/index option; use C13 |
| Aurora PostgreSQL role | Verified as a vector-store option; use C14 |
| Relationship between OpenSearch and Aurora | Verified as alternatives within the simplified agenda architecture; use C15 |
| Updated information | Qualify with synchronization/update requirement; use C18 |

No unresolved technical claim currently blocks narrative design. Phase 4 must
remain within the approved claims and qualification rules in this file.

## 17. Acceptance Criteria

This knowledge base is ready for Gate B review when:

- Every in-scope concept has a beginner-safe explanation.
- Generic RAG concepts are separated from AWS service mappings.
- Presentation-safe claims have stable IDs.
- Every approved AWS claim maps to one or more official sources.
- Direct claims are distinguished from safe synthesis/inference.
- Hallucination, accuracy, freshness, citation, and “fully managed” wording are
  constrained.
- OpenSearch Serverless and Aurora PostgreSQL are represented as alternatives.
- All Phase 3 deferrals from `SCOPE.md` are resolved.
- No implementation, demo, code, pricing, Region, or model-list scope has been
  added.
- `OPERATION.md` records the artifact, validation result, roadmap status, and
  next action.
