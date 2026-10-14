# Custom agent state extends AgentState

State is the mutable data that flows through the agent graph and is checkpointed. By subclassing `AgentState` (which already has `messages`) and passing it as `state_schema`, you can track extra fields such as user preferences that tools and middleware read and update.

```python
from langchain.agents import create_agent, AgentState

class CustomState(AgentState):
    user_preferences: dict

agent = create_agent(model="openai:gpt-5.5", tools=[get_user_preference], state_schema=CustomState)
agent.invoke({"messages": [...], "user_preferences": {"units": "metric"}})
```

Related:

* [20261014080500](../20261014080500) ToolRuntime gives tools access to state, context and store -- tools read state via runtime.state

* [20261014081000](../20261014081000) Runtime context is static per-invocation configuration -- context is static, state evolves

* [20261014081800](../20261014081800) Class-based middleware bundles hooks, config and state -- middleware can declare a state_schema too

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Short-term memory\
  <https://docs.langchain.com/oss/python/langchain/short-term-memory>

* Intro to LangChain, Module 2 Lesson 2: Context and State\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #context-and-state #exam-build
