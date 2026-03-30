# The Fermi Paradox as a Survival Function

## Abstract

The absence of confirmed extraterrestrial intelligence despite conditions favorable for its emergence — the Fermi paradox — has been dominated by the Drake equation, a framework that cannot incorporate observational evidence, cannot distinguish emergence scarcity from survival brevity, and has no inferential structure. This paper replaces the Drake equation with a survival analysis framework in which civilizational communicative lifetimes are modeled through hazard-rate functions and the sixty-year SETI null result — zero confirmed detections — enters as a censored observation in a Poisson likelihood. Under the exponential (constant) hazard model, the maximum-likelihood hazard rate diverges: zero detections are maximally consistent with the shortest possible communicative lifetime. The 95% confidence upper bound on mean communicative lifetime is E[T] ≤ 3.00 / (f_SETI · Λ), where f_SETI is the detection fraction of current SETI surveys and Λ is the civilizational emergence rate. Extending to the Weibull hazard model, which allows age-dependent risk, the mean-lifetime bound is invariant under the shape parameter k, but the tail structure of the survival function distinguishes early-acting hazard (k < 1, decreasing risk with civilizational age) from late-acting hazard (k > 1, increasing risk). Under early-acting hazard, a subpopulation of long-lived civilizations accumulates over galactic history, creating detection tension beyond the electromagnetic SETI window. Under late-acting hazard, civilizations cluster near the mean lifetime, producing no long-lived residual. The late-acting hazard model is therefore structurally more consistent with zero detections across all observational channels. This conclusion is conditional: it requires the emergence rate to exceed a computable threshold Λ_crit = −ln α / (f_SETI · τ), where α is the significance level (α = 0.05 for 95% confidence) and τ is a reference developmental timescale against which communicative lifetime is compared. Below this threshold, the silence is uninformative about survival. The framework reduces the Fermi paradox to a single empirical question — whether Λ exceeds Λ_crit — and derives what follows from each answer.

---

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

The paper proceeds as follows. Section 3 derives the maximum-likelihood hazard rate under the exponential model and extends the analysis to the Weibull case. Section 4 applies the derived constraints to the filter-location question, presents sensitivity analysis across the model's parameters, and subjects the framework to adversarial stress-testing against competing models. Section 5 positions this work within the existing literature. Section 6 discusses implications. Section 7 concludes.

---

## 3. Core Derivations

**Notation.** This section introduces one standard statistical quantity not defined in Section 1: α ∈ (0, 1), the significance level for hypothesis testing, with corresponding confidence level 1 − α. Unless otherwise stated, α = 0.05 (95% confidence). All other symbols are as defined in Section 1.

### 3.1 Maximum Likelihood Under Exponential Hazard

**Lemma 1 (Monotonicity of Expected Detectable Count).** Let μ(λ) = f_SETI · Λ · (1 − exp(−λ · T_gal)) / λ as in Definition 11. Then dμ/dλ < 0 for all λ > 0. That is, the expected detectable count is strictly decreasing in the hazard rate.

*Proof.*

Step 1. Define g(λ) = (1 − exp(−λ · T_gal)) / λ, so that μ(λ) = f_SETI · Λ · g(λ). Since f_SETI > 0 and Λ > 0, it suffices to show dg/dλ < 0.

Step 2. Differentiate:

  dg/dλ = [λ · T_gal · exp(−λ · T_gal) − (1 − exp(−λ · T_gal))] / λ²
         = [(λ · T_gal + 1) · exp(−λ · T_gal) − 1] / λ²

Step 3. Substitute u = λ · T_gal > 0. Define φ(u) = (u + 1) · exp(−u) − 1. The numerator of dg/dλ equals φ(λ · T_gal), so dg/dλ = φ(u) / λ².

Step 4. Evaluate at the boundary: φ(0) = (0 + 1) · 1 − 1 = 0.

Step 5. Differentiate φ: φ'(u) = exp(−u) − (u + 1) · exp(−u) = −u · exp(−u) < 0 for all u > 0.

Step 6. Since φ is continuous, φ(0) = 0, and φ'(u) < 0 for all u > 0, it follows that φ(u) < 0 for all u > 0.

Step 7. Since λ² > 0 and φ(u) < 0 for u = λ · T_gal > 0, we have dg/dλ = φ(u)/λ² < 0 for all λ > 0. Therefore dμ/dλ = f_SETI · Λ · dg/dλ < 0. ∎


**Theorem 1 (Maximum Likelihood Hazard Rate).** Suppose:

(H1) N_det ∼ Poisson(μ(λ)) with μ(λ) = f_SETI · Λ · (1 − exp(−λ · T_gal)) / λ (Definition 11, exponential model),
(H2) f_SETI > 0, Λ > 0, T_gal > 0,
(H3) N_det = 0.

Then the log-likelihood ℓ(λ) = −μ(λ) is strictly increasing on (0, ∞). The supremum sup_{λ > 0} ℓ(λ) = 0 is not attained at any finite λ. The maximum likelihood estimate of the mean communicative lifetime is E[T]_ML → 0.

*Proof.*

Step 1. By the Poisson probability mass function, P(N_det = 0 | μ) = exp(−μ). The log-likelihood is:

  ℓ(λ) = ln P(N_det = 0 | λ) = ln exp(−μ(λ)) = −μ(λ)

Step 2. Differentiate: dℓ/dλ = −dμ/dλ. By Lemma 1, dμ/dλ < 0, hence dℓ/dλ > 0 for all λ > 0. The log-likelihood is strictly increasing on (0, ∞).

Step 3. Evaluate the limits. As λ → ∞: since exp(−λ · T_gal) → 0, we have μ(λ) = f_SETI · Λ · (1 − exp(−λ · T_gal))/λ → f_SETI · Λ / λ → 0. Therefore ℓ(λ) = −μ(λ) → 0⁻.

Step 4. As λ → 0⁺: by L'Hôpital's rule, (1 − exp(−λ · T_gal))/λ → T_gal, so μ(λ) → f_SETI · Λ · T_gal > 0. Therefore ℓ(λ) → −f_SETI · Λ · T_gal < 0.

Step 5. The function ℓ is strictly increasing on (0, ∞) with lim_{λ → ∞} ℓ(λ) = 0. The supremum equals 0 and is not attained at any finite λ. No finite maximizer exists.

Step 6. Since E[T] = 1/λ under the exponential model, the MLE-implied mean lifetime satisfies E[T]_ML = 1/λ̂_ML → 0 as the likelihood-maximizing sequence λ̂_ML → ∞. ∎

**Remark.** Theorem 1 states that zero detections are maximally consistent with the highest possible hazard rate — equivalently, the shortest possible communicative lifetime. No finite hazard rate is favored over a larger one. This degeneracy of the MLE motivates the confidence-bound approach: rather than a point estimate, we derive the region of hazard rates not rejected by the data.


**Theorem 2 (Confidence Bound on Expected Detectable Count).** Let N_det ∼ Poisson(μ) with μ ≥ 0, and suppose N_det = 0 is observed. For any significance level α ∈ (0, 1), the 100(1 − α)% upper confidence bound on μ is:

  μ_upper(α) = −ln α

*Proof.*

Step 1. For a candidate parameter value μ₀ ≥ 0, the p-value for testing H₀: μ = μ₀ against the observation N_det = 0 is:

  p(μ₀) = P(N_det ≤ 0 | μ = μ₀) = P(N_det = 0 | μ₀) = exp(−μ₀)

The second equality holds because N_det is non-negative and integer-valued under the Poisson model, so P(N_det ≤ 0) = P(N_det = 0).

Step 2. The 100(1 − α)% confidence set consists of all μ₀ for which the observation is not rejected at level α:

  p(μ₀) ≥ α  ⟺  exp(−μ₀) ≥ α  ⟺  μ₀ ≤ −ln α

Step 3. The confidence interval is [0, −ln α], with upper endpoint μ_upper(α) = −ln α.

Numerical evaluation: μ_upper(0.05) = −ln(0.05) ≈ 2.996; μ_upper(0.01) = −ln(0.01) ≈ 4.605; μ_upper(0.10) = −ln(0.10) ≈ 2.303. ∎


**Corollary 1 (Upper Bound on Mean Communicative Lifetime).** Under hypotheses (H1)–(H3) of Theorem 1, and the steady-state approximation (valid when E[T] ≪ T_gal; see Lemma 2), the observation N_det = 0 at significance level α implies:

  E[T] ≤ −ln α / (f_SETI · Λ)

*Proof.*

Step 1. In the steady-state regime, μ(λ) ≈ f_SETI · Λ · E[T] (Definition 11, steady-state form: μ ≈ f_SETI · Λ / λ = f_SETI · Λ · E[T], valid when λ · T_gal ≫ 1).

