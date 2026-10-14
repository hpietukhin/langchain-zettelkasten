# Multimodal input uses content blocks

Instead of a plain string, message content can be a list of typed blocks (text, image, file, audio). The same structure works across providers, so an agent can be given an image of a fridge and asked for a recipe (the course's Personal Chef project).

```python
from langchain.messages import HumanMessage

msg = HumanMessage(content=[
    {"type": "text", "text": "What can I cook with this?"},
    {"type": "image", "url": "https://example.com/fridge.jpg"},
])
agent.invoke({"messages": [msg]})
```

Related:

* [20261014080600](../20261014080600) Messages are the unit of context -- a message's content may be a list of blocks

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Messages\
  <https://docs.langchain.com/oss/python/langchain/messages>

* Intro to LangChain, Lesson 4: Multimodal Messages\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

Tags:

    #langchain-foundations #multimodal-messages #exam-build
