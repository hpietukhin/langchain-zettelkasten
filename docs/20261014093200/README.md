# Code-based evaluators: deterministic, cheap, exact

Code evaluators check things that have a crisp definition: exact match, regex/format, valid JSON/schema, whether a specific tool was called, trajectory order, length, latency. They are fast, free and perfectly consistent, so prefer them whenever the criterion can be programmed.

```python
def called_search_tool(outputs: dict) -> bool:
    msgs = outputs["messages"]
    return any(tc["name"] == "search" for m in msgs for tc in getattr(m, "tool_calls", []) or [])
```

Related:

* [20261014093300](../20261014093300) LLM-as-judge grades subjective qualities with a model -- the alternative

* [20261014093400](../20261014093400) Choosing an evaluator: code first, judge for semantics, humans for ground truth -- when to use which

* [20261014093100](../20261014093100) Evaluators take inputs, outputs and reference_outputs -- the function shape

* [20261014101700](../20261014101700) Structure: Exam section 2 · Test (evaluators and experiments) -- exam section hub

Refs:

* Building Reliable Agents, Module 2 Lesson 4: Code-based Eval\
  <https://academy.langchain.com/courses/building-reliable-agents>

* LangSmith docs: Code evaluators\
  <https://docs.langchain.com/langsmith/code-evaluator>

Tags:

    #building-reliable-agents #langsmith-evaluation #code-based-evals #exam-test
