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

Phase 7 inspected all 16 template slides and validated the source slide and
inherited edit targets for every output slide. The accepted map is recorded in
§9 and in the external scratch `template-frame-map.json`. PowerPoint authoring
must use the prepared duplicated-source starter deck and this accepted map.

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

**Validated template source:** Source slide **1** — cover-gradient composition,
adapted as a merge-safe section divider.

**Validated inherited-object plan:**

- Keep background, brand marks, master objects, palette, and typography.
- Rewrite title and subtitle placeholders in place.
- Delete presenter/event metadata only if Phase 7 classifies those inherited
  objects as editable sample placeholders.

Exact targets: rewrite `sh/ihkbixcj`, `sh/547294r6`; delete
`sh/7qp4be9c`, `sh/432tk7up`, `sh/r6tsv2t0`.

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

**Validated template source:** Source slide **3** — claim, tag, callout, and
inherited image composition.

**Validated inherited-object plan:**

- Keep brand chrome, title hierarchy, footer, and image crop conventions.
- Rewrite title and body text in place.
- Replace the sample image only through its inherited media frame.
- Remove unused sample labels only after Phase 7 identifies them explicitly.

Exact targets: rewrite `sh/0fq9gri9`, `sh/n2l4fq98`, `sh/m1c3mlsn`,
`sh/v6l4jq94`, `sh/x8nml0ra`, `sh/ja54na9g`, `sh/03ix43e5`; delete
`sh/i9w3u58v`, `sh/e10f2twf`, `sh/14ryd8fq`; replace `im/sretwbud`.

---

### Slide 3 — The core RAG mental model

**Narrative role:** Give the beginner definition that the rest of the module
will unpack.

**Primary claim:** RAG retrieves relevant external context before the foundation
model generates a response; it does not retrain the model.

**Exact audience-visible copy:**

- Title: `RAG keeps three things separate`
- Subtitle: `Retrieve relevant context before the model generates a response.`
- Stage number: `1`
- Stage 1 heading: `SOURCE DATA`
- Stage 1 detail: `External knowledge outside the model`
- Stage number: `2`
- Stage 2 heading: `RETRIEVED CONTEXT`
- Stage 2 detail: `Relevant passages added to the prompt`
- Stage number: `3`
- Stage 3 heading: `GENERATED RESPONSE`
- Stage 3 detail: `The model's answer`
- Footer statement: `Use external knowledge without retraining the model.`

**Visual intent:** A compact left-to-right three-object conceptual map that
distinguishes stored source material, selected context, and generated output.
The inherited connectors show how information moves without presenting this as
the detailed runtime process.

**Density budget:** Three headings, three short details, one subtitle, and one
footer statement. No prose paragraph.

**Script mapping:** `SCRIPT.md` → `Slide 3 — Retrieve first, generate second`.

**Approved claims and sources:** C02 → S1, S2; C03 → S1, S4; C04 → S1, S6, S7.

**Validated template source:** Source slide **9** — three connected inherited
stages, supporting image frame, and conclusion bar.

**Validated inherited-object plan:** Keep connectors, node geometry, number
labels, background, footer structure, and brand objects. Rewrite title,
subtitle, three headings, three bodies, slide number, and conclusion; replace
the inherited image inside its existing frame.

Exact targets: rewrite `sh/vi5s3a98`, `sh/1cfmhgne`, `sh/0b65obm9`,
`sh/hcji5o7a`, `sh/cnu1kzyd`, `sh/wba1cjqp`, `sh/bml0buxs`,
`sh/va103ep4`, `sh/98ji147e`, `sh/ml8j6p8n`; replace `im/lsrqloba`.

---

### Slide 4 — Cloud Mastery Knowledge Assistant

**Narrative role:** Make the abstract flow concrete without turning the talk
into a demo.

**Primary claim:** The assistant can answer an event question by grounding the
response in a retrieved agenda passage rather than relying on model memory.

