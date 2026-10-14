# Online evaluators score production runs with filters and sampling

Created on a tracing project's **Evaluators** tab: LLM-as-judge or code evaluator, optional filter (e.g. runs with negative user feedback, a certain tool call, a metadata value), a sampling rate (0.1 = 10% to control cost), optional backfill to past runs (only at creation) and a spend limit. Results appear as feedback on runs.

```python
# online code evaluator body (runs inside LangSmith)
def perform_eval(run, example):
    out = run["outputs"]
    return {"has_citation": "http" in str(out)}
```

Related:

* [20261014093700](../20261014093700) Offline vs online evaluation -- contrast

* [20261014093900](../20261014093900) Multi-turn online evaluators judge whole threads -- thread-level variant

* [20261014095100](../20261014095100) Alerts fire on threshold breaches of a project metric -- alert on their feedback scores

* [20261014094400](../20261014094400) Online evals vs Insights: known questions vs unknown patterns -- how they differ from Insights

* [20261014094000](../20261014094000) Align LLM judges to human labels before trusting them -- align online judges too

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* LangSmith docs: Online LLM-as-judge evaluators\
  <https://docs.langchain.com/langsmith/online-evaluations-llm-as-judge>

* LangSmith docs: Online code evaluators\
  <https://docs.langchain.com/langsmith/online-evaluations-code>

Tags:

    #building-reliable-agents #monitoring-production-agents #online-evals #exam-monitor
