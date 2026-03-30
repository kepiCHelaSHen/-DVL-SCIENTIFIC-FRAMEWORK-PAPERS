# FROZEN SPEC — The Fermi Paradox as a Survival Function
# Lock date: 2026-03-30
# Locked by: James P Rice Jr.
# DO NOT MODIFY AFTER LOCK DATE.

---

## PARAMETERS

### PARAMETER 1: Observational baseline
- **Value:** 0 confirmed detections in 60+ years of SETI observation
- **Unit:** dimensionless
- **Tolerance:** exact — this is the censored data point the model conditions on
- **Source:** Tarter 2001 | The Search for Extraterrestrial Intelligence | ARA&A 39:511-548
- **Notes:** The silence is not absence of evidence — it is a censored observation in the survival analysis sense. The model must treat it formally as such.
- **KNOWN PRIOR DRIFT RISK:** LOW — this fact is not in dispute

### PARAMETER 2: Galaxy age
- **Value:** 13.6 Gyr
- **Unit:** billion years
- **Tolerance:** +/- 0.1 Gyr
- **Source:** Planck Collaboration 2020 | A&A 641:A6
- **Notes:** Sets the upper bound on the time domain of the survival function.
- **KNOWN PRIOR DRIFT RISK:** LOW

### PARAMETER 3: Milky Way stellar count (communicating-capable stars)
- **Value:** ~10^11
- **Unit:** stars
- **Tolerance:** order of magnitude
- **Source:** Bland-Hawthorn & Gerhard 2016 | ARA&A 54:529-596
- **Notes:** Used only to set the population baseline. Exact value doesn't drive results — the survival function result is robust across an order of magnitude.
- **KNOWN PRIOR DRIFT RISK:** LOW

### PARAMETER 4: SETI sensitivity baseline
- **Value:** Kardashev Type I equivalent transmitters detectable within ~100 light-years
- **Source:** Tarter 2001; updated by Enriquez et al. 2017 | ApJ 849:104
- **Notes:** This scopes what "silence" means. The model must be explicit about what the silence rules out vs. what it cannot constrain.
- **KNOWN PRIOR DRIFT RISK:** MEDIUM — LLM prior may overstate SETI coverage

### PARAMETER 5: Survival function form
- **Value:** Exponential hazard (constant hazard rate) as baseline; Weibull extension for age-dependent hazard (increasing hazard = late filter; decreasing = early filter)
- **Source:** Cox 1972 | Journal of the Royal Statistical Society 34(2):187-220
- **Notes:** Start with exponential for tractability. Weibull lets you distinguish early vs. late filter formally. This is the core methodological contribution.
- **KNOWN PRIOR DRIFT RISK:** HIGH — Author may default to simpler probabilistic framing without survival analysis machinery. Must use Cox/Weibull formalism.

### PARAMETER 6: The core result
- **Value:** Under exponential hazard, the maximum likelihood hazard rate consistent with zero detections implies a mean civilizational communicative lifetime short enough to be consistent ONLY with a late-stage filter (post-technological).
- **Source:** Rice [this paper] — derived result
- **Notes:** This is the punchline. Do not soften it. Derive it formally and state it plainly: the silence points to a filter ahead of us, not behind us.
- **KNOWN PRIOR DRIFT RISK:** HIGH — Author may hedge. The Peer Reviewer must enforce the claim if the math supports it.

---

## ORACLE

The model is valid if and only if:
1. The survival function is formally defined with explicit hazard rates
2. The censored observation (zero detections) is correctly incorporated via the likelihood function, not treated as a simple probability
3. The ML hazard rate is derived analytically, not estimated by intuition
4. The filter location result follows mathematically from M2 — not re-argued
5. The Drake equation critique in the Introduction is precise, not rhetorical

Peer Reviewer must verify: does the late-filter conclusion follow from the math, or is it asserted? If asserted, REJECT.

---

## MILESTONE MAP

| Milestone | Deliverable | Gate |
|-----------|-------------|------|
| M1 | Formal model setup — survival function framework, hazard rates, censored observation structure. Drake critique. Notation. | Peer Reviewer ACCEPT |
| M2 | Core derivation — ML hazard rate from zero detections. Weibull extension for early vs. late filter. | Peer Reviewer ACCEPT |
| M3 | Implication — what ML hazard rate implies about filter location. Sensitivity analysis table. Competing models rejected. | Peer Reviewer ACCEPT |
| M4 | Full paper — Introduction, Related Work, Discussion, Conclusion. Self-contained Abstract. | Peer Reviewer ACCEPT + Editor ACCEPT |

---

## KNOWN PRIOR DRIFT RISKS

### DRIFT RISK 1: Drake reversion
- **Risk:** Reverting to Drake equation framing instead of survival analysis
- **Mitigation:** Every section must use survival function notation. Drake appears only in the critique.

### DRIFT RISK 2: Censored observation mishandling
- **Risk:** Treating zero detections as P(detection)=0 instead of a censored observation
- **Mitigation:** Peer Reviewer checks likelihood function formulation.

### DRIFT RISK 3: Late-filter hedging
- **Risk:** Hedging the late-filter conclusion when the math supports a strong claim
- **Mitigation:** Peer Reviewer enforces U4 (underclaiming). If math supports it, state it.

### DRIFT RISK 4: Hanson conflation
- **Risk:** Conflating the Great Filter (Hanson) with the survival function result — related but distinct
- **Mitigation:** Paper derives the filter location; Hanson assumed it. Must be clear.

### DRIFT RISK 5: Speculative filter candidates
- **Risk:** Adding sections on specific filter candidates (AI, nuclear war, climate)
- **Mitigation:** This paper is formal, not speculative. Keep it tight.

### DRIFT RISK 6: SETI coverage overstatement
- **Risk:** Overstating what SETI has actually surveyed
- **Mitigation:** Be precise about what the silence constrains.

### DRIFT RISK 7: Missing sensitivity analysis
- **Risk:** Skipping the sensitivity analysis table
- **Mitigation:** M3 must include table varying hazard rate, SETI radius, galaxy age.

### DRIFT RISK 8: Missing competing model rejections
- **Risk:** Failing to formally reject: Drake equation, Rare Earth, Great Filter, Non-Poisson emergence, Non-uniform emergence rate
- **Mitigation:** Each must be rejected with a specific formal reason.

### DRIFT RISK 9: Orphan figures
- **Risk:** Figure references without Python/matplotlib code
- **Mitigation:** Every figure must have executable code. Minimum: survival function, likelihood function, filter location posterior.
