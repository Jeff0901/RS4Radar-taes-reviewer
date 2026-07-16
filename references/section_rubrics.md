# Section Rubrics and Concern Severity

## Scoring Scale

Use the same 0-3 scale for each applicable section:

- `0 - Missing or invalid`: absent, internally inconsistent, or unable to support the manuscript's purpose.
- `1 - Weak`: recognizable intent, but major information or evidence is missing; substantial revision required.
- `2 - Adequate`: technically usable and mostly complete, with bounded revisions needed.
- `3 - Strong`: clear, traceable, technically complete for the claim, and close to internal submission quality.
- `N/A`: genuinely not applicable or integrated elsewhere. Explain where the function is fulfilled.

Do not compute Overall Readiness from an unweighted average. Ethics, confidentiality, TAES fit, model validity, contribution clarity, and core evidence are gates.

## Title

### 0

- Generic or misleading; system/task cannot be identified.
- Claims `optimal`, `robust`, `real-time`, or similar properties contradicted by the manuscript.

### 1

- Names only a generic algorithm or broad radar topic.
- Omits the task, system/scenario, or defining mechanism needed to distinguish the work.

### 2

- Identifies the task and method family; scope is accurate.
- Could be more specific about the system, failure condition, or method mechanism.

### 3

- Concisely identifies the object/system, task, and distinctive mechanism or condition.
- Uses calibrated, verifiable wording without promotional adjectives.

## Abstract

### 0

- Missing or inconsistent with the paper.
- Contains claims unsupported by the methods or experiments.

### 1

- Mostly background and `we propose` language.
- Problem, mechanism, assumptions, quantitative result, or contribution is unclear.

### 2

- States context, specific problem, method idea, and main evidence.
- Some claims lack conditions, quantitative anchors, or comparative meaning.

### 3

- Forms a compact chain: system context -> failure/bottleneck -> mechanism -> evidence under stated conditions -> bounded contribution.
- Results are concrete and do not exceed the tested scope.

## Introduction

### Required Problem Chain

1. Why does the problem matter in the radar/electronic system?
2. What do existing method families solve?
3. Under what condition do they fail?
4. What physical, statistical, or mathematical mechanism causes the failure?
5. What is the paper's core idea?
6. Does each contribution map to later theory or experiment?

### 0

- No coherent research problem or literature context.
- Contribution/originality cannot be identified.

### 1

- Literature is listed by acronym or chronology without a failure-driven synthesis.
- Gap is generic (`low accuracy`, `high complexity`) and not tied to a mechanism.
- Contributions are vague or unverifiable.

### 2

- System relevance, method families, failure condition, gap, and contributions are mostly clear.
- Some links between gap, mechanism, or evidence remain implicit.

### 3

- The problem chain is explicit and technically grounded.
- Closest work is compared by model, information, prior, mechanism, and cost.
- Contributions are specific, verifiable, comparative, and aligned to later sections.

## Problem Formulation

### Required Bridge

`physical scene/acquisition -> echo or measurement -> sampling/processing -> discrete model -> assumptions -> estimation/optimization objective`

### 0

- Core model is absent, dimensionally invalid, or incompatible with the stated system.
- Later variables have no source.

### 1

- A generic matrix model appears after radar prose with missing derivation, dimensions, or physical meanings.
- Noise/clutter/motion/grid assumptions are hidden.
- The objective does not follow naturally from the measurement model.

### 2

- Echo/measurement model, discretization, dimensions, assumptions, and objective are largely traceable.
- Minor notation, approximation, or boundary details remain incomplete.

### 3

- Continuous physics and discrete algorithmic model are connected without jumps.
- Every important variable and approximation is defined, dimensionally valid, and physically interpreted.
- Identifiability and applicability boundaries are visible.

## Proposed Method

### 0

- Method cannot be reproduced or does not solve the formulated problem.
- Derivation contains a core invalid step.

### 1

- Algorithm steps are present but motivation, distinction, initialization, stopping, or assumptions are unclear.
- New modules look like engineering tuning without a verifiable mechanism.
- Complexity/convergence claims are unsupported.

### 2

- Core mechanism, derivation, algorithm, and baseline difference are clear.
- Some implementation, parameter, convergence, or complexity details need revision.

### 3

- Each module resolves a diagnosed failure, and equations/algorithm are consistent.
- Novelty is comparative; conditions, parameter selection, convergence limits, complexity, memory, and online/offline work are appropriately addressed.

## Experiments

### 0

- No evidence for the central claim, fabricated/inconsistent evidence, or irreparably unfair comparison.