Step 2. By Theorem 2, μ ≤ −ln α at confidence level 1 − α.

Step 3. Combining Steps 1 and 2: f_SETI · Λ · E[T] ≤ −ln α.

Step 4. Since f_SETI > 0 and Λ > 0, divide both sides: E[T] ≤ −ln α / (f_SETI · Λ). ∎

**Remark.** The bound is self-consistent: if E[T] is small relative to T_gal (as the bound implies for any non-negligible Λ), then λ · T_gal = T_gal/E[T] ≫ 1, and the steady-state approximation is valid. The bound scales inversely with both f_SETI and Λ — the more frequently civilizations emerge and the more thoroughly SETI surveys the sky, the shorter each civilization's communicative window must be to produce zero detections.


**Lemma 2 (Steady-State Approximation Error).** Let S(t; θ) be any survival function with finite mean E[T] = ∫₀^∞ S(t; θ) dt. Under the detection model of Definition 11:

  μ(θ) = f_SETI · Λ · (E[T] − R(θ))

where R(θ) = ∫_{T_gal}^∞ S(t; θ) dt is the tail remainder. For the exponential model, R(λ) = exp(−λ · T_gal) / λ, and the relative error of the steady-state approximation μ ≈ f_SETI · Λ · E[T] is:

  |μ − f_SETI · Λ · E[T]| / (f_SETI · Λ · E[T]) = R(λ) / E[T] = exp(−λ · T_gal)

*Proof.*

Step 1. By Definition 11, μ = f_SETI · Λ · ∫₀^{T_gal} S(t) dt.

Step 2. Decompose the mean: E[T] = ∫₀^∞ S(t) dt = ∫₀^{T_gal} S(t) dt + ∫_{T_gal}^∞ S(t) dt. Therefore ∫₀^{T_gal} S(t) dt = E[T] − R(θ).

Step 3. Substituting: μ = f_SETI · Λ · (E[T] − R(θ)).

Step 4. For the exponential model: R(λ) = ∫_{T_gal}^∞ exp(−λt) dt = exp(−λ · T_gal) / λ. Since E[T] = 1/λ, the relative error is R(λ)/E[T] = exp(−λ · T_gal).

Step 5. When λ · T_gal ≫ 1 (equivalently E[T] ≪ T_gal), exp(−λ · T_gal) is negligible. For λ · T_gal = 10: relative error ≈ 4.5 × 10⁻⁵. For λ · T_gal = 100: relative error ≈ 3.7 × 10⁻⁴⁴. ∎


### 3.2 Weibull Extension: Age-Dependent Hazard

**Theorem 3 (Weibull Admissible Region).** Under the Weibull hazard model (Definition 9) with:

(H1) N_det ∼ Poisson(μ(k, η)) where μ(k, η) = f_SETI · Λ · η · Γ(1 + 1/k) in steady state (Definition 11 with E[T] = η · Γ(1 + 1/k) from Definition 9),
(H2) N_det = 0,
(H3) f_SETI > 0, Λ > 0,

the set of Weibull parameters consistent with the observation at confidence level 1 − α is:

  A(α, Λ) = {(k, η) ∈ (0, ∞)² : η · Γ(1 + 1/k) ≤ −ln α / (f_SETI · Λ)}

*Proof.*

Step 1. In steady state, μ(k, η) = f_SETI · Λ · E[T] = f_SETI · Λ · η · Γ(1 + 1/k). This follows from Definition 11 (steady-state form) and Definition 9 (E[T] = η · Γ(1 + 1/k) for the Weibull distribution).

Step 2. By Theorem 2, N_det = 0 at significance level α requires μ ≤ −ln α.

Step 3. Combining: f_SETI · Λ · η · Γ(1 + 1/k) ≤ −ln α.

Step 4. Rearranging: η · Γ(1 + 1/k) ≤ −ln α / (f_SETI · Λ), which defines A(α, Λ). ∎


**Corollary 2 (Mean Lifetime Invariance Under Shape Variation).** The upper bound on E[T] derived from N_det = 0 is:

  E[T] ≤ −ln α / (f_SETI · Λ)

regardless of whether k < 1 (decreasing hazard, early-acting filter), k = 1 (constant hazard, exponential model), or k > 1 (increasing hazard, late-acting filter). A single Poisson count of zero constrains the first moment of the survival distribution but does not resolve the hazard shape parameter k.

*Proof.* The admissible set A(α, Λ) in Theorem 3 constrains the product η · Γ(1 + 1/k) = E[T]. The bound on E[T] is −ln α / (f_SETI · Λ), independent of k. Different (k, η) pairs trace the same constraint surface in E[T] regardless of how E[T] decomposes into shape and scale. ∎

**Remark.** Corollary 2 establishes a fundamental limitation: a single Poisson count cannot resolve the two-parameter Weibull model. The SETI null result constrains the mean communicative lifetime but cannot by itself determine whether the hazard is early-acting or late-acting. Distinguishing early from late filter requires either additional observational constraints or structural arguments about the relationship between E[T] and the timescales of civilizational development. Section 3.3 develops the latter.


**Theorem 4 (Tail Ordering by Hazard Shape).** Let S₁(t) = exp(−(t/η₁)^{k₁}) and S₂(t) = exp(−(t/η₂)^{k₂}) be two Weibull survival functions (Definition 9) with:

(H1) 0 < k₁ < k₂,
(H2) η₁ · Γ(1 + 1/k₁) = η₂ · Γ(1 + 1/k₂) (equal mean lifetimes).

Then there exists t* > 0 such that S₁(t) > S₂(t) for all t > t*. The survival function with lower shape parameter has a strictly heavier right tail.

*Proof.*

Step 1. Since S₁ and S₂ are distinct continuous functions with the same integral (equal means: ∫₀^∞ S₁(t) dt = ∫₀^∞ S₂(t) dt), there exists at least one crossing point. That is, S₁ − S₂ changes sign at least once on (0, ∞).

Step 2. Consider the log-survival ratio:

  ln(S₁(t) / S₂(t)) = −(t/η₁)^{k₁} + (t/η₂)^{k₂} = (t/η₂)^{k₂} − (t/η₁)^{k₁}

Step 3. As t → ∞, the term (t/η₂)^{k₂} grows as t^{k₂} and (t/η₁)^{k₁} grows as t^{k₁}. Since k₂ > k₁ > 0, the higher-exponent term dominates:

  lim_{t → ∞} [(t/η₂)^{k₂} − (t/η₁)^{k₁}] = +∞

This holds because for any constants a₂ = 1/η₂ > 0, a₁ = 1/η₁ > 0 and exponents k₂ > k₁ > 0, (a₂t)^{k₂} / (a₁t)^{k₁} = (a₂^{k₂}/a₁^{k₁}) · t^{k₂ − k₁} → ∞.

Step 4. Since ln(S₁(t)/S₂(t)) → +∞, we have S₁(t)/S₂(t) → ∞. Both S₁(t) and S₂(t) tend to 0, but S₂(t) decays strictly faster. There exists t* such that S₁(t) > S₂(t) for all t > t*.

Step 5. By Step 1, S₁ and S₂ cross, so S₂(t) > S₁(t) for some t < t*. This is consistent: the higher-k distribution decays slower initially (lower early hazard when k₂ > 1) but faster eventually. ∎

**Interpretation.** At equal mean lifetime, a Weibull model with smaller k (early-acting hazard, decreasing with civilizational age) produces a heavier right tail — more long-lived survivors — than a model with larger k (late-acting hazard, increasing with age). Early-acting hazard concentrates risk at young ages, permitting a tail of resilient long-lived civilizations. Late-acting hazard concentrates risk at older ages, ensuring that essentially no civilizations substantially exceed the mean lifetime. This structural distinction is independent of the E[T] constraint from Corollary 1 and becomes observationally consequential in Section 4.


### 3.3 Filter Location

**Theorem 5 (Late-Filter Threshold).** Let τ > 0 be an arbitrary reference timescale. Under:

(H1) N_det ∼ Poisson(μ) with μ = f_SETI · Λ · E[T] in steady state (Definition 11),
(H2) f_SETI > 0, Λ > 0,
(H3) N_det = 0,
(H4) The steady-state approximation is valid (E[T] ≪ T_gal; Lemma 2),

the 100(1 − α)% confidence upper bound on E[T] satisfies E[T]_upper < τ if and only if:

  Λ > Λ_crit(τ, α) ≡ −ln α / (f_SETI · τ)

When Λ exceeds this critical threshold, all hazard rates consistent with N_det = 0 at significance level α give E[T] < τ.

*Proof.*

