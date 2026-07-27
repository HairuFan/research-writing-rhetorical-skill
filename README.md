# Research Writing Rhetorical Skill

An open-source skill for rhetorical diagnosis, evidence-aligned claim calibration, paragraph coherence, and natural, high-density research writing.

Rather than replacing transition words mechanically, the skill reasons about manuscript section, rhetorical purpose, logical relation, study design, evidence strength, and surrounding context before revising the text.

## v1 foundation MVP

The current foundation includes:

- a complete `SKILL.md` workflow and output contract;
- a rhetorical-move and logical-relation taxonomy;
- study-design-aware claim-calibration rules;
- a naturalness, density, and anti-template audit;
- a meaning-preservation audit with critical-failure gates;
- ten Before / With Skill demonstration cases;
- an 80-case paired evaluation MVP and scoring rubric.

## Core workflow

`diagnose -> revise -> calibrate -> audit`

The skill is designed to:

- repair transitions based on the actual logical relation;
- synthesize prior research rather than list studies;
- separate results from interpretation;
- align causal and mechanistic language with the research design;
- remove formulaic AI-style framing, repetition, and over-explanation;
- preserve the author's findings, uncertainty, scope, and substantive position.

## Files

- [`SKILL.md`](skill/research-writing-rhetorical-skill/SKILL.md)
- [`Rhetorical taxonomy`](skill/research-writing-rhetorical-skill/references/rhetorical-taxonomy.md)
- [`Claim calibration`](skill/research-writing-rhetorical-skill/references/claim-calibration.md)
- [`Naturalness audit`](skill/research-writing-rhetorical-skill/references/naturalness-audit.md)
- [`Meaning-preservation audit`](skill/research-writing-rhetorical-skill/references/meaning-preservation.md)
- [`10 demonstration cases`](examples/README.md)
- [`80-case evaluation MVP`](evals/benchmark-mvp.yaml)
- [`Evaluation rubric`](evals/rubric.md)

## AI-detection notice

This project reduces formulaic AI-style prose through rhetorical specificity, controlled syntactic variation, concision, and contextual alignment. It does not guarantee an AI-detector result and does not claim to be undetectable, detector-proof, or safe under every detection tool.

AI detectors differ across tools and may produce false positives or false negatives. Review the final text for factual and statistical accuracy, meaning preservation, citations, attribution, and compliance with relevant institutional, publisher, or journal policies on AI-assisted writing.

## License

Apache License 2.0.
