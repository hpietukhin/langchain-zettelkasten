# Skill frontmatter: name and a specific description

The `description` is the only thing the agent sees during discovery, so it must say what the skill does and when to use it. Keep frontmatter concise and the body under about 5,000 tokens. Codify repeated multi-step workflows, domain knowledge, tested scripts and guidelines as skills.

```python
SKILL_MD = """---
name: arxiv-search
description: Search arXiv for research papers. Use when the user asks about academic papers or recent research.
---
# arxiv-search
1. Run scripts/search.py with the query.
2. Summarise the top 5 results with links.
"""
```

Related:

* [20261014085900](../20261014085900) SKILL.md skills use progressive disclosure -- how skills are loaded

* [20261014101600](../20261014101600) Structure: Exam section 1 · Build (create_agent, deepagents, context) -- exam section hub

Refs:

* Deep Agents docs: Skills\
  <https://docs.langchain.com/oss/python/deepagents/skills>

* Agent Skills specification\
  <https://agentskills.io/specification>

Tags:

    #deep-agents-foundations #skills #exam-build
