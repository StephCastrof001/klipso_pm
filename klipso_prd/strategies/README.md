# Strategy Registry — klipso_prd

All 20 reasoning strategies with arXiv sources. Every strategy is a prompt engineering
pattern from peer-reviewed research — free to implement, free to use.

## Tier Classification

| Tier | Name | Principle | Best For |
|------|------|-----------|----------|
| **Tier 1** | Most Effective | Extended thinking + verification | Complex multi-hop reasoning |
| **Tier 2** | Highly Effective | Exploration + reflection | Ambiguous problems, open-ended PRDs |
| **Tier 3** | Contextual | Structured decomposition | Known problem types, LATAM context |
| **Tier 4** | Baseline | Direct prompting | Simple features, fast iterations |

---

## Strategy Map

### Tier 1 — Most Effective

| ID | Strategy | arXiv | Year | Key Result |
|----|----------|-------|------|------------|
| T1-01 | Chain-of-Thought | [2201.11903](https://arxiv.org/abs/2201.11903) | 2022 | +63% on arithmetic (Wei et al., Google) |
| T1-02 | Self-Consistency | [2203.11171](https://arxiv.org/abs/2203.11171) | 2022 | +17.9% on GSM8K (Wang et al., Google) |
| T1-03 | Chain-of-Verification (CoVe) | [2309.11495](https://arxiv.org/abs/2309.11495) | 2023 | +18% factuality, reduces hallucinations (Dhuliawala et al., Meta) |

### Tier 2 — Highly Effective

| ID | Strategy | arXiv | Year | Key Result |
|----|----------|-------|------|------------|
| T2-01 | Tree of Thoughts (ToT) | [2305.10601](https://arxiv.org/abs/2305.10601) | 2023 | +74% on Game of 24 (Yao et al., Princeton/Google) |
| T2-02 | Graph of Thoughts (GoT) | [2308.09687](https://arxiv.org/abs/2308.09687) | 2023 | +62% on complex tasks (Besta et al., ETH Zürich) |
| T2-03 | ReAct | [2210.03629](https://arxiv.org/abs/2210.03629) | 2022 | +34% on knowledge-intensive tasks (Yao et al., Princeton) |
| T2-04 | Reflexion | [2303.11366](https://arxiv.org/abs/2303.11366) | 2023 | +21% on HumanEval (Shinn et al., MIT/Northeastern) |
| T2-05 | Buffer of Thoughts (BoT) | [2406.04271](https://arxiv.org/abs/2406.04271) | 2024 | +11-51% accuracy, 12% cost of ToT (Yang et al., NeurIPS 2024 Spotlight) |

### Tier 3 — Contextual

| ID | Strategy | arXiv | Year | Key Result |
|----|----------|-------|------|------------|
| T3-01 | Plan-and-Solve | [2305.04091](https://arxiv.org/abs/2305.04091) | 2023 | Reduces calc errors vs CoT (Wang et al., S'pore Mgmt Univ) |
| T3-02 | Skeleton-of-Thought (SoT) | [2307.15337](https://arxiv.org/abs/2307.15337) | 2023 | 2.39x speedup via parallel decoding (Ning et al., Tsinghua/MSRA) |
| T3-03 | Step-Back Prompting | [2310.06117](https://arxiv.org/abs/2310.06117) | 2023 | +36% on MMLU Physics (Zheng et al., Google DeepMind) |
| T3-04 | Generate-Knowledge | [2110.08387](https://arxiv.org/abs/2110.08387) | 2022 | +3.4% on commonsense QA (Liu et al., U Washington) |
| T3-05 | Few-Shot | [GPT-3 Paper](https://arxiv.org/abs/2005.14165) | 2020 | Foundational in-context learning (Brown et al., OpenAI) |
| T3-06 | Least-to-Most | [2205.10625](https://arxiv.org/abs/2205.10625) | 2022 | Solves problems CoT can't via sub-problem decomposition (Zhou et al., Google) |
| T3-07 | Multimodal-CoT | [2302.00923](https://arxiv.org/abs/2302.00923) | 2023 | Integrates vision reasoning into CoT (Zhang et al., Salesforce) |

### Tier 4 — Baseline

| ID | Strategy | Description | Use Case |
|----|----------|-------------|----------|
| T4-01 | Zero-Shot | Direct prompt, no examples | Simple, well-defined features |
| T4-02 | Meta-Prompting | Prompt generates the prompt | Unknown optimal structure |

---

## Selection Algorithm

```
Given: claim_type, complexity_score, latam_context, has_firecrawl

if complexity_score >= 0.75:
    primary = T2-05 (Buffer of Thoughts)  # most cost-efficient at high complexity
    fallback = T2-01 (Tree of Thoughts)

elif hallucination_risk:
    primary = T1-03 (Chain-of-Verification)
    secondary = T1-02 (Self-Consistency)

elif latam_context:
    primary = T3-01 (Plan-and-Solve)  # structured, good for regulatory context
    enrich_with = Firecrawl(competitors=["Yape","Culqi","MercadoPago","BBVA Perú"])

elif has_codebase:
    primary = T2-03 (ReAct)  # reasoning + action on code
    fallback = T2-04 (Reflexion)

else:
    primary = T1-01 (Chain-of-Thought)  # baseline always works
```

---

## Papers You Should Read (priority order)

1. **Buffer of Thoughts** — NeurIPS 2024 Spotlight — arxiv.org/abs/2406.04271
   *Why*: Best cost/accuracy ratio. Stores thought-templates in a meta-buffer.

2. **Chain-of-Verification** — arxiv.org/abs/2309.11495
   *Why*: Directly addresses hallucination — the #1 PRD generation failure mode.

3. **Tree of Thoughts** — arxiv.org/abs/2305.10601
   *Why*: Best exploration strategy for open-ended PRD problems.

4. **Self-Consistency** — arxiv.org/abs/2203.11171
   *Why*: Simple, proven +17.9% with just majority voting across samples.

5. **Chain-of-X Survey** — arxiv.org/abs/2401.14295
   *Why*: 2024 survey covering all "Chain-of-X" paradigms in one paper.
