LLM as Judge


Evals  vs Vibes => 
* Claude Code team relies on vibes coz Tight feedback, Dogfoiding creates instant feedback, Team members are the eval set
* When do you rely on Vibes vs Eval Set


Agent High Level :

￼


￼

Questions for a GIT Commit Agent POC:
￼

EVALS Pyramid similar to Traditional Testing model:

￼


Eval Frameworks:
1. DeepEval,(python)
2. PromptFoo
3. The above are used for prompt testing but agentic testing gets more complex


GIT Commit POC Unit Test Evals:
￼

[Q]What is Golden Dataset
Something that’s fast and can run via pre-commit hook, 50 test cases pretty cost inexpensive


Golden DataSet sourced from Hugging Face
￼


Make sure golden data set is gated and you don’t run with large data and get huge BILL!!!
￼

LLM as JUDGE

Testing Diff via LLM as Judge, earlier it was via regex checks
This type of testing will be a bit more expensive
￼

The above tests won’t be run as part of pre commit hook, but will be run when underlying data changes, or model changes etc coz of the COST!

Observability or Testing in live:

OpenTelemetry is an open standard

￼


How to test in LIVE?
￼

* In our POC, if a user approves commit message, its a green signal, if they edited then neutral, if they cancelled then not good send feedback
* A/B testing, ship 2 versions and see which performs better

Summary:

* Build out directional eval suite using Jupyter notebook
* Create your own tooling, 3rd party isn’t mature enough to get tied to one solution
* Don’t be afraid to test in Live
* Look for opportunities to use cheaper models. Having diverse set of smaller models might be the way of future.
* As complexity explodes, different agents, telemetry becomes key. 
￼




