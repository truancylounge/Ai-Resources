# Introduction
Agentic systems are often characterized by features by **autonomy**, allowing them to act without constant human oversight;
**proactiveness**, initiating actions towards their goals and **reactiveness**, responds effectively to changes in their environment. 
They are fundamentally **goal-oriented**, constantly working towards objectives.\
A critical capability is **tool use**, enabling them to interact with external APIs, databases or services - effectively reaching beyond immediate canvas.\
They possess **memory**, retain information across interactions, and can engage in communication with users, other systems, or even other agents operating on same or connected canvases.

Effectively realizing these characteristics introduces significant complexity. Hence, we need agentic design patterns to breakdown these complexities.

## Why patterns matter in Agentic Development
> How does the agent maintain state across multiple steps on its canvas?\
> How does it decide when and how to use the tool?\
> How is communication between agents managed?\
> How do you build resilience into system to handle unexpected outcomes or errors?

The complexities above is precisely why agentic design patterns are indispensable. They aren't rigid rules, but rather battle-tested templates
or blueprints that offer proven approaches to standard design and implementation challenges in the agentic domain.\
Using design patterns helps you avoid reinventing fundamental solutions for tasks like managing conversational flow, integrating external capabilities, or coordinating multiple target actions.\
Leveraging these established approaches accelerates your development process, allowing you to focus on unique aspects of your application rather than foundational mechanics of agent behavior. 

### 1. Prompt Chaining Pattern
Prompt chaining, sometimes referred to as Pipeline pattern, represents a powerful paradigm for handling intricate tasks when leveraging LLMs.\
Rather than expecting an LLM to solve a complex problem in single, monolithic step, prompt chaining advocates for divide-and-conquer strategy.\
The core idea is to break down the original, daunting problem into a sequence of smaller, more manageable sub-problems. Each sub-problem is addressed via a specially designed prompt and the output generated from one prompt is fed as input to subsequent prompt in the chain. 

- Limitations of single prompts: 
  - For multifaceted tasks, using a single, complex prompt for an LLM can be inefficient, causing model to struggle with constraints and instructions, potentially leading to instruction neglect.
  - Leads to **parts of the prompt are overlooked**, **contextual drift** where model loses track of initial context
  - **error propagation** where early errors amplify
  - Prompts which require a longer context window where model gets insufficient information to respond back
  - Hallucinations where cognitive load increases the chance of incorrect information. 
- Prompt Chaining, addresses these challenges by breaking the complex task into focussed, sequential workflow, which significantly improve reliability and control.

###