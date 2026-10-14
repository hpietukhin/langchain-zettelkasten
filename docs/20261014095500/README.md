# langgraph.json declares graphs, dependencies and env

A deployable app has dependency files (requirements.txt/pyproject), the graph code, and `langgraph.json`. `graphs` maps graph IDs to `path:variable`; `dependencies` lists packages to install; `env` points to an env file for local runs. Multiple graphs can share one deployment.

```python
LANGGRAPH_JSON = {
    "dependencies": ["."],
    "graphs": {"my_agent": "./your_package/your_file.py:agent"},
    "env": "./.env",
}
```

Related:

* [20261014095400](../20261014095400) Deployment terminology: graph, deployment, revision, assistant, thread, run -- graph IDs come from here

* [20261014095900](../20261014095900) Export a compiled graph unless you need per-run factories -- how the graph is exported

* [20261014101100](../20261014101100) Secrets belong in deployment environment variables, not code -- env file vs deployment secrets

* [20261014101200](../20261014101200) TTLs bound how long threads, checkpoints and store items live -- TTL also lives here

* [20261014100600](../20261014100600) Custom routes add your own HTTP endpoints to the Agent Server -- http.app also lives here

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Application structure\
  <https://docs.langchain.com/langsmith/application-structure>

* LangSmith Deployment course, Module 1 Lesson 2: Deploy\
  <https://academy.langchain.com/courses/langsmith-deployment>

Tags:

    #langsmith-deployment-foundations #deploy-your-agent #exam-deploy
