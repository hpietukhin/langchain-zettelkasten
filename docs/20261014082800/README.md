# PIIMiddleware detects and handles sensitive data

`PIIMiddleware(pii_type, detector=..., strategy=...)` scans content for built-in types (e.g. email, credit card) or custom regex/function detectors and applies a strategy such as `block`, `redact`, `mask` or `hash`. It is a deterministic guardrail that runs inside the agent.

```python
from langchain.agents.middleware import PIIMiddleware

agent = create_agent(model="gpt-5.5", tools=[], middleware=[
    PIIMiddleware("email", strategy="redact"),
    PIIMiddleware("api_key", detector=r"sk-[a-zA-Z0-9]{32}", strategy="block"),
])
```

Related:

* [20261014095300](../20261014095300) Redact secrets from traces with an anonymizer -- redaction on the tracing side

* [20261014095200](../20261014095200) Monitoring security: prompt injection, data leaks, abuse -- monitoring for leaks in production

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Built-in middleware\
  <https://docs.langchain.com/oss/python/langchain/middleware/built-in>

* LangChain docs: Guardrails\
  <https://docs.langchain.com/oss/python/langchain/guardrails>

Tags:

    #langchain-foundations #guardrails #middleware #monitoring-security #exam-build