**Exact audience-visible copy:**

- Title: `Ground answers in Cloud Mastery documents`
- Stage number: `1`
- Label: `Question`
- Question: `How long is the RAG session?`
- Stage number: `2`
- Label: `Retrieved agenda passage`
- Passage: `RAG with Bedrock — 20 minutes`
- Stage number: `3`
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

**Validated template source:** Source slide **9** — three connected states. The
provisional source slide 14 was rejected because its full-bleed image and four
overlays would let the supporting use case dominate the conceptual narrative.

**Validated inherited-object plan:**

- Keep background, title, brand chrome, and inherited content alignment.
- Rewrite existing overlay text boxes as the three scenario states.
- Replace any irrelevant sample background/media only through inherited media
  targets.
- Avoid adding chat bubbles or simulated product UI.

Exact targets: rewrite `sh/vi5s3a98`, `sh/1cfmhgne`, `sh/hcji5o7a`,
`sh/cnu1kzyd`, `sh/wba1cjqp`, `sh/bml0buxs`, `sh/va103ep4`,
`sh/98ji147e`, `sh/ml8j6p8n`; delete `sh/0b65obm9`; replace
`im/lsrqloba`.

---

### Slide 5 — Knowledge preparation

**Narrative role:** Explain what must happen before the first user question.

**Primary claim:** Source documents are divided into chunks, represented as
embeddings, and indexed in a vector store; changed content must be synchronized.

**Exact audience-visible copy:**

- Title: `Prepare knowledge before the first question`
- Step number: `1`
- Step 1: `Documents`
- Step 1 detail: `Agenda and event materials`
- Step number: `2`
- Step 2: `Chunks`
- Step 2 detail: `Smaller passages`
- Step number: `3`
- Step 3: `Embeddings`
- Step 3 detail: `Numerical representations`
- Step number: `4`
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

**Validated template source:** Source slide **11** — four-step process inside an
inherited dark rounded container.

**Validated inherited-object plan:**

- Keep process connectors, node geometry, title, and brand elements.
- Rewrite all four inherited nodes and their descriptions.
- Use inherited icon/media slots only if they remain legible and accurate.
- Do not add service logos; this slide explains generic concepts.

Exact targets: rewrite `sh/6hgv65cn`, `sh/98rytw72`, `sh/o7ih0r6h`,
`sh/zaxs3yhc`, `sh/tsnip0ny`, `sh/65wzelo7`, `sh/j2lgjq5w`,
`sh/y1czalob`.

---

### Slide 6 — Embeddings and semantic similarity

**Narrative role:** Explain why retrieval can find relevant meaning even when
the question and passage use different words.

**Primary claim:** Embeddings are numerical representations that allow a vector
store to retrieve content by semantic similarity.

**Exact audience-visible copy:**

- Title: `Embeddings create a map of meaning`
- Subtitle: `Embeddings map meaning. Vector stores find nearby content.`
- Example A label: `Question`
- Example A: `How long is the RAG session?`
- Example B label: `Agenda passage`
- Example B: `RAG with Bedrock — 20 minutes`
- Main statement: `Similar meaning can be close — even when the words differ.`

**Visual intent:** A simple “map of meaning” analogy with the question and
agenda passage positioned close together. Other faint points may suggest
unrelated topics, but do not add axes, equations, scores, or fake precision.

**Density budget:** Two short examples, one subtitle, and one statement. No
bullet list, paragraph, equation, or numerical similarity score.

**Script mapping:** `SCRIPT.md` → `Slide 6 — A map of meaning`.

**Approved claims and sources:** C06 → S4, S5; C07 → S4, S5, S8; C08 → S4.

**Validated template source:** Source slide **8** — inherited image frame, two
equal example cards, and conclusion bar.

**Validated inherited-object plan:**

- Keep title, background, typography, and two-region alignment.
- Rewrite inherited comparison labels and central takeaway.
- Reuse existing shapes only where they support the analogy.
- Do not convert the analogy into a dashboard, scatter chart, or scientific
  measurement.

