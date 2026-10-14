# Async subagents run in the background

Synchronous subagents block until done. `AsyncSubAgent` launches a task on a graph (by `graph_id`, optionally a remote `url`) and returns immediately, so the supervisor can run parallel workstreams, check progress, steer mid-flight, or cancel. Without a `url` the graph is co-deployed in the same deployment.

```python
from deepagents import AsyncSubAgent, create_deep_agent

async_subagents = [
    AsyncSubAgent(name="researcher",
                  description="Research agent for information gathering and synthesis",
                  graph_id="researcher"),
]
agent = create_deep_agent(model="openai:gpt-5.5", subagents=async_subagents)
```

Related:

* [20261014084400](../20261014084400) Defining subagents with dicts or CompiledSubAgent -- synchronous subagents block the supervisor

* [20261014100100](../20261014100100) Assistants version configuration separately from code -- async subagents point at deployed graphs

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Async subagents\
  <https://docs.langchain.com/oss/python/deepagents/async-subagents>

* Deep Agents course, Module 5 Lesson 4: Asynchronous Subagents\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #deep-agents-foundations #delegation #asynchronous-subagents #exam-build
