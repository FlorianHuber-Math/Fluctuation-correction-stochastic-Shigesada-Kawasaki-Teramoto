# Numerical experiments for the λ-modified stochastic SKT system

This repository accompanies the paper

> F. Huber, *Existence of martingale solutions to a stochastic Shigesada–Kawasaki–Teramoto cross-diffusion system* (revised version, 2026).

The notebook `skt_lambda_numerics.ipynb` reproduces Section 7 (Figures 1 and 2). It compares the following, in one dimension with two species:

- **SPDE:** the discretized stochastic SKT equation with the λ-modified Itô–Stratonovich correction (λ/N)𝒯.
- **Particle system:** the moderately interacting system of Chen, Daus, Holzinger and Jüngel.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/<user>/<repo>/blob/main/skt_lambda_numerics.ipynb)

(Replace `<user>/<repo>` in the badge link with the GitHub path of this repository.)

## Contents

| Section of the notebook | What it does |
|---|---|
| 1 | Parameters and initial data |
| 2 | Finite-volume Euler–Maruyama scheme for the SPDE with the correction term in closed form |
| 3 | Particle system and mollified mean-field limit |
| 4 | Bias estimation with a control variate |
| 5 | Experiment 1: dependence on λ (mean, variance, pathwise effect) |
| 6 | Experiment 2: O(1/N) bias of the particles against the SPDE, and the matching λ* |
| 7 | Figures |
| 8 | Interpretation and caveats |

## Running it

- **On Colab:** open the notebook with the badge above and run all cells. `numpy`, `numba` and `matplotlib` are preinstalled.
- **Locally:**
  ```
  pip install numpy numba matplotlib jupyter
  jupyter notebook skt_lambda_numerics.ipynb
  ```
- **Run time:**
  - `FULL = False` (default): about 10–15 minutes on two CPU cores, with error bars 2–3 times larger than in the paper.
  - `FULL = True`: the sample sizes of the paper, several hours.

## Main findings

- The value of λ shifts the mean by exactly the deterministic effect of (λ/N)𝒯.
- The variance does not depend on λ.
- The pathwise effect of λ is below 1.3% of the fluctuations for N ≥ 1000.
- The particle system matches the Itô equation (λ = 0) when the noise scale equals the interaction range.
- It matches λ ≈ 0.39 ± 0.10 when the noise is correlated over twice the interaction range. In this sense λ acts as a renormalization constant.

## License

MIT (or adapt as you prefer).
