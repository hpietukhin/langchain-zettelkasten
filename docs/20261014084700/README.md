# Backends decide where a deep agent's files live

The filesystem tools are an interface; a pluggable backend implements them. Built-ins: `StateBackend` (default, in graph state), `FilesystemBackend` (local disk), `StoreBackend` (LangGraph store), `ContextHubBackend` (LangSmith Hub repo), sandbox backends (+`execute`), `LocalShellBackend` (host shell, +`execute`), and `CompositeBackend` to route path prefixes to different backends. Custom backends implement the backend protocol.

```python
from deepagents import create_deep_agent
from deepagents.backends import StateBackend

agent = create_deep_agent(model="openai:gpt-5.5", backend=StateBackend())  # same as the default
```

Related:

* [20261014084800](../20261014084800) StateBackend: ephemeral files in thread state -- default, thread-scoped

* [20261014084900](../20261014084900) FilesystemBackend reads and writes the real local disk -- real disk

* [20261014085000](../20261014085000) StoreBackend makes files durable across threads -- durable across threads

* [20261014085100](../20261014085100) CompositeBackend routes path prefixes to different backends -- route paths

* [20261014085200](../20261014085200) Sandboxes isolate code execution from the host -- isolated execution

* [20261014085700](../20261014085700) FilesystemPermission rules gate built-in file tools -- path rules on top

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Backends\
  <https://docs.langchain.com/oss/python/deepagents/backends>

* Deep Agents course, Module 2 Lesson 2: The Filesystem Backends\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #deep-agents-foundations #execution-environment #filesystem-backends #exam-build
