# RAG with Amazon Bedrock — Slide Content Specification

## 1. Document Status

- Phase: **6 — English slide-content specification**.
- Audience-visible language: **English**.
- Delivery script and speaker notes: Vietnamese in `SCRIPT.md`.
- Working slide count: **11 slides**.
- Planned delivery time: **17:40**, leaving **2:20** inside the 20-minute slot.
- PowerPoint authoring status: **not started**.
- Template status: `Slide/Template.pptx` remains immutable.

This document is the content contract for the RAG module. All text explicitly
listed under **Exact audience-visible copy** is eligible to appear on the slide.
Production notes, timings, claim IDs, source IDs, and template instructions must
not appear in the audience-facing deck.

The source-slide numbers below are **provisional candidates only**. Phase 7 must
inspect all 16 template slides, validate every candidate, identify inherited
object IDs, and publish the final output-to-source map before PowerPoint editing.

## 2. Communication Job and Narrative Contract

> By the end, newcomers should be able to explain why RAG is useful, describe
> its retrieve-then-generate flow, and recognize how Amazon Bedrock Knowledge
> Bases and a vector store support that flow.

Narrative arc:

1. Establish the knowledge gap.
2. Introduce the retrieve-first mental model.
3. Make the model concrete through one event use case.
4. Explain preparation and semantic retrieval.
5. Walk through the runtime flow.
6. Map the generic flow to Amazon Bedrock Knowledge Bases.
7. Place the two agenda-relevant vector-store choices correctly.
8. Set realistic expectations and close with synthesis.

## 3. Global Audience-Copy Rules

- Use takeaway-oriented titles and plain language for newcomers.
- Keep official AWS product names unchanged.
- Keep source data, retrieved context, and generated response visually distinct.
- Never imply that RAG retrains the foundation model.
- Never claim that RAG guarantees correctness or eliminates hallucinations.
- Qualify source attribution as available in supported Bedrock flows.
- Qualify freshness: changed source content must be synchronized with the index.
- Present Amazon OpenSearch Serverless and Amazon Aurora
  PostgreSQL-Compatible Edition as alternatives, not sequential steps.
- Do not show timings, speaker guidance, claim IDs, source IDs, implementation
  instructions, Kahoot content, demo steps, pricing, or deep configuration.
- Preserve template font sizes. If copy does not fit, shorten it or remap/split
  the slide; do not shrink typography below the inherited hierarchy.
- Use at most two full process diagrams: preparation on Slide 5 and runtime on
  Slide 7. Other visuals should be simple examples, contrasts, or branches.

## 4. Slide-by-Slide Authoring Contract

### Slide 1 — Section divider

**Narrative role:** Mark the start of the RAG module inside the larger team
deck.

**Primary teaching job:** Establish the topic without repeating the event-level
opening.

**Exact audience-visible copy:**

- Title: `RAG with Amazon Bedrock`
- Subtitle: `Retrieve the right context. Generate a grounded response.`

**Visual intent:** Minimal section divider. Preserve the template's strongest
brand composition; no diagram, agenda, presenter details, or extra body copy.

**Density budget:** One title and one short subtitle; target fewer than 12 words
outside the title.

**Script mapping:** `SCRIPT.md` → `Slide 1 — RAG with Amazon Bedrock`.

**AWS support:** No technical claim required. The subtitle previews C02 and C09
without adding detail.

**Provisional template need:** Candidate source slide **1** — title/divider
composition. Phase 7 must confirm that this source can be reduced to a section
divider without leaving presenter or event-title placeholders.

**Inherited-object intent, pending object IDs:**

- Keep background, brand marks, master objects, palette, and typography.
- Rewrite title and subtitle placeholders in place.
- Delete presenter/event metadata only if Phase 7 classifies those inherited
  objects as editable sample placeholders.

---

### Slide 2 — The knowledge gap

**Narrative role:** Create the need for retrieval before defining RAG.

**Primary claim:** A capable foundation model may still lack the private,
domain-specific, or recently changed information needed for the current
question.

**Exact audience-visible copy:**

- Title: `A powerful model can still miss your answer`
- Lead-in: `Foundation models may not know:`
- Bullet 1: `Your private documents`
- Bullet 2: `Your domain-specific knowledge`
- Bullet 3: `Your latest updates`
- Closing line: `The knowledge exists — but not inside the model.`

