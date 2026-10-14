# Alerts fire on threshold breaches of a project metric

Alerts are scoped to one tracing project (or one agent environment). Metrics: run count, cost, errors (count or percent), feedback score (choose a feedback key), latency. A condition = aggregation (average/percentage/count) + operator + threshold + window (5 or 15 minutes). Notifications go to Slack, PagerDuty, Dynatrace or any webhook.

```python
# pseudo-config: metric = Errors, aggregation = Percentage, operator = >=, threshold = 5,
# window = 5 min, filter: run_type == llm  -> notify PagerDuty
```

Related:

* [20261014094500](../20261014094500) Cost tracking derives spend from token usage and model pricing -- cost alerts require cost tracking

* [20261014093800](../20261014093800) Online evaluators score production runs with filters and sampling -- feedback score alerts

* [20261014094800](../20261014094800) Monitoring latency and errors -- error and latency alerts

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* Monitoring Production Agents, Module 4: Setting Up Alerts\
  <https://academy.langchain.com/courses/production-monitoring>

* LangSmith docs: Alerts\
  <https://docs.langchain.com/langsmith/alerts>

Tags:

    #monitoring-production-agents #monitoring-security #alerting #exam-monitor
