# Cost Optimization Strategy

## Introduction
Large Language Models incur cost based on:
- Token usage
- Embedding volume
- Inference frequency

This project is designed to minimize operational cost while maintaining accuracy.

---

## Key Cost Challenges in AI Recruitment Systems
- Large resume sizes
- Repetitive embedding of verbose text
- Unnecessary LLM calls
- High storage overhead

---

## Cost Optimization Techniques Used

### 1. Compression Before Embedding
- Resumes and job descriptions are compressed before embedding
- Reduces text size by 60–80%
- Leads to:
  - Lower embedding cost
  - Faster retrieval
  - Smaller vector storage

---

### 2. Smaller Vector Footprint
- Fewer tokens result in smaller embeddings
- FAISS stores optimized vectors efficiently
- Reduces memory usage

---

### 3. Retrieval-Based Generation
- LLM is called only on retrieved candidates
- Avoids full-dataset processing
- Reduces inference cost

---

### 4. Deterministic Output
- Temperature is set to 0
- Prevents re-generation and retry loops
- Ensures consistent responses

---

### 5. Limited Context Window
- Only top-K resumes are passed to the LLM
- Prevents unnecessary context expansion

---

## Cost Comparison (Conceptual)

| Approach | Cost |
|--------|------|
| Full Resume Processing | High |
| Keyword Matching | Medium |
| RAG without Compression | Medium |
| RAG with Compression (This Project) | Low |

---

## Conclusion
By combining compression, semantic retrieval, and controlled LLM usage,
the system achieves significant cost savings while maintaining high-quality
candidate screening results.
