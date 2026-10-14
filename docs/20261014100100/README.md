# Assistants version configuration separately from code

An assistant is an instance of a graph with a specific configuration (prompts, model, tools). One graph can have many assistants (per customer, environment, A/B variant). Editing creates a new version you can promote or roll back. Invoke by graph ID (default assistant) or assistant UUID. Assistants exist only in LangSmith Deployment, not in open-source LangGraph.

```python
a = await client.assistants.create("agent", config={"configurable": {"system_prompt": "Write tweets"}},
                                   name="tweet-writer")
await client.assistants.update(a["assistant_id"], config={"configurable": {"system_prompt": "Write short tweets"}})
```

Related:

* [20261014095400](../20261014095400) Deployment terminology: graph, deployment, revision, assistant, thread, run -- assistant vs graph

* [20261014100000](../20261014100000) A revision ships new code to an existing deployment -- code changes need revisions, config changes don't

* [20261014095000](../20261014095000) A/B testing agents in production with metadata -- assistants as experiment variants

* [20261014095900](../20261014095900) Export a compiled graph unless you need per-run factories -- factories can read assistant config

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith Deployment course, Module 2 Lesson 2: Assistants\
  <https://academy.langchain.com/courses/langsmith-deployment>

* LangSmith docs: Assistants\
  <https://docs.langchain.com/langsmith/assistants>

Tags:

    #langsmith-deployment-foundations #connecting-with-your-agent #assistants #exam-deploy
