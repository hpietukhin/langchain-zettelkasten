# Agent Inbox: notify, question and review interrupts

Ambient agents need a place where humans see pending actions. Human touchpoints are: *notify* (FYI), *question* (agent asks for missing info), *review* (approve/edit/reject a tool call such as sending an email or scheduling a meeting). The interrupt payload describes the action and allowed responses.

```python
from langgraph.types import interrupt

def review_send(state):
    resp = interrupt({"action_request": {"action": "send_email", "args": state["email"]},
                      "config": {"allow_accept": True, "allow_edit": True, "allow_respond": True}})
    return {"review": resp}
```

Related:

* [20261014092000](../20261014092000) Ambient agents act on event streams, not chat prompts -- the use case

* [20261014091600](../20261014091600) interrupt() pauses a graph for human input -- each inbox item is an interrupt

* [20261014082400](../20261014082400) HITL decisions: approve, edit, reject, respond -- accept/edit/respond/ignore map to resume values

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Ambient Agents with LangGraph course\
  <https://academy.langchain.com/courses/ambient-agents>

Tags:

    #ambient-agents #human-in-the-loop #exam-build
