# RAG on AWS — Locked Presentation Scope

## 1. Purpose

This document locks the content boundary for the **RAG on AWS** module of the
Cloud Mastery event. It determines what the 20-minute segment must teach, what
it may mention only briefly, and what it must leave to other presenters or
future learning.

The scope is designed for content accuracy first. AWS-specific terminology and
service roles in this document were preliminarily validated through the AI
Agents on AWS plugin and `awsknowledge`. Deeper technical claims, implementation
details, and current capability checks remain subject to Phase 3 verification
before they can appear in the script or slides.

## 2. Agenda Placement

The module belongs to the **Amazon Bedrock Generative AI** block in
`AGENDA.md`.

Relevant agenda context:

1. Foundation Models
2. Guardrails
3. Agents
4. **RAG with Bedrock** — this module
5. Kahoot MiniGame — owned by another team member

The duplicated `Embedding Models` line under RAG is a typing error. The scope
contains one embeddings topic only and does not invent a replacement topic.

The deck is a mergeable section of the team's master presentation, not an
independent event deck.

## 3. Audience Profile

Primary audience: newcomers to cloud and generative AI.

Assume the audience:

- Has no prior working knowledge of RAG.
- Does not yet understand embeddings or vector databases.
- May have heard the earlier event explanation of foundation models and Amazon
  Bedrock.
- Needs intuition and a coherent mental model before AWS service details.
- Benefits more from one consistent scenario than from a catalogue of features.

Content implications:

- Explain plain-language meaning before introducing technical terminology.
- Introduce one new conceptual layer at a time.
- Use minimal slide text and move supporting explanation into the Vietnamese
  talk track.
- Avoid implementation-specific detail that does not improve the core mental
  model.

## 4. Duration and Delivery Constraints

- Total assigned duration: **20 minutes**.
- The final narrative should target approximately 18–19 minutes, preserving a
  1–2 minute safety margin for natural pacing and transitions.
- Kahoot time is not included.
- Slide count is intentionally flexible. Information density, readability, and
  template fit determine the final count.
- Audience-visible slide content is English.
- Full talk track and concise speaker notes are Vietnamese.
- The module starts with a short section divider titled
  **RAG with Amazon Bedrock**.
- The module must end with a concise synthesis and team handoff, not a generic
  thank-you or independent Q&A slide.

## 5. Communication Job

> By the end of the segment, a newcomer should be able to explain why RAG is
> useful, describe its retrieve-then-generate flow, and recognize how Amazon
> Bedrock Knowledge Bases and a vector store support that flow.

## 6. Central Takeaway

> RAG does not retrain the foundation model. It retrieves relevant information
> and supplies that information as context before the model generates an
> answer.

Supporting takeaway:

> Retrieval can make an answer more grounded in selected source data, but it
> does not guarantee that every generated answer is correct.

The exact wording and evidence for the supporting takeaway must be verified in
Phase 3 before audience-facing use.

## 7. Learning Outcomes

After the segment, the audience should be able to:

1. Explain why a foundation model may not know private, organization-specific,
   or newly updated information.
2. Define RAG in plain language as retrieving relevant information before
   generation.
3. Distinguish among source data, retrieved context, and generated response.
4. Describe why documents are split into chunks.
5. Explain embeddings as numerical representations that support semantic
   comparison, without needing to understand embedding mathematics.
6. Explain the role of a vector store in storing and finding relevant embedded
   content.
7. Describe the two high-level RAG stages:
   - preparation/ingestion; and
   - runtime retrieval and generation.
8. Recognize that Amazon Bedrock Knowledge Bases can manage or simplify key
   parts of the RAG workflow.
9. Recognize Amazon OpenSearch Serverless and Amazon Aurora
   PostgreSQL-Compatible Edition as agenda-relevant vector-store choices, not
   mandatory sequential stages.
10. State one important limitation: RAG improves access to selected context but
    does not make the model infallible.

## 8. In-Scope Content

### 8.1 The problem RAG addresses

- A foundation model's pre-trained knowledge does not automatically include an
  organization's private documents.
- Pre-trained knowledge may not contain newly updated information.
- Sending an entire document collection in every prompt is not a useful
  beginner mental model for scalable retrieval.

### 8.2 Core RAG concept

- Retrieval comes before generation.
- Retrieved information augments the model input as context.
- RAG uses external data without presenting it as model retraining or
  fine-tuning.

### 8.3 Preparation/ingestion flow

