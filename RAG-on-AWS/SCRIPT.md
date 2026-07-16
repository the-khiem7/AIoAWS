# RAG with Amazon Bedrock — Presentation Script

## Document Status

- Phase 4 status: narrative blueprint and timing plan completed.
- Phase 5 status: full Vietnamese talk tracks and concise speaker notes completed;
  Gate C script QA passed.
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

## 12. Phase 5 Delivery Script

The wording below is the Vietnamese delivery layer for the 11 narrative beats.
The full talk track may be rehearsed almost verbatim. The speaker notes are the
short-form live reference.

### Slide 1 — Section divider

- Planned duration: **0:20**.
- Speaking objective: mark the RAG section and create immediate continuity from
  the preceding Amazon Bedrock content.
- Approved claims: none; navigation only.

#### Transition in

> Tiếp theo, chúng ta sẽ đi vào một cách rất phổ biến để đưa dữ liệu riêng vào
> trải nghiệm generative AI.

#### Full talk track

> Phần tiếp theo của chúng ta là **RAG with Amazon Bedrock**. Trong khoảng 20
> phút, chúng ta sẽ trả lời ba câu hỏi: vì sao cần RAG, RAG thực sự hoạt động như
> thế nào, và Amazon Bedrock giúp chúng ta ở những bước nào.

#### Speaker notes

- RAG with Amazon Bedrock.
- Ba câu hỏi: why, how, AWS mapping.
- Vào thẳng vấn đề, không giới thiệu lại sự kiện.

#### Transition out

> Trước hết, hãy bắt đầu từ một nghịch lý: model rất mạnh nhưng vẫn có thể không
> trả lời được câu hỏi của chúng ta.

#### Terminology note

- Đọc “RAG” nhất quán như từ tiếng Anh /ræg/; không cần đánh vần từng ký tự.

### Slide 2 — The model can be powerful and still miss the answer

- Planned duration: **1:30**.
- Speaking objective: establish the private/recent-information gap without
  making the foundation model sound weak.
- Approved claims: C01.

#### Transition in

> Model rất mạnh, vậy tại sao chúng ta vẫn cần thêm một hệ thống như RAG?

#### Full talk track

> Chúng ta vừa nói về foundation models và khả năng tạo nội dung rất mạnh của
> chúng. Nhưng một model mạnh không có nghĩa là model biết mọi thứ.
>
> Hãy lấy chính sự kiện Cloud Mastery làm ví dụ. Model có thể giải thích cloud là
> gì, AI là gì, thậm chí Amazon Bedrock là gì. Nhưng liệu model có tự biết agenda
> nội bộ mới nhất của sự kiện hôm nay không? Liệu nó có biết phần RAG của chúng ta
> kéo dài bao nhiêu phút, hoặc team vừa cập nhật tài liệu nào vào sáng nay không?
>
> Thông thường, câu trả lời là không. Những dữ liệu đó có thể là dữ liệu riêng,
> dữ liệu rất đặc thù cho tổ chức, hoặc được tạo ra sau thời điểm model được huấn
> luyện.
>
> Vì vậy, đây không hẳn là vấn đề model kém. Vấn đề là model đang thiếu đúng
> context cần thiết cho câu hỏi hiện tại. Và đó chính là khoảng trống mà RAG được
> thiết kế để giải quyết.

#### Speaker notes

- Model mạnh ≠ biết mọi dữ liệu.
- Ví dụ: agenda Cloud Mastery mới nhất.
- Private, domain-specific, recent information.
- Vấn đề chính: thiếu context, không nhất thiết do model yếu.
- Claim C01.

#### Transition out

> Vậy làm thế nào để cung cấp đúng thông tin cho model mà không phải huấn luyện
> lại model từ đầu?

#### Terminology note

- Dùng “foundation model” trên lần nhắc đầu; có thể nói ngắn là “model” ở các câu
  sau.
- “Context” được hiểu là thông tin tham chiếu cho yêu cầu hiện tại, không phải bộ
  nhớ vĩnh viễn.

