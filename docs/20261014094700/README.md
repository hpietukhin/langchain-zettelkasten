# LangChain Tuned Evaluators: managed judges like Perceived Error

Beta, enabled by an org admin. Perceived Error (Tuned) flags threads where the user appears to perceive a mistake, even without explicit ratings or system errors. Requires a project with threads (at least two traces, user->assistant message lists); billed only when feedback is attached.

```python
# pseudo-config (UI): tracing project -> Evaluators -> + Evaluator -> LangChain Tuned
# -> Perceived Error (Tuned) -> optional filter + sampling -> Save
```

Related:

* [20261014093900](../20261014093900) Multi-turn online evaluators judge whole threads -- they run on threads

* [20261014094600](../20261014094600) Tracking user sentiment with feedback -- detects perceived errors

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* LangSmith docs: Tuned evaluators\
  <https://docs.langchain.com/langsmith/tuned-evaluators>

Tags:

    #monitoring-production-agents #online-evals #exam-monitor
