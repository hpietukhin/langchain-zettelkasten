# @dynamic_prompt computes the system prompt per model call

A function decorated with `@dynamic_prompt` receives the `ModelRequest` and returns the system prompt string. It can look at message count, runtime context (role, preferences) or the store. The change is transient: it shapes one call, not saved state.

```python
from langchain.agents import create_agent
from langchain.agents.middleware import dynamic_prompt, ModelRequest

@dynamic_prompt
def state_aware_prompt(request: ModelRequest) -> str:
    base = "You are a helpful assistant."
    if len(request.messages) > 10:
        base += "\nThis is a long conversation - be extra concise."
    return base

agent = create_agent(model="gpt-5.5", tools=[], middleware=[state_aware_prompt])
```

Related:

* [20261014081000](../20261014081000) Runtime context is static per-invocation configuration -- prompts often depend on context

* [20261014081700](../20261014081700) Wrap-style hooks intercept model and tool calls -- dynamic_prompt is a wrap_model_call specialisation

* [20261014083900](../20261014083900) A deep agent's system_prompt is prepended to a built-in prompt -- deep agents' static prompt vs dynamic

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Context engineering\
  <https://docs.langchain.com/oss/python/langchain/context-engineering>

* Intro to LangChain, Module 3 Lesson 4: Dynamic Agents\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #dynamic-agents #middleware #context-engineering #exam-build
