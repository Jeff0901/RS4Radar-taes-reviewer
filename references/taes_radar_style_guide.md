# RS4Radar Corpus Style Guide

## Evidence Boundary

This guide synthesizes 26 TAES papers in the frozen Zotero `RS4Radar` corpus. It is not a random or journal-wide sample and is concentrated in a small set of collaborating author teams. Every item below is a **RS4Radar corpus pattern**, never a TAES rule or acceptance criterion.

The optional `rd_recovery_review_guide.md` is a secondary, topic-specific synthesis of a narrow RD/IAA-oriented subset that overlaps this corpus. It adds no independent support count and cannot upgrade any pattern to E1.

Evidence classes used by this Skill:

- `E0`: official IEEE/TAES source.
- `E1`: cross-team TAES style preference. No E1 rules exist in v1.
- `E2`: radar technical standard or broadly established technical requirement.
- `E3`: group public research context.
- `E4`: single-paper observation.
- `S`: synthetic test-only material; never rule evidence.

## Empirical Pattern Ledger

### CORPUS-STYLE-001 - System consequence before algorithm

- Rule type: RS4Radar corpus writing pattern
- Sources: RS4R-001, RS4R-002, RS4R-003, RS4R-004, RS4R-005, RS4R-007, RS4R-008, RS4R-009, RS4R-010, RS4R-011, RS4R-012, RS4R-013, RS4R-019, RS4R-020, RS4R-023, RS4R-024, RS4R-025, RS4R-026, RS4R-027
- Support count: 19 papers
- Topics: T1, T2, T3, T5, T6
- Applicable sections: Abstract, Introduction
- Confidence: High within this corpus; limited author-team diversity
- Pattern: Introduce the radar/electronic-system value and the physical performance consequence before presenting the algorithm family.
- Allowed use: Ask whether the manuscript explains what system task fails and why the failure matters.
- Prohibited inference: Do not require the same paragraph order or wording; do not call it a TAES-wide convention.

### CORPUS-STYLE-002 - Physical-to-mathematical bridge

- Rule type: RS4Radar corpus writing pattern
- Sources: RS4R-001, RS4R-002, RS4R-003, RS4R-004, RS4R-005, RS4R-006, RS4R-007, RS4R-008, RS4R-009, RS4R-010, RS4R-011, RS4R-012, RS4R-013, RS4R-015, RS4R-016, RS4R-017, RS4R-018, RS4R-019, RS4R-020, RS4R-021, RS4R-022, RS4R-023, RS4R-024, RS4R-025, RS4R-026, RS4R-027; RS4R-014 excluded
- Support count: 26 TAES papers
- Topics: T1-T6
- Applicable section: Problem Formulation
- Confidence: High within this corpus
- Pattern: Define a system/measurement model, explain the physical meaning of variables and assumptions, then derive the inverse, estimation, optimization, covariance, or geometry problem.
- Allowed use: Flag a jump from radar prose to an abstract matrix problem when variables or assumptions cannot be traced.
- Prohibited inference: Do not demand a standalone section named `Problem Formulation`; integrated formulations are acceptable.

### CORPUS-STYLE-003 - Specific, verifiable, comparative contribution statements

- Rule type: RS4Radar corpus writing pattern
- Sources: RS4R-001, RS4R-002, RS4R-003, RS4R-004, RS4R-005, RS4R-006, RS4R-007, RS4R-008, RS4R-009, RS4R-010, RS4R-011, RS4R-012, RS4R-013, RS4R-015, RS4R-016, RS4R-017, RS4R-018, RS4R-019, RS4R-020, RS4R-021, RS4R-022, RS4R-023, RS4R-024, RS4R-025, RS4R-026, RS4R-027; RS4R-014 excluded
- Support count: 26 TAES papers
- Topics: T1-T6
- Applicable sections: Abstract, Introduction, Conclusion
- Confidence: High within this corpus
- Pattern: Stronger contribution statements identify the scenario, bottleneck, mechanism, and evidence or comparison target.
- Allowed use: Diagnose vague contributions and ask for a claim-to-evidence mapping.
- Prohibited inference: A contribution list is not mandatory if the same information is clear in prose.

