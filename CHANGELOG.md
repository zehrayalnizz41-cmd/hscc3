# Changelog

## 1.0.2 — 2026-09-28

- Added optional common time fixed effects via the `timefe` option.
- Time effects are partialled out from the joint HSCC3 design using an FWL-equivalent transformation.
- Time effects are treated as common nuisance parameters and are kept outside the heterogeneous-slope blocks.
- Retained the frozen HSCC3-JOINT point-estimator architecture.
- Retained HC3-adjusted Driscoll–Kraay / SCC inference.
- Added reporting of time fixed-effects status in the estimation output.
- Added recovery and storage of centered common time effects in `e(timefe_b)`.
- Fixed the display routine so recovered common time effects are read from `e(timefe_b)` rather than the temporary Mata/Stata matrix name.
- No change was made to the HSCC3 point estimator, penalty structure, or HC3-DK inference.

## 1.0.1 — 2026-09-27

- Added descriptive HSCC3 within R-squared (`e(r2_w)`).
- Retained frozen HSCC3-JOINT point-estimator architecture.
- Retained HC3-adjusted Driscoll–Kraay / SCC inference.
- Added fixed-N, large-T theoretical documentation.
- Added validation and reproducibility documentation.

## 1.0.0 — 2026-09-27

- Initial Stata command.
- Joint partial-pooling heterogeneous-slope estimator.
- Systematic + residual slope heterogeneity.
- PSD-corrected residual slope covariance.
- HC3-DK covariance.
