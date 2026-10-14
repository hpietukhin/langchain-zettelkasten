# Models are chosen with provider:model strings or init_chat_model

A model can be given as a `"provider:model"` string (e.g. `"openai:gpt-5.5"`) or as an initialized chat model. `init_chat_model` creates a provider-agnostic chat model, so switching providers is a one-string change. Model *profiles* (e.g. `max_input_tokens`) feed features such as fraction-based summarization triggers.

```python
from langchain.chat_models import init_chat_model

model = init_chat_model("openai:gpt-5.5", temperature=0)
print(model.invoke("Say hi").content)
# a custom profile when provider data is missing
model2 = init_chat_model("gpt-5.5", profile={"max_input_tokens": 100_000})
```

Related:

* [20261014080200](../20261014080200) create_agent builds a production agent graph -- accepts either a string or a model instance

* [20261014082000](../20261014082000) Dynamic model and tool selection with request.override -- swap models per call with middleware

* [20261014082600](../20261014082600) ModelFallbackMiddleware tries alternative models on failure -- fallback chains also take model strings

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Models\
  <https://docs.langchain.com/oss/python/langchain/models>

* Intro to LangChain, Lesson 1: Foundational Models\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #foundational-models #exam-build
