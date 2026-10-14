# ContextEditingMiddleware clears old tool outputs

Tool results are often the biggest part of context. `ContextEditingMiddleware` with `ClearToolUsesEdit` removes older tool outputs once a token trigger is crossed, keeping only the last `keep` results. No extra LLM call is needed.

```python
from langchain.agents.middleware import ContextEditingMiddleware, ClearToolUsesEdit

mw = ContextEditingMiddleware(edits=[ClearToolUsesEdit(trigger=100000, keep=3)])
agent = create_agent(model="gpt-5.5", tools=[search], middleware=[mw])
```

Related:

* [20261014082100](../20261014082100) SummarizationMiddleware compresses old history -- contrast: summarises instead of deleting

* [20261014084100](../20261014084100) Offloading moves large tool payloads to the filesystem -- deep agents offload to files instead

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Built-in middleware\
  <https://docs.langchain.com/oss/python/langchain/middleware/built-in>

Tags:

    #langchain-foundations #managing-long-conversations #middleware #context-engineering #exam-build
