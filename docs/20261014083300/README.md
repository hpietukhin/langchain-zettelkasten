# Long-term memory lives in a store, namespaced across threads

A store (`BaseStore`) keeps JSON documents under a namespace tuple and key, independent of thread. Pass `store=` to `create_agent`; tools reach it through `runtime.store`. Use it for user profiles, preferences and learned facts. `InMemoryStore` is for development.

```python
from langchain.tools import tool, ToolRuntime
from langgraph.store.memory import InMemoryStore

store = InMemoryStore()

@tool
def save_pref(pref: str, runtime: ToolRuntime) -> str:
    """Remember a user preference."""
    runtime.store.put(("users", "u1"), "prefs", {"pref": pref})
    return "saved"

agent = create_agent("claude-sonnet-4-6", tools=[save_pref], store=store)
```

Related:

* [20261014080800](../20261014080800) Short-term memory = checkpointer + thread_id -- contrast: thread-scoped

* [20261014080500](../20261014080500) ToolRuntime gives tools access to state, context and store -- tools access runtime.store

* [20261014091900](../20261014091900) The LangGraph store: namespaces, keys and search -- LangGraph store API

* [20261014090100](../20261014090100) Agent-scoped vs user-scoped memory via store namespaces -- deep agents expose the store as files

* [20261014095700](../20261014095700) Storage durability on LangSmith Deployment -- server-provisioned store in deployment

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Long-term memory\
  <https://docs.langchain.com/oss/python/langchain/long-term-memory>

* Intro to LangGraph, Module 5: Memory\
  <https://academy.langchain.com/courses/intro-to-langgraph>

Tags:

    #langchain-foundations #langgraph-memory #long-term-memory #exam-build
