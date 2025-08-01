# Benchmark for Half-Truth Detection

This repository contains the benchmark used in our work on **half-truth detection** in fact verification. We build on a concurrent submission **currently under double-blind review**, which introduces this new task. Due to anonymity requirements, we are unable to disclose author identity at this time.

We believe that early access to the benchmark will benefit the community and support reproducibility.

## Task Description

While traditional fact verification systems determine whether a claim is factually correct, they often fail to detect **omission-based manipulation** — cases where a claim is technically accurate but misleading due to the omission of critical context.

To address this, we propose the task of **half-truth detection**, where the goal is to identify such omissions and assess their impact on the claim's implied meaning.

The dataset consists of political claims annotated with:
- **Claim**
- **Presented Evidence (PE)**
- **Hidden Evidence (HE)**
- **Verdict**: {True, Half-True, False}
- **Inferred Intent**

## Dataset Statistics

- **Total claims**: 14,994
- **Split**:
  - Train: 11,994
  - Dev: 1,000
  - Test: 2,000

- **Label Distribution**:

| Split | True | Half-True | False | Total |
|-------|------|-----------|-------|-------|
| Train | 1,352 | 4,564     | 6,078 | 11,994 |
| Dev   | 64    | 195       | 741   | 1,000  |
| Test  | 93    | 406       | 1,501 | 2,000  |

- **Annotation Types**:
  - Sentence-level evidence alignment (PE / HE)
  - Claim intent statements (inferred by LLM + human validation)
  - Critical Hidden Evidence (CHE) annotations

## Label Definitions

| Final Label | Source PolitiFact Ratings |
|-------------|---------------------------|
| True        | True                      |
| Half-True   | Mostly True, Half True    |
| False       | Mostly False, False, Pants on Fire |

## Example

**Claim**: "Unemployment is at a 50-year low, showing our economic policies are working."

**Presented Evidence (PE)**:
- Unemployment rate is 3.5%, lowest in 50 years (official labor data).

**Hidden Evidence (HE)**:
- Most new jobs are part-time/gig-based.
- Labor force participation remains low.
- Growth concentrated in hospitality/retail sectors.

**TRACER Verdict**: Half-True (due to omission of job quality context)

## Citation Note

This repository is associated with a paper under review. Please refer to the anonymous link for citation purposes during the review process:

https://anonymous.4open.science/ (fill in once generated)

We will release the official version and code upon acceptance.

## Repository Structure

- `data/` — contains JSON files for train/dev/test splits
- `README.md` — this file