Exact targets: rewrite `sh/8r2lo7mt`, `sh/g72x4zyd`, `sh/ri9g7uhw`,
`sh/sjix0zy1`, `sh/je9g3ahk`, `sh/ehgvihwr`, `sh/zipwbmdc`,
`sh/lgbepgvm`; replace `im/8ni54bu9`.

---

### Slide 7 — Runtime retrieve-and-generate flow

**Narrative role:** Connect the prepared vector store to the complete runtime
answer path.

**Primary claim:** At runtime, the system retrieves relevant chunks, adds them
as context, and only then asks the foundation model to generate a response.

**Exact audience-visible copy:**

- Title: `Retrieve context before generating`
- Subtitle: `Question → Retrieval → Context → Response`
- Step number: `1`
- Step 1 heading: `Ask a question`
- Step 1 detail: `Search by meaning`
- Step number: `2`
- Step 2 heading: `Retrieve`
- Step 2 detail: `Relevant chunks`
- Step number: `3`
- Step 3 heading: `Add context`
- Step 3 detail: `Chunks + question`
- Step number: `4`
- Step 4 heading: `Generate`
- Step 4 detail: `Foundation model answer`
- Output label: `Answer + source attribution*`
- Footnote: `*In supported retrieval-and-generation flows.`

**Visual intent:** Second detailed process diagram. Use the four inherited
left-to-right nodes from question/search through retrieval and augmentation to
the foundation-model response. The retrieved chunk remains conceptually
distinct from the generated answer.

**Density budget:** Four nodes with a heading/detail pair, one output label, and
one footnote. No API names or implementation detail.

**Script mapping:** `SCRIPT.md` → `Slide 7 — From question to grounded response`.

**Approved claims and sources:** C08 → S4; C09 → S1, S4, S6; C11 → S7; C12 →
S7, S11.

**Validated template source:** Source slide **11** — four-step inherited process.
Question and semantic search are combined inside node 1 because the source
layout has exactly four nodes.

**Validated inherited-object plan:**

- Keep inherited connector direction, title, step rhythm, and brand elements.
- Rewrite process nodes in place.
- Preserve enough separation between retrieved context and generated output.
- Handle any additional output/source placeholder through an inherited target;
  do not overlay it on top of the process.

Exact targets: rewrite `sh/6hgv65cn`, `sh/98rytw72`, `sh/o7ih0r6h`,
`sh/zaxs3yhc`, `sh/tsnip0ny`, `sh/65wzelo7`, `sh/j2lgjq5w`,
`sh/y1czalob`.

---

### Slide 8 — AWS managed workflow mapping

**Narrative role:** Map the now-familiar generic RAG flow to Amazon Bedrock.

**Primary claim:** Amazon Bedrock Knowledge Bases manages or simplifies key RAG
steps across preparation and runtime while leaving quality decisions important.

**Exact audience-visible copy:**

- Title: `Amazon Bedrock Knowledge Bases simplifies RAG`
- Subtitle: `One managed workflow across preparation and runtime.`
- Capability 1 label: `Prepare`
- Capability 1 detail: `Connect, chunk, embed, and store`
- Capability 2 label: `Retrieve`
- Capability 2 detail: `Find relevant source chunks`
- Capability 3 label: `Generate`
- Capability 3 detail: `Create a response from retrieved context`
- Capability 4 label: `Attribute`
- Capability 4 detail: `Return sources in supported flows*`
- Footer: `*Supported retrieval-and-generation flows. Quality decisions still matter.`

**Visual intent:** Four inherited capability rows map the generic RAG model to
Amazon Bedrock Knowledge Bases. The inherited image frame contains a compact,
accurate AWS capability visual rather than a process overlay or Console
screenshot.

**Density budget:** Four short label/detail pairs, one subtitle, and one footer.
No configuration, API, pricing, or Region content.

