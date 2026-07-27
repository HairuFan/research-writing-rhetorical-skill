---
name: research-writing-rhetorical-skill
description: >
  Diagnose and revise academic and research writing for rhetorical coherence,
  paragraph transitions, evidence-aligned claim strength, naturalness,
  concision, and reduction of formulaic AI-style prose. Use when a user asks
  to improve, tighten, restructure, audit, or professionally rewrite a
  research sentence, paragraph, manuscript section, literature review,
  discussion, limitation, conclusion, or reviewer response.
license: Apache-2.0
metadata:
  author: Hairu Fan
  version: "1.0.0-mvp"
---

# Research Writing Rhetorical Skill

## Purpose

Improve research prose by reasoning about the argument before changing the language.
The skill is not a synonym replacer, grammar checker, citation generator, plagiarism
checker, full-paper generator, or AI-detector bypass tool.

Core sequence:

`diagnose -> revise -> calibrate -> audit`

## Supported tasks

- revise a sentence without changing its substantive meaning;
- repair transitions between adjacent sentences;
- bridge two paragraphs;
- audit paragraph-level rhetorical flow;
- audit a manuscript section;
- calibrate claims to the study design and evidence;
- reduce formulaic AI-style prose and unnecessary explanation;
- revise reviewer responses for respectful directness.

## Supported sections

Abstract, introduction, literature review, theory, methods, results, discussion,
limitations, conclusion, and reviewer response.

## Required workflow

Before returning a revision:

1. Identify the user's task and the manuscript section.
2. Infer the study design only when the text supports the inference. Otherwise mark it as unknown.
3. Identify the rhetorical move performed by each relevant sentence.
4. Determine the logical relation between adjacent ideas.
5. Identify the evidence level required by each claim.
6. Diagnose repetition, vagueness, mechanical signposting, and over-explanation.
7. Revise while preserving the author's substantive meaning and intended directness.
8. Perform the meaning-preservation audit.
9. Perform the claim-calibration audit.
10. Perform the naturalness and density audit.
11. Revise again if any critical requirement fails.
12. Return the clean revision and only the most useful diagnostic notes.

## Rhetorical reasoning

Use `references/rhetorical-taxonomy.md` to classify the communicative function.
Do not add a transition marker until the logical relation is clear.

Common relations include continuation, contrast, concession, qualification,
distinction, cause, consequence, synthesis, gap-to-objective,
result-to-interpretation, interpretation-to-implication, and
limitation-to-future-work.

Prefer the least intrusive structure that makes the relation clear:

1. marker-free lexical continuity;
2. parallel or contrastive syntax;
3. subordinate clause;
4. explicit transition marker;
5. separate bridge sentence only when needed.

Do not place an explicit connector in every sentence.

## Claim calibration

Read `references/claim-calibration.md` whenever the text makes causal,
mechanistic, novelty, generalizability, significance, or literature-wide claims.

Default principles:

- observational evidence supports association more readily than causation;
- cross-sectional evidence does not establish temporal order;
- simulation establishes behavior under specified assumptions, not live-deployment effectiveness;
- qualitative evidence supports interpreted processes and experiences, not population prevalence by default;
- a nonsignificant estimate is not proof of no effect;
- one dataset does not establish universal generalizability;
- do not claim that no prior work exists without systematic support.

## Naturalness and density

Read `references/naturalness-audit.md` for prose that is repetitive, generic,
over-explained, or explicitly described as AI-style.

Target style:

- natural, professional, and non-template-like;
- specific to the research question, design, variables, and decision context;
- high in substantive information and low in filler;
- varied only where variation improves clarity;
- concise without deleting uncertainty, limitations, or necessary technical detail.

Do not make prose longer merely to sound academic.
Do not introduce artificial imperfections to appear human.

## Meaning preservation

Read `references/meaning-preservation.md` before finalizing every revision.
The revised text must preserve direction, magnitude, uncertainty, statistical
status, causal status, comparison group, population, temporal order, scope,
boundary conditions, and author position when these are present.

Critical failures include invented findings, citations, methods, mechanisms,
novelty, changed significance, strengthened causality, reversed comparisons,
and removed limitations.

## Output modes

### Clean mode

Use by default when the user simply asks for revision.

```markdown
## Revised text

[revision]

## Key revision note

[one concise note, only when useful]
```

### Diagnostic mode

Use when the user asks why the text was changed.

```markdown
## Revised text

[revision]

## Rhetorical diagnosis

[move and logical relation]

## Main issues

[only the important issues]

## Claim calibration

[include only when relevant]
```

### Full audit mode

Use when the user explicitly requests an audit.

```markdown
## Revised text

[revision]

## Audit summary

- Meaning preservation: Pass / Needs review
- Rhetorical fit: Pass / Needs review
- Claim calibration: Pass / Needs review
- Naturalness and density: Pass / Needs review
- Template repetition: Corrected / None found / Needs review
- Citation or evidence need: [specific note]
```

Do not present a detector score or a pseudo-precise quality score as objective truth.

## AI-detection notice

The skill reduces formulaic AI-style patterns through rhetorical specificity,
controlled syntactic variation, concision, and contextual alignment. It does not
guarantee an AI-detector outcome and must not claim to be undetectable,
detector-proof, or guaranteed to obtain a particular score.

Detector results differ across tools and can contain false positives or false
negatives. At the end of substantial revisions, remind the user to review factual
and statistical accuracy, meaning preservation, citations, attribution, and the
relevant institutional, publisher, or journal policy on AI-assisted writing.

## Prohibited behavior

Never:

- invent citations, findings, methods, mechanisms, or contributions;
- strengthen causality or generalizability without support;
- replace precise technical language with vague academic language;
- add an explicit transition to every sentence;
- return long synonym lists instead of a best-fit revision;
- use inflated novelty claims such as “first,” “unprecedented,” or “groundbreaking” without evidence;
- remove qualifications merely to improve concision;
- describe the output as AI-safe, human-written, undetectable, or detector-proof;
- optimize for bypassing academic integrity systems.

## Final silent audit

Before answering, verify:

1. The substantive meaning is preserved.
2. No unsupported content has been added.
3. Claim strength matches the evidence and study design.
4. The rhetorical move fits the manuscript section.
5. Adjacent ideas have a clear logical relationship.
6. Generic framing and mechanical signposting have been removed where unnecessary.
7. Each sentence contributes new analytical information.
8. The prose is concise but retains necessary uncertainty and scope.
9. Sentence variation is purposeful rather than decorative.
10. The final text reads as a context-specific research argument rather than a reusable template.
