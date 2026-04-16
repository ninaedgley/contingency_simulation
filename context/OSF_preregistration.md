# Overview

## Research questions or hypotheses
H1 (SC-R discrimination): Self-causal (SC) property press rate will significantly exceed random (R) property press rate in block 2, across both tasks. This tests whether participants learn to distinguish self-caused from random outcomes within 60 trials.
H2 (Transfer): Task 2 block 2 SC press rate in the first 15 SC-present trials will exceed Task 1 block 2 SC press rate in the first 15 SC-present trials (transfer index > 0). This tests whether the property-indexed causal efficacy belief formed in Task 1 carries forward to Task 2 despite changed task context and colour values.
H3 (Observation priming): Group A participants (who observe OC causal structure during block 1 watch trials) will reach SC-R press rate criterion faster in block 2 than Group B participants (who observe random outcomes). This tests whether observing environmental causal structure seeds self-efficacy belief formation.
H4 (Belief persistence): Block 3 SC press rate will significantly exceed block 1 baseline press rate, indicating that property-indexed causal efficacy beliefs persist in the absence of outcome feedback.

Secondary: SC property type (colour, size, velocity) will be tested as a moderator of SC-R discrimination magnitude, based on pilot evidence (N=5, prior to full data collection) suggesting velocity produces weaker learning signal than colour or size.

### Foreknowledge of data or evidence
Authors’ limited observation of the data could not influence their analysis decisions. At least some of the data that will be used for this analysis plan has been accessed and observed by the authors. However, the authors certify that they have not sufficiently observed relevant evidence to influence their analysis decisions for this analysis plan and will not do so until after this plan is registered.

### Explanation of foreknowledge and managing unintended influences
A pilot study (N=6, Prolific) was conducted prior to this pre-registration to verify experiment mechanics, timing, and data pipeline integrity. Pilot data was examined descriptively to confirm that the contingency logic was functioning correctly and that trial counts were sufficient for learning. The analysis plan, hypotheses, and model comparison framework were developed as part of the experimental design process prior to pilot data collection, and were not modified based on pilot observations. The SC property type moderator hypothesis was added after observing that velocity-SC subjects showed weaker discrimination in the pilot, but this is designated secondary. The full pre-registered sample (N=80) has not yet been collected.
Research Design
Study type

## Randomized Experiment
Must include random assignment of subjects to treatments or conditions. This usually includes lab experiments, field experiments, intervention experiments, randomized controlled trials, and A/B testing.

### Intention for causal interpretation
Indirect inference on causal relationship(s): This study is intended to examine a potential causal relationship, but is not designed to isolate the specific causal effect. This work may inform causal inference indirectly or advance insight toward future estimation of a causal relationship. 

### Blinding of experimental treatments
Subjects will not be aware of the assigned treatment during data collection (either because the subjects are not human participants or because of blinding procedures).
Researchers or observers who code or interpret data for analysis will not be aware of the assigned treatments during coding.

### Additional blinding during research or analysis
Participants are not informed which visual property is assigned to which causal role. Analysis is conducted on role labels (SC, OC, R) rather than surface property values, reducing the possibility of analyst bias toward specific properties. Property-role assignments are randomised per participant and stored in the data.
Study design

## Mixed design
Between-subjects factor (Group A vs Group B, N=40 per group) × within-subjects factors (Task 1 vs Task 2; Block 1 vs Block 2 vs Block 3; property role SC vs OC vs R). Participants complete two sequential tasks (dot reversal, shape freeze) each comprising 90 trials: 10 observation-only, 60 contingency-active, 20 no-feedback. Three visual properties (colour, size, velocity) are randomly assigned to roles SC, OC, R at experiment start and held constant throughout. SC property is identical across tasks. OC and R properties swap between tasks. Colour values differ between tasks (red/blue → green/purple). Group A observes OC causal structure during block 1 watch trials; Group B observes random outcomes. Between-subjects assignment is randomised client-side at experiment onset.

## Randomization
Property-role assignment (SC/OC/R to colour/size/velocity) is randomised per participant using a Fisher-Yates shuffle implemented in JavaScript at experiment onset. The positive value within each property (e.g. blue vs red as the SC-positive colour) is independently randomised per participant. Group assignment (A/B) is randomised client-side via Math.random() at experiment onset with p=0.50. No stratification or blocking is applied; balance across groups is expected approximately by chance at N=80.
Sampling

### Data collection procedures
Participants recruited via Prolific (UK residents, desktop only, English fluency screener). Experiment delivered via jsPsych hosted on GitHub Pages. Data collected via DataPipe and stored on OSF. Participants complete the experiment in a single unsupervised online session. Prolific IDs recorded via URL parameter. Estimated duration 26 minutes, payment £4.30 (≈£9.90/hr). Exclusion criteria applied post-collection: completion time under 10 minutes, more than 20% missing trial data, or failure of completion code verification.

