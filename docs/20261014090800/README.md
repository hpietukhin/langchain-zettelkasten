# add_messages and MessagesState manage chat history

`add_messages` appends new messages, updates existing ones with the same ID, and deletes those targeted by `RemoveMessage`. `MessagesState` is a ready schema with `messages: Annotated[list[AnyMessage], add_messages]`.

```python
from langgraph.graph import MessagesState

class State(MessagesState):
    summary: str
```

Related:

* [20261014090700](../20261014090700) Reducers define how state updates are merged -- a special reducer

* [20261014080600](../20261014080600) Messages are the unit of context -- what it merges

* [20261014090900](../20261014090900) Trimming and removing messages controls context in graphs -- removing messages with RemoveMessage

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangGraph docs: Graph API\
  <https://docs.langchain.com/oss/python/langgraph/graph-api>

* Intro to LangGraph, Module 2: State and Memory\
  <https://academy.langchain.com/courses/intro-to-langgraph>

Tags:

    #intro-to-langgraph #langgraph-state #langchain-messages #exam-build
