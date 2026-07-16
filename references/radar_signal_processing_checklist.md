# Radar Signal Processing Review Checklist

## How to Use

Mark each applicable item `Pass`, `Partial`, `Fail`, or `N/A`. A `Fail` becomes a Major Concern only when it threatens the manuscript's scope fit, core claim, technical validity, evidence chain, or reproducibility. Do not demand irrelevant tests merely to fill a checklist.

For every claimed contribution, ask:

1. What hypothesis or failure mechanism does it address?
2. What observation would support or falsify it?
3. Which experiment or derivation provides that observation?
4. Would another test materially change the revision decision? If not, do not request it.

## A. System and TAES Fit

- [ ] The radar/electronic system, sensing geometry, operating environment, and task are named.
- [ ] The paper locates the proposed method in the processing chain: waveform, front end, sampling, calibration, matched filtering, beamforming, RD processing, detection, tracking, imaging, or decision stage.
- [ ] The system consequence is concrete: masking, defocusing, migration, resolution loss, ambiguity, bias, false alarms, missed detections, tracking error, computation, memory, latency, or hardware burden.
- [ ] The method's assumptions are plausible for the stated radar chain and not merely convenient for optimization.
- [ ] Simulation parameters have physical units and are mutually consistent with bandwidth, PRI/PRF, CPI, aperture, wavelength, range/velocity resolution, and SNR definitions.
- [ ] Claimed engineering relevance is matched by appropriate implementation or measured-data evidence.

## B. Physical and Measurement Model

- [ ] Transmitted waveform or probing signal is defined when relevant.
- [ ] Received echo/measurement model includes propagation delay, Doppler, amplitude/phase, array response, or scattering terms required by the method.
- [ ] Fast time, slow time, pulse/snapshot/frame indices, and sampling operations are distinguishable.
- [ ] Discretization from continuous scene parameters to cells/grid/dictionary is shown.
- [ ] All vectors and matrices have stated or inferable dimensions, and products are dimensionally valid.
- [ ] Target/scatterer assumptions are stated: point/extended, sparse/dense, Swerling model, constant velocity, maneuvering, coherent/correlated, on-grid/off-grid, near/far field.
- [ ] Noise, clutter, interference, calibration, synchronization, quantization, and front-end effects are modeled or explicitly excluded.
- [ ] Approximation conditions are stated next to the approximation: narrowband, far field, small migration, local linearization, independent snapshots, Gaussianity, low rank, sparsity, or stationarity.
- [ ] Identifiability/observability is addressed when source count, grid, virtual aperture, geometry, or quantization could make the inverse problem nonunique.

## C. Bridge to the Algorithmic Model

- [ ] Every optimization variable, covariance, dictionary atom, steering vector, filter, state, or latent variable can be traced to the physical model.
- [ ] The objective or estimator follows from a likelihood, residual, MMSE/WLS criterion, covariance fit, detection statistic, physical constraint, or stated prior.
- [ ] Regularization and priors have physical/statistical interpretations, not only numerical convenience.
- [ ] The manuscript explains what information is lost or approximated during MF, RD, focusing, vectorization, covariance estimation, downsampling, quantization, or model reduction.
- [ ] Model mismatch is connected to an operational effect rather than named abstractly.
- [ ] If the method corrects mismatch, the corrected model is used consistently in both derivation and experiments.

## D. Proposed Method

- [ ] The method's core mechanism is distinguishable from baseline implementation details.
- [ ] Each module has a stated purpose tied to an earlier failure mechanism.
- [ ] The algorithm listing matches the equations, initialization, stopping condition, and output.
- [ ] Hyperparameters, thresholds, window/filter sizes, grid intervals, iteration counts, and priors have a selection rule or sensitivity analysis when decision-relevant.
- [ ] Convergence or stability claims are supported by proof, conditions, or empirical evidence with calibrated wording.
- [ ] Claimed novelty is comparative: it states what information, constraint, model term, or operation differs from prior methods.
- [ ] Complexity includes the dominant variables and operations; runtime claims include hardware/software and implementation conditions.
- [ ] Offline/online work, precomputation, storage, and per-cell/per-iteration cost are distinguished when relevant.

## E. Experiment Evidence Chain

Create a claim-to-evidence table before requesting new experiments:

| Claim | Required observation | Existing evidence | Gap | Decision value of new test |
|---|---|---|---|---|

### Scenario Selection

Select only applicable scenarios:

