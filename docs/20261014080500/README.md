# ToolRuntime gives tools access to state, context and store

A tool parameter typed `ToolRuntime` is hidden from the model and injected at execution time. It exposes `runtime.state` (current graph state, e.g. messages), `runtime.context` (static per-invocation context), and `runtime.store` (long-term memory). This lets tools be context-aware without the model having to pass secrets or IDs.

```python
from langchain.tools import tool, ToolRuntime

@tool
def get_user_preference(pref_name: str, runtime: ToolRuntime) -> str:
    """Get a user preference value."""
    prefs = runtime.state.get("user_preferences", {})
    return prefs.get(pref_name, "Not set")
```

Related:

* [20261014080400](../20261014080400) Tools are typed functions whose docstring is the model's manual -- extends plain tools

* [20261014081000](../20261014081000) Runtime context is static per-invocation configuration -- runtime.context carries per-run config

* [20261014080900](../20261014080900) Custom agent state extends AgentState -- runtime.state exposes custom fields

* [20261014083300](../20261014083300) Long-term memory lives in a store, namespaced across threads -- runtime.store for cross-thread memory

* [20261014083400](../20261014083400) Context engineering: model, tool and life-cycle context -- this is tool context

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Tools\
  <https://docs.langchain.com/oss/python/langchain/tools>

* Intro to LangChain, Module 2 Lesson 2: Context and State\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #context-and-state #langchain-tools #exam-build
