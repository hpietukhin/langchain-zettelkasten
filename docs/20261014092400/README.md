# Tracing records every step of an agent as runs in a trace

With `LANGSMITH_TRACING=true` and `LANGSMITH_API_KEY` set, LangChain/LangGraph agents trace automatically into the project named by `LANGSMITH_PROJECT`. Arbitrary Python is traced with `@traceable`; provider SDKs with wrappers like `wrap_openai`.

```python
import os
os.environ["LANGSMITH_TRACING"] = "true"
os.environ["LANGSMITH_PROJECT"] = "email-agent"
from langsmith import traceable

@traceable(run_type="chain", name="pipeline")
def pipeline(q: str) -> str:
    return agent.invoke({"messages": [{"role": "user", "content": q}]})["messages"][-1].content
```

Related:

* [20261014092500](../20261014092500) Reading a trace: project, trace, run, run types -- how a trace is structured

* [20261014092600](../20261014092600) Metadata and tags make traces filterable -- annotate traces

* [20261014092700](../20261014092700) Group traces into threads with session_id or thread_id metadata -- group traces into conversations

* [20261014092300](../20261014092300) The Agent Development Lifecycle: build, test, deploy, monitor -- first step of the cycle

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* Building Reliable Agents, Module 1 Lesson 2: Tracing with LangSmith\
  <https://academy.langchain.com/courses/building-reliable-agents>

* LangSmith docs: Observability concepts\
  <https://docs.langchain.com/langsmith/observability-concepts>

Tags:

    #building-reliable-agents #langsmith-observability #tracing-with-langsmith #exam-monitor