**Script mapping:** `SCRIPT.md` → `Slide 8 — Amazon Bedrock Knowledge Bases manages key RAG steps`.

**Approved claims and sources:** C10 → S4, S6; C11 → S7; C12 → S7, S11.

**Validated template source:** Source slide **12** — four inherited framework
rows, image frame, and conclusion box. The provisional two-lane wording was
reframed to fit the inherited structure directly.

**Validated inherited-object plan:**

- Keep background, title, framework hierarchy, footer, and brand marks.
- Rewrite inherited framework text as preparation/runtime lanes.
- Replace supporting media only through an inherited frame if needed.
- Do not add unofficial AWS marks or generated product UI.

Exact targets: rewrite `sh/4nupgvmx`, `sh/wvupgz6t`, `sh/xw3q94ne`,
`sh/bulo7u58`, `sh/orapcf6h`, `sh/mps7a5or`, `sh/nq1o3a5w`,
`sh/1oj61kn6`, `sh/hkbm5wzu`, `sh/fit436ho`, `sh/uh0na1g3`,
`sh/7u94zmhs`; replace `im/czudcjap`.

---

### Slide 9 — Vector-store alternatives

**Narrative role:** Place the two agenda-relevant AWS services in the same
architectural role.

**Primary claim:** Amazon OpenSearch Serverless and Amazon Aurora
PostgreSQL-Compatible Edition are alternative vector-store choices in this
simplified architecture.

**Exact audience-visible copy:**

- Title: `One vector-store role, two AWS choices`
- Subtitle: `Choose one vector-store option for this architecture.`
- Card 1 heading: `VECTOR STORE`
- Card 1 detail: `Store and retrieve embeddings`
- Card 2: `AMAZON OPENSEARCH SERVERLESS`
- Card 3: `AMAZON AURORA POSTGRESQL-COMPATIBLE EDITION`
- Closing line: `Choose one option for this architecture — they are alternatives, not sequential steps.`

**Visual intent:** Three equal inherited cards: one names the architectural
role, and two name the AWS alternatives. Number circles are removed so the
composition does not imply sequence, ranking, or a winner.

**Density budget:** One short role/detail, two official service names, one
subtitle, and one clarification sentence. No selection criteria.

**Script mapping:** `SCRIPT.md` → `Slide 9 — One vector-store role, multiple AWS choices`.

**Approved claims and sources:** C13 → S8, S9; C14 → S9, S10, S14; C15 → S8,
S9, S10.

**Validated template source:** Source slide **15** — three equal inherited cards
and conclusion bar. Provisional source slide 8 was rejected because its
pink/green semantics imply a better/worse comparison.

**Validated inherited-object plan:**

- Keep equal visual weight, title, brand chrome, and typography.
- Rewrite both option regions and the shared role label.
- Use authentic AWS service identity only if official source assets are placed
  through inherited media targets.
- Delete any comparison verdict or directional sample content.

Exact targets: rewrite `sh/7md8jqpo`, `sh/t87ml0ji`, `sh/s7y5sv2x`,
`sh/gjax03m9`; delete `sh/m9c3e1kn`, `sh/wrm9kvep`, `sh/vqdsrqx4`,
`sh/4vm9ovel`, `sh/judsvqxg`, `sh/0z29cbyh`; rewrite and reposition
`sh/hsvat0fa`, `sh/5wvax0f6`, `sh/l0bqlgf2` within their inherited cards.

---

### Slide 10 — Benefits and limitations

**Narrative role:** Set realistic expectations before the closing synthesis.

**Primary claim:** RAG can improve grounding and traceability, but final quality
still depends on data, retrieval, and generation; it does not guarantee correct
answers.

**Exact audience-visible copy:**