Step 1. By Corollary 1, E[T] ≤ E[T]_upper(Λ, α) = −ln α / (f_SETI · Λ) at confidence level 1 − α.

Step 2. [Forward direction] Suppose Λ > −ln α / (f_SETI · τ). Then:

  E[T]_upper = −ln α / (f_SETI · Λ) < −ln α / (f_SETI · (−ln α / (f_SETI · τ)))

The right-hand side simplifies: −ln α / (f_SETI · (−ln α / (f_SETI · τ))) = −ln α · f_SETI · τ / (f_SETI · (−ln α)) = τ.

Therefore E[T]_upper < τ, and since E[T] ≤ E[T]_upper, we have E[T] < τ.

Step 3. [Converse] Suppose Λ ≤ −ln α / (f_SETI · τ). Then:

  E[T]_upper = −ln α / (f_SETI · Λ) ≥ −ln α / (f_SETI · (−ln α / (f_SETI · τ))) = τ

The upper bound permits E[T] ≥ τ. The observation N_det = 0 does not force E[T] < τ at significance level α. ∎


**Corollary 3 (Properties of the Critical Emergence Rate).** The function Λ_crit(τ, α) = −ln α / (f_SETI · τ) satisfies:

(a) ∂Λ_crit/∂τ = −(−ln α) / (f_SETI · τ²) < 0. Longer reference timescales require lower emergence rates to trigger the lifetime constraint.

(b) ∂Λ_crit/∂α = −1 / (α · f_SETI · τ) < 0 for α ∈ (0, 1), since ∂(−ln α)/∂α = −1/α. Stricter significance levels (smaller α) require higher emergence rates.

(c) Λ_crit is inversely proportional to f_SETI. Reduced SETI sensitivity weakens the constraint proportionally.

*Proof.* Each follows from direct differentiation of Λ_crit = −ln α / (f_SETI · τ). ∎


**Theorem 6 (Hazard Shape and Survivor Accumulation).** Suppose Λ > Λ_crit(τ, α) so that E[T] < τ (Theorem 5). Under the Weibull model (Definition 9), consider two parameter pairs (k₁, η₁) and (k₂, η₂) in A(α, Λ) with the same mean E[T] and k₁ < k₂. The expected number of civilizations that have emerged over [0, T_gal] and survive beyond age τ is:

  N_surv(τ; k, η) = Λ · T_gal · S(τ; k, η) = Λ · T_gal · exp(−(τ/η)^k)

For τ > t* (where t* is the crossing point from Theorem 4):

  N_surv(τ; k₁, η₁) > N_surv(τ; k₂, η₂)

*Proof.*

Step 1. The number of civilizations that emerged over [0, T_gal] is approximately Λ · T_gal (expected count of a Poisson process with rate Λ over interval T_gal).

Step 2. Each civilization survives beyond age τ independently with probability S(τ; k, η) = exp(−(τ/η)^k) (Definition 9).

Step 3. The expected number surviving beyond age τ is N_surv(τ) = Λ · T_gal · S(τ).

Step 4. By Theorem 4, S₁(τ) > S₂(τ) for all τ > t* when k₁ < k₂ and means are equal. Since Λ · T_gal > 0, the ordering is preserved: N_surv(τ; k₁, η₁) > N_surv(τ; k₂, η₂). ∎

**Interpretation.** Under a decreasing-hazard model (k < 1), more civilizations survive to advanced ages despite having the same mean lifetime. These long-lived civilizations are present in the galaxy for extended periods, contributing to the detectable population over long timescales. Under an increasing-hazard model (k > 1), civilizations cluster near the mean lifetime and few survive much beyond it. The combination of short E[T] (forced by N_det = 0 through Corollary 1) with the absence of even a single long-lived detectable civilization (N_det = 0) creates stronger tension under k < 1 than under k ≥ 1. This structural distinction, while not resolvable from the Poisson count alone (Corollary 2), becomes a discriminating factor when combined with auxiliary constraints on civilizational development timescales (developed in Section 4).


### 3.4 Summary of Proof Chain

The derivations in this section establish the following logical chain:

1. **Lemma 1** → The expected detectable count μ decreases with hazard rate λ.
2. **Theorem 1** → The MLE of λ from N_det = 0 diverges; the data maximally favor the shortest possible communicative lifetime.
3. **Theorem 2** → The Poisson null observation yields a finite upper confidence bound μ_upper = −ln α.
4. **Corollary 1** → This bound translates to E[T] ≤ −ln α / (f_SETI · Λ) under the steady-state approximation (justified by **Lemma 2**).
5. **Theorem 3** → The Weibull generalization produces the same E[T] constraint, defining an admissible region in (k, η) space.
6. **Corollary 2** → The constraint on E[T] is invariant under the hazard shape k: a single null count cannot resolve whether the hazard is early- or late-acting.
7. **Theorem 4** → At equal E[T], lower k produces heavier survival tails — more long-lived civilizations.
8. **Theorem 5** → For any reference timescale τ, the data force E[T] < τ if and only if the emergence rate exceeds a computable threshold Λ_crit(τ, α).
9. **Theorem 6** → When E[T] < τ, the expected number of civilizations surviving beyond age τ is strictly larger under decreasing hazard (k < 1) than increasing hazard (k > 1).

The application of these results to the filter-location question — including numerical evaluation of Λ_crit for physically meaningful timescales, sensitivity analysis, and competing-model comparisons — is developed in Section 4.

[Figure 1: Log-Likelihood Under Exponential Hazard]

```python
# Figure 1: Log-likelihood ℓ(λ) = −μ(λ) under exponential hazard model
import matplotlib.pyplot as plt
import numpy as np

f_SETI = 1e-7
Lambda = 1e-2  # emergence rate, civilizations per year
T_gal = 13.6e9  # years

lambda_vals = np.logspace(-12, -4, 1000)
mu_vals = f_SETI * Lambda * (1 - np.exp(-lambda_vals * T_gal)) / lambda_vals
ell_vals = -mu_vals

fig, ax = plt.subplots(1, 1, figsize=(8, 5))
ax.semilogx(lambda_vals, ell_vals, 'k-', linewidth=2)
ax.axhline(y=0, color='gray', linestyle='--', linewidth=0.5)
ax.axhline(y=-(-np.log(0.05)), color='red', linestyle='--', linewidth=1,
           label=r'$\ell = -\mu_{\rm upper}$ ($\alpha = 0.05$, $\mu_{\rm upper} \approx 3.0$)')
ax.set_xlabel(r'Hazard rate $\lambda$ [yr$^{-1}$]', fontsize=12)
ax.set_ylabel(r'Log-likelihood $\ell(\lambda)$', fontsize=12)
ax.set_title(r'Log-likelihood under exponential hazard, $N_{\rm det} = 0$'
             '\n' r'($f_{\rm SETI} = 10^{-7}$, $\Lambda = 10^{-2}$ yr$^{-1}$)',
             fontsize=12)
ax.legend(fontsize=10, loc='lower right')
ax.set_xlim(lambda_vals[0], lambda_vals[-1])
plt.tight_layout()
plt.savefig('figures/figure_1.pdf', dpi=300, bbox_inches='tight')
```

[Figure 2: Weibull Survival Functions at Equal Mean Lifetime]

```python
# Figure 2: Weibull survival functions for k = 0.5, 1.0, 2.0 at equal E[T]
import matplotlib.pyplot as plt
import numpy as np
from scipy.special import gamma

E_T = 1.0  # normalized mean lifetime

k_values = [0.5, 1.0, 2.0]
labels = [r'$k = 0.5$ (decreasing hazard — early filter)',
          r'$k = 1.0$ (constant hazard — exponential)',
          r'$k = 2.0$ (increasing hazard — late filter)']
colors = ['blue', 'black', 'red']
styles = ['--', '-', '-.']

t = np.linspace(0, 5 * E_T, 1000)

fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(14, 5))

# Panel A: Survival functions
for k, label, color, style in zip(k_values, labels, colors, styles):
    eta = E_T / gamma(1 + 1.0/k)
    S = np.exp(-(t / eta)**k)
    ax1.plot(t / E_T, S, color=color, linestyle=style, linewidth=2, label=label)

ax1.set_xlabel(r'$t\, /\, E[T]$', fontsize=12)
ax1.set_ylabel(r'$S(t)$', fontsize=12)
ax1.set_title('(a) Survival functions', fontsize=12)
ax1.legend(fontsize=9, loc='upper right')
ax1.set_xlim(0, 5)
ax1.set_ylim(0, 1.05)
ax1.axvline(x=1.0, color='gray', linestyle=':', linewidth=0.5)

# Panel B: Hazard functions
t_hz = np.linspace(0.01 * E_T, 5 * E_T, 1000)
for k, label, color, style in zip(k_values, labels, colors, styles):
    eta = E_T / gamma(1 + 1.0/k)
    h = (k / eta) * (t_hz / eta)**(k - 1)
    ax2.plot(t_hz / E_T, h * E_T, color=color, linestyle=style, linewidth=2,
             label=label)

ax2.set_xlabel(r'$t\, /\, E[T]$', fontsize=12)
ax2.set_ylabel(r'$h(t) \cdot E[T]$  (dimensionless)', fontsize=12)
ax2.set_title('(b) Hazard functions', fontsize=12)
ax2.legend(fontsize=9, loc='upper left')
ax2.set_xlim(0, 5)
ax2.set_ylim(0, 5)
ax2.axvline(x=1.0, color='gray', linestyle=':', linewidth=0.5)

plt.tight_layout()
plt.savefig('figures/figure_2.pdf', dpi=300, bbox_inches='tight')
```

