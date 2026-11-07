# Validation status

## Verified

### 1. Reference implementation

The baseline `hscc3` Stata command reproduces the frozen reference implementation in the motivating application.

The optional `timefe` extension preserves the frozen HSCC-JOINT architecture in the main slope blocks, but its dedicated validation is reported separately below.

### 2. Point-estimator Monte Carlo

The frozen HSCC-JOINT architecture was evaluated under:

- homogeneous slopes,
- random slope heterogeneity,
- systematic slope heterogeneity,
- cross-sectional dependence,
- cross-sectional dependence + AR(1) + heteroskedasticity.

The point estimator showed strong RMSE performance relative to pooled FE and, in many heterogeneous designs, relative to MG.

### 3. Inference pilot

HC3 + Driscoll–Kraay inference was evaluated at multiple `T` values.

The main finite-sample limitation was mild small-`T` undercoverage. Calibration improved as `T` increased.

### 4. Residual block bootstrap

A circular moving-block residual bootstrap was tested and rejected because it generally produced even smaller standard errors and poorer coverage.

### 5. Algebraic properties

The following finite-sample properties have been derived:

- closed-form solution,
- convexity,
- uniqueness under rank/null-space conditions,
- mean-slope identification under centered heterogeneity,
- PSD residual slope covariance,
- pooling-limit behavior,
- pooled-FE special case,
- weak-penalty limit.

### 6. First asymptotic framework

Under fixed `N`, `T -> infinity`, bounded estimated penalty, and standard score/HAC regularity conditions:

- consistency follows,
- first-order asymptotic normality follows,
- the penalty is first-order asymptotically negligible,
- the HC3-DK covariance is consistent for the central slope asymptotic variance.

### 7. Common time fixed effects

Version 1.0.2 adds the optional `timefe` specification.

Common time effects are partialled out from the complete joint HSCC design using an FWL-equivalent transformation.

The time effects are treated as common nuisance components and are kept outside:

- the heterogeneous-slope blocks,
- the systematic heterogeneity component,
- the residual slope-deviation penalty.

This preserves the HSCC heterogeneous-slope architecture while allowing additive common period effects to be controlled for.

The `timefe` implementation should be treated as an extension of the empirical specification rather than as a separate estimator.

Dedicated numerical validation of the `timefe` implementation against an equivalent manually residualized specification is recommended before treating the extension as fully validated.

## Not yet established

- full double asymptotics (`N,T -> infinity`);
- general strong-factor endogeneity robustness;
- full generated-regressor asymptotics for stochastic `z_i`;
- higher-order finite-sample covariance correction;
- separate asymptotic theory specifically for the `timefe` extension beyond the maintained fixed-`N`, large-`T` framework.

## Recommended claims

Use:

> proposed HSCC3 estimator

> fixed-N, large-T consistency and asymptotic normality under stated regularity conditions

> HC3-DK inference under standard HAC conditions

Avoid:

> universally consistent

> robust to all forms of cross-sectional dependence

> fully established double-asymptotic theory
