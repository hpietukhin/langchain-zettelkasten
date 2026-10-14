# Agent-scoped vs user-scoped memory via store namespaces

With namespace `(assistant_id,)` every conversation for that agent shares the same memory files: the agent builds one evolving persona. With `(user_id,)` each user gets an isolated copy, so preferences never leak between users. Skills can be scoped the same way.

```python
backend = CompositeBackend(
    default=StateBackend(),
    routes={"/memories/": StoreBackend(namespace=lambda rt: (rt.server_info.user.identity,))},  # per user
)
```

Related:

* [20261014085000](../20261014085000) StoreBackend makes files durable across threads -- namespace function on StoreBackend

* [20261014091900](../20261014091900) The LangGraph store: namespaces, keys and search -- same tuple namespaces

* [20261014100700](../20261014100700) Authentication vs authorization -- user identity comes from auth

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Memory\
  <https://docs.langchain.com/oss/python/deepagents/memory>

Tags:

    #deep-agents-foundations #memory #langsmith-deployment-foundations #exam-build
