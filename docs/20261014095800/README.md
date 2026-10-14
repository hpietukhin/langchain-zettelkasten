# Don't configure a checkpointer or store in deployed graph code

The Agent Server automatically injects the checkpointer and store configured for the deployment at runtime. Compiling with your own `InMemorySaver` would bypass durable storage and break server features, so export the graph without them.

```python
# agent.py for deployment
from langchain.agents import create_agent
agent = create_agent(model="openai:gpt-5.5", tools=[search])   # no checkpointer=, no store=
```

Related:

* [20261014080800](../20261014080800) Short-term memory = checkpointer + thread_id -- locally you pass a checkpointer

* [20261014095700](../20261014095700) Storage durability on LangSmith Deployment -- the server provides Postgres-backed persistence

* [20261014095900](../20261014095900) Export a compiled graph unless you need per-run factories -- injection works for both export styles

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Agent Server\
  <https://docs.langchain.com/langsmith/agent-server>

* LangSmith Deployment course, Module 4 Lesson 1: Memory in LangGraph\
  <https://academy.langchain.com/courses/langsmith-deployment>

Tags:

    #langsmith-deployment-foundations #memory #exam-deploy
