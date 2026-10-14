# LocalShellBackend runs commands on the host without isolation

`LocalShellBackend(root_dir, env)` exposes files and an `execute` tool directly on the host. No isolation: only for controlled local development. Restrict `env` (e.g. PATH) and never use it for untrusted input in production.

```python
from deepagents.backends import LocalShellBackend
agent = create_deep_agent(model="openai:gpt-5.5",
                          backend=LocalShellBackend(root_dir=".", env={"PATH": "/usr/bin:/bin"}))
```

Related:

* [20261014085200](../20261014085200) Sandboxes isolate code execution from the host -- the safe alternative

* [20261014084900](../20261014084900) FilesystemBackend reads and writes the real local disk -- files only, no execution

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Backends\
  <https://docs.langchain.com/oss/python/deepagents/backends>

Tags:

    #deep-agents-foundations #sandboxing #execution-environment #exam-build
