# Online evals vs Insights: known questions vs unknown patterns

Online evaluators continuously score each (sampled) run or thread against a criterion you already know matters, producing feedback you can chart and alert on. Insights is periodic, exploratory analysis that discovers categories of usage and failure you did not know to look for. Typical flow: Insights finds a failure mode -> write an online evaluator / dataset examples for it.

```python
# known question  -> online evaluator: "Did the agent cite a source?" (every 10% of runs)
# unknown pattern -> Insights report: "What are users asking and where does the agent fail?"
```

Related:

* [20261014093800](../20261014093800) Online evaluators score production runs with filters and sampling -- continuous scoring

* [20261014094300](../20261014094300) Insights clusters traces into usage and failure patterns -- exploratory clustering

* [20261014095100](../20261014095100) Alerts fire on threshold breaches of a project metric -- alerts use online scores, not Insights

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* Monitoring Production Agents course\
  <https://academy.langchain.com/courses/production-monitoring>

* LangSmith docs: Insights\
  <https://docs.langchain.com/langsmith/insights>

Tags:

    #monitoring-production-agents #online-evals #insights #exam-monitor