---

## 4. Application and Boundary Conditions

**Notation.** This section introduces no new symbols for the core analysis (Sections 4.1–4.3). Sections 4.4–4.5, which analyze assumption violations and extensions, introduce auxiliary notation as needed, flagged at first use.

### 4.1 Numerical Evaluation of the Lifetime Bound

By Corollary 1, the observation N_det = 0 constrains the mean communicative lifetime at 95% confidence (α = 0.05):

  E[T] ≤ −ln(0.05) / (f_SETI · Λ) ≈ 3.00 / (f_SETI · Λ)

This bound depends on the product f_SETI · Λ — the effective rate at which detectable civilizations emerge per unit time. Table 1 evaluates E[T]_upper across the plausible range of f_SETI and Λ.

**Table 1: Upper bound on mean communicative lifetime (95% confidence, Corollary 1)**

| Λ (civ yr⁻¹) | f_SETI | f_SETI · Λ (yr⁻¹) | E[T]_upper (yr) | E[T]_upper / T_gal |
|---------------|--------|---------------------|------------------|---------------------|
| 10⁻⁴          | 10⁻⁷   | 10⁻¹¹               | 3.0 × 10¹¹       | 22                  |
| 10⁻²          | 10⁻⁷   | 10⁻⁹                | 3.0 × 10⁹        | 0.22                |
| 10⁻¹          | 10⁻⁷   | 10⁻⁸                | 3.0 × 10⁸        | 0.022               |
| 1             | 10⁻⁷   | 10⁻⁷                | 3.0 × 10⁷        | 2.2 × 10⁻³          |
| 10²           | 10⁻⁷   | 10⁻⁵                | 3.0 × 10⁵        | 2.2 × 10⁻⁵          |
| 10⁻²          | 10⁻⁵   | 10⁻⁷                | 3.0 × 10⁷        | 2.2 × 10⁻³          |
| 1             | 10⁻⁵   | 10⁻⁵                | 3.0 × 10⁵        | 2.2 × 10⁻⁵          |

All values follow from a single application of Corollary 1 with μ_upper(0.05) = 2.996 (Theorem 2). No assumptions beyond the Poisson detection model (Definition 12), the steady-state approximation (Lemma 2), and the frozen parameters (Definitions 2–4, 10) are required.

The bound becomes astrophysically constraining — E[T]_upper < T_gal — when f_SETI · Λ exceeds the threshold:

  (f_SETI · Λ)_min = −ln(0.05) / T_gal ≈ 3.00 / (13.6 × 10⁹) ≈ 2.2 × 10⁻¹⁰ yr⁻¹

For f_SETI = 10⁻⁷ (Definition 10), this requires Λ > 2.2 × 10⁻³ civ yr⁻¹ — approximately one civilization emerging every 450 years across the galaxy. For f_SETI = 10⁻⁸, the threshold rises to Λ > 2.2 × 10⁻² civ yr⁻¹.

### 4.2 Filter Location Under Non-Negligible Emergence

The constraint in Section 4.1 bounds E[T] from above but does not by itself locate the dominant civilizational hazard in time. This section applies Theorems 4, 5, and 6 to establish the filter-location result.

**Step 1: Critical emergence rate threshold.** By Theorem 5, for any reference timescale τ > 0, the observation N_det = 0 forces E[T] < τ at 95% confidence if and only if Λ > Λ_crit(τ, 0.05) = 3.00 / (f_SETI · τ). Table 2 evaluates Λ_crit for timescales relevant to the filter question.

**Table 2: Critical emergence rates for reference timescales (f_SETI = 10⁻⁷, α = 0.05)**

| τ (yr) | Physical interpretation | Λ_crit (civ yr⁻¹) | 1/Λ_crit (yr per civ) |
|--------|------------------------|---------------------|------------------------|
| 10¹⁰   | ≈ T_gal                | 3.0 × 10⁻³          | 333                    |
| 10⁹    | Stellar main-sequence  | 3.0 × 10⁻²          | 33                     |
| 10⁸    | Complex life evolution | 3.0 × 10⁻¹          | 3.3                    |
| 10⁷    | Post-Cambrian era      | 3.0                  | 0.33                   |
| 10⁶    | Quaternary period      | 30                   | 0.033                  |
| 10⁵    | Species lifetime       | 300                  | 3.3 × 10⁻³             |

By Corollary 3(a), Λ_crit decreases with τ: longer reference timescales require lower emergence rates to trigger the constraint. If Λ > 3 × 10⁻³ civ yr⁻¹ (one civilization per 333 years), the data force E[T] below galactic age. If Λ > 0.3 civ yr⁻¹ (one per 3.3 years), the data force E[T] below the timescale for complex life evolution on Earth.

**Step 2: Hazard shape and the survival tail.** By Corollary 2, the upper bound on E[T] is invariant under the Weibull shape parameter k: the single Poisson count N_det = 0 constrains E[T] = η · Γ(1 + 1/k) but cannot resolve whether k < 1 (early-acting hazard) or k > 1 (late-acting hazard). The two scenarios are distinguished by their structural implications.

By Theorem 4, among Weibull survival functions with equal E[T], those with smaller k have strictly heavier right tails — more probability mass beyond any sufficiently large time t*. By Theorem 6, the expected number of civilizations surviving beyond any reference age τ > t* is strictly larger under k < 1 than under k > 1:

  N_surv(τ; k₁, η₁) > N_surv(τ; k₂, η₂)   for k₁ < k₂ and equal E[T]

**Step 3: The consistency argument.** Consider two Weibull parameterizations consistent with N_det = 0 at the same E[T], with Λ > Λ_crit so that E[T] is constrained to be short:

(i) k = 0.5 (early-acting hazard, decreasing with age): Most civilizations perish within a small fraction of E[T] after emergence. Survivors become increasingly resilient with age. By Theorem 4, the survival function has a heavy right tail. By Theorem 6, a subpopulation of long-lived civilizations accumulates over galactic history, each present for durations ≫ E[T] — potentially exceeding 10⁹ yr. These civilizations are present in the galaxy for timescales during which their cumulative energy consumption, spatial footprint, and electromagnetic signature grow monotonically. Their non-detection requires that every such long-lived civilization independently evades all detection channels, including those not captured by f_SETI as defined in Definition 10.

(ii) k = 2 (late-acting hazard, increasing with age): Hazard grows with civilizational age. Civilizations cluster near E[T] in communicative duration. By Theorem 4, the survival function has a light right tail. Essentially no civilization survives more than a few multiples of E[T]. The galaxy's communicative population at any instant consists only of recently emerged civilizations, each present for a duration of order E[T]. Zero detections arise from the short individual exposure time of each civilization relative to SETI's coverage.

Both parameterizations yield the same μ = f_SETI · Λ · E[T] (Corollary 2) and are therefore equally consistent with N_det = 0 under the baseline Poisson detection model. The scenarios diverge in the following respect: under (i), the accumulation of long-lived civilizations over T_gal = 13.6 Gyr implies a persistent subpopulation whose detectability extends beyond the scope of electromagnetic SETI — through energy-consumption signatures, stellar engineering, or colonization artifacts — while under (ii), no such subpopulation forms.

The observation is not merely N_det = 0 for electromagnetic SETI. It is the absence of any confirmed signature of extraterrestrial technology across all observational channels over the entire history of modern astronomy. This broader null result creates stronger tension with the heavy-tail scenario (k < 1, early-acting hazard) than with the light-tail scenario (k > 1, late-acting hazard), because the long-lived subpopulation predicted by k < 1 would produce signatures across channels not modeled by f_SETI.

**Result.** The late-filter conclusion follows from the conjunction of two elements:

**(A) Formal constraint (Theorems 1–5):** Under exponential or Weibull hazard with non-negligible emergence rate Λ > Λ_crit(τ, α), the observation N_det = 0 bounds E[T] below physically meaningful timescales.

