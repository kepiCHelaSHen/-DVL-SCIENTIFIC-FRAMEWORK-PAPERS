# The Fermi Paradox as a Survival Function

## 1. Definitions

### 1.1 Foundational Objects

**Definition 1 (Probability Space).** Let (Ω, F, P) denote the underlying probability space on which all random quantities in this paper are defined. Ω is the sample space of possible histories of civilizational emergence and survival in the Milky Way; F is the σ-algebra of measurable events; P is the probability measure.

**Definition 2 (Galactic Age).** T_gal = 13.6 Gyr, the age of the Milky Way as a star-forming system (Planck Collaboration 2020, A&A 641:A6). Tolerance: ±0.1 Gyr. This parameter sets the upper limit of the time domain for the survival model.

**Definition 3 (Stellar Population).** N★ ≈ 10^{11}, the approximate number of stars in the Milky Way (Bland-Hawthorn & Gerhard 2016, ARA&A 54:529–596). This enters as an order-of-magnitude scale factor; all central results are robust across one order of magnitude in N★.

**Definition 4 (Emergence Rate).** Λ > 0 [civilizations · yr⁻¹], the mean rate at which communicative civilizations emerge across the galaxy, treated as constant over galactic history. This compound parameter subsumes the product N★ · f_p · n_e · f_l · f_i · f_c / T_gal from the Drake equation (Drake 1961). We treat Λ as a single irreducible parameter because its internal decomposition is not resolvable from current observational data. Crucially, Λ parameterizes emergence only — it says nothing about how long civilizations survive. The decoupling of emergence rate from survival time is the structural departure from the Drake equation that motivates this paper.

### 1.2 Survival Model

**Definition 5 (Communicative Lifetime).** T : Ω → [0, ∞), a non-negative random variable representing the duration of a civilization's communicative window — the interval from the onset of detectable electromagnetic emission to its permanent cessation.

**Definition 6 (Survival Function).** S : [0, ∞) → [0, 1], defined by

  S(t) = P(T > t)

for t ≥ 0. The probability that a randomly selected civilization remains in its communicative window for at least time t after emergence. Required boundary conditions: S(0) = 1, lim_{t→∞} S(t) = 0.

**Definition 7 (Hazard Function).** h : (0, ∞) → [0, ∞), defined by

  h(t) = −d/dt [ln S(t)] = f(t) / S(t)

where f(t) = −dS(t)/dt is the probability density of T. The hazard h(t) gives the instantaneous rate of communicative cessation at time t, conditional on survival to time t. The cumulative hazard is H(t) = ∫₀ᵗ h(s) ds, with the fundamental relationship S(t) = exp(−H(t)). This framework follows the standard formulation of Cox (1972, JRSS-B 34:187–220).

**Definition 8 (Exponential Hazard Model).** The baseline constant-hazard model: h(t) = λ for all t > 0, where λ > 0 is the hazard rate parameter. This gives:

- S(t) = exp(−λt)
- f(t) = λ exp(−λt)
- E[T] = 1/λ
- Var(T) = 1/λ²

The exponential model assumes that the instantaneous risk of communicative cessation does not depend on how long the civilization has been communicating — a memoryless process. It serves as the baseline against which age-dependent hazard is tested.

**Definition 9 (Weibull Hazard Model).** The generalization to age-dependent hazard:

  h(t) = (k/η)(t/η)^{k−1}

for t > 0, with scale parameter η > 0 and shape parameter k > 0. This gives:

- S(t) = exp(−(t/η)^k)
- E[T] = η · Γ(1 + 1/k)

where Γ denotes the Euler gamma function. The shape parameter k determines the hazard profile:

- k = 1: constant hazard, recovering the exponential model with λ = 1/η
- k > 1: monotonically increasing hazard — civilizations face escalating risk with age (**late-acting filter**)
- k < 1: monotonically decreasing hazard — civilizations that survive their early period face diminishing risk (**early-acting filter**)

The Weibull model is the minimal extension of the exponential that can distinguish early-acting from late-acting hazard using a single additional parameter.

### 1.3 Observation Model

