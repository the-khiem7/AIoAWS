# RAG with Amazon Bedrock — Presentation Script

## Document Status

- Phase 4 status: narrative blueprint and timing plan.
- Phase 5 status: full Vietnamese talk tracks and concise speaker notes are not
  yet authored.
- Audience-visible English slide copy is not defined here; that belongs in
  `SLIDE-CONTENT.md` during Phase 6.
- All technical claims must use approved claim IDs from `KNOWLEDGE.md`.

## 1. Communication Job

> By the end of the segment, a newcomer should be able to explain why RAG is
> useful, describe its retrieve-then-generate flow, and recognize how Amazon
> Bedrock Knowledge Bases and a vector store support that flow.

Vietnamese delivery intent:

> Sau phần trình bày, người mới phải có thể giải thích vì sao cần RAG, mô tả
> được luồng “retrieve trước, generate sau”, và nhận ra Amazon Bedrock Knowledge
> Bases cùng vector store nằm ở đâu trong luồng đó.

## 2. Central Takeaway

> RAG does not retrain the foundation model. It retrieves relevant information
> and supplies that information as context before the model generates an
> answer.

Vietnamese delivery line to preserve:

> RAG không huấn luyện lại foundation model. RAG tìm thông tin liên quan, đưa
> thông tin đó vào context, rồi model mới tạo câu trả lời.

Required qualification:

> RAG can reduce hallucination risk and improve grounding, but it does not
> guarantee correctness.

## 3. Narrative Arc

The deck uses a cumulative technical-learning arc:

1. **Section entry** — mark the start of the team's RAG module.
2. **Information gap** — a capable model can still lack the needed private or
   recent information.
3. **Core answer** — RAG retrieves context before generation; it does not
   retrain the model.
4. **Concrete scenario** — the Cloud Mastery assistant makes the abstract
   problem tangible.
5. **Preparation flow** — documents become retrievable chunks and embeddings.
6. **Retrieval intuition** — embeddings and vector stores enable semantic
   comparison.
7. **Runtime flow** — question → retrieval → context → generation.
8. **AWS mapping** — Amazon Bedrock Knowledge Bases manages or simplifies key
   steps.
9. **Architecture choice** — OpenSearch Serverless and Aurora PostgreSQL occupy
   the vector-store slot as alternatives.
10. **Responsible expectation** — RAG improves grounding and traceability but
    still requires good data, retrieval, evaluation, and careful claims.
11. **Synthesis and handoff** — resolve the opening tension and transfer cleanly
    to the next team section.

This is not a product catalogue, implementation tutorial, or sales pitch. Each
beat answers a question raised by the previous beat.

## 4. Timing Budget

Target planned delivery: **17 minutes 40 seconds**.

Reserved safety margin: **2 minutes 20 seconds** within the assigned 20 minutes.

The safety margin covers natural pauses, audience reaction, slower explanation
of embeddings, and team transitions. It is not available for adding demo or
Kahoot content.

| Beat | Working role—not final slide title | Time | Running total |
|---:|---|---:|---:|
| 1 | Section divider | 0:20 | 0:20 |
| 2 | Establish the information gap | 1:30 | 1:50 |
| 3 | Define RAG and correct the retraining misconception | 1:40 | 3:30 |
| 4 | Introduce the Cloud Mastery Knowledge Assistant | 1:30 | 5:00 |
| 5 | Explain preparation/ingestion | 1:55 | 6:55 |
| 6 | Build intuition for embeddings and vector stores | 2:05 | 9:00 |
| 7 | Explain runtime retrieval and generation | 2:10 | 11:10 |
| 8 | Map the generic flow to Amazon Bedrock Knowledge Bases | 1:55 | 13:05 |
| 9 | Place OpenSearch Serverless and Aurora in the architecture | 1:25 | 14:30 |
| 10 | Balance benefits with limitations | 1:45 | 16:15 |
| 11 | Resolve the story and hand off | 1:25 | 17:40 |

The provisional hypothesis is one slide per beat, for 11 module slides including
the section divider. Phase 6 may merge or split beats when template fit demands
it, but it must preserve narrative jobs, learning order, and total timing.

## 5. Beat-by-Beat Narrative Blueprint

### Beat 1 — Section divider

- Duration: 0:20.
- Narrative job: signal the start of the RAG module without restarting the whole
  event presentation.
