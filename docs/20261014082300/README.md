# HumanInTheLoopMiddleware pauses before sensitive tool calls

`interrupt_on` maps tool names to `True`, `False`, or a config with `allowed_decisions`. When the model proposes a listed tool call, the graph raises an interrupt and waits; state is checkpointed so the run can resume later, even in another process.

```python
from langchain.agents.middleware import HumanInTheLoopMiddleware
from langgraph.checkpoint.memory import InMemorySaver

agent = create_agent(
    model="gpt-5.5", tools=[send_email, read_email], checkpointer=InMemorySaver(),
    middleware=[HumanInTheLoopMiddleware(interrupt_on={
        "send_email": {"allowed_decisions": ["approve", "edit", "reject"]},
        "read_email": False,
    })],
)
```

Related:

* [20261014082400](../20261014082400) HITL decisions: approve, edit, reject, respond -- what the reviewer can answer

* [20261014091600](../20261014091600) interrupt() pauses a graph for human input -- built on LangGraph interrupts

* [20261014080800](../20261014080800) Short-term memory = checkpointer + thread_id -- needs a checkpointer and thread_id

* [20261014090200](../20261014090200) interrupt_on adds human approval to a deep agent -- deep agents expose it as interrupt_on

* [20261014092100](../20261014092100) Agent Inbox: notify, question and review interrupts -- ambient agents surface these interrupts

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Human-in-the-loop\
  <https://docs.langchain.com/oss/python/langchain/human-in-the-loop>

* Intro to LangChain, Module 3 Lesson 3: Human In The Loop\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #human-in-the-loop #middleware #exam-build
