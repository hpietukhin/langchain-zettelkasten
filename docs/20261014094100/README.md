# Annotation queues route runs to human reviewers

A queue holds runs or threads for people to review against a rubric (feedback keys), add corrections, and send to datasets. Fill it manually, from experiments, or with automation rules (e.g. all runs with negative user feedback).

```python
q = client.create_annotation_queue(name="Negative feedback review")
client.add_runs_to_annotation_queue(q.id, run_ids=[run.id])
```

Related:

* [20261014094000](../20261014094000) Align LLM judges to human labels before trusting them -- labels used for alignment

* [20261014092900](../20261014092900) Adding examples: from traces, annotation queues, rules or the SDK -- reviewed runs become examples

* [20261014094200](../20261014094200) Automation rules act on matching traces -- rules can fill queues

* [20261014101700](../20261014101700) Structure: Exam section 2 · Test (evaluators and experiments) -- exam section hub

Refs:

* LangSmith docs: Annotation queues\
  <https://docs.langchain.com/langsmith/annotation-queues>

Tags:

    #building-reliable-agents #langsmith-evaluation #human-feedback #exam-test
