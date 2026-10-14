# Checkpoints snapshot state at every super-step

A checkpointer saves a `StateSnapshot` per step, grouped by `thread_id`. This enables memory, human-in-the-loop, time travel and fault tolerance (resume from the last good step). `graph.get_state(config)` returns the latest snapshot.

```python
from langgraph.checkpoint.memory import InMemorySaver
graph = builder.compile(checkpointer=InMemorySaver())
cfg = {"configurable": {"thread_id": "1"}}
graph.invoke({"text": "hi"}, cfg)
print(graph.get_state(cfg).values)
```

Related:

* [20261014080800](../20261014080800) Short-term memory = checkpointer + thread_id -- what the agent sees

* [20261014091500](../20261014091500) Time travel: replay or fork from a past checkpoint -- replay and fork from checkpoints

* [20261014091600](../20261014091600) interrupt() pauses a graph for human input -- interrupts rely on checkpoints

* [20261014091800](../20261014091800) Durability modes trade speed for crash safety -- when checkpoints are written

* [20261014095700](../20261014095700) Storage durability on LangSmith Deployment -- Postgres on the Agent Server

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangGraph docs: Persistence\
  <https://docs.langchain.com/oss/python/langgraph/persistence>

* Intro to LangGraph, Module 2: Chatbot w/ memory\
  <https://academy.langchain.com/courses/intro-to-langgraph>

Tags:

    #intro-to-langgraph #langgraph-persistence #langgraph-memory #storage-durability #exam-build
