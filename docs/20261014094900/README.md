# Dashboards chart project metrics over time

Each project gets prebuilt dashboards (trace count, latency, errors, tokens, cost, feedback). Custom dashboards add charts with filters and group-by on metadata or tags, e.g. cost per customer or feedback per prompt version.

```python
# pseudo-config: chart = "Cost", project = "email-agent", group by metadata.plan_type, window = 7d
```

Related:

* [20261014094500](../20261014094500) Cost tracking derives spend from token usage and model pricing -- cost charts

* [20261014094800](../20261014094800) Monitoring latency and errors -- latency/error charts

* [20261014095000](../20261014095000) A/B testing agents in production with metadata -- group by metadata

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* LangSmith docs: Dashboards\
  <https://docs.langchain.com/langsmith/dashboards>

Tags:

    #monitoring-production-agents #monitoring-quality #exam-monitor
