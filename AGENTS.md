# Cloud Mastery — RAG on AWS Working Instructions

## 1. Mission

This workspace supports the preparation of one presentation segment for the
**Cloud Mastery** event. The assigned segment is **RAG on AWS**, presented as
part of the broader **Amazon Bedrock Generative AI** session.

The final RAG deck is only one module of a larger team presentation. After this
module is completed, the team will merge it into the event's master deck.

The objective is to produce an accurate, beginner-friendly explanation of RAG
on AWS, together with a Vietnamese speaking script and an English PowerPoint
deck that faithfully follows the supplied template.

Do not create or maintain a distilled execution prompt. `AGENTS.md` and
`RAG-on-AWS/OPERATION.md` are the canonical handoff mechanism.

## 2. Canonical Inputs

- `AGENDA.md`: overall Cloud Mastery agenda and the source for the RAG scope.
- `Slide/Template.pptx`: the visual and structural source for every RAG slide.
- The **AI Agents on AWS** plugin, especially the `awsknowledge` MCP server:
  the authoritative knowledge source for current AWS technical claims.
- The **Presentations** plugin: the required workflow for inspecting,
  duplicating, editing, exporting, rendering, and validating the PowerPoint.

Read `AGENDA.md`, this file, and `RAG-on-AWS/OPERATION.md` before continuing an
existing run. If `OPERATION.md` does not exist, create it before substantive
research or authoring begins.

## 3. Confirmed Presentation Requirements

### Audience and duration

- Audience: newcomers to cloud and generative AI.
- Assume no prior knowledge of embeddings, vector databases, RAG, or Amazon
  Bedrock.
- Speaking duration: **20 minutes** for the RAG segment.
- Slide count is not fixed. Choose it according to information density,
  narrative pacing, and legibility. Split dense ideas across slides rather than
  shrinking text or overloading layouts.

### Language

- Audience-visible slide content: **English**.
- Presentation script and speaking guidance: **Vietnamese**.
- Keep official AWS product names and important technical terms in English;
  explain them naturally in Vietnamese in the script.

### Content focus

The presentation must prioritize the core concepts:

- The problem RAG solves.
- A beginner-friendly definition of RAG.
- Why a foundation model's built-in knowledge may be insufficient.
- The difference between retrieval and generation.
- The role of documents, chunking, embeddings, and vector stores at a
  conceptual level.
- The end-to-end RAG flow.
- How Knowledge Bases for Amazon Bedrock supports a managed RAG workflow.
- The role of supported vector-store choices relevant to the agenda, including
  Amazon OpenSearch Serverless and Amazon Aurora PostgreSQL-Compatible Edition.
- Benefits, limitations, and realistic expectations, without implying that RAG
  guarantees correctness or eliminates hallucinations.

The duplicated `Embedding Models` line in `AGENDA.md` is a typing error. Treat
it as one agenda item; do not invent a replacement topic merely to fill the
duplicate.

### Excluded work

Do not include the following unless the user later expands the scope:

- AWS Console demo or live demo.
- Step-by-step implementation tutorial.
- Application code, SDK code, or API walkthrough.
- Detailed IAM, security, networking, pricing, or operational guidance.
- Deep RAG evaluation, benchmarking, or advanced optimization.
- Kahoot questions, answers, facilitation, or slide content. Kahoot is not the
  presenter's responsibility and is outside the 20-minute RAG scope.
- Event-level opening slides, presenter biography, contact slide, or the master
  deck's general Q&A section.

## 4. Narrative and Use Case

Use one simple scenario to connect the concepts, but keep the conceptual
explanation as the main focus.

Default scenario: **Cloud Mastery Knowledge Assistant**.

In this scenario, an attendee asks questions about the event agenda, workshop
content, and Cloud Mastery documents. The assistant retrieves relevant passages
from the document collection and supplies that context to a foundation model
before the model generates an answer.

Use the scenario to explain:

- Why the model should not rely only on pre-trained knowledge.
- Why sending every document in every prompt is inefficient.
- How documents become chunks and embeddings.
- How semantic retrieval finds relevant context.
- How retrieved context augments the prompt.
- How the model generates a grounded response.
- Where Amazon Bedrock Knowledge Bases and the vector store fit.

