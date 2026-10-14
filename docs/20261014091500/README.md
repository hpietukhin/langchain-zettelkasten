# Time travel: replay or fork from a past checkpoint

`get_state_history(config)` lists prior checkpoints. Invoking with a past checkpoint's config replays from there; `update_state` creates a new forked checkpoint with edited values, letting you debug or explore alternatives.

```python
history = list(graph.get_state_history(cfg))
past = history[2].config
fork_cfg = graph.update_state(past, {"text": "edited"})
graph.invoke(None, fork_cfg)   # continue from the fork
```

Related:

* [20261014091400](../20261014091400) Checkpoints snapshot state at every super-step -- history to travel through

* [20261014091600](../20261014091600) interrupt() pauses a graph for human input -- edit state during a pause

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangGraph docs: Persistence\
  <https://docs.langchain.com/oss/python/langgraph/persistence>

* Intro to LangGraph, Module 3: Time travel\
  <https://academy.langchain.com/courses/intro-to-langgraph>

Tags:

    #intro-to-langgraph #human-in-the-loop #langgraph-persistence #exam-build
