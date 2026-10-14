# A revision ships new code to an existing deployment

Creating a deployment creates its first revision. Later code changes are released as new revisions (UI "+ New Revision", or `langgraph deploy` again for CLI-created deployments) without creating a new deployment; the revision form also edits environment variables and secrets. Interrupt a revision only if it is stuck.

```python
# shell
# langgraph deploy            # finds the deployment by name and creates a new revision
```

Related:

* [20261014095400](../20261014095400) Deployment terminology: graph, deployment, revision, assistant, thread, run -- revision vs deployment

* [20261014101100](../20261014101100) Secrets belong in deployment environment variables, not code -- revisions can change env vars and secrets

* [20261014100100](../20261014100100) Assistants version configuration separately from code -- config changes don't need a revision

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Revisions\
  <https://docs.langchain.com/langsmith/deployment-revisions>

Tags:

    #langsmith-deployment-foundations #deploy-your-agent #exam-deploy
