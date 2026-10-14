# create_agent vs create_deep_agent: when to use which

Both return a LangGraph graph and accept model, tools, system prompt, middleware, checkpointer and store. `create_agent` starts minimal: you add middleware for planning, memory, compression or HITL yourself. Use it for focused, shorter tasks where you want full control. `create_deep_agent` adds a fixed middleware stack (todos, filesystem + backends, subagents, summarization, prompt caching, skills/memory, HITL via `interrupt_on`) and a long built-in system prompt. Use it for open-ended, multi-step, long-running work (research, coding, analysis) where context management matters.

```python
from langchain.agents import create_agent
from langchain.agents.middleware import TodoListMiddleware
from deepagents import create_deep_agent

a = create_agent("openai:gpt-5.5", tools=[search], middleware=[TodoListMiddleware()])  # opt-in features
b = create_deep_agent(model="openai:gpt-5.5", tools=[search])                             # features by default
```

Related:

* [20261014080200](../20261014080200) create_agent builds a production agent graph -- the lean harness

* [20261014083500](../20261014083500) Deep Agents is a batteries-included agent harness -- the opinionated harness

* [20261014083800](../20261014083800) The Deep Agents middleware stack -- what create_deep_agent adds as middleware

* [20261014083000](../20261014083000) TodoListMiddleware gives the agent a planning tool -- planning can be added to create_agent manually

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Overview\
  <https://docs.langchain.com/oss/python/deepagents/overview>

* LangChain docs: Agents\
  <https://docs.langchain.com/oss/python/langchain/agents>

* Deep Agents docs: Customization\
  <https://docs.langchain.com/oss/python/deepagents/customization>

Tags:

    #deep-agents-foundations #langchain-foundations #exam-build
