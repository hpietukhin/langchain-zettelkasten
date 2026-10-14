# The LangGraph store: namespaces, keys and search

The store saves JSON values under `(namespace_tuple, key)`; `search(namespace, query=...)` supports semantic search when an index is configured. Typical namespaces: `(user_id, "memories")`. Memory can be a single profile document (schema) or a growing collection.

```python
from langgraph.store.memory import InMemoryStore
store = InMemoryStore()
store.put(("u1", "memories"), "m1", {"food": "likes pizza"})
print(store.search(("u1", "memories")))
```

Related:

* [20261014083300](../20261014083300) Long-term memory lives in a store, namespaced across threads -- used by agents through runtime.store

* [20261014090100](../20261014090100) Agent-scoped vs user-scoped memory via store namespaces -- deep agents' namespace functions

* [20261014101200](../20261014101200) TTLs bound how long threads, checkpoints and store items live -- store items can expire

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangGraph docs: Persistence\
  <https://docs.langchain.com/oss/python/langgraph/persistence>

* Intro to LangGraph, Module 5: Memory store\
  <https://academy.langchain.com/courses/intro-to-langgraph>

Tags:

    #intro-to-langgraph #langgraph-memory #long-term-memory #exam-build
