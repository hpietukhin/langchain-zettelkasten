# @auth.authenticate validates credentials and returns the user

The handler may accept `authorization`, `headers`, `path`, `method`, etc. It validates the token (e.g. JWT from Auth0/Supabase) and returns a user dict with at least `identity`, or raises `Auth.exceptions.HTTPException(401)`. The user is available to AuthZ handlers as `ctx.user` and inside the graph via `config["configuration"]["langgraph_auth_user"]`.

```python
from langgraph_sdk import Auth
auth = Auth()

@auth.authenticate
async def authenticate(authorization: str | None) -> Auth.types.MinimalUserDict:
    user = verify_jwt(authorization)          # your IdP check
    if not user:
        raise Auth.exceptions.HTTPException(status_code=401, detail="Invalid token")
    return {"identity": user["sub"]}
```

Related:

* [20261014100700](../20261014100700) Authentication vs authorization -- concept

* [20261014100900](../20261014100900) @auth.on handlers enforce per-resource access -- uses ctx.user from here

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith Deployment course, Module 5 Lesson 2: Authentication\
  <https://academy.langchain.com/courses/langsmith-deployment>

* LangSmith docs: Authentication & access control\
  <https://docs.langchain.com/langsmith/auth>

Tags:

    #langsmith-deployment-foundations #multi-tenant-auth #exam-deploy
