# Tools are typed functions whose docstring is the model's manual

The `@tool` decorator turns a Python function into a tool: the name, the type hints and the docstring become the schema the model sees. Good names and descriptions are prompt engineering; the model only knows what the tool does from them.

```python
from langchain.tools import tool

@tool
def get_weather(city: str) -> str:
    """Return the current weather for a city."""
    return f"It is sunny in {city}."
```

Related:

* [20261014080200](../20261014080200) create_agent builds a production agent graph -- tools are passed to the agent

* [20261014080500](../20261014080500) ToolRuntime gives tools access to state, context and store -- tools can also read runtime state

* [20261014081200](../20261014081200) MCP exposes external tools through a standard protocol -- tools can come from MCP servers

* [20261014082900](../20261014082900) LLMToolSelectorMiddleware narrows large toolsets -- too many tools can be pre-filtered

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Tools\
  <https://docs.langchain.com/oss/python/langchain/tools>

* Intro to LangChain, Lesson 2: Tools\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #langchain-tools #exam-build
