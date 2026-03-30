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
