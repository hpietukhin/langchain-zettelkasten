# Insights clusters traces into usage and failure patterns

An Insights Report (Plus/Enterprise; needs a model configuration) samples traces from a project/environment, answers guided questions about what you want to learn, and produces an executive summary plus hierarchical categories and subcategories with frequency bars, error rate, latency, cost and feedback per category. Reports run in the background (up to ~30 min). `client.generate_insights(chat_histories=...)` analyses external chat logs.

```python
from langsmith import Client
report = Client().generate_insights(chat_histories=[
    [{"role": "user", "content": "how are you"}, {"role": "assistant", "content": "good!"}],
])
```

Related:

* [20261014094400](../20261014094400) Online evals vs Insights: known questions vs unknown patterns -- contrast with online evals

* [20261014092700](../20261014092700) Group traces into threads with session_id or thread_id metadata -- reports run over traces/threads

* [20261014092900](../20261014092900) Adding examples: from traces, annotation queues, rules or the SDK -- found failures become examples

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* Monitoring Production Agents, Module 2: Analyze Trends with Insights\
  <https://academy.langchain.com/courses/production-monitoring>

* LangSmith docs: Insights\
  <https://docs.langchain.com/langsmith/insights>

* Building Reliable Agents, Module 3 Lesson 2: Insights Agent\
  <https://academy.langchain.com/courses/building-reliable-agents>

Tags:

    #monitoring-production-agents #product-analytics #insights #exam-monitor
