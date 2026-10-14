# Align LLM judges to human labels before trusting them

LangSmith's **Align Evaluator** flow: select experiments or runs, have experts label them in an annotation queue, test the judge prompt against the labels, inspect disagreements, refine the prompt and repeat. The *alignment score* is the percentage of examples where the judge agrees with the human label. Works for offline and online evaluators.

```python
# alignment score = agree / total
labels = {"ex1": True, "ex2": False, "ex3": True}
judge  = {"ex1": True, "ex2": True,  "ex3": True}
score = sum(labels[k] == judge[k] for k in labels) / len(labels)   # 0.67 -> refine the prompt
```

Related:

* [20261014093300](../20261014093300) LLM-as-judge grades subjective qualities with a model -- what is aligned

* [20261014094100](../20261014094100) Annotation queues route runs to human reviewers -- where humans label

* [20261014093600](../20261014093600) Reading experiments without overfitting to noise -- misaligned judges create false signals

* [20261014101700](../20261014101700) Structure: Exam section 2 · Test (evaluators and experiments) -- exam section hub

Refs:

* LangSmith docs: Improve LLM-as-judge evaluators using human feedback\
  <https://docs.langchain.com/langsmith/improve-judge-evaluator-feedback>

Tags:

    #building-reliable-agents #langsmith-evaluation #evaluator-alignment #exam-test