**Visual intent:** One clear knowledge-gap composition: model on one side and a
small collection of event documents on the other, separated by a visible gap.
Do not depict a real AWS interface.

**Density budget:** Maximum three bullets, each under five words, plus one
closing sentence.

**Script mapping:** `SCRIPT.md` → `Slide 2 — The model can be powerful and still miss the answer`.

**Approved claims and sources:** C01 → S1, S3.

**Provisional template need:** Candidate source slide **3** — takeaway title,
short claim block, and supporting image frame.

**Inherited-object intent, pending object IDs:**

- Keep brand chrome, title hierarchy, footer, and image crop conventions.
- Rewrite title and body text in place.
- Replace the sample image only through its inherited media frame.
- Remove unused sample labels only after Phase 7 identifies them explicitly.

---

### Slide 3 — The core RAG mental model

**Narrative role:** Give the beginner definition that the rest of the module
will unpack.

**Primary claim:** RAG retrieves relevant external context before the foundation
model generates a response; it does not retrain the model.

**Exact audience-visible copy:**

- Title: `RAG retrieves before it generates`
- Step 1: `Ask a question`
- Step 2: `Retrieve relevant context`
- Step 3: `Add context to the prompt`
- Step 4: `Generate a response`
- Footer statement: `Use external knowledge without retraining the model.`
- Object label: `Source data`
- Object label: `Retrieved context`
- Object label: `Generated response`

**Visual intent:** A compact left-to-right four-step conceptual flow. Use the
three object labels to distinguish stored source material, selected context,
and generated output. This is a mental-model strip, not one of the two detailed
process diagrams.

**Density budget:** Four short step labels, three object labels, and one footer
statement. No prose paragraph.

**Script mapping:** `SCRIPT.md` → `Slide 3 — Retrieve first, generate second`.

**Approved claims and sources:** C02 → S1, S2; C03 → S1, S4; C04 → S1, S6, S7.

**Provisional template need:** Candidate source slide **11** — inherited
horizontal process structure.

**Inherited-object intent, pending object IDs:**

- Keep connectors, step spacing, title, footer, and brand elements where
  compatible.
- Rewrite inherited step labels.
- Reuse inherited process nodes; do not overlay a new parallel process.
- Delete surplus process nodes only if the validated map marks them for deletion.

---

### Slide 4 — Cloud Mastery Knowledge Assistant

**Narrative role:** Make the abstract flow concrete without turning the talk
into a demo.

**Primary claim:** The assistant can answer an event question by grounding the
response in a retrieved agenda passage rather than relying on model memory.

**Exact audience-visible copy:**

- Title: `Ground answers in Cloud Mastery documents`
- Label: `Question`
- Question: `How long is the RAG session?`
- Label: `Retrieved agenda passage`
- Passage: `RAG with Bedrock — 20 minutes`
- Label: `Generated answer`
- Answer: `The RAG session lasts 20 minutes.`
- Closing line: `Answer from event content, not memory alone.`

**Visual intent:** A single scenario with three clearly differentiated states:
question, retrieved passage, and generated answer. The agenda passage should
look like a document excerpt, not a screenshot or fake UI.

**Density budget:** One short question, one short source passage, one short
answer, and one closing line.

**Script mapping:** `SCRIPT.md` → `Slide 4 — Cloud Mastery Knowledge Assistant`.

**Approved claims and sources:** C01 → S1, S3; C02 → S1, S2; C04 → S1, S6, S7.
The `20 minutes` value comes from canonical `AGENDA.md`, not an AWS source.

**Provisional template need:** Candidate source slide **14** — use-case or
overlay composition with multiple inherited content regions.

**Inherited-object intent, pending object IDs:**

- Keep background, title, brand chrome, and inherited content alignment.
- Rewrite existing overlay text boxes as the three scenario states.
- Replace any irrelevant sample background/media only through inherited media
  targets.
- Avoid adding chat bubbles or simulated product UI.

---

### Slide 5 — Knowledge preparation

**Narrative role:** Explain what must happen before the first user question.

**Primary claim:** Source documents are divided into chunks, represented as
embeddings, and indexed in a vector store; changed content must be synchronized.

**Exact audience-visible copy:**

