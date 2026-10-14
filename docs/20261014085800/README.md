# AGENTS.md is always-loaded memory

Files passed via `memory=[...]` (conventionally `AGENTS.md`) are injected into the system prompt on every run: project conventions, preferences, critical rules. No progressive disclosure, so keep it short. The agent can update it with `edit_file`, which is how it "learns".

```python
agent = create_deep_agent(model="openai:gpt-5.5", memory=["/memories/AGENTS.md"],
                          backend=CompositeBackend(default=StateBackend(),
                                                   routes={"/memories/": StoreBackend()}))
```

Related:

* [20261014085900](../20261014085900) SKILL.md skills use progressive disclosure -- contrast: loaded on demand

* [20261014090100](../20261014090100) Agent-scoped vs user-scoped memory via store namespaces -- where the file lives decides who shares it

* [20261014085100](../20261014085100) CompositeBackend routes path prefixes to different backends -- typically on a store route

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Memory\
  <https://docs.langchain.com/oss/python/deepagents/memory>

* Deep Agents docs: Context engineering\
  <https://docs.langchain.com/oss/python/deepagents/context-engineering>

* Deep Agents course, Module 3 Lesson 3: Memory\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #deep-agents-foundations #context-management #agents-md #memory #exam-build
