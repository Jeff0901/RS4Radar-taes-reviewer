# RD Recovery Review Guide

## Contents

1. Evidence and scope boundary
2. Section calibration
3. Experiment and metric audit
4. Claim-strength and language calibration
5. Severity calibration
6. Representative rewrite frames
7. Prohibited inferences

## 1. Evidence and Scope Boundary

Use this guide only when the manuscript's central task is range-Doppler image recovery, sidelobe suppression, matched-filter-output reconstruction, weak-target recovery, or a closely related IAA/WLS/RFPA processing problem.

This guide is a sanitized secondary synthesis of a narrow RD/IAA-oriented paper set that substantially overlaps the frozen RS4Radar corpus. It refines review questions but:

- does not add independent support counts;
- does not define an E1 or TAES-wide writing rule;
- does not prescribe one algorithm family, section order, paragraph count, sentence count, or word count;
- must not be projected onto unrelated DOA, MIMO, STAP, SAR, navigation, tracking, or spacecraft-RF manuscripts.

Apply the base rubric in `section_rubrics.md`; use this guide only to calibrate RD-specific evidence and wording.

## 2. Section Calibration

### Abstract

Reconstruct these functions, allowing the author to combine or reorder them:

1. Name the radar task and operating setting.
2. State the physical/processing failure and observable consequence.
3. Identify the method and only the mechanisms needed to explain its distinction.
4. State a theory or complexity property only if its conditions are available.
5. Report representative, claim-matched evidence.
6. Bound the result to the evaluated regime.

Flag the Abstract when it:

- spends more information on generic radar importance than the actual failure;
- lists modules or acronyms without a causal role;
- says only `excellent`, `effective`, or `better` without metric, comparator, or condition;
- reports a reconstruction image as detection evidence;
- implies measured, deployed, robust, or real-time performance without that evidence;
- reproduces the Introduction literature narrative or future-work list.

Do not impose a numeric length, sentence count, or acronym budget. Review information cost instead: every defined acronym and named module must earn its place.

### Introduction

Check for this problem chain:

1. Radar system/task and the role of MF/RD processing.
2. Concrete failure, such as strong-target leakage, masking, coupling, migration, or grid mismatch.
3. Method families synthesized by capability, assumption, failure condition, and cost.
4. A shared measurement/inverse-problem structure that justifies importing a general algorithm family into RD recovery.
5. The precise condition under which closest methods remain insufficient.
6. A core idea whose mechanism answers that condition.
7. Specific, verifiable, comparative contributions mapped to later evidence.

Treat a cross-domain algorithm transfer as ungrounded when the Introduction relies only on a shared equation label or acronym. The manuscript should identify what the unknown object, observation, dictionary/operator, prior, and operational metric mean in the radar chain.

### Problem Formulation

Audit the full variable chain as applicable:

```text
waveform/pulse train
-> propagation and received echo
-> demodulation and sampling
-> range/Doppler grid and atoms
-> MF/RD processing
-> desired/interference/noise decomposition
-> equivalent vector or matrix model
-> estimation/detection objective
```

Require:

- distinct names for raw samples, processed/MF outputs, and algorithm inputs;
- fast-time, slow-time, pulse/frame, and RD-cell indices;
- dimensions, units, normalization, and complex-conjugation conventions;
- a physical interpretation for coupling, dictionary, covariance, residual, and regularizer terms;
- assumptions adjacent to the equations they enable;
- a physical inequality or stated regime for neglected migration, off-grid effects, clutter, or other mismatch;
- a closing sentence that identifies the exact inverse problem and the failure term addressed next.

Do not require this chain to occupy a standalone section. Do flag a phrase such as `after standard processing` when it hides the operations that determine the model.

### Proposed Method

Check the organization by function:

1. Point to the diagnosed model term or failure condition.
2. Give an overview of input, state/variable flow, modules, and output.
3. Define the ideal estimator or update before implementation shortcuts.
4. Explain why each module changes the diagnosed failure.
5. State initialization, hyperparameters, stopping/termination, and failure handling.
6. Provide an algorithm listing or equivalent executable sequence when the equations alone do not define control flow.
7. Separate algorithm identity from fast implementation and software safeguards.

For every module, ask:

