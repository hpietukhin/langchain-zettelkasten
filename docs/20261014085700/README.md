# FilesystemPermission rules gate built-in file tools

`permissions=[FilesystemPermission(operations, paths, mode)]` with `mode` `allow`, `deny` or `interrupt`. Rules are first-match-wins; if none match, access is allowed. They apply only to built-in filesystem tools, not to custom/MCP tools or the `execute` command in sandboxes. Subagents inherit the parent's rules unless their spec overrides them.

```python
from deepagents import FilesystemPermission, create_deep_agent

agent = create_deep_agent(model="openai:gpt-5.5", permissions=[
    FilesystemPermission(operations=["write"], paths=["/secrets/**"], mode="interrupt"),
    FilesystemPermission(operations=["write"], paths=["/**"], mode="deny"),
], checkpointer=InMemorySaver())
```

Related:

* [20261014084700](../20261014084700) Backends decide where a deep agent's files live -- permissions sit on top of a backend

* [20261014090200](../20261014090200) interrupt_on adds human approval to a deep agent -- mode interrupt raises HITL

* [20261014085200](../20261014085200) Sandboxes isolate code execution from the host -- permissions don't stop shell access in sandboxes

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Permissions\
  <https://docs.langchain.com/oss/python/deepagents/permissions>

Tags:

    #deep-agents-foundations #execution-environment #sandboxing #exam-build
