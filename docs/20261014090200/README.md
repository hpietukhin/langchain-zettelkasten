# interrupt_on adds human approval to a deep agent

`create_deep_agent(interrupt_on={...})` configures `HumanInTheLoopMiddleware`: `True` (approve/edit/reject/respond), `False`, or an `InterruptOnConfig` with `allowed_decisions` and an optional `when` predicate for conditional interrupts. Interrupts also apply inside subagents.

```python
agent = create_deep_agent(
    model="openai:gpt-5.5", tools=[remove_file, fetch_file],
    interrupt_on={"remove_file": True, "fetch_file": False},
    checkpointer=MemorySaver(),
)
```

Related:

* [20261014082300](../20261014082300) HumanInTheLoopMiddleware pauses before sensitive tool calls -- the underlying middleware

* [20261014082400](../20261014082400) HITL decisions: approve, edit, reject, respond -- decision types

* [20261014090300](../20261014090300) Threads and checkpointers in deep agents -- a checkpointer is required

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Human-in-the-loop\
  <https://docs.langchain.com/oss/python/deepagents/human-in-the-loop>

* Deep Agents course, Module 1 Lesson 8: HITL\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #deep-agents-foundations #human-in-the-loop #exam-build
