# response_format returns validated structured output

Passing a schema (Pydantic model, dataclass, TypedDict or JSON schema) as `response_format` makes the agent finish with a parsed object in `result["structured_response"]`. `ProviderStrategy` uses the provider's native structured output; `ToolStrategy` emulates it with an artificial tool call and supports `handle_errors` for retries. A bare schema lets LangChain pick the strategy.

```python
from pydantic import BaseModel
from langchain.agents import create_agent
from langchain.agents.structured_output import ToolStrategy

class Contact(BaseModel):
    name: str
    email: str

agent = create_agent(model="openai:gpt-5.5", tools=[], response_format=ToolStrategy(Contact))
out = agent.invoke({"messages": [{"role": "user", "content": "John, john@x.com"}]})
print(out["structured_response"])
```

Related:

* [20261014080200](../20261014080200) create_agent builds a production agent graph -- an argument of create_agent

* [20261014082000](../20261014082000) Dynamic model and tool selection with request.override -- middleware can override response_format per request

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Structured output\
  <https://docs.langchain.com/oss/python/langchain/structured-output>

Tags:

    #langchain-foundations #structured-output #exam-build
