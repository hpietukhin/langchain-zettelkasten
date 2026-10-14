# Ambient agents act on event streams, not chat prompts

An ambient agent listens to signals (emails, events, schedules) and acts in the background, pulling a human in only when needed. The course builds an email assistant: triage (ignore / notify / respond), a response agent with tools, HITL review, memory, and deployment; evaluated with LangSmith.

```python
# pseudo-structure of the course's email assistant graph
# START -> triage_router --(ignore)--> END
#                       --(notify)--> interrupt to human --> END
#                       --(respond)-> response_agent (tools + HITL) --> END
```

Related:

* [20261014092100](../20261014092100) Agent Inbox: notify, question and review interrupts -- how humans interact with them

* [20261014092200](../20261014092200) Ambient agents learn preferences from human feedback -- they learn from feedback

* [20261014100500](../20261014100500) Cron jobs run assistants on a schedule -- schedules can trigger them

* [20261014082300](../20261014082300) HumanInTheLoopMiddleware pauses before sensitive tool calls -- interrupts are the human touchpoint

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Ambient Agents with LangGraph course\
  <https://academy.langchain.com/courses/ambient-agents>

* agents-from-scratch notebooks\
  <https://github.com/langchain-ai/agents-from-scratch>

Tags:

    #ambient-agents #human-in-the-loop #exam-build
