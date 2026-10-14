# Structure: Course · Introduction to LangGraph

Free Academy course (public notebooks in langchain-ai/langchain-academy): graphs and routers, state and memory, human-in-the-loop, building assistants (parallelization, subgraphs, map-reduce), long-term memory, deployment.

The Related list below is grouped by focus area / module (the text after -- names the group). Find all notes of this area with: pyzet grep '#intro-to-langgraph'

Related:

* [20261014090600](../20261014090600) A LangGraph graph is state, nodes and edges -- Graph API

* [20261014091000](../20261014091000) Conditional edges route based on state -- Graph API

* [20261014091100](../20261014091100) Command combines a state update with routing -- Graph API

* [20261014090700](../20261014090700) Reducers define how state updates are merged -- Graph API

* [20261014090800](../20261014090800) add_messages and MessagesState manage chat history -- Graph API

* [20261014090900](../20261014090900) Trimming and removing messages controls context in graphs -- State and memory

* [20261014091400](../20261014091400) Checkpoints snapshot state at every super-step -- State and memory

* [20261014080800](../20261014080800) Short-term memory = checkpointer + thread_id -- State and memory

* [20261014091600](../20261014091600) interrupt() pauses a graph for human input -- Human-in-the-loop

* [20261014091700](../20261014091700) Command(resume=...) continues an interrupted thread -- Human-in-the-loop

* [20261014091500](../20261014091500) Time travel: replay or fork from a past checkpoint -- Human-in-the-loop

* [20261014091200](../20261014091200) Send fans out work to parallel node instances -- Building assistants

* [20261014091300](../20261014091300) Subgraphs compose graphs as nodes -- Building assistants

* [20261014091900](../20261014091900) The LangGraph store: namespaces, keys and search -- Long-term memory

* [20261014083300](../20261014083300) Long-term memory lives in a store, namespaced across threads -- Long-term memory

* [20261014091800](../20261014091800) Durability modes trade speed for crash safety -- Deployment

* [20261014101500](../20261014101500) langgraph dev runs a local Agent Server with Studio -- Deployment

Refs:

* Introduction to LangGraph\
  <https://academy.langchain.com/courses/intro-to-langgraph>

* langchain-academy notebooks\
  <https://github.com/langchain-ai/langchain-academy>

Tags:

    #intro-to-langgraph #structure-note
