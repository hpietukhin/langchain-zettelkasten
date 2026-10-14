# Sandbox lifecycle: thread-scoped or assistant-scoped

Most apps choose one sandbox per thread (isolation per conversation/user) or one per assistant (shared state, cheaper). Sandboxes cost money while running; always shut them down (e.g. `try/finally`, TTLs).

```python
sandbox = Daytona().create()
try:
    agent = create_deep_agent(model="openai:gpt-5.5", backend=DaytonaSandbox(sandbox=sandbox))
    agent.invoke({"messages": [{"role": "user", "content": "Run pytest"}]})
finally:
    sandbox.stop()
```

Related:

* [20261014085200](../20261014085200) Sandboxes isolate code execution from the host -- what is being scoped

* [20261014100200](../20261014100200) Threads hold state, runs execute; stateless and background runs -- a thread is a conversation

* [20261014100100](../20261014100100) Assistants version configuration separately from code -- an assistant is a configured graph

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Sandboxes\
  <https://docs.langchain.com/oss/python/deepagents/sandboxes>

* Deep Agents docs: Going to production\
  <https://docs.langchain.com/oss/python/deepagents/going-to-production>

Tags:

    #deep-agents-foundations #sandboxing #langsmith-deployment-foundations #exam-build
