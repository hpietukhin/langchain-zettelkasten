# Conditional edges route based on state

`add_conditional_edges(source, routing_fn)` calls a function on the state and goes to the node name it returns (or `END`). This is how the ReAct agent decides between calling tools and finishing.

```python
from langgraph.graph import END

def route(state) -> str:
    return "tools" if state["messages"][-1].tool_calls else END

builder.add_conditional_edges("model", route)
```

Related:

* [20261014090600](../20261014090600) A LangGraph graph is state, nodes and edges -- static edges

* [20261014091100](../20261014091100) Command combines a state update with routing -- routing from inside a node

* [20261014080000](../20261014080000) An agent is a model calling tools in a loop -- the agent's tools-or-end decision is a conditional edge

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangGraph docs: Graph API\
  <https://docs.langchain.com/oss/python/langgraph/graph-api>

* Intro to LangGraph, Module 1: Router\
  <https://academy.langchain.com/courses/intro-to-langgraph>

Tags:

    #intro-to-langgraph #langgraph-graph-api #exam-build
