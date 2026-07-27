# Manual Smoke Test — 2026-07-26

## Status

- Skill version: `1.0.0-mvp`
- Benchmark version: `1.0.0-mvp`
- Model: Claude Sonnet 5
- Evaluation type: manual paired baseline-versus-skill smoke test
- Evaluator: PI blind preference review
- Cases: 10 rhetorical templates
- Purpose: internal MVP gate before the full 80-case benchmark

This report records a preliminary smoke test. It is not a substitute for the planned 80-case benchmark and should not be presented as comprehensive validation.

## Aggregate Result

| Outcome | Count |
|---|---:|
| Skill preferred | 8 |
| Tie | 2 |
| Baseline preferred | 0 |
| Skill critical failures | 0 |

Derived summary:

- Skill preferred rate: 80%
- Skill non-loss rate: 100%
- Observed skill critical-error rate: 0%

## Case-Level Results

| Case | Rhetorical task | Result | Strength | Benchmark interpretation |
|---|---|---|---|---|
| T01 | Generic framing | Skill preferred | Clear | Discriminative |
| T02 | Prior work to gap | Skill preferred | Clear | Discriminative |
| T03 | Gap to objective | Skill preferred | Clear | Discriminative |
| T04 | Literature synthesis | Skill preferred | Clear | Discriminative |
| T05 | Methods sequencing | Skill preferred | Clear | Strongly discriminative |
| T06 | Repetitive results | Tie | None | Ceiling effect |
| T07 | Unsupported causality | Tie | None | Ceiling effect |
| T08 | Vague implication | Skill preferred | Clear | Discriminative |
| T09 | Simulation limitation | Skill preferred | Clear | Strongly discriminative |
| T10 | Reviewer response | Skill preferred | Slight | Discriminative |

## Main Observed Gains

The skill most consistently improved:

- removal of mechanical transitions and academic boilerplate;
- information density and sentence compression;
- concept- or method-centered organization;
- unsupported-content control;
- evidential-boundary calibration in limitations;
- reduction of excessive reviewer-response praise;
- avoidance of unnecessary novelty and specificity escalation.

## Remaining Risks

The smoke test also identified several noncritical issues to monitor in the full benchmark:

- occasional mild relation strengthening, such as `correspondingly`;
- small scope expansion, such as `a series of robustness tests`;
- incomplete calibration of literature-coverage claims such as `few studies`;
- literature synthesis that sometimes remains a compressed list rather than a true cross-study synthesis;
- incomplete specification of the validation needed after simulation-based evidence.

## MVP Gate Decision

The internal smoke-test gate passed:

- preferred over baseline target: met;
- no observed skill critical failures: met;
- meaning preservation in the reviewed cases: met;
- unsupported-content control: met;
- template reduction in applicable cases: met.

Decision: freeze this version for evaluation and proceed to the full 80-case benchmark without revising the skill between pilot and full-run generation.

## Interpretation Boundary

Supported conclusion:

> In this 10-case manual smoke test, the skill was preferred in eight cases, tied in two ceiling-effect cases, and produced no observed critical meaning, causality, or fabrication failures.

Not yet supported:

> The skill has been comprehensively validated across study designs or production settings.

That stronger conclusion requires completion of the blinded 80-case benchmark and reporting by rhetorical task, study design, and failure type.