- Audience question answered: “What topic are we entering now?”
- Required visible title later: **RAG with Amazon Bedrock**.
- Claim IDs: none; this is navigation.
- Use-case role: none.
- Transition in: inherit the earlier Amazon Bedrock discussion.
- Transition out intent: move immediately from the model's capability to its
  information boundary.
- Density rule: title only or title plus one short subtitle if the inherited
  template requires it.

### Beat 2 — Establish the information gap

- Duration: 1:30.
- Narrative job: create the reason RAG is needed.
- Audience question answered: “If foundation models are powerful, what is still
  missing?”
- Primary claim: a foundation model may lack private, domain-specific, or recent
  information.
- Claim IDs: C01.
- Use-case role: briefly ask whether the model already knows the private Cloud
  Mastery agenda and latest event updates.
- Evidence-to-meaning move: the issue is sometimes missing context, not a weak
  model.
- Transition out intent: ask how an application can provide the missing
  information without retraining the model.
- Misconception to avoid: “The model is bad because it does not know our private
  documents.”

### Beat 3 — Define RAG and correct the retraining misconception

- Duration: 1:40.
- Narrative job: provide the central mental model before introducing technical
  components.
- Audience question answered: “What does RAG add?”
- Primary claim: retrieve relevant information, add it as context, then
  generate.
- Claim IDs: C02, C03, C04.
- Use-case role: none beyond a one-sentence connection.
- Required distinction:
  - source data;
  - retrieved context; and
  - generated response.
- Required correction: RAG does not retrain the foundation model.
- Transition out intent: make the model concrete through one event-related
  question.
- Audience checkpoint: listeners should be able to repeat “retrieve first,
  generate second.”

### Beat 4 — Introduce the Cloud Mastery Knowledge Assistant

- Duration: 1:30.
- Narrative job: turn the abstract definition into one relatable scenario.
- Audience question answered: “What would this look like in our event?”
- Scenario: an attendee asks about the agenda or workshop documents; the
  assistant retrieves the relevant passage before the model answers.
- Claim IDs: C01, C02, C04.
- Use-case role: establish the example that later beats revisit.
- Evidence-to-meaning move: the agenda stays external to the model, yet the
  model can use it at request time.
- Transition out intent: ask how the documents become searchable by meaning.
- Guardrail: do not imply that this assistant has been built, tested, or
  measured.

### Beat 5 — Explain preparation/ingestion

- Duration: 1:55.
- Narrative job: separate knowledge preparation from runtime questions.
- Audience question answered: “How does a document collection become
  retrievable?”
- Flow:
  1. source documents;
  2. split into chunks;
  3. create embeddings;
  4. write to a vector index/store;
  5. retain connection to source content.
- Claim IDs: C05, C06, C07, C18.
- Use-case role: Cloud Mastery agenda and workshop documents move through the
  preparation flow.
- Required nuance: updated content must be synchronized or reprocessed; RAG does
  not guarantee automatic real-time freshness.
- Transition out intent: pause on the two unfamiliar terms—embedding and vector
  store—and explain them intuitively.
- Visual hypothesis: one simple left-to-right process; no implementation detail.

### Beat 6 — Build intuition for embeddings and vector stores

- Duration: 2:05.
- Narrative job: give newcomers enough intuition to understand semantic
  retrieval.
- Audience question answered: “How can the system compare a question with
  passages by meaning?”
- Claim IDs: C06, C07, C08.
- Embedding explanation: numerical representation used for comparison.
- Teaching analogy: coordinates on a “map of meaning.” Label this as an analogy,
  not a literal UI or AWS architecture.
- Vector-store explanation: searchable index that stores embeddings and finds
  similar content.
- Required correction: the vector store retrieves content; it does not generate
  prose.
- Use-case role: “How long is the RAG session?” can match the agenda passage even
  if the words are not identical.
- Transition out intent: now run the attendee's question through the complete
  runtime flow.
- Density risk: do not combine embedding mathematics, dimensions, model lists,
  or similarity algorithms.

### Beat 7 — Explain runtime retrieval and generation

- Duration: 2:10.
- Narrative job: complete the end-to-end RAG mental model.
- Audience question answered: “What happens when the user asks a question?”
- Flow:
  1. user question;
  2. query representation;
  3. similarity retrieval;
  4. relevant chunks;
  5. augmented context;
  6. foundation-model response;
  7. source references when supported/configured.
- Claim IDs: C08, C09, C11, C12.
- Use-case role: retrieve the Cloud Mastery agenda chunk and use it to answer the
  attendee.
