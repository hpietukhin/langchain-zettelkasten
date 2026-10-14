# Secrets belong in deployment environment variables, not code

API keys (model providers, tools) are added as environment variables/secrets when creating the deployment or a new revision; they are injected at runtime and read with `os.environ`. Don't commit `.env`; never pass secrets through prompts or state; give agents scoped credentials; and redact secrets from traces.

```python
import os
from langchain.chat_models import init_chat_model
model = init_chat_model("openai:gpt-5.5", api_key=os.environ["OPENAI_API_KEY"])   # set as a deployment secret
```

Related:

* [20261014100000](../20261014100000) A revision ships new code to an existing deployment -- secrets are edited per revision

* [20261014095500](../20261014095500) langgraph.json declares graphs, dependencies and env -- env file is for local dev

* [20261014095300](../20261014095300) Redact secrets from traces with an anonymizer -- keep them out of traces too

* [20261014101300](../20261014101300) Encryption at rest for Agent Server data -- stored data protection

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Deploy to Cloud\
  <https://docs.langchain.com/langsmith/deploy-to-cloud>

* LangSmith docs: Cloud environment variables\
  <https://docs.langchain.com/langsmith/env-var-cloud>

Tags:

    #langsmith-deployment-foundations #secret-handling #exam-deploy
