# TTLs bound how long threads, checkpoints and store items live

`checkpointer.ttl` in `langgraph.json`: `strategy` `delete` (remove the whole thread with runs and checkpoints) or `keep_latest` (keep thread + latest checkpoint, prune older ones), `default_ttl` in minutes, `sweep_interval_minutes`. `store.ttl`: `default_ttl`, `refresh_on_read`. Without TTL nothing expires. Applies to new data; per-thread TTL can be set on `threads.create`.

```python
LANGGRAPH_JSON = {
    "checkpointer": {"ttl": {"strategy": "delete", "default_ttl": 43200, "sweep_interval_minutes": 10}},
    "store": {"ttl": {"default_ttl": 10080, "refresh_on_read": True}},
}
thread = await client.threads.create(ttl={"strategy": "delete", "ttl": 43200})
```

Related:

* [20261014095700](../20261014095700) Storage durability on LangSmith Deployment -- what is being expired

* [20261014095500](../20261014095500) langgraph.json declares graphs, dependencies and env -- configured in langgraph.json

* [20261014091900](../20261014091900) The LangGraph store: namespaces, keys and search -- store item TTL

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Configure TTL\
  <https://docs.langchain.com/langsmith/configure-ttl>

Tags:

    #langsmith-deployment-foundations #storage-durability #exam-deploy
