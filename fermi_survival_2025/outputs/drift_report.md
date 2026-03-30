# Drift Report

Paper: fermi_survival_2025
Date: 2026-03-30
SHELL Version: 5.0
Models: Author=Claude, Peer Reviewer=Claude, Editor=Claude, Orchestrator=Claude

## Rejection Summary Table

No drift detected. All milestones accepted on first Peer Reviewer submission.

The only rejection in the pipeline was from the Editor (M4, editorial issues only):

| Milestone | Turn | Checklist Item | Issue | Drift Type |
|-----------|------|----------------|-------|------------|
| M4 | 4 | E5 | Abstract used τ and α without definition | STRUCTURAL_ERROR |
| M4 | 4 | E15 | Missing transition sentence Section 4→5 | STRUCTURAL_ERROR |
| M4 | 4 | E9 | Pipeline artifact text in paper body | STRUCTURAL_ERROR |

These were editorial issues, not parameter drift or scientific errors.

## Parameter-Level Drift Summary

No parameter drift occurred. All frozen spec parameters were correctly used in every milestone submission.

## Aggregate Statistics

- Total Author submissions: 5 (M1: 1, M2: 1, M3: 1, M4: 2 — 1 initial + 1 editorial revision)
- Total Peer Reviewer rejections: 0
- Total Editor rejections: 1 (editorial only)
- Rejection rate per milestone: M1: 0%, M2: 0%, M3: 0%, M4: 0% (PR), 50% (Editor, 1/2)
- Most-drifted parameter: None — zero parameter drift across all milestones

## Interpretation

The Author (Claude) exhibited zero parameter drift and zero scientific drift across four milestones. All Peer Reviewer checks passed on first submission for every milestone. The single Editor rejection addressed presentational issues (Abstract self-containment, transition sentences, pipeline artifacts) rather than scientific content. This pattern is consistent with strong prompt adherence and effective drift-risk mitigation from the frozen spec.
