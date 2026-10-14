# SKILL.md skills use progressive disclosure

A skill is a folder with a `SKILL.md` (frontmatter + instructions) and optional `scripts/`, `references/`, `assets/`. `SkillsMiddleware` loads in three levels: (1) at startup only name+description of every skill go into the prompt; (2) when relevant the agent reads the full `SKILL.md` with `read_file`; (3) supporting files are read only as instructions require. This keeps many skills cheap.

```python
agent = create_deep_agent(model="openai:gpt-5.5", skills=["./skills/"])
# ./skills/arxiv-search/SKILL.md, ./skills/arxiv-search/scripts/search.py
```

Related:

* [20261014085800](../20261014085800) AGENTS.md is always-loaded memory -- contrast: always loaded

* [20261014090000](../20261014090000) Skill frontmatter: name and a specific description -- how to write the frontmatter

* [20261014084300](../20261014084300) Context isolation: subagents quarantine heavy work -- both reduce context load

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Skills\
  <https://docs.langchain.com/oss/python/deepagents/skills>

* Deep Agents course, Module 3 Lesson 2: Skills\
  <https://academy.langchain.com/courses/foundation-introduction-to-deepagents>

Tags:

    #deep-agents-foundations #context-management #skills #exam-build
