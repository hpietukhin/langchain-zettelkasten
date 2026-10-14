# The general-purpose subagent is added automatically

Unless you supply a synchronous subagent named `general-purpose`, Deep Agents adds one with the main agent's tools/filesystem, so the agent can always offload a subtask into a clean context. To run without the `task` tool, disable it via the harness profile (`GeneralPurposeSubagentProfile(enabled=False)`) and pass no synchronous subagents.

```python
# replace the default by name
agent = create_deep_agent(model="openai:gpt-5.5", subagents=[{
    "name": "general-purpose",
    "description": "General helper for isolated subtasks",
    "system_prompt": "Complete the task and report back briefly.",
}])
```

Related:

* [20261014084400](../20261014084400) Defining subagents with dicts or CompiledSubAgent -- custom subagents

* [20261014090400](../20261014090400) Harness profiles tune the harness per provider or model -- configured through the harness profile

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Subagents\
  <https://docs.langchain.com/oss/python/deepagents/subagents>

Tags:

    #deep-agents-foundations #delegation #exam-build
