# Reducers define how state updates are merged

By default a node's update overwrites a key. Annotating a key with a reducer (e.g. `operator.add`) makes updates combine instead, which is essential when parallel nodes write the same key.

```python
from operator import add
from typing import Annotated
from typing_extensions import TypedDict

class State(TypedDict):
    results: Annotated[list[str], add]   # appended, not overwritten
```

Related:

* [20261014090600](../20261014090600) A LangGraph graph is state, nodes and edges -- state schema

* [20261014090800](../20261014090800) add_messages and MessagesState manage chat history -- the most common reducer

* [20261014091200](../20261014091200) Send fans out work to parallel node instances -- parallel branches need reducers

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangGraph docs: Graph API\
  <https://docs.langchain.com/oss/python/langgraph/graph-api>

* Intro to LangGraph, Module 2: State and Memory\
  <https://academy.langchain.com/courses/intro-to-langgraph>

Tags:

    #intro-to-langgraph #langgraph-state #exam-build
