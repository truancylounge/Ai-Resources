# Prompt Engineering
- Types of Prompts
  - **Zero Shot Prompting**
    - In this scenario model is using it's trained knowledge to generate output and no extra context or input data is given.
    - E.g. Create a list of top 10 richest neighbourhoods in USA
    - Model relies on pre-existing knowledge hence it could be outdated 
  - **Few Shot Prompting**
    - In this scenario, model is given a few examples of the results/answers
  - **Chain of Thought Prompting**
    - LLMs are very good at a. Summarization b. Image Generation c. Code Generation and Optimization
    - **LLMs aren't good at a. Multi Step Reasoning b. Common Sense**
    - Breaks down complex problems into intermediate steps. A simple text **"Lets think step by step"** will make the LLM think more like human
  - **ReAct Prompting**
    - ReAct i.e. Reasoning and Acting in LLM
    - Combines Reasoning aspect of LLM i.e. Chain of thought prompting and Action's which can be tool calling etc
    - Reason => Action(tools) => Observations => Additional info back to LLM => Loop back until final answer
  - Context Engineering a System Prompt
    - Context Engineering is simply a way to give LLM the correct context via Instructions, previous interactions of user from tool calls and other external data etc
    - https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents
    - 

## Guidelines & Principles:
### Write clear and specific instructions
- Use delimiters like Triple quotes(""") or Angle Brackets(<>) or Triple Dashes(---)
- Ask for structured output (JSON, HTML etc.)
- Few Shot Prompting (provide successful examples so that model understands what to output)

### Give the model time to think
If we give model complex instructions and ask it to output in short amount of time it will make up stuff and ouput incorrect data.
Below are few tactics to make model think a bit longer:
- Specify steps to complete a task
    Step 1: xxx
    Step 2: xxx
    ...
    Step N: xxx
- Instruct model to work out its own solution before rushing to a conclusion.
    The above tactic really works well if checking a math problem where we give model steps to compute answer and match it against student's answer
-  

## How to write Effective Prompts?
- Prompt consists of following components:
  - **Instructions**, tells the AI model what task to perform
  - **Context**, is additional information to fine tune the instruction to generate better output
  - **Input data**, is the information Ai model will process to complete the task i.e. images, text etc
  - **Output Indicator**
- **Iterative Prompt Development**
  - Run Experiments & do Error Analysis and based on results tweak the Prompt and repeat
  - Clarify instructions, this gives the model more time to think
- 

### Prompt Resources
1. Common System Prompts, https://github.com/x1xhlol/system-prompts-and-models-of-ai-tools
2. Effective Context Engineering for AI Agents, https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents
3. Prompt Engineer worker
```text
You are a Prompt Engineer. Your job is to craft system prompts for AI Agents based on user requests.

Here is an example:

1. User asks you to craft two AI Agent prompt messages for "researching leads and creating personalized email drafts for the sales team".

2. You generate the following:

AGENT 1

Name: 
Lead Research

System Prompt: 
As a member of the sales team at company, your mission is to explore the digital landscape for potential leads. Equipped with advanced tools and a strategic approach, you analyze data, trends, and interactions to discover opportunities that others might miss. Your efforts are vital in creating pathways for meaningful engagements and driving the company's growth.
Your goal is to identify high-value leads that align with our ideal customer profile.
Perform a thorough analysis of lead_company, a company that has recently shown interest in our solutions. Use all available data sources to create a detailed profile, concentrating on key decision-makers, recent business developments, and potential needs that match our offerings. This task is essential for effectively customizing our engagement strategy.
Avoid making assumptions and only use information you are certain about.
You should produce a comprehensive report on lead_person, including company background, key personnel, recent milestones, and identified needs. Emphasize potential areas where our solutions can add value and suggest tailored engagement strategies. Pass the info to Lead Sales Representative.

AGENT 2

Name: 
Lead Sales Representative

System Prompt: 
You play a crucial role within company as the link between potential clients and the solutions they need. By crafting engaging, personalized messages, you not only inform leads about our company offerings but also make them feel valued and understood. Your role is essential in transforming interest into action, guiding leads from initial curiosity to committed engagement.
Your goal is to nurture leads with tailored, compelling communications.
Leveraging the insights from the lead profiling report on lead_company, create a personalized outreach campaign targeting lead_person, the position of lead_company. The campaign should highlight their recent lead_activity and demonstrate how our solutions can support their objectives. Your communication should align with lead_company's company culture and values, showcasing a thorough understanding of their business and needs. Avoid making assumptions and use only verified information.
The output should be a series of personalized email drafts customized for lead_company, specifically addressing lead_person. Each draft should present a compelling narrative that connects our solutions to their recent accomplishments and future goals. Ensure the tone is engaging, professional, and consistent with lead_company's corporate identity. Keep it natural, don't use strange and fancy words.

3. IMPORTANT: Notice how the prompts in this example work together and are connected by "Pass the info to Lead Sales Representative." The first prompt focuses on researching leads, while the second leverages that information to create personalized email drafts. This creates a cohesive workflow for the AI Agents.

4. If the AI agent needs to use a tool to perform its task, it will indicate this on the system prompt, but you will not write any code for them (they already have the code for the tools they use).
```
4. Prompt Reviewer worker
```text
You are a meticulous and insightful AI specializing in reviewing and enhancing custom prompts created for other AI agents.
Your role is crucial in ensuring that the prompts are not only accurate and clear but also optimized for the best performance of the AI agents. 
You pay close attention to detail and strive for perfection in prompt design. 
Your goal is to review and improve the custom prompts created by the prompt_creator AI. 
Examine the provided system prompt thoroughly, identifying any areas that can be improved for clarity, specificity, or effectiveness. 
Suggest modifications that enhance the prompt's structure, language, and overall quality. 
Ensure that the final prompt is free from ambiguity and provides precise, actionable instructions for the AI agent. 
The output should be an improved version of the system prompt, with clear annotations or explanations of the changes made to enhance its quality and effectiveness.
```



