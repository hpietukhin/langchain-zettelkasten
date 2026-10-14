# Harness profiles tune the harness per provider or model

A harness profile (beta) is a declarative bundle of system-prompt, tool, middleware and subagent tweaks registered for a provider or a specific model, e.g. `base_system_prompt`, `system_prompt_suffix`, `excluded_tools`. Same agent code, model-specific tuning.

```python
# pseudo-example of the idea (beta API):
# profile = HarnessProfile(system_prompt_suffix="Prefer parallel tool calls.",
#                          excluded_tools=["glob"])
# registered for "openai:gpt-5.5" -> applied whenever that model is used
```

Related:

* [20261014083800](../20261014083800) The Deep Agents middleware stack -- profiles add/remove stack pieces

* [20261014083900](../20261014083900) A deep agent's system_prompt is prepended to a built-in prompt -- base prompt override

* [20261014084500](../20261014084500) The general-purpose subagent is added automatically -- configure the default subagent

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Profiles\
  <https://docs.langchain.com/oss/python/deepagents/profiles>

* Deep Agents docs: Comparison\
  <https://docs.langchain.com/oss/python/deepagents/comparison>

Tags:

    #deep-agents-foundations #agent-harness #exam-build