**(B) Structural consistency (Theorems 4, 6):** Among survival models consistent with the formal constraint, late-acting hazard (k > 1) produces a transient population structure — civilizations emerging and ceasing on timescales ≪ T_gal with no long-lived residual — consistent with zero detections across all channels. Early-acting hazard (k < 1) produces an accumulating subpopulation of long-lived civilizations whose extended presence creates detection tension beyond the baseline Poisson model.

The combination of (A) and (B) identifies late-acting hazard — a post-technological filter that intensifies with civilizational age — as the interpretation most consistent with the SETI null result under non-negligible emergence. This result is derived from the mathematical structure of the Weibull survival model (Theorems 4–6) applied to the constraint from the Poisson likelihood (Theorems 1–3). It is conditional on Λ > Λ_crit and does not refute the alternative hypothesis that Λ is negligibly small.

### 4.3 Sensitivity Analysis

Table 3 evaluates the robustness of the lifetime bound (Corollary 1) and the late-filter conclusion to perturbations of each model parameter by at least one order of magnitude in each direction.

**Table 3: Sensitivity analysis**

| Parameter | Baseline | 10× Lower | 10× Higher | Effect on E[T]_upper | Conclusion holds? | Notes |
|-----------|----------|-----------|------------|----------------------|-------------------|-------|
| f_SETI | 10⁻⁷ | 10⁻⁸ | 10⁻⁶ | 10× higher / 10× lower | YES | Linear scaling; bound weakens but structure unchanged |
| Λ | 10⁻² yr⁻¹ | 10⁻³ yr⁻¹ | 10⁻¹ yr⁻¹ | 10× higher / 10× lower | YES at baseline; PARTIAL at 10⁻³ | At Λ = 10⁻³, E[T]_upper ≈ 2.2 T_gal — marginal constraint |
| T_gal | 13.6 Gyr | 1.36 Gyr | 136 Gyr | Negligible | YES | Enters only via Lemma 2; relative error < 10⁻⁴ for E[T] < T_gal/10 |
| α | 0.05 | 0.005 | 0.5 | 1.77× higher / 4.3× lower | YES | −ln(0.005) = 5.30; −ln(0.5) = 0.69; sub-linear scaling |
| k (Weibull) | 1 | 0.5 | 2.0 | None (Corollary 2) | YES | E[T] bound independent of k; only structural interpretation changes |

The E[T] bound is structurally robust: it scales as (f_SETI · Λ)⁻¹ and is insensitive to T_gal (Lemma 2) and to the Weibull shape k (Corollary 2). The conclusion degrades only when f_SETI · Λ falls below (f_SETI · Λ)_min ≈ 2.2 × 10⁻¹⁰ yr⁻¹, at which point the bound exceeds T_gal and becomes vacuous.

The single parameter combination to which the conclusion is vulnerable is f_SETI · Λ. This vulnerability is not a defect; it reflects the fundamental degeneracy identified in Corollary 1: the observation constrains the product f_SETI · Λ · E[T], not any factor individually. Breaking this degeneracy requires an independent estimate of Λ (from astrobiological surveys) or of f_SETI (from SETI sensitivity modeling). The model correctly identifies the bottleneck for further progress.

### 4.4 Boundary Conditions

#### 4.4.1 Natural Enemy: The Rare Emergence Objection

The strongest objection to the late-filter conclusion is that Λ is negligibly small: civilizations emerge so rarely that the galaxy has hosted at most a handful over its entire history, rendering the silence uninformative about communicative lifetime. This is the Rare Earth hypothesis (Ward & Brownlee 2000, *Rare Earth: Why Complex Life Is Uncommon in the Universe*, Copernicus Books), formalized in the survival framework as Λ < Λ_crit(τ, α) for all timescales τ of interest.

Under rare emergence, the bound E[T] ≤ −ln α / (f_SETI · Λ) exceeds T_gal, the observation N_det = 0 carries no information about survival time, and the filter-location analysis of Section 4.2 does not apply. This is the formal boundary of the paper's central claim.

**Why the rare emergence objection does not invalidate the result.** Theorem 5 states the late-filter conclusion as a biconditional: E[T] < τ if and only if Λ > Λ_crit(τ, α). The theorem is valid for all Λ > 0. When Λ ≤ Λ_crit, the antecedent of the conditional fails — the theorem makes no claim about E[T]. The paper's result is immune to the rare emergence objection by construction: it does not assert that Λ is large; it derives what follows if Λ is non-negligible.

**Where the boundary lies.** For f_SETI = 10⁻⁷ and α = 0.05, the late-filter conclusion requires Λ > 3 × 10⁻³ civ yr⁻¹ to force E[T] below galactic age (Table 2). This threshold corresponds to one new communicative civilization per ~330 years across ~10¹¹ stars — at the optimistic end of published estimates but not extreme.

**The partition.** Under this framework, the Fermi paradox admits exactly two mutually exclusive resolutions at confidence level 1 − α:

(I) **Rare emergence (Λ ≤ Λ_crit):** The silence reflects the scarcity of civilizations. E[T] is unconstrained by the data. No conclusion about filter location is possible from the SETI null result alone.

(II) **Late filter (Λ > Λ_crit):** The silence reflects the brevity of communicative windows. E[T] < τ at confidence 1 − α. Late-acting hazard (k > 1) is structurally favored by the argument of Section 4.2.

The framework reduces the Fermi paradox to a single empirical question: whether Λ exceeds Λ_crit. It does not answer this question. It establishes what follows from each answer.

#### 4.4.2 Assumption Violations

The following analysis considers what happens when each model assumption is relaxed. Auxiliary notation introduced for generalization is flagged at first use.

**A1. Poisson emergence (Definition 12).** If civilizational emergence is non-Poisson — for example, clustered due to correlated star-formation episodes — the zero-count probability changes. Let P₀(μ) denote the zero-count probability of the alternative counting distribution with mean μ [new symbol, used only in this subsection]. The 95% upper bound on μ from N_det = 0 becomes μ_upper = −ln P₀(μ_upper), solved implicitly. For over-dispersed distributions (variance > mean), P₀(μ) > exp(−μ) for the same mean, so μ_upper increases: the bound on E[T] weakens. For under-dispersed distributions, P₀(μ) < exp(−μ), so the bound tightens. Correlated emergence (the physically motivated direction) produces over-dispersion. Quantitatively, for a Negative Binomial model with dispersion parameter r, P₀(μ) = (1 + μ/r)⁻ʳ, and the bound μ_upper satisfies (1 + μ_upper/r)⁻ʳ = α. At r = 1 (geometric distribution), μ_upper(0.05) = 1/α − 1 = 19, compared to 3.00 for the Poisson. The E[T] bound weakens by a factor of 6.3. The structural conclusion — short E[T] under non-negligible Λ implies late filter — remains valid; only the numerical threshold shifts.

**A2. Constant emergence rate (Definition 4).** If Λ(t) varies over galactic history, the steady-state detection model becomes μ = f_SETI · ∫₀^{T_gal} Λ(t) · S(T_gal − t) dt [generalized form of Definition 11]. Define the effective emergence rate Λ_eff = (1/T_gal) · ∫₀^{T_gal} Λ(t) dt [new symbol, used only in this subsection]. Under the steady-state approximation (E[T] ≪ T_gal), μ ≈ f_SETI · Λ_eff · E[T] · T_gal / T_gal = f_SETI · Λ_eff · E[T]. The filter-location analysis applies with Λ_eff replacing Λ. If emergence is concentrated in recent galactic history (Λ increasing with metallicity), then the recent effective rate exceeds the time-average, and the bound on E[T] is conservative (slightly too weak). If emergence was concentrated early (Λ decreasing), the bound weakens. In either case, the structural form of the bound is preserved.

**A3. Exponential/Weibull hazard form (Definitions 8–9).** The E[T] bound from Corollary 1 relies only on the steady-state approximation μ ≈ f_SETI · Λ · E[T], which by Lemma 2 holds for any survival distribution with finite mean and E[T] ≪ T_gal. The bound on E[T] is distribution-free. Only the hazard-shape analysis (Theorems 4, 6) requires the Weibull parametric form. If the true hazard is non-Weibull, the filter-location argument of Section 4.2 does not apply in its specific form, but the qualitative direction is preserved: any survival distribution with a heavier right tail than a Weibull of the same mean (e.g., log-normal, Pareto) would produce even more long-lived civilizations, strengthening the tension with N_det = 0. Any distribution with a lighter tail (e.g., bounded support) would weaken it.

