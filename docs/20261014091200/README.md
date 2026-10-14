# Send fans out work to parallel node instances

Returning a list of `Send(node, payload)` from a conditional edge launches one node invocation per item with its own input: dynamic map-reduce (e.g. one research worker per subtopic). Results are merged by the reducer on the target key.

```python
from langgraph.types import Send

def fan_out(state):
    return [Send("write_section", {"topic": t}) for t in state["topics"]]

builder.add_conditional_edges("plan", fan_out, ["write_section"])
```

Related:

* [20261014090700](../20261014090700) Reducers define how state updates are merged -- fan-in requires a reducer

* [20261014084300](../20261014084300) Context isolation: subagents quarantine heavy work -- parallel subagents are the agent-level analogue

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangGraph docs: Graph API\
  <https://docs.langchain.com/oss/python/langgraph/graph-api>

* Intro to LangGraph, Module 4: Map-reduce\
  <https://academy.langchain.com/courses/intro-to-langgraph>

Tags:

    #intro-to-langgraph #langgraph-parallelization #exam-build
