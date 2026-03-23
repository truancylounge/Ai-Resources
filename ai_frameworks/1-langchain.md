# LangChain

## Concepts
- **Grounding**, means connecting an AI model to specific, trusted and external data sources to ensure its response is accurate, current and relevant.
    It acts as fact-checker, anchoring the model abstract knowledge to real world data to reduce hallucinations and relying on outdated untrusted data.
- **Structured Output**
  - https://docs.langchain.com/oss/python/langchain/structured-output
  - ToolStrategy or ProviderStrategy
- **ChatModels**, 
  - https://docs.langchain.com/oss/python/langchain/models
  - Chat models are language models that use a sequence of messages as inputs and return messages as output
  - In addition to text generation, many models support
    - **Tool Calling**
    - **Structured output**
    - **Multimodality**
    - **Reasoning**
  - Key methods of a Chat Model are:
    - **invoke**, primary method to interact with chat model, takes list of messages as input and returns list of messages as output
    - **stream**, method that allows you to stream output of a chat model as it is generated
    - **batch**, method that allow you to batch multiple requests to a chat model together for more efficient processing
    - **bind_tools**, method to bind a tool to a chat model for use in the models execution context
    - **with_structured_output**, a wrapper around the invoke method for models that natively supports structured output.
- **Messages**
  - https://docs.langchain.com/oss/python/langchain/messages
  - Messages are fundamental unit of context for models in LangChain. 
  - Messages are objects that contain:
    - **Role**, identifies the message type (System, User)
    - **Content**, actual content of the message, like text, images, audio, docs etc
    - **Metadata**, optional fields such as response information, message IDs, token usage etc
  ```pycon
  from langchain.messages import SystemMessage, HumanMessage, AIMessage
  
  messages = [
  SystemMessage("You are a poetry expert"),
  HumanMessage("Write a haiku about spring"),
  AIMessage("Cherry blossoms bloom...")
  ]
  
  response = model.invoke(messages)
  ```