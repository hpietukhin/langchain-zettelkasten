# Monitoring latency and errors

Watch percentiles (P50/P99), not only averages, and break latency down by run (model vs tool time, time to first token). Track error rate by run type and tag to find the failing tool or provider (e.g. rate limits). Filter the runs table by `status == error` to read failing traces.

```python
errors = client.list_runs(project_name="email-agent", error=True, start_time=yesterday)
for r in errors:
    print(r.name, r.error[:80], (r.end_time - r.start_time).total_seconds())
```

Related:

* [20261014092500](../20261014092500) Reading a trace: project, trace, run, run types -- per-run latency and status

* [20261014094900](../20261014094900) Dashboards chart project metrics over time -- charts

* [20261014095100](../20261014095100) Alerts fire on threshold breaches of a project metric -- thresholds on errors/latency

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* Monitoring Production Agents, Module 3: Monitoring Latency and Errors\
  <https://academy.langchain.com/courses/production-monitoring>

Tags:

    #monitoring-production-agents #monitoring-quality #exam-monitor
