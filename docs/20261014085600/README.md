# Interpreters give agents an in-memory code workspace

An interpreter (beta) lets the agent write code that runs inside the agent loop in memory; only the relevant results are returned, intermediate values never enter the context. Lighter than a sandbox, but not a replacement for OS-level isolation.

```python
# pseudo-example (beta API may change): the model writes code, the runtime returns a small result
# agent -> code: "rows = query(); return sum(r['amount'] for r in rows)"
# runtime -> "42137.50"   (the raw rows never enter the context window)
```

Related:

* [20261014085200](../20261014085200) Sandboxes isolate code execution from the host -- contrast: full OS isolation

* [20261014084300](../20261014084300) Context isolation: subagents quarantine heavy work -- both keep intermediate results out of context

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Interpreters\
  <https://docs.langchain.com/oss/python/deepagents/interpreters>

* Deep Agents course, Module 2 Lesson 4: Interpreter\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #deep-agents-foundations #execution-environment #exam-build