**A4. Independence of communicative lifetimes.** If civilizational lifetimes are correlated — for instance, through galactic-scale catastrophes that simultaneously terminate multiple civilizations — the effective variance of N_det increases, equivalent to over-dispersion. The effect is structurally identical to A1: the bound weakens quantitatively but the filter-location argument is preserved. Negative correlation (competition for resources, predatory civilizations) would reduce variance and tighten the bound.

**A5. f_SETI as a constant (Definition 10).** SETI sensitivity has increased over 60+ years. If f_SETI is time-varying, the detection model uses the cumulative sensitivity over the observation window. Since the current f_SETI is the highest in the survey's history, using the current value in the bound is conservative — it yields a tighter constraint than the historical time-average would. The bound is therefore not invalidated by historical variations in SETI coverage.

#### 4.4.3 Edge Cases

**E1. Λ → 0⁺.** E[T]_upper = −ln α / (f_SETI · Λ) → ∞. The bound becomes vacuous. The model correctly reports that if civilizations never emerge, zero detections constrains nothing about their survival.

**E2. f_SETI → 0⁺.** The bound diverges identically. A search with zero sensitivity cannot constrain civilizational properties. The bound is honest about the information content of the observation.

**E3. f_SETI · Λ → ∞.** E[T]_upper → 0. Zero detections demands essentially zero communicative lifetime. This limit is unphysical (f_SETI ≤ 1) but the monotonic dependence is correct.

**E4. k → 0⁺ (extreme early filter).** Under the Weibull model, h(0⁺) → ∞ as k → 0⁺. The survival function approaches a mixture of a point mass at T = 0 and a heavy algebraic tail. The steady-state approximation may become inaccurate because the effective support extends beyond T_gal. At k < 0.1, the exact integral μ(k, η) = f_SETI · Λ · ∫₀^{T_gal} exp(−(t/η)^k) dt should replace the steady-state form. The tail-ordering result of Theorem 4 remains valid for all k₁ < k₂ > 0, so the structural argument of Section 4.2 is unaffected.

**E5. k → ∞ (extreme late filter).** The Weibull distribution converges to a point mass at T = η. All civilizations survive for exactly η years and then cease. This is the maximum-concentration scenario. The model is well-behaved; E[T] = η and the Poisson constraint applies directly.

**E6. Single-event sensitivity.** The Poisson model treats civilizations as independent draws. If N_det = 0 reflects a single galactic sterilization event (gamma-ray burst, galactic collision) rather than individual civilizational cessation, the independence assumption is violated. In this scenario, the hazard function h(t) should be decomposed into an individual component h_ind(t) and a correlated catastrophic component h_cat, with h(t) = h_ind(t) + h_cat. The bound on E[T] = 1/(h_ind + h_cat) remains valid, but the interpretation shifts: the short lifetime may reflect correlated catastrophe rather than individual civilizational fragility. This does not change the filter-location conclusion — a correlated catastrophe is itself a late-acting filter if it operates on post-technological timescales — but it changes the nature of the filter from endogenous (civilizational self-destruction) to exogenous (astrophysical catastrophe).

#### 4.4.4 Competing Models

**C1. Drake equation (Drake 1961).** The Drake equation estimates N = R★ · f_p · n_e · f_l · f_i · f_c · L. It fails as an inferential tool because (a) it provides no mechanism for conditioning on N_det = 0, (b) it treats L as a multiplicative constant indistinguishable from the emergence terms, and (c) it contains no hazard function and therefore cannot perform filter-location analysis. The survival model replaces the Drake product with μ = f_SETI · Λ · E[T] (Definition 11), decoupling emergence from survival and incorporating the null observation through the Poisson likelihood (Definition 12). **Formal reason for rejection:** The Drake equation is an accounting identity, not an inferential model. It cannot condition on data, cannot distinguish early from late filter, and cannot produce the confidence bounds of Theorems 2–5.

**C2. Rare Earth hypothesis (Ward & Brownlee 2000).** Rare Earth proposes that Λ ≈ 0. In this framework, Rare Earth is not a competing model but the alternative branch of the same partition (Section 4.4.1, Resolution I). It is not rejected; it is subsumed as the special case Λ < Λ_crit. **Formal status:** Rare Earth and the late-filter result are complementary branches. Rare Earth addresses emergence scarcity; this paper addresses survival brevity. They answer different questions.

**C3. Great Filter (Hanson 1998).** Hanson argued that the silence implies at least one extremely improbable or lethal step in civilizational development. This paper's framework is consistent with Hanson's conclusion (a filter exists) but advances beyond it: the Weibull hazard function h(t) gives the instantaneous filter intensity as a function of civilizational age, and the shape parameter k distinguishes early-acting from late-acting filters formally (Theorems 4–6). Hanson's argument establishes filter existence as a logical necessity given the silence but provides no quantitative mechanism for locating the filter within the developmental sequence. **Formal reason for supersession:** The Great Filter framework is subsumed, not contradicted. This paper inherits Hanson's existence result and adds location information through the hazard function. Every result derived here is consistent with Hanson (1998); the contribution is the location analysis that Hanson's framework cannot perform.

**C4. Non-Poisson emergence models.** If emergence follows a clustered, self-exciting, or otherwise non-Poisson process, the zero-count probability changes (see Section 4.4.2, A1). For any counting distribution with mean μ and P(0 | μ) > 0, the observation N_det = 0 constrains μ from above, and the renewal theorem guarantees μ ∝ E[T] for any survival distribution with finite mean in the steady-state regime. The numerical threshold shifts (weakening by a factor up to ~6× for realistic over-dispersion) but the qualitative structure of the bound is preserved. **Formal reason for rejection as an alternative:** Non-Poisson emergence changes quantitative thresholds but not the qualitative structure. The late-filter conclusion under non-Poisson emergence holds at a shifted Λ_crit. It is a generalization of the baseline model, not an alternative to it.

**C5. Non-uniform emergence rate.** If Λ(t) varies over galactic time, the time-homogeneous Poisson model is a special case. The generalization replaces Λ with an effective time-averaged rate Λ_eff (Section 4.4.2, A2). The filter-location analysis applies with Λ_eff substituted for Λ. **Formal reason for rejection as an alternative:** The time-varying case is a straightforward generalization, not a competing framework. It shifts the threshold without altering the conditional conclusion.

### 4.5 Open Problems

**O1. The Λ degeneracy.** The central limitation of this framework is that the SETI null result constrains the product f_SETI · Λ · E[T] but cannot decompose it into its factors without external information. Breaking this degeneracy requires independent empirical estimates of Λ (from exoplanet biosignature surveys constraining f_l · f_i · f_c) or of f_SETI (from comprehensive SETI sensitivity analyses). Until such estimates are available, the late-filter conclusion remains conditional on Λ > Λ_crit. This is the single most important open problem for the framework.

**O2. Non-parametric hazard estimation.** The Weibull model is the minimal parametric extension of the exponential that distinguishes early from late filter using a single additional parameter. The true civilizational hazard function may be non-monotonic — for example, elevated risk in early technological periods, reduced risk during a consolidation phase, and re-elevated risk at advanced stages. Non-parametric or semi-parametric hazard estimation requires N_det > 0. With zero detections, only low-parameter parametric models are identifiable. Non-parametric filter location is a fundamentally multi-detection problem that awaits future data.

**O3. Multi-channel detection.** The model uses a single f_SETI scoped to electromagnetic detection (Definition 10). Incorporating independent channels — infrared excess from Dyson spheres, stellar dimming from megastructures, atmospheric biosignatures — would replace f_SETI with an effective detection fraction f_eff = 1 − ∏_j (1 − f_j) > f_SETI [new symbol, this subsection only], tightening the constraint. Multi-channel analysis is deferred to future work.

**O4. Temporal resolution.** The observation N_det = 0 treats 60+ years of SETI as a single Poisson window. Modeling the time-varying sensitivity of successive surveys as a detection rate function would slightly tighten bounds near the current threshold but does not change the asymptotic structure of the result.

[Figure 3: Lifetime Bound as a Function of Emergence Rate]