- Required distinction: retrieval and generation remain conceptually separate
  even when a managed AWS operation combines them.
- Transition out intent: ask which parts teams must build themselves and which
  parts Amazon Bedrock can manage.
- Audience checkpoint: listeners can narrate the flow from question to response.

### Beat 8 — Map the generic flow to Amazon Bedrock Knowledge Bases

- Duration: 1:55.
- Narrative job: connect the already-understood generic model to AWS.
- Audience question answered: “Where does Amazon Bedrock fit?”
- Primary claim: Amazon Bedrock Knowledge Bases can manage or simplify important
  RAG steps from content preparation through retrieval and response support.
- Claim IDs: C10, C11, C12.
- Use-case role: map the event documents, vector store, retrieval, and response
  to the managed AWS capability.
- Required qualification: say “manages or simplifies key steps”; do not claim
  that all data and quality decisions disappear.
- Transition out intent: isolate the vector-store slot and explain the two AWS
  names listed in the agenda.
- Scope guardrail: do not show APIs, console steps, security settings, or code.

### Beat 9 — Place OpenSearch Serverless and Aurora in the architecture

- Duration: 1:25.
- Narrative job: prevent the agenda from being misread as a sequential service
  chain.
- Audience question answered: “Are OpenSearch and Aurora both required?”
- Primary claim: Amazon OpenSearch Serverless and Amazon Aurora
  PostgreSQL-Compatible Edition are agenda-relevant alternatives for the
  vector-store role.
- Claim IDs: C13, C14, C15.
- Use-case role: the Cloud Mastery assistant needs one appropriate vector-store
  choice in the simplified architecture, not both in sequence.
- Required visual logic: one Bedrock knowledge-base flow branching to two
  alternative vector-store options.
- Transition out intent: service selection is not the final lesson; set realistic
  expectations about what RAG can and cannot guarantee.
- Scope guardrail: no product comparison, recommendation, pricing, scale, or
  configuration detail.

### Beat 10 — Balance benefits with limitations

- Duration: 1:45.
- Narrative job: prevent overclaiming and make the audience's mental model
  operationally honest.
- Audience question answered: “Does RAG guarantee a correct answer?”
- Benefits:
  - access to selected private or updated context;
  - more grounded responses;
  - source attribution in supported flows.
- Limitations:
  - source quality and synchronization matter;
  - retrieval can be incomplete or irrelevant;
  - the model still generates the final response;
  - RAG can reduce hallucination risk but cannot guarantee correctness.
- Claim IDs: C12, C16, C17, C18.
- Use-case role: even with the agenda indexed, a wrong or outdated source can
  still produce a poor answer.
- Required wording: “reduce risk,” never “prevent” or “eliminate.”
- Transition out intent: compress the whole talk into three durable takeaways.

### Beat 11 — Resolve the story and hand off

- Duration: 1:25.
- Narrative job: answer the opening tension and prepare the next team segment.
- Audience question answered: “What should I remember?”
- Three takeaways:
  1. RAG adds external context without retraining the foundation model.
  2. The core flow is retrieve first, generate second.
  3. Amazon Bedrock Knowledge Bases can manage key steps, but data and retrieval
     quality still matter.
- Claim IDs: C02, C03, C10, C16.
- Use-case role: one sentence returning to the Cloud Mastery assistant.
- Closing resolution: the model did not need to memorize the agenda; it needed
  access to the right context at the right time.
- Transition out: brief neutral handoff to the next team-owned section/Kahoot.
- Prohibited ending: generic “Thank you,” independent Q&A, or new technical
  detail.

## 6. Cumulative Learning Checkpoints

| After beat | Audience should now understand | If not, later beats will fail because… |
|---:|---|---|
| 2 | The problem is missing private/recent context | RAG would appear unnecessary |
| 3 | RAG means retrieve context, then generate; no retraining | Components would be mistaken for training infrastructure |
| 4 | The concept applies to a concrete event question | The remaining architecture would feel abstract |
| 6 | Chunks, embeddings, and vector stores have distinct roles | Runtime retrieval would be opaque |
| 7 | Preparation and runtime are separate flows | Bedrock mapping would look like unexplained automation |
| 8 | Bedrock Knowledge Bases maps to known RAG steps | AWS service names would become a product inventory |
| 9 | OpenSearch and Aurora are alternatives in one conceptual slot | The agenda could be misread as a sequential architecture |
| 10 | RAG improves grounding but still requires evaluation | The closing could overpromise correctness |
| 11 | Three durable takeaways resolve the opening question | The module is ready for team handoff |

