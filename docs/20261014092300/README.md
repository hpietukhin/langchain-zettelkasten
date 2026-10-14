# The Agent Development Lifecycle: build, test, deploy, monitor

Agents are non-deterministic, so reliability comes from iteration: build a first version, observe traces, turn failures into dataset examples and evaluators, run experiments, deploy, monitor production with online evaluators, Insights and alerts, then feed production findings back into datasets. The certification exam is organised around this cycle.

```python
# pseudo-loop
# build -> trace -> curate dataset from traces -> evaluate(experiment)
#       -> deploy revision -> online evals / insights / alerts -> new examples -> ...
```

Related:

* [20261014092400](../20261014092400) Tracing records every step of an agent as runs in a trace -- observation starts the cycle

* [20261014093000](../20261014093000) An experiment runs a target over a dataset with evaluators -- offline testing

* [20261014093800](../20261014093800) Online evaluators score production runs with filters and sampling -- production testing

* [20261014095400](../20261014095400) Deployment terminology: graph, deployment, revision, assistant, thread, run -- deploy

* [20261014094300](../20261014094300) Insights clusters traces into usage and failure patterns -- monitor and feed back

* [20261014101700](../20261014101700) Structure: Exam section 2 · Test (evaluators and experiments) -- exam section hub

Refs:

* Building Reliable Agents, Intro: The Agent Development Lifecycle\
  <https://academy.langchain.com/courses/building-reliable-agents>

Tags:

    #building-reliable-agents #agent-development-lifecycle #exam-test
