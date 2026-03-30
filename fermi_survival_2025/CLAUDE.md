# The Fermi Paradox as a Survival Function — NORTH STAR
# Read this at the start of every session. Two minutes max.

## What We Are Building
A formal survival analysis model replacing the Drake equation. The silence
is a censored observation. The math points to a late-stage filter.

## The Core Claim
Under exponential hazard, zero detections over 60 years implies a mean
communicative lifetime consistent only with a dominant post-technological filter.
This is derived, not speculated.

## Key Files
- CHAIN_PROMPT.md — master doc, wins all conflicts
- spec/frozen_spec.md — frozen parameters, never modify
- state/state_vector.md — save game
- state/innovation_log.md — audit trail
- state/dead_ends.md — do not repeat these
- prompts/04_paper_orchestrator.md — the pipeline

## Frozen Parameters (quick reference)
| Parameter | Value | Source |
|-----------|-------|--------|
| Detections | 0 (censored) | Tarter 2001 |
| Galaxy age | 13.6 Gyr | Planck 2020 |
| Stellar count | ~10^11 | Bland-Hawthorn & Gerhard 2016 |
| SETI baseline | KI within ~100 ly | Tarter 2001; Enriquez et al. 2017 |
| Hazard model | Exponential + Weibull | Cox 1972 |
| Core result | Late-stage filter | Rice [this paper] |

## Critical Enforcements
- Survival function formalism — not Drake probability math
- Zero detections = censored observation, not P=0
- Late-filter conclusion must be derived, not asserted
- No speculation about specific filter candidates
- Weibull extension required to distinguish early vs. late filter

## Current Status
See STATUS.md.

## Do Not Touch
See SACRED_FILES.md.
