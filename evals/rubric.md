# Evaluation Rubric

Evaluate the same input under two conditions:

1. base model without the skill;
2. the same model with the skill enabled.

Use blind review whenever possible.

## Dimensions

### 1. Meaning preservation — 20 points

- 20: all material claims, qualifiers, comparisons, and boundaries preserved;
- 15: minor wording ambiguity with no substantive change;
- 10: one material qualification weakened or added;
- 5: substantial drift;
- 0: critical failure.

### 2. Rhetorical fit — 15 points

- 15: the revision performs the intended move and fits the manuscript section;
- 10: generally appropriate but partially misaligned;
- 5: fluent but performs the wrong move;
- 0: unusable for the section.

### 3. Logical coherence — 15 points

- 15: relation between ideas is explicit and accurate;
- 10: relation is understandable but weakly expressed;
- 5: connector or structure misrepresents the logic;
- 0: contradiction or broken progression.

### 4. Claim calibration — 15 points

- 15: strength matches design and evidence;
- 10: slightly over- or under-calibrated;
- 5: material causal, mechanistic, novelty, or generalizability overstatement;
- 0: critical inference error.

### 5. Naturalness and specificity — 15 points

- 15: natural, professional, context-specific prose;
- 10: mostly natural with some generic wording;
- 5: formulaic, vague, or over-polished;
- 0: incoherent or misleading.

### 6. Density and concision — 10 points

- 10: every sentence contributes analytical information;
- 7: minor redundancy;
- 4: substantial filler or over-explanation;
- 0: unusably verbose or compressed beyond clarity.

### 7. Syntactic variation — 5 points

- 5: purposeful variation supports clarity;
- 3: minor repetition;
- 1: strongly repetitive cadence;
- 0: variation damages readability.

### 8. Template reduction — 5 points

- 5: formulaic framing and mechanical signposting removed;
- 3: partial improvement;
- 1: templates remain prominent;
- 0: more formulaic than the input.

## Critical errors

Any critical error overrides the numeric total and marks the case as failed:

- invented citation, result, method, mechanism, dataset, or contribution;
- changed numerical value or comparison direction;
- changed statistical significance;
- unsupported strengthening of causality;
- removal of a material limitation;
- fabricated novelty;
- detector-evasion claim.

## MVP pass criteria

A case passes when:

- total score is at least 85/100;
- meaning preservation is at least 18/20;
- claim calibration is at least 13/15;
- rhetorical fit is at least 13/15;
- critical errors equal zero.

## Paired evaluation fields

Record:

- case ID;
- model and version;
- prompt condition: base or with-skill;
- output;
- dimension scores;
- critical-error flags;
- reviewer preference;
- reviewer notes.

## MVP targets

- at least 70% of with-skill outputs preferred over baseline;
- at least 95% meaning-preservation pass rate;
- at least 90% claim-calibration pass rate;
- fewer than 2% critical errors;
- at least 80% success on template-reduction cases.

These are project release targets, not claims that the rubric is an objective measure of writing quality.
