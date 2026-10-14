# Messages are the unit of context

Chat models consume and emit typed messages: `SystemMessage` (instructions), `HumanMessage` (user input), `AIMessage` (model output, may contain `tool_calls`) and `ToolMessage` (a tool's result, linked by `tool_call_id`). Dicts like `{"role": "user", "content": ...}` are accepted as shorthand.

```python
from langchain.messages import HumanMessage, AIMessage, SystemMessage

msgs = [SystemMessage("Be terse."), HumanMessage("2+2?")]
reply: AIMessage = model.invoke(msgs)
print(reply.content, reply.tool_calls)
```

Related:

* [20261014080000](../20261014080000) An agent is a model calling tools in a loop -- the loop appends messages

* [20261014080700](../20261014080700) Multimodal input uses content blocks -- content can be multimodal blocks

* [20261014080800](../20261014080800) Short-term memory = checkpointer + thread_id -- message history is what the checkpointer persists

* [20261014090800](../20261014090800) add_messages and MessagesState manage chat history -- how graphs merge message lists

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Messages\
  <https://docs.langchain.com/oss/python/langchain/messages>

* Intro to LangChain, Module 1\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #langchain-messages #exam-build
