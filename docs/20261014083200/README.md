# Streaming modes expose progress, tokens and updates

`agent.stream(..., stream_mode=...)` yields incremental output: `"updates"` (state changes per step), `"values"` (full state after each step), `"messages"` (LLM tokens with metadata) and `"custom"` (data you emit with `get_stream_writer`). Several modes can be combined.

```python
for chunk in agent.stream({"messages": [{"role": "user", "content": "Plan a trip"}]},
                          stream_mode="updates"):
    print(chunk)
```

Related:

* [20261014082300](../20261014082300) HumanInTheLoopMiddleware pauses before sensitive tool calls -- interrupts appear in the updates stream

* [20261014100300](../20261014100300) Connect to a deployment with the LangGraph SDK or RemoteGraph -- the same modes over the Agent Server API

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Streaming\
  <https://docs.langchain.com/oss/python/langchain/streaming>

Tags:

    #langchain-foundations #streaming #exam-build