```python
# Figure 3: E[T]_upper vs. Λ for different f_SETI values (application of Corollary 1)
import matplotlib.pyplot as plt
import numpy as np

alpha = 0.05
mu_upper = -np.log(alpha)
T_gal = 13.6e9

Lambda_vals = np.logspace(-5, 2, 1000)
f_SETI_values = [1e-8, 1e-7, 1e-6, 1e-5]
labels = [r'$f_{\rm SETI} = 10^{-8}$',
          r'$f_{\rm SETI} = 10^{-7}$ (baseline)',
          r'$f_{\rm SETI} = 10^{-6}$',
          r'$f_{\rm SETI} = 10^{-5}$']
colors = ['blue', 'black', 'red', 'darkgreen']
styles = ['--', '-', '-.', ':']

fig, ax = plt.subplots(1, 1, figsize=(8, 6))

for f_SETI, label, color, style in zip(f_SETI_values, labels, colors, styles):
    ET_upper = mu_upper / (f_SETI * Lambda_vals)
    ax.loglog(Lambda_vals, ET_upper, color=color, linestyle=style,
              linewidth=2, label=label)

ax.axhline(y=T_gal, color='gray', linestyle=':', linewidth=1,
           label=r'$T_{\rm gal} = 13.6$ Gyr')
ax.axhline(y=1e8, color='orange', linestyle=':', linewidth=0.7,
           label=r'$\tau = 10^8$ yr (complex life)')
ax.axhline(y=1e4, color='purple', linestyle=':', linewidth=0.7,
           label=r'$\tau = 10^4$ yr (civilization)')

ax.set_xlabel(r'Emergence rate $\Lambda$ [civ yr$^{-1}$]', fontsize=12)
ax.set_ylabel(r'$E[T]_{\rm upper}$ [yr]  (95% confidence)', fontsize=12)
ax.set_title(r'Upper bound on mean communicative lifetime from $N_{\rm det} = 0$'
             '\n' r'(Corollary 1, $\alpha = 0.05$)', fontsize=12)
ax.legend(fontsize=9, loc='upper right')
ax.set_xlim(1e-5, 1e2)
ax.set_ylim(1e2, 1e16)
plt.tight_layout()
plt.savefig('figures/figure_3.pdf', dpi=300, bbox_inches='tight')
```

[Figure 4: Filter Location Threshold Map]

```python
# Figure 4: Λ_crit(τ) threshold — regions where data force E[T] < τ (Theorem 5)
import matplotlib.pyplot as plt
import numpy as np

alpha = 0.05
mu_upper = -np.log(alpha)
f_SETI = 1e-7

tau_vals = np.logspace(3, 11, 1000)
Lambda_crit = mu_upper / (f_SETI * tau_vals)

fig, ax = plt.subplots(1, 1, figsize=(8, 6))

ax.loglog(tau_vals, Lambda_crit, 'k-', linewidth=2,
          label=r'$\Lambda_{\rm crit}(\tau) = -\ln\alpha\, /\, (f_{\rm SETI} \cdot \tau)$')
ax.fill_between(tau_vals, Lambda_crit, 1e6, alpha=0.15, color='red',
                label=r'$\Lambda > \Lambda_{\rm crit}$: $E[T] < \tau$ forced (late filter)')
ax.fill_between(tau_vals, 1e-10, Lambda_crit, alpha=0.15, color='blue',
                label=r'$\Lambda < \Lambda_{\rm crit}$: $E[T]$ unconstrained')

refs = [(1e4, 'Civilization'), (1e6, 'Geological'),
        (1e8, 'Complex life'), (1e10, 'Galactic')]
for tau_ref, name in refs:
    lc = mu_upper / (f_SETI * tau_ref)
    ax.plot(tau_ref, lc, 'ko', markersize=5)
    ax.annotate(name, (tau_ref, lc), textcoords="offset points",
                xytext=(10, 5), fontsize=9)

ax.set_xlabel(r'Reference timescale $\tau$ [yr]', fontsize=12)
ax.set_ylabel(r'Critical emergence rate $\Lambda_{\rm crit}$ [civ yr$^{-1}$]',
              fontsize=12)
ax.set_title(r'Filter location threshold (Theorem 5, $f_{\rm SETI} = 10^{-7}$, $\alpha = 0.05$)',
             fontsize=12)
ax.legend(fontsize=9, loc='upper right')
ax.set_xlim(1e3, 1e11)
ax.set_ylim(1e-10, 1e6)
plt.tight_layout()
plt.savefig('figures/figure_4.pdf', dpi=300, bbox_inches='tight')
```

---

## 5. Related Work

The preceding sections established the survival function framework, derived its core results, and stress-tested its assumptions. We now position this framework within the existing literature. This section provides a comparative critique of the formal frameworks most directly relevant to the survival function approach, focusing on what each framework's mathematical structure can and cannot achieve. Works discussed in the Introduction (Section 2) are revisited here with deeper analytical focus on their formal limitations; works not previously discussed are introduced with the literature gap formula.

### 5.1 The Drake Equation and Its Statistical Extensions

The Introduction (Section 2) identified three structural failures of the Drake equation: inability to condition on N_det = 0, conflation of emergence and survival, and insensitivity to the distinction between rare emergence and rapid extinction. These are model-class limitations, not parameter-estimation problems. The Drake equation belongs to the class of static accounting identities: it maps an input tuple to a scalar output (N) with no likelihood function, no time domain, and no inferential machinery.

Sandberg, Drexler & Ord (2018) proposed propagating parameter uncertainty through the Drake product via Monte Carlo simulation with log-uniform priors on each factor. Their central result — that P(N < 1) is non-negligible under plausible uncertainties — transforms the Drake equation from a point estimate into a probability distribution over N and addresses the question "is the silence surprising?" But the probabilistic Drake equation cannot address "what does the silence tell us about civilizational survival?" The distinction is foundational. Sandberg, Drexler & Ord treat the silence as the explanandum — the thing to be explained — while this paper treats it as the datum — evidence to be incorporated through L(θ) = exp(−μ(θ)) (Definition 12). No statistical extension of the Drake equation can perform filter-location analysis, because the Drake product N = R★ · f_p · n_e · f_l · f_i · f_c · L contains no hazard function h(t) and therefore provides no mechanism for distinguishing early-acting from late-acting risk. The survival function framework replaces the model class, not the parameter values.

### 5.2 The Great Filter

Hanson (1998) recognized that the silence, combined with the apparent hospitality of the galaxy for life, implies the existence of at least one highly improbable or highly lethal step — a "filter" — in the sequence from prebiotic chemistry to galaxy-spanning civilization. This was a genuine insight: the filter exists as a logical necessity given the observations. But Hanson's argument is a counting argument: given n "hard steps" between origin and expansion, and given the silence, the total product of step-transition probabilities must be very small. This product structure is formally identical to the Drake equation augmented by an existence constraint.

The critical limitation is that Hanson's framework provides no formal tool for locating the filter. Hanson posed the question — is the filter ahead of us or behind us? — but his product-of-probabilities decomposition has no time-dependent structure. Every permutation of step difficulties that yields the same total product is equally consistent with the data. The Weibull hazard function h(t) = (k/η)(t/η)^{k−1} (Definition 9) introduces the time-dependent structure that the product decomposition lacks. The shape parameter k indexes the filter's position in civilizational developmental time, and Theorems 4–6 derive observational consequences that differ by k. The relationship between the two frameworks is subsumption: every result in this paper is consistent with Hanson's existence argument, but the location results (Section 4.2) are inaccessible from Hanson's framework because it cannot distinguish two filter configurations that yield the same aggregate transition probability.

### 5.3 Anthropic Reasoning

Carter (1983) constrained the probability of intelligent life's emergence by observing that Earth's biological development time (~4 Gyr) is comparable to the Sun's main-sequence lifetime (~10 Gyr). If emergence probability per unit time were high, emergence would have occurred substantially earlier; the timing suggests emergence is a rare event relative to the available window. Carter's argument operates in a fundamentally different inference space from the survival function approach: Carter conditions on the observer's existence and extracts constraints on emergence probability, while this paper conditions on the SETI null result and extracts constraints on survival time. The two inferences are complementary. Carter's framework cannot extract survival-time information from the silence, because it treats the observer's existence — not the SETI null observation — as the entire evidential basis.

A complete Bayesian analysis would integrate both inference channels: using Carter-type anthropic arguments to constrain Λ (via bounds on the per-star emergence rate) and the survival-function likelihood to constrain E[T] given Λ. This integration would partially resolve the Λ degeneracy identified in Open Problem O1 (Section 4.5). The anthropic prior on Λ, combined with the survival-function likelihood, would yield a posterior distribution over (Λ, E[T]) that could sharpen the filter-location result. Such integration exceeds the scope of this paper but represents a natural extension of the framework.

### 5.4 Dissolution Arguments

Sandberg, Drexler & Ord (2018) argued that the Fermi paradox "dissolves" once uncertainty is properly propagated: the paradox arises from treating uncertain parameters as known constants and then being surprised by the tension between optimistic N estimates and the observed silence. Under proper uncertainty propagation, there is no tension to explain. This argument is correct as far as it goes — the Drake equation, treated as a point estimator, does produce a false paradox. But dissolution addresses a narrower question than this paper's framework. Dissolution establishes that the silence is not surprising under parameter uncertainty; this paper establishes what the silence constrains under any fixed parameterization. The survival function framework does not require the paradox to exist in order to function: it extracts information from N_det = 0 regardless of whether that observation was "expected" or "surprising." The conditional constraint E[T] ≤ −ln α / (f_SETI · Λ) holds whether or not the analyst finds N_det = 0 surprising. Dissolution and survival-function inference answer different questions and are fully compatible.

