# Common Flaws and Corrective Actions

## Evidence Boundary

These are review failure modes derived from official criteria, radar technical checks, and repeated RS4Radar corpus observations. They are **not** claimed to be common flaws in the user's lab. No internal-draft or reviewer-comment evidence was available for v1.

## CF-001 - Algorithm Without a System Loop

- Evidence: E0 TAES scope/technical areas; CORPUS-STYLE-001/002
- Typical severity: Major, P1
- Symptom: A sophisticated optimizer is presented without a radar/electronic-system task, acquisition chain, or physical consequence.
- Impact: Weak TAES fit and no basis for judging assumptions or metrics.
- Required action: State the system, measurement chain, failure mechanism, and operational metric; derive the algorithm model from them.

## CF-002 - Vague Contribution

- Evidence: CORPUS-STYLE-003
- Typical severity: Major, P1
- Symptom: `We propose a novel method to improve radar performance.`
- Impact: Novelty, verification path, and closest comparison are undefined.
- Required action: Name the scenario, bottleneck, mechanism, and evidence. Ensure Specific, Verifiable, and Comparative properties.

## CF-003 - Introduction as a Literature Inventory

- Evidence: official front-section requirement; CORPUS-STYLE-001/004
- Typical severity: Major or Minor depending on novelty clarity
- Symptom: One citation paragraph per acronym with no shared assumptions or failure condition.
- Impact: The gap appears asserted rather than derived.
- Required action: Reorganize by method family, solved capability, failure condition, cause, and the paper's core idea.

## CF-004 - Physical-to-Matrix Jump

- Evidence: CORPUS-STYLE-002; radar checklist B/C
- Typical severity: Major, P1
- Symptom: Radar prose is followed by `y = Ax + n` without acquisition, discretization, dimensions, or variable meanings.
- Impact: The method may solve a different or physically invalid problem.
- Required action: Add the continuous echo/measurement model, processing operations, grid/dictionary construction, assumptions, and objective bridge.

## CF-005 - Undefined Dimensions or Symbol Drift

- Evidence: E2 technical correctness
- Typical severity: Major if equations become invalid; otherwise Minor
- Symptom: Matrix products cannot be checked; one symbol changes meaning; conjugate/transpose conventions vary.
- Impact: Derivation and implementation are not auditable.
- Required action: Define dimensions at first use, audit every product, and use a notation table for formula-heavy manuscripts.

## CF-006 - Hidden Assumptions

- Evidence: CORPUS-STYLE-010; radar checklist B
- Typical severity: Major when central, otherwise Minor
- Symptom: Far-field, narrowband, Gaussian, independent, sparse, low-rank, constant-velocity, known-noise, or stationary assumptions appear only implicitly.
- Impact: Claims are applied outside the regime in which equations hold.
- Required action: State each assumption beside the derivation it enables and repeat the key boundary in Experiments/Conclusion.

## CF-007 - Ignored Grid Mismatch, Straddling, or Migration

- Evidence: CORPUS-STYLE-009
- Typical severity: Major when the contribution claims robustness or fine resolution
- Symptom: Continuous range/Doppler/angle parameters are simulated only at grid centers.
- Impact: Reported gains may disappear under realistic offsets or motion.
- Required action: Either justify exact alignment or add a decision-relevant mismatch model and stress test.

## CF-008 - Attractive Maps Without Quantitative Evidence

- Evidence: official IEEE experimental-design/reproducibility criteria; CORPUS-STYLE-006/011
- Typical severity: Major, P1
- Symptom: Two or three RD/SAR/DOA images are the only evidence for detection, estimation, robustness, or efficiency.
- Impact: Visual dynamic range and normalization can conceal error, false alarms, or variability.
- Required action: Add task-matched metrics such as Pd/Pfa, RMSE, bias, sidelobe floor, PSLR/ISLR, amplitude error, CRB, runtime, or memory.

## CF-009 - Unfair or Untraceable Baselines

