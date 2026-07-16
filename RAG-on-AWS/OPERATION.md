# RAG on AWS — Source of Operation Truth

## 1. Mission

Produce a beginner-friendly, 20-minute **RAG on AWS** presentation module for
the Cloud Mastery event. The module must include verified AWS knowledge, an
English slide-content specification, a Vietnamese presentation script in two
formats, and a PowerPoint deck derived only from duplicated layouts in
`Slide/Template.pptx`.

This file is the canonical execution state and handoff document. A new agent
must read, in order:

1. `AGENTS.md`
2. `RAG-on-AWS/OPERATION.md`
3. `AGENDA.md`
4. The active domain artifact named in **Exact Next Action**

## 2. Current Execution State

| Field | Value |
|---|---|
| Current phase | Phase 6 — Produce and review the English slide-content specification |
| Phase status | `Pending` |
| Current task | Phase 5 completed; Phase 6 is ready to start |
| Last updated | 2026-07-16 21:58 +07:00 |
| Blocking issue | None |
| Exact next action | Start Phase 6 and create `RAG-on-AWS/SLIDE-CONTENT.md` with exact English audience-visible copy for the 11-slide hypothesis, narrative role, visual intent, script mapping, claim/source references, density constraints, and provisional template-layout needs; do not edit the PPTX yet. |

## 3. Confirmed Scope

### Context

- Event: Cloud Mastery.
- Parent session: Amazon Bedrock Generative AI.
- Assigned module: RAG on AWS / RAG with Amazon Bedrock.
- The RAG deck is a partial deck that the team will later merge into a larger
  event presentation.

### Audience and delivery

- Audience: newcomers to cloud and generative AI.
- Assumed prior knowledge: none for RAG, embeddings, vector databases, or
  Amazon Bedrock.
- RAG presentation time: 20 minutes with a small safety margin.
- Slide copy: English.
- Full talk track and speaker notes: Vietnamese.
- Slide count: flexible according to content density and readability.

### Required content

- The problem RAG solves.
- A beginner-friendly definition of RAG.
- Retrieval versus generation.
- Documents, chunks, embeddings, and vector stores at a conceptual level.
- The end-to-end RAG flow.
- Knowledge Bases for Amazon Bedrock.
- The agenda-relevant role of Amazon OpenSearch Serverless and Amazon Aurora
  PostgreSQL-Compatible Edition.
- Benefits, limitations, and realistic expectations.
- A supporting use case: Cloud Mastery Knowledge Assistant.

### Explicit exclusions

- Live or recorded AWS Console demo.
- Step-by-step implementation instructions.
- SDK, API, or application code walkthrough.
- Deep IAM, security, networking, pricing, operations, evaluation, or advanced
  RAG optimization.
- Kahoot creation or facilitation. Kahoot is outside the presenter's
  responsibility and outside the 20-minute RAG scope.
- Event-level opening, presenter biography, contact, generic thank-you, or
  independent Q&A slides.

### Deck boundary

- The first slide is a short section divider titled **RAG with Amazon Bedrock**.
- The deck contains only slides belonging to the RAG module.
- The ending must synthesize the topic and hand off cleanly to the next team
  section.

## 4. Canonical Inputs and Initial Evidence

| Input | Purpose | Verification | Initial Git blob fingerprint |
|---|---|---|---|
| `AGENTS.md` | Durable project rules and gates | Present; 17,638 bytes; checked 2026-07-16 | `d12bf3ecb01812b3e524d2bdc7dcb51e998d558e` |
| `AGENDA.md` | Overall event agenda and RAG placement | Present; 1,058 bytes; RAG subsection confirmed under Amazon Bedrock Generative AI | `43d58f66ee8715c5fadd7df974713204595929be` |
| `Slide/Template.pptx` | Immutable visual and structural source deck | Present; 13,899,151 bytes; no write performed | `53fa4c005acc8eb1c840a818dc6749eb5c6ceeec` |

The template fingerprint above is the baseline immutability reference. Recheck
it before final delivery. Any mismatch must be investigated before proceeding.

## 5. Roadmap

Only one phase may be `In Progress`. A phase is complete only when its artifact
and validation evidence are current.

