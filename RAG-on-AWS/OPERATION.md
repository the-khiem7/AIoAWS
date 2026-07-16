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
| Current phase | Phase 8 — Duplicate template slides and author the RAG PowerPoint |
| Phase status | `Pending` |
| Current task | Phase 7 completed; Phase 8 is ready to start |
| Last updated | 2026-07-16 22:26 +07:00 |
| Blocking issue | None |
| Exact next action | Start Phase 8 from the prepared scratch `template-starter.pptx`; use artifact-tool to edit only the inherited targets in the validated frame map, create/resolve the six planned replacement visuals, and export a distinct `Slide/RAG-on-AWS.pptx` without modifying the source template. |

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
| 6 | Produce and review the English slide-content specification | `SLIDE-CONTENT.md`; copy and source coverage review | `Completed` |
| 7 | Audit the complete template and map every output slide | Template audit; validated output-to-source slide map | `Completed` |
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

## 6E. Phase 6 Task-Level Progress

| Task | Evidence | Status |
|---|---|---|
| Re-read Presentations content and template-following rules | Presentations skill, content-quality rules, template-following contract, and canonical Phase 6 inputs reviewed | `Completed` |
| Draft exact English audience-visible copy for slides 1–11 | `SLIDE-CONTENT.md` contains exact titles, labels, statements, and footnotes for all 11 slides | `Completed` |
| Map each slide to script sections and approved AWS claims/sources | Per-slide mapping plus consolidated coverage matrix records C01–C18 subsets and S1–S15 references | `Completed` |
| Record visual intent, density constraints, and provisional template-layout needs | Every slide records visual intent, density budget, candidate source slide, and inherited-object intent; final mapping remains deferred to Phase 7 | `Completed` |
| Run Gate D copy, density, alignment, source, and scope validation | Passed: 11/11 slides contain all required contracts; visible-copy density is 12–50 words; C01–C18 and S1–S15 references validate; no internal terms appear in visible-copy blocks; canonical fingerprints are unchanged | `Completed` |
| Close Phase 6 and prepare Phase 7 handoff | Roadmap, artifact registry, QA, operation log, and exact next action updated | `Completed` |

## 6F. Phase 7 Task-Level Progress

