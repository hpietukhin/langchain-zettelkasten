# Managed Deep Agents run a deep agent as a LangSmith-hosted service

Deep Agents can run self-hosted (your own Agent Server image via `langgraph build`) or as Managed Deep Agents in LangSmith; tools, middleware and subagents carry over unchanged. Deployments include an Agent Server (streaming, threads, run history, webhooks, auth) and multi-tenancy (scoped threads, per-user sandboxes, RBAC).

```python
# same agent definition works in both modes
agent = create_deep_agent(model="openai:gpt-5.5", tools=[search], skills=["/skills/"])
# self-host: `langgraph build` ; managed: deploy via LangSmith (MDA project structure)
```

Related:

* [20261014083500](../20261014083500) Deep Agents is a batteries-included agent harness -- the same harness

* [20261014095400](../20261014095400) Deployment terminology: graph, deployment, revision, assistant, thread, run -- runs on LangSmith Deployment primitives

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* Deep Agents course, Module 6: Managed Deep Agents\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

* Deep Agents docs: Comparison\
  <https://docs.langchain.com/oss/python/deepagents/comparison>

Tags:

    #deep-agents-foundations #managed-deep-agents #langsmith-deployment-foundations #exam-deploy