- Title: `Prepare knowledge before the first question`
- Step 1: `Documents`
- Step 1 detail: `Agenda and event materials`
- Step 2: `Chunks`
- Step 2 detail: `Smaller passages`
- Step 3: `Embeddings`
- Step 3 detail: `Numerical representations`
- Step 4: `Vector store`
- Step 4 detail: `Indexed for similarity search`
- Footer statement: `Synchronize the data and index when source content changes.`

**Visual intent:** First detailed process diagram: Documents → Chunks →
Embeddings → Vector store. Show one document becoming several passages, then
compact numerical representations, then one indexed store. Keep the depiction
conceptual and non-mathematical.

**Density budget:** Four nodes with one short detail each, plus one footer
statement. No implementation options or configuration labels.

**Script mapping:** `SCRIPT.md` → `Slide 5 — Prepare the knowledge before asking questions`.

**Approved claims and sources:** C05 → S4, S5; C06 → S4, S5; C07 → S4, S5, S8;
C18 → S2, S6.

**Provisional template need:** Candidate source slide **11** — four-step process
layout.

**Inherited-object intent, pending object IDs:**

- Keep process connectors, node geometry, title, and brand elements.
- Rewrite all four inherited nodes and their descriptions.
- Use inherited icon/media slots only if they remain legible and accurate.
- Do not add service logos; this slide explains generic concepts.

---

### Slide 6 — Embeddings and semantic similarity

**Narrative role:** Explain why retrieval can find relevant meaning even when
the question and passage use different words.

**Primary claim:** Embeddings are numerical representations that allow a vector
store to retrieve content by semantic similarity.

**Exact audience-visible copy:**

- Title: `Embeddings create a map of meaning`
- Example A label: `Question`
- Example A: `How long is the RAG session?`
- Example B label: `Agenda passage`
- Example B: `RAG with Bedrock — 20 minutes`
- Main statement: `Similar meaning can be close — even when the words differ.`
- Definition 1: `Embedding = numerical representation`
- Definition 2: `Vector store = finds nearby meaning`

**Visual intent:** A simple “map of meaning” analogy with the question and
agenda passage positioned close together. Other faint points may suggest
unrelated topics, but do not add axes, equations, scores, or fake precision.

**Density budget:** Two short examples, one statement, and two compact
definitions. No bullet list or paragraph.

**Script mapping:** `SCRIPT.md` → `Slide 6 — A map of meaning`.

**Approved claims and sources:** C06 → S4, S5; C07 → S4, S5, S8; C08 → S4.

**Provisional template need:** Candidate source slide **8** — contrast or
two-region composition suitable for positioning two related examples.

**Inherited-object intent, pending object IDs:**

- Keep title, background, typography, and two-region alignment.
- Rewrite inherited comparison labels and central takeaway.
- Reuse existing shapes only where they support the analogy.
- Do not convert the analogy into a dashboard, scatter chart, or scientific
  measurement.

---

### Slide 7 — Runtime retrieve-and-generate flow

**Narrative role:** Connect the prepared vector store to the complete runtime
answer path.

**Primary claim:** At runtime, the system retrieves relevant chunks, adds them
as context, and only then asks the foundation model to generate a response.

**Exact audience-visible copy:**

- Title: `At runtime, retrieve context before generating`
- Step 1: `Ask a question`
- Step 2: `Search by meaning`
- Step 3: `Retrieve relevant chunks`
- Step 4: `Add chunks as context`
- Step 5: `Generate the answer`
- Output label: `Answer + source attribution*`
- Footnote: `*In supported retrieval-and-generation flows.`

**Visual intent:** Second detailed process diagram. Use a left-to-right or
top-to-bottom flow from question through retrieval and augmentation to the
foundation-model response. The retrieved chunk must be visually distinct from
the generated answer.

**Density budget:** Five short step labels, one output label, and one footnote.
No API names or implementation detail.

**Script mapping:** `SCRIPT.md` → `Slide 7 — From question to grounded response`.

**Approved claims and sources:** C08 → S4; C09 → S1, S4, S6; C11 → S7; C12 →
S7, S11.

**Provisional template need:** Candidate source slide **11** — process layout.
Phase 7 must test whether the inherited structure supports five concise stages;
if not, select another process source or split only after timing review.