Do not turn the scenario into a demo or let it displace the core RAG concepts.

The deck must begin with a short section-divider slide titled:
**“RAG with Amazon Bedrock”**.

Because this module will be merged into a larger deck, create a clean transition
from the preceding Bedrock content and a concise handoff at the end. Do not add
a standalone event title slide, presenter introduction, generic thank-you slide,
or independent Q&A slide.

## 5. Required Deliverables

Use the following structure unless the user explicitly changes it:

```text
RAG-on-AWS/
├── OPERATION.md
├── SCOPE.md
├── KNOWLEDGE.md
├── SCRIPT.md
└── SLIDE-CONTENT.md

Slide/
├── Template.pptx
└── RAG-on-AWS.pptx
```

### `RAG-on-AWS/SCOPE.md`

Record:

- The RAG segment's place in the full agenda.
- Audience, duration, learning outcomes, inclusions, and exclusions.
- Narrative objective and central takeaway.
- Relationship to preceding and following event sections.

### `RAG-on-AWS/KNOWLEDGE.md`

Record:

- Beginner-friendly explanations of all concepts needed by the deck.
- AWS-specific mappings and terminology.
- Verified AWS claims and their official source URLs.
- Important caveats, limitations, and wording constraints.
- A source-to-claim mapping that makes slide and script claims auditable.

### `RAG-on-AWS/SCRIPT.md`

The script must contain **both formats** for every slide:

1. **Full talk track**: a natural Vietnamese script that can be rehearsed and
   spoken almost verbatim.
2. **Speaker notes**: concise Vietnamese bullets for quick reference during the
   live presentation.

Also include for every slide:

- Suggested duration.
- Speaking objective.
- Transition into the slide.
- Transition to the next slide.
- Pronunciation or terminology notes when useful.

The total planned duration must fit within 20 minutes with a small safety
margin. Do not include Kahoot time.

### `RAG-on-AWS/SLIDE-CONTENT.md`

This is the authoring contract for the PowerPoint. For every output slide,
record:

- Slide number and narrative role.
- English title and exact audience-visible copy.
- Intended visual or diagram.
- Source slide number from `Slide/Template.pptx`.
- Inherited objects/placeholders to edit, replace, keep, or delete.
- Link to the corresponding section in `SCRIPT.md`.
- Supporting AWS claims and source references.
- Density and layout notes.

Complete and review this file before editing the PowerPoint.

### `Slide/RAG-on-AWS.pptx`

- Contains only the RAG module slides.
- Uses duplicated source slides/layouts from `Slide/Template.pptx`.
- Is designed to merge into the team's larger deck.
- Contains the “RAG with Amazon Bedrock” section divider.
- Does not contain the event-level opening, speaker introduction, Kahoot, or
  general Q&A slides.

## 6. Source of Operation Truth

`RAG-on-AWS/OPERATION.md` is mandatory and is the canonical execution state.
It must allow a new agent with no conversation memory to understand the task,
current state, completed evidence, remaining work, and exact next action.

Create it before substantive execution and update it at the start and end of
every meaningful phase. Update it immediately after a decision, scope change,
research milestone, artifact creation, validation result, blocker, or handoff.

### Continuous documentation rule

Documentation updates are part of every unit of work, not a cleanup activity at
the end of a phase.

- After completing **every small step or small task**, immediately update the
  corresponding domain document with the new result, evidence, decision, or
  validation outcome.
- In the same unit of work, update `RAG-on-AWS/OPERATION.md` with the roadmap
  status, operation-log entry, affected artifact, and exact next action.
- Do not start the next small task while the documents for the completed task
  are stale.
- Do not batch several completed tasks and document them later.
- Research must be recorded in `KNOWLEDGE.md`; scope decisions in `SCOPE.md`;
  script work in `SCRIPT.md`; slide authoring decisions in `SLIDE-CONTENT.md`;
  PowerPoint and QA results in `OPERATION.md` and the relevant artifact record.
- A task is not complete until both its working artifact and its tracking entry
  have been updated.
- Before yielding to the user or ending a turn, confirm that `OPERATION.md` is
  at least as current as every artifact changed during that turn.

