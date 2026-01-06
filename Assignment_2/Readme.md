# Assignment 2 – LangGraph with Hugging Face LLMs

This assignment explores building **agent-based workflows using LangGraph**
combined with **Hugging Face–hosted LLMs**.  
Each question demonstrates a different graph design pattern.

---

## Folder Structure

```
Assignment_2/
│
├── Q1.py # Single-node LangGraph app with chat history
├── Q2.py # Multi-agent LangGraph (Question Analyzer + Answer Generator)
├── Q3.py # Router-based LangGraph with specialized agents
└── README.md
```

---

## Q1. Single-Node LangGraph with Chat History

### Objective
Build a **LangGraph application with a single Hugging Face LLM node** that:
- Answers user queries
- Maintains **chat history in graph state**
- Is tested with multiple queries from different domains

---

### Approach

- A custom **graph state (`GraphState`)** is defined using `TypedDict`
- The state stores a sequence of `HumanMessage` and `AIMessage` objects
- A single LangGraph node (`llm_node`) is created that:
  - Reads the entire message history from state
  - Formats messages into Hugging Face chat format
  - Calls a Hugging Face hosted LLM using `InferenceClient`
  - Appends the model’s response back into state

---

### Model Used
- **Model:** `meta-llama/Llama-3.2-3B-Instruct`
- **Provider:** Hugging Face Inference API
- **Temperature:** `0.7`
- **Max tokens:** `512`

---

### Graph Design

- Entry point: `llm`
- Single node graph
- The graph terminates immediately after the LLM responds

User Input → LLM Node → END


---

### Testing

The graph is tested using **three different user queries**:
1. Coding: *“Explain Python decorators”*
2. Mathematics: *“What is the derivative of x²?”*
3. General Knowledge: *“Who discovered gravity?”*

The same state object is reused across queries to verify that
**conversation history is preserved**.

---

### Key Concepts Demonstrated

- LangGraph `StateGraph` construction
- State persistence using message accumulation
- Hugging Face LLM integration via `InferenceClient`
- Multi-turn conversational behavior with a single node

---