**Inherited-object intent, pending object IDs:**

- Keep inherited connector direction, title, step rhythm, and brand elements.
- Rewrite process nodes in place.
- Preserve enough separation between retrieved context and generated output.
- Handle any additional output/source placeholder through an inherited target;
  do not overlay it on top of the process.

---

### Slide 8 — AWS managed workflow mapping

**Narrative role:** Map the now-familiar generic RAG flow to Amazon Bedrock.

**Primary claim:** Amazon Bedrock Knowledge Bases manages or simplifies key RAG
steps across preparation and runtime while leaving quality decisions important.

**Exact audience-visible copy:**

- Title: `Amazon Bedrock Knowledge Bases manages key RAG steps`
- Lane 1 heading: `Prepare`
- Lane 1 flow: `Connect source data → Chunk → Create embeddings → Store vectors`
- Lane 2 heading: `Run`
- Lane 2 flow: `Retrieve relevant chunks → Generate a response → Return source attribution*`
- Main statement: `One managed workflow across preparation and runtime.`
- Footnote: `*In supported retrieval-and-generation flows.`

**Visual intent:** A compact two-lane AWS mapping: preparation above and
runtime below. Use the official product name as the containing capability, not
as a magical single box that hides every quality decision. Avoid an AWS Console
screenshot.

**Density budget:** Two lane headings, seven short flow labels, one statement,
and one footnote. No configuration, API, pricing, or Region content.

**Script mapping:** `SCRIPT.md` → `Slide 8 — Amazon Bedrock Knowledge Bases manages key RAG steps`.

**Approved claims and sources:** C10 → S4, S6; C11 → S7; C12 → S7, S11.

**Provisional template need:** Candidate source slide **12** — framework/list
composition with an inherited supporting visual region. Phase 7 should prefer a
source that can contain two lanes without adding a parallel custom layout.

**Inherited-object intent, pending object IDs:**

- Keep background, title, framework hierarchy, footer, and brand marks.
- Rewrite inherited framework text as preparation/runtime lanes.
- Replace supporting media only through an inherited frame if needed.
- Do not add unofficial AWS marks or generated product UI.

---

### Slide 9 — Vector-store alternatives

**Narrative role:** Place the two agenda-relevant AWS services in the same
architectural role.

**Primary claim:** Amazon OpenSearch Serverless and Amazon Aurora
PostgreSQL-Compatible Edition are alternative vector-store choices in this
simplified architecture.

**Exact audience-visible copy:**

- Title: `One vector-store role, two AWS choices`
- Center label: `Vector store`
- Center detail: `Store and retrieve embeddings`
- Option 1: `Amazon OpenSearch Serverless`
- Option 2: `Amazon Aurora PostgreSQL-Compatible Edition`
- Closing line: `Choose one option for this architecture — they are alternatives, not sequential steps.`

**Visual intent:** One central vector-store role branching to two equal options.
Do not use a feature-comparison table, winner badge, sequence arrow, or implied
recommendation.

**Density budget:** One role, two service names, and one clarification sentence.
No selection criteria.

**Script mapping:** `SCRIPT.md` → `Slide 9 — One vector-store role, multiple AWS choices`.

**Approved claims and sources:** C13 → S8, S9; C14 → S9, S10, S14; C15 → S8,
S9, S10.

**Provisional template need:** Candidate source slide **8** — equal two-option
composition. Phase 7 must confirm the inherited reading order does not imply a
before/after sequence.

**Inherited-object intent, pending object IDs:**

- Keep equal visual weight, title, brand chrome, and typography.
- Rewrite both option regions and the shared role label.
- Use authentic AWS service identity only if official source assets are placed
  through inherited media targets.
- Delete any comparison verdict or directional sample content.

---

### Slide 10 — Benefits and limitations

**Narrative role:** Set realistic expectations before the closing synthesis.

**Primary claim:** RAG can improve grounding and traceability, but final quality
still depends on data, retrieval, and generation; it does not guarantee correct
answers.

**Exact audience-visible copy:**

- Title: `Better grounding is not a correctness guarantee`
- Left heading: `RAG can help`
- Left item 1: `Use private or updated data`
- Left item 2: `Retrieve relevant context`
- Left item 3: `Improve traceability with sources*`
- Right heading: `RAG still depends on`
- Right item 1: `Source quality and freshness`
- Right item 2: `Chunking and retrieval quality`
- Right item 3: `Generated-response quality`
- Closing line: `RAG can reduce hallucination risk. It does not guarantee correctness.`
- Footnote: `*In supported retrieval-and-generation flows.`

