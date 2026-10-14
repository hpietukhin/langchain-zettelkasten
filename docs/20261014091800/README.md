# Durability modes trade speed for crash safety

`durability` controls when checkpoints are written: `"exit"` (only when the run ends: fastest, least safe), `"async"` (written in the background while the next step runs: Agent Server default) and `"sync"` (written before the next step starts: safest, slowest).

```python
graph.invoke(inputs, cfg, durability="sync")
```

Related:

* [20261014091400](../20261014091400) Checkpoints snapshot state at every super-step -- what is being persisted

* [20261014095700](../20261014095700) Storage durability on LangSmith Deployment -- Agent Server default is async

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangGraph docs: Persistence\
  <https://docs.langchain.com/oss/python/langgraph/persistence>

* LangSmith docs: Agent Server\
  <https://docs.langchain.com/langsmith/agent-server>

Tags:

    #intro-to-langgraph #langgraph-persistence #storage-durability #exam-deploy
