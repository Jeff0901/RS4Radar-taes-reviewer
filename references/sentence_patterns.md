# Synthesized Sentence Patterns

## Use Boundary

These are newly synthesized frames based on the RS4Radar observation cards and the user's stated review goals. They are not quotations, not official TAES wording, and not mandatory prose. Replace every bracketed field with manuscript-specific technical content.

Use a frame only after the technical claim is valid. Do not improve rhetoric to hide a missing model, comparison, or experiment.

## Title Frames

- `[Mechanism] for [radar task] under [failure condition]`
- `[Radar/system task] via [distinctive physical or algorithmic mechanism]`
- `[Task] for [system/waveform] with [mismatch, motion, clutter, or hardware condition]`
- `[System or architecture]: [task] and [second verifiable system contribution]`

Avoid:

- `A Novel Method for Radar Signal Processing`
- `An Efficient and Robust Framework for Improved Performance`
- Unqualified `optimal`, `real-time`, `universal`, or `first` claims.

## Abstract Frames

### Context and consequence

- `[System/waveform] provides [operational benefit], but [physical/statistical mechanism] produces [observable performance loss].`
- `In [scenario], [existing processing stage] is vulnerable to [failure], which causes [masking/bias/defocusing/complexity consequence].`

### Gap

- `Existing [method family] assumes [condition]; when [violating condition] occurs, [specific model term or estimator property] becomes invalid.`
- `Although [prior approach] addresses [subproblem], its performance is limited by [unmodeled mechanism or engineering tradeoff].`

### Method mechanism

- `To address this mismatch, we formulate [measurement/estimation model] that explicitly incorporates [physical term].`
- `The proposed method first [module 1 and purpose], and then [module 2 and purpose].`
- `By exploiting [structure/measurement information], the method reduces [dominant operation or uncertainty] while preserving [required property].`

### Evidence

- `Under [tested conditions], the method improves [defined metric] relative to [closest baselines] while requiring [runtime/complexity condition].`
- `Monte Carlo simulations over [randomized factors] show [statistical result], and [measured-data type] confirms [only the module actually tested].`

### Boundary

- `The present validation assumes [important condition]; [unvalidated extension] remains outside the current claim.`

## Introduction Problem Chain

### System importance

- `[Task] is required in [system/mission] because [operational decision or consequence].`
- `For [radar mode], [physical quantity] determines [resolution/detection/estimation behavior].`

### Method-family synthesis

- `[Family A] addresses [benefit] by [mechanism], but depends on [assumption or cost].`
- `[Family B] relaxes [limitation], at the expense of [new cost or prior].`
- `Both families retain the assumption that [shared failure condition].`

### Gap with cause

- `When [condition] occurs, [physical or mathematical property] is violated, leading to [observable failure].`
- `The remaining limitation is therefore not [generic symptom], but [specific coupling, leakage, mismatch, or identifiability issue].`

### Core idea

- `The central idea is to [mechanism] so that [restored property] can be used for [task].`
- `Rather than [baseline operation], we use [new information/constraint] to [technical effect].`

### Contribution list

- `First, we derive [model/result] that connects [physical effect] to [estimation consequence].`
- `Second, we develop [method] that [mechanism], differing from [closest method] in [substantive distinction].`
- `Third, we establish [proof/complexity/observability result] under [conditions].`
- `Finally, we evaluate [claims] using [scenarios, metrics, baselines, and measured/simulated evidence].`

Contribution quality test:

- **Specific:** names the bottleneck and scenario.
- **Verifiable:** maps to a derivation, metric, or experiment.
- **Comparative:** states the substantive difference from closest work.

## Problem Formulation Frames

### Scene and acquisition

- `Consider a [radar/array] operating with [waveform, aperture, pulses, or sensors] in [geometry].`
- `The [target/source] is modeled as [point/extended/sparse/correlated/moving], with [parameter] satisfying [condition].`

### Echo or measurement

- `After [downconversion/sampling/matched filtering/DFT], the observation at [index] is written as ...`
- `The first term represents [desired physical component], whereas the remaining terms correspond to [interference, clutter, mismatch, and noise].`

### Discretization and dimensions

- `Discretizing [continuous parameter] with interval [value] yields [number] cells and the matrix [symbol] in [dimension].`
- `Each column of [dictionary/steering matrix] corresponds to [physical hypothesis], while [coefficient] represents [physical quantity].`

### Assumptions and limits

- `This model assumes [condition], which is valid when [physical inequality or operating regime].`
- `The effect of [excluded phenomenon] is neglected; therefore, the analysis does not cover [boundary].`

### Objective bridge

- `Because [noise/statistical/physical argument], estimating [quantity] is equivalent to solving [criterion].`
- `The failure of the nominal model can be expressed as [mismatch term], motivating the augmented problem ...`

## Proposed Method Frames

### Module motivation

- `The [first module] addresses [failure identified in Section X] by [mechanism].`
- `After [module 1] restores [property], [module 2] estimates [quantity] using [criterion].`

### Comparative distinction

- `Unlike [baseline], which uses [information/assumption], the proposed method incorporates [new term/information] and therefore [testable consequence].`
- `The improvement is not due to [shared step]; it follows from [distinctive mechanism].`

### Parameter and convergence

- `[Parameter] controls the tradeoff between [two effects]; Section X evaluates the operating range used here.`
- `The iteration terminates when [observable criterion] falls below [threshold] or after [maximum] steps.`
- `This argument establishes [bounded claim] under [conditions]; it does not prove [stronger claim].`

### Complexity

- `The dominant online cost is [operation] with order [expression] in [problem dimensions].`
- `[Matrix/dictionary] is independent of [runtime data] and can be computed offline, requiring [storage].`
- `Runtime is reported on [hardware/software] using the same [data and stopping rule] for all methods.`

## Experiment Frames

### Hypothesis-first setup

- `This experiment tests whether [mechanism] prevents [specified failure] under [condition].`
- `To isolate [module], we compare [full method] with [matched intermediate baseline] while keeping [controls] fixed.`

### Fairness

- `All methods use the same [data/noise/ROI/grid/iteration budget], and method-specific parameters follow [selection rule].`
- `[Baseline] assumes [oracle prior]; this advantage is retained and disclosed in the comparison.`

### Statistical result

- `Over [number] independent trials, [metric] is computed by randomizing [factors].`
- `The performance gap remains within [condition], but diminishes when [boundary], consistent with [model explanation].`

### Image interpretation

- `Figure X illustrates [qualitative phenomenon]; the corresponding quantitative change is reported by [metric] in Table/Figure Y.`
- `The map alone does not establish [detection/estimation] performance; [metric] provides that evidence.`

### Negative or boundary result

- `Beyond [condition], the assumption [name] no longer holds and performance degrades; this bounds the current claim.`

## Conclusion Frames

- `This work addressed [specific system problem] caused by [mechanism].`
- `The proposed [method] resolves this issue by [core mechanism], with [theory/experiment] supporting [bounded claims].`
- `The evidence covers [conditions] but not [unvalidated regime].`
- `Future work will examine [specific unresolved system factor], rather than restating generic performance improvement.`

## Reviewer Rewrite Policy

- Rewrite only representative key sentences or one short paragraph.
- Preserve equations, technical meaning, and author voice.
- State the diagnosis before the rewrite.
- Never fabricate numbers, baselines, novelty, policy, or evidence.
- If the source claim is unsupported, propose a claim structure with placeholders instead of polishing it into a stronger claim.