**Definition 10 (SETI Detection Fraction).** f_SETI ∈ (0, 1], the fraction of currently communicative civilizations that existing SETI programs would detect, given their spectral coverage, sky coverage, temporal coverage, and sensitivity. Under the baseline assumption of sensitivity to Kardashev Type I equivalent isotropic transmitters within approximately 100 light-years (Tarter 2001, ARA&A 39:511–548; Enriquez et al. 2017, ApJ 849:104), f_SETI is bounded above by the stellar fraction within the detection volume: f_SETI ≲ 10⁻⁷ (approximately 10⁴ stars within 100 ly of approximately 10¹¹ total). Actual f_SETI may be significantly smaller due to incomplete spectral, spatial, and temporal coverage. All constraints derived in this paper scale linearly with 1/f_SETI; smaller f_SETI weakens the constraint on communicative lifetime correspondingly.

**Definition 11 (Expected Detectable Count).** Under the assumption that civilizations emerge as a homogeneous Poisson process with rate Λ over [0, T_gal], the expected number of civilizations currently in their communicative window and detectable by SETI is:

  μ(θ) = f_SETI · Λ · ∫₀^{T_gal} S(t; θ) dt

where θ denotes the survival model parameters (θ = λ for the exponential model; θ = (k, η) for the Weibull model).

For the exponential model:

  μ(λ) = f_SETI · Λ · (1 − exp(−λ · T_gal)) / λ

When λ · T_gal ≫ 1, the steady-state approximation gives μ(λ) ≈ f_SETI · Λ / λ = f_SETI · Λ · E[T].

For the Weibull model with η ≪ T_gal:

  μ(k, η) ≈ f_SETI · Λ · η · Γ(1 + 1/k) = f_SETI · Λ · E[T]

This convergence to f_SETI · Λ · E[T] in the steady-state regime is a consequence of the renewal theorem and holds for any survival distribution with finite mean.

**Definition 12 (Censored Observation).** The observational datum is N_det = 0: zero confirmed detections of extraterrestrial communicative intelligence across 60+ years of SETI observation (Tarter 2001). Under the Poisson detection model, N_det ∼ Poisson(μ(θ)), yielding the likelihood function:

  L(θ) = P(N_det = 0 | θ) = exp(−μ(θ))

and log-likelihood:

  ℓ(θ) = −μ(θ)

The observation N_det = 0 is treated as a **censored observation** in the following precise sense: it provides an upper bound on the expected detectable count μ without resolving the underlying parameters θ individually. Zero detections does not entail that no civilizations exist — it constrains the product f_SETI · Λ · E[T] from above. This treatment is the structural departure from interpretations that equate silence with absence (P = 0). The censoring is informative: it partitions parameter space into regions consistent and inconsistent with the datum, enabling formal inference on the hazard rate.

### 1.4 Symbol Table

| Symbol | Type | Definition | Introduced |
|--------|------|-----------|------------|
| (Ω, F, P) | Standard | Probability space | Def. 1 |
| T_gal | Parameter | Galactic age, 13.6 Gyr | Def. 2 |
| N★ | Parameter | Stellar population, ≈10¹¹ | Def. 3 |
| Λ | Parameter | Emergence rate [civ·yr⁻¹] | Def. 4 |
| T | Random variable | Communicative lifetime | Def. 5 |
| S(t) | Function | Survival function, P(T > t) | Def. 6 |
| h(t) | Function | Hazard function | Def. 7 |
| f(t) | Function | Density of T, −dS/dt | Def. 7 |
| H(t) | Function | Cumulative hazard, ∫₀ᵗ h(s)ds | Def. 7 |
| λ | Parameter | Exponential hazard rate | Def. 8 |
| k | Parameter | Weibull shape | Def. 9 |
| η | Parameter | Weibull scale | Def. 9 |
| Γ | Standard | Euler gamma function | Def. 9 |
| f_SETI | Parameter | SETI detection fraction | Def. 10 |
| μ(θ) | Derived | Expected detectable count | Def. 11 |
| θ | Parameter vector | Survival model parameters | Def. 11 |
| N_det | Observed | Detection count (= 0) | Def. 12 |
| L(θ) | Function | Likelihood function | Def. 12 |
| ℓ(θ) | Function | Log-likelihood function | Def. 12 |

---

## 2. Introduction

