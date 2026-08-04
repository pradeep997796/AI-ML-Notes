For a **3–5 years GenAI/AI Engineer** interview, interviewers usually expect:

* Strong understanding of LLMs and RAG
* Hands-on experience with LangChain/LangGraph
* Knowledge of Vector DBs
* Basic system design
* Agentic AI concepts
* Production deployment understanding

They generally do **not** expect deep ML research or model training from scratch.

# 1. LLM Fundamentals

### Q1. What is an LLM?

**Interview Answer**

> A Large Language Model (LLM) is a neural network, typically based on the Transformer architecture, trained on massive amounts of text data to understand and generate human-like language. Examples include GPT-4, Gemini, Claude, and Llama. LLMs can perform tasks such as question answering, summarization, code generation, and reasoning.

---

### Q2. How does an LLM work?

**Interview Answer**

> LLMs tokenize input text, convert tokens into embeddings, process them through Transformer layers using self-attention, and predict the most probable next token repeatedly until the response is generated.

---

### Q3. What are the limitations of LLMs?

**Interview Answer**

* Hallucination
* Limited context window
* No real-time knowledge by default
* Lack of domain-specific knowledge
* High inference cost

---

# 2. Embeddings

### Q4. What are embeddings?

**Interview Answer**

> Embeddings are dense numerical vector representations of text, images, or other data that capture semantic meaning. Similar concepts are represented by vectors that are close together in vector space.

---

### Q5. Why are embeddings important in RAG?

**Interview Answer**

> Embeddings enable semantic search. User queries and documents are converted into vectors, allowing retrieval based on meaning rather than exact keyword matches.

---

### Q6. Difference between token embeddings and document embeddings?

**Interview Answer**

* Token embeddings represent individual words/tokens.
* Document embeddings represent an entire sentence, paragraph, or document.

---

# 3. Vector Databases

### Q7. What is a Vector Database?

**Interview Answer**

> A Vector Database stores embeddings and enables efficient similarity search using nearest-neighbor algorithms.

Examples:

* Pinecone
* Weaviate
* Milvus
* Qdrant
* Chroma

---

### Q8. Why not use SQL databases?

**Interview Answer**

> SQL databases are optimized for exact matches, while vector databases are optimized for semantic similarity search across high-dimensional embeddings.

---

# 4. RAG

### Q9. What is RAG?

**Interview Answer**

> Retrieval-Augmented Generation combines retrieval and generation. Relevant documents are retrieved from a knowledge source and provided to the LLM as context before generating a response.

Architecture:

```text
User Query
    ↓
Embedding
    ↓
Vector Search
    ↓
Retrieved Context
    ↓
LLM
    ↓
Answer
```

---

### Q10. Why use RAG instead of fine-tuning?

**Interview Answer**

| RAG                  | Fine-Tuning                 |
| -------------------- | --------------------------- |
| Easy updates         | Retraining required         |
| Lower cost           | Expensive                   |
| Real-time knowledge  | Static knowledge            |
| Better for documents | Better for behavior changes |

---

### Q11. What causes poor RAG performance?

**Interview Answer**

* Poor chunking
* Weak embeddings
* Bad retrieval strategy
* Missing metadata
* No reranking

---

# 5. LangChain

### Q12. What is LangChain?

**Interview Answer**

> LangChain is a framework for building LLM applications by providing components such as document loaders, text splitters, embeddings, retrievers, vector stores, prompts, and chains.

---

### Q13. Why use LangChain?

**Interview Answer**

* Faster development
* Standardized integrations
* Supports multiple LLM providers
* Simplifies RAG implementation

---

# 6. FAISS / Pinecone

### Q14. What is FAISS?

**Interview Answer**

> FAISS (Facebook AI Similarity Search) is an open-source library developed by Meta for fast vector similarity search and nearest-neighbor retrieval.

---

### Q15. FAISS vs Pinecone?

**Interview Answer**

| FAISS               | Pinecone          |
| ------------------- | ----------------- |
| Local               | Managed Cloud     |
| Free                | Paid              |
| Self-hosted         | Fully managed     |
| No built-in scaling | Automatic scaling |

---

# 7. Hybrid Search

### Q16. What is Hybrid Search?

**Interview Answer**

> Hybrid Search combines semantic vector search with keyword-based search (such as BM25) to improve retrieval quality.

---

### Q17. Why Hybrid Search?

Example:

Query:

```text
Error Code ERR-5001
```

Vector search may struggle.

Keyword search finds exact matches.

Hybrid search combines both strengths.

---

# 8. Reranking

### Q18. What is Reranking?

**Interview Answer**

> Reranking is a second-stage retrieval process where initially retrieved documents are reordered using a more accurate model.

