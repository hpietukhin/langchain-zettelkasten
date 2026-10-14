# Monitoring security: prompt injection, data leaks, abuse

Production agents must be monitored for prompt-injection attempts, PII/secret leakage in outputs, unexpected tool use and unusual volume. Combine prevention (guardrail middleware), detection (online evaluators flagging suspicious runs) and response (alerts, annotation queues).

```python
def leaks_secret(run, example):
    return {"secret_leak": "sk-" in str(run["outputs"])}   # online code evaluator
```

Related:

* [20261014093800](../20261014093800) Online evaluators score production runs with filters and sampling -- detect issues with evaluators

* [20261014082800](../20261014082800) PIIMiddleware detects and handles sensitive data -- prevent in the agent

* [20261014095300](../20261014095300) Redact secrets from traces with an anonymizer -- keep secrets out of traces

* [20261014095100](../20261014095100) Alerts fire on threshold breaches of a project metric -- page on spikes

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* Monitoring Production Agents, Module 4: Monitoring Security\
  <https://academy.langchain.com/courses/production-monitoring>

Tags:

    #monitoring-production-agents #monitoring-security #exam-monitor