| # | Phase | Required output/evidence | Status |
|---:|---|---|---|
| 1 | Initialize operation truth and confirm workspace inputs | `OPERATION.md`; input existence and baseline fingerprints | `Completed` |
| 2 | Extract and lock the RAG scope from the agenda | `SCOPE.md`; scope-to-agenda validation | `Completed` |
| 3 | Research and verify RAG knowledge with AWS sources | `KNOWLEDGE.md`; source-to-claim mapping | `Completed` |
| 4 | Design the beginner-focused 20-minute narrative | Narrative and timing plan recorded in domain artifacts | `Completed` |
| 5 | Write and review the Vietnamese script in both formats | `SCRIPT.md`; timing and transition review | `Completed` |
| 6 | Produce and review the English slide-content specification | `SLIDE-CONTENT.md`; copy and source coverage review | `Pending` |
| 7 | Audit the complete template and map every output slide | Template audit; validated output-to-source slide map | `Pending` |
| 8 | Duplicate template slides and author the RAG PowerPoint | `Slide/RAG-on-AWS.pptx`; original template unchanged | `Pending` |
| 9 | Render, inspect, and validate every slide | Per-slide visual QA evidence | `Pending` |
| 10 | Run final content, source, timing, fidelity, and merge QA | Final QA ledger and resolved findings | `Pending` |
| 11 | Complete handoff and mark delivered artifacts | Final artifact registry and team handoff | `Pending` |

## 6. Phase 1 Task-Level Progress

| Task | Evidence | Status |
|---|---|---|
| Confirm `AGENTS.md` exists | File metadata and Git blob fingerprint recorded | `Completed` |
| Confirm `AGENDA.md` exists and contains the RAG subsection | Agenda read directly; RAG placement and duplicate Embedding Models line observed | `Completed` |
| Confirm immutable template exists | File metadata and baseline fingerprint recorded | `Completed` |
| Create canonical operation-truth structure | This file created | `Completed` |
| Validate zero-context handoff completeness | Roadmap, confirmed decisions, canonical inputs, baseline fingerprints, artifact registry, operation log, QA state, and exact next action verified | `Completed` |

## 6A. Phase 2 Task-Level Progress

| Task | Evidence | Status |
|---|---|---|
| Re-read agenda and durable project rules | `AGENDA.md`, `AGENTS.md`, and Phase 2 handoff reviewed at phase start | `Completed` |
| Retrieve official AWS evidence for scope terminology and service boundaries | Official Bedrock, chunking, vector-store, OpenSearch Serverless, and Aurora PostgreSQL documentation registered | `Completed` |
| Draft `RAG-on-AWS/SCOPE.md` | Scope artifact created with all required sections and preliminary AWS source mapping | `Completed` |
| Validate scope against agenda, project rules, and AWS evidence | Gate A passed: all required boundaries, outcomes, transitions, terminology, and source links verified | `Completed` |
| Close Phase 2 and prepare Phase 3 handoff | Updated roadmap, artifacts, QA, and exact next action | `Completed` |

## 6B. Phase 3 Task-Level Progress

| Task | Evidence | Status |
|---|---|---|
| Re-read canonical scope and verify fingerprints | `SCOPE.md` and template fingerprints match Phase 2 records | `Completed` |
| Research RAG purpose and Bedrock Knowledge Bases workflow | Official AWS sources confirm external-data grounding, retrieve-then-generate, no retraining requirement, preprocessing/runtime phases, and source citations | `Completed` |
| Research chunking, embeddings, semantic retrieval, and vector stores | Official AWS sources confirm manageable chunks, numerical vector representations, semantic comparison, vector indexing, OpenSearch Serverless, and Aurora PostgreSQL roles | `Completed` |
| Research benefits, limitations, citations, and safe wording | AWS sources support “reduce/minimize risk,” evaluation need, retrieval relevance checks, and citations; no elimination guarantee | `Completed` |
| Draft `RAG-on-AWS/KNOWLEDGE.md` | Knowledge artifact created with 18 approved claims, 15 source records, coverage matrix, wording constraints, and resolved deferrals | `Completed` |
| Validate all scope deferrals and claim coverage | Gate B passed: 18 claims, 15 source records/URLs, complete coverage matrix, safe inference labels, and all deferrals resolved | `Completed` |
| Close Phase 3 and prepare Phase 4 handoff | Updated roadmap, artifacts, QA, and next action | `Completed` |

