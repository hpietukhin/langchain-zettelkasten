# Evaluators take inputs, outputs and reference_outputs

An offline evaluator is a function receiving any of `inputs`, `outputs`, `reference_outputs` (or `run`/`example`) and returning a bool/number, or a dict with `key` and `score` (plus optional `comment`). Reference-free evaluators need no expected output; reference-based ones compare against it.

```python
def exact_label(outputs: dict, reference_outputs: dict) -> bool:
    return outputs["label"] == reference_outputs["label"]

def concise(outputs: dict) -> dict:
    return {"key": "concise", "score": len(outputs["answer"]) < 500}
```

Related:

* [20261014093200](../20261014093200) Code-based evaluators: deterministic, cheap, exact -- deterministic evaluators

* [20261014093300](../20261014093300) LLM-as-judge grades subjective qualities with a model -- model-graded evaluators

* [20261014093000](../20261014093000) An experiment runs a target over a dataset with evaluators -- where evaluators run

* [20261014101700](../20261014101700) Structure: Exam section 2 · Test (evaluators and experiments) -- exam section hub

Refs:

* LangSmith docs: Evaluate an application\
  <https://docs.langchain.com/langsmith/evaluate-llm-application>

* LangSmith evaluation concepts\
  <https://docs.langchain.com/langsmith/evaluation-concepts>

Tags:

    #building-reliable-agents #langsmith-evaluation #exam-test
