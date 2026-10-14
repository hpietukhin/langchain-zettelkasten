# Defining subagents with dicts or CompiledSubAgent

A `SubAgent` dict has `name`, `description` (what the supervisor sees when choosing), `system_prompt`, `tools`, and optional `model` and `middleware`. For custom workflows wrap a prebuilt graph (with a `messages` state key) as `CompiledSubAgent(name, description, runnable)`. The supervisor launches subagents with the `task` tool.

```python
from deepagents import CompiledSubAgent, create_deep_agent
from langchain.agents import create_agent

analyzer = CompiledSubAgent(
    name="data-analyzer",
    description="Specialized agent for complex data analysis tasks",
    runnable=create_agent("openai:gpt-5.5", tools=[run_sql]),
)
agent = create_deep_agent(model="openai:gpt-5.5", subagents=[analyzer])
```

Related:

* [20261014084300](../20261014084300) Context isolation: subagents quarantine heavy work -- why

* [20261014084500](../20261014084500) The general-purpose subagent is added automatically -- the default subagent

* [20261014084600](../20261014084600) Async subagents run in the background -- non-blocking variant

* [20261014085700](../20261014085700) FilesystemPermission rules gate built-in file tools -- subagents inherit permissions

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Subagents\
  <https://docs.langchain.com/oss/python/deepagents/subagents>

* Deep Agents course, Module 4 Lesson 2: Building a Subagent Team\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #deep-agents-foundations #delegation #building-a-subagent-team #exam-build
