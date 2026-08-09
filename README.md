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

## Claude / Model Compatibility

This repository follows the core Anthropic Agent Skills pattern: a self-contained skill directory with an uppercase `SKILL.md`, YAML frontmatter containing `name` and `description`, and supporting files in `references/`. Anthropic describes Agent Skills as portable folders of instructions and resources that Claude can discover and load when relevant.

### Claude Code

Claude Code can use the skill either directly from this repository or as a project-scoped/user-scoped Agent Skill.

Clone the repository:

```bash
git clone https://github.com/HairuFan/research-writing-rhetorical-skill.git
cd research-writing-rhetorical-skill
```

For a project-scoped installation, copy the skill directory into the project's `.claude/skills/` directory:

```bash
mkdir -p .claude/skills
cp -R skill/research-writing-rhetorical-skill .claude/skills/research-writing-rhetorical-skill
```

For a user-scoped installation, copy it into `~/.claude/skills/`:

```bash
mkdir -p ~/.claude/skills
cp -R skill/research-writing-rhetorical-skill ~/.claude/skills/research-writing-rhetorical-skill
```

Start a new Claude Code session after installation so the skill can be discovered.

Example invocation:

```text
Use the Research Writing Rhetorical Skill to revise the following Discussion paragraph.

Study design: observational
Output mode: clean

Preserve substantive meaning, uncertainty, scope, citations, and causal status.
Do not invent findings, mechanisms, methods, novelty, or application settings.

[Paste text]
```

For repository files:

```text
Apply the Research Writing Rhetorical Skill to manuscript.md.

Audit:
- rhetorical coherence
- claim calibration
- unsupported specificity
- template repetition
- meaning preservation

Do not change numerical results or citations.
```

The filename must remain exactly `SKILL.md`. The `name` and `description` metadata help Claude determine when the skill is relevant.

Anthropic currently supports Agent Skills across Claude.ai, Claude Code, the Claude Agent SDK, and the Claude Developer Platform. See Anthropic's [Agent Skills overview](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills) and the [Anthropic Skills repository](https://github.com/anthropics/skills).

### Model compatibility and evaluation scope

The skill is designed to be model-agnostic at the instruction layer, but model behavior can vary.

**Empirically evaluated:**

- Claude Sonnet 5 — used as the generator in the v1.0.0 paired benchmark.

**Supported usage patterns:**

- Claude Code / Agent Skills;
- Claude.ai custom skills where available;
- Claude API / Agent SDK workflows that support Agent Skills;
- ChatGPT Skills;
- Codex;
- project or agent environments that can load `SKILL.md` and its reference files.

The published v1.0.0 benchmark results apply to the evaluated Claude Sonnet 5 generation setup. They should not be assumed to generalize unchanged to every Claude model, ChatGPT model, or agent environment. Cross-model validation is a planned direction for future releases.

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