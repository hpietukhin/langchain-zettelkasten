# Cron jobs run assistants on a schedule

`client.crons.create(assistant_id, schedule="0 9 * * *", input=...)` creates a new thread per execution; `crons.create_for_thread` reuses one thread. Delete crons you no longer need to avoid cost.

```python
cron = await client.crons.create("agent", schedule="0 9 * * 1-5",
                                 input={"messages": [{"role": "user", "content": "Summarise my inbox"}]})
await client.crons.delete(cron["cron_id"])
```

Related:

* [20261014092000](../20261014092000) Ambient agents act on event streams, not chat prompts -- scheduled triggers for background agents

* [20261014100200](../20261014100200) Threads hold state, runs execute; stateless and background runs -- crons create runs

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Cron jobs\
  <https://docs.langchain.com/langsmith/cron-jobs>

Tags:

    #langsmith-deployment-foundations #ambient-agents #exam-deploy