The project-local Codex hook in `.codex/hooks.json` only injects a reminder when
a task starts or resumes. It must not attempt to determine task completion,
select documents, compare timestamps, or update documentation mechanically.
Those decisions require the agent to understand the work and apply the rules in
this file. The hook is only a reminder, never a substitute for agent judgment.

It must contain at least:

1. Mission and current scope.
2. Confirmed requirements and exclusions.
3. Current phase, current status, and next action.
4. Roadmap with one of these statuses for every phase:
   - `Pending`
   - `In Progress`
   - `Blocked`
   - `Completed`
5. Decision log with date, decision, rationale, and affected artifacts.
6. Assumptions and open questions.
7. AWS source registry and claim coverage.
8. Artifact registry with path, purpose, status, and last validation result.
9. Template audit summary and slide-to-source mapping status.
10. Operation log summarizing meaningful tools, commands, file changes,
    outputs, and failures.
11. QA results and unresolved issues.
12. Handoff instructions, including the exact next safe action.

Do not record hidden chain-of-thought or private internal reasoning. Record
decisions, evidence, assumptions, concise rationale, actions, results, and
reproducible next steps.

### Required roadmap

Track at least these phases:

1. Initialize operation truth and confirm workspace inputs.
2. Extract and lock the RAG scope from the agenda.
3. Research and verify RAG knowledge with AWS sources.
4. Design the beginner-focused 20-minute narrative.
5. Write and review the Vietnamese script in both required formats.
6. Produce and review the English slide-content specification.
7. Audit the complete template and map every output slide to a source slide.
8. Duplicate template slides and author the RAG PowerPoint.
9. Render, inspect, and validate every slide.
10. Run final content, source, timing, template-fidelity, and merge-readiness QA.
11. Complete the handoff and mark all delivered artifacts.

Only one phase should be `In Progress` at a time. A phase may be marked
`Completed` only when its required artifact and validation evidence exist.
Within a phase, update its task-level progress continuously according to the
continuous documentation rule above.

## 7. AWS Knowledge Rules

- Use the AI Agents on AWS plugin and `awsknowledge` as the primary source for
  AWS technical knowledge.
- Begin using `awsknowledge` in Phase 2 while the scope is being authored, not
  only in the deeper research phase. Validate AWS terminology, service roles,
  and technical boundaries before accepting them into `SCOPE.md`.
- Phase 2 may define the teaching boundary, but it must not introduce an AWS
  technical claim from model memory alone. Record the supporting AWS source or
  defer the claim explicitly to Phase 3 for verification.
- Prefer official AWS documentation over blogs. Use official AWS blogs when
  they provide necessary architecture explanations or current feature context.
- Search before asserting current product capabilities, supported vector stores,
  model choices, or managed workflow behavior.
- Preserve the exact official AWS product names.
- Record the source URL and the claim it supports in `KNOWLEDGE.md`.
- Distinguish AWS-documented facts from presentation simplifications,
  recommendations, and inferred teaching analogies.
- Do not fabricate metrics, customer outcomes, architecture properties, service
  support, quotations, or citations.
- If sources conflict or appear outdated, resolve the conflict using the most
  current authoritative AWS documentation and record the decision.

## 8. PowerPoint and Template Rules

`Slide/Template.pptx` is immutable.

- Never modify, overwrite, rename, move, or delete the template.
- Never author directly inside the original template file.
- Inspect all source slides before selecting layouts.
- Create output slides by duplicating suitable source slides.
- Preserve the source deck's background, slide master, dimensions, typography,
  font sizes, palette, spacing, logo, footer, and brand elements.
- Edit inherited objects/placeholders in place. Do not rebuild a parallel theme
  from approximate colors or screenshots.
- If content does not fit, shorten it, choose another source layout, or split it
  across slides. Do not silently shrink text below the template's established
  hierarchy.
- Use the Presentations plugin's template-following workflow and artifact-tool.
- Do not use `python-pptx` or direct OOXML mutation.
- Do not leave default or empty PowerPoint placeholders in the final deck.
- Keep visuals accurate and traceable. Do not generate fake AWS interfaces,
  logos, screenshots, or evidence.