- [ ] Nominal model where the method should work.
- [ ] Failure condition targeted by the contribution: off-grid, migration, leakage, quantization, coupling, mismatch, low snapshots, or adverse geometry.
- [ ] Operational stress condition: low SNR, high dynamic range, strong clutter/interference, close targets, dense sources, maneuver, calibration error, or hardware nonideality.
- [ ] Model-boundary condition that reveals where the method stops working.
- [ ] Measured or hardware-in-the-loop data when deployment or system robustness is a central claim.

### Baseline Fairness

- [ ] Baselines are technically relevant and include the closest method family or prior version.
- [ ] All methods use the same data, random seeds/instances where possible, ROI, target truth, noise/clutter, preprocessing, grid, stopping budget, and metric definitions.
- [ ] Baseline priors are disclosed: known source/target count, true noise power, oracle tuning, true grid, calibration, or ground-truth-aided threshold.
- [ ] Parameters are tuned by a stated common procedure or each method's published recommendation.
- [ ] A baseline is not deliberately constrained to a smaller search region, fewer iterations, or weaker hardware without justification.
- [ ] Failed or out-of-memory baselines report implementation and resource limits rather than being silently omitted.

### Quantitative Evidence

- [ ] Imaging evidence includes task-relevant quantitative metrics, not only visually appealing RD/SAR/angle maps.
- [ ] Estimation uses bias, MSE/RMSE/AMSE, CRB, resolution probability, or confidence intervals as applicable.
- [ ] Detection uses Pd, Pfa, ROC, miss/false-alarm behavior, or threshold calibration as applicable.
- [ ] Sidelobe work reports PSLR/ISLR, sidelobe floor, non-target-cell MSE, weak-target amplitude error, or another defined measure.
- [ ] Complexity claims include operations, runtime, memory, iterations, latency, or throughput as applicable.
- [ ] Stochastic claims use enough independent trials and report what is randomized; uncertainty or variability is visible.
- [ ] Ablations isolate separable claimed mechanisms. Do not request ablations that cannot answer a causal question.
- [ ] Sensitivity tests focus on parameters authors must choose in practice.

### Reproducibility

- [ ] Radar/system parameters and units are tabulated or complete in text.
- [ ] Data-generation distributions, target/clutter placements, SNR/INR definitions, and randomization are specified.
- [ ] Algorithm initialization, stopping, thresholds, grids, and code/library versions are stated.
- [ ] Runtime hardware/software and parallelization are reported.
- [ ] Figures and tables state what claim they support.
- [ ] Supplementary code/data is labeled and described when used; the main text remains interpretable.

## F. Topic-Specific Branches

### F1. RD Imaging, Pulse Compression, IAA/APC

- [ ] Pulse train, waveform, PRF/PRI, CPI, sampling, range/velocity grids, and MF/RD operations are defined.
- [ ] Raw samples, MF/RD outputs, and algorithm inputs use distinct symbols or an explicit equivalence; `standard processing` does not hide model-defining operations.
- [ ] The MF output is decomposed into desired response, range sidelobes, Doppler sidelobes, joint interference, clutter, and noise as applicable.
- [ ] Strong/weak target masking is tied to dynamic range, sidelobe floor, processing gain, and detector behavior.
- [ ] RCM/DFM, intrapulse Doppler, acceleration, and velocity ambiguity are modeled or bounded.
- [ ] On-grid assumptions are tested or justified; off-grid/straddling is included when central to the claim.
- [ ] Local-window methods justify window support and edge handling.
- [ ] IAA/APC/RMMSE covariance construction, initialization, regularization, convergence, and per-cell cost are reproducible.
- [ ] RD maps use common axes, units, dB definitions, normalization, and color limits; a slice/local view or exact metric supports the central visual claim.
- [ ] Reconstruction is not renamed detection without a detector, threshold, target-present/absent model, and Pd/Pfa evidence.
- [ ] MSE/NMSE, complex/amplitude/power error, full-map/target/background regions, and linear/dB averaging are defined without metric drift.
- [ ] Fast implementations distinguish exact algebraic reuse from controlled approximation and separate precomputation, online work, memory, and end-to-end timing.
- [ ] Result paragraphs distinguish direct observation, mechanism-consistent interpretation, and causal attribution supported by an isolating comparison.

### F2. RFPA and Agile Waveforms

