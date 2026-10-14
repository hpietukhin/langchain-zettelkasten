# Deployment terminology: graph, deployment, revision, assistant, thread, run

*Graph*: the code blueprint (a compiled LangGraph/agent) registered in `langgraph.json`. *Deployment*: a running Agent Server instance on LangSmith hosting one or more graphs with its database. *Revision*: one deployed version of the code/config of a deployment; new code = new revision, same deployment. *Assistant*: a graph + a specific configuration (prompt, model, tools); each graph gets a default assistant. *Thread*: a persistent conversation with its checkpointed state. *Run*: one execution of an assistant, usually on a thread.

```python
from langgraph_sdk import get_client
client = get_client(url=DEPLOYMENT_URL)                     # deployment
assistant = await client.assistants.create("agent", config={"configurable": {"model": "gpt-5.5"}})  # graph "agent"
thread = await client.threads.create()                      # thread
run = await client.runs.wait(thread["thread_id"], assistant["assistant_id"],
                             input={"messages": [{"role": "user", "content": "hi"}]})  # run
```

Related:

* [20261014095500](../20261014095500) langgraph.json declares graphs, dependencies and env -- graphs are registered in langgraph.json

* [20261014100000](../20261014100000) A revision ships new code to an existing deployment -- revision

* [20261014100100](../20261014100100) Assistants version configuration separately from code -- assistant

* [20261014100200](../20261014100200) Threads hold state, runs execute; stateless and background runs -- thread and run

* [20261014095600](../20261014095600) The Agent Server: API server, Postgres and Redis task queue -- what a deployment runs

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith Deployment course, Module 1 Concepts\
  <https://academy.langchain.com/courses/langsmith-deployment>

* LangSmith docs: Agent Server\
  <https://docs.langchain.com/langsmith/agent-server>

* LangSmith docs: Assistants\
  <https://docs.langchain.com/langsmith/assistants>

Tags:

    #langsmith-deployment-foundations #deploy-your-agent #exam-deploy
