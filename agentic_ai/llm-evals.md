# Evaluations

## Intro to Evals
- We should structure our Evaluations to iterate on and improve both the **output quality** and **path taken** by our agent. 
![Evaluation-Driven Development](../docs/content/imgs/workflow/evals-agent-workflow.png)
- **Broad category of Evaluations**:  
  - **LLM Model Evaluation**
    - Measures the general language understanding of a foundation model
    - Benchmark Datasets --> LLM
    - Example of Benchmark Datasets: 
      - **MMLU** (Mulitple choice questions covering math, philosophy, medicine...)
      - **HumanEval** (code generation)
  - **LLM System Evaluation**
    - Evaluate how well the entire application including the LLM performs for the specific application
    - Testing Datasets --> LLM
    - Testing datasets can be manually created, synthesized or curated i.e. real world data
- When testing an LLM based system we need to test the entire eco-system which includes **LLM | Prompt | Tools | Memory | Data sources**
- **Common types of Evaluations for LLM System**:
  - Hallucinations, Is LLM accurately providing context or making things up?
  - Retrieval relevance, Are the retrieved documents or context relevant to user query?
  - Q&A on retrieved data, Does the response match ground truth the user needs?
  - Toxicity, Is LLM outputting harmful or undesirable language?
  - Summarization performance, 
  - Code writing correctness and readability
- Evals for Agents:
  - What are Agents? Agents are software based systems that can take actions on behalf of user utilizing reasoning
  - 3 Main components of an Agent:
    - **Reasoning**, powered by AI (LLM)
    - **Routing**, interpreting request and determining the correct tool
    - **Action**, executing code/tools (creating requests, utilizing APIs, making LLM calls)
  - Agents use cases:
    - Personal Assistants, that help take notes and transcribe information for us
    - Desktop or Browser Agents, that help automate repetitive tasks
    - Automated scraping and summarization
    - Research Assistant
  - Example of Evals for a Trip Planning Agent 
  ![Trip Planning Agent Evals](../docs/content/imgs/workflow/evals-trip-planning-agent.png)

> [!NOTE] Evaluation Metrics:
> **Ground Truth**, metric which show how far away the output is from reference output
> 

## Tools used to Evaluate Agents
- Trace Instrumentation, Used to understand what's happening with our agent underneath the hood
- Eval Runner, which contains LLM as judge
- Data Sets, which can be used to rerun experiments
- Human Feedback, to capture human annotations
- Prompt Playground, used to iterate on your data to get expected results

![Tools used to Evaluate Agents](../docs/content/imgs/workflow/evals-tools.png)

## Resources
- https://docs.n8n.io/advanced-ai/evaluations/overview/
- 