### CORPUS-STYLE-004 - Method modules follow diagnosed failure mechanisms

- Rule type: RS4Radar corpus writing pattern
- Sources: RS4R-001, RS4R-003, RS4R-004, RS4R-005, RS4R-008, RS4R-009, RS4R-010, RS4R-011, RS4R-012, RS4R-013, RS4R-016, RS4R-018, RS4R-019, RS4R-020, RS4R-022, RS4R-023, RS4R-024, RS4R-025, RS4R-026, RS4R-027
- Support count: 20 papers
- Topics: T1-T6
- Applicable sections: Introduction, Problem Formulation, Proposed Method
- Confidence: High within this corpus
- Pattern: Each major method module is motivated by a named mismatch, coupling, leakage, quantization, geometry, computational, or identifiability problem.
- Allowed use: Ask why each module is needed and which earlier failure it resolves.
- Prohibited inference: Do not reject a simpler single-module method merely for having fewer components.

### CORPUS-STYLE-005 - Engineering cost accompanies accuracy

- Rule type: RS4Radar corpus evidence pattern
- Sources: RS4R-001, RS4R-002, RS4R-003, RS4R-004, RS4R-005, RS4R-007, RS4R-008, RS4R-009, RS4R-011, RS4R-012, RS4R-013, RS4R-015, RS4R-017, RS4R-018, RS4R-020, RS4R-021, RS4R-022, RS4R-024, RS4R-025, RS4R-026, RS4R-027
- Support count: 21 papers
- Topics: T1-T5
- Applicable sections: Proposed Method, Theory/Complexity, Experiments
- Confidence: High within this corpus
- Pattern: Complexity, memory, iteration count, window/filter size, runtime, sampling, or implementation partition is evaluated alongside accuracy.
- Allowed use: Treat an unsubstantiated `fast`, `low-complexity`, or `real-time` claim as unsupported.
- Prohibited inference: Do not require runtime when the manuscript makes no efficiency claim and complexity is not decision-relevant.

### CORPUS-STYLE-006 - Statistical evidence for stochastic claims

- Rule type: RS4Radar corpus evidence pattern
- Sources: RS4R-001, RS4R-002, RS4R-003, RS4R-005, RS4R-006, RS4R-007, RS4R-011, RS4R-012, RS4R-013, RS4R-015, RS4R-016, RS4R-017, RS4R-018, RS4R-019, RS4R-021, RS4R-022, RS4R-023, RS4R-024
- Support count: 18 papers explicitly recorded with Monte Carlo/statistical evaluation
- Topics: T1-T6
- Applicable section: Experiments
- Confidence: High within this corpus
- Pattern: Claims about noise, random waveforms, random target layouts, estimation error, detection, or convergence are supported with repeated trials, distributions, RMSE/MSE, probability, bias, variance, or CRB comparisons.
- Allowed use: Require statistical evidence when the claim itself is stochastic.
- Prohibited inference: Do not demand Monte Carlo for a deterministic identity or a single measured-system demonstration that makes no stochastic generalization.

### CORPUS-STYLE-007 - Measured data is valuable but not universal

- Rule type: RS4Radar corpus evidence pattern
- Sources: RS4R-001, RS4R-011, RS4R-016, RS4R-018, RS4R-020, RS4R-022
- Support count: 6 papers with explicit measured/experimental data in their cards
- Topics: T1, T4, T5
- Applicable section: Experiments
- Confidence: High for presence count; no claim about the rest of TAES
- Pattern: Measured data strengthens model-to-system validity, but many corpus papers rely on theory and simulation.
- Allowed use: Request measured data when deployment or hardware robustness is a central claim.
- Prohibited inference: Absence of measured data alone is not an automatic Major Concern when the paper's claim is theoretical and the simulation/theory evidence is sufficient.

### CORPUS-STYLE-008 - Module isolation supports causal claims

