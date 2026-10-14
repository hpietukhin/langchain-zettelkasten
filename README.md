# LangChain Certified Agent Engineer — Zettelkasten

A Zettelkasten of **136 atomic notes** and **12 structure (hub) notes** covering the theory of the free
[LangChain Academy](https://academy.langchain.com/collections) courses, written to prepare for the
**LangChain Certified Agent Engineer** exam (sections Build, Test, Deploy, Monitor; 25% each).

Every atom holds one idea, explained in its own words, with a short Python snippet (APIs checked against
[docs.langchain.com](https://docs.langchain.com) in October 2026), links to related atoms with a short context
phrase, and source references (Academy lesson and/or docs page).

## Start here

* [20261014101600](docs/20261014101600/README.md) Structure: Exam section 1 · Build (create_agent, deepagents, context)
* [20261014101700](docs/20261014101700/README.md) Structure: Exam section 2 · Test (evaluators and experiments)
* [20261014101800](docs/20261014101800/README.md) Structure: Exam section 3 · Deploy (LangSmith Deployment)
* [20261014101900](docs/20261014101900/README.md) Structure: Exam section 4 · Monitor (traces, cost, Insights, alerts)
* [20261014102000](docs/20261014102000/README.md) Structure: Course · Introduction to LangChain (LangChain Foundations, Python)
* [20261014102100](docs/20261014102100/README.md) Structure: Course · Introduction to Deep Agents (Deep Agents Foundations)
* [20261014102200](docs/20261014102200/README.md) Structure: Course · Building Reliable Agents with LangSmith
* [20261014102300](docs/20261014102300/README.md) Structure: Course · Introduction to LangSmith Deployment
* [20261014102400](docs/20261014102400/README.md) Structure: Course · Monitoring Production Agents
* [20261014102500](docs/20261014102500/README.md) Structure: Course · Introduction to LangGraph
* [20261014102600](docs/20261014102600/README.md) Structure: Course · Ambient Agents with LangGraph
* [20261014102700](docs/20261014102700/README.md) Structure: Index · LangChain Certified Agent Engineer Zettelkasten

## Structure

The repo follows the [pyzet](https://github.com/tpwo/pyzet) layout and ZettelMark-style format:

```
docs/
  <YYYYMMDDhhmmss>/README.md   # one zettel per folder, the folder name is its unique ID
```

Each zettel:

```markdown
# Title (one idea)

Explanation in own words.

```python
# short snippet
```

Related:

* [20261014080000](../20261014080000) Linked note title -- why it is linked

Refs:

* Source description\
  <https://docs.langchain.com/...>

Tags:

    #course-or-module-tag #topic-tag #exam-section
```

> Note: current pyzet (0.14) stores zettels in `docs/` (its `ZETDIR` constant), so that is used here instead of
> the older `zettels/` folder name, so that all pyzet commands work out of the box.

Tags are derived from course / module / topic names (e.g. `#langchain-foundations`, `#deep-agents-foundations`,
`#context-management`, `#langsmith-evaluation`, `#multi-tenant-auth`, `#monitoring-cost`) plus one exam-section
tag (`#exam-build`, `#exam-test`, `#exam-deploy`, `#exam-monitor`). Hubs carry `#structure-note`.

## Using pyzet

```bash
pip install pyzet
git clone https://github.com/hpietukhin/langchain-zettelkasten ~/langchain-zettelkasten
mkdir -p ~/.config/pyzet
printf 'repo: ~/langchain-zettelkasten\neditor: vim\n' > ~/.config/pyzet/pyzet.yaml

pyzet list                      # all notes, newest first
pyzet tags                      # tag counts
pyzet grep '#exam-deploy'       # every note for an exam section
pyzet grep -i 'double texting'  # full-text search
pyzet print --id 20261014080200 # show one note
pyzet add                       # write a new zettel (opens your editor, commits)
```

## Courses covered

* Introduction to LangChain (Python) — LangChain Foundations (Build)
* Introduction to Deep Agents — Deep Agents Foundations (Build)
* Building Reliable Agents with LangSmith (Test) + Introduction to Agent Observability & Evaluations
* Introduction to LangSmith Deployment (Deploy)
* Monitoring Production Agents (Monitor)
* Introduction to LangGraph (Python)
* Project: Ambient Agents with LangGraph

Snippets are illustrative study aids, not a test suite; a few pure-concept notes use pseudo-code, clearly marked.
APIs change quickly — when in doubt, the linked docs page wins.