- What quantity enters and leaves?
- Which earlier failure does it address?
- What information or prior does it use?
- Is its claimed effect derived, directly measured, or inferred?
- Which closest method differs in mechanism rather than name?

### Implementation and Complexity

For each claimed acceleration, require this chain:

```text
direct expression
-> repeated bottleneck
-> exploitable structure
-> recurrence/reuse/approximation
-> exact or approximate status
-> cost before and after
-> effect on the algorithm or error
```

Check that the manuscript distinguishes:

- preprocessing, shared front end, method-specific precomputation, online iteration, and end-to-end work;
- arithmetic complexity, memory, iterations, wall-clock runtime, latency, and throughput;
- per-cell, per-iteration, per-scene, and per-frame cost;
- exact algebraic reuse from a controlled approximation;
- fixed-budget timing from method-specific stopping.

An asymptotic reduction does not establish lower wall-clock time. A measured runtime does not establish real-time capability without a deadline, dimensions, platform, implementation, and timing boundary.

### Experiments

Use this flexible evidence progression:

1. Common radar, scene, grid, noise, baseline, stopping, normalization, and hardware setup.
2. A representative or mechanism-isolating scene.
3. Quantitative support for what the map appears to show.
4. A decision-relevant difficulty or parameter axis.
5. Statistical stability when the claim is stochastic.
6. Convergence, operations, memory, or runtime when efficiency is claimed.
7. A boundary/mismatch case only when it tests a retained claim.

For each result paragraph, separate:

- **Observation:** what the figure/table directly shows.
- **Comparison:** metric, baseline, condition, and direction.
- **Interpretation:** mechanism consistent with the observation.
- **Attribution:** causal statement, allowed only when the comparison isolates the mechanism.
- **Boundary:** the tested regime and any degradation or unresolved alternative.

Do not request every item above. Request the minimum evidence that can change novelty, validity, claim scope, or an author decision.

### Conclusion

Check that the Conclusion answers:

1. What exact RD problem was addressed?
2. What mechanism distinguishes the method?
3. What evidence supports which claim?
4. What cost or tradeoff matters?
5. What model or evidence boundary remains?

The Conclusion should move from novelty pitch to mechanism-evidence-boundary synthesis. It should not copy the Abstract, repeat the numbered contribution list, introduce a new claim, list figures, or predict publication outcome.

## 3. Experiment and Metric Audit

### RD Visual Evidence

A 2-D RD map is useful for showing structure, masking, sidelobes, or target separation. It is not sufficient by itself for detection, estimation, robustness, or efficiency. Check:

- axes, units, dB definition, reference, color limits, and common normalization;
- truth/reference panel when available;
- a slice, local view, or exact metric for weak/strong or closely spaced targets;
- whether visual clipping or normalization hides amplitude error or false peaks.

### Metric Semantics

Keep these distinctions explicit:

| Distinction | Review question |
|---|---|
| Reconstruction vs detection | Is there a detector, threshold, target-present/absent model, and Pd/Pfa before using `detection`? |
| Amplitude vs power | Is dB conversion and dynamic range consistent with the underlying quantity? |
| Complex error vs amplitude error | Does the metric include phase error or only magnitude error? |
| MSE vs NMSE | Is normalization by a defined reference energy present? |
| Full-map vs target-cell vs background error | Which cells are averaged, excluded, or guarded? |
| Mean in linear domain vs mean in dB | Which operation is performed first and why? |
| Stopping vs convergence | Is a termination event being misreported as a mathematical convergence result? |
| Runtime vs speedup | Are preprocessing, stopping, implementation, and platform comparable? |
| Numerical floor vs zero | Is clipping/machine precision being interpreted as physical cancellation? |

If a metric uses ground truth, true target count, true noise power, or a target guard region, require it to be labeled as an offline evaluation metric or oracle-assisted quantity rather than a deployable detector.

### Baseline Fairness

Require a comparison record for:

- observation and random realization;
- RD grid, ROI, preprocessing, and normalization;
- target-count/noise/clutter/oracle information;
- initialization, tuning rule, iteration budget, and stopping;
- code path, hardware, parallelization, and timed region;
- failures, fallback paths, and excluded trials.

