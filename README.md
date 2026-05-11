# Contingency Simulation

This repository contains the data, code, and analysis relevant to *Self-Representation: Learning Contingency?*, a perceptual decision-making study. It was run in parallel to an ongoing theoretical integrative review, which assesses existing formal computational models of self-representation across the cognitive sciences. 

The review finds that self-representation, traditionally studied across 'levels' of self and interactive complexity (embodied, affective, agentic, social, narrative), can be understood as sharing a common computational goal : encoding the agent's position within the causal structure it perceives in its environment. This is hypothesised to develop primarily through patterns of contingency - causal relationships whose origin can be attributed to the self (kept intentionally distinct in name from Sense of Agency, SoA to avoid confusions between the terms).

The review proposes a layered inferential process: multisensory integration → causal inference → contingency. This experiment operationalises the contingency layer, by hypothesising that contingency is encoded through statistical learning : which properties co-occur reliably with self-indexed causality? When does the agent hold a distinct position in the causal network it observes? 
If this mechanism holds true, learnt property-indexed contingency would transfer across contexts, since it informs self-representation - broader priors over contingency and behavioural affordances over time. 

Property-indexed contingency is operationalised as `SC` in the following experiment - a condition in which action (press) reliably causes the reversal of dot motion. To test the validity of the hypothesis, the experiment was designed with OC (observed-causality) and R (random) conditions, offering alternative interpretations. Each subject performed 2 perceptual decision-making tasks, each sharing the SC property. 

Press rates, learning, and relationships between variables were assessed, alongside 4 candidate computational models. Details can be found below.

- **OSF Preregistration**: https://osf.io/uj92x
- **Data**: https://osf.io/eh4vq


## Experimental Design

- **Code setup for experimental design**: https://github.com/ninaedgley/property_contingency_exp

2 perceptual decision-making tasks for each subject (N = 70) - one involving dots moving in a circular fashion, the other involving squares crossing the screen from right to left. In both tasks, subjects were asked to determine when to press a spacebar, causing the shapes to either reverse their motion direction (T1), or to move upwards (T2). Their presses either caused the reversal, or did not : this depended on specific properties of the shapes.

**Block Structure**
1. 10 watch-only trials, in which subjects either observed random property-outcome relationships, or observed causal structure. This varied per group (described below).
2. 60 press-enabled trials, forming the bulk of observations and learning. For each trial, subjects had 4s to observe the motion of shapes and determine whether to press. 2s would pass (effort to avoid strong binding effects), before the outcome (reversal vs. no change) was revealed. 
3. 20 press-enabled trials, with no outcome shown.

Manipulations involved assigning properties to various roles, varying property assignments across tasks, and a between-subjects manipulation into two groups. Each is described below.

**Property Assignment**
- 3 visual properties were randomised : colour (red & blue in Task 1, green & purple in Task 2), size (large, small), and velocity (fast, slow).
- Properties were assigned one of 3 roles : SC (self-causal), OC (observed-causal), and R (random).
- For trials with SC active : dots would reverse (or squares would move upwards) if subjects pressed (p = 0.95), and would almost certainly not reverse if they did not press (p = 0.05). 
- For trials with OC active : dots would reverse (or squares would move upwards), regardless of whether the subjects pressed (p = 0.9).
- For trials with R active : dots would reverse (or squares would move upwards) minimally, regardless of what the subject did (p = 0.1).
- Within properties, specific values were assigned either active or inactive roles. For example : if `colour` was assigned the `SC` role, one of its values would be treated as active (red), and the other inactive (blue). Across the task, if the subject pressed on trials in which red dots appeared, the dots would reverse. Blue would not be predictive of contingency. As properties are present on all trials (size, colour, velocity being inherent to the visual representation in each task), values, rather than properties as a whole, needed to discriminate between contingency-affording circumstances and not.