The question of why we observe no evidence of extraterrestrial intelligence — the Fermi paradox — has generated extensive speculation but remarkably little formal analysis. The field's dominant quantitative framework, the Drake equation (Drake 1961), is not a model in the inferential sense. It is an accounting identity: a product of seven factors, most of which are unconstrained by observation, yielding an estimate of the number of currently communicating civilizations that ranges across orders of magnitude depending entirely on the analyst's priors. The structural failure of the Drake equation is threefold. First, it provides no mechanism for incorporating observational evidence — the product N = R★ · f_p · n_e · f_l · f_i · f_c · L cannot be updated on the single most informative datum available: the observed silence. Second, it treats civilizational emergence as a static product of independent probabilities rather than a process unfolding in continuous time. Third, and most critically, it conflates the rate at which civilizations emerge with the duration for which they survive. The Drake equation's final term L, the mean communicative lifetime, enters as a simple multiplicative factor indistinguishable in its effect from the emergence probability terms that precede it. A small N can result from rare emergence or rapid extinction; the equation is structurally incapable of distinguishing these two fundamentally different explanations for the silence.

Drake (1961) proposed the Drake equation to estimate the number of currently communicating civilizations by decomposing N into a product of astrophysical and biological factors, but the equation fails under the condition that its terms are empirically unconstrained and its output cannot be conditioned on the observed silence — zero confirmed detections across six decades of search. This paper introduces a survival analysis framework (Definitions 4–9) that replaces the Drake product with a hazard-rate model, formally decouples the emergence rate Λ from the communicative lifetime T, and uses N_det = 0 as a censored observation to derive constraints on the hazard rate through the likelihood function (Definition 12).

Hanson (1998) proposed the Great Filter hypothesis to explain the apparent absence of extraterrestrial civilizations, arguing that at least one step in the developmental sequence from prebiotic chemistry to galaxy-spanning civilization must be extraordinarily improbable. But the Great Filter fails under the condition that it provides no quantitative method for locating the filter within the developmental sequence. Hanson's argument establishes the existence of a filter as a logical necessity given the silence, but cannot formally distinguish early-acting filters — those that suppress civilizational emergence — from late-acting filters — those that destroy civilizations after technological maturity. The distinction is consequential: an early filter is anthropically reassuring; a late filter is not. This paper introduces the Weibull hazard model (Definition 9), whose shape parameter k formally distinguishes early-acting filters (k < 1, decreasing hazard) from late-acting filters (k > 1, increasing hazard), enabling a quantitative filter-location analysis conditioned on the SETI null result — an analysis that Hanson's framework cannot perform.

Carter (1983) proposed an anthropic argument constraining the number of "hard steps" in the emergence of intelligent observers, based on the observation that Earth's biological development timeline is comparable to the Sun's main-sequence lifetime. But Carter's framework fails under the condition that it treats the observer's own existence as the primary datum, extracting constraints on emergence probability while providing no mechanism for incorporating the additional information contained in the SETI null result. The zero-detection observation is independent of and complementary to the anthropic datum: it constrains not how likely we are to exist, but how long civilizations like us are likely to persist. This paper treats N_det = 0 as a censored datum in a formal Poisson likelihood (Definition 12), extracting survival-time information from the silence that purely anthropic arguments cannot access.

The contributions of this paper are:

1. **Reformulation.** We replace the Drake equation with a continuous-time survival analysis model (Definitions 4–9), formally decoupling the emergence rate Λ from the communicative lifetime T and defining the civilizational survival function S(t) with explicit hazard rates h(t) following the Cox (1972) framework.

2. **Derivation.** We derive maximum-likelihood constraints on the hazard rate λ from the censored observation N_det = 0 via the Poisson likelihood L(θ) = exp(−μ(θ)) (Definition 12), establishing an upper bound on mean communicative lifetime E[T] as a function of f_SETI and Λ.

3. **Filter location.** We extend the baseline exponential model to the Weibull hazard (Definition 9) to determine whether the dominant civilizational hazard is early-acting or late-acting. We show that under any parameterization consistent with the observed silence and a non-negligible emergence rate, the data are most consistent with a dominant late-stage filter — a hazard that strikes after civilizations reach technological maturity.

The paper proceeds as follows. Section 3 derives the maximum-likelihood hazard rate under the exponential model and extends the analysis to the Weibull case. Section 4 applies the derived constraints to the filter-location question, presents sensitivity analysis across the model's parameters, and subjects the framework to adversarial stress-testing against competing models. Section 5 discusses implications. Section 6 concludes.

No figures required for this section.
