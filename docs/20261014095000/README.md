# A/B testing agents in production with metadata

Route a share of traffic to a variant (different prompt, model or assistant), tag every trace with the variant, and compare feedback, online-eval scores, latency and cost grouped by that metadata. Decide only when the difference is larger than noise.

```python
variant = "B" if hash(user_id) % 10 == 0 else "A"
agent_for[variant].invoke(inputs, config={"metadata": {"variant": variant}})
```

Related:

* [20261014092600](../20261014092600) Metadata and tags make traces filterable -- label the variant

* [20261014100100](../20261014100100) Assistants version configuration separately from code -- assistants are natural variants

* [20261014094900](../20261014094900) Dashboards chart project metrics over time -- compare variants

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* Monitoring Production Agents, Module 3: A/B Testing\
  <https://academy.langchain.com/courses/production-monitoring>

Tags:

    #monitoring-production-agents #monitoring-quality #exam-monitor
