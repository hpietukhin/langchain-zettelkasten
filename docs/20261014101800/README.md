# Structure: Exam section 3 · Deploy (LangSmith Deployment)

Deploy = 25%. Course: LangSmith Deployment Foundations. Focus areas: terminology (graph, deployment, revision, assistant, thread, run), multi-region serving, secret handling, authentication vs authorization, storage durability.

The Related list below is grouped by focus area / module (the text after -- names the group). Find all notes of this area with: pyzet grep '#exam-deploy'

Related:

* [20261014095400](../20261014095400) Deployment terminology: graph, deployment, revision, assistant, thread, run -- terminology

* [20261014095500](../20261014095500) langgraph.json declares graphs, dependencies and env -- terminology

* [20261014100000](../20261014100000) A revision ships new code to an existing deployment -- terminology

* [20261014100100](../20261014100100) Assistants version configuration separately from code -- terminology

* [20261014100200](../20261014100200) Threads hold state, runs execute; stateless and background runs -- terminology

* [20261014095600](../20261014095600) The Agent Server: API server, Postgres and Redis task queue -- terminology

* [20261014095900](../20261014095900) Export a compiled graph unless you need per-run factories -- terminology

* [20261014101400](../20261014101400) Serverless vs Dedicated deployments -- terminology

* [20261014101000](../20261014101000) Data regions: where LangSmith and deployments live -- multi-region serving

* [20261014101100](../20261014101100) Secrets belong in deployment environment variables, not code -- secret handling

* [20261014095300](../20261014095300) Redact secrets from traces with an anonymizer -- secret handling

* [20261014101300](../20261014101300) Encryption at rest for Agent Server data -- secret handling

* [20261014100700](../20261014100700) Authentication vs authorization -- authentication vs authorization

* [20261014100800](../20261014100800) @auth.authenticate validates credentials and returns the user -- authentication vs authorization

* [20261014100900](../20261014100900) @auth.on handlers enforce per-resource access -- authentication vs authorization

* [20261014095700](../20261014095700) Storage durability on LangSmith Deployment -- storage durability

* [20261014095800](../20261014095800) Don't configure a checkpointer or store in deployed graph code -- storage durability

* [20261014091400](../20261014091400) Checkpoints snapshot state at every super-step -- storage durability

* [20261014091800](../20261014091800) Durability modes trade speed for crash safety -- storage durability

* [20261014101200](../20261014101200) TTLs bound how long threads, checkpoints and store items live -- storage durability

* [20261014085000](../20261014085000) StoreBackend makes files durable across threads -- storage durability

* [20261014100300](../20261014100300) Connect to a deployment with the LangGraph SDK or RemoteGraph -- connecting and operating

* [20261014100400](../20261014100400) Double texting strategies: enqueue, reject, interrupt, rollback -- connecting and operating

* [20261014100500](../20261014100500) Cron jobs run assistants on a schedule -- connecting and operating

* [20261014100600](../20261014100600) Custom routes add your own HTTP endpoints to the Agent Server -- connecting and operating

* [20261014101500](../20261014101500) langgraph dev runs a local Agent Server with Studio -- connecting and operating

* [20261014090500](../20261014090500) Managed Deep Agents run a deep agent as a LangSmith-hosted service -- connecting and operating

Refs:

* LangSmith Deployment course\
  <https://academy.langchain.com/courses/langsmith-deployment>

* LangSmith docs: Agent Server\
  <https://docs.langchain.com/langsmith/agent-server>

Tags:

    #exam-deploy #structure-note
