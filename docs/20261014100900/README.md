# @auth.on handlers enforce per-resource access

A broad `@auth.on` handler runs for every resource action; specific handlers like `@auth.on.threads.create` or `@auth.on.assistants` override it. The common pattern adds an `owner` to resource metadata on create and returns a filter dict so reads/searches only see the caller's resources: multi-tenant isolation.

```python
@auth.on
async def add_owner(ctx: Auth.types.AuthContext, value: dict):
    """Make resources private to their creator."""
    filters = {"owner": ctx.user.identity}
    value.setdefault("metadata", {}).update(filters)
    return filters
```

Related:

* [20261014100800](../20261014100800) @auth.authenticate validates credentials and returns the user -- identity source

* [20261014100200](../20261014100200) Threads hold state, runs execute; stateless and background runs -- the resources being protected

* [20261014085400](../20261014085400) Sandbox lifecycle: thread-scoped or assistant-scoped -- multi-tenant isolation

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith Deployment course, Module 5 Lesson 3: Authorization\
  <https://academy.langchain.com/courses/langsmith-deployment>

* LangSmith docs: Resource authorization\
  <https://docs.langchain.com/langsmith/resource-auth>

Tags:

    #langsmith-deployment-foundations #multi-tenant-auth #exam-deploy
