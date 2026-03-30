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
