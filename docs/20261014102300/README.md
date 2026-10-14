# Structure: Course · Introduction to LangSmith Deployment

Free Academy course: Module 1 Deploy Your Agent, Module 2 Connecting With Your Agent, Module 3 Deployment UI, Module 4 Memory, Module 5 Multi-Tenant Auth, Module 6 Deep Agent Deploy.

The Related list below is grouped by focus area / module (the text after -- names the group). Find all notes of this area with: pyzet grep '#langsmith-deployment-foundations'

Related:

* [20261014095400](../20261014095400) Deployment terminology: graph, deployment, revision, assistant, thread, run -- Module 1: Deploy Your Agent

* [20261014095500](../20261014095500) langgraph.json declares graphs, dependencies and env -- Module 1: Deploy Your Agent

* [20261014095600](../20261014095600) The Agent Server: API server, Postgres and Redis task queue -- Module 1: Deploy Your Agent

* [20261014095900](../20261014095900) Export a compiled graph unless you need per-run factories -- Module 1: Deploy Your Agent

* [20261014100000](../20261014100000) A revision ships new code to an existing deployment -- Module 1: Deploy Your Agent

* [20261014101400](../20261014101400) Serverless vs Dedicated deployments -- Module 1: Deploy Your Agent

* [20261014101500](../20261014101500) langgraph dev runs a local Agent Server with Studio -- Module 1: Deploy Your Agent

* [20261014101100](../20261014101100) Secrets belong in deployment environment variables, not code -- Module 1: Deploy Your Agent

* [20261014101000](../20261014101000) Data regions: where LangSmith and deployments live -- Module 1: Deploy Your Agent

* [20261014100300](../20261014100300) Connect to a deployment with the LangGraph SDK or RemoteGraph -- Module 2: Connecting With Your Agent

* [20261014100100](../20261014100100) Assistants version configuration separately from code -- Module 2: Connecting With Your Agent

* [20261014100200](../20261014100200) Threads hold state, runs execute; stateless and background runs -- Module 2: Connecting With Your Agent

* [20261014100400](../20261014100400) Double texting strategies: enqueue, reject, interrupt, rollback -- Module 2: Connecting With Your Agent

* [20261014100600](../20261014100600) Custom routes add your own HTTP endpoints to the Agent Server -- Module 2: Connecting With Your Agent

* [20261014100500](../20261014100500) Cron jobs run assistants on a schedule -- Module 2: Connecting With Your Agent

* [20261014095700](../20261014095700) Storage durability on LangSmith Deployment -- Module 4: Memory

* [20261014095800](../20261014095800) Don't configure a checkpointer or store in deployed graph code -- Module 4: Memory

* [20261014101200](../20261014101200) TTLs bound how long threads, checkpoints and store items live -- Module 4: Memory

* [20261014101300](../20261014101300) Encryption at rest for Agent Server data -- Module 4: Memory

* [20261014085000](../20261014085000) StoreBackend makes files durable across threads -- Module 4: Memory

* [20261014090100](../20261014090100) Agent-scoped vs user-scoped memory via store namespaces -- Module 4: Memory

* [20261014100700](../20261014100700) Authentication vs authorization -- Module 5: Multi-Tenant Auth

* [20261014100800](../20261014100800) @auth.authenticate validates credentials and returns the user -- Module 5: Multi-Tenant Auth

* [20261014100900](../20261014100900) @auth.on handlers enforce per-resource access -- Module 5: Multi-Tenant Auth

* [20261014090500](../20261014090500) Managed Deep Agents run a deep agent as a LangSmith-hosted service -- Module 6: Deep Agent Deploy

* [20261014085400](../20261014085400) Sandbox lifecycle: thread-scoped or assistant-scoped -- Module 6: Deep Agent Deploy

Refs:

* Introduction to LangSmith Deployment\
  <https://academy.langchain.com/courses/langsmith-deployment>

Tags:

    #langsmith-deployment-foundations #structure-note
