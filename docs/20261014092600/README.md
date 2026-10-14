# Metadata and tags make traces filterable

Tags are strings, metadata is key/value. Attach them statically on `@traceable`, dynamically via the run tree, or with `config={"tags": [...], "metadata": {...}}` on LangChain invocations. Use them for user IDs, plan type, prompt/model version and environment so you can filter, group dashboards and target evaluators.

```python
import langsmith as ls

@ls.traceable(tags=["my-tag"], metadata={"my-key": "my-value"})
def call(q): ...

agent.invoke(inputs, config={"tags": ["prod"], "metadata": {"user_id": "u1", "variant": "B"}})
```

Related:

* [20261014092700](../20261014092700) Group traces into threads with session_id or thread_id metadata -- thread IDs are metadata

* [20261014095000](../20261014095000) A/B testing agents in production with metadata -- variants as metadata

* [20261014093800](../20261014093800) Online evaluators score production runs with filters and sampling -- filters select which runs to score

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* LangSmith docs: Add metadata and tags\
  <https://docs.langchain.com/langsmith/add-metadata-tags>

Tags:

    #monitoring-production-agents #langsmith-observability #exam-monitor
