# Sandboxes isolate code execution from the host

Because you cannot predict what an agent will run, give it an isolated environment that cannot reach your credentials, files or network. A sandbox backend provides the filesystem tools plus `execute`. Providers include LangSmith Sandboxes (first-party), Daytona and others.

```python
from deepagents import create_deep_agent
from deepagents.backends import LangSmithSandbox
from langsmith.sandbox import SandboxClient

ls_sandbox = SandboxClient().create_sandbox()
agent = create_deep_agent(model="anthropic:claude-sonnet-4-6",
                          system_prompt="You are a Python coding assistant with sandbox access.",
                          backend=LangSmithSandbox(sandbox=ls_sandbox))
```

Related:

* [20261014084700](../20261014084700) Backends decide where a deep agent's files live -- sandboxes are backends

* [20261014085300](../20261014085300) Two patterns: agent inside the sandbox vs sandbox as a tool -- agent in sandbox vs sandbox as tool

* [20261014085400](../20261014085400) Sandbox lifecycle: thread-scoped or assistant-scoped -- lifecycle and cost

* [20261014085500](../20261014085500) LocalShellBackend runs commands on the host without isolation -- the unsafe alternative

* [20261014085700](../20261014085700) FilesystemPermission rules gate built-in file tools -- permissions don't constrain sandboxes

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Sandboxes\
  <https://docs.langchain.com/oss/python/deepagents/sandboxes>

* Deep Agents course, Module 2 Lesson 3: Sandboxes and LocalShell\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

* LangSmith docs: Sandboxes\
  <https://docs.langchain.com/langsmith/sandboxes>

Tags:

    #deep-agents-foundations #execution-environment #sandboxing #exam-build
