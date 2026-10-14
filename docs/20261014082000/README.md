# Dynamic model and tool selection with request.override

Inside `wrap_model_call` you can replace the model, tools, messages or response format for a single call via `request.override(...)`, e.g. use a cheaper model for short conversations or expose admin tools only to admins.

```python
from langchain.agents.middleware import wrap_model_call
from langchain.chat_models import init_chat_model

big, small = init_chat_model("openai:gpt-5.5"), init_chat_model("openai:gpt-5.4-mini")

@wrap_model_call
def pick_model(request, handler):
    model = big if len(request.messages) > 10 else small
    return handler(request.override(model=model))
```

Related:

* [20261014081700](../20261014081700) Wrap-style hooks intercept model and tool calls -- implemented as wrap_model_call

* [20261014080300](../20261014080300) Models are chosen with provider:model strings or init_chat_model -- models to switch between

* [20261014082900](../20261014082900) LLMToolSelectorMiddleware narrows large toolsets -- prebuilt dynamic tool filtering

* [20261014082600](../20261014082600) ModelFallbackMiddleware tries alternative models on failure -- prebuilt switching on failure

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Context engineering\
  <https://docs.langchain.com/oss/python/langchain/context-engineering>

* Intro to LangChain, Module 3 Lesson 4: Dynamic Agents\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #dynamic-agents #middleware #exam-build
