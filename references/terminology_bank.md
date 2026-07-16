# Radar and Array Terminology Bank

## Usage Rules

- Define each abbreviation at first use in the manuscript and use one form consistently.
- Do not expand a term differently across sections.
- Preserve distinctions below; several are not interchangeable.
- This is a working corpus terminology bank, not an IEEE standards glossary.

## Core Radar Processing

| Term | Meaning and review caution |
|---|---|
| MF | Matched filter. State whether it is range-only, Doppler-only, 2-D, or applied to a particular waveform replica. |
| RD | Range-Doppler. Define range and Doppler/velocity cell intervals and whether the map is MF, FFT, or estimator output. |
| Pulse compression | Matched/mismatched processing that trades waveform duration for range resolution/processing gain. Do not equate it with sidelobe-free recovery. |
| Processing gain | Define the reference input/output SNR and normalization. Do not infer detection gain from a prettier image. |
| PSLR | Peak sidelobe ratio; state sign convention, dimensions, and excluded mainlobe region. |
| ISLR | Integrated sidelobe ratio; state integration regions and normalization. |
| RCM | Range cell migration. Distinguish migration across slow time from off-grid range straddling within a cell. |
| DFM | Doppler frequency migration. Define the motion/order that causes Doppler drift across bins. |
| Straddling / off-grid | A continuous parameter lies between discrete grid points. State the offset interval and affected steering/response model. |
| Weak-target masking | Strong-target sidelobes/clutter exceed a weak target's response. Quantify dynamic range and detector/metric effect. |
| RD reconstruction / detection | Reconstruction estimates an RD field or coefficients. Detection requires a decision rule, threshold, target-present/absent model, and false-alarm behavior. Do not infer detection from ranked cells or a visually clean map. |

## Adaptive and Sparse Estimation

| Term | Meaning and review caution |
|---|---|
| IAA | Iterative adaptive approach. Specify data model, covariance update, initialization, regularization, stopping, and variant. |
| IAA-APES | IAA formulation associated with amplitude and phase estimation/WLS. Do not use as a generic name for every iterative adaptive filter. |
| APC | Adaptive pulse compression. State the MMSE/RMMSE formulation and whether filtering is per pulse, range cell, or RD cell. |
| RMMSE | Reiterative minimum mean-square error filtering. Define prior/power updates and covariance assumptions. |
| WLS | Weighted least squares. State the weight/covariance source and whether it is known, estimated, or updated. |
| SPICE | Sparse iterative covariance-based estimation. Name the weighting/variant and hyperparameter behavior. |
| Sparse recovery | Requires a stated sparse object, dictionary, observation model, coherence/grid assumptions, and recovery criterion. |
| Group sparsity | Multiple vectors/matrices share support. Identify the grouped dimension: snapshots, frequencies, sensors, covariance columns, or locations. |
| Gridless | Avoids a discretized search grid; it does not automatically avoid model mismatch, finite-sample error, or identifiability limits. |
| Tensor completion | Recovers missing tensor entries under rank/observation assumptions. State the mask, rank mechanism, solver, and stopping. |

## Waveform Agility and Sidelobes

| Term | Meaning and review caution |
|---|---|
| RFPA | Random frequency and pulse repetition interval agile. Define both distributions/ranges and any dependence. |
| RMWFPA | Random multi-timeslot wide-gap frequency-hopping and PRI agile, as used in the corpus. Define it explicitly; do not assume readers know this nonstandard compound acronym. |
| AF | Ambiguity function. Distinguish a realization from expectation/variance for random waveforms and state normalization. |
| Near sidelobe | In RFPA corpus usage, the range sidelobe region confined near the mainlobe/about a pulsewidth; define the exact region in the manuscript. |
| Distant sidelobe | RFPA range sidelobe floor outside the near region, associated with adjacent-pulse echo components; define the region. |
| WGFHS | Wide-gap frequency-hopping sequence. State minimum gap and number of adjacent timeslots constrained. |
| OOSB | Out-of-subband. Identify whose subband and which selected frequency intervals. |
| LPF / FIR-DSSF | Low-pass filter / finite-impulse-response distant-sidelobe suppression filter. Report pass/stop bands, order/length, ripple, attenuation, and ringing span. |

## DSSS and Navigation-Like Processing

| Term | Meaning and review caution |
|---|---|
| DSSS | Direct-sequence spread spectrum. Define PN/spreading code, code period, chip rate, data symbols, and correlation interval. |
| MPE | Multipath effect. Distinguish path parameter estimation from downstream multipath-error mitigation. |
| MAI | Multiple-access interference. Report code family, number of interferers, ISR, and power-control assumptions. |
| DLL / PLL | Delay-lock loop / phase-lock loop. State loop bandwidth, coherent time, lock/dynamic assumptions, and error sources. |
| ISR / INR | Interference-to-signal ratio / interference-to-noise ratio. Define numerator, denominator, and integration point. |

