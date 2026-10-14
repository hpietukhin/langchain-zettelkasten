# Offloading moves large tool payloads to the filesystem

When a tool result exceeds a token threshold (default 20,000), the deep agent writes it to the backend and keeps only a file path plus a short preview (first 10 lines) in the conversation. Large tool *inputs* (e.g. full file contents in write/edit calls) are truncated to file pointers once context crosses ~85% of the window. The agent can re-read or grep the file when needed.

```python
# nothing to configure: offloading is part of every create_deep_agent
agent = create_deep_agent(model="openai:gpt-5.5", tools=[huge_sql_query])
# a 50k-token result becomes e.g. "Result saved to /large_tool_results/<id> (preview: ...)"
```

Related:

* [20261014084200](../20261014084200) Deep agents summarise history at about 85% of the window -- the second compression mechanism

* [20261014084700](../20261014084700) Backends decide where a deep agent's files live -- offloaded content lives in the backend

* [20261014082200](../20261014082200) ContextEditingMiddleware clears old tool outputs -- create_agent's simpler analogue

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Context engineering\
  <https://docs.langchain.com/oss/python/deepagents/context-engineering>

* Deep Agents course, Module 3 Lesson 1: Summarization and Offload\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #deep-agents-foundations #context-management #summarization-and-offload #exam-build
