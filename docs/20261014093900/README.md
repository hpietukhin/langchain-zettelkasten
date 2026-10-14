# Multi-turn online evaluators judge whole threads

Some qualities only exist at conversation level: did the user's goal get met, did the user get frustrated, did the agent repeat itself. Thread-level rules wait until a thread is idle, then evaluate the root-run history and attach feedback to the thread.

```python
# pseudo-config (UI): Source = Threads, idle time = 10 min,
# judge prompt: "Given the full conversation, did the assistant resolve the user's request? true/false"
```

Related:

* [20261014092700](../20261014092700) Group traces into threads with session_id or thread_id metadata -- threads must be configured

* [20261014093800](../20261014093800) Online evaluators score production runs with filters and sampling -- run-level counterpart

* [20261014094600](../20261014094600) Tracking user sentiment with feedback -- thread-level sentiment/frustration

* [20261014094700](../20261014094700) LangChain Tuned Evaluators: managed judges like Perceived Error -- LangChain-managed thread judges

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* LangSmith docs: Multi-turn online evaluators\
  <https://docs.langchain.com/langsmith/online-evaluations-multi-turn>

Tags:

    #monitoring-production-agents #online-evals #threads #exam-monitor