---

### Q19. Why use reranking?

**Interview Answer**

* Improves relevance
* Reduces hallucinations
* Improves answer quality

---

# 9. LangGraph

### Q20. What is LangGraph?

**Interview Answer**

> LangGraph is a framework for building stateful, multi-step, and multi-agent AI workflows with nodes, edges, state management, and conditional routing.

---

### Q21. LangChain vs LangGraph?

| LangChain        | LangGraph           |
| ---------------- | ------------------- |
| Chains           | Graph workflows     |
| Simple RAG       | Agentic systems     |
| Linear execution | Conditional routing |
| Stateless        | Stateful            |

---

# 10. Agents

### Q22. What is an AI Agent?

**Interview Answer**

> An AI Agent is an LLM-powered system capable of reasoning, making decisions, and using tools to accomplish tasks autonomously.

---

### Q23. Single Agent vs Multi-Agent?

| Single Agent       | Multi-Agent                  |
| ------------------ | ---------------------------- |
| Simpler            | More scalable                |
| One responsibility | Specialized responsibilities |
| Harder to extend   | Easier to maintain           |

---

# 11. Tool Calling

### Q24. What is Tool Calling?

**Interview Answer**

> Tool Calling allows an LLM to invoke external functions, APIs, databases, or services when additional information or actions are required.

---

### Q25. Example?

User asks:

```text
Weather in Pune
```

LLM calls:

```text
Weather API
```

Receives:

```text
29°C
```

Generates answer.

---

# 12. Memory

### Q26. Why is memory important?

**Interview Answer**

> Memory allows the system to maintain context across interactions and provide more personalized and coherent responses.

---

### Q27. Types of memory?

* Short-term memory
* Long-term memory
* Episodic memory
* Semantic memory

---

# 13. MCP

### Q28. What is MCP?

**Interview Answer**

> Model Context Protocol (MCP) is an open standard that allows AI models to access tools, databases, files, and services through a unified interface.

---

### Q29. Benefits of MCP?

* Standardization
* Reusable integrations
* Easier tool access
* Reduced development effort

---

# 14. Agentic AI

### Q30. What is Agentic AI?

**Interview Answer**

> Agentic AI refers to AI systems that can plan, reason, use tools, maintain memory, and execute multi-step workflows autonomously to achieve goals.

---

### Q31. Example?

Trip Planner:

```text
Planner Agent
 ↓
Weather Agent
 ↓
Budget Agent
 ↓
Itinerary Agent
 ↓
Final Plan
```

---

# 15. RAGAS Evaluation

### Q32. What is RAGAS?

**Interview Answer**

> RAGAS is a framework used to evaluate RAG systems by measuring retrieval quality and answer quality.

---

### Q33. Important RAGAS Metrics?

* Faithfulness
* Context Precision
* Context Recall
* Answer Relevancy

---

# 16. Production Deployment

### Q34. How would you deploy a RAG application?

**Interview Answer**

Architecture:

```text
Frontend (Streamlit/React)
          ↓
FastAPI Backend
          ↓
LangChain/LangGraph
          ↓
Vector Database
          ↓
LLM Provider
```

---

### Q35. How would you reduce LLM costs?

**Interview Answer**

* Response caching
* Better retrieval
* Smaller models where possible
* Context compression
* Rate limiting

---

# Scenario-Based Questions

### Q36. Retrieval is poor. What would you do?

**Answer**

* Improve chunking
* Better embeddings
* Hybrid search
* Add reranking
* Metadata filtering

---

### Q37. LLM hallucinates despite RAG.

**Answer**

* Strong grounding prompts
* Better retrieval
* Reranking
* Citation-based answers
* Lower temperature

---

### Q38. FAISS becomes slow with millions of documents.

**Answer**

* Move to Pinecone/Qdrant/Milvus
* Distributed indexing
* Metadata filtering
* Approximate nearest-neighbor search

---

### Q39. Weather API fails in your Trip Planner.

**Answer**

* Retry logic
* Fallback API
* Graceful degradation
* User notification

---

### Q40. Why should we hire you for a GenAI role?

**Sample Answer**

> I bring a combination of Python development, data engineering experience, and hands-on GenAI project work. I have built systems involving Multimodal RAG, CLIP embeddings, FAISS vector search, LangChain, and Agentic AI workflows using LangGraph. I understand not only how to use LLMs but also how to build scalable retrieval, orchestration, and deployment pipelines around them.

For your profile, mastering these 40 questions and being able to explain your **Multimodal RAG** and **Agentic AI Trip Planner** architecture confidently would put you in a strong position for many 3–5 year GenAI Engineer interviews.