| Task | Evidence | Status |
|---|---|---|
| Re-read Presentations and template-following rules | Skill, content rules, template contract, `OPERATION.md`, and `SLIDE-CONTENT.md` reviewed | `Completed` |
| Inspect all 16 source slides and inherited objects | Presentations inspection produced 16 full-size renders, 16 layout JSON files, manifest, NDJSON inventory, 20 extracted media assets, and font/theme evidence; montage and every slide reviewed at full size | `Completed` |
| Record complete template audit and reusable layout inventory | `template-audit.txt` records all 16 source slides, selected/rejected layouts, theme/font/media evidence, preservation contract, risks, and reusable families | `Completed` |
| Map 11 output slides to validated source slides | `template-frame-map.json` maps all outputs, 105 inherited edit targets, and all nine omitted source slides; `deviation-log.txt` and `source-notes.txt` record deviations/provenance | `Completed` |
| Validate frame map and prepare starter deck | Validator passed with zero issues; starter deck contains 11 duplicated slides in mapped order, 8,536,855 bytes; previews/layouts and separately generated contact sheet inspected | `Completed` |
| Update `SLIDE-CONTENT.md` with accepted source/object plan | All 11 slide contracts now record validated source slides, exact inherited target IDs/actions, template-fit exact copy, and a consolidated map | `Completed` |
| Run Gate E validation and close Phase 7 | Gate E passed: validator zero issues, 11 mapped starter slides, 105 inherited targets, zero add actions, complete canonical mapping, unchanged template fingerprint, and Phase 8 handoff | `Completed` |

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
| 2026-07-16 | Keep the accepted 11-slide specification for Gate D | The 17:40 narrative fits the slot, each slide has one teaching job, and visible-copy density remains within 12–50 words | `SLIDE-CONTENT.md`, `SCRIPT.md` |
| 2026-07-16 | Map outputs to source slides `1,3,9,9,11,8,11,12,15,8,15` | Full template inspection found these inherited patterns best preserve the narrative and avoid unsupported parallel layouts | `SLIDE-CONTENT.md`, Phase 7 frame map, final deck |
| 2026-07-16 | Replace provisional source 14 with source 9 for the use case | Three connected states distinguish question, retrieved passage, and generated answer without letting a full-bleed scenario dominate | `SLIDE-CONTENT.md`, final deck slide 4 |
| 2026-07-16 | Use source 15 for vector-store alternatives and remove number circles | Equal cards avoid the better/worse semantics of source 8 and the sequence semantics of inherited numbers | `SLIDE-CONTENT.md`, final deck slide 9 |
| 2026-07-16 | Adapt runtime and Bedrock copy to inherited structures | Runtime uses four nodes by combining question/search; Bedrock uses four capability rows instead of overlaying a custom two-lane layout | `SLIDE-CONTENT.md`, final deck slides 7–8 |
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
| `RAG-on-AWS/SLIDE-CONTENT.md` | English slide authoring contract and validated source/object map | Completed / canonical | Gates D–E passed 2026-07-16; 11 exact-copy blocks, 11 validated source slides, 105 inherited targets, template-fit revisions, complete approved claim coverage; fingerprint `ac9febd5def18955cdf894392ede99b9ccffb39b` |
| Phase 7 external scratch evidence | Template inspection, audit, frame map, deviation/source notes, starter deck, layouts, renders, and QA | Completed / retained | `C:\Users\THEKHI~1\AppData\Local\Temp\codex-presentations\manual-20260716-cloudmastery\rag-template-audit\tmp`; frame-map validator passed; starter fingerprint `eb7d329e7c3bcd66d7bd35fec365ac4f7d4227d7` |
| `Slide/RAG-on-AWS.pptx` | Merge-ready RAG slide module | Not created | `Pending` |

## 11. Template Audit Summary

- Template path: `Slide/Template.pptx`.
- Immutability baseline: Git blob fingerprint
  `53fa4c005acc8eb1c840a818dc6749eb5c6ceeec`.
- Full inspection accepted: 16 renders, 16 layout JSON files, object inventory,
  theme/font evidence, 20 extracted media assets, montage, and full-size review.
- Accepted output-to-source order:
  `1,3,9,9,11,8,11,12,15,8,15`.
- Frame map: 11 outputs, 105 inherited edit targets, nine omitted source slides,
  zero `add` actions, validator `pass` with zero issues.
- Starter deck: 11 duplicated source slides, 8,536,855 bytes, fingerprint
  `eb7d329e7c3bcd66d7bd35fec365ac4f7d4227d7`.
- Full audit, frame map, deviation log, source notes, starter deck, previews,
  layouts, and QA reports are retained under the Phase 7 external scratch path
  recorded in the artifact registry.
