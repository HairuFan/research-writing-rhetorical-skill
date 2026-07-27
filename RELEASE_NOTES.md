# Research Writing Rhetorical Skill v1.0.0

This is the first stable evaluated release of the Research Writing Rhetorical Skill.

## Included

- section-aware rhetorical revision;
- rhetorical-move and logical-relation diagnosis;
- study-design-aware claim calibration;
- meaning-preservation and unsupported-content safeguards;
- naturalness, density, and template-reduction audits;
- clean, diagnostic, and full-audit output modes;
- ten demonstration cases;
- an 80-case paired evaluation benchmark and rubric.

## Evaluation summary

Final human-audited outcomes across 80 paired cases:

- skill preferred: 43 cases (53.75%);
- baseline preferred: 21 cases (26.25%);
- tie: 16 cases (20.00%);
- skill non-loss rate: 73.75%;
- skill win share among non-tied cases: 67.19%;
- observed skill critical failures: 0.

Two blinded Gemini 3.6 Flash judge runs provided preliminary ratings. All inter-run disagreements and all concordant baseline-preferred cases were reviewed by a human adjudicator.

## Demonstrated strengths

- causal and evidential claim calibration;
- limitation and simulation-boundary language;
- gap-to-objective transitions;
- reviewer-response directness;
- reduction of generic framing and repetitive academic templates.

## Known limitations

- generic research-need language can be replaced by equivalent boilerplate;
- broad source language can occasionally be narrowed beyond the supplied context;
- literature synthesis may introduce unsupported contrast markers;
- lexical variation can weaken parallel structure;
- concise revisions can occasionally weaken source emphasis.

See `evals/results/v1.0.0-evaluation-report.md` for the complete interpretation and release rationale.

## Versioning note

The comparative preference target of 70% remains an improvement objective. Version 1.0.0 is released on the basis of clear overall benefit, strong meaning preservation, zero observed critical failures, and transparent documentation of remaining weaknesses.