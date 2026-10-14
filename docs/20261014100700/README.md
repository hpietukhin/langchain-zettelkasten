# Authentication vs authorization

Authentication (AuthN) verifies *who* the caller is and runs on every request (`@auth.authenticate`). Authorization (AuthZ) decides *what* that identity may do with a specific resource (`@auth.on` handlers). Typical setup: an identity provider issues tokens, the client sends them, the Agent Server (resource server) validates them and enforces ownership. LangSmith Cloud defaults to LangSmith API keys (`x-api-key`); self-hosted has no default auth.

```python
from langgraph_sdk import Auth
auth = Auth()           # referenced in langgraph.json: {"auth": {"path": "./auth.py:auth"}}
```

Related:

* [20261014100800](../20261014100800) @auth.authenticate validates credentials and returns the user -- AuthN handler

* [20261014100900](../20261014100900) @auth.on handlers enforce per-resource access -- AuthZ handlers

* [20261014090100](../20261014090100) Agent-scoped vs user-scoped memory via store namespaces -- user identity scopes memory

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith Deployment course, Module 5 Lesson 1: Introduction to Auth\
  <https://academy.langchain.com/courses/langsmith-deployment>

* LangSmith docs: Authentication & access control\
  <https://docs.langchain.com/langsmith/auth>

Tags:

    #langsmith-deployment-foundations #multi-tenant-auth #exam-deploy
