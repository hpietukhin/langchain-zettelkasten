# Datasets are collections of examples for offline evaluation

An example has `inputs`, optional reference `outputs` and `metadata`. Good datasets mix hand-written cases, production traces (especially failures) and synthetic edge cases. Splits and versions let you evaluate subsets and reproduce past experiments.

```python
from langsmith import Client
client = Client()
ds = client.create_dataset(dataset_name="Email triage")
client.create_examples(dataset_id=ds.id, examples=[
    {"inputs": {"email": "Invoice overdue"}, "outputs": {"label": "respond"}, "metadata": {"source": "prod"}},
])
```

Related:

* [20261014092900](../20261014092900) Adding examples: from traces, annotation queues, rules or the SDK -- ways to grow a dataset

* [20261014093000](../20261014093000) An experiment runs a target over a dataset with evaluators -- datasets are what experiments run over

* [20261014093100](../20261014093100) Evaluators take inputs, outputs and reference_outputs -- reference_outputs come from examples

* [20261014101700](../20261014101700) Structure: Exam section 2 · Test (evaluators and experiments) -- exam section hub

Refs:

* Building Reliable Agents, Module 2 Lesson 2: Creating Datasets\
  <https://academy.langchain.com/courses/building-reliable-agents>

* LangSmith docs: Manage datasets programmatically\
  <https://docs.langchain.com/langsmith/manage-datasets-programmatically>

Tags:

    #building-reliable-agents #langsmith-evaluation #creating-datasets #exam-test
