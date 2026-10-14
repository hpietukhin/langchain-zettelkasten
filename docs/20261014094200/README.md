# Automation rules act on matching traces

A rule = filter + sampling rate + action. Actions include adding runs to a dataset, adding to an annotation queue, running an online evaluator, and calling a webhook. They turn production traffic into a continuous improvement loop without manual triage.

```python
# pseudo-config (UI): filter: feedback_key == "user_score" and score == 0
# sampling: 1.0 -> action: add to annotation queue "Negative feedback review"
```

Related:

* [20261014093800](../20261014093800) Online evaluators score production runs with filters and sampling -- evaluators are one rule type

* [20261014092900](../20261014092900) Adding examples: from traces, annotation queues, rules or the SDK -- add to dataset

* [20261014094100](../20261014094100) Annotation queues route runs to human reviewers -- send to a queue

* [20261014095100](../20261014095100) Alerts fire on threshold breaches of a project metric -- webhooks and alerts

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* Building Reliable Agents, Module 3 Lesson 4: Automations\
  <https://academy.langchain.com/courses/building-reliable-agents>

* LangSmith docs: Automation rules\
  <https://docs.langchain.com/langsmith/rules>

Tags:

    #building-reliable-agents #monitoring-production-agents #automations #exam-monitor
