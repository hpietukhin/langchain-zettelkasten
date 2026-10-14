# Agent = model + harness

LangChain frames an agent as a model plus a harness: the prompt, the tools, and middleware that shape behaviour. The job of a harness is to get the model the right context at the right time. `create_agent` is a lean, highly configurable harness; `create_deep_agent` is a heavier harness that pre-installs planning, a filesystem, subagents and context compression.

```python
from langchain.agents import create_agent
from deepagents import create_deep_agent

lean = create_agent(model="openai:gpt-5.5", tools=[search])          # you add what you need
deep = create_deep_agent(model="openai:gpt-5.5", tools=[search])     # planning, files, subagents built in
```

Related:

* [20261014080000](../20261014080000) An agent is a model calling tools in a loop -- the loop the harness wraps

* [20261014080200](../20261014080200) create_agent builds a production agent graph -- a minimal, configurable harness

* [20261014083500](../20261014083500) Deep Agents is a batteries-included agent harness -- an opinionated, batteries-included harness

* [20261014083400](../20261014083400) Context engineering: model, tool and life-cycle context -- the harness's job is context engineering

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Agents\
  <https://docs.langchain.com/oss/python/langchain/agents>

* Deep Agents course, Lesson 1: Deep Agents Overview\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #langchain-foundations #deep-agents-foundations #agent-harness #context-engineering #exam-build
