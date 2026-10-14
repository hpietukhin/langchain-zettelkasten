# Choosing an evaluator: code first, judge for semantics, humans for ground truth

Ask: can the criterion be checked programmatically? Use code. Is it semantic or open-ended? Use an LLM judge (aligned to humans). Is it hard to score absolutely but easy to compare? Use pairwise. Is ground truth unknown? Use human annotation. Exam tip: an exact-format or tool-call check never needs an LLM judge.

```python
evaluators = [called_search_tool,       # code: tool usage
              exact_label,              # code: classification
              correctness_evaluator]    # LLM judge: free-text answer quality
```

Related:

* [20261014093200](../20261014093200) Code-based evaluators: deterministic, cheap, exact -- deterministic

* [20261014093300](../20261014093300) LLM-as-judge grades subjective qualities with a model -- semantic

* [20261014094100](../20261014094100) Annotation queues route runs to human reviewers -- human

* [20261014093500](../20261014093500) Pairwise evaluation compares two experiments head-to-head -- relative preference

* [20261014093700](../20261014093700) Offline vs online evaluation -- where it runs

* [20261014101700](../20261014101700) Structure: Exam section 2 · Test (evaluators and experiments) -- exam section hub

Refs:

* Building Reliable Agents, Module 2 Lesson 1: Evaluating Agents\
  <https://academy.langchain.com/courses/building-reliable-agents>

* LangSmith evaluation concepts\
  <https://docs.langchain.com/langsmith/evaluation-concepts>

Tags:

    #building-reliable-agents #langsmith-evaluation #exam-test
