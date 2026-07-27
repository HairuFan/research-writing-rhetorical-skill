# Research Writing Rhetorical Skill

An open-source skill for rhetorical diagnosis, evidence-aligned claim calibration, paragraph coherence, and natural, high-density research writing.

Rather than replacing transition words mechanically, the skill reasons about manuscript section, rhetorical purpose, logical relation, study design, evidence strength, and surrounding context before revising the text.

## v1.0.0

Version 1.0.0 is the first stable evaluated release. It includes:

- a complete `SKILL.md` workflow and output contract;
- a rhetorical-move and logical-relation taxonomy;
- study-design-aware claim-calibration rules;
- a naturalness, density, and anti-template audit;
- a meaning-preservation audit with critical-failure gates;
- ten Before / With Skill demonstration cases;
- an 80-case paired evaluation benchmark and scoring rubric.

## Core workflow

`diagnose -> revise -> calibrate -> audit`

The skill is designed to:

- repair transitions based on the actual logical relation;
- synthesize prior research rather than list studies;
- separate results from interpretation;
- align causal and mechanistic language with the research design;
- remove formulaic AI-style framing, repetition, and over-explanation;
- preserve the author's findings, uncertainty, scope, and substantive position.

## Installation and use

### ChatGPT Skills

1. Download the latest release from the repository's [Releases page](https://github.com/HairuFan/research-writing-rhetorical-skill/releases).
2. Extract the release archive.
3. Compress the contents of `skill/research-writing-rhetorical-skill/` so that `SKILL.md` is at the root of the ZIP file alongside the `references/` folder.
4. In ChatGPT, open **Skills**, select **New skill**, and choose **Upload from your computer**.
5. Upload the skill ZIP and complete installation.

Skills availability may depend on the user's ChatGPT account and workspace settings. See the official [Skills in ChatGPT documentation](https://help.openai.com/en/articles/20001066-skills-in-chatgpt).

Example prompt:

```text
Use the Research Writing Rhetorical Skill to revise the following paragraph.

Section: Discussion
Study design: Observational
Output mode: Clean

Preserve substantive meaning, scope, evidence strength, and causal status.
Do not add citations, findings, methods, mechanisms, or application settings.

[Paste text]
```

### Codex

Clone the repository and ask Codex to follow the skill definition:

```bash
git clone https://github.com/HairuFan/research-writing-rhetorical-skill.git
cd research-writing-rhetorical-skill
```

Example prompt:

```text
Apply the skill defined in
skill/research-writing-rhetorical-skill/SKILL.md

to revise manuscript.md.

Preserve meaning, uncertainty, citations, numerical results, and causal status.
```

### ChatGPT Project fallback

Users without direct Skills access can create a ChatGPT Project, upload `SKILL.md` and the files in `references/`, and add this project instruction:

```text
For academic-writing revision requests, follow the uploaded Research Writing Rhetorical Skill files. Prioritize meaning preservation, claim calibration, rhetorical fit, naturalness, and unsupported-content control.
```

ChatGPT Projects can combine uploaded reference files with project-specific instructions. See the official [Projects in ChatGPT documentation](https://help.openai.com/en/articles/10169521-projects-in-chatgpt).

## Evaluation

Version 1.0.0 was evaluated on 80 paired baseline-versus-skill cases covering 10 rhetorical tasks and 8 study-design conditions.

| Outcome | Cases | Share |
|---|---:|---:|
| Skill preferred | 43 | 53.75% |
| Baseline preferred | 21 | 26.25% |
| Tie | 16 | 20.00% |
| Skill critical failures | 0 | 0.00% |

The skill won 67.19% of non-tied decisions and had a 73.75% non-loss rate. Evaluation used two blinded Gemini 3.6 Flash judge runs, followed by human adjudication of all inter-run disagreements and human review of every case in which both judge runs preferred the baseline.

The strongest gains appeared in claim calibration, evidential-boundary writing, gap-to-objective transitions, reviewer responses, and template reduction. Known limitations include occasional boilerplate substitution, unsupported narrowing, overuse of contrast markers, and loss of parallel structure. See the [v1.0.0 evaluation report](evals/results/v1.0.0-evaluation-report.md).

## Share your experience

Used the skill on a manuscript paragraph, literature review, limitation, discussion, or reviewer response? Share what worked, what remained awkward, and whether the original meaning and claim strength were preserved.

Use the [user feedback issue template](https://github.com/HairuFan/research-writing-rhetorical-skill/issues/new?template=user-feedback.yml) to report:

- the manuscript section or writing task;
- what improved;
- what did not work well;
- whether meaning, scope, and evidential strength were preserved;
- an optional before/after example that you are permitted to share.

Do not post confidential manuscripts, unpublished findings, reviewer-confidential material, personal data, or copyrighted text that you do not have permission to share.

## Files

- [`SKILL.md`](skill/research-writing-rhetorical-skill/SKILL.md)
- [`Rhetorical taxonomy`](skill/research-writing-rhetorical-skill/references/rhetorical-taxonomy.md)
- [`Claim calibration`](skill/research-writing-rhetorical-skill/references/claim-calibration.md)
- [`Naturalness audit`](skill/research-writing-rhetorical-skill/references/naturalness-audit.md)
- [`Meaning-preservation audit`](skill/research-writing-rhetorical-skill/references/meaning-preservation.md)
- [`10 demonstration cases`](examples/README.md)
- [`80-case evaluation benchmark`](evals/benchmark-mvp.yaml)
- [`Evaluation rubric`](evals/rubric.md)
- [`v1.0.0 evaluation report`](evals/results/v1.0.0-evaluation-report.md)
- [`Release notes`](RELEASE_NOTES.md)

## AI-detection notice

This project reduces formulaic AI-style prose through rhetorical specificity, controlled syntactic variation, concision, and contextual alignment. It does not guarantee an AI-detector result and does not claim to be undetectable, detector-proof, or safe under every detection tool.

AI detectors differ across tools and may produce false positives or false negatives. Review the final text for factual and statistical accuracy, meaning preservation, citations, attribution, and compliance with relevant institutional, publisher, or journal policies on AI-assisted writing.

## License

Apache License 2.0.