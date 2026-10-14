# Offline vs online evaluation

Offline evaluators run on a curated dataset before release (experiments, regression testing, references available). Online evaluators run on live production traces as they arrive (no reference outputs, so they are reference-free: LLM judges, code checks, thread-level checks) and attach feedback for monitoring and alerts.

```python
# offline
client.evaluate(target, data="Email triage", evaluators=[exact_label])
# online: configured in the UI on a tracing project (Evaluators tab), with filter + sampling rate
```

Related:

* [20261014093000](../20261014093000) An experiment runs a target over a dataset with evaluators -- offline

* [20261014093800](../20261014093800) Online evaluators score production runs with filters and sampling -- online

* [20261014094000](../20261014094000) Align LLM judges to human labels before trusting them -- applies to both

* [20261014092300](../20261014092300) The Agent Development Lifecycle: build, test, deploy, monitor -- both sides of the lifecycle

* [20261014101700](../20261014101700) Structure: Exam section 2 · Test (evaluators and experiments) -- exam section hub

Refs:

* Building Reliable Agents, Module 3 Lesson 3: Online Evals\
  <https://academy.langchain.com/courses/building-reliable-agents>

* LangSmith evaluation concepts\
  <https://docs.langchain.com/langsmith/evaluation-concepts>

Tags:

    #building-reliable-agents #langsmith-evaluation #online-evals #exam-test
