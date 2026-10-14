# StoreBackend makes files durable across threads

Files are saved in the LangGraph `BaseStore`, so they survive across threads and restarts (Postgres-backed on LangSmith Deployment). A `namespace` function decides whose files they are, e.g. per assistant or per user.

```python
from deepagents.backends import StoreBackend
agent = create_deep_agent(model="openai:gpt-5.5", backend=StoreBackend(), store=store)
```

Related:

* [20261014083300](../20261014083300) Long-term memory lives in a store, namespaced across threads -- uses the LangGraph store

* [20261014085100](../20261014085100) CompositeBackend routes path prefixes to different backends -- usually mounted on /memories/

* [20261014090100](../20261014090100) Agent-scoped vs user-scoped memory via store namespaces -- namespace controls sharing

* [20261014095700](../20261014095700) Storage durability on LangSmith Deployment -- store is provisioned on LangSmith Deployment

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Backends\
  <https://docs.langchain.com/oss/python/deepagents/backends>

* LangSmith Deployment course, Module 4 Lesson 3: Memory in Deep Agents\
  <https://academy.langchain.com/courses/langsmith-deployment>

Tags:

    #deep-agents-foundations #filesystem-backends #storage-durability #exam-build
