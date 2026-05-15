# Agent Research Findings — Strategy Templates
> Extracted from 4 parallel agents on 2026-05-15
> Sources: princeton-nlp, noahshinn, spcl/ETH Zürich, stanfordnlp/dspy, NirDiamant

---

## Agent 1 — Tree of Thoughts (`princeton-nlp/tree-of-thought-llm`)
**Paper:** arXiv:2305.10601 — Yao et al., Princeton/Google 2023
**Key result:** +74% on Game of 24 vs standard prompting

### Generate Prompt (Sample mode)
```
{problem}
Generate {n_generate} possible thoughts/next steps.
Be creative and diverse.
```

### Generate Prompt (Propose mode)
```
{problem}
Given the current state, propose {n_propose} next steps.
Each step should be distinct and build toward the solution.
```

### Evaluate Prompt (Vote mode)
```
Given the problem and the following thoughts, vote for the most promising one.
Thoughts:
{thoughts_numbered}

Vote for the best thought (index 1-{n}):
```

### Evaluate Prompt (Score mode)
```
Evaluate the following thought for solving the problem.
Problem: {problem}
Thought: {thought}
Score from 1-10 where 10 = definitely correct, 1 = definitely wrong.
Score:
```

### Traversal modes
- **BFS** (breadth-first): explore all branches at each level, prune low scorers
- **DFS** (depth-first): follow one branch deep, backtrack on failure
- **Configurable:** `n_select_sample`, `n_evaluate_sample`, `n_generate_sample`

---

## Agent 2 — Reflexion (`noahshinn/reflexion`)
**Paper:** arXiv:2303.11366 — Shinn et al., MIT/Northeastern 2023
**Key result:** +21% on HumanEval coding benchmark

### Self-Reflection Prompt (exact from `generate_reflections.py`)
```
You will be given the history of a past experience in which you were placed 
in an environment and given a task to complete. You were unsuccessful in 
completing the task. Do not summarize your environment, but rather think 
about the strategy and path you took to attempt to complete the task. 
Devise a concise, new plan of action that accounts for your mistake with 
reference to specific actions that you should have taken. For example, if 
you tried A and B but forgot C, then devise a plan to achieve C with 
environment-specific actions. You will need this later when you are solving 
the same task. Give your plan after "Plan".
```

### Memory Injection Format (injected before new attempt)
```
Plans from past attempts:
Trial #1: [reflection text]
Trial #2: [reflection text]
Trial #3: [reflection text]

Now attempt the task again with this context in mind.
```

### Memory constraints (from `update_memory()`)
- Maximum 3 reflections kept in buffer (`memory[-3:]`)
- Each reflection is a natural-language plan, NOT a summary of what happened
- Memory prepended to the reflection prompt on each retry

### Retry Loop Structure
```
1. Execute task → log interaction trace
2. Check success: if not env['is_success']:
3. Generate reflection: LLM(failure_log + memory_buffer)
4. Append to memory: env['memory'] += [reflection]
5. Next trial: inject memory into new reflection prompt
6. Repeat until success or max_attempts (default: 3)
```

### Real example output
> Agent tried to heat coffee mug. Failure trace: examined stoveburner for 3 steps.
> Reflection → "Plan: I should heat the mug directly on the stoveburner then transfer to coffeemachine. I was stuck examining instead of acting."

---

## Agent 3 — Graph of Thoughts (`spcl/graph-of-thoughts`, ETH Zürich)
**Paper:** arXiv:2308.09687 — Besta et al., ETH Zürich 2023
**Key result:** +62% on complex tasks vs linear prompting

### 4 Core Operations

#### Generate
```
Generate {num_thoughts} distinct thoughts/approaches for the following:
{input}

Each thought should be independent and explore a different angle.
Thought 1:
```

#### Aggregate (merge N thoughts into 1)
```
Merge the following solutions into one comprehensive, non-redundant solution:

Solution 1: {thought_1}
Solution 2: {thought_2}
[...]
Solution N: {thought_N}

Merged solution:
```

#### Score (evaluate quality)
```
Rate the following solution on a scale of 0-10.
Provide a brief justification.

Solution: {thought}

Score (0-10):
Justification:
```

#### Improve (refine existing thought)
```
Improve the following solution based on these criteria: {criteria}

Current solution: {thought}

Improved solution:
```

### DAG Execution Pattern
```
Input → [Generate x4] → [Score each] → [Aggregate top 2] → [Improve] → Output
              ↓                ↓
         parallel           prune <6
```

### Real application (merge sort from repo)
```
Merge these two sorted sub-arrays into one sorted array:
Sub-array 1: {left_half}
Sub-array 2: {right_half}
Merged sorted array:
```

---

## Agent 4 — DSPy / ReAct (`stanfordnlp/dspy`)
**Paper:** arXiv:2310.03714 — Khattab et al., Stanford 2023

