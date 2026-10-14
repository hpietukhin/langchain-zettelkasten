# Connect to a deployment with the LangGraph SDK or RemoteGraph

`langgraph_sdk.get_client(url=..., api_key=...)` gives async clients for assistants, threads, runs, crons and store. `RemoteGraph` wraps a deployed graph so it can be invoked like a local graph or used as a node/subgraph. Requests to LangSmith-hosted deployments authenticate with `x-api-key` by default.

```python
from langgraph_sdk import get_client
client = get_client(url="https://my-deploy.us.langgraph.app", api_key=LANGSMITH_API_KEY)
threads = await client.threads.search(metadata={"user_id": "u1"})
```

Related:

* [20261014100200](../20261014100200) Threads hold state, runs execute; stateless and background runs -- SDK resources

* [20261014100800](../20261014100800) @auth.authenticate validates credentials and returns the user -- requests carry an API key or custom token

* [20261014083200](../20261014083200) Streaming modes expose progress, tokens and updates -- the same stream modes

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith Deployment course, Module 2 Lesson 1: Connecting\
  <https://academy.langchain.com/courses/langsmith-deployment>

* LangSmith docs: RemoteGraph\
  <https://docs.langchain.com/langsmith/use-remote-graph>

Tags:

    #langsmith-deployment-foundations #connecting-with-your-agent #exam-deploy
