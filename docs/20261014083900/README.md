# A deep agent's system_prompt is prepended to a built-in prompt

The final prompt = your `system_prompt` + built-in guidance for filesystem tools, todos and subagents + memory files + skill metadata + tool descriptions. `system_prompt` is static; for per-user variation use `@dynamic_prompt` middleware that reads `request.runtime.context` or the store.

```python
agent = create_deep_agent(
    model="openai:gpt-5.5",
    system_prompt="You are a research assistant. Always cite sources. "
                  "Use subagents for parallel research on different topics.",
)
```

Related:

* [20261014081900](../20261014081900) @dynamic_prompt computes the system prompt per model call -- use middleware when the prompt must vary

* [20261014085800](../20261014085800) AGENTS.md is always-loaded memory -- memory is also injected into the prompt

* [20261014090400](../20261014090400) Harness profiles tune the harness per provider or model -- base_system_prompt / system_prompt_suffix per model

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Context engineering\
  <https://docs.langchain.com/oss/python/deepagents/context-engineering>

* Deep Agents course, Lesson 4: The System Prompt\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #deep-agents-foundations #deep-agents-system-prompt #context-engineering #exam-build
