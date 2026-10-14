# MCP exposes external tools through a standard protocol

The Model Context Protocol standardises how applications offer tools and context to LLMs. LangChain can connect to an MCP server, list its tools, and hand them to `create_agent` or `create_deep_agent` like any other tool. Servers can be local (stdio) or remote (HTTP), and connections can be authenticated. Install the extra with `pip install "langchain[mcp]"`.

```python
from langchain.agents import create_agent
from langchain.mcp import MCPAdapter

async def main():
    async with MCPAdapter("https://example.com/mcp") as adapter:
        tools = await adapter.list_tools()
        agent = create_agent("claude-sonnet-5", tools)
        return await agent.ainvoke({"messages": [{"role": "user", "content": "..."}]})
```

Related:

* [20261014080400](../20261014080400) Tools are typed functions whose docstring is the model's manual -- MCP tools become ordinary LangChain tools

* [20261014083500](../20261014083500) Deep Agents is a batteries-included agent harness -- deep agents accept MCP tools too

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: MCP\
  <https://docs.langchain.com/oss/python/langchain/mcp/index>

* Intro to LangChain, Module 2 Lesson 1: MCP\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

* Deep Agents course, Lesson 6: MCP\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #langchain-foundations #model-context-protocol #langchain-tools #deep-agents-foundations #exam-build