- Gates A–E are complete. Phase 8 must author only from the prepared starter and
  validated inherited targets.
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
| 2026-07-16 22:03 | 6 | Started Phase 6 using Presentations content and template-following rules | Phase 6 is the only roadmap phase `In Progress`; canonical scope, knowledge, and script are the content inputs; final template mapping and PPTX editing remain deferred | `OPERATION.md` | Draft exact English copy and slide authoring contract |
| 2026-07-16 22:03 | 6 | Created `RAG-on-AWS/SLIDE-CONTENT.md` | Added exact English copy for 11 slides, narrative roles, primary claims, visual intents, density budgets, script links, approved claim/source mappings, provisional source-layout candidates, inherited-object intent, and Phase 7 mapping contract | `SLIDE-CONTENT.md`, `OPERATION.md` | Run Gate D validation |
| 2026-07-16 22:06 | 6 | Ran Gate D slide-specification validation | Verified 11 slide headings, exact-copy blocks, visual intents, density budgets, script mappings, and provisional template candidates; visible copy is 12–50 words per slide; all C01–C18 occur in the specification; no internal-production terms occur in visible-copy blocks; source and scope wording passed | `SLIDE-CONTENT.md`, `OPERATION.md` | Recheck canonical fingerprints and close Phase 6 |
| 2026-07-16 22:06 | 6 | Rechecked canonical artifact fingerprints | Template `53fa4c005acc8eb1c840a818dc6749eb5c6ceeec`, scope `e4c16c9b682406a7c5d6216f48990700e9c3d583`, knowledge `e410aafeb0af8c8989ede23665d64cfa829ecc00`, and script `d95441f64eabe59b5f46ce875c6da2c7026398d6` remain unchanged | `OPERATION.md` | Close Phase 6 |
| 2026-07-16 22:06 | 6 | Closed Phase 6 | `SLIDE-CONTENT.md` accepted as canonical with fingerprint `ea7f283cde109cf27ca573efb60025d0cd776ba5`; Phase 7 prepared | `SLIDE-CONTENT.md`, `OPERATION.md` | Audit all 16 template slides and validate the output-to-source map |
| 2026-07-16 22:09 | 7 | Started Phase 7 using Presentations template-following mode | Phase 7 is the only roadmap phase `In Progress`; full 16-slide inspection and inherited-object mapping will precede any PowerPoint authoring | `OPERATION.md` | Inspect the complete source deck in external scratch space |
| 2026-07-16 22:10 | 7 | Inspected all 16 source slides with Presentations template-following tooling | Generated 16 renders, 16 layout JSON files, template manifest, object inventory, 20 extracted media assets, and theme/font evidence under external scratch; reviewed montage and each slide at full size | `OPERATION.md` | Record the complete reusable-layout audit |
| 2026-07-16 22:14 | 7 | Completed the 16-slide template audit | `template-audit.txt` records every source slide, selected layout families, rejected provisional mappings, preservation rules, and Phase 8 risks; viable inherited structures exist for all 11 outputs | `OPERATION.md` | Build the exact output-to-source frame map |
| 2026-07-16 22:17 | 7 | Created and validated the output-to-source frame map | Mapped all 11 outputs to sources 1, 3, 8, 9, 11, 12, and 15; recorded exact inherited edit targets, nine omitted-source reasons, deviations, and asset provenance; validator returned `pass` with zero issues | `OPERATION.md` | Prepare the duplicated-source starter deck |
| 2026-07-16 22:18 | 7 | First starter-deck preparation attempt failed in optional contact-sheet generation | The script created `template-starter.pptx` and its inspect artifact, then raised `TypeError: Cannot read properties of undefined (reading 'trim')` in `runContactSheet`; source template and canonical artifacts were unchanged | `OPERATION.md` | Rerun without optional contact sheet and create montage separately |
| 2026-07-16 22:19 | 7 | Prepared and inspected the duplicated-source starter deck | Rerun without the optional contact-sheet argument succeeded: 11 mapped slides, 8,536,855 bytes, per-slide renders/layouts, and manifest; a separate montage confirmed the expected source order and inherited design | `OPERATION.md` | Apply validated source/object mapping to `SLIDE-CONTENT.md` |
| 2026-07-16 22:24 | 7 | Applied the validated template map to `SLIDE-CONTENT.md` | Replaced every provisional source with an accepted source slide, added exact inherited target IDs/actions, recorded the 11-slide mapping, and revised exact copy where required by inherited structures without changing claims or narrative order | `SLIDE-CONTENT.md`, `OPERATION.md` | Run Gate E validation |
| 2026-07-16 22:25 | 7 | Ran Gate E template-map validation | Verified 11 output slides, 105 inherited targets, zero add actions, nine omitted sources, exact starter/source order, 11 exact-copy blocks, 11 validated-source contracts, zero stale provisional markers, and no final deck created prematurely; validator passed with zero issues | `SLIDE-CONTENT.md`, `OPERATION.md` | Recheck template fingerprint and close Phase 7 |
| 2026-07-16 22:26 | 7 | Rechecked source-template immutability and accepted canonical fingerprints | Template remains `53fa4c005acc8eb1c840a818dc6749eb5c6ceeec`; canonical `SLIDE-CONTENT.md` is `ac9febd5def18955cdf894392ede99b9ccffb39b`; starter is `eb7d329e7c3bcd66d7bd35fec365ac4f7d4227d7` | `OPERATION.md` | Close Phase 7 |
| 2026-07-16 22:26 | 7 | Closed Phase 7 and Gate E | Complete audit/map/starter evidence exists, `SLIDE-CONTENT.md` is current, template is unchanged, and Phase 8 may author from the duplicated-source starter | `SLIDE-CONTENT.md`, `OPERATION.md` | Author `Slide/RAG-on-AWS.pptx` in Phase 8 |

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
- Gate D passed: all 11 slides contain exact English copy, visual intent,
  density budget, script mapping, and approved claim/source references.
