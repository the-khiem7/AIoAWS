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
