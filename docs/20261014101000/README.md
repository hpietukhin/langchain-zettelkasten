# Data regions: where LangSmith and deployments live

LangSmith Cloud orgs live in one region: smith.langchain.com (GCP US), eu.smith.langchain.com (GCP EU), apac.smith.langchain.com (APAC), aws.smith.langchain.com (AWS US). A deployment's data region (US or EU) is implied by the org where it is created; deployments and their databases cannot be migrated between regions, and an org cannot have workspaces in several regions. For multi-region serving you create separate orgs/deployments per region and route users to the nearest one. Static NAT IPs per region help allowlisting.

```python
import os
os.environ["LANGSMITH_ENDPOINT"] = "https://eu.api.smith.langchain.com"   # EU org for tracing/SDK
eu_client = get_client(url=EU_DEPLOYMENT_URL)
us_client = get_client(url=US_DEPLOYMENT_URL)
client = eu_client if user_region == "eu" else us_client
```

Related:

* [20261014095400](../20261014095400) Deployment terminology: graph, deployment, revision, assistant, thread, run -- a deployment belongs to an org

* [20261014101100](../20261014101100) Secrets belong in deployment environment variables, not code -- region-specific endpoints in env

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Cloud platform features\
  <https://docs.langchain.com/langsmith/cloud-platform-features>

* LangSmith docs: Regions FAQ\
  <https://docs.langchain.com/langsmith/regions-faq>

Tags:

    #langsmith-deployment-foundations #multi-region #exam-deploy
