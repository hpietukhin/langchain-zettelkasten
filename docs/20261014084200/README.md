# Deep agents summarise history at about 85% of the window

`SummarizationMiddleware` is in the bare stack. When context nears the model's limit (85% of `max_input_tokens` from the model profile, keeping ~10% recent) and nothing more can be offloaded, an LLM writes a structured summary (intent, artifacts, next steps) that replaces history, and the full original transcript is written to the filesystem so details remain recoverable. Fallback without a profile: 170,000-token trigger, keep 6 messages.

```python
from langchain.chat_models import init_chat_model
model = init_chat_model("openai:gpt-5.5", profile={"max_input_tokens": 200_000})
agent = create_deep_agent(model=model)  # summarizes around 170k tokens
```

Related:

* [20261014082100](../20261014082100) SummarizationMiddleware compresses old history -- the same middleware used by create_agent

* [20261014084100](../20261014084100) Offloading moves large tool payloads to the filesystem -- offloading is tried first

* [20261014080300](../20261014080300) Models are chosen with provider:model strings or init_chat_model -- thresholds come from model profiles

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Context engineering\
  <https://docs.langchain.com/oss/python/deepagents/context-engineering>

Tags:

    #deep-agents-foundations #context-management #summarization-and-offload #exam-build
