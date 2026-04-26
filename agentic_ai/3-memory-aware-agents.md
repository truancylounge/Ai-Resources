# Building Memory Aware Agents

**AI Agents memory lifecycle**

![Ai Agents Memory Lifecycle](../docs/content/imgs/overview/ai-agents-memory-lifecycle.png)

**Memory Engineering** broadly consists of following principles - Data Engineering, Agent Engineering, ML Engineering & Information Retrieval

![Memory Engineering](../docs/content/imgs/overview/ai-agents-memory-engineering.png)

## Agent
- An AI agent is a computational entity that has the following capabilities
  - **Perception**, perceives its environment through inputs
  - **Reasoning**, reasons and plans using an LLM as its cognitive engine
  - **Action**, takes actions via tools and integrations
  - **Memory**, augmented with persistent memory to store, retrieve and apply knowledge across interactions

## Stateless Agents
- Stateless agent can perceive inputs, reason and produce actions or outputs but cannot retain or recall information beyond single interaction.
- Disadvantages of stateless agents
  - Cannot perform Long-Horizon tasks
  - No Context awareness across sessions
  - No Learning or Adaptation abilities, i.e. any new information provided during current interactions cannot be used in future interactions
  - High Operations costs, since we have to do a lot of Context Stuffing i.e. pass all past interaction data for every interaction 

## Memory Augments Agents
- Memory augment agents store and retrieve memory into a database about user interactions
- Advantages of memory agents
  - Supports Long-Horizon tasks
  - Sustained context awareness across sessions
  - Improved efficiency and Reduced operational cost
  - Greater reliability in Multi Step workflow

## Agent Memory
Agent memory enables an AI Agent to persistently store, organize, retrieve and reuse information across time, interactions and execution contexts.
This ensures temporal and contextual continuity, even across fragmented interactions.
- Types of Agent memory
  - Short Term memory
    - **Semantic Cache**, caching mechanism that leverages vector search and previous received responses from an LLM to essentially use as response for similar queries in subsequent interactions.
    - **Working Memory**, scratchpad for LLM which is lost after an interaction or session.
      - **LLM Context window**
      - **Session Based**
  - Long Term memory
    - **Procedural**, we store steps and interactions that an agent has taken to achieve its goal, i.e. tools calls and other interactions.
      It's ideal to record the steps in form of external memory which can be referenced and pulled in subsequent interactions.
      - Workflow memory
      - Toolbox memory
    - **Semantic**, this is knowledge base or any external domain specific knowledge that agent needs to compute the task.
      - Entity Memory
      - Knowledge Base
      - Persona
    - **Episodic**, this is a form of conversational memory where attributes are stored based on their timestamp.
      - Summaries
      - Conversational

In an agentic system, there are three main components where memory is located:
  - In our LLM which has **parametric memory** i.e. all the data it has been trained with.
  - Embedding model, which has memory by which it could draw semantic and context information from when generating an embedding
  - Database, most traffic in our agentic system 

![AI Agent Memory vs RAG Pipeline](../docs/content/imgs/architecture/ai-agent-memory-rag-arch.png)

## Agent Memory Core
This is the primary database of an agentic system responsible for managing the complete lifecycle of agent memory.
This database layer handles persistent storage, efficient retrieval and memory operations that enables agents to adapt to new information, learn from interactions and maintain consistent performance across sessions.


## Memory Core & Memory Manager & Memory Operations
- Memory Core & Memory Manager combined give AI Agents memory-augmented behavior

![Ai Agents Memory Types](../docs/content/imgs/overview/ai-agents-memory-types.png)

![Ai Agents Memory Operations](../docs/content/imgs/overview/ai-agents-memory-ops.png)

- Classification of Memory operations in Agentic Systems
  - **Deterministic** (executed automatically by code)
    - Operations are run under **explicit, fixed conditions** e.g. "always at start of agent loop" or "always after tool execution"
    - **Advantages of deterministic Retrieval**:
      - **Context bootstrapping**
        - agent needs prior context to remain consistent and avoid repeatable mistakes
        - Without deterministic retrieval agent is stateless and starts from scratch
      - The agent can't choose to look up what it does not know exists
      - **Predictability**, always loading memory produces consistent behavior and makes the system easier to evaluate and debug
      - Reliability, Completeness, Reduced congnitive load (model should focus on task execution and not memory bookkeeping)
  - **Agent Triggered** (decided by LLM at runtime)
    - Operations that run only when model decides it's necessary, based on intent and situation
    - Not everything deserves long-term storage, the agent can distinguish signal from noise
    - **Cost and latency control** (Deep retrieval, reranking, summarization and consolidation cost tokens/time). Trigger only when needed to reduce overhead.
    - Higher-quality memory management
      - Decisions about what to store and how to compress requires semantic understanding of intent
      - THe model is well suited to decided when a memory action is worthwhile
    - **Advantages of Agent-Triggered Memory Ops**:
      - Higher signal-to-noise memory
      - Reduced memory bloat
      - Selective compute usage (summarize, expand, retrieve only when valuable)
    - External Tool Call's are Agent triggered as well as judgement is needed based on User Query. 
![AI Agents Memory Ops Classification](../docs/content/imgs/journey/ai-agent-memory-ops-classification.png)

## Useful Patterns
- Context Engineering, Maximising value of each token passed to LLM context, we want to have high signal/noise ratio for single token passed into LLM via various data sources.
![Context Engineering](../docs/content/imgs/journey/ai-agent-context-engineering.png)
- 