When methods require different stopping rules, recommend a fixed-budget view, a practical-stopping view, or a transparent component-level timing report rather than a single unqualified speedup.

## 4. Claim-Strength and Language Calibration

### Evidence Ladder

| Evidence | Suitable language | Avoided upgrade |
|---|---|---|
| Definition/design | `defines`, `constructs`, `uses`, `imposes` | performance guarantee |
| Conditional derivation | `derives`, `satisfies`, `holds under` | global proof/optimality |
| Limited scene/sweep | `illustrates`, `indicates`, `is consistent with` | robustness/general validity |
| Repeated quantitative evidence | `shows`, `yields lower [metric]`, `provides empirical support` | universal superiority |
| Measured/system evidence | `validated on [specific data/system]` | deployment beyond tested chain |
| Formal theorem | `proves/guarantees [exact property] under [conditions]` | guarantees outside theorem scope |

Prefer a metric-specific fact over `novel`, `excellent`, `effective`, `significant`, `superior`, `robust`, or `fast`. If `significant` is statistical, require the test, effect estimate, uncertainty, and multiplicity policy as applicable.

### Information Flow

- Use a concrete technical subject: waveform, coupling term, estimator, update, figure, metric, or experiment.
- Let transitions encode cause, contrast, or evidence; avoid connector sequences that merely enumerate sentences.
- Introduce why an equation is needed before displaying it, then interpret its terms and boundary afterward.
- Keep one dominant reasoning move per sentence; split sentences that combine condition, mechanism, effect, and complexity.
- Share facts across Abstract, Introduction, and Conclusion, but do not reuse the same sentence sequence.

## 5. Severity Calibration

Usually Major/P1:

- the RD algorithm model cannot be traced to acquisition or MF/RD processing;
- reconstruction is claimed as detection without a detector/evidence chain;
- a central result changes meaning because of metric or normalization drift;
- a causal module claim lacks an isolating comparison;
- an efficiency/real-time contribution mixes offline, online, fallback, or incompatible timing;
- the only evidence for a central stochastic/detection/estimation claim is one normalized image.

Usually Minor/P2-P3:

- a locally recoverable unit, acronym, axis label, or figure-reference ambiguity;
- a missing equation transition when the model remains traceable;
- repetitive connectors, abstract nouns, or local tense/voice inconsistency that does not alter technical meaning.

Classify by impact, not by manuscript location or grammar surface.

## 6. Representative Rewrite Frames

Use only after diagnosis and replace every bracket with manuscript facts.

- Problem: `In [RD setting], [physical/processing effect] can cause [observable consequence].`
- Gap: `[Method family] addresses [capability] but relies on [assumption/cost], which fails or becomes limiting under [condition].`
- Model bridge: `After [named processing steps], the samples are stacked into [model], where [operator] represents [radar meaning] and [unknown] contains [scene quantity].`
- Approximation: `Under [physical inequality/regime], [effect] is neglected; outside this regime, [model term or claim] must be revised.`
- Method distinction: `To control [diagnosed term], the method replaces/augments [closest component] with [mechanism].`
- Complexity: `[Quantity] is independent of [runtime data] and is precomputed; the online stage retains [dominant operations and cost].`
- Experiment: `Figure X illustrates [phenomenon], while [metric] in Table/Figure Y quantifies [claim] under [condition].`
- Bounded result: `Across [trials/settings], [metric] is [relation] relative to [baseline]; the conclusion is limited to [generator/regime].`
- Conclusion: `Within [tested scope], the evidence supports [narrow mechanism-specific takeaway] but does not yet cover [unvalidated boundary].`

Do not assemble these frames sequentially into a full section. Preserve author voice and avoid source-paper imitation.

## 7. Prohibited Inferences

- Do not say TAES requires this section order, a fixed Abstract/Conclusion length, Monte Carlo, measured data, off-grid tests, or an ablation table.
- Do not treat a narrow RD paper set as evidence for other radar topics.
- Do not request detection metrics when the manuscript makes only a reconstruction claim.
- Do not request a mismatch, clutter, motion, or hardware experiment after the corresponding claim has been explicitly removed and the boundary is physically justified.
- Do not infer internal lab preferences or proprietary design choices from this guide.
- Do not reproduce source-paper wording or construction-material content.

