# Command(resume=...) continues an interrupted thread

Invoke the graph again on the same thread with `Command(resume=value)`; the value becomes the return value of `interrupt()`. With several pending interrupts, map interrupt IDs to resume values.

```python
from langgraph.types import Command
graph.invoke({"draft": "Hi"}, cfg)            # pauses
graph.invoke(Command(resume="yes"), cfg)      # interrupt() returns "yes"
```

Related:

* [20261014091600](../20261014091600) interrupt() pauses a graph for human input -- what is being resumed

* [20261014082400](../20261014082400) HITL decisions: approve, edit, reject, respond -- agents resume with a decisions payload

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangGraph docs: Interrupts\
  <https://docs.langchain.com/oss/python/langgraph/interrupts>

Tags:

    #intro-to-langgraph #human-in-the-loop #langgraph-interrupts #exam-build