### Slide 3 — Retrieve first, generate second

- Planned duration: **1:40**.
- Speaking objective: give the central RAG definition and correct the retraining
  misconception.
- Approved claims: C02, C03, C04.

#### Transition in

> Câu trả lời của RAG rất đơn giản về mặt ý tưởng: retrieve trước, generate sau.

#### Full talk track

> RAG là viết tắt của **Retrieval-Augmented Generation**. Tên nghe khá kỹ thuật,
> nhưng chúng ta có thể hiểu bằng hai hành động.
>
> Hành động thứ nhất là **retrieve**: tìm phần thông tin bên ngoài có liên quan
> đến câu hỏi. Hành động thứ hai là **generate**: đưa phần thông tin vừa tìm được
> vào context, rồi foundation model mới tạo câu trả lời.
>
> Điểm rất quan trọng ở đây là RAG không huấn luyện lại foundation model. Dữ liệu
> nguồn vẫn nằm bên ngoài model. Với mỗi yêu cầu, hệ thống chỉ lấy phần phù hợp và
> đưa phần đó cho model sử dụng tại thời điểm trả lời.
>
> Chúng ta cũng cần tách ba khái niệm. Thứ nhất là **source data**—tài liệu gốc.
> Thứ hai là **retrieved context**—đoạn thông tin được chọn từ tài liệu. Thứ ba là
> **generated response**—câu trả lời bằng ngôn ngữ tự nhiên do model tạo ra.
>
> Nếu chỉ nhớ một câu trong phần này, hãy nhớ: **retrieve first, generate
> second**.

#### Speaker notes

- RAG = Retrieval-Augmented Generation.
- Retrieve: tìm thông tin liên quan.
- Generate: model tạo câu trả lời từ question + context.
- Không retrain model.
- Source data ≠ retrieved context ≠ generated response.
- Câu nhớ: retrieve first, generate second.
- Claims C02–C04.

#### Transition out

> Bây giờ, hãy biến định nghĩa này thành một tình huống rất gần với sự kiện hôm
> nay.

#### Terminology note

- “Retrieval” là truy xuất; “generation” là sinh câu trả lời.
- Tránh nói “RAG học tài liệu” vì dễ khiến người nghe hiểu thành training.

### Slide 4 — Cloud Mastery Knowledge Assistant

- Planned duration: **1:30**.
- Speaking objective: make the RAG definition concrete with one consistent
  event-related scenario.
- Approved claims: C01, C02, C04.

#### Transition in

> Giả sử chúng ta có một trợ lý hỏi đáp dành riêng cho Cloud Mastery.

#### Full talk track

> Hãy tưởng tượng một người tham dự mở Cloud Mastery Knowledge Assistant và hỏi:
> “Phần RAG kéo dài bao lâu?”
>
> Foundation model có thể hiểu câu hỏi, nhưng nó không tự biết agenda nội bộ mới
> nhất. Vì vậy, hệ thống sẽ tìm trong bộ tài liệu Cloud Mastery, lấy đúng đoạn có
> thông tin “RAG with Bedrock—20 minutes”, rồi đưa đoạn đó vào context.
>
> Sau đó model mới tạo câu trả lời: “Phần RAG kéo dài 20 phút.”
>
> Trong ví dụ này, agenda là source data. Dòng chứa thời lượng là retrieved
> context. Còn câu trả lời cuối cùng là generated response.
>
> Ví dụ này chỉ dùng để giải thích. Chúng ta không giả định trợ lý đã được xây
> dựng hoặc đã đạt một mức accuracy nào. Điều cần quan sát là model không phải
> ghi nhớ agenda; model chỉ cần được cung cấp đúng context khi người dùng đặt câu
> hỏi.

#### Speaker notes

- Question: “Phần RAG kéo dài bao lâu?”
- Agenda = source data.
- Dòng “20 minutes” = retrieved context.
- Câu trả lời = generated response.
- Teaching example, không phải demo/kết quả thật.
- Claims C01, C02, C04.

#### Transition out