## Arrays, DOA, and Localization

| Term | Meaning and review caution |
|---|---|
| DOA / AOA | Direction/angle of arrival. State angular convention, broadside/endfire reference, dimensionality, and units. |
| ULA | Uniform linear array. State sensor count, spacing, aperture, wavelength reference, and aliasing condition. |
| Sparse array | Nonuniform physical array designed to create virtual lags; do not confuse with sparse sources. |
| Difference coarray | Virtual sensor locations from pairwise physical-array differences. Distinguish unique and consecutive lags. |
| DOF | Degree of freedom. State whether it means virtual lags, rank, independent measurements, or resolvable sources. |
| QSS | Quasi-stationary signal. Define frame-level stationarity and cross-frame variation. |
| CRB | Cramer-Rao bound. State deterministic/stochastic model, nuisance parameters, priors, and whether assumptions match the estimator. |
| Focusing | Maps wideband subbands to a reference manifold. Report focusing angles/frequency and approximation error. |
| Near field / far field | State relative to which aperture: a source can be near-field to a distributed network and far-field to each subarray. |
| One-bit ADC | Quantizer preserving signs relative to thresholds. Model threshold knowledge, AGC, harmonics, and loss of amplitude. |

## SAR and Imaging Systems

| Term | Meaning and review caution |
|---|---|
| SAR / ArcSAR / C-SAR | Synthetic aperture / arc synthetic aperture / circular SAR. State trajectory, aperture support, dimensionality, and acquisition geometry. |
| BPA / FBP / GFBP | Back projection / filtered back projection / generalized FBP. Define interpolation, phase compensation, grid, and complexity. |
| RPP | Range-profile projection. Define normalization and azimuth support before coherence-factor use. |
| PCF / FPCF | Phase coherence factor / full-azimuth PCF. State how phase consistency is calculated and how memory is reduced. |
| SPC | Scattering phase correction in the corpus C-SAR context. Do not confuse it with statistical process control or other fields. |
| Migration correction | Specify range, azimuth, elevation, or Doppler migration and the physical approximation behind correction. |

## Spacecraft RF Measurement

| Term | Meaning and review caution |
|---|---|
| LOS | Line of sight. Include coordinate frame, direction convention, and whether magnitude is retained. |
| Wahba problem | Least-squares rotation estimation from corresponding vector sets. State weights, noncollinearity, and SVD/orthogonality handling. |
| 3-2-1 Euler angles | Yaw-pitch-roll sequence used in the corpus paper. State rotation direction and singularity. |
| Formation geometry | Relative node positions governing observability and covariance. Include distance-dependent RF measurement error and omitted operational constraints. |

## Evidence and Metrics

| Term | Meaning and review caution |
|---|---|
| SNR | Define signal and noise powers and the processing stage at which they are measured. |
| MSE / RMSE / AMSE | Define averaging dimensions, normalization, excluded cells, and Monte Carlo randomization. |
| MSE / NMSE | NMSE requires an explicit reference-energy normalization. Do not relabel a mean squared error as normalized because the displayed image was normalized. |
| Amplitude / power | Distinguish magnitude from squared magnitude and use the corresponding dB conversion. State whether dynamic range and error are defined in amplitude, power, or complex-coefficient space. |
| Convergence / termination | Meeting a stopping rule or maximum iteration budget is not a convergence proof. Report the rule, stop reason, and iteration count. |
| Runtime / speedup / end-to-end time | State timed components, preprocessing, precomputation, stopping, platform, repetitions, and parallelism. A component runtime is not an end-to-end speedup or real-time guarantee. |
| Numerical floor | Clipping or machine precision used for reporting. Do not describe a floor-limited value as physical zero, exact cancellation, or further measurable improvement. |
| Pd / Pfa | Probability of detection / false alarm. State detector, threshold, trial count, and target-present/absent models. |
| Monte Carlo trial | One independent draw of stated random variables. Report seed policy or distributions and number of trials. |
| Real data | State acquisition hardware, scene, preprocessing, calibration, and which contribution it validates. Simulator-generated or stationary-rig data should be labeled precisely. |
| Robust | Name the perturbation set and tested range. `Robust` without a defined uncertainty or stress test is not verifiable. |
| Real-time | Requires a deadline/throughput target and measured implementation under relevant hardware/data dimensions. Runtime alone is not enough. |