## 7. Claim Coverage by Beat

| Claim ID | Beat(s) | Narrative purpose |
|---|---|---|
| C01 | 2, 4 | Establish the private/recent-information gap |
| C02 | 3, 4, 11 | Define retrieve-before-generate |
| C03 | 3, 11 | Correct the retraining misconception |
| C04 | 3, 4 | Separate source, context, and response |
| C05 | 5 | Explain chunking |
| C06 | 5, 6 | Explain embeddings |
| C07 | 5, 6 | Explain the vector-store role |
| C08 | 6, 7 | Explain semantic retrieval |
| C09 | 7 | Show context augmentation before generation |
| C10 | 8, 11 | Map the workflow to Bedrock Knowledge Bases |
| C11 | 7, 8 | Preserve retrieval/generation separation |
| C12 | 7, 8, 10 | Qualify source attribution |
| C13 | 9 | Place OpenSearch Serverless |
| C14 | 9 | Place Aurora PostgreSQL |
| C15 | 9 | Establish alternatives, not sequence |
| C16 | 10, 11 | Constrain hallucination/correctness claims |
| C17 | 10 | Establish the need for evaluation |
| C18 | 5, 10 | Qualify freshness and synchronization |

All 18 approved claims have a narrative home. This does not mean every claim
must become visible slide text; most belong in the Vietnamese explanation.

## 8. Use-Case Discipline

The Cloud Mastery Knowledge Assistant appears in beats 2, 4–10, and 11, but its
role changes:

- Beat 2: pose the information gap.
- Beat 4: establish the scenario.
- Beats 5–7: demonstrate preparation and runtime.
- Beats 8–9: map the scenario to AWS components.
- Beat 10: show why grounding is not a correctness guarantee.
- Beat 11: close the loop in one sentence.

The use case must not introduce fictional performance results, user quotes,
architecture measurements, or claims that the assistant already exists.

## 9. Density and Visual Guidance for Later Phases

- One primary teaching job per beat/slide.
- Use at most two process diagrams in the module:
  - preparation flow; and
  - runtime flow.
- Beat 6 may use a simple semantic-space analogy visual, but not embedding
  mathematics.
- Beat 9 should use one branching choice visual, not a comparison table.
- Keep timings in `SCRIPT.md`; do not expose them on audience-facing slides.
- Place explanation in the talk track rather than filling slides with
  definitions.
- If a template layout cannot support a beat legibly, split the beat while
  preserving the timing budget; do not shrink text.

## 10. Phase 5 Authoring Contract

Phase 5 must expand every beat into both required Vietnamese formats:

1. **Full talk track** — natural Vietnamese prose that can be rehearsed and
   spoken almost verbatim.
2. **Speaker notes** — concise Vietnamese bullets for live reference.

For every beat/slide, Phase 5 must add:

- Speaking objective.
- Transition into the slide.
- Full talk track.
- Speaker notes.
- Transition to the next slide.
- Pronunciation or terminology note when useful.
- Planned duration matching or improving the Phase 4 budget.

Phase 5 may refine phrasing and timing but must not:

- Change the central takeaway.
- Add unsupported AWS claims.
- Exceed the 20-minute limit.
- Consume the 2:20 safety margin with new scope.
- Add demo, Kahoot, implementation, code, pricing, or service-comparison detail.
- Write final audience-visible English slide copy; that remains Phase 6 work.

## 11. Phase 4 Acceptance Criteria

Phase 4 is complete when:

- The narrative resolves the communication job and central takeaway.
- Every beat has one narrative job and one audience question.
- The sequence is cumulative and each transition creates the need for the next
  beat.
- The required section divider is first.
- The opening information gap is resolved in the closing.
- The planned duration is 17:40 with a 2:20 safety margin.
- All 18 approved claim IDs have a narrative home.
- The Cloud Mastery Knowledge Assistant supports rather than dominates the
  explanation.
- Generic RAG concepts precede AWS service mapping.
- OpenSearch Serverless and Aurora PostgreSQL are alternatives, not a sequence.
- Benefits and limitations are balanced.
- No final slide copy or PowerPoint authoring has started prematurely.
- `OPERATION.md` records validation, artifact state, and the Phase 5 next action.