- Source documents or data sources.
- Text extraction only as a high-level step where needed.
- Chunking into manageable pieces.
- Creating embeddings.
- Writing embeddings to a vector index/vector store while retaining a link to
  the source material.

AWS documentation describes this flow as converting content to text, splitting
it into chunks, converting chunks to embeddings, and storing those embeddings
in a vector database or index. See [How Amazon Bedrock knowledge bases
work](https://docs.aws.amazon.com/bedrock/latest/userguide/kb-how-it-works.html)
and [How content chunking works for knowledge
bases](https://docs.aws.amazon.com/bedrock/latest/userguide/kb-chunking.html).

### 8.4 Runtime flow

- User question.
- Query embedding or semantic representation at a conceptual level.
- Similarity-based retrieval of relevant chunks.
- Adding retrieved information to the model context.
- Foundation-model generation based on the question and retrieved context.
- Source references/citations may be introduced conceptually but require exact
  capability wording from Phase 3 research.

AWS documentation describes runtime retrieval as comparing a query vector with
stored embeddings to find semantically similar content, then using the
retrieved information to augment a foundation-model response. See [How Amazon
Bedrock knowledge bases
work](https://docs.aws.amazon.com/bedrock/latest/userguide/kb-how-it-works.html).

### 8.5 Amazon Bedrock mapping

- Official audience-facing term: **Amazon Bedrock Knowledge Bases**.
- Some AWS documentation and historical material may use **Knowledge Bases for
  Amazon Bedrock**; treat these as references to the same capability unless a
  source explicitly distinguishes a newer knowledge-base type.
- Present the service as simplifying or managing key RAG workflow tasks, not as
  removing the need for sound data and retrieval design.
- Explain the AWS mapping only after the generic RAG mental model is clear.

### 8.6 Vector-store choices relevant to the agenda

- **Amazon OpenSearch Serverless** may serve as the vector-store backend for an
  Amazon Bedrock knowledge base.
- **Amazon Aurora PostgreSQL-Compatible Edition** may serve as a vector-store
  backend for an Amazon Bedrock knowledge base.
- These services are alternatives or architecture choices in this teaching
  scope. The presentation must not imply that both are required in one RAG
  pipeline.
- Do not turn the presentation into a product comparison. Selection guidance,
  prerequisites, cost, and operational trade-offs are deferred.

Preliminary evidence: [Knowledge bases for Amazon Bedrock — vector
databases](https://docs.aws.amazon.com/prescriptive-guidance/latest/retrieval-augmented-generation-options/rag-fully-managed-bedrock.html),
[Prerequisites for using a vector store you created for a knowledge
base](https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base-setup.html),
and [Using Aurora PostgreSQL as a Knowledge Base for Amazon
Bedrock](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/AuroraPostgreSQL.VectorDB.html).

### 8.7 Benefits and limitations

Benefits may include:

- Access to selected private or domain-specific data.
- Access to updated source material after ingestion/synchronization.
- More relevant context for generation.
- A clearer connection between a response and retrieved source content.

Limitations that must remain visible:

- Retrieval quality depends on the data, chunking, embeddings, index, query,
  and retrieval configuration.
- Retrieved context can be incomplete or irrelevant.
- The foundation model still generates the final response.
- RAG does not guarantee factual correctness and must not be presented as
  eliminating hallucinations.

Exact benefit and limitation phrasing must be sourced and reviewed in Phase 3.

## 9. Out-of-Scope Content

Do not include the following in the 20-minute module unless the user explicitly
changes the scope:

- AWS Console or live demo.
- Step-by-step creation of a knowledge base.
- SDK, API, CLI, SQL, or application code.
- Infrastructure as Code.
- Production architecture design in operational detail.
- Detailed IAM, VPC, encryption, compliance, security, or data-governance
  guidance.
- Pricing, cost estimation, performance benchmarks, or sizing.
- Detailed comparison of vector-store products.
- Advanced chunking strategy configuration.
- Hybrid search, reranking, query decomposition, metadata filtering, or
  agentic RAG beyond an optional one-sentence acknowledgement.
- RAG evaluation frameworks or benchmark design.
- Fine-tuning or model customization workflows.
- Multimodal RAG.
- Bedrock Agents implementation details.
- Kahoot questions, answers, timing, or facilitation.
- Event-level opening, presenter introduction, contact, Q&A, or thank-you
  slides.

## 10. Teaching Use Case

### Cloud Mastery Knowledge Assistant

An attendee asks a question about the Cloud Mastery agenda, workshop content,
or event documents. The foundation model does not automatically possess this
private or newly updated event information. The system retrieves relevant
passages from the Cloud Mastery document collection and supplies them as context
before the foundation model generates an answer.

The scenario supports this teaching sequence:

```text
Cloud Mastery documents
        ↓
Split into chunks
        ↓
Create embeddings
        ↓
Store them in a vector store
        ↓
Attendee asks a question
        ↓
Retrieve relevant chunks
        ↓
Add retrieved context
        ↓
Foundation model generates an answer
```

The scenario is explanatory only. It must not become a demo, implementation
tutorial, or fictional customer-success story.

## 11. Narrative Boundaries

The narrative must answer these questions in order:

1. What information problem remains after choosing a capable foundation model?
2. What does RAG add to the request-response process?
3. How is source content prepared for retrieval?
4. How does a user question retrieve relevant context?
5. How does Amazon Bedrock map onto this generic flow?
6. Where does the vector store fit, and what do the two agenda-listed AWS
   options represent?
7. What should a newcomer remember—and what should they not overclaim?

The narrative must not become a list of AWS products. Generic concepts come
first; AWS service mapping comes second.

## 12. Transition In

The preceding team content introduces other Amazon Bedrock capabilities. The
RAG module should enter with this logical bridge:

> A capable foundation model is only part of the solution. What happens when
> the answer depends on our own documents or information that changed after the
> model was trained?

This transition motivates RAG without repeating the earlier Foundation Models,
Guardrails, or Agents sections.

## 13. Transition Out

The module should close by resolving the opening question:

> RAG gives the model relevant external context at request time: retrieve first,
> then generate.

The final handoff should be brief and neutral so the team can transition into
the separately owned Kahoot or next master-deck section. Do not create Kahoot
content inside this module.

## 14. Terminology Boundaries

| Term | Beginner-safe meaning in this module | Do not imply |
|---|---|---|
| RAG | Retrieve relevant information, add it as context, then generate an answer | The model is retrained |
| Chunk | A manageable piece of source content used for retrieval | Every chunking strategy is equivalent |
| Embedding | A numerical representation used to compare semantic similarity | It is a human-readable summary |
| Vector store | A system/index that stores embeddings and supports similarity retrieval | It generates the final answer |
| Retrieval | Finding source content relevant to the question | Retrieval guarantees relevance |
| Augmentation | Supplying retrieved information as model context | Context permanently changes the model |
| Generation | The foundation model produces the final natural-language response | The response is a verbatim database result |
| Amazon Bedrock Knowledge Bases | An AWS capability that simplifies/manages important RAG workflow steps | It removes all data, retrieval, and quality design decisions |
| Amazon OpenSearch Serverless | One agenda-relevant vector-store option | It must be used together with Aurora |
| Amazon Aurora PostgreSQL-Compatible Edition | One agenda-relevant vector-store option | Any Aurora engine or configuration is automatically suitable |

## 15. Source Requirements

- AI Agents on AWS and `awsknowledge` are mandatory for AWS research.
- Prefer official AWS user guides and service documentation.
- Record every audience-facing AWS claim and its source in
  `RAG-on-AWS/KNOWLEDGE.md` during Phase 3.
- Treat this document's AWS links as preliminary scope evidence, not a complete
  knowledge base.
- Recheck current supported capabilities before writing final slide copy.
- Clearly label teaching analogies and do not present them as AWS architecture
  guarantees.
- If an AWS claim cannot be verified, omit it or record an explicit deferral;
  do not fill the gap from memory.

## 16. Acceptance Criteria

Phase 2 is complete only when:

- The module's agenda placement is explicit.
- The 20-minute duration and safety margin are explicit.
- The newcomer audience and learning outcomes are explicit.
- The duplicated `Embedding Models` line is handled as a typo.
- Required and excluded content are unambiguous.
- Kahoot, demo, code, and advanced implementation work are excluded.
- The Cloud Mastery Knowledge Assistant is locked as the supporting use case.
- The transition into and out of the team module is defined.
- Amazon OpenSearch Serverless and Amazon Aurora PostgreSQL-Compatible Edition
  are represented as agenda-relevant vector-store choices rather than mandatory
  sequential components.
- AWS terminology and service boundaries have preliminary official evidence.
- Any claims requiring deeper validation are explicitly deferred to Phase 3.
- `OPERATION.md` records the artifact, validation result, roadmap status, and
  exact next action.
