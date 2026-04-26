# Building Memory Aware Agents

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
Agent memory enables an AI Agent to persistently store, organize, retrieve and reuse information across time, interactions and execution contexts. \n
This ensures temporal and contextual continuity, even across fragmented interactions.
- Types of Agent memory
  - Short Term memory
    - **Semantic Cache**, caching mechanism that leverages vector search and previous received responses from an LLM to essentially use as response for similar queries in subsequent interactions.
    - **Working Memory**, scratchpad for LLM which is lost after an interaction or session.
      - **LLM Context window**
      - **Session Based**
  - Long Term memory
    - **Procedural**, we store steps and interactions that an agent has taken to achieve its goal, i.e. tools calls and other interactions. \n
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
      
![AI Agent Memory vs RAG Pipeline](../docs/content/imgs/architecture/ai-agent-memory-rag-arch.png)


## Agent Memory Core



