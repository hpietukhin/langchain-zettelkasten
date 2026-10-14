# TodoListMiddleware gives the agent a planning tool

Adds a `write_todos` tool and prompt guidance so the agent writes and updates a task list for multi-step work. Planning keeps long tasks on track and makes progress visible in state and UIs.

```python
from langchain.agents.middleware import TodoListMiddleware

agent = create_agent(model="gpt-5.5", tools=[read_file, write_file, run_tests],
                     middleware=[TodoListMiddleware()])
```

Related:

* [20261014083700](../20261014083700) Deep agents' built-in tools -- deep agents include write_todos by default

* [20261014083600](../20261014083600) create_agent vs create_deep_agent: when to use which -- one of the things deep agents add

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Built-in middleware\
  <https://docs.langchain.com/oss/python/langchain/middleware/built-in>

Tags:

    #langchain-foundations #deep-agents-foundations #middleware #planning #exam-build
