# Serverless vs Dedicated deployments

Serverless: cost-optimised, shared multi-tenant database, scales to zero when idle (beta); good for dev, previews and latency-tolerant agents. Dedicated: always on, own database with backups and HA, autoscaling replicas; for customer-facing production. Both in Small/Medium/Large; the type is immutable after creation, the size is not. Max request payload 25 MB.

```python
# shell: langgraph deploy --deployment-type ...   (type fixed at creation)
```

Related:

* [20261014095400](../20261014095400) Deployment terminology: graph, deployment, revision, assistant, thread, run -- a deployment's type

* [20261014095600](../20261014095600) The Agent Server: API server, Postgres and Redis task queue -- same server, different infrastructure

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Cloud platform features\
  <https://docs.langchain.com/langsmith/cloud-platform-features>

Tags:

    #langsmith-deployment-foundations #deploy-your-agent #exam-deploy
