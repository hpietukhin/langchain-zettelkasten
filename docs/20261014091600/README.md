# interrupt() pauses a graph for human input

Calling `interrupt(payload)` inside a node saves state and surfaces the payload to the caller (`__interrupt__`). Execution can resume hours later. On resume the node re-runs from the beginning, so code before `interrupt` must be idempotent.

```python
from langgraph.types import interrupt

def approve(state):
    answer = interrupt({"question": "Send this email?", "draft": state["draft"]})
    return {"approved": answer == "yes"}
```

Related:

* [20261014091700](../20261014091700) Command(resume=...) continues an interrupted thread -- how to continue

* [20261014082300](../20261014082300) HumanInTheLoopMiddleware pauses before sensitive tool calls -- agents wrap this in middleware

* [20261014091400](../20261014091400) Checkpoints snapshot state at every super-step -- state is saved while paused

* [20261014092100](../20261014092100) Agent Inbox: notify, question and review interrupts -- ambient UIs show interrupts

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangGraph docs: Interrupts\
  <https://docs.langchain.com/oss/python/langgraph/interrupts>

* Intro to LangGraph, Module 3: Human-in-the-loop\
  <https://academy.langchain.com/courses/intro-to-langgraph>

Tags:

    #intro-to-langgraph #human-in-the-loop #langgraph-interrupts #exam-build
