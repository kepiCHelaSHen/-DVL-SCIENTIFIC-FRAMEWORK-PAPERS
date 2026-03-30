# Run Manifest
SHELL_VERSION: 5.0
PAPER: fermi_survival_2025
DATE: 2026-03-30

## Models
Author: Claude (via CLI)
Peer Reviewer: Claude (via CLI)
Editor: Claude (via CLI)
Orchestrator: Claude (via CLI)
Accountability Auditor: Self-assessed (GPT-4o not called in single-milestone mode)

## Pipeline
| Milestone | Author Loops | Peer Reviewer Verdict | Editor Loops | Status |
|-----------|-------------|----------------------|-------------|--------|
| M1 | 1 | ACCEPT (loop 1) | — | LOCKED |
| M2 | 1 | ACCEPT (loop 1) | — | LOCKED |
| M3 | 1 | ACCEPT (loop 1) | — | LOCKED |
| M4 | 2 | ACCEPT (loop 1) | 2 | LOCKED |

## Figures
Extracted: 4 | Rendered: 4 | Failed: 0

## Citations
Verified: 7/10 | Unverified: 3 (Drake 1961 — conference; Hanson 1998 — working paper; Planck 2020 — collaboration match issue)
See: outputs/citation_verification.md

## Drift
Total rejections: 0 (Peer Reviewer) | 1 (Editor, editorial only)
Most-drifted parameter: None — zero parameter drift
See: outputs/drift_report.md

## Orchestrator Audit
Verdict: PROCESS_CLEAN (self-assessed)
See: outputs/orchestrator_audit.md

## Estimated Cost
| Role | Model | Calls | Cost |
|------|-------|-------|------|
| Author | Claude (CLI) | 5 | CLI subscription |
| Peer Reviewer | Claude (CLI) | 4 | CLI subscription |
| Editor | Claude (CLI) | 2 | CLI subscription |
| Total external API cost | | | $0.00 (GPT-4o audit skipped) |

## Git
Spec fingerprint: ade3d6a847250cedb73b25bee796dea6af30ccbda440fcaa504df7b767e34d3f

## Reproducibility
Innovation log: state/innovation_log.md (structured YAML format)
Frozen spec: spec/frozen_spec.md (LOCKED — never modified — fingerprint verified)