> Nhưng trước khi hệ thống có thể tìm đúng đoạn agenda, chúng ta phải biến bộ tài
> liệu thành một nguồn có thể truy xuất được.

#### Terminology note

- Không dùng từ “database” cho toàn bộ source data; source có thể là tài liệu hoặc
  hệ thống khác.

### Slide 5 — Prepare the knowledge before asking questions

- Planned duration: **1:55**.
- Speaking objective: explain the preparation/ingestion flow and separate it
  from runtime retrieval.
- Approved claims: C05, C06, C07, C18.

#### Transition in

> Bước đầu tiên không xảy ra khi người dùng đặt câu hỏi. Nó xảy ra trước đó, khi
> chúng ta chuẩn bị knowledge source.

#### Full talk track

> Hãy nhìn vào luồng chuẩn bị dữ liệu. Đầu tiên, chúng ta có source documents—ví
> dụ agenda, tài liệu workshop hoặc FAQ của sự kiện.
>
> Tiếp theo, hệ thống chia tài liệu thành những phần nhỏ hơn gọi là **chunks**.
> Tại sao không dùng nguyên cả tài liệu? Vì một tài liệu dài thường chứa rất nhiều
> chủ đề, trong khi câu hỏi chỉ cần một vài đoạn liên quan. Chunks giúp retrieval
> làm việc ở mức cụ thể hơn.
>
> Sau đó, mỗi chunk được chuyển thành một **embedding**, tức là một dạng biểu diễn
> bằng các con số. Các embeddings này được ghi vào một **vector store** hoặc
> vector index, đồng thời vẫn giữ liên kết về tài liệu gốc.
>
> Như vậy, luồng chuẩn bị có thể nhớ bằng bốn bước: documents, chunks,
> embeddings, vector store.
>
> Có thêm một lưu ý về dữ liệu mới. Nếu agenda thay đổi, source data và index
> cũng cần được đồng bộ hoặc cập nhật. RAG không tự động bảo đảm rằng mọi câu trả
> lời luôn dùng dữ liệu mới nhất nếu pipeline chưa đưa thay đổi đó vào index.
>
> Đây là preparation flow. Nó khác với runtime flow—luồng xảy ra khi người dùng
> thật sự đặt câu hỏi—mà chúng ta sẽ xem ngay sau đây.

#### Speaker notes

- Preparation xảy ra trước câu hỏi.
- Documents → chunks → embeddings → vector store.
- Chunk = đoạn nhỏ, retrieval cụ thể hơn.
- Giữ mapping về source document.
- Dữ liệu thay đổi cần sync/update index.
- Tách preparation và runtime.
- Claims C05–C07, C18.

#### Transition out

> Hai thuật ngữ mới nhất ở đây là embedding và vector store. Chúng ta sẽ dừng lại
> một chút để hiểu trực giác của chúng.

#### Terminology note

- “Ingestion” có thể giải thích là quá trình đưa và chuẩn bị dữ liệu cho hệ
  thống.
- Không đi vào token size hoặc chunking strategy nâng cao.

### Slide 6 — A map of meaning

- Planned duration: **2:05**.
- Speaking objective: build a beginner-safe intuition for embeddings, semantic
  similarity, and vector stores.
- Approved claims: C06, C07, C08.

#### Transition in

> Làm thế nào máy tính biết một câu hỏi và một đoạn tài liệu có ý nghĩa gần nhau,
> dù chúng không dùng chính xác cùng từ ngữ?

#### Full talk track