- Title: `Better grounding is not a correctness guarantee`
- Subtitle: `Grounded answers still depend on the full quality chain.`
- Left heading: `RAG still depends on`
- Left item 1: `Source quality and freshness`
- Left item 2: `Chunking and retrieval quality`
- Left item 3: `Generated-response quality`
- Right heading: `RAG can help`
- Right item 1: `Use private or updated data`
- Right item 2: `Retrieve relevant context`
- Right item 3: `Improve traceability with sources*`
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

**Validated template source:** Source slide **8** — inherited image frame, two
balanced contrast cards, and conclusion bar.

**Validated inherited-object plan:**

- Keep title, two-column balance, typography, brand elements, and footer.
- Rewrite both inherited comparison regions and the closing statement.
- Replace supporting images only if an inherited frame remains necessary.
- Remove sample verdicts or metrics; no fabricated numbers.

Exact targets: rewrite `sh/8r2lo7mt`, `sh/g72x4zyd`, `sh/ri9g7uhw`,
`sh/sjix0zy1`, `sh/je9g3ahk`, `sh/ehgvihwr`, `sh/zipwbmdc`,
`sh/lgbepgvm`; replace `im/8ni54bu9`.

---

### Slide 11 — Synthesis and handoff

**Narrative role:** Resolve the opening knowledge gap, reinforce three durable
ideas, and hand off cleanly to the next team section.

**Primary claim:** RAG adds the right external context before generation;
Amazon Bedrock Knowledge Bases simplifies key steps, but quality still matters.

**Exact audience-visible copy:**

- Title: `Three things to remember`
- Subtitle: `The RAG mental model in three ideas.`
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

**Validated template source:** Source slide **15** — three numbered inherited
takeaway cards and conclusion bar.

**Validated inherited-object plan:**

- Keep the three-card hierarchy, title, background, brand marks, and footer.
- Rewrite each inherited takeaway heading/detail in place.
- Rewrite or delete the inherited closing element only if explicitly mapped.
- Do not add independent ending or Q&A slides.

Exact targets: rewrite `sh/7md8jqpo`, `sh/t87ml0ji`, `sh/s7y5sv2x`,
`sh/hsvat0fa`, `sh/5wvax0f6`, `sh/l0bqlgf2`, `sh/gjax03m9`.

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

## 7. Phase 7 Validated Template Map

The Presentations template-following audit inspected all 16 source slides and
accepted this output-to-source mapping:

| Output slide | Source slide | Inherited pattern | Edit targets |
|---:|---:|---|---:|
| 1 | 1 | Cover gradient / section divider | 5 |
| 2 | 3 | Problem claim, tags, callout, image | 11 |
| 3 | 9 | Three connected conceptual states | 11 |
| 4 | 9 | Three connected use-case states | 11 |
| 5 | 11 | Four-step preparation process | 8 |
| 6 | 8 | Image plus two semantic examples | 9 |
| 7 | 11 | Four-step runtime process | 8 |
| 8 | 12 | Four-row AWS capability framework | 13 |
| 9 | 15 | Three equal vector-store role/option cards | 13 |
| 10 | 8 | Benefit/dependency comparison | 9 |
| 11 | 15 | Three numbered takeaways | 7 |

Validation evidence:

- All 16 source slides were reviewed at full size.
- The frame-map validator passed with zero issues.
- The map contains 11 output slides and 105 inherited edit targets.
- The duplicated-source starter deck contains 11 slides in the expected order.
- Source slides 2, 4, 5, 6, 7, 10, 13, 14, and 16 are intentionally omitted.
- Slides 5 and 7 remain the only full process diagrams.
- Slide 9 removes inherited number circles so the service choices do not read
  as a sequence or ranking.
- No new card, panel, table, chart, or parallel theme layout is permitted.
- Font family, size, weight, spacing, master, background, footer, logo, and
  brand chrome remain inherited from the mapped source slide.

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
- Every slide now has a validated source slide and exact inherited-object plan.
- `Slide/Template.pptx` remains unchanged and no output PPTX has been authored.
