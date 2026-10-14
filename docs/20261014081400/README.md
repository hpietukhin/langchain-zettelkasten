# Handoffs pattern: the active agent changes via state

In handoffs, a tool updates a state variable (for example the current step or active agent) and the next turn is handled by a different prompt/agent configuration, which then talks directly to the user. Use it when control should move to a specialist rather than come back to a coordinator. Tools return a `Command` that updates state.

```python
from langchain.tools import tool, ToolRuntime
from langchain.messages import ToolMessage
from langgraph.types import Command

@tool
def transfer_to_billing(runtime: ToolRuntime) -> Command:
    """Hand the conversation to the billing specialist."""
    return Command(update={
        "active_agent": "billing",
        "messages": [ToolMessage("Transferred to billing", tool_call_id=runtime.tool_call_id)],
    })
```

Related:

* [20261014081300](../20261014081300) Subagents pattern: wrap a specialist agent as a tool -- contrast: supervisor stays in control

* [20261014091100](../20261014091100) Command combines a state update with routing -- handoffs use Command to update state and route

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Multi-agent handoffs\
  <https://docs.langchain.com/oss/python/langchain/multi-agent/handoffs>

Tags:

    #langchain-foundations #multi-agent-systems #exam-build