**Visual intent:** Balanced benefit-versus-dependency composition. Neither side
should dominate. Use a restrained contrast, not green “correct” versus red
“wrong.”

**Density budget:** Two headings, three short items per side, one closing line,
and one footnote. Keep explanations in the Vietnamese script.

**Script mapping:** `SCRIPT.md` → `Slide 10 — Better grounding is not a correctness guarantee`.

**Approved claims and sources:** C12 → S7, S11; C16 → S11, S13, S15; C17 →
S13; C18 → S2, S6.

**Provisional template need:** Candidate source slide **6** — balanced
comparison layout.

**Inherited-object intent, pending object IDs:**

- Keep title, two-column balance, typography, brand elements, and footer.
- Rewrite both inherited comparison regions and the closing statement.
- Replace supporting images only if an inherited frame remains necessary.
- Remove sample verdicts or metrics; no fabricated numbers.

---

### Slide 11 — Synthesis and handoff

**Narrative role:** Resolve the opening knowledge gap, reinforce three durable
ideas, and hand off cleanly to the next team section.

**Primary claim:** RAG adds the right external context before generation;
Amazon Bedrock Knowledge Bases simplifies key steps, but quality still matters.

**Exact audience-visible copy:**

- Title: `Three things to remember`
- Takeaway 1 heading: `No retraining required`
- Takeaway 1 detail: `Use external knowledge as context.`
- Takeaway 2 heading: `Retrieve first, generate second`
- Takeaway 2 detail: `Find relevant context before the response.`
- Takeaway 3 heading: `Managed workflow, quality still matters`
- Takeaway 3 detail: `Amazon Bedrock Knowledge Bases simplifies key steps.`
- Closing line: `Right context first. Better-grounded response next.`

**Visual intent:** Three inherited takeaway regions with equal hierarchy and a
single closing line. No thank-you, presenter contact, Q&A invitation, or Kahoot
reference.

**Density budget:** Three headings, three one-sentence details, and one closing
line.

**Script mapping:** `SCRIPT.md` → `Slide 11 — Three things to remember`.

**Approved claims and sources:** C02 → S1, S2; C03 → S1, S4; C10 → S4, S6;
C16 → S11, S13, S15.

**Provisional template need:** Candidate source slide **15** — three-key-
takeaways composition.

**Inherited-object intent, pending object IDs:**

- Keep the three-card hierarchy, title, background, brand marks, and footer.
- Rewrite each inherited takeaway heading/detail in place.
- Rewrite or delete the inherited closing element only if explicitly mapped.
- Do not add independent ending or Q&A slides.

## 5. Slide-to-Script and Claim Coverage Matrix

| Slide | Script section | Claim IDs | Source IDs |
|---:|---|---|---|
| 1 | Slide 1 — RAG with Amazon Bedrock | Preview only | None required |
| 2 | Slide 2 — The model can be powerful and still miss the answer | C01 | S1, S3 |
| 3 | Slide 3 — Retrieve first, generate second | C02, C03, C04 | S1, S2, S4, S6, S7 |
| 4 | Slide 4 — Cloud Mastery Knowledge Assistant | C01, C02, C04 | S1, S2, S3, S6, S7; `AGENDA.md` |
| 5 | Slide 5 — Prepare the knowledge before asking questions | C05, C06, C07, C18 | S2, S4, S5, S6, S8 |
| 6 | Slide 6 — A map of meaning | C06, C07, C08 | S4, S5, S8 |
| 7 | Slide 7 — From question to grounded response | C08, C09, C11, C12 | S1, S4, S6, S7, S11 |
| 8 | Slide 8 — Amazon Bedrock Knowledge Bases manages key RAG steps | C10, C11, C12 | S4, S6, S7, S11 |
| 9 | Slide 9 — One vector-store role, multiple AWS choices | C13, C14, C15 | S8, S9, S10, S14 |
| 10 | Slide 10 — Better grounding is not a correctness guarantee | C12, C16, C17, C18 | S2, S6, S7, S11, S13, S15 |
| 11 | Slide 11 — Three things to remember | C02, C03, C10, C16 | S1, S2, S4, S6, S11, S13, S15 |

