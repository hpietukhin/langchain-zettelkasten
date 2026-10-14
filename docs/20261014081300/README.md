# Subagents pattern: wrap a specialist agent as a tool

In the subagents (supervisor) pattern a main agent calls worker agents through tools. The worker runs with its own prompt and tools, and only its final answer returns to the supervisor. The supervisor keeps control of the conversation; the workers are stateless helpers. The course's Wedding Planner project uses this shape.

```python
from langchain.agents import create_agent

subagent = create_agent(model="openai:gpt-5.5", tools=[web_search])

def call_research_agent(query: str):
    """Research a topic and return a summary."""
    result = subagent.invoke({"messages": [{"role": "user", "content": query}]})
    return result["messages"][-1].content

main_agent = create_agent(model="openai:gpt-5.5", tools=[call_research_agent])
```

Related:

* [20261014081400](../20261014081400) Handoffs pattern: the active agent changes via state -- the alternative pattern

* [20261014084300](../20261014084300) Context isolation: subagents quarantine heavy work -- why delegation keeps context clean

* [20261014084400](../20261014084400) Defining subagents with dicts or CompiledSubAgent -- deep agents' built-in version (task tool)

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Multi-agent subagents\
  <https://docs.langchain.com/oss/python/langchain/multi-agent/subagents>

* Intro to LangChain, Module 2 Lesson 3: Multi-Agent Systems\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #multi-agent-systems #exam-build