### ChainOfThought (auto-generated from any signature)
Any signature `Question → Answer` becomes:
```
Given the fields `question`, produce the fields `answer`.

question: {question}

Reasoning: Let's think step by step in order to produce the answer.
           We need to...

answer:
```
**Key insight:** DSPy inserts the reasoning field automatically — no manual CoT prompt needed.

### ReAct Agent Loop (exact from dspy source)
```
You are an Agent. 
In each episode you will be given the fields `{input_fields}` and your goal 
is to always produce `{output_fields}`.

To do this, you will interleave next_thought, next_tool_name, and next_tool_args,
and receive observation after each tool call.

When you are ready, provide the final answer.

Thought: {reasoning}
Tool: {tool_name}
Args: {tool_args}
Observation: {tool_output}
[repeat until done]
Thought: done
Tool: finish
Answer: {final_answer}
```

### Signature-based prompt generation
```python
# DSPy signature = declarative I/O spec
class Classify(dspy.Signature):
    """Classify sentiment of a product review."""
    sentence: str = dspy.InputField()
    sentiment: Literal['positive', 'negative', 'neutral'] = dspy.OutputField()
    confidence: float = dspy.OutputField()
```
→ DSPy auto-generates the full prompt from this spec. No manual templating.

---

## NirDiamant Notebooks (⭐7.5k — `NirDiamant/Prompt_Engineering`)
**Source:** `/klipso_pm/Prompt_Engineering/all_prompt_engineering_techniques/`

### Chain-of-Thought (`cot-prompting.ipynb`)
```
# Basic
"Answer the following question step by step concisely: {question}"

# Advanced (4-step structure)
"""Solve step by step. For each step:
1. State what you're going to calculate
2. Write the formula (if applicable)
3. Perform the calculation
4. Explain the result

Question: {question}
Solution:"""
```

### Self-Consistency (`self-consistency.ipynb`)
```
# Path generation (run N times with different seeds)
"Solve using a unique approach. This is path {N}: {problem}"

# Aggregation
"Analyze all paths below and determine the most consistent answer:
{paths_list}
Most consistent answer:"

# Self-check
"Evaluate the consistency and reliability of this result:
Result: {result}
Reasoning: {reasoning}
Is this consistent? Rate 1-5:"
```

### Task Decomposition (`task-decomposition-prompts.ipynb`)
```
# Decompose
"Break down the task of {task_description} into 3 subtasks.
For each subtask, provide a brief description of what it should accomplish.
Task: {task}
Subtasks:
1."

# Per-subtask analysis
"Analyze {aspect} based on: {data}
Calculate {metric} and provide brief analysis."

# Integration
"Based on the following analyses, provide an overall assessment:
{analysis_1}
{analysis_2}
{analysis_3}
Summarize key points and give overall evaluation."
```

### Prompt Chaining (`prompt-chaining-sequencing.ipynb`)
```
# Sequential: output N → input N+1
Step 1: "Write a short {genre} story in 3-4 sentences."
Step 2: "Summarize the following story in one sentence:\n{story}"

# Dynamic follow-up generation
"Based on the question '{question}' and the answer '{answer}',
generate a relevant follow-up question."

# Error handling with validation
Generate → Extract → Validate → Retry(max=3)
```

---

## Coverage Summary

| Strategy | arXiv | Template Source | Status |
|---|---|---|---|
| Chain-of-Thought | 2201.11903 | NirDiamant notebook | ✅ |
| Self-Consistency | 2203.11171 | NirDiamant notebook | ✅ |
| Task Decomposition | — | NirDiamant notebook | ✅ |
| Prompt Chaining | — | NirDiamant notebook | ✅ |
| Tree of Thoughts | 2305.10601 | princeton-nlp repo | ✅ |
| Reflexion | 2303.11366 | noahshinn/reflexion | ✅ |
| Graph of Thoughts | 2308.09687 | ETH Zürich spcl | ✅ |
| ReAct | 2210.03629 | DSPy (Stanford) | ✅ |
| Meta-Prompting / DSPy | 2310.03714 | DSPy signatures | ✅ |
| Chain-of-Verification | 2309.11495 | arXiv paper direct | ⚡ from paper |
| Buffer of Thoughts | 2406.04271 | arXiv paper direct | ⚡ from paper |
| Plan-and-Solve | 2305.04091 | arXiv paper direct | ⚡ from paper |
| Step-Back Prompting | 2310.06117 | arXiv paper direct | ⚡ from paper |
| Skeleton-of-Thought | 2307.15337 | arXiv paper direct | ⚡ from paper |
| Least-to-Most | 2205.10625 | arXiv paper direct | ⚡ from paper |
| Few-Shot | 2005.14165 | GPT-3 paper | ⚡ from paper |
| Zero-Shot | — | baseline | ⚡ trivial |
| Generate-Knowledge | 2110.08387 | arXiv paper direct | ⚡ from paper |
| Multimodal-CoT | 2302.00923 | arXiv paper direct | ⚡ from paper |
| Graph-of-Thoughts (v2) | 2308.09687 | ETH Zürich spcl | ✅ |

**✅ = exact template extracted from code**
**⚡ = extractable directly from arXiv paper**
