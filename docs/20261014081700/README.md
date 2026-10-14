# Wrap-style hooks intercept model and tool calls

`wrap_model_call` and `wrap_tool_call` receive the request and a `handler`. You decide whether to call the handler zero, one or many times, and can modify the request (`request.override(...)`) or the response. This is the right shape for retries, caching, fallbacks and per-call model or tool changes.

```python
from typing import Callable
from langchain.agents.middleware import wrap_model_call, ModelRequest, ModelResponse

@wrap_model_call
def retry_model(request: ModelRequest, handler: Callable[[ModelRequest], ModelResponse]) -> ModelResponse:
    for attempt in range(3):
        try:
            return handler(request)
        except Exception:
            if attempt == 2:
                raise
```

Related:

* [20261014081600](../20261014081600) Node-style hooks run before or after agent and model steps -- contrast: sequential hooks

* [20261014082000](../20261014082000) Dynamic model and tool selection with request.override -- a wrap_model_call use case

* [20261014082700](../20261014082700) Retry middleware handles transient tool and model errors -- prebuilt retry uses this shape

* [20261014081900](../20261014081900) @dynamic_prompt computes the system prompt per model call -- a specialised wrap hook

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Custom middleware\
  <https://docs.langchain.com/oss/python/langchain/middleware/custom>

Tags:

    #langchain-foundations #middleware #exam-build
