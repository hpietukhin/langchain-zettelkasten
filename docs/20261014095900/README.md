# Export a compiled graph unless you need per-run factories

A compiled graph is loaded once at container start and reused (no per-request overhead). A factory function is called whenever the server needs the graph, letting you choose models/tools per assistant config, but it adds overhead to every invocation, so keep it light.

```python
from langchain.agents import create_agent

agent = create_agent(model="openai:gpt-5.5", tools=[search])          # compiled (recommended)

def make_agent(config):                                               # factory
    model = config["configurable"].get("model", "openai:gpt-5.5")
    return create_agent(model=model, tools=[search])
```

Related:

* [20261014095500](../20261014095500) langgraph.json declares graphs, dependencies and env -- where the export is referenced

* [20261014100100](../20261014100100) Assistants version configuration separately from code -- factories can read assistant config

* [20261014101800](../20261014101800) Structure: Exam section 3 · Deploy (LangSmith Deployment) -- exam section hub

Refs:

* LangSmith docs: Agent Server\
  <https://docs.langchain.com/langsmith/agent-server>

Tags:

    #langsmith-deployment-foundations #deploy-your-agent #exam-deploy
