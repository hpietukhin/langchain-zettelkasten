# create_agent builds a production agent graph

`langchain.agents.create_agent` returns a compiled LangGraph graph implementing the tool-calling loop. Key arguments: `model`, `tools`, `system_prompt`, `middleware`, `response_format`, `state_schema`, `context_schema`, `checkpointer`, `store`. Because the result is a LangGraph graph you get streaming, persistence, interrupts and deployment for free.

```python
from langchain.agents import create_agent

agent = create_agent(
    model="anthropic:claude-sonnet-5",
    tools=[get_weather],
    system_prompt="You are a helpful weather assistant.",
)
result = agent.invoke({"messages": [{"role": "user", "content": "Weather in Bratislava?"}]})
print(result["messages"][-1].content)
```

Related:

* [20261014080000](../20261014080000) An agent is a model calling tools in a loop -- implements the loop

* [20261014080300](../20261014080300) Models are chosen with provider:model strings or init_chat_model -- how the model argument is resolved

* [20261014080400](../20261014080400) Tools are typed functions whose docstring is the model's manual -- what goes into tools

* [20261014081500](../20261014081500) Middleware hooks into every step of the agent loop -- the main extension point

* [20261014083600](../20261014083600) create_agent vs create_deep_agent: when to use which -- compare with create_deep_agent

* [20261014090600](../20261014090600) A LangGraph graph is state, nodes and edges -- returns a compiled LangGraph graph

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Agents\
  <https://docs.langchain.com/oss/python/langchain/agents>

* Intro to LangChain, Module 1\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #create-agent #exam-build
