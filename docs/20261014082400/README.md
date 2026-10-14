# HITL decisions: approve, edit, reject, respond

Approve runs the call as proposed; edit changes the arguments first (change conservatively, or the model may re-plan); reject skips the call with a message explaining why; respond answers on behalf of the tool (use only when the human *is* the tool, e.g. an ask-user prompt, never to deny a side-effecting action). Resume with `Command(resume={"decisions": [...]})` on the same thread.

```python
from langgraph.types import Command

cfg = {"configurable": {"thread_id": "t1"}}
agent.invoke({"messages": [{"role": "user", "content": "Delete old records"}]}, cfg)
agent.invoke(Command(resume={"decisions": [{"type": "approve"}]}), cfg)
```

Related:

* [20261014082300](../20261014082300) HumanInTheLoopMiddleware pauses before sensitive tool calls -- where decisions are configured

* [20261014091700](../20261014091700) Command(resume=...) continues an interrupted thread -- how decisions are sent back

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Human-in-the-loop\
  <https://docs.langchain.com/oss/python/langchain/human-in-the-loop>

* Deep Agents docs: Human-in-the-loop\
  <https://docs.langchain.com/oss/python/deepagents/human-in-the-loop>

Tags:

    #langchain-foundations #human-in-the-loop #exam-build
