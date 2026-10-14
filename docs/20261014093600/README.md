# Reading experiments without overfitting to noise

Agent outputs and LLM judges are stochastic. Before trusting a delta: repeat runs (`num_repetitions`) and look at variance, compare experiments per example (the comparison view highlights regressions/improvements), check whether differences are bigger than run-to-run noise, inspect the actual traces of changed examples, and avoid tuning prompts to a handful of examples (keep a held-out split).

```python
client.evaluate(target, data="Email triage", evaluators=[exact_label],
                num_repetitions=3, experiment_prefix="candidate-prompt-v2")
```

Related:

* [20261014093000](../20261014093000) An experiment runs a target over a dataset with evaluators -- what you compare

* [20261014094000](../20261014094000) Align LLM judges to human labels before trusting them -- a noisy judge looks like a regression

* [20261014092800](../20261014092800) Datasets are collections of examples for offline evaluation -- small datasets amplify noise

* [20261014101700](../20261014101700) Structure: Exam section 2 · Test (evaluators and experiments) -- exam section hub

Refs:

* Building Reliable Agents, Module 2 Lesson 3: Running Experiments\
  <https://academy.langchain.com/courses/building-reliable-agents>

* LangSmith docs: Evaluate an application\
  <https://docs.langchain.com/langsmith/evaluate-llm-application>

Tags:

    #building-reliable-agents #langsmith-evaluation #running-experiments #exam-test
