# StateBackend: ephemeral files in thread state

Files are stored in LangGraph state, so they persist across turns of the same thread (via the checkpointer) but are invisible to other threads. Ideal scratch space for offloading and notes; nothing touches the host.

```python
from deepagents.backends import StateBackend
agent = create_deep_agent(model="openai:gpt-5.5", backend=StateBackend(),
                          checkpointer=InMemorySaver())
```

Related:

* [20261014084700](../20261014084700) Backends decide where a deep agent's files live -- one of the backends

* [20261014080800](../20261014080800) Short-term memory = checkpointer + thread_id -- persists with the thread's checkpoints

* [20261014085000](../20261014085000) StoreBackend makes files durable across threads -- use for cross-thread durability

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Backends\
  <https://docs.langchain.com/oss/python/deepagents/backends>

Tags:

    #deep-agents-foundations #filesystem-backends #storage-durability #exam-build