> Một **embedding** là cách biểu diễn nội dung thành một dãy số để hệ thống có thể
> so sánh về mặt toán học. Chúng ta không cần học công thức trong phần này. Hãy
> dùng một hình dung đơn giản: embedding giống như tọa độ trên một “bản đồ ý
> nghĩa”.
>
> Trên bản đồ đó, các nội dung có ý nghĩa liên quan thường nằm gần nhau hơn. Ví
> dụ, câu hỏi “Phần RAG kéo dài bao lâu?” và đoạn agenda “RAG with Bedrock—20
> minutes” không có toàn bộ từ giống nhau, nhưng chúng nói về cùng một chủ đề.
>
> **Vector store** là nơi lưu và lập chỉ mục các embeddings để chúng ta có thể
> tìm những điểm gần với embedding của câu hỏi. Khi người dùng hỏi, câu hỏi cũng
> được biểu diễn để so sánh. Hệ thống tìm các chunks có mức độ tương đồng cao và
> trả chúng về làm candidate context.
>
> Có hai điều cần tránh hiểu nhầm. Embedding không phải là bản tóm tắt mà con
> người có thể đọc. Và vector store không viết câu trả lời. Nó chỉ giúp tìm nội
> dung có ý nghĩa liên quan. Foundation model vẫn là thành phần tạo ra câu trả
> lời cuối cùng.
>
> “Bản đồ ý nghĩa” chỉ là phép so sánh để chúng ta dễ hình dung. Trong hệ thống
> thực tế, embeddings là các vectors số và việc tìm kiếm dựa trên phép đo tương
> đồng.

#### Speaker notes

- Embedding = numerical representation.
- Analogy: tọa độ trên “map of meaning”.
- Meaning gần nhau → vectors có thể gần nhau.
- Vector store lưu/index embeddings, tìm similar chunks.
- Không phải summary; không generate câu trả lời.
- Analogy, không phải UI thật.
- Claims C06–C08.

#### Transition out

> Khi đã có vector store, chúng ta có thể chạy toàn bộ câu hỏi của người tham dự
> qua runtime flow.

#### Terminology note

- Đọc “embedding” gần như “em-be-đing”; “vector” là “véc-tơ”.
- Giải thích “semantic similarity” là gần nhau về ý nghĩa.

### Slide 7 — From question to grounded response

- Planned duration: **2:10**.
- Speaking objective: explain the complete runtime retrieve-and-generate flow.
- Approved claims: C08, C09, C11, C12.

#### Transition in

> Bây giờ người dùng thật sự đặt câu hỏi. Hãy theo dõi từng bước.

#### Full talk track

> Bước một, người tham dự hỏi: “Phần RAG kéo dài bao lâu?”
>
> Bước hai, hệ thống biểu diễn câu hỏi theo cách có thể so sánh với các embeddings
> đã lưu.
>
> Bước ba, vector store tìm các chunks có ý nghĩa gần với câu hỏi. Trong trường
> hợp này, một kết quả phù hợp là dòng agenda chứa “RAG with Bedrock—20 minutes”.
>
> Bước bốn, hệ thống đưa chunk vừa truy xuất vào context cùng với câu hỏi ban
> đầu. Đây chính là phần **augmentation** trong RAG.
>
> Bước năm, foundation model đọc question và context, rồi tạo câu trả lời bằng
> ngôn ngữ tự nhiên.
>
> Trong những Bedrock retrieval-and-generation flows được hỗ trợ, response cũng
> có thể đi kèm source attribution—thông tin cho biết context đến từ source chunk
> nào. Điều đó giúp tăng tính minh bạch, nhưng chúng ta không nên xem citation là
> bằng chứng rằng mọi từ trong câu trả lời đều chắc chắn đúng.
>
> Hãy để ý retrieval và generation là hai hành động khác nhau. Một managed
> operation có thể kết hợp chúng cho thuận tiện, nhưng về mặt tư duy, chúng ta
> vẫn cần biết đâu là đoạn được tìm thấy và đâu là nội dung do model tạo ra.
>
> Toàn bộ runtime flow có thể rút gọn thành: question, retrieve context,
> augment, generate.

#### Speaker notes

- Question → query representation.
- Vector store retrieves relevant chunks.
- Add chunks to context = augmentation.
- Foundation model generates response.
- Supported flows may include source attribution.
- Citation ≠ guarantee.
- Retrieval và generation tách biệt về concept.
- Claims C08, C09, C11, C12.

#### Transition out

> Nếu tự xây toàn bộ luồng này, chúng ta phải kết nối rất nhiều thành phần. Đây
> là lúc Amazon Bedrock Knowledge Bases xuất hiện.

