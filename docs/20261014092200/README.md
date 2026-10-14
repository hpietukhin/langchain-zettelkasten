# Ambient agents learn preferences from human feedback

When a reviewer edits or rejects an action, an LLM updates a stored preference profile (triage rules, writing style, calendar habits). The next run reads those preferences into its prompt, so the agent needs fewer corrections over time.

```python
def update_prefs(store, user_id, feedback: str):
    ns = (user_id, "response_preferences")
    old = store.get(ns, "profile")
    new = llm.invoke(f"Update these preferences {old.value if old else {}} given: {feedback}")
    store.put(ns, "profile", {"text": new.content})
```

Related:

* [20261014092100](../20261014092100) Agent Inbox: notify, question and review interrupts -- the source of feedback

* [20261014091900](../20261014091900) The LangGraph store: namespaces, keys and search -- where learned preferences are saved

* [20261014085800](../20261014085800) AGENTS.md is always-loaded memory -- same idea with memory files in deep agents

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Ambient Agents with LangGraph course\
  <https://academy.langchain.com/courses/ambient-agents>

Tags:

    #ambient-agents #langgraph-memory #long-term-memory #exam-build
