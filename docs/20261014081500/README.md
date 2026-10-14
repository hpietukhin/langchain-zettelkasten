# Middleware hooks into every step of the agent loop

Middleware is how you customise `create_agent` without rewriting the loop: logging, prompt transforms, tool selection, retries, fallbacks, rate limits, guardrails, summarization and human approval. Hooks run inside the compiled LangGraph graph before/after the model and tools. Middleware is passed as an ordered list and composes.

```python
from langchain.agents import create_agent
from langchain.agents.middleware import SummarizationMiddleware, HumanInTheLoopMiddleware

agent = create_agent(
    model="gpt-5.5",
    tools=[send_email],
    middleware=[
        SummarizationMiddleware(model="gpt-5.4-mini", trigger=("tokens", 4000)),
        HumanInTheLoopMiddleware(interrupt_on={"send_email": True}),
    ],
)
```

Related:

* [20261014080000](../20261014080000) An agent is a model calling tools in a loop -- what middleware wraps

* [20261014081600](../20261014081600) Node-style hooks run before or after agent and model steps -- node-style hooks

* [20261014081700](../20261014081700) Wrap-style hooks intercept model and tool calls -- wrap-style hooks

* [20261014081800](../20261014081800) Class-based middleware bundles hooks, config and state -- class-based middleware

* [20261014083100](../20261014083100) Catalogue of built-in middleware -- prebuilt middleware

* [20261014083800](../20261014083800) The Deep Agents middleware stack -- deep agents are built from middleware

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Middleware overview\
  <https://docs.langchain.com/oss/python/langchain/middleware/overview>

* Intro to LangChain, Module 3 Lesson 1: What is Middleware?\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #middleware #production-ready-agent #exam-build
