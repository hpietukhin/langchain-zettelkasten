# An experiment runs a target over a dataset with evaluators

`client.evaluate(target, data=dataset, evaluators=[...])` calls the target on every example, applies each evaluator, and stores everything as an experiment you can compare in the UI. Useful options: `experiment_prefix`, `description`, `max_concurrency`, `metadata` (model/prompt versions), `num_repetitions`.

```python
from langsmith import Client
client = Client()

def target(inputs: dict) -> dict:
    return {"label": triage(inputs["email"])}

results = client.evaluate(target, data="Email triage", evaluators=[exact_label],
                          experiment_prefix="gpt-5.4-mini baseline", max_concurrency=4)
```

Related:

* [20261014092800](../20261014092800) Datasets are collections of examples for offline evaluation -- input

* [20261014093100](../20261014093100) Evaluators take inputs, outputs and reference_outputs -- how scores are computed

* [20261014093600](../20261014093600) Reading experiments without overfitting to noise -- interpret results

* [20261014093500](../20261014093500) Pairwise evaluation compares two experiments head-to-head -- compare two experiments

* [20261014101700](../20261014101700) Structure: Exam section 2 · Test (evaluators and experiments) -- exam section hub

Refs:

* Building Reliable Agents, Module 2 Lesson 3: Running Experiments\
  <https://academy.langchain.com/courses/building-reliable-agents>

* LangSmith docs: Evaluate an application\
  <https://docs.langchain.com/langsmith/evaluate-llm-application>

Tags:

    #building-reliable-agents #langsmith-evaluation #running-experiments #exam-test
