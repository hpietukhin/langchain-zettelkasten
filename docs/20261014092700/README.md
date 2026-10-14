# Group traces into threads with session_id or thread_id metadata

A multi-turn conversation produces many traces. Setting a metadata key `session_id` or `thread_id` (same value on all runs, including child runs) groups them into a thread in LangSmith, so you can read the whole conversation, count its tokens and run thread-level evaluators. UUID v7 IDs are recommended.

```python
from langsmith import uuid7
THREAD_ID = str(uuid7())
agent.invoke(inputs, config={"metadata": {"thread_id": THREAD_ID},
                             "configurable": {"thread_id": THREAD_ID}})
```

Related:

* [20261014092500](../20261014092500) Reading a trace: project, trace, run, run types -- a thread is a sequence of traces

* [20261014093900](../20261014093900) Multi-turn online evaluators judge whole threads -- evaluate whole threads

* [20261014100200](../20261014100200) Threads hold state, runs execute; stateless and background runs -- deployment threads are a different but related concept

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* LangSmith docs: Configure threads\
  <https://docs.langchain.com/langsmith/threads>

Tags:

    #monitoring-production-agents #langsmith-observability #threads #exam-monitor
