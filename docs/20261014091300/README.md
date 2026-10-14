# Subgraphs compose graphs as nodes

A compiled graph can be added as a node of a parent graph. Shared state keys pass through; different schemas need a wrapper function to translate. Subgraphs keep large systems modular (e.g. one team per subgraph).

```python
sub = sub_builder.compile()
parent = StateGraph(State)
parent.add_node("research_team", sub)   # compiled graph as a node
```

Related:

* [20261014090600](../20261014090600) A LangGraph graph is state, nodes and edges -- a compiled graph is a node

* [20261014084400](../20261014084400) Defining subagents with dicts or CompiledSubAgent -- CompiledSubAgent wraps a graph

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangGraph docs: Graph API\
  <https://docs.langchain.com/oss/python/langgraph/graph-api>

* Intro to LangGraph, Module 4: Sub-graphs\
  <https://academy.langchain.com/courses/intro-to-langgraph>

Tags:

    #intro-to-langgraph #langgraph-subgraphs #exam-build
