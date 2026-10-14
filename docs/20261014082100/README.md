# SummarizationMiddleware compresses old history

When a `trigger` condition is met (tokens, messages, or a fraction of the model's max input), older messages are replaced by an LLM-written summary while the most recent ones (`keep`) are kept verbatim. This bounds context size for long-running conversations at the cost of losing detail.

```python
from langchain.agents.middleware import SummarizationMiddleware

agent = create_agent(
    model="gpt-5.5", tools=[],
    middleware=[SummarizationMiddleware(model="gpt-5.4-mini",
                                        trigger=("tokens", 4000),
                                        keep=("messages", 20))],
)
```

Related:

* [20261014080800](../20261014080800) Short-term memory = checkpointer + thread_id -- long threads eventually overflow

* [20261014082200](../20261014082200) ContextEditingMiddleware clears old tool outputs -- a lighter alternative that clears tool results

* [20261014084200](../20261014084200) Deep agents summarise history at about 85% of the window -- deep agents include it by default

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Built-in middleware\
  <https://docs.langchain.com/oss/python/langchain/middleware/built-in>

* Intro to LangChain, Module 3 Lesson 2: Managing Long Conversations\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #managing-long-conversations #middleware #context-engineering #exam-build
