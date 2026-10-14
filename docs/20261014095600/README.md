# The Agent Server: API server, Postgres and Redis task queue

A deployment consists of graph(s), PostgreSQL for persistence, and a task queue. Clients create runs; the API server enqueues them; queue workers execute them and publish events for streaming. Redis only carries ephemeral signalling (cancellation, streaming pub/sub); no run data persists in Redis. Retriable failures resume from the last checkpoint.

```python
# client -> POST /threads/{id}/runs  -> queue (Redis signal) -> worker executes graph
#        <- /stream events            <- worker publishes      -> Postgres: threads, runs, checkpoints, store
```

Related:

* [20261014095700](../20261014095700) Storage durability on LangSmith Deployment -- what is stored in Postgres

* [20261014100200](../20261014100200) Threads hold state, runs execute; stateless and background runs -- resources it exposes

* [20261014100400](../20261014100400) Double texting strategies: enqueue, reject, interrupt, rollback -- concurrency on a thread

* [20261014095400](../20261014095400) Deployment terminology: graph, deployment, revision, assistant, thread, run -- terminology

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Agent Server\
  <https://docs.langchain.com/langsmith/agent-server>

Tags:

    #langsmith-deployment-foundations #agent-server #storage-durability #exam-deploy