## 6C. Phase 4 Task-Level Progress

| Task | Evidence | Status |
|---|---|---|
| Re-read Presentations narrative rules and canonical artifacts | Presentations skill, content rules, `SCOPE.md`, and `KNOWLEDGE.md` reviewed; fingerprints unchanged | `Completed` |
| Define communication job, arc, and opening/closing resolution | 11-beat cumulative learning arc recorded in `SCRIPT.md` | `Completed` |
| Allocate provisional beats and 18–19 minute timing budget | 17:40 planned delivery plus 2:20 safety margin | `Completed` |
| Map beats to approved claim IDs and use-case roles | All C01–C18 mapped; use-case role documented per beat | `Completed` |
| Validate learning progression, density, transitions, and scope | Phase 4 QA passed: 11 beats/questions, 17:40 total, 2:20 margin, C01–C18 coverage, opening/closing resolution, and scope compliance verified | `Completed` |
| Close Phase 4 and prepare Phase 5 handoff | Updated roadmap, artifacts, QA, and next action | `Completed` |

## 6D. Phase 5 Task-Level Progress

| Task | Evidence | Status |
|---|---|---|
| Re-read Presentations rules and Phase 4 blueprint | Skill rules and canonical artifacts reviewed; fingerprints unchanged | `Completed` |
| Write full Vietnamese talk tracks for beats 1–11 | All 11 delivery-script sections contain natural Vietnamese prose | `Completed` |
| Write concise Vietnamese speaker notes for beats 1–11 | All 11 delivery-script sections contain short live-reference bullets | `Completed` |
| Add objectives, transitions, timing, and terminology notes | All 11 sections contain required metadata | `Completed` |
| Validate naturalness, newcomer clarity, claim safety, and timing | Gate C passed: all required sections present, claim wording reviewed, approximately 1,948 words, 17:40 target, and 2:20 safety margin retained | `Completed` |
| Close Phase 5 and prepare Phase 6 handoff | Updated roadmap, artifacts, QA, and next action | `Completed` |

## 7. Decision Log

| Date | Decision | Rationale | Affected artifacts |
|---|---|---|---|
| 2026-07-16 | Allocate 20 minutes to the RAG module | Confirmed by the user | `SCOPE.md`, `SCRIPT.md`, `SLIDE-CONTENT.md`, final deck |
| 2026-07-16 | Target a newcomer audience | Confirmed by the user | All content artifacts |
| 2026-07-16 | Use English slide copy and Vietnamese delivery material | Confirmed by the user | `SCRIPT.md`, `SLIDE-CONTENT.md`, final deck |
| 2026-07-16 | Exclude Kahoot and demo work | Assigned to other team members | Scope, narrative, script, final deck |
| 2026-07-16 | Treat the second `Embedding Models` agenda line as a typo | User confirmed it is not a second topic | `SCOPE.md`, `KNOWLEDGE.md`, slide plan |
| 2026-07-16 | Use Cloud Mastery Knowledge Assistant as the teaching use case | Relatable to the event and suitable for explaining the RAG flow to newcomers | Narrative, script, slides |
| 2026-07-16 | Begin with a “RAG with Amazon Bedrock” section divider | Enables clean merging into the team's master deck | `SLIDE-CONTENT.md`, final deck |
| 2026-07-16 | Keep slide count flexible | Density, pacing, and template fit determine the appropriate count | Narrative, slide plan, final deck |
| 2026-07-16 | Include both full talk track and concise speaker notes | User requires both rehearsal and live-reference formats | `SCRIPT.md` |
| 2026-07-16 | Preserve `Slide/Template.pptx` as immutable | User requirement and template-following contract | Template workflow and QA |
| 2026-07-16 | Do not create a distilled prompt | `AGENTS.md` and this file are the canonical handoff system | Project workflow |
| 2026-07-16 | Use AI Agents on AWS and `awsknowledge` from Phase 2 onward | Scope authoring contains AWS terminology and boundaries whose accuracy must be verified before deeper content research | `AGENTS.md`, `SCOPE.md`, `KNOWLEDGE.md`, this file |

## 8. Assumptions and Open Questions

### Active assumptions

