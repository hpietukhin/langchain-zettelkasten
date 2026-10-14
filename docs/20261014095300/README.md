# Redact secrets from traces with an anonymizer

`Client(anonymizer=create_secret_anonymizer())` replaces known credential formats in inputs, outputs, errors and metadata with `[SECRET_DETECTED]` before upload; `extra_rules` adds custom patterns, `create_anonymizer` uses only your rules. Run names, tags and attachments are not redacted, and redaction is not access control.

```python
from langsmith import Client
from langsmith.anonymizer import create_secret_anonymizer
client = Client(anonymizer=create_secret_anonymizer())
```

Related:

* [20261014082800](../20261014082800) PIIMiddleware detects and handles sensitive data -- in-agent PII handling

* [20261014101100](../20261014101100) Secrets belong in deployment environment variables, not code -- secrets in deployments

* [20261014095200](../20261014095200) Monitoring security: prompt injection, data leaks, abuse -- part of security posture

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Redact secrets from traces\
  <https://docs.langchain.com/langsmith/redact-secrets>

Tags:

    #monitoring-production-agents #monitoring-security #secret-handling #exam-deploy
