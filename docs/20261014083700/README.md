# Deep agents' built-in tools

Out of the box a deep agent gets `write_todos` (planning), filesystem tools `ls`, `read_file`, `write_file`, `edit_file`, `delete`, `glob`, `grep`, and `task` (delegate to a subagent). Sandbox backends and `LocalShellBackend` add `execute` for shell commands. Your own tools are added alongside.

```python
agent = create_deep_agent(model="openai:gpt-5.5", tools=[internet_search])
# model can now call: write_todos, ls, read_file, write_file, edit_file, delete,
# glob, grep, task, internet_search  (+ execute with a sandbox backend)
```

Related:

* [20261014083000](../20261014083000) TodoListMiddleware gives the agent a planning tool -- write_todos

* [20261014084700](../20261014084700) Backends decide where a deep agent's files live -- filesystem tools route through a backend

* [20261014085200](../20261014085200) Sandboxes isolate code execution from the host -- execute appears only with sandbox/shell backends

* [20261014084400](../20261014084400) Defining subagents with dicts or CompiledSubAgent -- the task tool

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Backends\
  <https://docs.langchain.com/oss/python/deepagents/backends>

* Deep Agents course, Module 1 Lesson 5: Tools\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #deep-agents-foundations #deep-agents-overview #exam-build
