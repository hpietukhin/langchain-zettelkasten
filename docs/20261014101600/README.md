# Structure: Exam section 1 · Build (create_agent, deepagents, context)

Build = 25% of the exam. Courses: LangChain Foundations (Intro to LangChain) and Deep Agents Foundations. Focus areas: differences between create_agent and deepagents, middleware, context engineering for long-running agents, AGENTS.md and SKILL.md, sandboxing.

The Related list below is grouped by focus area / module (the text after -- names the group). Find all notes of this area with: pyzet grep '#exam-build'

Related:

* [20261014080100](../20261014080100) Agent = model + harness -- create_agent vs deepagents

* [20261014080200](../20261014080200) create_agent builds a production agent graph -- create_agent vs deepagents

* [20261014083500](../20261014083500) Deep Agents is a batteries-included agent harness -- create_agent vs deepagents

* [20261014083600](../20261014083600) create_agent vs create_deep_agent: when to use which -- create_agent vs deepagents

* [20261014083700](../20261014083700) Deep agents' built-in tools -- create_agent vs deepagents

* [20261014083800](../20261014083800) The Deep Agents middleware stack -- create_agent vs deepagents

* [20261014081500](../20261014081500) Middleware hooks into every step of the agent loop -- middleware

* [20261014081600](../20261014081600) Node-style hooks run before or after agent and model steps -- middleware

* [20261014081700](../20261014081700) Wrap-style hooks intercept model and tool calls -- middleware

* [20261014081800](../20261014081800) Class-based middleware bundles hooks, config and state -- middleware

* [20261014083100](../20261014083100) Catalogue of built-in middleware -- middleware

* [20261014082100](../20261014082100) SummarizationMiddleware compresses old history -- middleware

* [20261014082300](../20261014082300) HumanInTheLoopMiddleware pauses before sensitive tool calls -- middleware

* [20261014082500](../20261014082500) Call-limit middleware stops runaway loops -- middleware

* [20261014082800](../20261014082800) PIIMiddleware detects and handles sensitive data -- middleware

* [20261014081900](../20261014081900) @dynamic_prompt computes the system prompt per model call -- middleware

* [20261014082000](../20261014082000) Dynamic model and tool selection with request.override -- middleware

* [20261014083400](../20261014083400) Context engineering: model, tool and life-cycle context -- context engineering for long-running agents

* [20261014084000](../20261014084000) Five kinds of context in a deep agent -- context engineering for long-running agents

* [20261014084100](../20261014084100) Offloading moves large tool payloads to the filesystem -- context engineering for long-running agents

* [20261014084200](../20261014084200) Deep agents summarise history at about 85% of the window -- context engineering for long-running agents

* [20261014084300](../20261014084300) Context isolation: subagents quarantine heavy work -- context engineering for long-running agents

* [20261014082200](../20261014082200) ContextEditingMiddleware clears old tool outputs -- context engineering for long-running agents

* [20261014081000](../20261014081000) Runtime context is static per-invocation configuration -- context engineering for long-running agents

* [20261014080500](../20261014080500) ToolRuntime gives tools access to state, context and store -- context engineering for long-running agents

* [20261014085800](../20261014085800) AGENTS.md is always-loaded memory -- AGENTS.md and SKILL.md

* [20261014085900](../20261014085900) SKILL.md skills use progressive disclosure -- AGENTS.md and SKILL.md

* [20261014090000](../20261014090000) Skill frontmatter: name and a specific description -- AGENTS.md and SKILL.md

* [20261014090100](../20261014090100) Agent-scoped vs user-scoped memory via store namespaces -- AGENTS.md and SKILL.md

* [20261014085200](../20261014085200) Sandboxes isolate code execution from the host -- sandboxing

* [20261014085300](../20261014085300) Two patterns: agent inside the sandbox vs sandbox as a tool -- sandboxing

* [20261014085400](../20261014085400) Sandbox lifecycle: thread-scoped or assistant-scoped -- sandboxing

* [20261014085500](../20261014085500) LocalShellBackend runs commands on the host without isolation -- sandboxing

* [20261014085700](../20261014085700) FilesystemPermission rules gate built-in file tools -- sandboxing

* [20261014084700](../20261014084700) Backends decide where a deep agent's files live -- sandboxing

Refs:

* Introduction to LangChain\
  <https://academy.langchain.com/courses/foundation-introduction-to-langchain-python>

* Introduction to Deep Agents\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

* LangChain docs: Agents\
  <https://docs.langchain.com/oss/python/langchain/agents>

Tags:

    #exam-build #structure-note
