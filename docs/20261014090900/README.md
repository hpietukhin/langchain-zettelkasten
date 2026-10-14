# Trimming and removing messages controls context in graphs

Returning `RemoveMessage(id=...)` from a node deletes messages from state permanently; alternatively you trim only what you send to the model (transient). Summarising older turns into a `summary` key and deleting them is the classic long-conversation pattern.

```python
from langchain.messages import RemoveMessage

def delete_old(state):
    return {"messages": [RemoveMessage(id=m.id) for m in state["messages"][:-2]]}
```

Related:

* [20261014090800](../20261014090800) add_messages and MessagesState manage chat history -- RemoveMessage works through it

* [20261014082100](../20261014082100) SummarizationMiddleware compresses old history -- the agent-level equivalent

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Intro to LangGraph, Module 2: Trim and filter messages / Summarization\
  <https://academy.langchain.com/courses/intro-to-langgraph>

* LangChain docs: Short-term memory\
  <https://docs.langchain.com/oss/python/langchain/short-term-memory>

Tags:

    #intro-to-langgraph #langgraph-memory #context-engineering #exam-build