#### Terminology note

- “Grounded response” nên giải thích là câu trả lời dựa trên context được cung
  cấp, không dịch thành “câu trả lời chắc chắn đúng”.

### Slide 8 — Amazon Bedrock Knowledge Bases manages key RAG steps

- Planned duration: **1:55**.
- Speaking objective: map the established generic RAG flow to Amazon Bedrock
  Knowledge Bases without overclaiming full automation.
- Approved claims: C10, C11, C12.

#### Transition in

> Chúng ta đã hiểu RAG ở mức generic. Bây giờ mới map các bước đó sang AWS.

#### Full talk track

> **Amazon Bedrock Knowledge Bases** giúp triển khai và quản lý nhiều bước quan
> trọng trong RAG workflow.
>
> Ở phía chuẩn bị dữ liệu, knowledge base có thể hỗ trợ lấy nội dung từ data
> source, parsing, chunking, tạo embeddings và đưa embeddings vào vector store
> theo configuration đã chọn.
>
> Ở runtime, knowledge base hỗ trợ truy xuất source chunks liên quan. Hệ thống có
> thể dùng kết quả retrieval trực tiếp, hoặc kết hợp retrieval với foundation
> model để tạo natural-language response và source attribution trong những flow
> được hỗ trợ.
>
> Giá trị chính ở đây là team không phải tự nối từng thành phần cơ bản từ con số
> không. Tuy nhiên, câu nói an toàn là Bedrock Knowledge Bases **quản lý hoặc đơn
> giản hóa các bước quan trọng**. Nó không làm biến mất mọi quyết định về dữ liệu,
> chunking, retrieval quality hay evaluation.
>
> Với Cloud Mastery assistant, chúng ta có thể map source documents, embeddings,
> vector store, retrieval và response về một managed AWS workflow rõ ràng hơn.
> Nhưng mental model vẫn giống như trước: retrieve context trước, model generate
> sau.

#### Speaker notes

- Map generic RAG → AWS sau khi audience đã hiểu flow.
- Preparation: source, parse, chunk, embed, vector store.
- Runtime: retrieve hoặc retrieve + generate.
- Supported source attribution.
- “Manage/simplify key steps,” không “mọi thứ tự động hoàn hảo”.
- Claims C10–C12.

#### Transition out

> Trong workflow này, vector store là một vị trí kiến trúc. Agenda của chúng ta
> liệt kê hai lựa chọn AWS cho vị trí đó.

#### Terminology note

- Trên slide giữ nguyên tên **Amazon Bedrock Knowledge Bases**.
- Không đưa API names vào lời nói trừ khi khán giả hỏi thêm sau buổi trình bày.

### Slide 9 — One vector-store role, multiple AWS choices

- Planned duration: **1:25**.
- Speaking objective: place OpenSearch Serverless and Aurora PostgreSQL in the
  same conceptual architecture slot as alternatives.
- Approved claims: C13, C14, C15.

#### Transition in

> OpenSearch và Aurora không phải hai bước phải chạy nối tiếp nhau.

#### Full talk track

> Trong kiến trúc đơn giản của chúng ta, knowledge base cần một vector store để
> lưu và tìm kiếm embeddings.
>
> **Amazon OpenSearch Serverless** là một lựa chọn AWS-native cho vector search.
> Nó có thể cung cấp vector index cho Amazon Bedrock Knowledge Bases.
>
> **Amazon Aurora PostgreSQL-Compatible Edition** là một lựa chọn khác. Với khả
> năng vector của PostgreSQL, Aurora có thể đảm nhiệm vai trò vector store cho
> knowledge base.
>
> Điều quan trọng trong 20 phút hôm nay không phải là chọn dịch vụ nào tốt hơn.
> Điều quan trọng là hiểu cả hai đang đứng ở cùng một vị trí trong simplified
> architecture: vị trí lưu và truy xuất vectors.
>
> Vì vậy, hãy đọc sơ đồ theo dạng “chọn một vector-store option phù hợp”, không
> phải “OpenSearch xong rồi chuyển sang Aurora”. Các tiêu chí cost, performance,
> operation và configuration nằm ngoài phạm vi phần này.

