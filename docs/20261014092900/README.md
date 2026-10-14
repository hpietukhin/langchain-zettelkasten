# Adding examples: from traces, annotation queues, rules or the SDK

In the UI you can add a run to a dataset from the trace view ("Add to dataset", editing outputs into a reference), from an annotation queue, or via an automation rule that adds matching runs. Programmatically use `create_examples` or create an example from a run. Edit the reference output: the agent's output is not automatically correct.

```python
run = next(client.list_runs(project_name="email-agent", error=False, limit=1))
client.create_example(inputs=run.inputs, outputs={"label": "ignore"},
                      dataset_name="Email triage", metadata={"from_run": str(run.id)})
```

Related:

* [20261014092800](../20261014092800) Datasets are collections of examples for offline evaluation -- where they go

* [20261014094100](../20261014094100) Annotation queues route runs to human reviewers -- human-reviewed additions

* [20261014094200](../20261014094200) Automation rules act on matching traces -- automatic additions

* [20261014092300](../20261014092300) The Agent Development Lifecycle: build, test, deploy, monitor -- production feeds testing

* [20261014101700](../20261014101700) Structure: Exam section 2 · Test (evaluators and experiments) -- exam section hub

Refs:

* LangSmith docs: Manage datasets in the application\
  <https://docs.langchain.com/langsmith/manage-datasets-in-application>

* LangSmith docs: Automation rules\
  <https://docs.langchain.com/langsmith/rules>

Tags:

    #building-reliable-agents #langsmith-evaluation #creating-datasets #exam-test
