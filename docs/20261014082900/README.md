# LLMToolSelectorMiddleware narrows large toolsets

With many tools, schemas bloat the prompt and confuse the model. This middleware asks a (cheap) model to pick the most relevant `max_tools` before the main call; `always_include` pins essentials.

```python
from langchain.agents.middleware import LLMToolSelectorMiddleware

mw = LLMToolSelectorMiddleware(model="gpt-5.4-mini", max_tools=3, always_include=["search"])
agent = create_agent(model="gpt-5.5", tools=many_tools, middleware=[mw])
```

Related:

* [20261014080400](../20261014080400) Tools are typed functions whose docstring is the model's manual -- each tool schema costs tokens

* [20261014082000](../20261014082000) Dynamic model and tool selection with request.override -- manual alternative

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Built-in middleware\
  <https://docs.langchain.com/oss/python/langchain/middleware/built-in>

Tags:

    #langchain-foundations #middleware #context-engineering #exam-build
