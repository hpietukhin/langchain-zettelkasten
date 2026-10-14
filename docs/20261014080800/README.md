# Short-term memory = checkpointer + thread_id

An agent remembers a conversation only if it is compiled with a checkpointer and every call passes the same `thread_id` in `config["configurable"]`. The checkpointer saves state after each step; a new thread_id starts with empty memory. `InMemorySaver` is for development; production uses a database-backed saver.

```python
from langchain.agents import create_agent
from langgraph.checkpoint.memory import InMemorySaver

agent = create_agent(model="openai:gpt-5.5", tools=[], checkpointer=InMemorySaver())
cfg = {"configurable": {"thread_id": "1"}}
agent.invoke({"messages": [{"role": "user", "content": "Hi, I'm Bob"}]}, cfg)
agent.invoke({"messages": [{"role": "user", "content": "What's my name?"}]}, cfg)  # remembers Bob
```

Related:

* [20261014091400](../20261014091400) Checkpoints snapshot state at every super-step -- the LangGraph mechanism underneath

* [20261014082100](../20261014082100) SummarizationMiddleware compresses old history -- keeps long threads within the window

* [20261014083300](../20261014083300) Long-term memory lives in a store, namespaced across threads -- contrast with cross-thread memory

* [20261014082300](../20261014082300) HumanInTheLoopMiddleware pauses before sensitive tool calls -- interrupts need a checkpointer

* [20261014095800](../20261014095800) Don't configure a checkpointer or store in deployed graph code -- on LangSmith Deployment the server injects it

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Short-term memory\
  <https://docs.langchain.com/oss/python/langchain/short-term-memory>

* Intro to LangChain, Lesson 3: Short-Term Memory\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #short-term-memory #langgraph-memory #exam-build