- [ ] Frequency/PRI agility distributions, ranges, dependence, hardware switching, and bandwidth are defined.
- [ ] Ambiguity-function statistics distinguish single realization, expectation, variance, mainlobe, near sidelobe, distant sidelobe, and ambiguity peaks.
- [ ] Near and distant sidelobes are traced to their different echo components.
- [ ] Waveform, transmitter constraints, receive filter, downsampling, and subsequent adaptive processing form a consistent chain.
- [ ] Frequency-gap, spectral leakage, constant-modulus, FIR length, ringing, and near-sidelobe-span tradeoffs are tested when relevant.

### F3. DSSS, Multipath, and MAI

- [ ] PN/spreading code, chip width/rate, sampling, correlation interval, data symbols, carrier, and path model are defined.
- [ ] Direct and reflected paths include delay, complex amplitude, phase, and Doppler/dynamics as applicable.
- [ ] Short-delay resolution, code cross-correlation, MAI power/ISR, and cell straddling are distinguished.
- [ ] DLL/PLL/tracking or open-loop assumptions and lock time are consistent with the claimed use.
- [ ] Code length, band-limiting, quantization, and front-end distortion are included when engineering performance is claimed.

### F4. DOA and Distributed Localization

- [ ] Array geometry, sensor positions, wavelength/spacing, aperture, near/far field, and coordinate conventions are defined.
- [ ] Wideband decomposition/focusing or time-domain convolution is physically valid for the bandwidth.
- [ ] Source number, correlation/coherence, stationarity/QSS frames, snapshots, and noise covariance assumptions are explicit.
- [ ] Claimed DOFs distinguish physical sensors, unique lags, consecutive lags, rank, and reliably resolvable sources.
- [ ] Sparse/grid methods examine grid mismatch; gridless/completion methods justify rank, holes, masks, and identifiability.
- [ ] CRB assumptions match the estimator and data model.
- [ ] Quantized/one-bit methods model thresholds, AGC, harmonics, and likelihood rather than applying a high-bit model unchanged.
- [ ] Distributed localization states geometry, synchronization, communication, target association, and single/multi-source limits.

### F5. SAR, ArcSAR, and Real-Aperture Superresolution

- [ ] Platform/antenna trajectory, aperture, beam pattern, range history, phase history, sampling, and propagation geometry are defined.
- [ ] Range/azimuth/elevation resolution is tied to bandwidth, aperture, wavelength, beamwidth, and range.
- [ ] Motion, height, projection, near-field, migration, and phase errors are derived before correction.
- [ ] Calibration sources and residual errors are reported.
- [ ] Image comparison uses common grids, windows, dynamic range, and normalization.
- [ ] Real-data claims distinguish stationary rigs, moving platforms, indoor/outdoor scenes, and full-azimuth coverage.

### F6. MIMO Radar

- [ ] Transmit/receive array geometry and virtual-array construction are defined.
- [ ] Waveform orthogonality/correlation, synchronization, channel separation, and calibration assumptions are explicit.
- [ ] Transmit and receive steering terms, target model, and dimensionality are consistent.
- [ ] Claims distinguish coherent MIMO, colocated/distributed MIMO, and phased-array behavior.
- [ ] Virtual aperture/DOF gains are validated under waveform and calibration errors.

### F7. STAP and Clutter Processing

- [ ] Space-time snapshot, array/PRF/CPI, steering vector, clutter ridge, and covariance model are defined.
- [ ] Training-data homogeneity, IID assumptions, sample support, target contamination, and nonstationarity are tested or bounded.
- [ ] Baselines use comparable training support and prior knowledge.
- [ ] Detection loss, SINR, Pd/Pfa, notch behavior, and computational burden are quantified.

### F8. Spacecraft RF Measurement

- [ ] Coordinate frames, attitude convention, LOS/range/angle measurements, and transformations are unambiguous.
- [ ] Observability/noncollinearity and singular configurations are analyzed.
- [ ] Radar equation and synchronization/tracking errors feed the measurement covariance.
- [ ] Formation optimization includes geometry constraints and states omitted dynamics, collision, scheduling, or control costs.
- [ ] Simulation-only results are not described as in-orbit validation.

## Major-Concern Triggers

Raise a Major Concern when any of the following affects a core claim:

- The mathematical model cannot be derived from or reconciled with the stated radar system.
- A key variable, dimension, assumption, or approximation is missing or inconsistent.
- The method solves a different problem than the one introduced.
- A central performance claim has no falsifiable quantitative evidence.
- Baseline comparison is materially unfair or relies on undisclosed oracle information.
- A claimed robustness condition is never tested.
- Complexity/real-time/deployment claims lack relevant evidence.
- The experiment demonstrates only an image while the claim concerns detection, estimation, robustness, or efficiency.
