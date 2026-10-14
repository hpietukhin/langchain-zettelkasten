# Catalogue of built-in middleware

Prebuilt middleware in `langchain.agents.middleware` includes: Summarization, HumanInTheLoop, ModelCallLimit, ToolCallLimit, ModelFallback, ModelRetry, ToolRetry, PII, TodoList, LLMToolSelector, ContextEditing, ShellTool and FilesystemFileSearch. Deep Agents add FilesystemMiddleware, SubAgentMiddleware and SkillsMiddleware. Exam tip: know which problem each solves.

```python
from langchain.agents.middleware import (
    SummarizationMiddleware, HumanInTheLoopMiddleware, ModelCallLimitMiddleware,
    ToolCallLimitMiddleware, ModelFallbackMiddleware, ToolRetryMiddleware,
    PIIMiddleware, TodoListMiddleware, LLMToolSelectorMiddleware, ContextEditingMiddleware,
)
```

Related:

* [20261014082100](../20261014082100) SummarizationMiddleware compresses old history -- summarization

* [20261014082200](../20261014082200) ContextEditingMiddleware clears old tool outputs -- context editing

* [20261014082300](../20261014082300) HumanInTheLoopMiddleware pauses before sensitive tool calls -- human in the loop

* [20261014082500](../20261014082500) Call-limit middleware stops runaway loops -- call limits

* [20261014082600](../20261014082600) ModelFallbackMiddleware tries alternative models on failure -- fallback

* [20261014082700](../20261014082700) Retry middleware handles transient tool and model errors -- retries

* [20261014082800](../20261014082800) PIIMiddleware detects and handles sensitive data -- PII

* [20261014082900](../20261014082900) LLMToolSelectorMiddleware narrows large toolsets -- tool selection

* [20261014083000](../20261014083000) TodoListMiddleware gives the agent a planning tool -- to-do list

* [20261014083800](../20261014083800) The Deep Agents middleware stack -- deep-agent specific middleware

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* LangChain docs: Built-in middleware\
  <https://docs.langchain.com/oss/python/langchain/middleware/built-in>

Tags:

    #langchain-foundations #middleware #exam-build
