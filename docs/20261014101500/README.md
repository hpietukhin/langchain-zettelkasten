# langgraph dev runs a local Agent Server with Studio

`langgraph dev` starts an in-memory development server from `langgraph.json` with hot reload, connected to LangSmith Studio for visual debugging (graph view, threads, interrupts, time travel). `langgraph up` runs it in Docker; `langgraph build` builds a production image.

```python
# shell
# pip install -U "langgraph-cli[inmem]"
# langgraph dev            # http://127.0.0.1:2024 + Studio
```

Related:

* [20261014095500](../20261014095500) langgraph.json declares graphs, dependencies and env -- reads langgraph.json

* [20261014095600](../20261014095600) The Agent Server: API server, Postgres and Redis task queue -- same API locally

* [20261014100600](../20261014100600) Custom routes add your own HTTP endpoints to the Agent Server -- test routes locally

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangChain docs: Studio\
  <https://docs.langchain.com/oss/python/langchain/studio>

* LangSmith Deployment course, Module 1\
  <https://academy.langchain.com/courses/langsmith-deployment>

Tags:

    #langsmith-deployment-foundations #intro-to-langgraph #exam-deploy
