# Class-based middleware bundles hooks, config and state

Subclass `AgentMiddleware` when a middleware needs constructor parameters, several hooks, or its own state schema / tools. Jumps are declared with `@hook_config(can_jump_to=[...])` on the method.

```python
from langchain.agents.middleware import AgentMiddleware, AgentState, hook_config
from langchain.messages import AIMessage

class MessageLimitMiddleware(AgentMiddleware):
    def __init__(self, max_messages: int = 50):
        super().__init__()
        self.max_messages = max_messages

    @hook_config(can_jump_to=["end"])
    def before_model(self, state: AgentState, runtime):
        if len(state["messages"]) >= self.max_messages:
            return {"messages": [AIMessage("Limit reached.")], "jump_to": "end"}
```

Related:

* [20261014081600](../20261014081600) Node-style hooks run before or after agent and model steps -- decorators are shortcuts for these methods

* [20261014081700](../20261014081700) Wrap-style hooks intercept model and tool calls -- wrap methods can live on the class too

* [20261014080900](../20261014080900) Custom agent state extends AgentState -- middleware can extend state

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Custom middleware\
  <https://docs.langchain.com/oss/python/langchain/middleware/custom>

Tags:

    #langchain-foundations #middleware #exam-build
