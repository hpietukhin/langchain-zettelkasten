# Cost tracking derives spend from token usage and model pricing

LangSmith computes cost for LLM runs from token counts (input, output, and details such as cache reads) and a model price map; LangChain integrations report usage automatically. For custom models, trace with `run_type="llm"`, metadata `ls_provider`/`ls_model_name`, and return `usage_metadata`. Costs roll up per trace, thread and project; slice by metadata to attribute cost to users or features.

```python
from langsmith import traceable

@traceable(run_type="llm", metadata={"ls_provider": "my_provider", "ls_model_name": "my_model"})
def chat_model(messages: list):
    return {"choices": [{"message": {"role": "assistant", "content": "Sure"}}],
            "usage_metadata": {"input_tokens": 27, "output_tokens": 13, "total_tokens": 40}}
```

Related:

* [20261014092500](../20261014092500) Reading a trace: project, trace, run, run types -- llm runs carry usage

* [20261014095100](../20261014095100) Alerts fire on threshold breaches of a project metric -- cost alerts

* [20261014092600](../20261014092600) Metadata and tags make traces filterable -- attribute cost by user or feature

* [20261014094900](../20261014094900) Dashboards chart project metrics over time -- chart cost over time

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* Monitoring Production Agents, Module 1: Token and Cost Breakdowns / Tracking Costs\
  <https://academy.langchain.com/courses/production-monitoring>

* LangSmith docs: Cost tracking\
  <https://docs.langchain.com/langsmith/cost-tracking>

Tags:

    #monitoring-production-agents #monitoring-cost #exam-monitor