- Use official AWS architecture icons/assets when AWS service identity matters.
- Use diagrams only when they materially improve beginner understanding.
- Keep each slide focused on one primary teaching job.

## 9. Content and Storytelling Standards

The communication job is:

> By the end of the segment, a newcomer should be able to explain why RAG is
> useful, describe its retrieve-then-generate flow, and recognize how Amazon
> Bedrock Knowledge Bases and a vector store support that flow.

Apply these standards:

- Build a cumulative learning sequence, not an inventory of AWS services.
- Use takeaway-oriented titles where the template supports them.
- Introduce terminology only when the audience has enough context to understand
  it.
- Explain technical terms in plain language before showing AWS mappings.
- Use the Cloud Mastery Knowledge Assistant consistently across the deck.
- Keep slide text concise; put explanation in the Vietnamese script.
- Avoid claiming that more context is always better.
- Avoid claiming that RAG trains or fine-tunes the foundation model.
- Avoid claiming that RAG guarantees factual answers.
- Make the distinction between source data, retrieved context, and generated
  response explicit.
- Close with a synthesis and handoff, not a generic thank-you slide.

## 10. Execution Workflow and Gates

Follow this sequence. Do not begin PowerPoint authoring before the earlier gates
are complete.

### Gate A — Scope locked

Required:

- `OPERATION.md` initialized.
- `SCOPE.md` completed and consistent with `AGENDA.md` and this file.
- Duration, audience, inclusions, exclusions, and deck boundaries recorded.
- AWS-specific terminology and service boundaries in `SCOPE.md` preliminarily
  validated through the AI Agents on AWS plugin and `awsknowledge`; source
  evidence or explicit Phase 3 verification deferrals recorded.

### Gate B — Knowledge verified

Required:

- `KNOWLEDGE.md` completed.
- Every important AWS claim mapped to an official source.
- Terminology and simplifications reviewed for a newcomer audience.

### Gate C — Narrative and script ready

Required:

- Narrative fits 20 minutes with a safety margin.
- `SCRIPT.md` contains the full Vietnamese talk track and concise speaker notes.
- Transitions support insertion into the master deck.

### Gate D — Slide specification ready

Required:

- `SLIDE-CONTENT.md` contains exact English copy and slide-by-slide intent.
- Information density is appropriate.
- Each slide has a planned source-template slide.

### Gate E — Template map validated

Required:

- All 16 template slides inspected.
- Every output slide mapped to a duplicated source slide.
- Editable inherited objects identified.
- The original template remains unchanged.

### Gate F — Deck authored and validated

Required:

- `Slide/RAG-on-AWS.pptx` exported as a distinct file.
- Every slide rendered and inspected individually at full size.
- No unintended overlap, clipping, title wrapping, broken visual, or unresolved
  placeholder remains.
- English slide copy matches `SLIDE-CONTENT.md`.
- Vietnamese script remains aligned with the final slide order.
- AWS claims remain traceable.
- Template fidelity and merge readiness pass.

## 11. Final QA Checklist

Before declaring completion, verify:

- The deck fits a 20-minute delivery with a safety margin.
- The deck is understandable to a newcomer without verbal prerequisites.
- The section divider is present.
- No event-level opening, presenter bio, Kahoot, demo, or general Q&A content is
  included.
- The use case supports rather than dominates the conceptual explanation.
- Slide text is English and the script is Vietnamese.
- `SCRIPT.md` contains both full talk tracks and concise speaker notes.
- Every AWS claim is supported by a recorded official source.
- Every output slide originates from a documented template source slide.
- `Slide/Template.pptx` is byte-for-byte untouched.
- `Slide/RAG-on-AWS.pptx` contains only the RAG module and is ready to merge.
- All generated files are registered in `OPERATION.md`.
- `OPERATION.md` identifies the final state and exact next action for the team.

## 12. Change Control

- User instructions override this file.
- When the user changes scope, update `AGENTS.md` only if the change is a durable
  project rule; always update `OPERATION.md` for the active execution state.
- Do not silently expand the scope.
- Record every material interpretation or unresolved ambiguity in
  `OPERATION.md` before proceeding.
- Preserve unrelated user files and existing worktree changes.
