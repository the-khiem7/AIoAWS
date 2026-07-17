# Slide 1

**Layout:** 1_Cover slide gradient 1

## RAG (Retrieval-Augmented Generation)

**Shape:**
- Retrieve the right context.
- Generate a grounded response.

---

# Slide 2

**Layout:** 1_Section Header dark

**Shape:**
- A powerful model can still miss your answer

**Shape:**
- Foundation models may not know:

**Shape:**
- The knowledge exists
- but not inside the model.

![Picture 659](Picture/slide2_img1.png)

**Shape:**
- Your private documents

![Picture 43](Picture/slide2_img2.png)

**Shape:**
- Your private documents

**Shape:**
- Your latest updates

![Picture 48](Picture/slide2_img3.png)

![Picture 50](Picture/slide2_img4.png)

---

# Slide 3

**Layout:** 1_Section Header dark

**Shape:**
- Retrieval

**Shape:**
- Augmented

**Shape:**
- Generation

![Picture 17](Picture/slide3_img1.png)

![Picture 32](Picture/slide3_img2.png)

**Shape:**
- RAG

---

# Slide 4

**Layout:** TWO_OBJECTS

**Shape:**
- RAG keeps three things separate

**Shape:**
- Retrieve relevant context before the model generates a response.

**Shape:**
- Use external knowledge without retraining the model.

**Shape:**
- SOURCE DATA

**Shape:**
- External knowledge
- outside the model

**Shape:**
- RETRIEVED CONTEXT

**Shape:**
- Relevant passages
- added to the prompt

**Shape:**
- GENERATED RESPONSE

**Shape:**
- The model's answer

---

# Slide 5

**Layout:** 1_Section Header dark

![Picture 2](Picture/slide5_img1.png)

**Shape:**
- RAG personalizes the answers

**Shape:**
- Retrieve relevant context before the model generates a response.

---

# Slide 6

**Layout:** Quote 2

**Shape:**
- Prepare knowledge before the first question

**Shape:**
- Synchronize the data and index when source content changes.

![Picture 35](Picture/slide6_img1.png)

![Picture 37](Picture/slide6_img2.png)

![Picture 39](Picture/slide6_img3.png)

**Shape:**
- DOCUMENTS

**Shape:**
- External knowledge
- outside the model

**Shape:**
- Chunks

**Shape:**
- Smaller passages

**Shape:**
- Vector store

**Shape:**
- Indexed for similarity search

**Shape:**
- Embeddings

**Shape:**
- Numerical representations

---

# Slide 7

**Layout:** Quote 2

**Shape:**
- Embeddings Process

**Shape:**
- [-0.43, 0.36, 0.67 ... ]

**Shape:**
- [0.12, -0.45, 0.88 ... ]

![Picture 27](Picture/slide7_img1.png)

**Shape:**
- Sport
- sneaker

![Picture 30](Picture/slide7_img2.png)

**Shape:**
- Softdrink

**Shape:**
- Nén dữ liệu thô thành tọạ độ đa chiều.
- Tìm kiếm dựa trên khoảng cách ngữ nghĩa, không phải so khớp chuỗi.

---

# Slide 8

**Layout:** BLANK

![Picture 2](Picture/slide8_img1.png)

**Shape:**
- RAG personalizes the answers

**Shape:**
- Retrieve relevant context before the model generates a response.

---

# Slide 9

**Layout:** Quote 2

**Shape:**
- Toán học của Độ tương đồng (Similarity Metrics)

**Shape:**
- Cosine

**Shape:**
- Đo theo góc giữa 2 vector

**Shape:**
- Dot Product

**Shape:**
- Phép nhân vô hướng

**Shape:**
- Euclidean

**Shape:**
- Đo khoảng cách hình học giữa 2 điểm

**Shape:**
- An toàn nhất, phổ biến nhất, đa dụng cho hầu hết các bài toán

**Shape:**
- Tối ưu hóa tuyệt đối cho tốc độ nhưng yêu cầuvector phải được chuẩn hóa trước

**Shape:**
- Dành cho đo lường sai số vật lý hoặc phát hiện dị thường

---

# Slide 10

**Layout:** BLANK

**Shape:**
- Embeddings create a map of meaning

**Shape:**
- Embeddings map meaning. Vector stores find nearby content.

**Shape:**
- Question

**Shape:**
- How long is the
- RAG session?

**Shape:**
- Agenda passage

**Shape:**
- RAG with Bedrock
- - 20 minutes

**Shape:**
- Similar meaning can be close
- even when the words differ.

![Picture 711](Picture/slide10_img1.png)

---

# Slide 11

**Layout:** Quote

**Shape (placeholder idx=4294967295):**
- 11

**Shape:**
- Amazon Bedrock Knowledge Bases simplifies RAG

**Shape:**
- One managed workflow across preparation and runtime.

**Shape:**
- Prepare

**Shape:**
- Connect, chunk, embed, and store

**Shape:**
- Retrieve

**Shape:**
- Find relevant source chunks

**Shape:**
- Generate

**Shape:**
- Create a response from retrieved context

**Shape:**
- Attribute

**Shape:**
- Return sources in supported flows*

**Shape:**
- *Supported retrieval-and-generation flows. Quality decisions still matter.

![Picture 747](Picture/slide11_img1.png)

**Speaker Notes:**
The Next Evolution: AgentOps for AI Systems

Challenges
Prompt versioning
LLM performance monitoring
Agent workflow tracing
Cost tracking (tokens)
Evaluation of AI outputs
Safety & hallucination monitoring

---

# Slide 12

**Layout:** Section Header dark

**Shape:**
- Options for Vector Storing

**Shape:**
- Choose one vector-store option for this architecture.

**Shape:**
- VECTOR STORE
- Store and retrieve embeddings

**Shape:**
- AMAZON OPENSEARCH
- SERVERLESS

**Shape:**
- AMAZON AURORA
- POSTGRESQL-COMPATIBLE
- EDITION

**Shape:**
- Choose one option for this architecture - they are alternatives, not sequential steps.

[Image: Graphic 7 (linked/external)]

[Image: Graphic 14 (linked/external)]

**Shape:**
- AMAZON OPENSEARCH
- SERVERLESS

**Shape:**
- AMAZON OPENSEARCH
- SERVERLESS

---

# Slide 13

**Layout:** BLANK

**Shape:**
- Better grounding is not a correctness guarantee

**Shape:**
- Grounded answers still depend on the full quality chain.

**Shape:**
- RAG still depends on

**Shape:**
- Source quality and freshness
- Chunking and retrieval quality
- Generated-response quality

**Shape:**
- RAG can help

**Shape:**
- Use private or updated data
- Retrieve relevant context
- Improve traceability with sources*

**Shape:**
- RAG can reduce hallucination risk. It does not guarantee correctness.
- *In supported retrieval-and-generation flows.

![Picture 711](Picture/slide13_img1.png)

---

# Slide 14

**Layout:** Section Header dark

**Shape:**
- Three things to remember

**Shape:**
- The RAG mental model in three ideas.

**Shape:**
- 1

**Shape:**
- No retraining required
- Use external knowledge as context.

**Shape:**
- 2

**Shape:**
- Retrieve first, generate second
- Find relevant context before the response.

**Shape:**
- 3

**Shape:**
- Managed workflow, quality still matters
- Amazon Bedrock Knowledge Bases simplifies key steps.

**Shape:**
- Right context first. Better-grounded response next.

---