#### Speaker notes

- Một conceptual slot: vector store.
- Option 1: Amazon OpenSearch Serverless.
- Option 2: Amazon Aurora PostgreSQL-Compatible Edition.
- Alternatives, không sequential.
- Không compare/recommend.
- Claims C13–C15.

#### Transition out

> Chúng ta đã có đầy đủ kiến trúc. Câu hỏi cuối cùng là: RAG giúp được gì, và nó
> không bảo đảm điều gì?

#### Terminology note

- Dùng đầy đủ “Amazon Aurora PostgreSQL-Compatible Edition” lần đầu.
- Có thể nói ngắn “Aurora PostgreSQL” ở câu sau.

### Slide 10 — Better grounding is not a correctness guarantee

- Planned duration: **1:45**.
- Speaking objective: balance RAG benefits with realistic limitations and safe
  hallucination wording.
- Approved claims: C12, C16, C17, C18.

#### Transition in

> RAG cải thiện thông tin đầu vào cho model, nhưng không biến generative AI thành
> một hệ thống luôn đúng.

#### Full talk track

> Lợi ích rõ nhất của RAG là model có thể sử dụng dữ liệu riêng hoặc dữ liệu được
> cập nhật bên ngoài training data. Retrieval giúp đưa context liên quan vào
> prompt, và source attribution trong những flow được hỗ trợ giúp chúng ta truy
> vết context đến từ đâu.
>
> Nhưng chất lượng cuối cùng phụ thuộc vào nhiều mắt xích. Source data có đúng và
> đủ mới không? Tài liệu được chia chunks có giữ đủ ý nghĩa không? Retrieval có
> lấy đúng đoạn liên quan không? Và model có diễn đạt đúng dựa trên context đó
> không?
>
> Vì vậy, cách nói chính xác là RAG **có thể giảm hallucination risk** bằng cách
> grounding câu trả lời trong nguồn bên ngoài. Không nên nói RAG ngăn chặn hoặc
> loại bỏ hallucinations. AWS cũng cung cấp cách đánh giá retrieval và generation
> riêng biệt, vì hai phần này đều có thể ảnh hưởng đến kết quả.
>
> Quay lại Cloud Mastery assistant: nếu agenda trong source đã cũ, hệ thống có
> thể truy xuất rất đúng nhưng vẫn trả lời bằng thông tin cũ. Nếu retrieval lấy
> sai chunk, model sẽ nhận context không phù hợp. RAG tốt cần dữ liệu tốt,
> retrieval tốt và evaluation phù hợp.

#### Speaker notes

- Benefits: private/updated context, grounding, traceability.
- Quality chain: data → chunks → retrieval → generation.
- Reduce hallucination risk, không eliminate/prevent.
- Evaluate retrieval và generation.
- Agenda cũ → answer vẫn có thể cũ.
- Claims C12, C16–C18.

#### Transition out

> Với giới hạn đó trong đầu, chúng ta có thể kết thúc bằng ba ý ngắn gọn.

#### Terminology note

- “Hallucination” giải thích ngắn là nội dung model tạo ra nghe hợp lý nhưng sai
  hoặc không có căn cứ.
- Không dùng “accuracy 100%” hoặc bất kỳ số liệu không có nguồn nào.

### Slide 11 — Three things to remember

- Planned duration: **1:25**.
- Speaking objective: resolve the opening problem, reinforce three durable
  takeaways, and hand off to the next team section.
- Approved claims: C02, C03, C10, C16.

#### Transition in

> Nếu chỉ mang theo ba điều sau phần này, hãy nhớ ba ý này.

#### Full talk track

