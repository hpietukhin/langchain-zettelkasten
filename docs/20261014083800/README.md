# The Deep Agents middleware stack

`create_deep_agent` builds middleware in a fixed order (the "bare stack" with only a model, the "full stack" with optional arguments). Middleware you pass is merged by `.name`: a match replaces the built-in instance in place; anything else is inserted into the stack. Required scaffolding such as `SubAgentMiddleware` cannot be excluded.

```python
from langchain.agents.middleware import ModelCallLimitMiddleware

agent = create_deep_agent(
    model="openai:gpt-5.5",
    middleware=[ModelCallLimitMiddleware(run_limit=50)],  # inserted into the deep agents stack
)
```

Related:

* [20261014081500](../20261014081500) Middleware hooks into every step of the agent loop -- deep agents are middleware compositions

* [20261014083100](../20261014083100) Catalogue of built-in middleware -- standard middleware reused

* [20261014090400](../20261014090400) Harness profiles tune the harness per provider or model -- profiles tweak the stack per model

* [20261014082100](../20261014082100) SummarizationMiddleware compresses old history -- always in the bare stack

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Customization\
  <https://docs.langchain.com/oss/python/deepagents/customization>

Tags:

    #deep-agents-foundations #middleware #exam-build
