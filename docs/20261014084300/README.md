# Context isolation: subagents quarantine heavy work

Tools with large outputs fill the context window quickly ("context bloat"). Delegating a subtask to a subagent means the dozens of intermediate tool calls live in the subagent's context; the supervisor receives only the final result. Don't use subagents for simple single-step tasks or when the supervisor needs the intermediate details.

```python
agent = create_deep_agent(model="openai:gpt-5.5", subagents=[{
    "name": "research-agent",
    "description": "Used to research more in-depth questions",
    "system_prompt": "You are a great researcher. Return a concise summary.",
    "tools": [internet_search],
}])
```

Related:

* [20261014084400](../20261014084400) Defining subagents with dicts or CompiledSubAgent -- how to define them

* [20261014081300](../20261014081300) Subagents pattern: wrap a specialist agent as a tool -- same idea in plain LangChain

* [20261014084000](../20261014084000) Five kinds of context in a deep agent -- one of the context categories

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Subagents\
  <https://docs.langchain.com/oss/python/deepagents/subagents>

* Deep Agents course, Module 4 Lesson 1: Delegation\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #deep-agents-foundations #delegation #context-management #exam-build
