# RBesT vs Bayesmeta: A Methodological Comparison

[![License: AGPL-3.0](https://img.shields.io/badge/License-AGPL%20v3-blue.svg)](LICENSE)
[![R](https://img.shields.io/badge/R-language-blue.svg)](https://www.r-project.org/)

This repository contains the methodological vignette and supporting analyses used to compare two widely adopted Bayesian evidence synthesis frameworks:

- **RBesT** (R Bayesian Evidence Synthesis Tools)
- **Bayesmeta**

The objective of this work is not to introduce a new methodology, but to provide a detailed mathematical and computational comparison of two established approaches for constructing Meta-Analytic Predictive (MAP) priors and incorporating historical information into current studies.

The analyses presented here served as a methodological reference during the development of:

## BayesianEvidenceSynthesis.jl

https://github.com/martingramage/BayesianEvidenceSynthesis.jl

---

## Motivation

Bayesian borrowing based on historical information has become an increasingly important component of modern clinical development. Among the most widely used approaches for constructing MAP priors are the workflows implemented in RBesT and Bayesmeta.

Although both frameworks address the same inferential objective, they rely on fundamentally different computational strategies:

| Package | Computational Strategy |
|----------|-----------------------|
| **RBesT** | MCMC-based Bayesian inference (Stan/Hamiltonian Monte Carlo) |
| **Bayesmeta** | Analytical and numerical integration for Normal-Normal Hierarchical Models (NNHM) |

Understanding the assumptions, strengths, limitations, and computational trade-offs of these approaches was an important step before developing an independent evidence synthesis framework in Julia.

---

## Relationship to BayesianEvidenceSynthesis.jl

This repository should be viewed as a methodological study that accompanies the development of BayesianEvidenceSynthesis.jl.

The analyses presented here were used to investigate:

- MAP prior construction workflows.
- Heterogeneity modelling strategies.
- Effective Sample Size (ESS) methodologies.
- Parametric mixture representations.
- Robustification procedures.
- Computational trade-offs between simulation-based and analytical approaches.

The conclusions obtained from this comparison informed several implementation choices in BayesianEvidenceSynthesis.jl, particularly regarding:

- MAP prior construction.
- ESS estimation.
- Posterior approximation.
- Robustification workflows.
- Report generation strategies.

BayesianEvidenceSynthesis.jl is an independent Julia implementation inspired by methodological concepts discussed in the Bayesian evidence synthesis literature and in the workflows available through RBesT and Bayesmeta.

---

## Contents

This repository includes:

- A complete methodological vignette.
- Mathematical derivations of the underlying hierarchical models.
- Comparative implementation examples using RBesT and Bayesmeta.
- Discussion of prior specification and heterogeneity modelling.
- Transformation of posterior predictive distributions between parameter scales.
- Graphical and numerical comparisons of resulting MAP priors.
- Supporting references from the Bayesian evidence synthesis literature.

---

## Main Topics Covered

### RBesT Workflow

- Generalized linear mixed models.
- MCMC estimation using Stan.
- MAP prior derivation.
- Mixture approximation using `automixfit`.
- Sensitivity analyses for heterogeneity priors.
- Robustification strategies.

### Bayesmeta Workflow

- Normal-Normal Hierarchical Models (NNHM).
- Analytical marginalization of latent parameters.
- Numerical integration over heterogeneity.
- Direct derivation of posterior predictive distributions.
- Mixture-of-normals representation.
- Transformation to the original response scale.

### Comparative Analysis

The vignette focuses on:

- Computational efficiency.
- Modelling assumptions.
- Posterior approximation accuracy.
- Parametric representation of MAP priors.
- Practical implications for historical borrowing in clinical trials.

---

## Key Findings

The comparison highlights the trade-offs between flexibility and computational efficiency:

- **RBesT** provides a flexible framework capable of handling generalized linear models and non-normal endpoints through MCMC estimation.
- **Bayesmeta** offers computationally efficient inference through analytical and numerical integration under the Normal-Normal Hierarchical Model framework.

Despite their different computational foundations, both approaches can yield closely aligned MAP prior distributions when their underlying modelling assumptions are satisfied.

These observations provided useful methodological guidance during the development of BayesianEvidenceSynthesis.jl.

---

## Intended Audience

This repository may be useful for:

- Bayesian statisticians.
- Clinical trial methodologists.
- Pharmaceutical statisticians.
- Researchers interested in historical borrowing.
- Developers implementing Bayesian evidence synthesis workflows.

---

## Citation

If you use this work as a methodological reference, please cite this repository and the original RBesT and Bayesmeta publications where appropriate.

---

## Acknowledgements

This work builds upon methodological concepts and software developed by the authors and contributors of RBesT and Bayesmeta. All credit for those packages belongs to their respective authors.

---

## License

This project is licensed under the GNU Affero General Public License v3.0 (AGPL-3.0).

See the `LICENSE` file for details.
