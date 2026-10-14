# Call-limit middleware stops runaway loops

`ModelCallLimitMiddleware` caps model calls per thread (`thread_limit`) and per invocation (`run_limit`); `ToolCallLimitMiddleware` does the same for all tools or one `tool_name`. `exit_behavior` decides whether to end gracefully or raise. They protect against infinite loops and cost blow-ups.

```python
from langchain.agents.middleware import ModelCallLimitMiddleware, ToolCallLimitMiddleware

agent = create_agent(model="gpt-5.5", tools=[search], middleware=[
    ModelCallLimitMiddleware(thread_limit=10, run_limit=5, exit_behavior="end"),
    ToolCallLimitMiddleware(tool_name="search", thread_limit=5, run_limit=3),
])
```

Related:

* [20261014081500](../20261014081500) Middleware hooks into every step of the agent loop -- a built-in middleware

* [20261014083100](../20261014083100) Catalogue of built-in middleware -- sibling middleware

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Built-in middleware\
  <https://docs.langchain.com/oss/python/langchain/middleware/built-in>

Tags:

    #langchain-foundations #middleware #guardrails #exam-build
