# A LangGraph graph is state, nodes and edges

State is a typed schema shared by all nodes. Nodes are functions that read state and return partial updates. Edges define control flow from `START` to `END`. `compile()` validates the graph and produces a runnable with `invoke`/`stream`.

```python
from typing_extensions import TypedDict
from langgraph.graph import StateGraph, START, END

class State(TypedDict):
    text: str

def shout(state: State):
    return {"text": state["text"].upper()}

builder = StateGraph(State)
builder.add_node("shout", shout)
builder.add_edge(START, "shout")
builder.add_edge("shout", END)
graph = builder.compile()
print(graph.invoke({"text": "hi"}))
```

Related:

* [20261014090700](../20261014090700) Reducers define how state updates are merged -- how node updates merge

* [20261014091000](../20261014091000) Conditional edges route based on state -- dynamic routing

* [20261014080200](../20261014080200) create_agent builds a production agent graph -- create_agent compiles to such a graph

* [20261014091400](../20261014091400) Checkpoints snapshot state at every super-step -- compiling with a checkpointer adds persistence

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangGraph docs: Graph API\
  <https://docs.langchain.com/oss/python/langgraph/graph-api>

* Intro to LangGraph, Module 1: Introduction\
  <https://academy.langchain.com/courses/intro-to-langgraph>

* LangChain Academy notebooks\
  <https://github.com/langchain-ai/langchain-academy>

Tags:

    #intro-to-langgraph #langgraph-graph-api #exam-build
