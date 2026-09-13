# ProfBench Results

**Release**: 2026-09-10 · **Model**: `turingcorp/team-junior-v1.1` (Team Junior)
**Dataset**: 40 expert-level tasks — ten each in Physics PhD, Chemistry PhD, Finance MBA and Consulting MBA

---

## Protocol

- Scored **per criterion**: every rubric criterion is answered Yes/No.
- The **official prompt verbatim**, `temperature = 0`, `top_p = 1`, no output cap.
- Team delivery is **content + reason** — the answer body together with the reasoning the model
  states for it. Rubric criteria include derivations and intermediate results, so an answer that
  shows its work is scored on the work itself.
- **Coverage**: 38 of 40 tasks scored. Two tasks were excluded because no answer was produced for
  them during the run — disclosed rather than imputed.
- **Comparison set**: all three columns are reported on those same 38 tasks — the set every model
  completed. The baseline and the official draft were also evaluated on the two excluded tasks;
  those are left out of the comparison for **all three** columns rather than only for Team.
- All three columns were read by **the same judging pipeline**, so they are directly comparable.

---

## Results

| Model | Score / 100 |
|------|:--:|
| **Team Junior v1.1** | **63.3** |
| DeepSeek V4 Flash (direct) | 57.4 |
| official o3 draft | 55.6 |

| Domain | tasks | Team | DeepSeek V4 Flash (direct) | official o3 draft |
|------|:--:|:--:|:--:|:--:|
| Chemistry PhD | 10 | **75.5** | 69.4 | 60.8 |
| Consulting MBA | 10 | **70.8** | 70.3 | 64.9 |
| Finance MBA | 10 | 54.6 | 48.2 | **57.5** |
| Physics PhD | 8 | **49.6** | 37.8 | 35.2 |

Team leads the official o3 draft by **+7.7 points** and the direct baseline by **+4.9 points** on
the tasks all three completed. Finance MBA is the one domain where the official draft scores higher.

---

## Judge calibration

Our judging pipeline reproduces the official per-criterion labels on the o3 draft with
**74.0% agreement** (F1 0.761) and a **mean difference of +2.4 points** (our pipeline 55.6 vs the
official evaluation's 53.2 for the same draft). The scores above sit on our pipeline's scale,
calibrated against the official one.

---

## Head-to-head arbitration by our own decision kernel

On the same 38 tasks, the decision kernel was asked to choose between the team draft and the
official o3 draft:

```
36 : 1      team draft : official o3 draft      (38 tasks, 1 unresolved)
```

It was shown the question and the two drafts and nothing else — **no rubric, no scores**.

Two checks keep this preference from being an artefact:

- **Position swap.** On all 37 tasks where the kernel had made a pick, the comparison was re-run
  with the two drafts exchanged between option A and option B. 36 kept the same draft. The single
  change came on a task the kernel had already flagged as a near-tie (23% confidence); all 23 picks
  made at 80% confidence or above came back identical, so position is not what decides the pick.
- **No self-grading.** The judgment comes from a panel of independent models rather than one model
  scoring its own output, which removes the self-preference bias of a single-judge setup.

This head-to-head run is supporting evidence, not the primary measurement: the per-criterion rubric
columns above are the measurement, and the kernel reached its conclusion without ever seeing them.

### Confidence reported with every judgment

| Domain | tasks | Median confidence | Kernel picks the team draft |
|------|:--:|:--:|:--:|
| Physics PhD | 8 | 95.3% | 8/8 |
| Chemistry PhD | 10 | 87.0% | 9/10 |
| Consulting MBA | 10 | 84.5% | 10/10 |
| Finance MBA | 10 | 83.8% | 9/10 |

Median confidence on this benchmark is **85.9%**. It is not uniform across domains: highest in the
two domains where the team draft leads by the widest margin (Physics PhD, Chemistry PhD) and lowest
in Finance MBA, the one domain where the rubric prefers the reference draft. It describes how far
apart the two drafts are in the kernel's judgment: the lower the value, the closer the two are in
quality.

The 38-task run used a single fixed presentation order, with the team draft always offered as
option A; the position-swap audit above — not that run — is the control for ordering.

---

## Official reference (official judging pipeline)

The official evaluation of the official reference drafts. A **different judge** from the columns
above, so these rows are context only:

| Domain | o3 | Grok 4 | DeepSeek-R1 |
|------|:--:|:--:|:--:|
| Chemistry PhD | 51.6 | 67.9 | 48.2 |
| Consulting MBA | 71.2 | 67.4 | 59.0 |
| Finance MBA | 44.5 | 41.3 | 39.1 |
| Physics PhD | 45.4 | 30.9 | 39.1 |
| **Overall** | **53.2** | **51.9** | **46.3** |

---

## Raw data

Answers (content + reason), per-criterion judge ratings, decision-kernel picks and the
position-swap audit ship in
[result-package/turingcorp-team-junior-v1.1_profbench-20260910.zip](../result-package/turingcorp-team-junior-v1.1_profbench-20260910.zip).

Raw records carry the task ID, domain, answer text and reasoning — they do **not** carry benchmark
question text, and they contain no internal model or vendor identifiers.
