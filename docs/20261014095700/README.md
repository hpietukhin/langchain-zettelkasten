# Storage durability on LangSmith Deployment

Three kinds of data persist in PostgreSQL: core resources (assistants, threads, runs, crons), checkpoints (short-term memory, one per step, making runs resumable), and the store (long-term memory across threads; replaceable with a custom store). Redis holds nothing durable. Durability of in-progress runs depends on the durability mode. Data lives until deleted or expired by TTL.

```python
# reading durable storage from a client
state = await client.threads.get_state(thread_id)                          # checkpoints
await client.store.put_item(("users", "u1"), key="prefs", value={"tone": "brief"})  # store
```

Related:

* [20261014095600](../20261014095600) The Agent Server: API server, Postgres and Redis task queue -- components

* [20261014091400](../20261014091400) Checkpoints snapshot state at every super-step -- short-term memory

* [20261014091900](../20261014091900) The LangGraph store: namespaces, keys and search -- long-term memory

* [20261014101200](../20261014101200) TTLs bound how long threads, checkpoints and store items live -- controlling retention

* [20261014091800](../20261014091800) Durability modes trade speed for crash safety -- write timing

* [20261014101300](../20261014101300) Encryption at rest for Agent Server data -- protecting stored data

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Agent Server\
  <https://docs.langchain.com/langsmith/agent-server>

* LangSmith Deployment course, Module 4: Memory\
  <https://academy.langchain.com/courses/langsmith-deployment>

Tags:

    #langsmith-deployment-foundations #memory #storage-durability #exam-deploy
