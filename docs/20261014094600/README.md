# Tracking user sentiment with feedback

Explicit sentiment: log thumbs up/down or ratings as feedback on the run (`create_feedback`). Implicit sentiment: an online LLM judge or tuned evaluator infers frustration from the conversation. Feedback scores become chartable metrics and alert conditions.

```python
from langsmith import Client
Client().create_feedback(run_id, key="user_score", score=1, comment="Great answer")
```

Related:

* [20261014093900](../20261014093900) Multi-turn online evaluators judge whole threads -- infer sentiment from conversations

* [20261014095100](../20261014095100) Alerts fire on threshold breaches of a project metric -- alert on feedback score drops

* [20261014094700](../20261014094700) LangChain Tuned Evaluators: managed judges like Perceived Error -- Perceived Error detects implicit dissatisfaction

* [20261014101900](../20261014101900) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts) -- exam section hub

Refs:

* Monitoring Production Agents, Module 3: Monitoring User Sentiment\
  <https://academy.langchain.com/courses/production-monitoring>

* LangSmith docs: Agent Server feedback\
  <https://docs.langchain.com/langsmith/agent-server-feedback>

Tags:

    #monitoring-production-agents #monitoring-quality #human-feedback #exam-monitor