### 1

- Only selected visual maps or single trials are shown while claims concern detection, estimation, robustness, or complexity.
- Baseline settings, metrics, randomization, or parameters are missing.
- Contribution modules are not testable from the presented evidence.

### 2

- Main claims have relevant quantitative evidence and fair baselines.
- Some statistical, robustness, sensitivity, ablation, runtime, or reproducibility evidence is missing, but the central conclusion is testable.

### 3

- Each central claim has a falsifiable and appropriately controlled test.
- Baselines are fair, metrics match the task, stochastic claims have statistical evidence, and implementation claims have cost evidence.
- Measured data is included when required by the claimed level of deployment; limitations remain visible.

Do not award or deduct points for experiment count. Judge whether the evidence answers the manuscript's hypotheses and decisions.

## Conclusion

### 0

- Contradicts the paper or makes unsupported claims.

### 1

- Repeats generic claims, introduces new results, or extrapolates beyond tested conditions.

### 2

- Accurately summarizes problem, mechanism, and main findings; limitations could be clearer.

### 3

- Closes the problem-contribution-evidence chain, states conditions and limitations, and avoids novelty/performance inflation.

## Optional Theory/Complexity Function

Score this function within Proposed Method unless it is a separate section:

- `0`: central proof/complexity claim invalid or absent.
- `1`: claim exists without conditions or dominant-term analysis.
- `2`: correct and adequate for the claim, with minor omissions.
- `3`: assumptions, derivation, complexity variables, and empirical consistency are clear.

## Concern Severity

### Major Concern

A problem that can change scope fit, novelty, validity, reproducibility, or the central conclusion. Examples:

- Weak TAES systems/application fit.
- Unclear or incremental contribution relative to closest work.
- Physical-to-mathematical model jump.
- Invalid assumption, missing identifiability condition, or dimension error affecting the method.
- Core claim lacks quantitative evidence.
- Only RD/SAR/angle images support a detection, estimation, robustness, or efficiency claim.
- Materially unfair baseline or undisclosed oracle prior.
- Deployment/real-time claim without system evidence.
- Ethics, originality, AI-disclosure, or confidentiality risk.

### Minor Concern

A local issue that does not overturn the central conclusion:

- A symbol, unit, parameter, or baseline detail missing but readily recoverable.
- Local explanation or figure/table readability issue.
- A limited citation-context gap not affecting novelty diagnosis.
- Overlong paragraph, duplicated statement, or inconsistent acronym.

### Language-Level Issue

- Grammar, article use, tense, awkward collocation, punctuation, or local word choice.
- Treat as language only when technical meaning is already unambiguous.
- If wording obscures an assumption, contribution, or result, classify by its technical impact instead.

## Priority Labels

- `P0`: a nontechnical hard gate involving authorization, confidentiality, ethics, originality, or an explicit official rule. Stop processing when the gate requires refusal; otherwise resolve it before submission.
- `P1`: blocks TAES fit, a central technical claim, model validity, reproducibility, or readiness. Invalid assumptions and invalid core models are `P1`, not `P0`.
- `P2`: materially improves completeness, reproducibility, or interpretation.
- `P3`: local clarity, presentation, or language polish.

## Concern Block Format

Every Major and substantive Minor Concern must use:

```text
Concern: [specific issue]
Evidence: [section/equation/figure/quote fragment or stated absence]
Impact: [why this affects fit, validity, evidence, or clarity]
Required Action: [concrete revision or decision-relevant experiment]
Priority: P0 | P1 | P2 | P3
```

## Overall Readiness

Use exactly one label:

### Not ready

- P0 issue unresolved; or
- TAES fit is missing; or
- the core model/contribution/evidence chain is invalid or absent.

### Substantial revision

- TAES-relevant problem is present, but one or more P1 issues block internal submission.
- Typical cases: model jump, unclear novelty, inadequate evidence, or unfair baselines.

### Near-ready

- No P0 issue and no fatal validity problem.
- Core sections score at least 2, but a small number of bounded P1/P2 revisions remain.

### Ready for internal submission

- No unresolved Major Concern.
- TAES fit, contribution, model, method, evidence, ethics, and reproducibility are adequate for a lab's submission workflow.
- This label is not an acceptance prediction.

## Article-Type Calibration

- For a Regular Paper, expect a well-rounded problem-model-method-evidence treatment.
- For Correspondence, accept a narrower contribution and integrated sections, but still require sufficient model, validity, and evidence for the one or two central points.
- Never infer that Correspondence is lower quality or that a Regular Paper needs a particular page count.
