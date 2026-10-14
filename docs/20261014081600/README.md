# Node-style hooks run before or after agent and model steps

`before_agent`, `before_model`, `after_model` and `after_agent` run sequentially at fixed points. They receive `(state, runtime)` and return a dict of state updates or `None`. With `can_jump_to` they can short-circuit, e.g. return `"jump_to": "end"` to stop the loop. Use them for logging, validation and state edits.

```python
from langchain.agents.middleware import before_model, AgentState
from langchain.messages import AIMessage
from langgraph.runtime import Runtime

@before_model(can_jump_to=["end"])
def check_message_limit(state: AgentState, runtime: Runtime):
    if len(state["messages"]) >= 50:
        return {"messages": [AIMessage("Conversation limit reached.")], "jump_to": "end"}
    return None
```

Related:

* [20261014081500](../20261014081500) Middleware hooks into every step of the agent loop -- one of two hook families

* [20261014081700](../20261014081700) Wrap-style hooks intercept model and tool calls -- the other family

* [20261014081800](../20261014081800) Class-based middleware bundles hooks, config and state -- same hooks as class methods

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Custom middleware\
  <https://docs.langchain.com/oss/python/langchain/middleware/custom>

Tags:

    #langchain-foundations #middleware #exam-build