**Task Manipulation**
- Task 1 property roles were assigned and kept constant throughout the trials.
- In Task 2, SC remains assigned to the same property - however, OC and R swap. If size was causally predictive of reversal, it became random in T2. Likewise, if velocity was predictive of random outcomes in T1, it became causally predictive of motion change in T2. 

**Group Manipulation**
- Subjects were randomly assigned (p = 0.5) to Group A, or Group B
- Group A's Block 1 trials (across both Task 1 and Task 2) had OC active : they were able to observe reversals and outcomes occurring at the same rate as the rest of the experiment. Since they were unable to press, this meant that they could observe the OC-assigned property reliably co-occurring with motion reversals.
- Group B's Block 1 trials (across both Task 1 and Task 2) showed random associations in reversals. No properties were active, and outcomes occurred randomly.
The rationale was to observe whether any priming effects could be discerned : if OC-observation in Group A reliably predicted higher SC or OC learning rates; on the other hand, whether observing random associations reduced the likelihood of learning causal relationships.


## Results - Key Findings

Hypothesis Tests, analysis, and detailed interpretation of results can be found at `notebooks/03_hypothesis_tests.ipynb`. The pre-registered hypotheses are the following:

1. **SC-R discrimination** - SC press rates will significantly exceed R press rates in block 2, across both tasks. This tests whether participants learn to distinguish self-caused from random outcomes within 60 trials.
2. **Transfer learning** - SC press rates in the first 15 SC trials of Task 2 Block 2 (T2B2) will exceed T1B2 SC press rates. This acts as a proxy for transfer learning across different tasks, and different property values.
3. **Observation priming** - Group A participants (who observe causal structure during the B1 learning block) will reach SC-R press rate criterion faster in block 2 than Group B participants (who only observe random behaviour in their respective learning block). This tests whether observing environmental causal structure seeds self-efficacy belief formation.
4. **Belief persistence** - B3 SC press rates will significantly exceed B2 press rates, indicating that property-indexed causal efficacy beliefs persist in the absence of outcome feedback.

### Hypothesis 1 - supported
The SC > R effect size was found to be statistically significant under the pre-registered one-tailed alpha = 0.05 threshold (t(69) = 2.239, p = 0.0142), but did not survive the Bonferroni correction (alpha = 0.0125). The estimated effect size was small, at d = 0.268, and the 95% CI on the mean difference was [0.007 - 0.122].
To clarify this finding, I conducted a post-hoc analysis - restricting the hypothesis to Task 1 - which survived the Bonferroni correction (p=0.0124, d=0.276). 

### Hypothesis 2 - null
The analyses run for H2 were a primary one-tailed t-test, and a secondary GEE test. Both showed below-threshold significance, at both corrected and uncorrected levels. The tests assumed that SC early-learning in Task 2 would be superior to Task 1. In fact, the direction of transfer is negative : 35.7% of subjects show positive transfer, while 50.0% show negative transfer (< 0). t(69) = -1.432, with Cohen's d = -0.171.
Both results indicate that no transfer learning was evident in the data, and that on the contrary, it might interfere with contingency learning. 

