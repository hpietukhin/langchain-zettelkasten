# LLM-as-judge grades subjective qualities with a model

For correctness against a reference, helpfulness, tone or groundedness, an LLM reads the inputs/outputs and returns a score with reasoning. `openevals.llm.create_llm_as_judge` builds one from a prompt (e.g. `CORRECTNESS_PROMPT`). Judges cost money, add noise and can be biased, so use clear rubrics, binary/low-cardinality scores, and align them with human labels.

```python
from openevals.llm import create_llm_as_judge
from openevals.prompts import CORRECTNESS_PROMPT

def correctness_evaluator(inputs: dict, outputs: dict, reference_outputs: dict):
    judge = create_llm_as_judge(prompt=CORRECTNESS_PROMPT, model="openai:o3-mini",
                                feedback_key="correctness")
    return judge(inputs=inputs, outputs=outputs, reference_outputs=reference_outputs)
```

Related:

* [20261014093200](../20261014093200) Code-based evaluators: deterministic, cheap, exact -- use code when possible

* [20261014094000](../20261014094000) Align LLM judges to human labels before trusting them -- judges must be calibrated

* [20261014093800](../20261014093800) Online evaluators score production runs with filters and sampling -- judges also run in production

* [20261014101700](../20261014101700) Structure: Exam section 2 · Test (evaluators and experiments) -- exam section hub

Refs:

* Building Reliable Agents, Module 2 Lesson 5: LLM-as-Judge\
  <https://academy.langchain.com/courses/building-reliable-agents>

* LangSmith docs: Evaluation quickstart\
  <https://docs.langchain.com/langsmith/evaluation-quickstart>

Tags:

    #building-reliable-agents #langsmith-evaluation #llm-as-judge #exam-test
