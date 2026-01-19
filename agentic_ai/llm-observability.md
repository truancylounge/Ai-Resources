# Observability

## OpenTelemetry (OTEL)
- OTEL is one of the most widely used standards for application observability
    - OTEL includes concepts of Collectors and Processor to receive traces and spans and enumerate them in a platform to visualize them and run evals on them.
    - Arize Phoenix is an framework to collect and visualize the data.
- Complete visibility into every layer of the LLM based software system: the application, the prompt, the response, token size etc
- OTEL is typically made up of **1. Traces** & **2. Spans**
- **Traces**:
    - A trace records the paths taken by requests(made by an application or end-user) as they propagate through multiple steps
    - Full run through of the application, all the way from input to output
    - Traces constitute multiple spans
- **Spans**:
    - Data captured on individual steps in an LLM app or pipeline
- **Instrumentation**, is the process is capturing traces and spans.
    - It refers to the process of marking which functions or code blocks as spans and which attributes are collected
    - We can add decorators in code to mark the data to be captured
    - Tools like Arize Phoenix automatically do the above process for us esp with LLM code.
- The detailed logs generated will be used to run Evals on the systems.
- Trace and Spans of Data Analysis Agent (LLM spans in Orange, Chain spans in blue and Tool spans in yellow)
  ![Data Analyst Phoenix Trace](../docs/content/imgs/samples/observability-trace-phoenix-sample1.png)

> [!NOTE]
> **OpenInference** is a set of conventions and plugins that is complimentary to OpenTelemetry to enable tracing of AI applications.

## Why is Observability Important:
- **Simplifies debugging** when building your application
- **Provides a detailed log** of each call made in your app, which is necessary to run **performance evaluations**
- Helps understand and control **the unpredictable behavior of LLMs**
- 