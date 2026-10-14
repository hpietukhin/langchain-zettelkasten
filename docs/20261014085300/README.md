# Two patterns: agent inside the sandbox vs sandbox as a tool

Either the whole agent runs inside the sandbox and acts on its local filesystem, or the agent runs outside (e.g. in a long-lived server) and executes commands in a remote sandbox over the network. Deep Agents supports both via backends; the second keeps API keys and the agent loop outside the untrusted environment.

```python
# sandbox as a tool: agent runs on the Agent Server, commands run remotely
agent = create_deep_agent(model="openai:gpt-5.5", backend=DaytonaSandbox(sandbox=Daytona().create()))
```

Related:

* [20261014085200](../20261014085200) Sandboxes isolate code execution from the host -- what a sandbox is

* [20261014085400](../20261014085400) Sandbox lifecycle: thread-scoped or assistant-scoped -- who shares a sandbox

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Comparison with Claude Agent SDK\
  <https://docs.langchain.com/oss/python/deepagents/comparison>

* Deep Agents docs: Sandboxes\
  <https://docs.langchain.com/oss/python/deepagents/sandboxes>

Tags:

    #deep-agents-foundations #sandboxing #exam-build
