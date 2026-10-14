# Threads hold state, runs execute; stateless and background runs

A thread accumulates checkpoints across runs; a run on a thread continues the conversation. Runs can be streamed, awaited (`runs.wait`), launched in the background and joined later, cancelled, or stateless (no thread: nothing persisted). Threads can be searched, copied and given a TTL.

```python
thread = await client.threads.create()
async for chunk in client.runs.stream(thread["thread_id"], "agent",
                                      input={"messages": [{"role": "user", "content": "hi"}]},
                                      stream_mode="updates"):
    print(chunk.event, chunk.data)
```

Related:

* [20261014095400](../20261014095400) Deployment terminology: graph, deployment, revision, assistant, thread, run -- definitions

* [20261014100400](../20261014100400) Double texting strategies: enqueue, reject, interrupt, rollback -- several runs on one thread

* [20261014100300](../20261014100300) Connect to a deployment with the LangGraph SDK or RemoteGraph -- how to call them

* [20261014100500](../20261014100500) Cron jobs run assistants on a schedule -- scheduled runs

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Use threads\
  <https://docs.langchain.com/langsmith/use-threads>

* LangSmith docs: Runs\
  <https://docs.langchain.com/langsmith/runs>

Tags:

    #langsmith-deployment-foundations #connecting-with-your-agent #exam-deploy