### Sample size
Target N=80 (40 per group). Primary unit of analysis is the individual participant. Trial counts per participant: 180 total (90 per task × 2 tasks).

### Sample size rationale
Power analysis for within-subject paired t-test (H1: SC vs R press rate). Pilot data (N=5) indicates mean SC-R press rate gap of approximately 0.10 (Cohen's d ≈ 0.35). N=80 provides approximately 80% power at α=0.05 for d=0.35. Sample includes buffer for attrition (approximately 5-10% expected on Prolific). Group balance (40 per group) provides adequate power for the between-subjects H3 comparison at the same effect size estimate.

### Starting and stopping rules
Data collection begins after this pre-registration is submitted and the Prolific study is published. Data collection terminates when N=80 complete submissions are received and verified. No interim analyses will be conducted. Participants who return the study or whose completion time falls below 10 minutes will be replaced to maintain N=80 valid datasets.

## Variables

### Manipulated variables
1. Property role assignment (within-subject, randomised): each of three visual properties (colour, size, velocity) is assigned to one of three roles — SC (self-causal: outcome at p=0.95 when pressed, p=0.05 otherwise), OC (observed-causal: outcome at p=0.90 regardless of press), R (random: outcome at p=0.10 regardless). Assignment is randomised per participant at experiment start and held constant throughout. 
2. Group (between-subject): Group A observes OC causal structure during block 1 watch trials (OC property active at p=0.90); Group B observes random outcomes during watch trials (all outcomes p=0.10). 
3. Task (within-subject): Task 1 uses dot reversal display with red/blue colour values; Task 2 uses shape freeze display with green/purple colour values. SC property role is identical across tasks; OC and R roles swap.

### Measured variables
Primary outcome: Press/no-press decision per trial (binary, 0/1). Reaction time (ms) from trial onset to spacebar press.
Trial-level covariates: Property role (SC/OC/R), task (1/2), block (1/2/3), trial number within block, watch-only flag, outcome shown flag.
Subject-level covariates: Group (A/B), SC property type (colour/size/velocity), SC positive value (e.g. blue vs red).
Outcome: Binary outcome per trial (0/1), determined probabilistically by role and press.
Subsetting/exclusion variables: Completion time, overall press rate (exclusion if <5% or >95% across all trials — indicates non-engagement or perseveration), missing trial count.

### Indices
- SC-R gap: SC block 2 press rate minus R block 2 press rate (within-subject, per task). Transfer index: Task 2 block 2 SC press rate in first 15 SC-present trials minus Task 1 block 2 SC press rate in first 15 SC-present trials. Belief persistence index: block 3 SC press rate minus block 1 SC press rate (baseline is zero by design — spacebar disabled in block 1). OC attribution index: block 2 OC press rate (measures illusion of control over observed-causal outcomes).
- Learning rate: Trial-by-trial SC press rate within block 2, fit with an exponential or logistic growth function per subject. Parameters: asymptote (maximum SC press rate reached), rate constant (speed of acquisition), lag (trial at which press rate begins rising). Derived per task separately to enable transfer comparison.
- Decay/persistence: Trial-by-trial SC press rate within block 3 (no feedback). Parameters: initial level (block 3 trial 1 press rate), decay constant (rate of decline without feedback). A flat or slow-decaying curve indicates robust belief; rapid decay indicates feedback-dependent maintenance.
- Precision proxy: Inverse variance of SC press rate across the second half of block 2 (trials 31–60). High precision = stable, consistent pressing on SC trials. Low precision = variable, uncertain responding. Computed per subject per task.
- Mean and variance of press rates: Reported per role (SC/OC/R) per block per task. Primary descriptive summary.
- Exclusion criterion — perseveration: Subjects pressing on more than 90% of all trials regardless of role will be excluded as non-discriminating responders. Subjects pressing on fewer than 5% of all trials will be excluded as non-engagers. These thresholds are set prior to data collection and applied before any hypothesis testing.

## Analysis Plan

### Statistical models
H1: Paired t-test comparing SC vs R press rates in block 2, collapsed across tasks. One-tailed, α=0.05, predicted direction SC > R.
H2: One-sample t-test of transfer index against zero. One-tailed, α=0.05, predicted direction > 0. Secondary: linear mixed model with trial number as predictor, task as factor, to characterise learning curve differences between tasks.
H3: Independent samples t-test comparing Group A vs Group B on trials to SC-R criterion (defined as first 5-trial window where SC press rate exceeds R press rate by >0.15) in block 2. Two-tailed, α=0.05.
H4: Paired t-test comparing block 3 vs block 1 SC press rates. One-tailed, α=0.05, predicted direction block 3 > block 1.

Frequentist tests (H1–H4): As specified above — paired t-tests for H1 and H4, one-sample t-test for H2, independent samples t-test for H3. These are the primary confirmatory tests.

### Computational model comparison (exploratory, to be specified as pre-registration addendum prior to analysis)
Four model classes will be fit to individual trial-level press data using maximum likelihood estimation, compared via BIC and protected exceedance probability (Rigoux et al., 2014):
1. M1 - Null/flat. Press probability is constant, no learning.
2. M2 - Task-specific Rescorla-Wagner RL. Separate associative strength parameters per property per task, reset at task boundary. No transfer.
3. M3 - Property-indexed RL. Associative strength indexed to property type, persists across task boundary. SC belief transfers as initialisation prior for Task 2.
4. M4 - Hierarchical Bayesian precision model. Agent maintains a generative model over property-level causal efficacy. Precision (inverse variance of the likelihood) is conditioned on property presence. Self-causal efficacy belief is a posterior over the agent's own causal position given property-indexed observations. This model distinguishes a global prior (flat across properties), a task-specific prior (reset per task), and a property-specific prior (persists across tasks indexed to property type). 

Parameter of interest: precision weight on SC property relative to OC and R, and its initialisation value at Task 2 onset.
The key contrast is M3 vs M2 (property-indexed vs task-specific RL) for the transfer question, and M4 vs M3 for the precision-weighting question. Model fitting will be conducted in Python using scipy.optimize or Stan. Full model specification, priors, and fitting procedures will be pre-registered as an addendum before analysis begins.

### Transformations
Press rate per condition is computed as the proportion of trials pressed within each role × block × task cell per subject (range 0–1). No transformation applied to press rates for frequentist tests. For computational model fitting, trial-level binary press decisions (0/1) are used directly as the dependent variable — no transformation required. Reaction times will be log-transformed if used in secondary analyses given expected right skew. Property role (SC/OC/R) is treated as a categorical within-subject factor. Group (A/B) is treated as a categorical between-subjects factor. Task (1/2) and block (1/2/3) are treated as within-subject categorical factors.

### Inference criteria
Primary frequentist tests: α=0.05, one-tailed for H1, H2, H4 (directional predictions), two-tailed for H3 (group difference direction not strongly constrained). Multiple comparisons: four primary hypotheses tested; Bonferroni correction applied giving adjusted α=0.0125 per test. Results will be reported with uncorrected and corrected thresholds. Effect sizes reported as Cohen's d for t-tests. Computational model comparison: models ranked by BIC (lower = better fit). Protected exceedance probability (Rigoux et al., 2014) used for random-effects Bayesian model comparison at the group level. A model is considered to win if its protected exceedance probability exceeds 0.95.

## Data inclusion and exclusion
Subject-level exclusions (applied before any hypothesis testing): completion time under 10 minutes (insufficient engagement); overall press rate below 5% or above 95% across all trials (non-engagement or perseveration); more than 20% of trials with missing press data. Trial-level exclusions: watch-only trials (block 1 trials 1–10) excluded from all press rate analyses. Instruction screen rows excluded from all analyses. Only outcome-phase rows used for press rate and outcome calculations. Outlier subjects: press rates more than 3 SD from the group mean on any primary measure will be flagged and reported but not automatically excluded — sensitivity analyses will be run with and without these subjects.

### Missing data
Missing press data on individual trials (e.g. due to browser timeout) will be treated as no-press (0) if the trial was not a watch-only trial and the outcome phase data row exists. Subjects with more than 20% missing trial data will be excluded entirely as specified above. No imputation will be performed. All analyses conducted on available complete cases after exclusions are applied.

### Other planned analysis
SC property type (colour, size, velocity) as a moderator of SC-R discrimination and transfer index — one-way ANOVA across three property groups, with post-hoc comparisons if significant. Learning curve fitting: exponential growth function fit to trial-by-trial SC press rate within block 2, per subject per task. Parameters (asymptote, rate, lag) compared across tasks to characterise transfer at the learning dynamics level. Belief persistence decay: exponential decay function fit to block 3 SC press rate series. Decay constant compared against zero to test whether beliefs are stable or eroding without feedback. OC attribution analysis: block 2 OC press rate reported as a secondary measure of illusion of control, compared against R press rate.

## Other

### Context and additional information
This study is part of a broader research programme examining how self-representation is formalised across the cognitive sciences. The theoretical framework proposes that self-representation emerges through a layered inferential process: multisensory integration establishes the self-other boundary, causal inference extracts relational structure, and contingency — defined as the agent-indexed subset of causal inference — constitutes the computational basis of self-representation at higher levels. The current study operationalises the environmental affordance side of this framework: testing whether property-indexed contingency beliefs formed during causal learning are encoded at the property-type level and transfer across contexts. A planned follow-up study will test whether self-related properties (characteristics of the agent that co-occur with causal efficacy) are encoded by the same mechanism. The computational model (M4) is intended to formalise precision-weighted belief updating over property-indexed causal efficacy within the Active Inference framework. 
Experiment code and data are publicly available at https://github.com/ninaedgley/property_contingency_exp. 
Data will be stored on OSF at https://osf.io/eh4vq.