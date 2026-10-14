# CompositeBackend routes path prefixes to different backends

A composite backend has a `default` and `routes` keyed by path prefix. The common pattern: scratch files thread-scoped in state, but `/memories/` (and `/skills/`) persisted in the store, giving the agent one filesystem with mixed durability.

```python
from deepagents.backends import CompositeBackend, StateBackend, StoreBackend

backend = CompositeBackend(
    default=StateBackend(),
    routes={"/memories/": StoreBackend(namespace=lambda rt: (rt.server_info.assistant_id,))},
)
agent = create_deep_agent(model="openai:gpt-5.5", backend=backend, memory=["/memories/AGENTS.md"])
```

Related:

* [20261014084800](../20261014084800) StateBackend: ephemeral files in thread state -- typical default route

* [20261014085000](../20261014085000) StoreBackend makes files durable across threads -- typical /memories/ route

* [20261014085800](../20261014085800) AGENTS.md is always-loaded memory -- memory files under /memories/

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Backends\
  <https://docs.langchain.com/oss/python/deepagents/backends>

* Deep Agents docs: Memory\
  <https://docs.langchain.com/oss/python/deepagents/memory>

Tags:

    #deep-agents-foundations #filesystem-backends #memory #exam-build