- The RAG section follows other Amazon Bedrock concepts and precedes the
  separately owned Kahoot section.
- The final module should be merge-ready without a standalone presenter intro
  or generic closing slide.
- The Cloud Mastery Knowledge Assistant is an explanatory scenario, not a demo
  application to be built.
- AWS claims will be researched at execution time through the AI Agents on AWS
  plugin and `awsknowledge`, not accepted from memory alone.

### Open questions

- None currently blocking Phase 2. Any new ambiguity discovered during scope
  extraction must be recorded here before proceeding.

## 9. AWS Source Registry and Claim Coverage

| Source | Claims covered | Status |
|---|---|---|
| AI Agents on AWS plugin / `awsknowledge` | Primary verification and research channel from Phase 2 onward | Available; mandatory for Phase 2 scope validation and Phase 3 research |
| [How Amazon Bedrock knowledge bases work](https://docs.aws.amazon.com/bedrock/latest/userguide/kb-how-it-works.html) | Official baseline for RAG, preprocessing, chunks, embeddings, vector indexes, retrieval, and response augmentation | Retrieved through `awsknowledge`; preliminary Phase 2 source |
| [Grounding and Retrieval Augmented Generation](https://docs.aws.amazon.com/prescriptive-guidance/latest/agentic-ai-serverless/grounding-and-rag.html) | Foundation models may lack proprietary/recent data; RAG combines semantic retrieval and generation using external context without retraining | Retrieved through `awsknowledge`; accepted Phase 3 source |
| [What is RAG?](https://aws.amazon.com/what-is/retrieval-augmented-generation/) | Generic external-data, retrieval, prompt augmentation, and update flow | Retrieved through `awsknowledge`; accepted explanatory source |
| [Retrieval Augmented Generation options and architectures on AWS](https://docs.aws.amazon.com/prescriptive-guidance/latest/retrieval-augmented-generation-options/introduction.html) | RAG references authoritative data outside model training sources before generation | Retrieved through `awsknowledge`; accepted Phase 3 source |
| [Retrieving information using Amazon Bedrock Knowledge Bases](https://docs.aws.amazon.com/bedrock/latest/userguide/kb-how-retrieval.html) | Retrieve returns relevant source chunks; RetrieveAndGenerate combines retrieval with model invocation and includes source attribution | Retrieved through `awsknowledge`; accepted Phase 3 source |
| [Amazon Bedrock FAQs](https://aws.amazon.com/bedrock/faqs/) | Retrieved information includes citations; AWS frames this as improving transparency and minimizing hallucination risk | Retrieved through `awsknowledge`; accepted supporting source |
| [How content chunking works for knowledge bases](https://docs.aws.amazon.com/bedrock/latest/userguide/kb-chunking.html) | Documents are split into manageable chunks; chunks are converted to embeddings and written to a vector index | Retrieved through `awsknowledge`; accepted for Phase 2 terminology |
| [Data lifecycle in generative AI](https://docs.aws.amazon.com/prescriptive-guidance/latest/strategy-data-considerations-gen-ai/lifecycle.html) | Data quality, updates, chunking, embedding-model choice, and retrieval settings affect RAG relevance and quality | Retrieved through `awsknowledge`; accepted Phase 3 source |
| [Evaluate the performance of RAG sources](https://docs.aws.amazon.com/bedrock/latest/userguide/evaluation-kb.html) | Retrieval and generation are separately evaluable; relevance and response effectiveness are not assumed | Retrieved through `awsknowledge`; accepted Phase 3 limitation source |
| [Security considerations for data in generative AI](https://docs.aws.amazon.com/prescriptive-guidance/latest/strategy-data-considerations-gen-ai/security.html) | RAG is one mitigation that can reduce hallucinations by grounding answers; hallucinations also arise from the probabilistic nature of LLMs | Retrieved through `awsknowledge`; accepted safe-wording source |
| [Knowledge bases for Amazon Bedrock — vector databases](https://docs.aws.amazon.com/prescriptive-guidance/latest/retrieval-augmented-generation-options/rag-fully-managed-bedrock.html) | Vector-store role; Amazon OpenSearch Serverless and Amazon Aurora PostgreSQL-Compatible Edition are supported agenda-relevant choices | Retrieved through `awsknowledge`; accepted for Phase 2 service boundary |
| [Prerequisites for using a vector store you created for a knowledge base](https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base-setup.html) | Amazon OpenSearch Serverless vector search collections and indexes can store Bedrock-generated embeddings | Retrieved through `awsknowledge`; accepted for Phase 2 service role |
| [Using Aurora PostgreSQL as a Knowledge Base for Amazon Bedrock](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/AuroraPostgreSQL.VectorDB.html) | Aurora PostgreSQL can store chunks/vectors and serve as a vector-store backend for Bedrock Knowledge Bases | Retrieved through `awsknowledge`; accepted for Phase 2 service role |
| [Amazon Aurora FAQs](https://aws.amazon.com/rds/aurora/faqs/) | pgvector enables Aurora PostgreSQL to store, index, search, and query embeddings for semantic similarity | Retrieved through `awsknowledge`; accepted Phase 3 source |
| Official AWS documentation URLs | RAG, Knowledge Bases for Amazon Bedrock, embeddings, vector stores, OpenSearch Serverless, Aurora PostgreSQL, evaluation, and hallucination wording | Phase 3 source-to-claim coverage complete |

No technical AWS claim is considered verified until it is recorded with an
official source in `KNOWLEDGE.md`.

## 10. Artifact Registry

| Artifact | Purpose | State | Last validation |
|---|---|---|---|
| `AGENTS.md` | Durable working rules | Existing / canonical | Existence and fingerprint verified 2026-07-16 |
| `AGENDA.md` | Event scope source | Existing / canonical | Read and fingerprint verified 2026-07-16 |
| `Slide/Template.pptx` | Immutable source deck | Existing / canonical | Existence, size, and baseline fingerprint verified 2026-07-16 |
| `RAG-on-AWS/OPERATION.md` | Source of operation truth | Created / canonical | Zero-context handoff structure validated 2026-07-16 |
| `RAG-on-AWS/SCOPE.md` | Locked scope and learning outcomes | Completed / canonical | Gate A passed 2026-07-16; Git blob fingerprint `e4c16c9b682406a7c5d6216f48990700e9c3d583` |
| `RAG-on-AWS/KNOWLEDGE.md` | Verified AWS knowledge and citations | Completed / canonical | Gate B passed 2026-07-16; 18 approved claims, 15 source records, fingerprint `e410aafeb0af8c8989ede23665d64cfa829ecc00` |
| `RAG-on-AWS/SCRIPT.md` | Narrative blueprint, full Vietnamese talk tracks, and speaker notes | Completed / canonical | Gate C passed 2026-07-16; 11 full tracks, 11 note sets, all metadata, approximately 1,948 words; fingerprint `d95441f64eabe59b5f46ce875c6da2c7026398d6` |
| `RAG-on-AWS/SLIDE-CONTENT.md` | English slide authoring contract | Not created | `Pending` |
| `Slide/RAG-on-AWS.pptx` | Merge-ready RAG slide module | Not created | `Pending` |

## 11. Template Audit Summary

- Template path: `Slide/Template.pptx`.
- Immutability baseline: Git blob fingerprint
  `53fa4c005acc8eb1c840a818dc6749eb5c6ceeec`.
- Full template inspection and slide mapping belong to Phase 7 and have not yet
  been accepted as execution evidence.
- No output slide may be authored until Gates A–D are complete and the Phase 7
  mapping has been validated.
- Final QA must recheck the template fingerprint and investigate any mismatch.

## 12. Operation Log

| Time (+07:00) | Phase | Action | Result / evidence | Affected artifact | Next action |
|---|---:|---|---|---|---|
| 2026-07-16 21:20 | 1 | Read workspace input metadata | `AGENTS.md`, `AGENDA.md`, and `Slide/Template.pptx` are present | This file | Fingerprint inputs |
| 2026-07-16 21:20 | 1 | Attempted SHA-256 with PowerShell `Get-FileHash` | Cmdlet unavailable; no file changed | None | Use Git blob hashes as reproducible fingerprints |
| 2026-07-16 21:20 | 1 | Generated Git blob fingerprints | Fingerprints recorded in Canonical Inputs | This file | Create operation truth |
| 2026-07-16 21:20 | 1 | Read `AGENDA.md` directly | Confirmed RAG under Amazon Bedrock, duplicated Embedding Models line, and Kahoot listing | This file | Validate handoff completeness |
| 2026-07-16 21:20 | 1 | Created `RAG-on-AWS/OPERATION.md` | Roadmap, decisions, artifacts, source registry, template baseline, and handoff state initialized | `OPERATION.md` | Perform final Phase 1 validation |
| 2026-07-16 21:22 | 1 | Validated zero-context handoff completeness | Required context, roadmap, evidence, artifacts, decisions, QA state, and exact next action are present and internally consistent | `OPERATION.md` | Close Phase 1 and prepare Phase 2 |
| 2026-07-16 21:22 | 1 | Closed Phase 1 | Phase 1 marked `Completed`; Phase 2 is the next pending phase | `OPERATION.md` | Create `RAG-on-AWS/SCOPE.md` |
| 2026-07-16 21:22 | 1 | Rechecked template fingerprint and aligned handoff | Template fingerprint remains `53fa4c005acc8eb1c840a818dc6749eb5c6ceeec`; handoff now starts directly at Phase 2 | `OPERATION.md` | Await authorization to start Phase 2 |
| 2026-07-16 | Pre-Phase 2 | Strengthened AWS source requirement | User requires AWS Agents and `awsknowledge` during content authoring; durable rule and exact next action updated | `AGENTS.md`, `OPERATION.md` | Use `awsknowledge` while creating `SCOPE.md` |
| 2026-07-16 21:26 | Pre-Phase 2 | Verified `awsknowledge` access with an official Bedrock query | Retrieved the official AWS user-guide page describing RAG preprocessing and runtime retrieval; source registered without starting scope authoring | `OPERATION.md` | Use this and additional official AWS evidence during Phase 2 |
| 2026-07-16 21:27 | 2 | Started Phase 2 | Re-read agenda and durable rules; set Phase 2 as the only `In Progress` roadmap phase | `OPERATION.md` | Retrieve official AWS evidence for scope boundaries |
| 2026-07-16 21:28 | 2 | Retrieved Phase 2 AWS evidence through `awsknowledge` | Official sources confirm the preprocessing/runtime flow, chunking and embeddings terminology, vector-store role, OpenSearch Serverless, and Aurora PostgreSQL support | `OPERATION.md` | Draft `SCOPE.md` from confirmed evidence |
| 2026-07-16 21:30 | 2 | Created `RAG-on-AWS/SCOPE.md` | Scope now records agenda placement, audience, timing, learning outcomes, in/out boundaries, use case, transitions, terminology, preliminary AWS evidence, and acceptance criteria | `SCOPE.md`, `OPERATION.md` | Run Gate A validation |
| 2026-07-16 21:30 | 2 | Ran Gate A scope validation | All 16 scope sections, required decisions, five official AWS source links, agenda boundaries, and terminology constraints verified; template fingerprint unchanged | `SCOPE.md`, `OPERATION.md` | Close Phase 2 |
| 2026-07-16 21:30 | 2 | Closed Phase 2 | `SCOPE.md` accepted as canonical with fingerprint `e4c16c9b682406a7c5d6216f48990700e9c3d583`; Phase 3 prepared | `SCOPE.md`, `OPERATION.md` | Build `KNOWLEDGE.md` with AWS evidence |
| 2026-07-16 21:32 | 3 | Started Phase 3 | Canonical scope and template fingerprints match Phase 2 records; Phase 3 is the only roadmap phase `In Progress` | `OPERATION.md` | Research RAG purpose and Bedrock workflow |
| 2026-07-16 21:32 | 3 | Researched RAG purpose and Bedrock Knowledge Bases workflow through `awsknowledge` | Official sources confirm external-data grounding, retrieve-then-generate, no retraining requirement, preprocessing/runtime phases, retrieval separation, and citations | `OPERATION.md` | Research chunking, embeddings, and vector stores |
| 2026-07-16 21:33 | 3 | Researched chunking, embeddings, semantic retrieval, and vector-store roles | Official sources support the beginner mental model and confirm OpenSearch Serverless/Aurora PostgreSQL as alternative vector-store backends | `OPERATION.md` | Research limitations and safe wording |
| 2026-07-16 21:33 | 3 | Researched limitations, evaluation, citations, and hallucination wording | AWS supports wording such as reduce/minimize risk and provides separate retrieval/generation evaluation; no source supports an elimination guarantee | `OPERATION.md` | Draft `KNOWLEDGE.md` |
| 2026-07-16 21:36 | 3 | Created `RAG-on-AWS/KNOWLEDGE.md` | Added beginner mental model, core concepts, two-phase flow, use case, Bedrock mapping, vector-store roles, benefits/limitations, misconception corrections, vocabulary, 18 claim IDs, 15 source records, coverage matrix, and deferral resolution | `KNOWLEDGE.md`, `OPERATION.md` | Run Gate B validation |
| 2026-07-16 21:36 | 3 | Corrected claim-to-source traceability during Gate B | Hallucination claim C16 now maps to Bedrock FAQ, RAG evaluation, and security guidance rather than the unrelated data-lifecycle source | `KNOWLEDGE.md`, `OPERATION.md` | Continue Gate B validation |
| 2026-07-16 21:36 | 3 | Corrected Aurora claim traceability during Gate B | Claim C14 now maps to vector-store support, Aurora integration, and Aurora pgvector sources rather than the OpenSearch setup source | `KNOWLEDGE.md`, `OPERATION.md` | Complete Gate B validation |
| 2026-07-16 21:37 | 3 | Ran Gate B knowledge validation | Verified 18 sequential claim IDs, 15 source records and URLs, source-to-claim matrix, all scope concepts, safe inference labels, wording constraints, and eight resolved Phase 3 deferrals | `KNOWLEDGE.md`, `OPERATION.md` | Close Phase 3 |
| 2026-07-16 21:37 | 3 | Closed Phase 3 | `KNOWLEDGE.md` accepted as canonical with fingerprint `e410aafeb0af8c8989ede23665d64cfa829ecc00`; template and scope fingerprints remain unchanged | `KNOWLEDGE.md`, `OPERATION.md` | Design the 20-minute narrative in Phase 4 |
| 2026-07-16 21:42 | 4 | Started Phase 4 using Presentations narrative rules | Canonical scope/knowledge/template fingerprints match; final slide copy and PowerPoint authoring remain deferred | `SCRIPT.md`, `OPERATION.md` | Create narrative blueprint and timing plan |
| 2026-07-16 21:44 | 4 | Created Phase 4 narrative blueprint in `SCRIPT.md` | Added 11 cumulative beats, 17:40 timing plan, 2:20 safety margin, transitions, checkpoints, all 18 claim mappings, use-case discipline, density guidance, and Phase 5 contract | `SCRIPT.md`, `OPERATION.md` | Run Phase 4 narrative QA |
| 2026-07-16 21:44 | 4 | Ran Phase 4 narrative QA | Verified 11 beats, 11 audience questions, 18 claim-coverage entries, 17:40 total, 2:20 buffer, opening/closing resolution, use-case discipline, scope compliance, and no premature slide/PPT authoring | `SCRIPT.md`, `OPERATION.md` | Close Phase 4 |
| 2026-07-16 21:44 | 4 | Closed Phase 4 | Narrative blueprint accepted with fingerprint `d9eaa19a2f3cc159e9da5a2d33cd47b7e5409ad7`; Phase 5 prepared | `SCRIPT.md`, `OPERATION.md` | Write full Vietnamese talk tracks and speaker notes |
| 2026-07-16 21:54 | 5 | Started Phase 5 using Presentations narrative rules | Phase 4 blueprint and canonical fingerprints verified; script authoring will preserve the 17:40 target and approved claims | `SCRIPT.md`, `OPERATION.md` | Write both Vietnamese script formats for all 11 beats |
| 2026-07-16 21:56 | 5 | Drafted complete Phase 5 delivery script | Added full Vietnamese talk track, concise speaker notes, objective, duration, transitions, and terminology guidance for all 11 slides plus rehearsal guidance | `SCRIPT.md`, `OPERATION.md` | Run Gate C script QA |
| 2026-07-16 | 5 | Measured talk-track length during Gate C | 11 sections contain approximately 1,948 words; straight reading is about 16:14 at 120 WPM, leaving planned emphasis/transition time within the 17:40 target and preserving the 2:20 safety margin | `SCRIPT.md`, `OPERATION.md` | Complete Gate C review |
| 2026-07-16 21:58 | 5 | Ran Gate C script validation | Verified 11/11 full talk tracks, speaker notes, transition-in, transition-out, terminology, objectives, durations, and claim sets; reviewed newcomer clarity and prohibited wording | `SCRIPT.md`, `OPERATION.md` | Close Phase 5 |
| 2026-07-16 21:58 | 5 | Closed Phase 5 | Script accepted as canonical with fingerprint `d95441f64eabe59b5f46ce875c6da2c7026398d6`; Phase 6 prepared | `SCRIPT.md`, `OPERATION.md` | Create exact English slide-content specification |

## 13. QA and Unresolved Issues

### Completed checks

- Required canonical inputs exist.
- Agenda placement is understood.
- Initial template immutability fingerprint is recorded.
- Confirmed user decisions are represented in this file.
- Every required roadmap phase has an explicit status.
- Zero-context handoff information is complete and internally consistent.
- Phase 1 completion evidence is recorded.
- Gate A passed: `SCOPE.md` is consistent with `AGENTS.md`, `AGENDA.md`, and
  preliminary official AWS evidence.
- Scope covers the 20-minute limit, newcomer audience, typo handling, Kahoot
  exclusion, teaching use case, transitions, service-choice boundary, and
  Phase 3 verification deferrals.
- `Slide/Template.pptx` fingerprint remains unchanged after Phase 2.
- Gate B passed: every in-scope knowledge concept has a beginner-safe
  explanation and approved evidence boundary.
- `KNOWLEDGE.md` contains 18 approved claims, 15 official AWS source records,
  a complete source-to-claim matrix, safe inference labels, wording constraints,
  and resolved Phase 3 deferrals.
- Hallucination wording is restricted to reduce/minimize risk; elimination and
  correctness guarantees are prohibited.
- OpenSearch Serverless and Aurora PostgreSQL remain alternative vector-store
  choices in the simplified architecture.
- `Slide/Template.pptx` and canonical `SCOPE.md` fingerprints remain unchanged
  after Phase 3.
- Phase 4 narrative QA passed with 11 beats, 11 audience questions, all 18
  approved claim IDs mapped, and a 17:40 planned runtime plus 2:20 safety margin.
- Generic RAG concepts precede AWS mapping; the use case remains supporting;
  OpenSearch/Aurora remain alternatives; final slide copy and PowerPoint work
  remain deferred.
- Gate C passed: all 11 slides contain both Vietnamese formats plus objective,
  timing, transitions, terminology, and approved claim references.
- Script length is approximately 1,948 words; straight reading at 120 WPM is
  about 16:14, leaving planned emphasis/transition time within 17:40 and the
  separate 2:20 safety margin.
- Script wording preserves no-retraining, alternative-vector-store,
  supported-citation, synchronization, and reduce-not-eliminate boundaries.

### Pending checks

- Phase 6 exact English copy, density, script alignment, visual intent, and
  claim/source coverage.

### Unresolved issues

- None blocking the next phase.

## 14. Handoff Instructions

Phases 1–5 are complete. To continue with Phase 6:

1. Read `AGENTS.md` and this file.
2. Read canonical `SCOPE.md`, `KNOWLEDGE.md`, and `SCRIPT.md`.
3. Set Roadmap Phase 6 and the Current Execution State to `In Progress` before
   writing slide content.
4. Create `SLIDE-CONTENT.md` with exact English audience-facing copy for each
   slide, keeping the Vietnamese explanation in `SCRIPT.md`.
5. Record narrative role, primary claim, visual intent, script link, claim IDs,
   source references, and density constraints per slide.
6. Treat 11 slides as a hypothesis that may be adjusted for legibility, but
   preserve narrative order and timing.
7. Record provisional template-layout needs without editing the PPTX or claiming
   final source-slide mappings before the complete template audit.
8. Validate exact copy, newcomer readability, script alignment, visual economy,
   source coverage, and scope compliance.
9. Update the artifact registry, roadmap, operation log, QA state, and exact
   next action before starting Phase 7.

Do not begin AWS research, script writing, slide-content authoring, or
PowerPoint editing until its preceding gate is complete.