### Hypothesis 3 - null, with counterintuitive finding on exploratory follow-up analysis
The primary H3 test found no evidence that exposure to causal vs. random behaviour during learning blocks affected SC acquisition in block 2 (t = 0.27, p = 0.79, Cohen's d = 0.065). 
Further exploratory analysis of learning dynamics (collapsed across groups A and B) did nonetheless reveal an asymmetry in learning rates : discrimination during block 2 emerges primarily through R suppression (slope = -0.029, d = -0.42, p < 0.001) rather than SC acquisition (slope = 0.003, d = 0.27, p = 0.016). 
I used a paired comparison of slope magnitudes to evaluate whether this was significant - it confirmed it as a large effect (t = 6.97, p = 0.0000, Cohen's d = 0.84).
This challenges my premise for the initial hypothesis : while subjects do learn to respond to SC, the **dominant learning signal and driver of change seems to come from suppression of responses to random-outcome stimuli**. Under this interpretation, contingency learning potentially emerges through avoidance more than approach.

### Hypothesis 4 - supported, with nuance
H4 is supported, but depends on which parameter is selected to describe block 2 press rates.
- When comparing block 3 SC press rates to the block 2 mean SC press rate, I found a statistically significant increase (B2: 0.466 → B3: 0.515; t = 2.79, p = 0.007, d = 0.33). 
- However, when comparing to the last 10 trials of block 2 (the state at the end of active learning), there appeared to be no significant change in press rates (B2 late: 0.499 → B3: 0.515; t = 0.71, p = 0.48, d = 0.09).
This pattern indicates that average SC beliefs formed throughout block 2 *persist without decay* when feedback is removed, reflecting the mean press rate rather than the latest values. Nonetheless, the increase in SC press rates rel. to B2 reflects the learning trajectory within block 2 (SC slope was positive), not a continued learning in block 3. Within-block-3 slopes were flat (M = −0.0008, p = 0.42), confirming press rate stability rather than increase, diffusion, or outright extinction.
Both groups showed similar patterns: Group A changed +0.033 from B2 late, Group B changed −0.004. The absence of decay in either group suggests that contingency beliefs, once acquired, are stable over short timescales without reinforcement. 


## Interpretation

Overall, this experiment was informative, and showed that there is a nuanced interplay in statistical learning of contingency, related co-occurring properties, and whether this occurs at the level of the property, or of its specific values.

Hypothesis 1 findings confirmed that SC > R in Task 1, but not in Task 2. Throughout the analysis, OC dominance was evident : against my expectations, action-neutral causal structure seems to be learnt and acted against more than action-contingent causal structure. This held true when OC changes across Tasks, as the PsyTrack implementation (`notebooks/05_psytrack_implementation.ipynb`) shows - there is clear learning of new property roles as OC and R flip.

Hypothesis 3's counterintuitive findings challenge another one of my expectations going in - that changes in press rates could be attributed to *learning* about contingency relations, or causal structure. In fact, the changes in press rates (when both groups were considered together) showed that it was *suppression* of press-rates on random stimuli that seem to drive changes, not learning.
This finding would support contingency learning and navigating novel tasks via avoidance of random outcomes, rather than leaning into agency.

Finally, Hypothesis 4 confirmed that SC learning is maintained when feedback is removed, suggested a stable prior over press rates, with sufficient precision to persist without reinforcement. Taken together with the findings above, this suggests that SC is learnt, but does not necessarily drive higher press rates. Whether this is due to confusion with OC, the use of a different strategy than expected, or simply due to experimental design cannot be stated confidently. 

I think the main weaknesses in the experimental design come from a potentially difficult / confusing task (several co-occurring properties, relatively short learning blocks) and the underpowered design. I'd be curious to conduct a follow-up study with better experimental design, more trials per individual, and a simpler task.


## Notebooks
```
1. `01_raw_data_analysis.ipynb` — Preprocessing
2. `02_EDA.ipynb` — Exploratory Data Analysis
3. `03_hypothesis_tests.ipynb` — Pre-registered Hypothesis Tests (H1–H4)
4. `04_model_specification.ipynb` — Model Specifications
5. `05_psytrack_implementation.ipynb` — PsyTrack Implementation 
6. `06_model_fitting.ipynb` — Model fitting [planned]
7. `07_model_comparison.ipynb` — Model comparison and implications [planned]
```


## Repo structure
data/ — cleaned and preprocessed data, derived parameters and weights
notebooks/ — code, analysis, and interpretations
output/ — plots and figures referenced from notebooks 01 - 04
psytrack_figures/ — plots referenced in notebook 05, specific to the PsyTrack implementation


## Setup
Notebooks should be run in order. Processed data are included under `data/processed/`; raw Prolific exports were excluded.
`python3.11 -m venv .venv`
`source .venv/bin/activate`
`python -m pip install -r requirements.txt`
`python -m ipykernel install --user --name contingency-simulation`


## Contact
E: nina.edgley@pm.me