> Thứ nhất, RAG giúp foundation model sử dụng external knowledge mà không cần
> retrain model trên toàn bộ dữ liệu đó.
>
> Thứ hai, mental model cốt lõi là **retrieve first, generate second**. Hệ thống
> tìm context liên quan trước, sau đó foundation model mới tạo câu trả lời.
>
> Thứ ba, Amazon Bedrock Knowledge Bases có thể quản lý hoặc đơn giản hóa nhiều
> bước quan trọng trong workflow, nhưng data quality, retrieval quality và
> evaluation vẫn rất quan trọng.
>
> Quay lại câu hỏi đầu tiên: model không cần ghi nhớ agenda Cloud Mastery. Model
> cần được cung cấp đúng đoạn agenda, đúng thời điểm, để trả lời câu hỏi hiện tại.
>
> Đó là giá trị cốt lõi của RAG: đưa đúng context đến model trước khi model
> generate. Và cũng cần nhớ rằng RAG giúp câu trả lời grounded hơn, chứ không bảo
> đảm mọi câu trả lời luôn đúng.
>
> Phần RAG của chúng ta kết thúc tại đây. Mình xin chuyển sang phần tiếp theo của
> chương trình.

#### Speaker notes

- 1: External knowledge, no retraining requirement.
- 2: Retrieve first, generate second.
- 3: Bedrock simplifies key steps; quality/evaluation still matter.
- Close loop: model không memorize agenda, chỉ cần right context.
- Grounded hơn ≠ guaranteed correct.
- Handoff sang phần tiếp theo.

#### Transition out

> Mình xin chuyển sang phần tiếp theo của chương trình.

#### Terminology note

- Giữ nhịp chậm ở ba takeaways; đây là phần người nghe cần nhớ.
- Không mời Q&A hoặc giới thiệu Kahoot thay cho người phụ trách tiếp theo.

## 13. Rehearsal and Live-Delivery Guidance

### Timing discipline

- Planned scripted delivery remains **17:40**.
- Maintain the **2:20** safety margin for pauses, slower explanation, and team
  transition.
- QA count: 11 full-talk-track sections contain approximately 1,948
  whitespace-delimited words. At 120 words per minute, straight reading is about
  16:14; the 17:40 plan intentionally allows roughly 1:26 for emphasis, pointing
  to visuals, and slide transitions before the separate 2:20 safety margin.
- If running long, shorten examples in Slides 4 and 6 first. Do not remove the
  limitations in Slide 10 or the synthesis in Slide 11.
- If running short, pause for emphasis and restate the runtime flow. Do not add
  unverified implementation detail.

### Audience checks

Use rhetorical checks rather than stopping for a long interaction:

- After Slide 3: “Retrieve trước, generate sau.”
- After Slide 6: “Vector store tìm nội dung; model tạo câu trả lời.”
- After Slide 7: “Question → retrieve context → augment → generate.”
- After Slide 10: “Grounded hơn không có nghĩa là luôn đúng.”

### Delivery style

- Use a conversational pace and short pauses after each new term.
- Point to the current process step rather than reading every label.
- Repeat the phrase “retrieve first, generate second” no more than three times
  across the full module.
- Keep English AWS product names intact; explain their role in Vietnamese.
- Do not improvise claims about price, scale, Region support, model lists,
  security, or implementation.

## 14. Phase 5 Acceptance Criteria

Phase 5 is complete when:

- All 11 slides contain a full Vietnamese talk track.
- All 11 slides contain concise Vietnamese speaker notes.
- Every slide includes objective, duration, transition in, transition out, and
  terminology guidance.
- Talk tracks follow the Phase 4 narrative order and approved claim IDs.
- Language is understandable to a newcomer and sounds natural when spoken.
- RAG is never described as retraining the foundation model.
- OpenSearch Serverless and Aurora PostgreSQL remain alternatives.
- Hallucination wording uses reduce/minimize risk, never prevent/eliminate.
- No demo, Kahoot, code, implementation, pricing, or unsupported claim is added.
- The planned duration remains 17:40 with a 2:20 safety margin.
- Final audience-visible English slide copy remains deferred to Phase 6.
- `OPERATION.md` records script QA, artifact state, and the Phase 6 next action.
