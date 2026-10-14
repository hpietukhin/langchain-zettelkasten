# FilesystemBackend reads and writes the real local disk

`FilesystemBackend(root_dir=...)` gives the agent real files under a root directory (useful for coding agents on your machine). There is no execution and no isolation beyond the root; combine with permissions or use a sandbox in production.

```python
from deepagents.backends.filesystem import FilesystemBackend
agent = create_deep_agent(model="openai:gpt-5.5", backend=FilesystemBackend(root_dir="./project"))
```

Related:

* [20261014084700](../20261014084700) Backends decide where a deep agent's files live -- one of the backends

* [20261014085700](../20261014085700) FilesystemPermission rules gate built-in file tools -- restrict what it can touch

* [20261014085200](../20261014085200) Sandboxes isolate code execution from the host -- prefer sandboxes for untrusted work

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Backends\
  <https://docs.langchain.com/oss/python/deepagents/backends>

Tags:

    #deep-agents-foundations #filesystem-backends #sandboxing #exam-build
