# Deep Agents is a batteries-included agent harness

`deepagents` is LangChain's open-source harness for long-running, complex tasks. `create_deep_agent` builds on `create_agent` and pre-wires planning (`write_todos`), a virtual filesystem, subagent delegation (`task`), context compression (offloading + summarization), memory (`AGENTS.md`), skills (`SKILL.md`) and optional sandboxed execution. It returns a LangGraph graph, so persistence, streaming and deployment work the same way.

```python
from deepagents import create_deep_agent

agent = create_deep_agent(
    model="openai:gpt-5.5",
    system_prompt="You are a helpful assistant.",
    tools=[search, fetch_url],
    memory=["./AGENTS.md"],
    skills=["./skills/"],
)
```

Related:

* [20261014080100](../20261014080100) Agent = model + harness -- what a harness is

* [20261014083600](../20261014083600) create_agent vs create_deep_agent: when to use which -- how it differs from create_agent

* [20261014083700](../20261014083700) Deep agents' built-in tools -- the tools it adds

* [20261014083800](../20261014083800) The Deep Agents middleware stack -- it is assembled from middleware

* [20261014084700](../20261014084700) Backends decide where a deep agent's files live -- pluggable execution environment

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Overview\
  <https://docs.langchain.com/oss/python/deepagents/overview>

* Deep Agents course, Module 1 Lesson 1: Deep Agents Overview\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #deep-agents-foundations #deep-agents-overview #agent-harness #exam-build
