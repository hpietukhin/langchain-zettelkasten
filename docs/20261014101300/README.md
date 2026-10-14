# Encryption at rest for Agent Server data

Built-in AES encryption (one key, key rotation, selective JSON fields) covers most cases; custom encryption handlers support per-tenant keys or an external KMS.

```python
# pseudo-config: set the AES key as a deployment secret, e.g. an env var for the Agent Server
# (see the AES encryption guide for the exact variable name and lazy rotation)
```

Related:

* [20261014095700](../20261014095700) Storage durability on LangSmith Deployment -- what gets encrypted

* [20261014101100](../20261014101100) Secrets belong in deployment environment variables, not code -- keys are configured as secrets

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Encryption at rest\
  <https://docs.langchain.com/langsmith/encryption>

Tags:

    #langsmith-deployment-foundations #storage-durability #secret-handling #exam-deploy
