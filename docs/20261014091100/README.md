# Command combines a state update with routing

A node (or tool) can return `Command(update=..., goto=...)` to update state and pick the next node in one step, avoiding a separate routing function.

```python
from typing import Literal
from langgraph.types import Command

def triage(state) -> Command[Literal["billing", "support"]]:
    target = "billing" if "invoice" in state["text"] else "support"
    return Command(update={"route": target}, goto=target)
```

Related:

* [20261014091000](../20261014091000) Conditional edges route based on state -- alternative routing

* [20261014081400](../20261014081400) Handoffs pattern: the active agent changes via state -- handoffs use Command

* [20261014091700](../20261014091700) Command(resume=...) continues an interrupted thread -- Command also resumes interrupts

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangGraph docs: Graph API\
  <https://docs.langchain.com/oss/python/langgraph/graph-api>

Tags:

    #intro-to-langgraph #langgraph-graph-api #multi-agent-systems #exam-build
