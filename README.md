# AI-ML-Notes

For a **resume-worthy, interview-ready, GitHub-ready** version of both projects, don't think in days—think in phases.

## Project 1: Multimodal RAG (PDF + Images)

### Phase 1: Foundation (3–5 days)

* RAG fundamentals
* Embeddings
* Vector databases
* Chunking strategies
* CLIP architecture
* FAISS indexing

### Phase 2: PDF Processing (2–3 days)

* Text extraction using PyMuPDF
* Image extraction
* Metadata storage
* Chunk generation

### Phase 3: Multimodal Retrieval (3–4 days)

* CLIP text embeddings
* CLIP image embeddings
* Unified vector index
* Similarity search

### Phase 4: LLM Integration (2–3 days)

* LangChain integration
* GPT-4 Vision integration
* Context assembly
* Prompt engineering

### Phase 5: Production Features (3–5 days)

* FastAPI
* Streamlit UI
* Logging
* Error handling
* Docker

### Phase 6: Evaluation (2–3 days)

* RAGAS
* Retrieval metrics
* Latency measurement
* Hallucination testing

**Total: 15–25 days**

---

# Project 2: Agentic AI Trip Planner (LangGraph)

This project has higher industry value because it demonstrates agent orchestration and tool calling. LangGraph is specifically designed for stateful, multi-step agent workflows and multi-agent systems. ([Docs by LangChain][1])

## Architecture

```text
User Query
    │
    ▼
Planner Agent
    │
 ┌──┼──────────┐
 ▼  ▼          ▼
Weather  Research  Budget
 Agent     Agent    Agent
    │         │        │
    └────┬────┴────────┘
         ▼
    Itinerary Agent
         ▼
      Final Plan
```

---

## Step 1: Planner Agent (2–3 days)

Responsibilities:

* Understand user goal
* Break task into subtasks
* Decide which agents to call

Example:

Input:

```text
Plan a 5-day Goa trip under ₹25,000
```

Output:

```text
Need:
1. Research destination
2. Check weather
3. Calculate budget
4. Build itinerary
```

---

## Step 2: Research Agent (2–3 days)

Tools:

* Tavily Search
* Serper API

Responsibilities:

* Tourist places
* Attractions
* Restaurants
* Transportation

---

## Step 3: Weather Agent (1–2 days)

Tools:

* OpenWeather API

Responsibilities:

* Current weather
* Forecast
* Travel recommendations

---

## Step 4: Budget Agent (2–3 days)

Responsibilities:

* Hotel costs
* Food costs
* Transport costs
* Budget optimization

---

## Step 5: Itinerary Agent (3–4 days)

Responsibilities:

* Day-wise schedule
* Time allocation
* Cost estimation

Example:

```text
Day 1:
10 AM - Check-in
12 PM - Baga Beach
5 PM - Sunset Point
```

---

## Step 6: LangGraph Workflow (4–6 days)

Create:

* StateGraph
* Nodes
* Edges
* Conditional routing

LangGraph excels at stateful, multi-step workflows with routing, persistence, memory, and tool orchestration. ([LangChain Reference Docs][2])

---

## Step 7: Memory (2–3 days)

Short-term:

* Current trip context

Long-term:

* User preferences
* Previous trips
* Budget patterns

---

## Step 8: Tool Calling (2–3 days)

Add:

* Weather API
* Maps API
* Hotel API
* Search API

---

## Step 9: UI + FastAPI (3–5 days)

Frontend:

* Streamlit

Backend:

* FastAPI

Features:

* Chat interface
* Trip export
* PDF itinerary

---

## Step 10: Production Readiness (4–5 days)

* Docker
* Logging
* Monitoring
* Retry mechanisms
* Error handling
* LangSmith tracing

---

# Final Timeline

### Basic Version

* Multimodal RAG: 2–3 weeks
* Agentic Trip Planner: 2–3 weeks

**Total: 1 month**

### Resume-Ready Version

* Documentation
* GitHub
* FastAPI
* Streamlit
* Docker
* Evaluation

**Total: 6–8 weeks**

### Strong GenAI Portfolio Version

Add:

* LangGraph
* Multi-Agent System
* Multimodal RAG
* RAGAS Evaluation
* FastAPI
* Docker
* AWS Deployment
* CI/CD

**Total: 8–12 weeks**

For your background (Python + SQL + Data Engineering), I would prioritize this order:

1. **Finish Agentic AI Trip Planner**
2. **Add LangGraph + Tool Calling**
3. **Deploy on FastAPI + Streamlit**
4. **Complete Multimodal RAG**
5. **Deploy both on AWS**
6. **Create detailed GitHub documentation and architecture diagrams**

That combination is strong enough to target **GenAI Engineer, AI Engineer, Applied AI Engineer, and LLM Engineer** interviews.

[1]: https://docs.langchain.com/oss/python/langgraph/overview?utm_source=chatgpt.com "LangGraph overview - Docs by LangChain"
[2]: https://reference.langchain.com/python/langgraph/overview?utm_source=chatgpt.com "LangGraph - Python API Reference | LangChain Reference"
