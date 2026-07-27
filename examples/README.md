# Capability Demonstration Cases

These examples show the intended difference between generic rewriting and rhetorical revision. They are also regression cases for future prompt and rule changes.

## 1. Generic framing to a specific problem

**Section:** Introduction  
**Capability:** naturalness, specificity, density

### Before

> In recent years, artificial intelligence has become increasingly important in many areas of society. It is important to note that AI fairness has also received growing attention from researchers and practitioners.

### With skill

> The expanding use of automated decision systems in hiring, lending, and public services has made group-level disparities a central deployment concern.

### Audit summary

- Meaning preservation: Pass
- Generic framing: Removed
- Specificity: Improved
- Unsupported content: None, assuming the listed settings are part of the manuscript context

---

## 2. Prior work to a precise research gap

**Section:** Introduction  
**Capability:** concession, literature-claim calibration, gap specification

### Before

> Previous studies have developed many fairness metrics. However, few studies have examined actionability. Therefore, more research is needed in this area.

### With skill

> Although prior work has substantially advanced the measurement of algorithmic disparities, it offers comparatively limited guidance on when an observed gap warrants intervention.

### Audit summary

- Meaning preservation: Pass
- Mechanical transitions: Removed
- Gap type: Decision gap
- Citation need: Literature-wide claim requires support

---

## 3. Gap to study objective

**Section:** Introduction  
**Capability:** study positioning, contribution specificity

### Before

> There is a gap in the literature regarding uncertainty. This study aims to fill this gap by proposing a new framework.

### With skill

> To connect disparity measurement with intervention decisions, we develop a framework that jointly considers effect magnitude, statistical uncertainty, sample adequacy, and deployment cost.

### Audit summary

- Meaning preservation: Needs author review if the four components were not specified elsewhere
- Generic gap language: Removed
- Study action: Made explicit
- Novelty inflation: Avoided

---

## 4. Study listing to literature synthesis

**Section:** Literature review  
**Capability:** synthesis, comparison, paragraph coherence

### Before

> Smith found that reweighting reduced demographic parity gaps. Jones found that equalized odds improved true positive rate parity. Brown found that adversarial debiasing sometimes reduced accuracy.

### With skill

> Across mitigation strategies, prior studies report a recurring trade-off between disparity reduction and predictive performance. Reweighting and post-processing often improve selected group metrics, whereas adversarial approaches produce less consistent accuracy effects across datasets.

### Audit summary

- Rhetorical move: Synthesize evidence
- Repetitive study-by-study structure: Removed
- Meaning preservation: Needs source check because the synthesis generalizes across studies
- Citation need: Required

---

## 5. Mechanical steps to analytical sequence

**Section:** Methods  
**Capability:** sequencing, methodological purpose, concise signposting

### Before

> First, we conducted descriptive analysis. Second, we estimated the models. Third, we conducted robustness analysis. Finally, we compared the results.

### With skill

> The analysis proceeded from sample and baseline characterization to primary model estimation and robustness evaluation across alternative specifications.

### Audit summary

- Sequence preserved: Pass
- Repetitive markers: Removed
- Density: Improved
- Specificity: Limited to information present in the source

---

## 6. Repetitive result reporting to dense prose

**Section:** Results  
**Capability:** result navigation, compression, repetition control

### Before

> The results show that SAP had a lower false-action rate. The results also show that SAP had a lower missed-bias rate. Furthermore, the results show that SAP had the lowest cost.

### With skill

> SAP reduced both false actions and missed biases relative to the comparison rules and achieved the lowest expected decision cost.

### Audit summary

- Meaning preservation: Pass if all comparisons use the same baseline
- Repetition: Removed
- Result distinctions: Preserved
- Claim calibration: Descriptive

---

## 7. Result separated from interpretation

**Section:** Results and Discussion boundary  
**Capability:** section fit, evidence alignment

### Before

> Only 22.57% of threshold-crossing gaps satisfied all mitigation criteria, which proves that traditional fairness thresholds are fundamentally unreliable.

### With skill — Results

> Only 22.57% of threshold-crossing gaps satisfied all mitigation criteria.

### With skill — Discussion

> This pattern indicates that threshold crossing alone provides an incomplete basis for intervention because many observed gaps lack sufficient precision or sample support.

### Audit summary

- Descriptive result: Preserved
- Unsupported proof claim: Removed
- Interpretation: Calibrated
- Additional mechanism detail: Must be supported by the analysis

---

## 8. Unsupported causality to evidence-aligned interpretation

**Section:** Discussion  
**Study design:** Observational  
**Capability:** claim calibration, causal-status preservation

### Before

> Experience causes salary inequality because women receive lower returns to experience than men.

### With skill

> Salary growth was less strongly associated with experience for women than for men, a pattern consistent with unequal returns across career stages.

### Audit summary

- Causal overstatement: Corrected
- Direction of comparison: Preserved
- Mechanism: Not claimed as identified
- Study-design fit: Improved

---

## 9. Boilerplate limitation to a precise boundary

**Section:** Limitations  
**Capability:** scope, transportability, concise qualification

### Before

> Like all studies, this study has several limitations that should be acknowledged. First, we only used simulated data. Therefore, the findings may not be generalizable to the real world, and future studies should use real-world data.

### With skill

> Because the framework is evaluated primarily through simulation, the results establish its behavior under controlled data-generating conditions rather than its effectiveness in live deployment. Validation on operational audit data is therefore needed to assess transportability.

### Audit summary

- Boilerplate: Removed
- Supported inference: Defined
- Unsupported inference: Defined
- Future work: Linked to the limitation

---

## 10. Over-softened reviewer response to visible action

**Section:** Reviewer response  
**Capability:** respectful directness, action visibility, reduced over-explanation

### Before

> We sincerely thank the reviewer for this very insightful and valuable comment. We completely agree that this is an important issue that needed to be addressed more clearly. Therefore, in response to the reviewer’s helpful suggestion, we have now added additional explanations and analyses to the revised manuscript.

### With skill

> Thank you for raising this point. We revised Section 4.2 to clarify the baseline specification and added a sensitivity analysis using alternative subgroup thresholds. The new results are reported in Table S3 and do not change the main conclusion.

### Audit summary

- Tone: Respectful and direct
- Revision action: Visible
- Location and consequence: Explicit
- Meaning preservation: Needs author review unless Section 4.2 and Table S3 are factual

## Use in regression testing

A future version should continue to:

1. remove generic framing without inventing facts;
2. distinguish contrast from concession;
3. connect gaps to concrete study actions;
4. synthesize rather than list studies;
5. express methods as analytical sequences;
6. compress repeated results safely;
7. separate observation from interpretation;
8. calibrate claims to study design;
9. state limitations as evidential boundaries;
10. make reviewer-response actions visible.
