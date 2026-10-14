# Context engineering: model, tool and life-cycle context

Agents fail mostly because the model lacked the right context. LangChain splits what you control into: *model context* (instructions, messages, tools, response format for a call; transient), *tool context* (what tools read from and write to state, store and runtime context; persistent) and *life-cycle context* (what happens between steps: summarization, guardrails, logging; persistent).

```python
# model context  -> @dynamic_prompt / wrap_model_call + request.override(...)
# tool context   -> ToolRuntime: runtime.state / runtime.context / runtime.store
# life-cycle ctx -> SummarizationMiddleware, PIIMiddleware, before_model hooks
agent = create_agent(model="gpt-5.5", tools=[save_pref],
                     middleware=[state_aware_prompt, SummarizationMiddleware(model="gpt-5.4-mini", trigger=("tokens", 8000))])
```

Related:

* [20261014081900](../20261014081900) @dynamic_prompt computes the system prompt per model call -- model context

* [20261014080500](../20261014080500) ToolRuntime gives tools access to state, context and store -- tool context

* [20261014082100](../20261014082100) SummarizationMiddleware compresses old history -- life-cycle context

* [20261014084000](../20261014084000) Five kinds of context in a deep agent -- the deep agents view of context

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Context engineering\
  <https://docs.langchain.com/oss/python/langchain/context-engineering>

Tags:

    #langchain-foundations #context-engineering #exam-build
