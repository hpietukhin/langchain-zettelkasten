# Threads and checkpointers in deep agents

A deep agent is a LangGraph graph: pass `checkpointer=` locally and use `thread_id` to continue a conversation, including its todos and StateBackend files. HITL resume requires the same thread. On LangSmith Deployment the server injects persistence.

```python
from langgraph.checkpoint.memory import MemorySaver
agent = create_deep_agent(model="openai:gpt-5.5", checkpointer=MemorySaver())
cfg = {"configurable": {"thread_id": "research-42"}}
agent.invoke({"messages": [{"role": "user", "content": "Start the report"}]}, cfg)
```

Related:

* [20261014080800](../20261014080800) Short-term memory = checkpointer + thread_id -- same mechanism as create_agent

* [20261014084800](../20261014084800) StateBackend: ephemeral files in thread state -- state-backed files persist with checkpoints

* [20261014095800](../20261014095800) Don't configure a checkpointer or store in deployed graph code -- omit the checkpointer when deploying

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents course, Module 1 Lesson 7: Messages, Threads, and Checkpointers\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

* Deep Agents docs: Human-in-the-loop\
  <https://docs.langchain.com/oss/python/deepagents/human-in-the-loop>

Tags:

    #deep-agents-foundations #short-term-memory #exam-build