Every claim ID above resolves to the approved claim registry in
`KNOWLEDGE.md`. No new technical AWS claim is introduced by this specification.

## 6. Official AWS Source Reference

The canonical source descriptions, authority labels, supported claims, and
safe-wording notes live in `KNOWLEDGE.md` §14–§17. URLs used by this slide
specification are:

| ID | Official AWS source |
|---|---|
| S1 | https://docs.aws.amazon.com/prescriptive-guidance/latest/agentic-ai-serverless/grounding-and-rag.html |
| S2 | https://aws.amazon.com/what-is/retrieval-augmented-generation/ |
| S3 | https://docs.aws.amazon.com/prescriptive-guidance/latest/retrieval-augmented-generation-options/introduction.html |
| S4 | https://docs.aws.amazon.com/bedrock/latest/userguide/kb-how-it-works.html |
| S5 | https://docs.aws.amazon.com/bedrock/latest/userguide/kb-chunking.html |
| S6 | https://docs.aws.amazon.com/prescriptive-guidance/latest/retrieval-augmented-generation-options/rag-fully-managed-bedrock.html |
| S7 | https://docs.aws.amazon.com/bedrock/latest/userguide/kb-how-retrieval.html |
| S8 | https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base-setup.html |
| S9 | https://docs.aws.amazon.com/prescriptive-guidance/latest/retrieval-augmented-generation-options/rag-fully-managed-bedrock.html |
| S10 | https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/AuroraPostgreSQL.VectorDB.html |
| S11 | https://aws.amazon.com/bedrock/faqs/ |
| S13 | https://docs.aws.amazon.com/bedrock/latest/userguide/evaluation-kb.html |
| S14 | https://aws.amazon.com/rds/aurora/faqs/ |
| S15 | https://docs.aws.amazon.com/prescriptive-guidance/latest/strategy-data-considerations-gen-ai/security.html |

S12 is retained in the canonical knowledge registry but is not required to
support exact audience-visible copy in this 11-slide specification.

## 7. Phase 7 Template-Mapping Contract

Before PowerPoint authoring, Phase 7 must:

1. Inspect all 16 slides in `Slide/Template.pptx` using the Presentations
   template-following workflow.
2. Validate or replace every provisional candidate source slide above.
3. Record one final source slide for every output slide; source slides may be
   reused.
4. Identify inherited object IDs and classify each as `keep`, `rewrite`,
   `replace`, or `delete`.
5. Ensure every audience-visible string has an inherited target or document a
   bounded, validated insertion only when the template contract permits it.
6. Preserve font family, size, weight, spacing, alignment, master, background,
   logo, footer, and brand chrome.
7. Confirm that Slides 5 and 7 are the only full process diagrams.
8. Confirm that Slide 9 reads as alternatives, not a sequence.
9. Confirm no slide requires text shrinking below the inherited hierarchy.
10. Publish the validated output-to-source map before creating a starter deck.

## 8. Phase 6 Acceptance Criteria

Phase 6 is complete when:

- All 11 planned slides have exact English audience-visible copy.
- Every slide has one narrative role, one primary teaching job/claim, visual
  intent, density budget, and script mapping.
- All technical claims map to approved C01–C18 claim IDs and official source
  IDs from `KNOWLEDGE.md`.
- No new unverified AWS capability, metric, recommendation, or guarantee is
  introduced.
- Slide copy distinguishes source data, retrieved context, and generated output.
- RAG is never described as retraining the foundation model.
- OpenSearch Serverless and Aurora PostgreSQL are shown as alternatives.
- Hallucination wording says `reduce risk` and never claims prevention or elimination.
- Source attribution is qualified as available in supported flows.
- Freshness is qualified by synchronization of changed content.
- Slide text is English; Vietnamese explanation remains in `SCRIPT.md`.
- No audience-facing timing, production notes, Kahoot, demo, code, pricing,
  presenter biography, general Q&A, or generic thank-you content appears.
- Every slide has a provisional template-layout candidate, with final mapping
  explicitly deferred to Phase 7.
- `Slide/Template.pptx` remains unchanged and no output PPTX has been authored.
