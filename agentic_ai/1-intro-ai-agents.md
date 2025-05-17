# Agentic AI
Decoding Ai Agents and their capabilities.

### Journey of Automation
![Ai Journey](../docs/content/imgs/journey/ai-journey.png)

### Key points
1. An AI Agent is an application or function that can essentially plan and take action (Apis/tools)
2. Data + Models (Reasoning i.e GPT) + Memory + Tools/Apis + Infra = AI Agents 
3. Rule Based vs AI Automation vs AI Agent
    ```text
   RuleBased - Auto-reply OOO to all emails
   AI Automation - Using Ai models like gemini etc to understand keywords/Context, provide relevant responses.
   AI Agent - Understand the intent, plan and send personalized responses + takes action! i.e in the email example an AI Agent understand what the ask is,
              performs a task i.e aggregate data and send as requested while you are OOO.```
4. Key Components of an AI Agent 
   - Orchestration
   - Models (LLMs)
   - Tools
   - Memory

    ![Ai Agent Components](../docs/content/imgs/journey/ai-agent-components.png)

### Architecture Patterns
- **Reflection Pattern**, feedback loop or reinforcement learning i.e self correction constantly to optimise the future.
- **Planning Pattern**, chain of thought prompting. Takes a structured approach i.e breakdown into multiple subtasks comes up with a plan and completes the task. 
- **Tool Use Pattern**, invokes tools/apis to complete the pattern
- **MultiAgent Pattern**, running multiple agents to complete the task
    ![Ai Agent Arch Patterns](../docs/content/imgs/architecture/ai-agent-arch-patterns.png)

### News Search & Summarizer Workflow 
- News Search Agent & News Summarizer Agent
- **SerpAPI** Scrape Google and other search engines from our fast, easy, and complete API.
- **CrewAi** Streamlines workflows across industries with powerful AI agents
    ![LowCode Agent workflow](../docs/content/imgs/workflow/news-summarizer-low-code-workflow.png)
    ![ProCode Agent workflow](../docs/content/imgs/workflow/news-summarizer-pro-code-workflow.png)

### AI Meal Planner Workflow
- Creates healthy meal plan that matches your medical needs and food preferences
- Frameworks used
  - **StreamLit**: UI Framework
  - **CrewAI**: Multi-agent Orchestration (Can be **LangChain** or **LangGraph**)
  - **Ollama**: Local LLM running Mistral
- Agents:
  - **Dietitian** which processes medical conditions/allergies
  - **Chef** which creates cuisine-specific meal plans
  - **GuardRail** which tests the finals results before being published to end user
    ![AI Meal Planner Workflow](../docs/content/imgs/workflow/meal-planner-workflow.png)
    ![AI Meal Planner UI](../docs/content/imgs/journey/meal-planner-ui.png)
### References
- [AICamp](https://www.youtube.com/@AICamp)
- [NirDiamant Github: GenAi_Agents](https://github.com/NirDiamant/GenAI_Agents)
  - [AI News Agent v1](https://medium.com/@nirdiamant21/stop-reading-start-understanding-your-ai-news-agent-simplified-9845e69a86c6)
  - [News TL;DR](https://github.com/NirDiamant/GenAI_Agents/blob/main/all_agents_tutorials/news_tldr_langgraph.ipynb)
  - [Building First AI Agent](https://diamantai.substack.com/p/your-first-ai-agent-simpler-than)
- [AI News Agent v2](https://github.com/vatsalsaglani/GenAINewsAgent)
- 
