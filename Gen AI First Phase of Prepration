Since you're building **Multimodal RAG** and **Agentic AI Trip Planner**, I'll explain these concepts from an interview and project-building perspective rather than academic definitions.

# 1. What is an LLM?

**LLM (Large Language Model)** is an AI model trained on massive amounts of text to understand and generate human language.

Examples:

* GPT-4
* Claude
* Gemini
* Llama
* Mistral

### What an LLM does

Input:

```text
Plan a 5-day Goa trip under ₹20,000
```

Output:

```text
Day 1: Arrival
Day 2: North Goa
...
```

### Limitation

LLMs don't know:

* Your company documents
* Today's flight prices
* Private PDFs
* Real-time weather

This limitation led to **RAG**.

---

# 2. What is RAG?

**Retrieval-Augmented Generation**

Instead of relying only on what the model learned during training:

```text
User Question
      ↓
Retrieve Relevant Data
      ↓
Send Context To LLM
      ↓
Generate Answer
```

### Example

Suppose your PDF contains:

```text
Company revenue increased by 40%
```

User asks:

```text
What was revenue growth?
```

RAG process:

```text
PDF
 ↓
Chunking
 ↓
Embeddings
 ↓
Vector DB
 ↓
Retrieve Relevant Chunk
 ↓
GPT-4
 ↓
Answer
```

Without RAG:

```text
LLM guesses
```

With RAG:

```text
LLM answers using retrieved document
```

---

# 3. What are Embeddings?

Embeddings are numerical vector representations of data.

Example:

```text
Dog
```

becomes

```text
[0.23, -0.45, 0.78, ...]
```

### Why?

Computers don't understand words.

They understand numbers.

---

### Similar meanings → Similar vectors

```text
Dog
Puppy
Pet
```

Vectors:

```text
Dog    → [0.2,0.5,0.1]
Puppy  → [0.21,0.48,0.12]
Pet    → [0.19,0.51,0.11]
```

Very close.

---

### Different meaning

```text
Airplane
```

Vector:

```text
[-0.7,0.9,-0.4]
```

Far away.

---

### Interview Question

**Why embeddings?**

Answer:

> Embeddings convert text, images, or documents into dense numerical vectors that preserve semantic meaning, enabling similarity search and retrieval.

---

# 4. What is Vector Search?

Traditional search:

```sql
WHERE name='Goa'
```

Exact match.

---

Vector search:

```text
Beach vacation
```

can find:

```text
Goa
Maldives
Bali
```

because meaning is similar.

---

### Process

```text
Query
 ↓
Embedding
 ↓
Vector Search
 ↓
Nearest Vectors
```

---

# 5. What is a Vector Database?

A database optimized for storing vectors and performing similarity search.

Normal DB:

```text
MySQL
PostgreSQL
```

store:

```text
Rows
Columns
```

---

Vector DB stores:

```text
[0.23,0.67,0.89...]
```

---

Examples:

* FAISS
* Chroma
* Pinecone
* Weaviate
* Milvus
* Qdrant

---

### Interview Answer

**Why not SQL?**

SQL is optimized for exact lookups.

Vector databases are optimized for semantic similarity search.

---

# 6. What is FAISS?

**Facebook AI Similarity Search**

Open-source vector search library from Meta.

### FAISS workflow

```text
Document
 ↓
Embedding
 ↓
FAISS Index
 ↓
Similarity Search
```

---

### Why FAISS?

Advantages:

* Fast
* Free
* Local
* No cloud dependency

Perfect for:

* RAG
* Prototypes
* Personal projects

---

### Interview Question

**Why FAISS?**

Answer:

> FAISS provides efficient nearest-neighbor search on high-dimensional embeddings and is suitable for local vector search applications.

---

# 7. What is Chunking?

LLMs have context limits.

Suppose PDF contains:

```text
100 pages
```

You cannot send everything.

---

Split document:

```text
Page
 ↓
Chunks
```

Example:

```text
Chunk 1
Chunk 2
Chunk 3
Chunk 4
```

---

### Recursive Chunking

LangChain's most common splitter:

```python
RecursiveCharacterTextSplitter(
    chunk_size=500,
    chunk_overlap=100
)
```

---

### Why overlap?

Without overlap:

```text
Chunk1:
The revenue increased...

Chunk2:
...by 40%
```

Information gets separated.

---

With overlap:

```text
Chunk1:
Revenue increased by...

Chunk2:
increased by 40%...
```

Better retrieval.

---

# 8. What is LangChain?

Framework for building LLM applications.

Think:

```text
Django → Web Apps
LangChain → LLM Apps
```

---

### Provides

#### Document Loading

```python
PyPDFLoader
CSVLoader
```

#### Chunking

```python
RecursiveCharacterTextSplitter
```

#### Embeddings

```python
OpenAIEmbeddings
HuggingFaceEmbeddings
```

#### Vector DB Integration

```python
FAISS
Chroma
Pinecone
```

#### Retrieval

```python
Retriever
```

#### Chains

```python
Prompt → LLM → Output
```

---

### RAG in LangChain

```text
PDF
 ↓
Loader
 ↓
Splitter
 ↓
Embeddings
 ↓
FAISS
 ↓
Retriever
 ↓
GPT-4
```

---

# 9. What is CLIP?

**Contrastive Language–Image Pretraining**

Created by OpenAI.

CLIP places:

```text
Text
and
Images
```

into the same vector space.

---

### Traditional Embeddings

Text:

```text
Dog
```

works.

Image:

🐶

cannot compare directly.

---

### CLIP

Text:

```text
Dog
```

↓

```text
[0.1,0.2,0.3]
```

Image:

🐶

↓

```text
[0.11,0.21,0.29]
```

Almost identical.

---

### Why useful?

Query:

```text
Show revenue chart
```

can retrieve:

📊 chart image

even if the query is text.

---

This is exactly what makes your **Multimodal RAG** possible.

---

# 10. Complete Multimodal RAG Architecture

```text
PDF
 │
 ├── Text Extraction
 │
 └── Image Extraction
        │
        ▼
      CLIP
        │
 ┌──────┴──────┐
 ▼             ▼
Text Vector  Image Vector
        │
        ▼
      FAISS
        │
        ▼
 User Query
        │
        ▼
 Query Embedding
        │
        ▼
 Similarity Search
        │
        ▼
 Retrieved Text + Images
        │
        ▼
 GPT-4 Vision
        │
        ▼
 Final Answer
```

---

# Interview One-Line Definitions

| Concept       | Best Interview Definition                                              |
| ------------- | ---------------------------------------------------------------------- |
| LLM           | Large Language Model that generates and understands natural language.  |
| RAG           | Retrieval-Augmented Generation combines retrieval with LLM generation. |
| Embedding     | Numerical vector representation capturing semantic meaning.            |
| Vector Search | Similarity search using embeddings.                                    |
| Vector DB     | Database optimized for storing and searching vectors.                  |
| FAISS         | Meta's library for fast nearest-neighbor vector search.                |
| Chunking      | Splitting documents into smaller retrievable pieces.                   |
| LangChain     | Framework for building LLM and RAG applications.                       |
| CLIP          | Model that maps text and images into the same embedding space.         |

If you're preparing for GenAI interviews, the next concepts to learn after these are:
**LangGraph → Agents → Tool Calling → Memory → MCP → Reranking → Hybrid Search → RAGAS Evaluation → Agentic AI Architecture**. These are commonly discussed in current GenAI Engineer interviews.