- Evidence: official objective/actionable review guidance; E2 technical fairness
- Typical severity: Major, P1
- Symptom: Different ROI, grids, data, iteration budgets, preprocessing, oracle priors, or tuned parameters are used without disclosure.
- Impact: Comparative contribution is not supported.
- Required action: Build a baseline-assumption table and rerun only comparisons whose fairness can affect the conclusion.

## CF-010 - Single-Trial Evidence for a Stochastic Claim

- Evidence: CORPUS-STYLE-006
- Typical severity: Major or Minor based on claim centrality
- Symptom: One noise realization supports a claim about detection probability, RMSE, random waveforms, or robustness.
- Impact: Variance and failure probability are unknown.
- Required action: Use independent trials, state randomized factors, report uncertainty/statistics, and justify trial count relative to the metric.

## CF-011 - Unsupported Efficiency or Real-Time Claim

- Evidence: CORPUS-STYLE-005
- Typical severity: Major when central, otherwise Minor
- Symptom: `low complexity` is based only on fewer equations or asymptotic notation omits dominant variables.
- Impact: Engineering contribution is unverifiable.
- Required action: Report dominant operations, problem dimensions, memory, iterations, runtime environment, online/offline work, and latency/throughput if `real-time` is claimed.

## CF-012 - Measured Data Overclaim

- Evidence: CORPUS-STYLE-007/010
- Typical severity: Major when deployment is central
- Symptom: Stationary, acoustic, indoor, or simulator-generated data is described as validating an airborne, radar, dynamic, or fielded system end to end.
- Impact: External validity exceeds the tested chain.
- Required action: State exactly which module and conditions the measured data validate; calibrate the remaining claim or add the relevant system test.

## CF-013 - Decorative Ablation

- Evidence: CORPUS-STYLE-008; hypothesis-driven experiment policy
- Typical severity: Minor request-quality issue
- Symptom: Every term is removed in turn without a causal hypothesis, or reviewers request exhaustive combinations with no decision value.
- Impact: Consumes effort without clarifying why the method works.
- Required action: Request only intermediate baselines that isolate a separable claimed mechanism or affect a design decision.

## CF-014 - Parameter Choice by Unreported Trial and Error

- Evidence: CORPUS-STYLE-005; cards RS4R-015, 017, 021
- Typical severity: Major when outcomes are sensitive, otherwise Minor
- Symptom: Threshold, grid, regularizer, window, or iteration is selected using truth but presented as deployable.
- Impact: Reproducibility and practical relevance are weak.
- Required action: Disclose the oracle/tuning process, derive a selector, or provide sensitivity and a practical rule.

## CF-015 - Conclusion Exceeds Evidence

- Evidence: section rubric; CORPUS-STYLE-010
- Typical severity: Major if it changes the central claim, otherwise Minor
- Symptom: `robust`, `universal`, `real-time`, `practical`, or `applicable to moving platforms` exceeds tested conditions.
- Impact: Readers cannot distinguish demonstrated performance from future work.
- Required action: Replace absolute wording with conditions and explicitly state untested regimes.

## CF-016 - Language Editing Before Technical Repair

- Evidence: Skill output behavior
- Typical severity: Workflow error
- Symptom: The review rewrites prose while model, novelty, or evidence remains unresolved.
- Impact: Polished language can mask a technically unready manuscript.
- Required action: Resolve P0/P1 technical and evidence concerns first; provide only representative rewrites after diagnosis.

## CF-017 - Treating a Corpus Example as a Journal Rule

- Evidence: RS4Radar evidence boundary
- Typical severity: Reviewer-method error
- Symptom: `TAES requires Monte Carlo`, `TAES always requires real data`, or `TAES papers use this section order` based on one or several corpus papers.
- Impact: Invents editorial policy and creates unjustified revision work.
- Required action: Label the observation as a corpus pattern, provide support count, and explain the underlying review objective.

## CF-018 - Invented Group Preference

- Evidence: missing internal material boundary
- Typical severity: Prohibited inference
- Symptom: Published papers are used to claim a supervisor's preferred wording, common student mistake, or internal rejection cause.
- Impact: Unsupported and potentially misleading personalization.
- Required action: Keep group-public papers as E3 context only. Internal-preference rules remain disabled until authorized evidence is supplied.
