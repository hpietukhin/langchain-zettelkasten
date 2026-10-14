# An agent is a model calling tools in a loop

The core agent loop: the model receives messages, decides whether to call tools, the tools run, their results are appended as tool messages, and the model is called again. The loop ends when the model answers without requesting any tool call (or when middleware jumps to the end). Everything an agent does well or badly comes down to what the model sees at each turn of this loop.

```python
# pseudo-structure of the loop that create_agent compiles into a graph
while True:
    ai_msg = model.invoke(messages)          # model node
    messages.append(ai_msg)
    if not ai_msg.tool_calls:               # no tool call -> finish
        break
    for call in ai_msg.tool_calls:          # tools node
        messages.append(run_tool(call))     # ToolMessage
```

Related:

* [20261014080200](../20261014080200) create_agent builds a production agent graph -- create_agent is the prebuilt implementation of this loop

* [20261014080100](../20261014080100) Agent = model + harness -- the harness is everything around the loop

* [20261014081500](../20261014081500) Middleware hooks into every step of the agent loop -- middleware hooks into each step of the loop

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Agents\
  <https://docs.langchain.com/oss/python/langchain/agents>

* Intro to LangChain, Module 1: Create Agent\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #create-agent #agent-harness #exam-build
