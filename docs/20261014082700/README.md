# Retry middleware handles transient tool and model errors

`ToolRetryMiddleware` (and `ModelRetryMiddleware`) re-invoke failing calls with exponential backoff (`max_retries`, `backoff_factor`, `initial_delay`), optionally restricted to certain tools or exception types via `retry_on`.

```python
from langchain.agents.middleware import ToolRetryMiddleware

agent = create_agent(model="gpt-5.5", tools=[flaky_api],
                     middleware=[ToolRetryMiddleware(max_retries=3, backoff_factor=2.0, initial_delay=1.0)])
```

Related:

* [20261014082600](../20261014082600) ModelFallbackMiddleware tries alternative models on failure -- what to do when retries are not enough

* [20261014081700](../20261014081700) Wrap-style hooks intercept model and tool calls -- retries are wrap-style

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Built-in middleware\
  <https://docs.langchain.com/oss/python/langchain/middleware/built-in>

Tags:

    #langchain-foundations #middleware #production-ready-agent #exam-build