- After template-fit revisions, audience-visible copy is 12–59 words per slide
  and contains no timing,
  speaker, claim-ID, source-ID, template, Kahoot, demo, pricing, Q&A, or
  presenter-production language.
- The specification covers all approved claims C01–C18 without introducing a
  new AWS capability, metric, recommendation, or correctness guarantee.
- `Slide/Template.pptx`, `SCOPE.md`, `KNOWLEDGE.md`, and `SCRIPT.md`
  fingerprints remain unchanged after Phase 6.
- Gate E passed: all 16 template slides were inspected through full-size
  renders and layout/object evidence.
- The accepted source order is `1,3,9,9,11,8,11,12,15,8,15`; the frame map
  contains 105 inherited targets and zero new-primitive/add actions.
- Template plan validation passed with zero issues; the duplicated-source
  starter has exactly 11 slides in the accepted order.
- `SLIDE-CONTENT.md` contains 11 validated source contracts and no stale
  provisional mapping markers.
- The source template fingerprint remains
  `53fa4c005acc8eb1c840a818dc6749eb5c6ceeec` after Phase 7.

### Pending checks

- Phase 8 artifact-tool authoring, exact-copy insertion, image replacement,
  inherited-object deletion/repositioning, and distinct PPTX export.

### Unresolved issues

- None blocking the next phase.

## 14. Handoff Instructions

Phases 1–7 and Gates A–E are complete. To continue with Phase 8:

1. Read `AGENTS.md` and this file.
2. Read canonical `SLIDE-CONTENT.md` and the matching sections in `SCRIPT.md`.
3. Reuse the retained Phase 7 scratch workspace and prepared
   `template-starter.pptx`; do not duplicate from the source template again
   unless the accepted map changes.
4. Set Roadmap Phase 8 and Current Execution State to `In Progress` before
   authoring.
5. Read the Presentations artifact-tool API references and initialize the
   artifact-tool workspace under the existing scratch `tmp` directory.
6. Resolve the six planned replacement visuals listed in `source-notes.txt`;
   use official AWS identity/assets where service identity matters and do not
   create fake interfaces or screenshots.
7. Import `template-starter.pptx` with artifact-tool and edit only the inherited
   targets in `template-frame-map.json` according to canonical exact copy.
8. Export a distinct `Slide/RAG-on-AWS.pptx`; never write to
   `Slide/Template.pptx`.
9. Update `OPERATION.md` immediately after each visual, authoring, export, or
   validation milestone before continuing to Phase 9.

Do not begin AWS research, script writing, slide-content authoring, or
PowerPoint editing until its preceding gate is complete.
