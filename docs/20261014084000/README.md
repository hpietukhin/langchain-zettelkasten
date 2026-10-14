# Five kinds of context in a deep agent

Deep Agents docs distinguish: *input context* (system prompt, memory, skills; at startup), *runtime context* (static invoke-time config that also propagates to subagents), *context compression* (offloading and summarization, automatic near limits), *context isolation* (subagents quarantine heavy work) and *long-term memory* (files persisted across threads). Context engineering for long-running agents is mostly about keeping the active window small and relevant.

```python
agent = create_deep_agent(
    model="openai:gpt-5.5",
    system_prompt="...",              # input context
    memory=["/memories/AGENTS.md"],   # input context, always loaded
    skills=["/skills/"],              # input context, progressive disclosure
    subagents=[researcher],           # isolation
    context_schema=Ctx,               # runtime context
)                                     # compression is built in
```

Related:

* [20261014083900](../20261014083900) A deep agent's system_prompt is prepended to a built-in prompt -- input context

* [20261014081000](../20261014081000) Runtime context is static per-invocation configuration -- runtime context

* [20261014084100](../20261014084100) Offloading moves large tool payloads to the filesystem -- compression

* [20261014084200](../20261014084200) Deep agents summarise history at about 85% of the window -- compression

* [20261014084300](../20261014084300) Context isolation: subagents quarantine heavy work -- isolation

* [20261014090100](../20261014090100) Agent-scoped vs user-scoped memory via store namespaces -- long-term memory

* [20261014083400](../20261014083400) Context engineering: model, tool and life-cycle context -- the general LangChain framing

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Context engineering\
  <https://docs.langchain.com/oss/python/deepagents/context-engineering>

* Deep Agents course, Module 3: Context Management\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #deep-agents-foundations #context-management #context-engineering #exam-build
