# Reading a trace: project, trace, run, run types

A *project* holds traces; a *trace* is one end-to-end operation (one invocation); it is a tree of *runs* (spans), each with a `run_type` such as `chain`, `llm`, `tool`, `retriever`. Read a trace top-down: root inputs/outputs, then the model calls (prompt, tool calls, tokens), the tool runs (args, results, errors), latency and cost per run.

```python
from langsmith import Client
client = Client()
for run in client.list_runs(project_name="email-agent", is_root=True, limit=5):
    print(run.name, run.run_type, run.status, run.total_tokens)
```

Related:

* [20261014092400](../20261014092400) Tracing records every step of an agent as runs in a trace -- how traces are produced

* [20261014092700](../20261014092700) Group traces into threads with session_id or thread_id metadata -- threads group traces

* [20261014094500](../20261014094500) Cost tracking derives spend from token usage and model pricing -- llm runs carry token usage

* [20261014094800](../20261014094800) Monitoring latency and errors -- status and latency per run

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* LangSmith docs: Observability concepts\
  <https://docs.langchain.com/langsmith/observability-concepts>

* Building Reliable Agents, Module 1 Lesson 3: Analyzing your Agent\
  <https://academy.langchain.com/courses/building-reliable-agents>

Tags:

    #monitoring-production-agents #langsmith-observability #reading-traces #exam-monitor
