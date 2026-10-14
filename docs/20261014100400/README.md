# Double texting strategies: enqueue, reject, interrupt, rollback

When a user sends a new message while a run on the same thread is still active, `multitask_strategy` decides: `enqueue` (default; run the new one after), `reject` (refuse the new one), `interrupt` (stop the current run, keep its progress, start the new one), `rollback` (stop and delete the current run, then start the new one).

```python
await client.runs.create(thread_id, "agent", input=new_msg, multitask_strategy="interrupt")
```

Related:

* [20261014100200](../20261014100200) Threads hold state, runs execute; stateless and background runs -- concurrent runs on one thread

* [20261014095600](../20261014095600) The Agent Server: API server, Postgres and Redis task queue -- the queue that orders runs

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Double texting\
  <https://docs.langchain.com/langsmith/double-texting>

Tags:

    #langsmith-deployment-foundations #agent-server #exam-deploy
