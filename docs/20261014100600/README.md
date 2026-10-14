# Custom routes add your own HTTP endpoints to the Agent Server

Point `http.app` in `langgraph.json` at a Starlette/FastAPI app; its routes are served alongside the built-in API (webhooks receivers, health checks, extra business endpoints). Test locally with `langgraph dev`.

```python
# webapp.py
from fastapi import FastAPI
app = FastAPI()

@app.get("/hello")
def hello():
    return {"hello": "world"}
# langgraph.json: {"http": {"app": "./webapp.py:app"}, ...}
```

Related:

* [20261014095500](../20261014095500) langgraph.json declares graphs, dependencies and env -- registered under http.app in langgraph.json

* [20261014100800](../20261014100800) @auth.authenticate validates credentials and returns the user -- custom auth can also protect custom routes

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith Deployment course, Module 2 Lesson 4: Custom Routes\
  <https://academy.langchain.com/courses/langsmith-deployment>

* LangSmith docs: Custom routes\
  <https://docs.langchain.com/langsmith/custom-routes>

Tags:

    #langsmith-deployment-foundations #connecting-with-your-agent #exam-deploy