- Rule type: RS4Radar corpus evidence pattern
- Sources: RS4R-004, RS4R-008, RS4R-025
- Support count: 3 papers with explicit module-isolating comparisons recorded in the cards
- Topics: T1, T2, T3
- Applicable section: Experiments
- Confidence: Moderate; narrow support
- Pattern: Intermediate baselines or module combinations isolate whether gains come from model correction, pipeline structure, or a new estimator.
- Allowed use: Request ablation when the paper attributes gains to multiple separable modules.
- Prohibited inference: Do not demand decorative ablations that cannot answer a concrete causal question.

### CORPUS-STYLE-009 - Modeling mismatch is made operational

- Rule type: RS4Radar corpus technical-writing pattern
- Sources: RS4R-001, RS4R-003, RS4R-004, RS4R-009, RS4R-010, RS4R-018, RS4R-024, RS4R-025
- Support count: 8 papers
- Topics: T1, T3, T4
- Applicable sections: Introduction, Problem Formulation, Experiments
- Confidence: High within these topics
- Pattern: Off-grid, straddling, migration, missing-lag, or related mismatch is connected to a concrete failure such as loss of orthogonality, residual sidelobes, defocusing, or biased amplitude.
- Allowed use: Ask for the mechanism and a mismatch stress test.
- Prohibited inference: Do not require off-grid tests when the acquisition or claim is provably grid-aligned.

### CORPUS-STYLE-010 - Limitations remain visible

- Rule type: RS4Radar corpus writing pattern
- Sources: RS4R-001, RS4R-005, RS4R-006, RS4R-008, RS4R-011, RS4R-012, RS4R-013, RS4R-017, RS4R-019, RS4R-020, RS4R-022, RS4R-027
- Support count: 12 representative papers
- Topics: T1-T6
- Applicable sections: Discussion, Experiments, Conclusion
- Confidence: Moderate to high
- Pattern: Assumption boundaries, simulation-only status, stationary-platform tests, one-source restrictions, future real-data needs, or implementation limits are stated explicitly.
- Allowed use: Recommend calibrated limitation language and prevent extrapolation beyond tested conditions.
- Prohibited inference: Do not force a separate `Limitations` heading.

### CORPUS-STYLE-011 - Evidence is aligned to contribution modules

- Rule type: RS4Radar corpus evidence pattern
- Sources: RS4R-001, RS4R-002, RS4R-003, RS4R-004, RS4R-005, RS4R-007, RS4R-008, RS4R-009, RS4R-010, RS4R-012, RS4R-013, RS4R-023, RS4R-024, RS4R-025, RS4R-026, RS4R-027
- Support count: 16 papers in the T1-T3 method chains
- Topics: T1, T2, T3
- Applicable sections: Introduction, Experiments, Conclusion
- Confidence: High in these topics
- Pattern: Model correction, estimator accuracy, weak-target/path recovery, parameter behavior, and efficiency are tested by different evidence rather than one composite figure.
- Allowed use: Build a contribution-to-evidence matrix and flag unsupported claims.
- Prohibited inference: Do not require every paper to use the same metrics or scenario count.

## Practical Writing Implications

- Prefer `For [system/scenario], [failure] causes [observable consequence]. To address this, ...` over `We propose a novel algorithm.`
- Keep the system model and the algorithm model in one variable chain.
- State assumptions next to the equation or claim they enable.
- Describe comparison differences by mechanism and prior information, not only by acronym.
- State what each experiment tests before showing its figure or table.
- Use calibrated verbs: `demonstrates under`, `supports`, `is consistent with`, `suggests`; reserve `proves` for formal proof.

## Non-Rules

- Real data is not universally mandatory.
- A standalone complexity section is not universally mandatory.
- A contribution bullet list is not universally mandatory.
- Every manuscript does not need all on-grid, off-grid, clutter, low-SNR, sensitivity, ablation, runtime, and Monte Carlo tests. Select tests that answer the paper's claims and failure hypotheses.
- The corpus does not establish preference for IAA, WLS, SPICE, sparse recovery, Bayesian inference, a specific section order, or a specific number of figures.
