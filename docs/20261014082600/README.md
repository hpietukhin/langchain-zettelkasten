# ModelFallbackMiddleware tries alternative models on failure

If the primary model call errors, the listed fallback models are tried in order. This improves availability across provider outages without changing agent logic.

```python
from langchain.agents.middleware import ModelFallbackMiddleware

agent = create_agent(model="gpt-5.5", tools=[],
                     middleware=[ModelFallbackMiddleware("gpt-5.4-mini", "claude-3-5-sonnet-20241022")])
```

Related:

* [20261014082700](../20261014082700) Retry middleware handles transient tool and model errors -- retry the same model first

* [20261014080300](../20261014080300) Models are chosen with provider:model strings or init_chat_model -- fallbacks are model strings or instances

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Built-in middleware\
  <https://docs.langchain.com/oss/python/langchain/middleware/built-in>

Tags:

    #langchain-foundations #middleware #production-ready-agent #exam-build