---

## 6. Discussion

The technical transition from derivation to interpretation requires explicit statement: Sections 3–4 established formal constraints; this section examines their implications without introducing new claims.

This paper has established three results. First, under exponential or Weibull hazard with non-negligible emergence rate (Λ > Λ_crit), the SETI null observation constrains the mean communicative lifetime to E[T] ≤ −ln α / (f_SETI · Λ) (Corollary 1). Second, this constraint is invariant under the Weibull shape parameter k: a single Poisson null count cannot resolve whether the hazard is early- or late-acting (Corollary 2). Third, the structural properties of the Weibull survival function — the tail ordering by shape parameter (Theorem 4) and its implications for survivor accumulation (Theorem 6) — favor late-acting hazard (k > 1) as the interpretation most consistent with zero detections across all observational channels (Section 4.2). These results merit discussion along four dimensions.

### 6.1 The Conditional Structure

The late-filter result is conditional on Λ > Λ_crit. This conditionality is a feature of the framework, not a weakness. The survival function approach does not resolve the Fermi paradox — it reduces it to a single empirical question (whether Λ exceeds Λ_crit) and derives what follows from each answer. The partition of Section 4.4.1 — rare emergence vs. late filter — is exhaustive and mutually exclusive at any given confidence level. Resolving the partition requires independent empirical constraints on Λ, most plausibly from exoplanet atmospheric characterization surveys capable of detecting biosignatures and thereby bounding the emergence rate from below.

The conditional structure also clarifies the relationship between this paper and the broader Fermi paradox literature. Many proposed "solutions" to the paradox — zoo hypotheses, dark forest scenarios, simulation arguments — implicitly assume non-negligible Λ and then explain the silence through behavioral or strategic assumptions. The survival function framework makes the Λ assumption explicit and derives what follows without behavioral assumptions about civilizational choices. If Λ > Λ_crit, the silence constrains E[T] regardless of whether civilizations choose to hide, choose to communicate, or are unaware of our existence. The constraint applies to communicative lifetime as defined in Definition 5 — the duration of detectable electromagnetic emission — not to civilizational survival per se.

### 6.2 Methodological Contribution

The replacement of the Drake equation with a survival function framework is not a notational change. It is a shift from estimation — guessing N from uncertain factors — to inference — constraining survival parameters from observed data. The structural innovation is the treatment of the SETI null result as a censored observation in a Poisson likelihood, rather than as a probability to be explained or a paradox to be resolved.

This treatment places Fermi paradox analysis on the same formal footing as clinical trials with censored endpoints, reliability engineering with failure-time data, and demographic studies with right-censored lifetimes — domains where the Cox (1972) framework and its extensions have been standard for half a century. The mathematical tools applied here — Poisson likelihoods, confidence bounds, Weibull hazard functions — are standard survival analysis. The contribution is methodological transfer: applying an established inference framework to a question that has been dominated by speculation and heuristic reasoning.

### 6.3 Implications for SETI Strategy

The framework provides a quantitative basis for SETI observing strategy. The effective constraint on E[T] scales as (f_SETI)⁻¹ (Corollary 1). Increasing f_SETI — through broader spectral coverage, deeper sensitivity, wider sky surveys, or multi-messenger detection channels — tightens the constraint on communicative lifetime and lowers the threshold Λ_crit at which the late-filter conclusion is triggered (Corollary 3(c)). A comprehensive survey that increases f_SETI by one order of magnitude (from ~10⁻⁷ to ~10⁻⁶) reduces E[T]_upper by the same factor and brings more of the plausible Λ range into the constrained regime.

The model provides a formal cost-benefit framework for SETI investment: the information gain from a survey improvement is quantifiable through the change in E[T]_upper and the corresponding expansion of the parameter space within which the late-filter conclusion holds. This contrasts with the Drake equation, which provides no mechanism for quantifying the information value of a null result.

### 6.4 The Nature of the Hazard

The late-filter result, if the emergence rate is non-negligible, implies that civilizations face escalating hazard with technological age. This paper derives this conclusion formally but deliberately does not speculate about the nature of the filter. The hazard function h(t) describes the rate of communicative cessation — it does not distinguish between civilizational extinction, voluntary withdrawal from electromagnetic communication, transition to undetectable communication modalities, or deliberate concealment. Each of these cessation modes produces the same observational signature (N_det = 0) and is therefore consistent with the formal result.

Identifying the mechanism behind the hazard requires evidence beyond the SETI null observation — evidence that this paper's framework correctly identifies as unavailable from current data (Open Problem O2, Section 4.5). The formal result constrains the timing of the dominant hazard (post-technological) but not its nature. This agnosticism is intentional: the model extracts what can be extracted from the available datum and stops where the data stop.

---

## 7. Conclusion

This paper has replaced the Drake equation with a survival analysis framework that treats the Fermi paradox as an inference problem rather than an estimation problem. The framework rests on three formal elements: the survival function S(t) = P(T > t) with explicit hazard rate h(t) under the Cox (1972) formalism (Definitions 5–9), the Poisson detection model μ(θ) = f_SETI · Λ · E[T] linking civilizational survival to observable consequences (Definition 11), and the treatment of N_det = 0 as a censored observation yielding the likelihood L(θ) = exp(−μ(θ)) (Definition 12).

From these elements, three principal results were derived:

1. The maximum-likelihood hazard rate under zero detections diverges (Theorem 1), and the 95% confidence upper bound on mean communicative lifetime is E[T] ≤ 3.00 / (f_SETI · Λ) (Corollary 1). This bound is structurally robust across the model's parameters (Table 3).

2. The Weibull extension distinguishes early-acting from late-acting hazard through the shape parameter k, but the single null observation cannot resolve k directly (Corollary 2). The distinction emerges from the structural properties of the Weibull survival tail (Theorem 4) and its implications for the accumulation of long-lived civilizations (Theorem 6).

3. Under any parameterization with non-negligible emergence rate (Λ > Λ_crit, Theorem 5), the observation N_det = 0 constrains E[T] below physically meaningful timescales. The consistency analysis of Section 4.2 identifies late-acting hazard (k > 1) — a post-technological filter that intensifies with civilizational age — as the interpretation most consistent with zero detections across all observational channels.

The framework reduces the Fermi paradox to a single empirical question: whether the civilizational emergence rate Λ exceeds the computable threshold Λ_crit(τ, α) = −ln α / (f_SETI · τ). If it does, the silence points to a late-stage filter. If it does not, the silence is uninformative about survival. The threshold is quantitative, the partition is exhaustive, and the conclusion is derived — not asserted.

---

## References

Bland-Hawthorn, J. & Gerhard, O. (2016). The Galaxy in Context: Structural, Kinematic, and Integrated Properties. *Annual Review of Astronomy and Astrophysics*, 54, 529–596.

Carter, B. (1983). The Anthropic Principle and Its Implications for Biological Evolution. *Philosophical Transactions of the Royal Society of London A*, 310, 347–363.

Cox, D. R. (1972). Regression Models and Life-Tables. *Journal of the Royal Statistical Society, Series B*, 34(2), 187–220.

Drake, F. D. (1961). Discussion at Space Science Board — National Academy of Sciences Conference on Extraterrestrial Intelligent Life, Green Bank, West Virginia.

Enriquez, J. E., Siemion, A. P. V., Foster, G., Gajjar, V., Hellbourg, G., Hickish, J., Isaacson, H., Price, D. C., Croft, S., DeBoer, D., Lebofsky, M., MacMahon, D. H. E. & Werthimer, D. (2017). The Breakthrough Listen Search for Intelligent Life: 1.1–1.9 GHz Observations of 692 Nearby Stars. *The Astrophysical Journal*, 849, 104.

Hanson, R. (1998). The Great Filter — Are We Almost Past It? Working paper, George Mason University. Available at: http://mason.gmu.edu/~rhanson/greatfilter.html

Planck Collaboration (2020). Planck 2018 Results. VI. Cosmological Parameters. *Astronomy & Astrophysics*, 641, A6.

Sandberg, A., Drexler, E. & Ord, T. (2018). Dissolving the Fermi Paradox. arXiv preprint, arXiv:1806.02404.

Tarter, J. (2001). The Search for Extraterrestrial Intelligence (SETI). *Annual Review of Astronomy and Astrophysics*, 39, 511–548.

Ward, P. D. & Brownlee, D. (2000). *Rare Earth: Why Complex Life Is Uncommon in the Universe*. New York: Copernicus Books.
