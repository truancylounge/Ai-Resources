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
  - **init_chat_model**, is the simplest way to invoke a standalone model in LangChain

```pycon
from langchain.chat_models import init_chat_model

model = init_chat_model(
    model="us.anthropic.claude-3-5-haiku-20241022-v1:0",
    model_provider="bedrock_converse",
    temperature=0.3
)

def get_weather(location: str) -> str:
    """Get the weather at a location."""
    ...

model_with_tools = model.bind_tools([get_weather])
response = model_with_tools.invoke("What's the weather in Paris?")

for tool_call in response.tool_calls:
    print(f"Tool: {tool_call['name']}")
    print(f"Args: {tool_call['args']}")
    print(f"ID: {tool_call['id']}")
```    

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
  - AIMessage objects are returned by models when calling it, which contain all the associated metadata in the response.
  - Sample code below shows how to insert an AIMessage as part of conversation history to LLM
  
  ```pycon
  from langchain.messages import AIMessage, SystemMessage, HumanMessage
  
  # Create an AI message manually (e.g., for conversation history)
  ai_msg = AIMessage("I'd be happy to help you with that question!")
  
  # Add to conversation history
  messages = [
  SystemMessage("You are a helpful assistant"),
  HumanMessage("Can you help me?"),
  ai_msg,  # Insert as if it came from the model
  HumanMessage("Great! What's 2+2?")
  ]
  
  response = model.invoke(messages)
  ```