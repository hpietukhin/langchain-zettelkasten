# Pairwise evaluation compares two experiments head-to-head

When absolute scores are unreliable ("is this summary good?"), it is easier to ask which of two outputs is better. `evaluate((exp_a, exp_b), evaluators=[...])` gives the evaluator both outputs per example; `randomize_order=True` reduces position bias.

```python
from langsmith import evaluate

def ranked_preference(inputs: dict, outputs: list[dict]) -> list:
    pref = judge_prefers(inputs["question"], outputs[0]["answer"], outputs[1]["answer"])
    return [1, 0] if pref == 1 else [0, 1] if pref == 2 else [0, 0]

evaluate(("experiment-1", "experiment-2"), evaluators=[ranked_preference], randomize_order=True)
```

Related:

* [20261014093000](../20261014093000) An experiment runs a target over a dataset with evaluators -- compares existing experiments

* [20261014093300](../20261014093300) LLM-as-judge grades subjective qualities with a model -- usually a judge decides the preference

* [20261014101700](../20261014101700) Structure: Exam section 2 · Test (evaluators and experiments) -- exam section hub

Refs:

* Building Reliable Agents, Module 2 Lesson 6: Pairwise Evaluations\
  <https://academy.langchain.com/courses/building-reliable-agents>

* LangSmith docs: Pairwise evaluations\
  <https://docs.langchain.com/langsmith/evaluate-pairwise>

Tags:

    #building-reliable-agents #langsmith-evaluation #pairwise-evaluations #exam-test
